# Setup

This is the setup guide for VyHub. VyHub is fully self-hosted and runs on your own server.

## Creating and activating the instance

1. Navigate to [https://app.vyhub.net/new-instance](https://app.vyhub.net/new-instance) and create your instance
2. Insert the name of your instance and your domain
3. Finish the instance creation
4. Go to your instance dashboard

## Installing

Pick whichever matches what you already have.

=== "Manual"

    Use this if you already have a Debian or Ubuntu server and want to wire up `docker compose` yourself.

    ### Prerequisites

    - **Someone who knows how to use linux and docker**
    - A linux server (virtual or dedicated)
        - At least 2 CPU cores and 4GB RAM
        - If a virtual server is used, make sure that the vCPU supports `x86-64-v2` or higher. A script that displays the supported architecture can be found at `tools/cpucheck` in the `vyhub-onprem` repository.
        - Recommended: A recent Debian or Ubuntu LTS version
        - [Install Docker Server](https://docs.docker.com/engine/install/#server)
        - [Install Docker Compose Plugin](https://docs.docker.com/compose/install/linux/#install-using-the-repository)
    - A domain
        - Create an A (and if available AAAA) DNS record that points to your server
        - If using Cloudflare, set the security level for the `/api` path to `Low`
    - An SSL certificate
        - When not using Cloudflare: Setup certbot to get a LetsEncrypt certificate
        - When using Cloudflare: Generate a free origin certificate on the Cloudflare dashboard
    - Backup
        - It is highly recommended to set up a backup solution for your server

    ### Steps

    1. Connect to your server via SSH (all following steps are done on the server)
    2. Clone the `vyhub-onprem` repository:

        ``` bash
        git clone https://github.com/matbyte-com/vyhub-onprem.git /opt/vyhub-onprem
        ```

    3. Navigate into the `vyhub-onprem` folder and run `gen-secrets.sh`:

        ``` bash
        cd /opt/vyhub-onprem
        ./gen-secrets.sh
        ```

    4. Put your SSL certificate and key in the folder `/opt/vyhub-onprem/nginx/certs/`. They should be in PEM format and named `vyhub.crt` and `vyhub.key`.

        If you are using certbot, consider creating a symbolic link to the actual cert/key with `ln -s`.

    5. In the VyHub Setup dialog on [vyhub.net](https://app.vyhub.net) choose **Manual (existing Debian / Ubuntu server)**.

    6. Log in to the VyHub container registry. Copy the `docker login` command shown in the Setup dialog and run it on the server - this is required to pull the VyHub image.

    7. Paste the `VYHUB_*` env block from the Setup dialog into `.env`.

    8. In `.env`, insert your Steam API key that can be generated [here](https://steamcommunity.com/dev/apikey).

        If you know what you are doing, you can further adjust config parameters. They are documented [here](https://github.com/matbyte-com/vyhub-onprem#environment-variables).

    9. In `docker-compose.override.yml`, change the vyhub image version to the newest version (see [changelog](../../changelog.md))

    10. Start VyHub via docker compose:

        ``` bash
        docker compose up -d
        ```

        Check that all 7 containers are running:
        ``` bash
        docker compose ps
        ```

        If a container is missing or is not running, check the logs with:
        ``` bash
        docker compose logs <service-name>
        ```

    11. Visit your VyHub instance and check that everything works.

=== "Automated (Hetzner Cloud)"

    Use this if you have no server yet and want everything provisioned for you. The setup script uses [OpenTofu](https://opentofu.org) to spin up a Debian 13 + Docker VM on [Hetzner Cloud](https://www.hetzner.com/cloud), runs the full installer, and optionally requests a Let's Encrypt certificate. Nightly auto-updates, self-healing healthchecks, and daily DB backups are configured out of the box.

    ### Prerequisites

    **On your laptop (a Linux machine, or WSL on Windows):**

    - [`tofu`](https://opentofu.org/docs/intro/install/) >= 1.6
    - `ssh`, `ssh-keygen`, `curl`, `jq`, `openssl`
    - An SSH keypair (`~/.ssh/id_ed25519` or `~/.ssh/id_rsa`)

    **In the cloud:**

    - A [Hetzner account](https://accounts.hetzner.com/signUp)
    - A Hetzner Cloud project: <https://console.hetzner.cloud/projects> → **+ New project**
    - An API token with **Read & Write** permission for the project: open the project, **Security → API Tokens → Generate API Token**. Copy the token immediately - Hetzner only shows it once.

    ### Steps

    1. Clone the `vyhub-onprem` repository and run the setup script on your laptop:

        ``` bash
        git clone https://github.com/matbyte-com/vyhub-onprem.git
        cd vyhub-onprem
        ./hcloud-setup.sh
        ```

    2. The script will:

        1. Ask for the Hetzner API token, location, server type and SSH key
        2. Ask for the VyHub config string. Open the Setup dialog on [vyhub.net](https://app.vyhub.net), choose **Automated (Hetzner Cloud)** and paste the single string shown there. It carries both the `VYHUB_*` env block and the registry credentials.
        3. Provision a Debian 13 VM with a firewall that only allows TCP 22/80/443
        4. Run the installer on the VM (Docker, secrets, stack startup) via cloud-init
        5. Print the A/AAAA DNS records you need to create
        6. Optionally request a Let's Encrypt certificate once DNS resolves

    3. Visit your VyHub instance and check that everything works.

    The script is idempotent. If something fails mid-way, you can re-run individual steps:

    ``` bash
    ./hcloud-setup.sh apply      # re-run `tofu apply` with the saved tfvars
    ./hcloud-setup.sh outputs    # show server IPs + management cheatsheet
    ./hcloud-setup.sh wait       # block until cloud-init finishes (streams the log)
    ./hcloud-setup.sh logs       # tail the cloud-init / install.sh output log
    ./hcloud-setup.sh ssh        # ssh root@<server>
    ./hcloud-setup.sh certbot    # request / replace the Let's Encrypt cert
    ./hcloud-setup.sh redeploy   # destroy + reprovision from scratch
    ./hcloud-setup.sh destroy    # delete the Hetzner resources
    ```

