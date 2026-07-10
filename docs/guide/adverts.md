# Adverts

Adverts are messages that are printed in the server chat regularly. Think of them like a newsletter for your server.
The interval can be changed per server in the configuration file of the game integration.

## Attributes

| Attribute    | Description                                                             |
|--------------|-------------------------------------------------------------------------|
| Title        | Title of the advert, not shown to users.                                |
| Content      | The content that should be printed to the chat. Multiple lines allowed. |
| Enabled      | Whether the advert is active and printed to the chat.                   |
| Color        | The color of the advert message. Not supported by Minecraft.            |
| Serverbundle | The serverbundles where the advert should be shown.                     |

Adverts can be reordered via drag and drop, and edited or deleted using the buttons on each entry.

## Text Colors
It is possible to change the text color within the message by using color tags.

Example:
`This is white. <green>This is green.</green> <red>This is red.</red>`

Available colors are:

- red
- green
- blue
- yellow
- pink

### Minecraft
In Minecraft, additional colors can be used by using the `§` notiation.

See `Chat Codes` [here](https://www.digminecraft.com/lists/color_list_pc.php).

## Interval

The interval is the time between two adverts. The interval can be changed in the config file of the game integration.

## Prefix
A prefix is printed before every line. The prefix can be changed in the config file of the game integration.
