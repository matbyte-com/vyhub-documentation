# Setup VyHub Selfhosting

This is the setup guide for VyHub Selfhosting.
The Selfhosting version allows you to host VyHub on your own server.

## Prerequisites

For hosting VyHub, some requirements must be met:

- **Someone who knows how to use linux and docker**
- A linux server (virtual or dedicated)
    - At least 2 CPU cores and 4GB RAM
    - If a virtual server is used, make sure that the vCPU supports `x86-64-v2` or higher. A script that displays the supported architecture can be found at `tools/cpucheck` in the `vyhub-onprem` repository.
    - Recommended: A recent Debian or Ubuntu LTS version
    -  [Install Docker Server](https://docs.docker.com/engine/install/#server)
    -  [Install Docker Compose Plugin](https://docs.docker.com/compose/install/linux/#install-using-the-repository)
- A domain
    - Create an A (and if available AAAA) DNS record that points to your server
    - If using Cloudflare, set the security level for the `/api` path to `Low`
- An SSL certificate
    - When not using Cloudflare: Setup certbot to get a LetsEncrypt certificate
    - When using Cloudflare: Generate a free origin certificate on the Cloudflare dashboard
- Backup
    - You should regularly create backups  of your server, including the VyHub database

## Creating and activating the selfhosting instance

1. Navigate to [https://app.vyhub.net/new-instance](https://app.vyhub.net/new-instance) and select `Self-Hosted`
2. Insert the name of your instance and your domain
3. Finish the instance creation
4. Got to your instance dashboard and activate your instance by choosing a plan and finishing the payment

## Installing

1. Connect to your server via SSH (all following steps are done on the server)
2. Clone the `vyhub-onprem` repository:

    ``` bash
    git clone https://github.com/matbyte-com/vyhub-onprem.git /opt/vyhub-onprem
    ```

3. Navigate into the `vyhub-onprem` folder and run `first-setup.sh`:

    ``` bash
    cd /opt/vyhub-onprem
    ./first-setup.sh
    ```

4. Put your SSL certificate and key in the folder `/opt/vyhub-onprem/nginx/certs/`. They should be in PEM format and named `vyhub.crt` and `vyhub.key`.

    If you are using certbot, consider creating a symbolic link to the actual cert/key with `ln -s`.

5. **SWITCH** Go to the dashboard of your instance at [app.vyhub.net](https://app.vyhub.net) and click on the `Setup` button. Follow the instructions there.

6. **SWITCH BACK** After finishing the setup dialog, go back to this page.

7. In `.env`, insert your Steam API key that can be generated [here](https://steamcommunity.com/dev/apikey).

    If you know wht you are doing, you can further adjust config parameters. They are documented [here](https://github.com/matbyte-com/vyhub-onprem#environment-variables).

8. In `docker-compose.override.yml`, change the vyhub image version to the newest version (see [changelog](../changelog.md))

9. Start VyHub via docker compose:

    ``` bash
    docker compose up -d
    ```

    Check that all 6 containers are running:
    ``` bash
    docker compose ps
    ```

    If a container is missing or is not running, check the logs with:
    ``` bash
    docker compose logs <service-name>
    ```

10. Visit your VyHub instance and check that everything works.

## Updating

To update your VyHub instance, follow these steps:

1. Update the `vyhub-onprem` repository:
    ``` bash
    git pull
    ```

2. Adjust the version number in `docker-compose.override.yml`

    The version numbers are built like this: `{major}.{minor}.{patch}`.
    To be sure, only update one minor version after another. 

    > Example: You want to update from `2.0.7` to `2.2.1`
    >
    > Solution: Update to the newest version of `2.1` (e.g. `2.1.3`) first and update to `2.2.1` afterwards.


3. Restart the containers:
    ``` bash
    docker compose up -d --force-recreate
    ```

4. Check that all 6 containers are running:
    ``` bash
    docker compose ps
    ```

    If a container is missing or is not running, check the logs with:
    ``` bash
    docker compose logs <service-name>
    ```