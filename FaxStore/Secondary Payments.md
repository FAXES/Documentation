:::info
Secondary Payments are in BETA and could hav bugs. Please submit any feedback on this feature to:

https://bugs.faxes.zone/projects/faxstore/add?t=feedback
:::

Secondary payments allow you to send funds of an item to a secondary payee. Configured in PayPal and Stripe the payment flows to where it's needed. See below on how to set these up for PalPal and Stripe.

For example if you have secondary payments setup on '2nd product' any transactions made for this item the profits and transaction will go to the secondary payee.

## PayPal
PayPal is easy to set this up for, all you have to do is place the email of another **business account** in order to send secondary payments.

## Stripe
Stripe uses [Stripe Connect](https://stripe.com/connect). On your business dashboard enable Connect and create a connected account using the 'Create' button.

Make sure to create an Express account and send the link to the payee you wish to have. Once they authorise through Stripes steps (dependant on where they're from) you will see them on the Connect page on your dashboard.

To get their account ID scrolldown on their Connect page and copy the Account information `ID`. It will look something like this `acct_4JEpD1O4mrWQQFpY`. This is the account ID you place into your FaxStore secondary payee for Stripe.

*[Improve this page](https://github.com/FAXES/Documentation/blob/main/FaxStore/Secondary%20Payments.md)*
