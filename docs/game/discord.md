# Discord

VyHub allows you to monetize your Discord server. It is possible to sync groups between VyHub and Discord.

The `Authorization` settings configure the login providers of your instance. They are split into a **Steam** and a
**Discord** tab.

## Steam

| Attribute | Description |
|-----------|-------------|
| Steam API Key | It's highly recommended to set your Steam API key here. It is used to fetch user data from Steam. Get one at the [Steam API key page](https://steamcommunity.com/dev/apikey). |

## Authorization Setup

1. In your VyHub instance go to the `Authorization` settings and enable Discord.
2. Go to the [Discord Developer Portal](https://discord.com/developers/applications) and create a new application.
3. Get your `client_id` and `client_secret`.
4. Enter the redirect URL shown in the `Authorization` settings.
   ![Discord Developer Settings](../assets/authorization_guide/discord_developer_portal.png)
5. Get your `bot_token` and enable the `presence` and `members` intent.
   ![Discord Bot Settings](../assets/authorization_guide/discord_bot_settings.png)

The following fields are available on the `Discord` tab of the `Authorization` settings:

| Attribute | Description |
|-----------|-------------|
| Discord | Toggle that enables Discord as a login provider. The fields below appear once it is enabled. |
| Client ID | The OAuth client ID of your Discord application (digits only). |
| Client Secret | The OAuth client secret of your Discord application. |
| Bot Token | The token of your Discord bot. |
| Discord Redirect URL | Read-only URL that must be added as a redirect URL in the Discord Developer Portal. |

## Setup

1. In VyHub open the `Add Server` dialog in the `Server` settings.
2. Get your `Guild ID` and enter it as the servers address
    - In Discord, open the server settings, go to `Widget` and copy the guild id
      ![Discord Role Permissions](../assets/game_integration_guide/discord_guild_id.png)
3. Create the server
4. Click on the `Setup` button of the server.
5. Click on the `Add` button to add the Bot to your Discord server.
    - The link can also be created manually:
      `https://discord.com/api/oauth2/authorize?client_id={discord_application_id}&permissions=268438545&scope=bot`
6. Make sure the bot can change roles.
    - In Discord, open the server settings.
    - Go to `Roles` and drag and drop VyHub Bot above groups you want to have synced.
      ![Discord Guild Id](../assets/game_integration_guide/discord_roles.png)

   > For higher security don’t allow the bot to sync admin groups.

## Group Sync

User groups are automatically synced.

VyHub group names can be mapped to server/in-game groups at the `Mappings` tab in the [group](../guide/group/group_sync.md)
settings. Please pay attention to capitalization.

> It is possible to use "role names" or "role ids" in the `mappings`

## Notifications

The discord bot can send notifications about Bans / Warnings / Purchases.

1. Set up the Discord bot by following the steps above and use the following commands directly in Discord.
2. Use command `/enable_notifications` to enable notifications by specifying the channel where to send notifications to
    - `channel` argument is required.
    - The other arguments are optional and allow you to set specific channels for different notification types.
3. [Optional] Use the command `/configure_notifications` to configure the message layout of the messages sent by the
   bot.

### Available Configuration Options

- Different channels for each notification type
- Enable / disable each notification type independently
- Set embeds title and description for each notification type independently

### Available Variable Replacements

- `{username}`
- `{reason}`
- `{length}`
- `{serverbundle}`
- `{packets}`
- `{purchase_amount}`
- `{frontend_url}`
- `{issuer}` (Bans and Warnings only)
- `{ticket_title}` (Tickets only)

## Troubleshooting

__Problem:__ Roles are not synced with Discord.

__Solution:__ Make sure roles have the exact name as provided to VyHub (Capitalization / Whitespaces...) and that the
VyHub role has higher permissions than other roles.
Also have a look in the logs; the Discord errors might help, when the bot can't connect to the Discord API.

__Problem:__ Notifications don't appear, even though I set up the notification channel.

__Solution:__ Make sure the bot has the required message write rights in the chosen channel.
