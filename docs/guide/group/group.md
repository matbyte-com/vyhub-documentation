# Groups

Groups are used to organize users and assign permissions to them. The use of this feature is optional and depends on
your use case.

## Attributes

Groups are configured in a dialog split into three tabs: `General`, `Properties` and `Mappings`.

### General

| Attribute        | Description                                                                                                                                                                             |
|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Name             | Name of the group (required)                                                                                                                                                           |
| Permission Level | Used to determine the ability to target other users (required, 0 - 100000)                                                                                                             |
| Max Ban Length   | [Advanced, Optional] Max length of bans the user can create, in days (0 - 365). Leave empty for infinite bans.                                                                         |
| Color            | Color the group is displayed with                                                                                                                                                     |
| Is Team          | Members of the group will be shown on the team page                                                                                                                                   |
| Protected        | Changes to memberships in this group are not allowed from third party applications like gameservers. Additionally, members of this group might be protected from bans.                |

### Properties

| Attribute          | Description                                                                     |
|--------------------|--------------------------------------------------------------------------------|
| Properties         | Permission management and access control for functionalities                   |
| Negated Properties | [Advanced] Negated properties (e.g. ban players from your website)             |

### Mappings

| Attribute                            | Description                                                                                           |
|--------------------------------------|-----------------------------------------------------------------------------------------------------|
| Serverbundle                         | Serverbundle the mapping is scoped for. Leave empty to make the mapping valid for all serverbundles. |
| Name of the group/rank/role          | Name of the group/rank/role on the server                                                            |

## Managing Groups

The group overview lists all groups sorted by permission level. For each group you can:

- Duplicate the group (a copy suffixed with `(Copy)` is created).
- View the active memberships of the group.
- Edit or delete the group.

## Assigning Groups

Groups can be assigned to users in the `User Dashboard` in the group section.
Furthermore, groups can be used as a reward in the shop can be assigned automatically through the
`VyHub Group` [shop reward](../shop/reward.md).

## Properties

Properties are used to control the user right management and access control. They can be used to restrict access to
certain pages, features, or actions. For example, only user groups with the `ban_create` property can create bans
through the website.

Learn more about properties in the [properties](./property.md) guide.

## Group Mappings

Group mappings are essential for the synchronization of groups on your servers when using the `VyHub Group Sync` and not
using simple commands. Learn more about the `VyHub Group Sync` in the [group sync](./group_sync.md) guide.

Without a Group Mapping, it is not clear which VyHub group belongs to which server group(s). Therefore, the Sync cannot
work.

A group mapping consists of two parts:

1. Serverbundle: The group mapping is scoped for this serverbundle. Leave empty to make the mapping valid for all
   bundles.
2. Name of group/rank/role: The name of the group/rank/role on your server.

### Example

Imagine that there are two serverbundles: One for Garry's Mod and one for Discord.

- We want that users that have the `Admin` VyHub group in the GMOD serverbundle should receive the `superadmin` in-game.
- Additionally, users that have the `Admin` VyHub group in the Discord serverbundle should receive the `Owner` role on
  the Discord server.

We go to the `Mappings` section of the `Admin` VyHub group and create two mappings:

- One for the GMOD serverbundle with `superadmin` as group name.
- One for the Discord serverbundle with `Owner` as group name.
