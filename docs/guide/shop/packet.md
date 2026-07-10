# Packets

Through the VyHub shop, you can sell packets (products) to your users. These packets can include anything from VIP ranks to
Item Drops. The rewards need to be set up in the [`Reward`](./reward.md) settings.

Packets are organized into [categories](#categories). Packets can be reordered by drag-and-drop (only when a category is
selected), copied, edited and deleted. In the packets overview, a packet may show flags such as *Custom Price*,
*Disabled*, *Not Buyable*, *Recurring*, *Expires* and *Limited Payments*.

## General

| Attribute                        | Description                                                                                          |
|----------------------------------|-----------------------------------------------------------------------------------------------------|
| Title                            | Name of the packet                                                                                  |
| Title displayed over image       | [Optional] Title displayed as an overlay on top of the packet image                                 |
| Subtitle                         | [Optional] Subtitle shown below the title                                                           |
| Category                         | The category the packet belongs to                                                                  |
| Subcategory                      | [Optional] To split a category into multiple subcategories                                          |
| Description                      | Rich-text description of the packet                                                                 |
| Image                            | Image displayed for the packet                                                                      |
| Active for                       | Duration (in days) the packet stays active after activation. Leave empty for packets that never disable over time. If **Recurring** is enabled, this is used as the subscription interval. |
| Enabled                          | If disabled, the packet cannot be purchased and all assigned/applied packets become inactive        |
| Buyable                          | If disabled, the packet can no longer be purchased in the shop                                       |
| Buyable if active (advanced)     | Buyable if the user already has this packet in an active state                                       |
| Buyable if inactive (advanced)   | Buyable if the user already has this packet in an inactive state                                     |
| Recommendable                    | The packet may be recommended to users in the "Recommendations" / "Recommended for you" sections    |

> Fields marked *(advanced)* are only shown when advanced settings are enabled.

## Payment

| Attribute                        | Description                                                                                                                                                                      |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Price                            | Price of the packet                                                                                                                                                             |
| Currency                         | The currency of the price                                                                                                                                                        |
| Credits                          | [Optional] Credit price of the packet (leave empty if the packet should not be purchasable with credits)                                                                        |
| Custom Price                     | [Optional] Let the user decide the price. The entered price above is used as the minimum price.                                                                                 |
| Limit payment methods (advanced) | [Optional] If payment methods are selected, only these can be used. If none are selected, all methods can be used.                                                              |
| Recurring                        | A subscription is created, charged every time the **Active for** duration expires. This limits the choice of payment gateways to those that support it, currently **Stripe** and **PayPal**. |

## Packet Relations

> This tab (advanced settings only) allows creating relations between packets and allows for upgradable packets.

### Types

| Type           | Description                                                                                                                                                                                                                                         |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Requires       | Requires the selected packet for a purchase (user must have it in an active state)                                                                                                                                                                  |
| Not compatible | Not compatible with the selected packet (cannot be purchased if the user has the selected packet)                                                                                                                                                   |
| Disables       | Disables the selected packet on purchase                                                                                                                                                                                                            |
| Upgrades       | Can be used to upgrade the selected packet. On activation the selected packet is disabled and the active time of the current packet is extended by the time the disabled packet had left                                                            |

## Rewards

The **Rewards** tab lets you assign one or more [rewards](./reward.md) to the packet. These rewards are executed when a
user purchases (or is granted) the packet.

## Categories

Packets are grouped into categories, managed on the **Categories** settings page. Categories can be reordered by
drag-and-drop.

| Attribute | Description                                       |
|-----------|---------------------------------------------------|
| Name      | Name of the category                              |
| Image     | Image displayed for the category                  |
| Enabled   | Whether the category (and its packets) is enabled |
