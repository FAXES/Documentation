Events are a great way to build and develop extensions in FaxStore. Events are always being added and are documented here for your use in extensions or development of FaxStore.

::: info
Suggest an event at the below link if you'd like to see a particular event
[Suggest new event](https://bugs.faxes.zone/projects/faxstore/add?t=feedback)
:::

Using events is easy as pie, all you do is use the associated name and arguments. Here are some examples.

Listen for an event (on)
```js
faxstore.on('login', function(userObject, DbUserResults) {
  // Do as you wish in the event, you can fetch data and even do other actions like make an automated webhook post.
  console.log(userObject);
  // userObject is the data passed in the users session (in an object), this will contain some login service data like their ID, avatar, and possibly guilds.
  console.log(DbUserResults);
  // This is an SQL object which contains the users database information.
});
```

Emit events (emit)
```js
const date = Date.now();
faxstore.emit('CreateAuditLog', 'UserID', 'Logged in', `logged in at <t:${date}>`);
```

So these two examples could be used together to create an audit log for when users login. Here's an example
```js
faxstore.on('login', function(userObject, DbUserResults) {
  const date = Date.now();
  faxstore.emit('CreateAuditLog', DbUserResults.userId, 'Logged in', `logged in at <t:${date}>`);
  
  // This example uses 'DbUserResults.userId' over 'userObject.id' as it can be more reliable and correlates to the database.
  // However, both would work the same.
});
```

## Events Dictionary

- **on** is a listen event that triggers with `faxstore.on()`
- **emit** is to emit an event to the system with `faxstore.emit()`

| Name                       | Arguments                                              | Description                                                                               | Type |
|----------------------------|--------------------------------------------------------|-------------------------------------------------------------------------------------------|------|
| CreateAuditLog             | UserId, Action, Details | Create An Audit Log. All Arguments Required. | emit |
| pushNotification           | userId, details, redirect | Creates a notification on the site for this user. All arguments required and are strings. | emit |
| removeDiscordRole          | userId, roles | Removes roles from the user is possible. | emit |
| addDiscordRole             | userId, roles | Adds roles to the user if possible. | emit |
| invoiceCreated             | invoiceId, invoicedUser, staffUser, invoicedItems, due | Emits when a invoice is created.  | on |
| invoiceUpdated             | invoiceId, invoicedUser, due, state | When an invoice is automatically updated for it's status, this event emits. | on |
| invoicePaid | invoiceID, paymentType, receiptID, invoicedItems | Emits when an invoice is paid by a user. | on |
| login                      | userObject, DbUserResults                              | Emits when a user logs into the site.                                                     | on   |
| logout                     | userObject                                             | Emits when a user logs out of the site.                                                   | on   |
| createUserAccount          | userObject, serviceType                                | Emits when a users account is first created.                                              | on   |
| onStart                    | licenseKey, siteDomain                                 | Emits when FaxStore first starts.                                                         | on   |
| userAccountDelete          | staffUserId, userId                                    | Emits when a users account is deleted.                                                    | on   |
| userAccountUnban           | staffUserId, user                                      | Emits when a users account is un-banned.                                                  | on   |
| userAccountBan             | staffUserId, user                                      | Emits when a users account is banned.                                                     | on   |
| userAccountUndisabled      | staffUserId, user                                      | Emits when a users account is un-disabled.                                                | on   |
| userAccountDisabled        | staffUserId, user                                      | Emits when a users account is disabled.                                                   | on   |
| userAccountStaffNoteEdited | staffUserId, user                                      | Emits when a staff member updates a users staff notes.                                    | on   |
| createCheckout             | userObject, cart, total, promoCode, paymentType            | Emits when a checkout is made on the site.                                                | on   |
| checkoutReturn             | userId, paymentId, cart                                | Emits when a checkout is returned to the store.                                           | on   |
| checkoutCancel             | userId                                                 | Emits when a checkout is cancelled by the user                                            | on   |
| subscriptionInvoiceCreated | invoiceId, userObject, items, expiry | Emits when a subscriptions invoice is first generated | on |
| subscriptionCancelled | subscription, userObject | Emits when a subscription is cancelled by a user. | on |
| subscriptionEnded | subscription, userId | Emits when a subscription ends after being cancelled. | on |
| releaseCreate | storeItem, release, releaseId, staffUser | Emits when a release is created | on |
| releaseEdit | release, staffUser | Emits when a release is edited | on |
| releaseDelete | release, staffUser | Emits when a release is deleted | on |
| blogpostCreate | userId, blogpost | Emits when a new blog post is created | on |
| blogpostDelete | userId, blogpostId | Emits when a blog post gets deleted | on |
| hasPermission | userData, permission | UserData (object) and permission (string or array). This event is to check for a [permission](/c/faxstore/permissions) a user may have. | on |
| formCreate | userObject, formObject | Emits when a form is created | on |
| formSubmitted | userObject, formId, formObject, submissionObject | Emits when a form gets submitted by a user | on |
| formReply | userObject, formId, comment | Emits when a form is replied to | on |
| formDelete | userObject, formObject | Emits when a form is deleted | on |
| reviewCreated | userObject, reviewId, reviewObject | Emits when a revire is created by a user | on |
| reviewResponse | userObject, reviewId, comment | Emits when a review is replied to by a staff member | on |
| reviewDeleted | userObject, reviewId | Emits when a review is deleted | on |
| storeListingCreate | userObject, listingObject | Emits when a new store listing is created. | on |
| storeListingEdit | userObject, listingId, listingObject | Emits when a store listing is edited. | on |
| storeListingPause | userObject, listingId, newState | Emits when a store listing pause setting is toggled. | on |
| storeListingDelete | userObject, listingId | Emits when a store listing is deleted | on |
| notificationCreated | userId, redirectURL, detailsObject | Emits when a notification is created. | on |
| quoteCreated | userObject, quoteID, quoteObject, createdAt | Emits when a quote is created. | on |
| quoteEdited | userObject, quoteID, quoteObject | Emits when a quote is edited/updated | on |
| quoteAccepted | userId, quoteID | Emits when a quote accepted by a user | on |
| packageCreated | userObject, packageID, packageObject, createdAt | Emits when a package is created. | on |
| packageEdited | userObject, packageID, packageObject | Emits when a package is edited | on |
| packageDeleted | userObject, packageID, packageObject | Emits when a package has been deleted | on |


*[Improve this page](https://github.com/FAXES/Documentation/blob/main/FaxStore/Events.md)*
