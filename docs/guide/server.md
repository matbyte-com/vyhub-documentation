# Server / Serverbundle

Gameservers are organized within serverbundles for grouping and better management.

`Servers` within the same `serverbundle` are from the same type (e.g. GMod, Minecraft).

`Serverbundles` are an abstraction from `servers`.  
Other features of VyHub like [Bans/Warnings](ban_warning.md) and the [Shop](shop/general.md) are using
serverbundles.

## Attributes

### Serverbundle

| Attribute       | Description                                                                              |
|-----------------|-----------------------------------------------------------------------------------------|
| Name            | Name of the serverbundle                                                                 |
| Type            | Server type of the bundle (e.g. GMod, Minecraft, Discord). All servers within the bundle share this type. |
| Multiple Groups | Users can be a member in multiple groups at once in this bundle.                         |
| Icon            | Icon displayed for the serverbundle                                                      |
| Default Group   | Default group every user (also non-logged-in users) has by default in the serverbundle. |

Serverbundles can be reordered via drag & drop. Each bundle also provides
[API Keys](#serverbundle-api-keys) (except for Discord and Teamspeak 3 bundles).

> Deleting a serverbundle also deletes all depending objects (rewards, servers, bans, warnings, ...). This action cannot be undone.

### Server

The server dialog shows a common set of fields plus additional fields depending on the selected type.

| Attribute    | Description                                                     |
|--------------|-----------------------------------------------------------------|
| Name         | Name of the server                                              |
| Hidden       | If enabled, the server is hidden from the public server list    |
| Type         | Server type (e.g. GMod, Minecraft, Discord, Teamspeak 3, Source, FiveM, Rust, 7 Days To Die, ARK: Survival Ascended) |
| Serverbundle | Serverbundle the server is assigned to                          |
| Address      | Server address (for Discord, enter the guild ID here)          |
| Port         | Port on which the service is running (not used for Discord)     |

#### Garry's Mod specific

| Attribute                | Description                                                                                                                                        |
|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| Sync Bans                | [Advanced] Enable ban sync for the server. Requires that groups are set up correctly and mapped to in-game groups.                                |
| Number of reserved slots | [Advanced] Number of player slots reserved for users in privileged groups.                                                                        |
| Keep reserved slots free | [Advanced] If enabled, reserved slots are always kept free so privileged users can join even if the server is full. The newest non-privileged user is kicked. |
| Hide reserved slots      | [Advanced] If enabled, reserved slots are not shown in the server list. Recommended together with the previous option.                            |

#### Teamspeak 3 specific

| Attribute      | Description                                             |
|----------------|--------------------------------------------------------|
| SSH Query Port | Query port of your TS3 server. The standard port is 10022. |
| Username       | Username used to connect to the server                 |
| Password       | Password used to connect to the server                 |

#### Source specific

| Attribute     | Description                    |
|---------------|--------------------------------|
| RCON Password | RCON password of the server    |

## Connect a new Gameserver

Navigate to the `Server` settings.  
Press the `Add Server` button and follow the steps in the dialog. A serverbundle must exist before a server can be added.

After you have added the server in your `VyHub instance` you need to install one of our plugins on your server.
Use the `Setup` action on a server to generate the setup commands / bot invite link for its type. A colored status
indicator next to each server shows whether it is online, offline or unknown.

## Serverbundle API Keys

Each serverbundle (except Discord and Teamspeak 3) can have API keys, which are used by integrations to
authenticate against VyHub. In the `API Keys` dialog you can:

- Create a new API key by entering a name and optionally selecting additional properties (scopes). The created
  token is shown once and can be copied.
- View existing keys with their name, hidden token and properties.
- Revoke a key (revoked keys are marked accordingly).

## Server Dashboard

The server dashboard shows current server information like a list of online players.

It can be accessed through the server-status on the startpage (news) or directly through the url:

- `https://<frontend-url>/server-dashboard/<server-id>`: The dashboard of the server with the respective server id


