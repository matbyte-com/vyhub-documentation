# Bans and Warnings

Bans and Warnings are another cool feature of VyHub. They make sure you are able to enforce rules on your server and
make it also more transparent for the players. Your player can always see their current warnings and bans on your VyHub
instance. There they are, for example, also able to protest a ban.

## Warnings

Warnings are a way to let users know that they did something wrong, without banning them.
You can configure in the settings, after how many warning a ban gets issued.

You can also integrate the Warning System with other plugins that automatically issue warnings.

### Attributes

| Attribute    | Description                                                             |
|--------------|-------------------------------------------------------------------------|
| User         | User that is being warned                                               |
| Reason       | Reason for the warning                                                  |
| Serverbundle | Serverbundle the warning is targeting and where the ban is then created |

When editing a warning, only the `Reason` can be changed.

### Add / Edit

Warnings can be added and edited through the designated `warning` page.

### Warning Settings

You can find further warning configurations in the settings.

| Attribute                                 | Description                                                                    |
|-------------------------------------------|-------------------------------------------------------------------------------|
| Warning Time To Live (days)               | Time (in days) until a warning is marked as expired                           |
| Number of warnings till automatic ban     | How many `active` warnings a user needs to get banned (0 for no automatic bans) |
| Length of automatic ban (minutes)         | How long (in minutes) a user is banned once the warning threshold is reached  |

Users are banned automatically when they reach the specified number of `active` warnings.

## Bans

Bans are targeting a user in one specific **[serverbundle](server.md)**. Global Bans across all serverbundles are also
possible, by leaving the serverbundle field blank.

### Attributes

| Attribute    | Description                                                          |
|--------------|---------------------------------------------------------------------|
| User         | User that is being banned                                           |
| Reason       | [Optional] Reason for the ban                                       |
| Length       | [Optional] Length of the ban in minutes (empty for lifetime ban)   |
| Serverbundle | [Optional] Serverbundle the ban is targeting (empty for global ban) |

When editing a ban, the `Reason`, `Length` and `Serverbundle` can be changed.

### Add / Edit

Bans can be added and edited through the designated `Bans` page.

### Ban Settings

You can find further ban configurations in the settings.

| Attribute                 | Description                                                                                              |
|---------------------------|--------------------------------------------------------------------------------------------------------|
| External ban protest URL  | [Optional] Leave empty for the VyHub ticket system, or enter a link to redirect users to an external site |

### Protests

Users can create ban protests for active bans. By default, Ban protests are shown as a ticket. There can only be one
open protest and a maximum of three total protests per ban.   
You can set a `Ban Protest URL` in the settings. Instead of creating a ticket, users are redirected to this site.

The button is disabled, when the `Ticket-System` is disabled and when there is no `Protest-Ban` URL set.

### Max ban length

You can assign a maximum ban length to groups. A user can then only create bans of the length the `maximum ban length`
property of the group with the highest permission level.

### Website Bans

Players can be banned from your VyHub website as well. Just add them to the `Banned (Website)` group.
The group prevents users from using the shop, creating tickets and posting in the forum. The 3 relevant negative
properties are `shop_use`, `ticket_create`, `forum_post`.


