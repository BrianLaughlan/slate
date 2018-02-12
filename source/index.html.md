---
title: SurveyHero API

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://www.surveyhero.com' target='_blank'>Powered by SurveyHero.com</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the SurveyHero API documentation.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: YOUR_API_KEY_HERE"
```

> Make sure to replace `YOUR_API_KEY_HERE` with your API key.

SurveyHero uses API keys to allow access to the API. You can register a new API key in your [SurveyHero account](https://www.surveyhero.com/user/account).

The API key must be included in all API requests to the server in a header that looks like the following:

`Authorization: YOUR_API_KEY_HERE`

<aside class="notice">
You must replace <code>YOUR_API_KEY_HERE</code> with your personal API key.
</aside>

# Surveys

## Get All Surveys

```shell
curl "https://surveyhero.com/api/surveys"
  -H "Authorization: YOUR_API_KEY_HERE"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "title": "My First Survey",
    "number_of_questions": 10,
    "number_of_responses": 100
  },
  {
    "id": 2,
    "title": "My Other Survey",
    "number_of_questions": 10,
    "number_of_responses": 100
  }
]
```

This endpoint retrieves all surveys from the account associated with the API key.

### HTTP Request

`GET https://surveyhero.com/api/surveys`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_shared_surveys | false | If set to true, the result will also include surveys that have been shared with the user.
include_deleted_surveys | false | If set to true, the result will also include surveys that the user has deleted. Note, this only includes surveys which are still currently recoverable.

## Get a Specific Survey

```shell
curl "https://surveyhero.com/api/surveys/2"
  -H "Authorization: YOUR_API_KEY_HERE"
```

> The above command returns JSON structured like this:

```json
{
"id": 2,
"title": "My Other Survey",
"number_of_questions": 10,
"number_of_responses": 100
}
```

This endpoint retrieves a specific survey.

### HTTP Request

`GET https://surveyhero.com/api/surveys/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the survey to retrieve