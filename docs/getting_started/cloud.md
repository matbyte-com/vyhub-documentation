# Setup VyHub Cloud

This is the quickstart guide for VyHub Cloud. For additional information about how to use VyHub, check out the `Guide`
section of the docs.

## Get your VyHub Instance

Using VyHub for your gaming community is as easy as a few clicks are.

1. Create your account on [app.vyhub.net](https://app.vyhub.net).
2. Go to the [Dashboard](https://app.vyhub.net/dashboard) and click `Create Instance`.
3. Fill out the required details. See [instance guide](../central/instance.md) for more information.
4. Click `Submit`.

Your VyHub instance is usually created within a few minutes. Your instance is ready as soon as the status changes to
`Provisioned`. You can find the status by visiting the instance details page.

## Open your VyHub Instance

Congratulations, you can now connect and login to your VyHub instance under the domain you’ve chosen in the
installation process. You can find the frontend URL on the details page of your instance.

All further steps are accomplished within the settings panel of your VyHub instance  
`(your-domain.com/settings)`

## Shop Only or Full Mode

VyHub offers a shop only mode that hides or disables all features that are not shop related. This helps if you do not
want to use all the other features of VyHub. Switching between these modes can be done at any time in the
`General Settings` of your instance.

## Connect your Gameserver

One of the first things to do is to connect your gameserver with VyHub.

> Each gameserver is organised in a [serverbundle](../guide/server.md).  
> All servers within a serverbundle are from the same type (e.g., GMOD, Minecraft, Discord)

1. (optional) Navigate to the `Server` settings and create your serverbundle.  
   We are going to choose the default group for new users in this bundle later.
2. Now it's time to connect your server, which is done in the same settings menu.  
   Follow the displayed instructions.
3. Install the fitting gameserver addon to your server. You can find it on this page in the "Game Integrations"
   section. (For example, [Garry's Mod](../game/gmod.md) or [Minecraft](../game/minecraft.md))

[*Additional Information*](../guide/server.md)

## Groups

You can now create all the user groups that you want.

> Memberships in a user group are scoped to a serverbundle.

1. Navigate to the `Group` settings and create your group.
    - The permission level is used to decide which users can be targeted by a member of the group
        - e.g., A user with permission level 42 can't target another user with the level of 99.

> A [group](../guide/group/group.md) has [properties](../guide/group/property.md) to control the user right management
> and access
> control.  
> Additional to properties, admins have all permissions. More admins can be added
> on [app.vyhub.net](https://app.vyhub.net).

2. Now edit the created group, switch to the `Properties` tab and choose all necessary properties.
3. At the `Mappings` tab, you can map the VyHub group to an in-game group.
4. Go back to the `Server` tab, edit your serverbundle and choose a created group as a default group.

[*Additional Information*](../guide/group/group.md)

## Shop

### Payment Gateways

Payment gateways (e.g., PayPal, Stripe) available for your customers can be added in the `Payment Gateway` settings.

You need to provide the VyHub instance with the payment providers **secrets**.
These secrets can be obtained directly from the payment provider after creating an account with them.

[*Additional Information*](../guide/shop/payment_gateway.md)

### Tax

For correct taxation of your sales, tax rules for your target countries must be created.

> In the `General` settings of the shop, you can decide whether buyers from countries where no tax rule is
> specified are allowed to use your shop.

To provide the correct tax information go to the `Tax` settings.

[*Additional Information*](../guide/shop/tax.md)

### Reward

> A reward may execute some action after a packet has been applied to a user.

Create a reward in the `Reward` settings.

[*Additional Information*](../guide/shop/reward.md)

### Packet

> Your created [packets](../guide/shop/packet.md "Packet") are available for purchase in the shop.

Packets are ordered within categories. Categories are created in the `Category` settings.  
A price is set in the `Payment` tab.

Do not forget to select the **rewards** the user receives after purchasing the packet.

[*Additional Information*](../guide/shop/packet.md "Packet")

## Customize your Community

VyHub is customizable for your needs.  
Try changing the theme in the **theme** settings or start creating your own pages in the **navigation** settings.

You can set the **community name** in the `General` settings.

Congratulations you’re all set up!
