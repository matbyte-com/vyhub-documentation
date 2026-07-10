# General Settings

The VyHub shop is the most important feature of VyHub. It allows you to sell VIP-Ranks, Item Drops, and more to your
users for real money. The VyHub shop works by executing commands on your server when a user buys a product.

Before a user can buy your packets, some configuration is needed. 

- Create a Packet Category
- Create a [Packet](./packet.md) with [Rewards](./reward.md)
- Set up [Payment Gateways / Payment Methods](./payment_gateway.md) and optionally [Tax Rules](./tax.md)

## General

| Attribute | Description |
|-----------|-------------|
| Default Currency | The default currency of the shop. Also used for the shop widget donation goal. |
| Customer address required for purchases of more than | For purchases with a total amount less than this value, the customer does not need to provide an address. Only applies to purchases that use the default currency. |
| Credits display title | Rename the payment method credits to anything you like (gulden, diamonds, coins, ...). |
| Show statistic widgets on shop page | If disabled, the enabled widgets (top donators, ...) are not shown on the shop page. |
| Enable donation goal | Show the donation goal widget throughout the website (News, Shop, Home). |
| Donation goal | Target amount for the donation goal widget. |
| Enable top donators | Show the top donators widget throughout the website (News, Shop, Home). |
| Number of donators to display | How many donators the top donators widget shows. |
| Days to display | Only count donations within this number of days for the top donators widget. Clearable to count all time. |
| Enable last donations | Show the last donations widget throughout the website (News, Shop, Home). |
| Donation goal display title | Title shown above the donation goal widget. |
| Top donators display title | Title shown above the top donators widget. |
| Last donations display title | Title shown above the last donations widget. |
| Allow purchases from countries without tax rule | If disabled, purchases from countries that do not have an explicit tax rule configured are not possible. |
| Tax included in packet price | Instead of adding taxes to the specified packet price on top, they are included in the price. |
| Show packets as list | Display packets in a list layout instead of the default card/grid layout. |
| Invoice logo | Logo that is displayed on the invoice. |
| Checkout checkboxes | Checkboxes that must be agreed to during checkout. Each entry has a text and an optional URL (e.g. "I agree to the Terms of Service"). |
| News | Rich-text content displayed on the shop/news page. |

## Business Address

The business address is shown on invoices and is used for tax purposes. Click `Change` to edit it. In addition to the standard address fields (Name, Street and Number, Addition, Zip Code, City, State, Country), a `VAT Number` field is available.

| Attribute | Description |
|-----------|-------------|
| Name | Name of the business or person. |
| Street and Number | Street and house number. |
| Addition | Optional address addition. |
| Zip Code | Postal / ZIP code. |
| City | City. |
| State | State / region. |
| Country | Country of the business address. |
| VAT Number | VAT identification number of the business. |

