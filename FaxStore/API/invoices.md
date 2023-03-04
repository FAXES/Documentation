The invoice API endpoints allow you to create, edit, and delete invoices on FaxStore.

/GET /api/invoice/<invoice_id>
Fetch an existing invoice's details by ID.

= {
  "id": 25,
  "userId": "117947035129820949693",
  "items": [
    {
      "title": "1",
      "url": "",
      "description": "11",
      "price": "1.99",
      "productId": null,
      "subId": null
    }
  ],
  "due": "1670371200000",
  "status": "Overdue",
  "createdAt": "1669629960260",
  "username": "Josh Mannens"
}
/GET

/POST /api/invoice
Create an invoice and optionally have it notify the user.

- uid [String](/c/faxstore/types#string) The accounts user ID to link the invoice too.
- username [String](/c/faxstore/types#string) The accounts username, optional.
- items [Array](/c/faxstore/types#array) A JSON array of [items](/c/faxstore/types#invoice-items) to have in the invoice.
- due [Timestamp](/c/faxstore/types#timestamp) Unix timestamp of when the invoice is due.
- status [String](/c/faxstore/types#string) The status of the invoice. Default 'Paid'.
- notify [Boolean](/c/faxstore/types#boolean) Whether to send the user a notification.

= {
    invoiceID: 12,
    createdAt: 1677935185833
}

/POST

/PATCH /api/invoice/<invoice_id>
Edit or modify an existing invoice.

- param

= {
  test: true,
  message: "string here",
  inty: 1234
}

/PATCH

/DELETE /api/invoice/<invoice_id>
Delete an existing invoice.

- invoice_id The invoice ID to be deleted. Passed as a URL parameter.

= response

/DELETE
