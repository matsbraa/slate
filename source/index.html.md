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
$.ajax({
  type: 'GET',
  url: 'https://services.bdo.no/feedback/api/queries',
  beforeSend: function(request) {
    request.setRequestHeader("Authorization", "YOUR_API_KEY");
  },
  success: function(resp) {

  },
  error: function(err) {

  }
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "queryId": 0001,
    "groupKey": "2",
    "groupName": "Klimaundersøkelser",
    "projectId": 1,
    "projectKey": "7ea0ea43",
    "projectName": "Get Midt-Norge",
    "surveyId": 2,
    "surveyName": "Pulsmåling 1 : Samhandling",
    "surveyKey": "4baa6310",
    "queryName": "2016  - Mars",
    "queryKey": "518dad",
    "isAnonymous": false,
    "endDate": "2016-03-23T00:00:00Z",
    "endDateFormatted": "23.03.16",
    "previewUrl": "",
    "reportUrl": "",
    "anonymousUrl": "",
    "statusUrl": "",
    "participantCount": 37,
    "deliveryCount": 29,
    "percentageCount": "78,38 %"
  },
  {
    "queryId": 0002,
    "groupKey": "2",
    "groupName": "Klimaundersøkelser",
    "projectId": 2,
    "projectKey": "7ea0ea43",
    "projectName": "Get Midt-Norge",
    "surveyId": 2,
    "surveyName": "Pulsmåling 1 : Samhandling",
    "surveyKey": "4baa6310",
    "queryName": "August-2016",
    "queryKey": "e8fb7026",
    "isAnonymous": false,
    "endDate": "2016-08-30T23:59:00Z",
    "endDateFormatted": "30.08.16",
    "previewUrl": "",
    "reportUrl": "",
    "anonymousUrl": "",
    "statusUrl": "",
    "participantCount": 39,
    "deliveryCount": 33,
    "percentageCount": "84,62 %"
  }
]
```

This endpoint retrieves all queries.

### HTTP Request

`GET https://services.bdo.no/feedback/api/queries`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
x | false | If set to true, the result will also include x.
y | true | If set to false, the result will include y.

## Get a Specific Query


```javascript
$.ajax({
  type: 'GET',
  url: 'https://services.bdo.no/feedback/api/queries/1',
  beforeSend: function(request) {
    request.setRequestHeader("Authorization", "YOUR_API_KEY");
  },
  success: function(resp) {

  },
  error: function(err) {

  }
});
```

> The above command returns JSON structured like this:

```json
[
  {
    "queryId": 0002,
    "groupKey": "2",
    "groupName": "Klimaundersøkelser",
    "projectId": 2,
    "projectKey": "7ea0ea43",
    "projectName": "Get Midt-Norge",
    "surveyId": 2,
    "surveyName": "Pulsmåling 1 : Samhandling",
    "surveyKey": "4baa6310",
    "queryName": "August-2016",
    "queryKey": "e8fb7026",
    "isAnonymous": false,
    "endDate": "2016-08-30T23:59:00Z",
    "endDateFormatted": "30.08.16",
    "previewUrl": "",
    "reportUrl": "",
    "anonymousUrl": "",
    "statusUrl": "",
    "participantCount": 39,
    "deliveryCount": 33,
    "percentageCount": "84,62 %"
  }
]
```

This endpoint retrieves a specific kitten.

### HTTP Request

`GET https://services.bdo.no/feedback/api/queries{ID}`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the query to retrieve
