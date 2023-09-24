
/GET /api/invoice/invoice_id
Returns an array of all invoices. Use an optional filter to get invoices by status.

- filter [Query] Can be; 'all', 'paid', 'unpaid', or 'cancelled'. Defaults to 'all'.

= [
	{
		"id": 1,
		"userId": "282762192544333827",
		"items": [
			{
				"title":"Changed",
				"description":"Item Description",
				"price":"11.99",
				"productId":null,
				"subId":null
			}
		],
		"due": "1650360961382",
		"status": "Cancelled",
		"createdAt": "1650360961382",
		"username": null,
		"tos": null,
		"memo": null
	}
]
/GET

/GET /api/invoice/:invoice_id
Returns an object with the requested invoice.

- invoice_id The invoice ID to be fetched.

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
  "username": "faxes"
}
/GET

/POST /api/invoice
Creates an invoice with the supplied information for it.

- uid* [String](/c/faxstore/types#string) The accounts user ID to link the invoice too.
- username [String](/c/faxstore/types#string) The accounts username, optional.
- items* [Array](/c/faxstore/types#array) A JSON array of [items](/c/faxstore/types#invoice-items) to have in the invoice.
- due [Timestamp](/c/faxstore/types#timestamp) Unix timestamp of when the invoice is due.
- status [String](/c/faxstore/types#string) The status of the invoice. Default 'Paid'.
- notify [Boolean](/c/faxstore/types#boolean) Whether to send the user a notification.

= {
    "id": 12,
    "createdAt": "1677935185833",
    link: "https://example.com/invoice/12"
}
/POST

/PATCH /api/invoice/:invoice_id
Modifies an existing invoice with the updated information.

- invoice_id The invoice ID to be updated.

= {
  "id": 12,
}
/PATCH

/DELETE /api/invoice/:invoice_id
Deletes an existing invoice from FaxStore. This does not mark it as cancelled, it fully removes it.

- invoice_id The invoice ID to be deleted.

= 200
/DELETE

*All requests require the Authorization header to be passed with your authorization token.*
