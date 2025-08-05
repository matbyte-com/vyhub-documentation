# Balance and Pricing

This article is about the pricing of VyHub instances and how payments are settled.

## Pricing of VyHub

> The free plan has been discontinued to enhance our user experience. We believe in offering comprehensive features
> without arbitrary limitations, and this change allows us to provide better support and resources for our users.

<sub>Non-EUR currencies are converted to EUR at the end of the billing cycle.</sub>

| Percentage | Plan              |
|------------|-------------------|
| 3.8%       | Pro Plan          |
| 3%         | Self-Hosting Plan |

### Example Revenues Fee

You will pay the base-price for your VyHub unless you earn money through the shop.  
The more revenue you generate, the more you save on fees, as can be seen in the following table:

| Revenue generated through VyHub | Formula                   | Total to pay | Comparable competitor* |
|---------------------------------|---------------------------|--------------|------------------------|
| 0.00 €                          | 14.99€                    | 14.99 €      | 14.00 €                |
| 222.00 €                        | 14.99€ + 222.00 € × 3.8%  | 23.43 €      | 25.10 €                |
| 2700.00 €                       | 14.99€ + 2700.00 € × 3.8% | 117.59 €     | 149.00 €               |

<sub>* Comparable competitor with a 5% commission and extra cost for SSL-Certificate and domain.</sub>

### Cancelling VyHub Pro and other Add-ons

You can cancel every add-on at the end of every billing cycle.   
Cancelling is easily done through the central instance
dashboard [https://app.vyhub.net/dashboard](https://app.vyhub.net/dashboard).

## Payment of your Instance

During the month, the revenue of your instance is collected and reflected in
your [VyHub Balance](https://app.vyhub.net/account). When setting up your VyHub instance, a membership is automatically
created. Life-time users have to top up manually or enable Auto-Charge for their account.

At the end of the month, all costs of the month come into effect and will be debited from your VyHub Balance.
You then have __7 days__ to settle up your negative balance, either manually or automatically (Auto-Charge). The payment
deadline is extended to __22 days__ when Auto-Charge is enabled.

### Recommended: Auto-Charge

We recommend setting up Auto-Charge for your account.
With Auto-Charge, you will never forget to top up your balance in time.

At the beginning of each month, you will receive an email about your outstanding balance.
The balance will then be collected through your selected payment method within the next 14 days.

**Supported Payment Methods**

- PayPal
- Stripe

> The minimum amount for a single charge is 5.00 €. Your positive balance will be used to settle the costs of the
> following months.

#### Example Charge Cycle

| Month   | Monthly Bill | Balance before charge | Charge Up | Balance after charge |
|---------|--------------|-----------------------|-----------|----------------------|
| Month 1 | - 3.00 €     | 0.00 €                | 5.00 €    | 2.00 €               |
| Month 2 | - 1.00 €     | 2.00 €                | 0.00 €    | 1.00 €               |
| Month 3 | - 8.00 €     | 1.00 €                | 7.00 €    | 0.00 €               |

#### Setting up Auto-Charge

You can set up Auto-Charge **without** any setup fee if your VyHub Balance is not negative.

If your VyHub Balance is negative, you will be charged a setup fee which reflects your current balance but is at least
5.00€.

| Balance before Setup | Setup Fee | Balance after Setup |  
|----------------------|-----------|---------------------|
| 0.00 €               | 0.00 €    | 0.00 €              | 
| 6.00 €               | 0.00 €    | 0.00 €              | 
| - 2.00 €             | 5.00 €    | 3.00 €              | 
| - 7.00 €             | 7.00 €    | 0.00 €              | 

### Prepaid

You can also manually top up your VyHub Balance.

> The minimum top-up amount is 5.00 €. Your positive balance will be used to settle the costs of the following months.

At the beginning of each month, you will receive an email about your outstanding balance. The outstanding amount must be
topped up, otherwise your instances will be stopped.

### Outstanding Balance

If you have got outstanding payments and your VyHub Balance is still negative after the payment deadline, all your
instances will be stopped. You can reactivate
them after you have settled the balance.

> We point out that accumulated debts must be settled in accordance with our terms and conditions in any case.

You can reactivate your disabled instance after you have settled the balance in the dashboard.

The payment deadline depends on the Auto-Charge status:

| Auto-Charge | Payment Deadline |
|-------------|------------------|
| Enabled     | 7 Days           | 
| Disabled    | 22 Days          | 

You will receive reminder emails if the payment deadline comes closer.

### Payout of VyHub Balance

A payout of your VyHub Balance is not possible.


