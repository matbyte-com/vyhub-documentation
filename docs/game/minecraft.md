# Minecraft

Download Link:

[https://github.com/matbyte-com/vyhub-minecraft/releases](https://github.com/matbyte-com/vyhub-minecraft/releases)

## Compatible Minecraft Plugin APIs

- Bukkit/Spigot/Paper (>=1.15)
- BungeeCord/Waterfall
- Velocity

## Compatible Permission Mods

One of the following permission mods is required to enable the group-sync between VyHub and Minecraft:

- [LuckPerms](https://luckperms.net)

## Installation

### Standalone (Bukkit/Spigot/Paper)

1. In VyHub open the `Add Server` dialog in the `Server` settings and create the server.
2. Click on the `Setup` button of the server and follow the instructions.
3. Optionally, adjust the config files to your needs.

### Proxy (BungeeCord/Velocity/Waterfall)

- The simplest way to set up VyHub within a proxy network is to create only one server and let every server use the same
  api-key.
- It is also possible to group some backend-servers into other serverbundles (like Citybuild and Jump&Run). This brings the advantage to specify
  different rewards/commands for different servers. We then recommend hiding the backend-servers from users using the
  `hidden` option in the server settings. This will hide servers from the players view.

> **!Important!** It is necessary to take care of data consistency with **UUIDS**.
> - BungeeCord/Waterfall: set `ip_forward` and `bungeecord` options to true
> - Velocity: use `modern` forwarding set `proxies.velocity.enabled` and `proxies.velocity.online-mode` to true. Set
    `proxies.velocity.secret` to match the `forwarding.secret` of your Velocity proxy.

> When using the same VyHub server_id for the backend servers and the proxy, make sure to set the `is_backend_server`
> option on your backend_servers to true. Then servers will not send their online players anymore, your proxy will take
> care of this.

## Group Sync

You can sell groups and VIP-ranks through VyHub for your gameserver. Syncing the user groups can be either done through
a command or by using the VyHub Group-Sync feature. Read more about syncing groups in
the [group](../guide/group/group_sync.md) guide.

> Group-Sync is deactivated when no permission-mod is found

User groups are automatically synced. For this to work correctly, the [serverbundle](../guide/server.md) must be in
`multigoup: enabled` mode.

VyHub group names can be mapped to in-game groups at the `Advanced Properties` tab in the [group](../guide/group/group.md)
settings.

## Bans and Warnings

> Bans and Warnings are synced between servers within one serverbundle.

When using a proxy network: When all backend servers are in one serverbundle, bans are global.

## Rewards

For Minecraft, the following types of rewards are supported:

- `COMMAND`: Executes a console command on the server

### Available replacements

The following string replacements are available for rewards:

- `%user_id%`: The VyHub user id
- `%nick%`: The players in-game nickname
- `%player_id%`: The players minecraft UUID
- `%player_ip_address%`: The player IP address
- `%applied_packet_id%`: The id of the applied packet
- `%packet_title%`: The title of the packet
- `%purchase_amount%`: Total amount with currency of the purchase. For example `30 EUR`. If packet was applied without
  purchase: `-`.

## Commands

- `/timeban <player> <minutes> <reason>`: Ban a player for the specified time.
- `/warn <player> <reason>`: Warn a player
- `/vylogin <token>`: Login to the VyHub website with a given token
- `/vh_config <key> <value>`: Set a config option
- `/vh_setup <api-key> <api_url> <server_id>`
