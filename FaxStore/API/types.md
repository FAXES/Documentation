This page goes through all the content types that are used in FaxStore. Mainly within it's API mentioning the type of data entry and an example of each.

#### String
The `String` object is used to represent and manipulate a sequence of characters. Strings are useful for holding data that can be represented in text form.

#### Array
The `Array` object, as with arrays in other programming languages, enables storing a collection of multiple items under a single variable name.

#### Boolean
A `true` or `false` value.

#### Timestamp
A `Timestamp` is represented as an Integer which is formated by the number of milliseconds elapsed since the epoch, which is defined as the midnight at the beginning of January 1, 1970, UTC.
For example this would look like `1677935185833`

#### Integer / Number
A `Number` is a digit based value which is not wrapped in a string or other form. Eg; `546`.

#### Invoice Items
An `Object` which contains data for invoices. Supports multiple `Array` entries and *doesn't* require the `productId`, `subId`, and `url` options. Example;
```
[
  {
    title: "Item One",
    url:"https://weblutions.com/store/itemone",
    description: "Item one is the best product ever!",
    price: "9.99",
    productId: null,
    subId: null
  },
  {
    title: "Item Two",
    description: "Custom item two",
    price: "5.00",
  },
]
```



---

*Ref; [developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects)*
