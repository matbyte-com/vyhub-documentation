# Packets

Through the VyHub shop, you can sell packets (products) to your users. These packets can include anything from VIP ranks to
Item Drops. The rewards need to be set up in the [`Reward`](./reward.md) settings.

| Attribute              | Description                                                                                |
|------------------------|--------------------------------------------------------------------------------------------|
| Subcategory            | [Optional] To split a category in multiple subcategories                                   |
| Enable                 | If disabled, packet can not be bought and all bought packets become inactive               |
| Active for             | The time the rewards are active for (Recurring payments possible)                          |
| Buyable                | If disabled, packet can not be bought anymore                                              |
| Buyable active state   | If disabled, packet can not be purchased if the user already has this packet active        |
| Buyable inactive state | If disabled, packet can not be purchased if the user already has this packet, but inactive |
| Recommendable          | Whether the packet will be recommended during the purchase as an upsell                     |

## Payment

| Attribute                        | Description                                                                                                                                                                      |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Price                            | Price of packet                                                                                                                                                                  |
| Currency                         | The currency of the price                                                                                                                                                        |
| Credits                          | [Optional] Credit price of packet (leave empty if the packet should not be purchasable by credits)                                                                               |
| Custom Price / Pay what you want | [Optional] The user can decide how much he wants to pay. The selected price/credits is used as minimum price.                                                                    |
| Recurring                        | Recurring payments every time the **active for** duration is expired - this limits the choice of payment gateways to those that support it. Currently **Stripe** and **PayPal**. |

## Packet Relations

> This setting allows creating relations between packets and allow for upgradable packets.

### Types

| Type           | Description                                                                                                                                                                                                                                         |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Not compatible | The current packet cannot be purchased if the user has the selected packet in an active state                                                                                                                                                       |
| Requires       | The current packet can only be purchased if the user has the selected packet in an active state                                                                                                                                                     |
| Disables       | When the current packet is activated, the selected packets will be disabled for the user                                                                                                                                                            |
| Upgrades       | When the current packet is activated and the user has the selected packet in an active state, the selected packet will be disabled for the user and the active time of the current packet will be extended by the time the disabled packet had left |
