This section covers the backend API calls for the license system along with validating the product(s) you wish to authorise.

:::info
Simply placing the license request into a program doesn't guarantee security for the product. Research ways to further secure your product via manipulation methods in your programming language.
:::


**Contents:**
- [Single Request Format](#single-request)
- [Multiple Request Format](#multiple-request)
- [Examples](/c/faxstore/license-system-examples)
- [V1 Request](#v1-request)

## Single Request

/POST /api/check/:PRODUCT_ID
Check a single license key against the system to confirm it complies with all its set conditions and that it's valid.

- PRODUCT_ID [URL] the FaxStore item product ID
- Authorization [Header] The license key to check/authorise
- info [Body] Additional notes to send with the request
- log [Body] Whether to log the license request or not, by default all requests are logged

= 200 = {
    status: "AUTHORISED",
    pass: true,
    details: `Authorisation completed - https://license.example.com`
}
/POST

## Multiple Request

Make an API call to the license system to see if a key matches any of an array of items.

/POST /api/check/multiple
Check a single license key against the system to confirm it complies with all its set conditions and that it's valid.
This method allows for multiple products to be provided if any have the matching license key it authorises.

- Authorization [Header] The license key to check/authorise
- proIds [Body] An array of product IDs to have checked
- info [Body] Additional notes to send with the request
- log [Body] Whether to log the license request or not, by default all requests are logged

= 200 = {
    status: "AUTHORISED",
    pass: true,
    details: `Authorisation completed - https://license.example.com`
}
/POST


### V1 Request

:::danger
Please note the V1 API has been removed from the License System in versions 1.9.0 and above. If you really need to use the V1 API, you can load [this JS file](https://weblutions.com/u/L8KleI.js) as an extension.
:::

```css
Type: POST
URL: 'https://license.your.domain/api/checkitem/PRODUCT_ID'
Headers:
    User-Agent: '*'
    Accept:  'application/json, text/plain, */*'
    authorization: USERS_LICENSE_KEY
```
