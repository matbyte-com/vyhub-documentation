# Ark Survival Ascended

> This plugin is currently only community supported. It is not maintained by the VyHub team. If you want to help us,
> please open a pull request or contact us.

Download Link:
[https://github.com/matbyte-com/vyhub-ark-sa/releases](https://github.com/matbyte-com/vyhub-ark-sa/releases)

## Features

- Shop / Donation Store
- Server Status
- Collect Playtime of your players

> The ASA plugin only supports the listed features. Other features are not (yet) implemented. Feel free to open pull
> requests and contribute to the plugin.

## Installation

1. In VyHub open the `Add Server` dialog in the `Server` settings and create the server.
2. Click on the `Setup` button of the server and follow the instructions.
3. Optionally, adjust the config files to your needs.

### Debug

It can happen that the command `/vh_setup` does not save the necessary settings. In that case, you can also try to run
the command from in-game as an admin.

As a last resort, you can also manually edit the `config.json` file in the plugin folder. The file is located in
`/Plugins/VyHub/Config/config.json`.

### Libcrypto and Libssl

> If you get error 126 on a load, you must install [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html)

## Group Sync

> Only direct commands are supported. The plugin does not support `VyHub Group Sync`.

You can sell groups and VIP-ranks through VyHub for your gameserver. Syncing the user groups can be either done through
a command or by using the VyHub Group-Sync feature. Read more about syncing groups in
the [group](../guide/group/group_sync.md) guide.

## Rewards

For Ark Survival Ascended, the following types of rewards are supported:

- `COMMAND`: Executes a console command on the server

### Available replacements

The following string replacements are available for rewards:

- `%user_id%`: The VyHub user id
- `%nick%`: The players in-game nickname
- `%player_id%`: The players EOSID
- `%applied_packet_id%`: The id of the applied packet
- `%packet_title%`: The title of the packet
- `%purchase_amount%`: Total amount with currency of the purchase. For example `30 EUR`.

## Commands

- `/vylogin <token>`: Login to the VyHub website with a given token
- `/vh_setup <api-key> <api_url> <server_id> <serverbundle_id>` Setup command (only functional in server-console)
