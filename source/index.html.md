---
title: API Reference

language_tabs:
  - shell
  - ruby

toc_footers:
  - <a href='http://getquipu.com'>Quipu</a>

includes:
  - errors

search: true
---

# Introduction

## REST API Conventions

The Quipu API is based on ... <a href="http://jsonapi.org/">JSON API</a>

All request should include the header `Accept: application/vnd.quipu.v1+json`.

# Authentication

We use OAuth2 to authorize the requests.

## Getting an access token

> Example request

```shell
curl "http://getquipu.com/oauth/token" \
  -H "Authorization: Basic MGE2NzJjZDY5YmFkYjE1NjM4MWUyOTdlZjJkZjk4ZmE1Mjg5ZDdkNTA4 ..." \
  -H "Content-Type: application/x-www-form-urlencoded;charset=UTF-8" \
  -d "grant_type=client_credentials"
```

```ruby
require 'oauth2'

oauth_client = OAuth2::Client.new("<client_id>", "<client_secret>", site: 'https://getquipu.com')

access_token = oauth_client.client_credentials.get_token
```

> Example response

```shell
{
  "token_type":    "bearer",
  "created_at":    1456339025,
  "access_token":  "7c74b8e69bdd19a90e1ffaf987ada2ca67b948b0bed7b2cf95ad58f5ecb14294",
  "refresh_token": null,
  "expires_at":    1456346225
}
```

```ruby
{
  token_type:    "bearer",
  created_at:    1456339025,
  access_token:  "7c74b8e69bdd19a90e1ffaf987ada2ca67b948b0bed7b2cf95ad58f5ecb14294",
  refresh_token: nil,
  expires_at:    1456346225
}
```

To get an access token you will need the account's `app_id` and `app_secret` credentials.

<aside class="notice">
  When a token expires you will need to request for a new one
</aside>

## Using the token in the requests

Blah blah blah

> Example request

```shell
curl "http://getquipu.com/invoices" \
  -H "Authorization: Bearer be32259bd1d0f4d3d02bcc0771b1b507e2b666ba9e9ba3d7c5639e853f722eb4" \
  -H "Accept: application/vnd.quipu.v1+json"
```
