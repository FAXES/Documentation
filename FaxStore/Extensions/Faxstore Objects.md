Here are some helpful tools in regards to [FaxStore Events](/c/faxstore/events) arguments.

## User Object

Below you will find all the info returned when the `userObject` is called.

```json
{
"loggedIn":true,
"id":"668497496124686347",
"username":"Shawn E.",
"avatar":"36346a9dd401b58d5aa3a0a793d25f5b",
"discriminator":"5229",
"guilds":null,
"bitfield":"0",
"banned":0,
"cart":[],
"promoCode":[null,null],
"authType":"discord",
"notis":[],
"hidebar":false,
"cookBar":true
}
```

## Store Item Object

Below you will find all the info returned when the `storeItem` is called.

```json
{
"id":1,
"title":"Store Item",
"urlId":"item",
"position":1,
"price":"20",
"description":"Cool Very New Store Item",
"credits":"Crediys",
"demoLink":"",
"createdAt":"1660248654988",
"itemType":1,
"onSale":0,
"requiredItem":null,
"tags":"",
"featureImage":"/images/feat-oVIxrEu-_vcP7Z95uai2QAo73.png",
"galleryImages":".",
"discordRole":"",
"hidden":0,
"usingLicenseSystem":0,
"status":"30",
"hiddenonstorepage":0,
"giftcard":0,
"paused":0,
"linked":"",
"inaccount":1,
"secPayeePayPal":"",
"secPayeeStripe":""
}
```

## Release Object

Below you will find all the info returned when the `release` is called.

```json
{
"title":"Release Title",
"version":"Release Version",
"changes":"Changes"
}
```

## Form Object

Below you will find all the info returned when the `formObject` is called.

```json
{
  "id":2,
  "title":"Form",
  "urlId":"form",
  "fields":"[{\"type\":\"text\",\"q\":\"Text // Represents a basic text field question \",\"opts\":null},{\"type\":\"area\",\"q\":\"TextArea // Creates the question as a text area \",\"opts\":null},{\"type\":\"drop\",\"q\":\" Dropdown \",\"opts\":[\" option1\",\"option2\",\"option3\"]}",
  "viewers":"",
  "allowReplies":1,
  "createdAt":"1659476388071"
}
```

## Submission Object

Below you will find all the info returned when the `submissionObject` is called.

```json
[
{"q":"Question 1 ","a":"Answer 1"},
{"q":"Question 2 ","a":"Answer 2"},
{"q":"Question 3 ","a":"Answer 3"},
{"q":"Question 4 ","a":"Answer 4"},
{"q":" Question 5 ","a":"option3"}
]
```

## Blog Post Object

Below you will find all the info returned when the `blogpost` is called.

```json
{
"title":"Blog Title",
"urlId":"UrlID",
"catId":"1",
"blogcontent":"Blog Content",
"image":"/images/blogfeat-r20ETCaOEh3F8T08bNd5wt_c9.png"
}
```

## Review Object

Below you will find all the info returned when the `reviewObject` is called.

```json
{
"product":"Store Item",
"stars":"2",
"comment":"asdasd"
}
```

---

> Special thanks to [Shawn E.](https://weblutions.com/user/668497496124686347) who maintains this documentation page.
