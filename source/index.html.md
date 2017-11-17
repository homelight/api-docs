---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - ruby
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the HomeLight API! 

This API follows the JSON:API Specification. You can view that <a href='http://jsonapi.org/'>here</a>.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Agents

## Find an Agent

`GET /api/vX/agents/:id`

### Description

Retrieves information about a specific agent.

Parameter | Required | Default | Options
--------- | -------- | ------- | -------
id | yes | none | none
include | no | none | preferences, transactions, metrics, badges, performance, awards


```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
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

# Agent Preferences

## All

`GET /api/vX/agents/:id/preferences`

### Description

Retrieves all of the agent preferences for a specific agent.

<aside class="warning">This can be a very slow call.</aside>

## Client Greetings

Client Greetings are shown on agent result cards in the **CLient Portal**.

> GET

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

> UPDATE

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

> DELETE

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

### GET

`GET /api/vX/agents/:id/preferences/greetings`


### UPDATE

`PATCH /api/vX/agents/:id/preferences/greetings`

### DELETE

`DELETE /api/vX/agents/:id/preferences/greetings`

<aside class="warning">This method remove the agents specific client greeting which will cause the default client greetings to be used when their agent card is shown.</aside>

## Professional Details

`GET /api/vX/agents/:id/preferences/professional-details`

### Description

Retrieves the professional details preferences for a specific agent

## Referral Settings

`GET /api/vX/agents/:id/preferences/referral-settings`

### Description

Retrieves the referral settings preferences for a specific agent

## Location Preferences

`GET /api/vX/agents/:id/preferences/locations`

### Description

Retrieves the location preferences for a specific agent

## Vacation Settings

`GET /api/vX/agents/:id/preferences/vacation-settings`

### Description

Retrieves the vacation settings preferences for a specific agent

## Specialties

`GET /api/vX/agents/:id/preferences/specialties`

### Description

Retrieves the specialty preferences for a specific agent



<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>


<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>
