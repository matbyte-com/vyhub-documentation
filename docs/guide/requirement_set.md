# Requirement Sets

Requirement sets are used for advanced requirements to limit access to an action or a certain resource.

## Usage of Requirement Sets

- Discounts
- **[HTML Pages](html_pages.md)**
- **[Forum](forum.md)**

## Attributes

| Attribute | Description                      |
|-----------|----------------------------------|
| Name      | Name to identify the set         |

When editing a requirement set, you can also manage its requirements and its logical formula (see below).

## Add / Edit

Requirement Sets and Requirements can be added and edited through the designated `Requirements` page.

## Requirements

| Attribute | Description                                  |
|-----------|----------------------------------------------|
| Type      | Type of requirement                          |
| Operator  | Operator of requirement                      |
| Key       | Relation to other resources (e.g. Packet-id) |
| Value     | Desired value (e.g. permission level 42)     |

The available operators and additional fields (Key/Value) depend on the selected type.

### Available Types

This list gives an overview of all available types with their respective operators.

- Groupmember (Equal, Not Equal) - select a group
- Permission Level (Equal, Not Equal, Less Equal Than, Less Than, Greater Than, Greater Equal Than) - value is a permission level (0-100)
- Permission Level (in Serverbundle) - like Permission Level, but for a specific **[serverbundle](server.md)**
- Property (Have, Have Not) - value is a property name
- Property (in Serverbundle) - like Property, but for a specific **[serverbundle](server.md)**
- User Attribute (Equal, Not Equal, Less Equal Than, Less Than, Greater Than, Greater Equal Than) - key is the attribute name, value is the attribute value
- Packet (Active, Only Active, Only Inactive, Inactive, Never Active) - select a packet
- Date (Equal, Not Equal, Less Equal Than, Less Than, Greater Than, Greater Equal Than) - value is a date
- User Self (Equal, Not Equal)

### Formula

With the formula, multiple requirements can be chained together into a logical formula. Each requirement is referenced by its ID (shown in the requirements table). Use the following operators:

- `|` for an OR connection
- `&` for an AND connection
- parentheses `()` for grouping

After entering a formula, use the `Edit Formula` button to validate and save it.

### Requirement Set Tester

You can test the evaluation of requirement sets against any user. Choose a user and you will see the result instantly.

#### Example

There are three requirements with the IDs 0, 1 and 2, and you want to make the requirement set evaluate to `true` if requirement 0 and one of requirements 1 and 2 are fulfilled.

For this the formula `0 & (1 | 2)` would be correct.

## Example Use Cases
Requirement Sets can be, for example, used for the limitation of access to custom **[HTML pages](html_pages.md)**.
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
