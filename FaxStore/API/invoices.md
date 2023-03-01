The invoice API endpoints allow you to create, edit, and delete invoices on FaxStore.

/POST /api/invoice
Create an invoice and optionally have it notify the user.

- uid [String] The accounts user ID to link the invoice too.
- username [String] The accounts username, optional.
- items [Array] A JSON array of [items](#) to have in the invoice.
- due [Timestamp] Unix timestamp of when the invoice is due.
- status [String] The status of the invoice. Default 'Paid'.

= response

/POST

/PATCH /api/invoice/<invoice_id>
Edit or modify an existing invoice.

- param

= response

/PATCH

/DELETE /api/invoice/<invoice_id>
Delete an existing invoice.

- invoice_id The invoice ID to be deleted. Passed as a URL parameter.

= response

/DELETE
