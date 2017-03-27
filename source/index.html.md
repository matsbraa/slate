---
title: Feedback API Reference

language_tabs:
  - javascript
  - csharp

toc_footers:

includes:
  - errors

search: true
---

# Introduction

Welcome to the Feedback API! You can use our API to access Feedback API endpoints, which can get information on various surveys, projects, and users in our database.

We have language bindings in Javascript and C#! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```csharp
var httprequest;
```

```javascript
var thisIsJavScript;
```

> Make sure to replace `YOUR_API_KEY` with your API key.

Information about how to obtain JWT TOKEN and include it in the request header.
We need to make a decision on how to handle tokens.
Included it in the request header like this:

`Authorization: Bearer YOUR_API_KEY`

<aside class="notice">
You must replace <code>YOUR_API_KEY</code> with your personal API key.
</aside>

# Queries
## Get All Queries

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Query


```javascript
const query = require('query');

let api = query.authorize('meowmeowmeow');
let max = api.query.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

### HTTP Request

`GET http://example.com/Queries/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the query to retrieve
