Statistics Tracking enables the ability to create custom fields to track statistics.


/POST /api/stat/:STAT_ID
Add a statistic to a project's connected statistics.

- :STAT_ID [URL] defines the statistic to send the data to
- title [Body] Add the title to add to the statistic entry
- data [Body] Contains the data object, an example is below
- expiresAt [Body] A MS timestamp of when the statistic entry will be deleted

= [201] Created statistic.
/POST

Data example:
```json
{"title":"My Title","data":{"Earned":2,,"Host":"your.domain"},"expiresAt":"1662092459618"}
```

Here is an example in Node.Js of how to complete this request using the fetch API.

```js
let url = 'http://feedback.example.com/api/stat/4';

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

Data keys are keys that we use in our API requests. These should be line separated for multiple to e in the request. They can contain spaces, -, and _ characters. However no additional special characters.

Data keys are shown in their own panels on the relevant statistic page. See the below image.

![alt](https://weblutions.com/i/y9gzF3.png)

When completing our API request, ensure the Data keys are the same as those created via the staff panel. Number data sets will sum the values together, whereas string data sets will sum plus one per set.
