# Rewards

Rewards are executed when a user purchases a packet. They can be used to give users in-game items, ranks, or execute
HTTP requests.

> A reward needs to be assigned to a packet to be able to be bought by your players / your customers.

New rewards can be created from scratch (`Create Reward`) or from ready-made **Templates** for supported games. The
available reward type and options depend on the selected serverbundle's server type.

## General

| Attribute                                        | Description                                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Name                                             | Name of the reward                                                                                                                                                                 |
| Serverbundle                                     | The reward is executed on all servers in the selected serverbundle, including servers added later. Can be left empty for rewards that are not serverbundle specific.               |
| Type                                             | The reward type (see below). Selectable once a serverbundle is chosen.                                                                                                             |
| Execute on event                                 | Event on which the reward is executed (see [Events](#events))                                                                                                                      |
| Limit to servers                                 | [Optional] Limit execution to the selected servers of the serverbundle. If none are selected, the reward runs on all servers in the bundle. (COMMAND, SCRIPT, TEAMSPEAK_CHANNEL)   |
| Only execute once (per packet)                   | If enabled, the reward is only executed once across ALL servers in the serverbundle, instead of every time the event happens                                                        |
| Only execute on one server                       | If enabled, the reward is only executed on the first server the user connects to. Must be combined with *Only execute once*.                                                        |
| Execute again if packet has been extended        | Execute this reward again if the packet has been extended (e.g. on a subscription payment)                                                                                         |

> The *Only execute once*, *Only execute on one server* and *Execute again if packet has been extended* options are only
> available for the COMMAND, SCRIPT and HTTP reward types.

## Reward Types

The reward type determines what the reward does. Which types are offered depends on the server type of the selected
serverbundle.

| Type              | Description                                    | Availability                                                    |
|-------------------|------------------------------------------------|----------------------------------------------------------------|
| COMMAND           | Execute a command on the server(s)             | All server types except Teamspeak 3 and Discord                |
| SCRIPT            | Execute a script on the server(s)              | GMOD and FiveM only                                            |
| CREDITS           | Add credits to the buyer's account             | All server types                                              |
| MEMBERSHIP        | Add a group membership                         | All server types                                              |
| HTTP              | Send an HTTP request                           | All server types                                              |
| TEAMSPEAK_CHANNEL | Create a Teamspeak channel                     | Teamspeak 3 only                                              |

### Type-specific fields

| Type              | Fields                                                                                                                                            |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| COMMAND           | **Command** – the command to execute (with autocomplete)                                                                                        |
| SCRIPT            | **Script** – the script to execute                                                                                                              |
| CREDITS           | **Credits** – amount of credits to add                                                                                                          |
| MEMBERSHIP        | **Group** – the group the membership is assigned to                                                                                            |
| HTTP              | **Method** (GET/POST/PUT/DELETE/PATCH), **URL**, **Number of Retries** (1-10, default 3) and optional **Headers** (key/value pairs)             |
| TEAMSPEAK_CHANNEL | **Parent Channel ID**, **Channel Group ID**, **Client Limit** and **Delete on expiration**                                                     |

## Events

The **Execute on event** option controls when the reward is triggered. The available events depend on the reward type.

| Event                    | Description                                                    |
|--------------------------|---------------------------------------------------------------|
| Execute directly         | Execute the reward immediately                                 |
| Execute on connect       | Execute when the user connects (COMMAND / SCRIPT only)         |
| Execute on spawn         | Execute when the user spawns (COMMAND / SCRIPT only)          |
| Execute on death         | Execute when the user dies (COMMAND / SCRIPT only)            |
| Execute when applied packet becomes inactive | Execute when the applied packet becomes inactive |

> COMMAND and SCRIPT rewards offer all events. CREDITS, MEMBERSHIP and HTTP rewards only offer *Execute directly* and
> *Execute when applied packet becomes inactive*. TEAMSPEAK_CHANNEL rewards are always executed directly.

## Testing your Rewards

To test your rewards, assign them to a packet.

After that, you have two options to test the rewards:

**Option 1**

Buy the packet in the shop. For example, use a 100% discount, or use a credit gateway.

**Option 2**

You can also manually apply the packet to the user.

Go to the  `Add applied packet` dialog. This dialog can be found in the
`Shop Administration` -> `Applied Packets` -> `Add applied packet`

## In-Game Rewards

VyHub works by executing commands on your server when a user buys a [packet](./packet.md).

Usual in-game reward types are `COMMAND` and `SCRIPT`.

For these types, string replacements can be used to insert player-specific data into the command or script; furthermore,
the User needs to be connected to the server.

The game-specific replacements are available in the docs of the game [integrations](../../game/integrations.md).

## Group Membership Rewards

Group membership rewards can be used to assign a user to a group on your server when they purchase a packet.

The use of the membership rewards is optional, you can also use the simple `COMMAND` reward type to assign groups.

Read more about the differences between the user sync and the commands in the [group](../group/group_sync.md)
documentation.

## HTTP Rewards

HTTP rewards can be used to send an HTTP request to a custom URL when a user purchases a packet.
They can be used to integrate with custom systems.

## Variable Replacements

For HTTP rewards and RCON server rewards, the following variable replacements can be used to insert user-specific data
into the URL or command.
For all other supported games, the replacements are documented in the respective game documentation.

> **Important:** If you want to make sure that the replacements contain the data of
> a specific user type (e.g., STEAM), select a serverbundle for the reward that belongs to the user type. Due to the
> architecture of VyHub, a user can have different accounts connected. If no serverbundle is selected for the reward,
> the
> user type is not guaranteed as the purchasing user account is used for replacements then.

The following variables within the URL are replaced:

- `%user_id%`: The VyHub user id
- `%user_type%`: The type of the VyHub user (e.g., STEAM, DISCORD, MINECRAFT, ...)
- `%user_identifier%`: The users identifier (e.g., steamid, discord id, minecraft uuid, ...)
- `%username%`: The user's nickname
- `%serverbundle_name%`: The serverbundle name
- `%serverbundle_id%`: The serverbundle id
- `%packet_name%`: The packet name
- `%packet_id%`: The packet id
- `%applied_packet_id%`: The applied packet id
- `%purchase_id%`: The purchase id
- `%purchase_amount%`: The purchase amount with currency
- `%purchase_amount_total%`: The purchase total amount
- `%purchase_amount_net%`: The purchase net amount
- `%purchase_amount_tax%`: The purchase tax amount
- `%purchase_amount_credits%`: The purchase credits
- `%currency_code%`: The currency code
- `%currency_symbol%`: The currency symbol




