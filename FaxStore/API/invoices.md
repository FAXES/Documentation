The invoice API endpoints allow you to create, edit, and delete invoices on FaxStore.

/POST /api/invoice
Create an invoice and sed it to a user.

- dff

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
