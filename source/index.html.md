---
title: API Reference

language_tabs:
  - javascript

toc_footers:
  - <a href='http://vivopoint.com' target="_blank">Visit VivoPoint</a>

includes:
  - errors

search: true
---



# Introduction

VivoPoint API documentation on how controllers should structure their API
endpoints to allow data retrival from the VivoPoint system.

Right now the VivoPoint system uses Ruby to ingest data but the controller
API itself should communicate via JSON. To this end, both only JavaScript
examples (in the dark area to the right) have been provided.



# Authentication


```javascript
const vapi = require('vapi');

let api = vapi.authorize('myapikey');
```

> Make sure to replace `myapikey` with your API key.

Controllers will need to support authentication. This will require working
with controller providers to determine what type of authentication works best
for them (OAuth, HTTPBasic).

One potential method of authentication is by using API keys. Keys allow
access to the API. We could _potentially_ have API keys available via the
controller itself and then map those into each corresponding system in the
VivoPoint admin.

We expect controllers will require an API key to be included in all API
requests.

<aside class="notice">
You must replace <code>myapikey</code> with your personal API key.
</aside>



# Snapshot

## Get current device data

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

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

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
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

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

