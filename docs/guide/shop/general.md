# General Settings

The VyHub shop is the most important feature of VyHub. It allows you to sell VIP-Ranks, Item Drops, and more to your
users for real money. The VyHub shop works by executing commands on your server when a user buys a product.

Before a user can buy your packets, some configuration is needed. 

- Create a Packet Category
- Create a [Packet](./packet.md) with [Rewards](./reward.md)
- Set up [Payment Gateways / Payment Methods](./payment_gateway.md) and optionally [Tax Rules](./tax.md)

| Attribute                                 | Description                                                                                                   |
|-------------------------------------------|---------------------------------------------------------------------------------------------------------------|
| Default Currency                          | The default currency of the shop. Also used for the shop widgets donation goal.                               |
| Credits Display Title                     | Define your own name for the payment method credits. Can be anything you like (gulden, diamonds, hearts, ...) |
| Invoice Logo URL                          | URL to a logo image that is shown on the invoice                                                              |
| Purchases from countries without tax rule | If enabled, purchases from countries where you did not define a tax rule are possible                         |
| Tax included in packet price              | Instead of adding taxes to the specified packet price on top, they are included in the price.                 |
| Checkout Checkboxes                       | Checkboxes which have to be agreed to during checkout. E.g. "I agree to the Terms of Service"                |


