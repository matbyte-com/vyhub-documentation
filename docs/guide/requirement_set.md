# Requirement Sets

Requirement sets are used for advanced requirements to limit access to an action or a certain resource.

## Usage of Requirement Sets

- **[Packets](shop/packet.md)**
- **[HTML Pages](html_pages.md)**
- **[Forum](forum.md)**

## Attributes

| Attribute | Description                             |
|-----------|-----------------------------------------|
| Name      | Unique nae to identify the set          |
| Formula   | Formula, which is going to be evaluated |

## Add / Edit

Requirement Sets and Requirements can be added and edited through the designated `Requirements` page.

## Requirements

| Attribute | Description                                  |
|-----------|----------------------------------------------|
| Type      | Type of requirement                          |
| Operator  | Operator of requirement                      |
| Key       | Relation to other resources (e.g. Packet-id) |
| Value     | Desired value (permission level 42)          |

### Available Types

This list gives an overview of all available types with their respective operations

- Group member (EQ, NEQ)
- Permission level (EQ, NEQ, LEQ, GEQ, LT, GT)
- Permission level within a specific **[serverbundle](server.md)**
- Property (HAVE, NHAVE)
- Property within a specific **[serverbundle](server.md)**
- User Attribute (EQ, NEQ, LEQ, GEQ, LT, GT, HAVE, NHAVE)
- Packet (ACTIVE, INACTIVE, NEVER_ACTIVE, ONLY_ACTIVE, ONLY_INACTIVE)
- Date (EQ, NEQ, LEQ, GEQ, LT, GT)
- User-Self (NEQ, EQ)

### Formula

With the formula multiple requirements can be chained together. A logical formula can be created.

## Example Use Cases
Requirement Sets can be for example used for the limitation of access to custom **[HTML pages](html_pages.md)**.
This way only players who have bought a certain packet or have a certain rank (e.g. VIP) can access the page.
### Forum: Create a “Team-Only” Part of the Forum

This is an easy use case for the `requirements`. The goal is to limit the access to one part of the forum to team members
only.

1. Create a moderator `group` (no special rights are necessary for this tutorial)
2. Create a `requirement set` and name it "ModeratorAccess"
3. Edit the "ModeratorAccess" `RequirementSet` and add click the "Add Requirement" button   
   3.1 Select Type "Groupmember"   
   3.2 Select Operator "= Equal"   
   3.3 Select your "moderator" group
4. The `requirement` is now added and has the ID 0
5. Type the necessary formula which only consists of the ID 0 (Formula: `0`)
6. Go to the `forum` and click the "Manage Topic Category" button   
   6.1 Name the `topic category` like you want   
   6.2 Select the "ModeratorAccess" `requirement set`

Congratulations! The newly created `topic category` is now only accessible by users which are part of the moderator `group`