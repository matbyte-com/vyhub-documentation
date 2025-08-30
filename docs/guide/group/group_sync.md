## Group Sync / User Sync

Many server owners want to sell VIP ranks or other group related perks to their users.

VyHub has two ways to make this possible. The simple use of commands, or the more advanced group sync.

### Commands

The use of commands is the simplest way to assign groups to users. You can use the `COMMAND` reward type to assign
groups to users.

Setting up this command is basic and works with any gameserver type.

A command might look like this:

- Garry's Mod: `ulx adduser %player_id% vip`
- Minecraft: `lp user %player_id% parent add vip`

### Group Sync

VyHub's group sync is a more advanced way to assign groups to users. It is more complicated to set up, but it offers
some cool advantages over the simple command solution.

1. The current groups of a user are displayed in the VyHub user dashboard. This allows players to directly distinguish
   between VIPs, admins, etc.
2. The group sync is a two-way sync. This means that if a user is assigned a group in-game, this group is also assigned
   in VyHub.
3. The group sync is less error-prone, as the groups are kept in sync, and it is not dependent on commands that might
   fail.

> For the group sync to work correctly, a group-mapping must be specified in the [group](./group.md) settings.



