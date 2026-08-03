# Payment Gateways / Payment Methods

Payment gateways are used to accept payments from your users. You can create multiple payment gateways to offer your
users more optionality. Without creating a payment gateway, users can't buy anything from your shop.

These common attributes are available for every gateway type:

| Attribute | Description |
|-----------|-------------|
| Type | The gateway type chosen when creating the gateway (read-only). |
| Name | Name of the gateway. |
| Subtitle | Subtitle shown during checkout. |
| Image | Optional. Default images are used when no image is uploaded. |
| Enabled | Enable the payment gateway. |

Depending on the selected type, additional attributes (such as environment, keys and secrets provided by the payment
provider) are shown. These are described in the per-gateway sections below. Secret attributes are write-only: once saved,
your input is not shown again and is only overwritten if you enter a new value. When editing a PayPal gateway,
a read-only `Webhook URL` field is also shown.

Deleting a gateway also deletes all purchases and payments that used it and cannot be undone. Consider disabling a gateway instead.

Please follow the instructions below to add a payment gateway.

## PayPal

[Video Tutorial](https://www.youtube.com/watch?v=vi9cLSjXDRI)

`Supports recurring payments: yes`

> If you want to test the payments with a sandbox account first, do the steps below, but with a `SANDBOX` application.

1. Create a [PayPal Business](https://www.paypal.com/business) account or upgrade your account to a business account. If
   you don't want to upgrade your account, you can use the PayPal (Easy) integration (see below).
2. [Create a REST API app](https://developer.paypal.com/developer/applications/) in the PayPal Developer settings. Make
   sure to create the app for the `Live`
   environment.
3. Under `LIVE APP SETTINGS`, enable `Transaction Search`, disable the `Payouts` feature and click `Save`.
4. In your VyHub instance, create a PayPal payment gateway, select `PRODUCTION` environment and insert your `Client ID`
   and `Client Secret`.
5. Click `Create` and edit the payment gateway again. At the bottom, copy the `Webhook URL` to your clipboard.
6. Back in the `PayPal Developer` portal, click `Add Webhook` under `LIVE WEBHOOKS` and paste the copied URL.
7. Select `All events`, scroll down and click `Save`.
8. Copy the `Webhook ID` of the created webhook into the form and click `Edit`.

## PayPal (Easy)

`Supports recurring payments: no`

The PayPal Easy/Legacy payment gateway is easier to set up and can be used without a PayPal business account.
However, it has some limitations as it doesn’t support subscription payments, refunds and the general payment handling
isn't as good as with the normal PayPal gateway.

1. In your VyHub instance, create a PayPal (Easy) payment gateway, select `PRODUCTION` environment and insert your
   primary PayPal email address.
2. Click `Create` and test if everything works fine.

## Stripe

```
Supports recurring payments: yes
Supported Stripe API version: 2026-06-24 and older
```

> If you want to test the payments with a test account first, do the steps below, but with a `TEST` application.

1. [Create a Stripe account](https://dashboard.stripe.com/register) or log into your existing one.
2. Open [Stripe Workbench](https://dashboard.stripe.com/workbench/overview) and locate the `API keys` section. Create a new Public and Secret key or copy the already existing ones.
3. In your VyHub instance, create a Stripe payment gateway, insert your `Public Key` and `Secret Key` and select your desired `Payment Methods`.
4. Click `Create`.
5. (Optional) Go to the [Webhooks Tab](https://dashboard.stripe.com/workbench/webhooks/), select the endpoint created by VyHub and click `Send test event` to test if everything works fine.
6. (Optional) In the settings of the payment gateway, enable `Accept pending payments` to enable fast payment
   processing for the Stripe payment methods that take several hours/days until a payment is finished.

> If you use a restricted API key instead of the standard secret key, make sure it has write permission for
> `Webhook Endpoints`. Otherwise VyHub can't create the webhook and payments won't be processed.

The webhook is also kept up to date automatically: if the address of your instance changes, VyHub updates the endpoint,
and when you delete the payment gateway, the endpoint is removed from your Stripe account again.

## Paysafecard

`Supports recurring payments: no`

> These are the instructions to become an official paysafecard partner. You can also create a payment gateway with
> manual
> code confirmation with a `Coupon` gateway (see below).

1. [Become a paysafecard partner](https://www.paysafecard.com/become-a-partner/).
2. In your VyHub instance, create a Paysafecard payment gateway, insert your `API Key` and select your
   desired `Environment`.
3. Click `Create`.
4. As no IP addresses can be whitelisted, ask paysafecard to give you a cryptographic certificate for authentification.
   The private key (`Client Key`) and certificate (`Client Certificate`) can be set in the payment gateway settings.
   The `Client Certificate` is usually in a file named something
   like `001_manXXXXXXXXXX_XXXXXXXX_distributor_paysafecard_com.crt`.

## Credits

`Supports recurring payments: no`

1. In your VyHub instance, create a credits payment gateway.

Create packets that have `Credits` as reward, so that users can buy credits with real money. You will need another
payment gateway for this.

> Credits can be renamed with a name that matches your community (gulden, diamonds, ...). Rename in the `general-shop`
> settings.

#### Manually adding Credits

Credits can be manually added or removed from within the `User Dashboard` -> `Purchases` -> `Credits`.

> It is possible to remove credits by entering a negative number of credits (e.g. -100 credits).


## Coupon

`Supports recurring payments: no`

> Coupon gateways can be used to manually approve coupons (e.g., paysafecard pins, amazon cards)

1. In your VyHub instance, create a coupon payment gateway.
2. After a purchase is made and coupons are entered by the user, the coupons need to be approved under
   the `confirm purchases` tab on the `shop admin` page.

## Free

`Supports recurring payments: no`

The `Free` payment gateway is an internal construct. It always exists, can't be deleted, and no other payment gateways
can be created with this type.

The `Free` payment gateway appears as a payment option whenever the total amount to pay is zero. This can happen if
there
is a zero packet price or a 100%
discount has been applied.
