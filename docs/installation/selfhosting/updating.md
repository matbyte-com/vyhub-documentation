# Updating

=== "Manual"

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

=== "Automated (Hetzner Cloud)"

    A systemd timer keeps the stack current with no manual maintenance:

    | Timer | Fires (local time) | Action |
    |-------|--------------------|--------|
    | `apt-daily-upgrade.timer` | ~01:00 ± 30 min | `unattended-upgrades` installs Debian + Docker apt updates |
    | (auto-reboot) | 02:00 | reboot if a kernel update required it |
    | `vyhub-onprem-update.timer` | ~03:30 ± 30 min | `git pull --ff-only && docker compose pull && docker compose up -d` |

    Inspect or control on the server:

    ``` bash
    systemctl list-timers --all | grep -E 'vyhub|apt-daily'
    journalctl -u vyhub-onprem-update.service  # container update logs
    journalctl -u unattended-upgrades.service  # OS upgrade logs
    sudo /opt/vyhub-onprem/setup/install.sh update   # run a container update on demand
    ```
