Since the 2.2 update of FaxStore permissions now use a new bitfield based system to allow better customisation and cater for every store owner. Below is a table that contains all the permissions that are in FaxStore.

Function example:
```js
// hasPermission(userData, permission)
// The second parameter (permission) can be a string of a permission or an array of permissions, if one is met it returns true.
if(hasPermission(userData || userInfo || {id: userId, bitfield: userBitfield}, 'VIEW_USERS')) {
  console.log(`User has permission 'VIEW_USERS'`);
  // Function returns a BOOLEAN
}

// More refined example:
if(hasPermission({id: '282762192544333827', bitfield: '19669056'}, 'MANAGE_OWNED_ITEMS')) {
  console.log(`User has permission 'VIEW_USERS'`);
}
```
This function is available as an event, and function in backend and EJS files.

| Name | Description |
|---|---|
| NONE | No permissions for the user. This is used for normal site users. |
| VIEW_STAFF_PANEL | Allows the user to view the staff panel, this essentially unlocks the 'Staff' button in the header. |
| EDIT_USER | Allows editing of user settings and edit the staff note on users. |
| EMAIL_USERS | Allows staff to send individual or mass emails. |
| DELETE_USERS | Allows staff to delete user accounts fully. |
| BAN_USERS | Allows staff to (un)ban users. |
| DISABLE_USERS | Allows staff to be able to (un)disable user accounts. |
| VIEW_USERS | Allows staff to view user profiles and details, including owned items, receipts. They can't action anything on the user only view. |
| VIEW_AUDIT_LOG | Allows staff to view the stores audit logs. |
| VIEW_INSIGHTS | Allows staff to view the stores insights along with individual store item statistics. |
| VIEW_INVOICES | Allows staff to only view invoices. |
| VIEW_GIFTCARDS | Allows staff to view users gift cards. |
| MANAGE_INVOICES | Allows staff to manage invoices; creating, editing, and cancelling. |
| MANAGE_BLOGS | Allows staff to manage blogs; create, delete, and edit both articles and blog settings (including categories) |
| MANAGE_PAGES | Allows staff to manage static pages, team members, and home page settings. |
| MANAGE_GALLERY | Allows staff to upload and delete images in the gallery. |
| MANAGE_PARTNERS | Allows staff to create, edit, and delete partners. |
| MANAGE_ORDERS | Allows staff to view and update all orders. |
| MANAGE_STORE | Allows staff to; create, edit, delete everything store related including releases. |
| MANAGE_SUBSCRIPTIONS | Allows staff to manage subscriptions and view them. |
| MANAGE_OWNED_ITEMS | Allows staff to add, delete and view a users owned items. |
| MANAGE_GIFTCARDS | Allows staff to add and delete gift cards from users. |
| OWNER | Allows every permission listed and can't be overridden by any permission. |
| MANAGE_FORMS | Allows staff to create, delete, edit, and view all forms. |
| MANAGE_QUOTES | Allows a user to create, update, and delete quotes. |
