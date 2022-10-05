Statistics Tracking enables the ability to create custom fields to track statistics.


### Request format

**Required parameters**
- `STAT_ID`: URL parameter of the stat ID to place the data into.
- `title`: The title of the request to display.
- `data`: An [bject](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) that contains the data to pass through the request.

**Optional parameters:**
- `expiresAt`: A string timestamp value of when the data set expires.

```css
Type: POST
URL: 'https://your.domain/api/stat/STAT_ID'
Headers:
    User-Agent: '*'
    Accept:  'application/json, text/plain, */*'
    authorization: API_AUTH_KEY
Parameters:
    title: 'Title'
    data: {}
    expiresAt: '1662092459618'
```

---

Here is an example in Node.Js of how to complete this request using the fetch API.

```js
const fetch = require('node-fetch');

let url = 'http://localhost:3000/api/stat/4';

let options = {
  method: 'POST',
  headers: {authorization: '1234'},
  body: '{"title":"My Title","data":{"Earned":2,,"Host":"your.domain"},"expiresAt":"1662092459618"}'
};

fetch(url, options)
  .then(res => res.json())
  .then(json => console.log(json))
  .catch(err => console.error('error:' + err));
```

## Creating a Tracked Statistic

Data keys are keys that we usee in our API request. These should be line seperated for multiple to e in the request. They can contain spaces, -, and _ characters. However no additional special characters.

Data keys are shown in their own panels on the relevant statistic page. See below image.

![alt](https://weblutions.com/i/y9gzF3.png)

When completing our API request, make sure the Data keys are the exact same to the keys created via the staff panel. Number data sets will sum the values all up together where as, string data sets will sum plus one per set.
