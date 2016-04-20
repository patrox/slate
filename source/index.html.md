---
title: Kraken API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Common

## Info

```shell
curl "http://example.com/info"
```

### HTTP Request

`GET http://example.com/info`

## Individual healthcheck

```shell
curl "http://example.com/individual-healthcheck/deadlocks"
```

### HTTP Request

`GET http://example.com/individual-healthcheck/{name}`

# Schedule API

## Get broadcasts

```shell
curl "http://example.com/data/NL/broadcasts"
```

### HTTP Request

`GET http://example.com/data/{region}/broadcasts`

## Get specific broadcast

```shell
curl "http://example.com/data/NL/broadcasts/e-326z3ayal-1elp0t"
```

### HTTP Request

`GET http://example.com/data/{region}/broadcasts/{id}`

# Remote Control API

## Tune to a channel

```shell
curl -XPOST "http://example.com/NL/users/123/smartcards/123123123/tune/channel"
```

### HTTP Request

`POST http://example.com/{countryCode}/users/{userId}/smartcards/{smartCardId}/tune/channel`

## Schedule a recording

```shell
curl -XPOST "http://example.com/NL/users/123/smartcards/123123123/recordings/broadcast"
```

### HTTP Request

`POST http://example.com/{countryCode}/users/{userId}/smartcards/{smartCardId}/recordings/broadcast`

## Get recordings

```shell
curl "http://example.com/NL/users/123/smartcards/123123123/recordings"
```

### HTTP Request

`GET http://example.com/{countryCode}/users/{userId}/smartcards/{smartCardId}/recordings`

# Customer Data

## Get profile

```shell
curl "http://example.com/NL/customers/123123/profile"
```

### HTTP Request

`GET http://example.com/{countryCode}/customers/{customerId}/profile`

## Update default smartcard

```shell
curl -XPUT "http://example.com/NL/customers/123123/profile"
```

### HTTP Request

`PUT http://example.com/{countryCode}/customers/{customerId}/profile`

## Get entitlements

```shell
curl "http://example.com/NL/customers/123123/entitlements"
```

### HTTP Request

`GET http://example.com/{countryCode}/customers/{customerId}/entitlements`

# Kittens

## Get All Kittens

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
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

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
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

