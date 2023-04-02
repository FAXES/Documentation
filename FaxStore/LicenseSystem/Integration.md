This section covers the backend API calls for the license system along with validating the product(s) you wish to authorise.

::: info
Simply placing the license request into a program doesn't guarantee security for the product. Research ways to further secure your product via manipulation methods in your programming language.
:::


**Contents:**
- [Single Request Format](#single-request)
- [Multiple Request Format](#multiple-request)
- [Examples](/c/faxstore/license-system-examples)
- [V1 Request](#v1-request)

---

## Single Request

Make a single product request to authorise a license key.

**Required Options:**
- `PRODUCT_ID'` the FaxStore item product ID.
- `USERS_LICENSE_KEY` the authorisation key from the license system.

**Optional Options:**
- `info` Query option to log additional details.
- `log` Query Boolean option to set to make logs not log.


```css
Type: POST
URL: 'https://license.your.domain/api/check/PRODUCT_ID'
Headers:
    User-Agent: '*'
    Accept:  'application/json, text/plain, */*'
    authorization: USERS_LICENSE_KEY
Parameters:
    info: 'string of details'
    log: false
```

## Multiple Request

Make an API call to the license system to see if a key matches any of an array of items.

**Required Options:**
- `proIds'`Query array of FaxStore item product IDs.
- `USERS_LICENSE_KEY` the authorisation key from the license system.

**Optional Options:**
- `info` Query option to log additional details.
- `log` Query Boolean option to set to make logs not log.


```css
Type: POST
URL: 'https://license.your.domain/api/check/multiple'
Headers:
    User-Agent: '*'
    Accept:  'application/json, text/plain, */*'
    authorization: USERS_LICENSE_KEY
Parameters:
    info: 'string of details'
    log: false
    proIds: [8, 16]
```


### V1 Request

The license system comes with required and optional options when making the request.

Required options:

- Product Id - the FaxStore item listing Id.
- Users License Key - the users license key for this product located on the license dashboard.


Optional Options:

- `log` - setting this to `false` will disable the the request being put into the 'Previous Auths' table.
- `info` - information or details that can be passed through the request and logged into the 'Previous Auths' table.


---

```css
Type: POST
URL: 'https://license.your.domain/api/checkitem/PRODUCT_ID'
Headers:
    User-Agent: '*'
    Accept:  'application/json, text/plain, */*'
    authorization: USERS_LICENSE_KEY
```

Success Response Information: (Object)
```js
{
  status: 'OK',
  pass: true,
  details: 'Authorisation completed!'
}
```

Failed Response Information: (Object)
```js
{
  status: 'NOT FOUND',
  pass: false,
  details: 'The supplied license key was not found. Please check your auth key is correct - https://license.my.domain'
}
```
