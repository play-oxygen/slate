---
title: Play Oxygen API v0.1.0
language_tabs:
  - shell: curl
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="play-oxygen-api">Play Oxygen API v0.1.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URLs:

* <a href="http://localhost:4000">http://localhost:4000</a>

<h1 id="play-oxygen-api-authentication">Authentication</h1>

## Session

<a id="opIdSession"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/auth/session/{client_id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

`POST /api/auth/session/{client_id}`

*Authentication for Client*

> Body parameter

```json
{
  "api_key": "po2_123456789",
  "secret": "sandbox_123456789"
}
```

<h3 id="session-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|client_id|path|integer|true|Client ID|
|body|body|[AuthParams](#schemaauthparams)|false|Client params|
|» api_key|body|string|true|API Key|
|» secret|body|string|true|API secret|

> Example responses

> 200 Response

```json
{
  "token": "eyJhbGciOiJIUzUxMiIsIn ... JUe4WCUMw"
}
```

<h3 id="session-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Client response|[UserResponse](#schemauserresponse)|

### Callbacks

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_AuthParams">AuthParams</h2>
<!-- backwards compatibility -->
<a id="schemaauthparams"></a>
<a id="schema_AuthParams"></a>
<a id="tocSauthparams"></a>
<a id="tocsauthparams"></a>

```json
{
  "api_key": "po2_123456789",
  "secret": "sandbox_123456789"
}

```

AuthParams

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|api_key|string|true|none|API Key|
|secret|string|true|none|API secret|

<h2 id="tocS_UserResponse">UserResponse</h2>
<!-- backwards compatibility -->
<a id="schemauserresponse"></a>
<a id="schema_UserResponse"></a>
<a id="tocSuserresponse"></a>
<a id="tocsuserresponse"></a>

```json
{
  "token": "eyJhbGciOiJIUzUxMiIsIn ... JUe4WCUMw"
}

```

UserResponse

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|token|string|false|none|JWT|

