---
title: API v
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id=""> v</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URLs:

* <a href="http://localhost:4000">http://localhost:4000</a>

# Authentication

- HTTP Authentication, scheme: bearer

<h1 id="-authentication">authentication</h1>

## Po2Web.AuthenticationController.session

<a id="opIdPo2Web.AuthenticationController.session"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/auth/session/{client_id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/auth/session/{client_id} HTTP/1.1
Host: localhost:4000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "api_key": "po2_123456789",
  "secret": "sandbox_123456789"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('http://localhost:4000/api/auth/session/{client_id}',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/auth/session/{client_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/auth/session/{client_id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:4000/api/auth/session/{client_id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:4000/api/auth/session/{client_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:4000/api/auth/session/{client_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

<h3 id="po2web.authenticationcontroller.session-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|client_id|path|integer|true|Client ID|
|body|body|[AuthParams](#schemaauthparams)|false|Client params|

> Example responses

> 200 Response

```json
{
  "token": "eyJhbGciOiJIUzUxMiIsIn ... JUe4WCUMw"
}
```

<h3 id="po2web.authenticationcontroller.session-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Client response|[UserResponse](#schemauserresponse)|

### Callbacks

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
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

