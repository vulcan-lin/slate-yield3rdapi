---
title: Yield Dance API v2
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
search: false
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: widdershins v4.0.1

---

<h1 id="yield-dance-api">Yield Dance API v2</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Welcome to the Yield Dance API! You can use our API to access Yield Dance API endpoints.

Base URLs:

* <a href="https://mixin-api.yield.dance/api/v2">https://mixin-api.yield.dance/api/v2</a>

<h1 id="yield-dance-api-authorization">Authorization</h1>

## post__auth

> Code samples

```shell
# You can also use wget
curl -X POST https://mixin-api.yield.dance/api/v2/auth \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://mixin-api.yield.dance/api/v2/auth HTTP/1.1
Host: mixin-api.yield.dance
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "mixin_token": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('https://mixin-api.yield.dance/api/v2/auth',
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

result = RestClient.post 'https://mixin-api.yield.dance/api/v2/auth',
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

r = requests.post('https://mixin-api.yield.dance/api/v2/auth', headers = headers)

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
    $response = $client->request('POST','https://mixin-api.yield.dance/api/v2/auth', array(
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
URL obj = new URL("https://mixin-api.yield.dance/api/v2/auth");
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
    req, err := http.NewRequest("POST", "https://mixin-api.yield.dance/api/v2/auth", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /auth`

Auth with Yield Dance. You must OAuth with mixin firstly to obtain the mixin token

> Body parameter

```json
{
  "mixin_token": "string"
}
```

<h3 id="post__auth-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AuthReq](#schemaauthreq)|true|Yield Dance Auth request|

> Example responses

> 200 Response

```json
{
  "token": "string"
}
```

<h3 id="post__auth-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Response of Yield Dance auth|[AuthResp](#schemaauthresp)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Common response|[commonResponse](#schemacommonresponse)|

<aside class="success">
 
</aside>

<h1 id="yield-dance-api-order">Order</h1>

## get__orders

> Code samples

```shell
# You can also use wget
curl -X GET https://mixin-api.yield.dance/api/v2/orders \
  -H 'Accept: application/json' \
  -H 'Authorization: string'

```

```http
GET https://mixin-api.yield.dance/api/v2/orders HTTP/1.1
Host: mixin-api.yield.dance
Accept: application/json
Authorization: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'string'
};

fetch('https://mixin-api.yield.dance/api/v2/orders',
{
  method: 'GET',

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
  'Accept' => 'application/json',
  'Authorization' => 'string'
}

result = RestClient.get 'https://mixin-api.yield.dance/api/v2/orders',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'string'
}

r = requests.get('https://mixin-api.yield.dance/api/v2/orders', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://mixin-api.yield.dance/api/v2/orders', array(
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
URL obj = new URL("https://mixin-api.yield.dance/api/v2/orders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
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
        "Accept": []string{"application/json"},
        "Authorization": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://mixin-api.yield.dance/api/v2/orders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /orders`

return a order list

<h3 id="get__orders-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string|true|Authorization|
|round_status|query|string|false|status of round|
|page_current|query|integer|false|current page index|
|page_size|query|integer|false|size of page|

#### Enumerated Values

|Parameter|Value|
|---|---|
|round_status|FUNDING|
|round_status|FUND_END|

> Example responses

> 200 Response

```json
{
  "code": 0,
  "data": [
    {
      "amount": "string",
      "apy_real": "string",
      "clearing_amount": "string",
      "clearing_asset_id": "string",
      "created_at": "string",
      "fraction_amount": "string",
      "fraction_asset_id": "string",
      "insurances": [
        {
          "compensation_amount": "string",
          "compensation_asset_id": "string",
          "compensation_price": "string",
          "description": "string",
          "exercised": true,
          "id": 0,
          "label": "string",
          "type": "string"
        }
      ],
      "mixin_user_id": "string",
      "mixin_user_name": "string",
      "oid": "string",
      "premium_amount": "string",
      "premium_asset_id": "string",
      "refund_amount": "string",
      "rid": "string",
      "round": {
        "apy_max": "string",
        "apy_min": "string",
        "clearing_asset_id": "string",
        "clearing_at": "string",
        "created_at": "string",
        "exercised": true,
        "expiry": "string",
        "funding_asset_id": "string",
        "hide": true,
        "insurance_enable": true,
        "max_fund": "string",
        "min_fund": "string",
        "rid": "string",
        "status": "string",
        "strike": "string",
        "updated_at": "string",
        "vault_type": "string"
      },
      "underlying_asset_id": "string",
      "underlying_price": "string",
      "updated_at": "string"
    }
  ],
  "msg": "string",
  "pagination": {
    "current": 0,
    "size": 0,
    "total": 0
  }
}
```

<h3 id="get__orders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Order item info|[ListOrderResponse](#schemalistorderresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Common response|[commonResponse](#schemacommonresponse)|

<aside class="success">
 
</aside>

## post__orders

> Code samples

```shell
# You can also use wget
curl -X POST https://mixin-api.yield.dance/api/v2/orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: string'

```

```http
POST https://mixin-api.yield.dance/api/v2/orders HTTP/1.1
Host: mixin-api.yield.dance
Content-Type: application/json
Accept: application/json
Authorization: string

```

```javascript
const inputBody = '{
  "order_amount": "string",
  "proxy_info": {
    "manufacturer": "string",
    "mixin_user_id": "string"
  },
  "rid": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'string'
};

fetch('https://mixin-api.yield.dance/api/v2/orders',
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
  'Accept' => 'application/json',
  'Authorization' => 'string'
}

result = RestClient.post 'https://mixin-api.yield.dance/api/v2/orders',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'string'
}

r = requests.post('https://mixin-api.yield.dance/api/v2/orders', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://mixin-api.yield.dance/api/v2/orders', array(
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
URL obj = new URL("https://mixin-api.yield.dance/api/v2/orders");
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
        "Authorization": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://mixin-api.yield.dance/api/v2/orders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /orders`

submit a order to round

> Body parameter

```json
{
  "order_amount": "string",
  "proxy_info": {
    "manufacturer": "string",
    "mixin_user_id": "string"
  },
  "rid": "string"
}
```

<h3 id="post__orders-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string|true|Authorization|
|body|body|[OrderReq](#schemaorderreq)|true|Order info|

> Example responses

> 200 Response

```json
{
  "code": 0,
  "data": {
    "mixin_pay_url": "string",
    "mixin_transfer_trace_id": "string",
    "oid": "string",
    "order_amount": "string",
    "rid": "string",
    "status": "string"
  },
  "msg": "string"
}
```

<h3 id="post__orders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Order created info|[CreateOrderResponse](#schemacreateorderresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Common response|[commonResponse](#schemacommonresponse)|

<aside class="success">
 
</aside>

## get__orders_{oid}

> Code samples

```shell
# You can also use wget
curl -X GET https://mixin-api.yield.dance/api/v2/orders/{oid} \
  -H 'Accept: application/json' \
  -H 'Authorization: string'

```

```http
GET https://mixin-api.yield.dance/api/v2/orders/{oid} HTTP/1.1
Host: mixin-api.yield.dance
Accept: application/json
Authorization: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'string'
};

fetch('https://mixin-api.yield.dance/api/v2/orders/{oid}',
{
  method: 'GET',

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
  'Accept' => 'application/json',
  'Authorization' => 'string'
}

result = RestClient.get 'https://mixin-api.yield.dance/api/v2/orders/{oid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'string'
}

r = requests.get('https://mixin-api.yield.dance/api/v2/orders/{oid}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://mixin-api.yield.dance/api/v2/orders/{oid}', array(
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
URL obj = new URL("https://mixin-api.yield.dance/api/v2/orders/{oid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
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
        "Accept": []string{"application/json"},
        "Authorization": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://mixin-api.yield.dance/api/v2/orders/{oid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /orders/{oid}`

return a order

<h3 id="get__orders_{oid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string|true|Authorization|
|oid|path|string|true|Order id|

> Example responses

> 200 Response

```json
{
  "code": 0,
  "data": {
    "amount": "string",
    "apy_real": "string",
    "clearing_amount": "string",
    "clearing_asset_id": "string",
    "created_at": "string",
    "fraction_amount": "string",
    "fraction_asset_id": "string",
    "insurances": [
      {
        "compensation_amount": "string",
        "compensation_asset_id": "string",
        "compensation_price": "string",
        "description": "string",
        "exercised": true,
        "id": 0,
        "label": "string",
        "type": "string"
      }
    ],
    "mixin_user_id": "string",
    "mixin_user_name": "string",
    "oid": "string",
    "premium_amount": "string",
    "premium_asset_id": "string",
    "refund_amount": "string",
    "rid": "string",
    "round": {
      "apy_max": "string",
      "apy_min": "string",
      "clearing_asset_id": "string",
      "clearing_at": "string",
      "created_at": "string",
      "exercised": true,
      "expiry": "string",
      "funding_asset_id": "string",
      "hide": true,
      "insurance_enable": true,
      "max_fund": "string",
      "min_fund": "string",
      "rid": "string",
      "status": "string",
      "strike": "string",
      "updated_at": "string",
      "vault_type": "string"
    },
    "underlying_asset_id": "string",
    "underlying_price": "string",
    "updated_at": "string"
  },
  "msg": "string"
}
```

<h3 id="get__orders_{oid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Order item|[GetOrderResponse](#schemagetorderresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Common response|[commonResponse](#schemacommonresponse)|

<aside class="success">
 
</aside>

<h1 id="yield-dance-api-round">Round</h1>

## get__rounds

> Code samples

```shell
# You can also use wget
curl -X GET https://mixin-api.yield.dance/api/v2/rounds \
  -H 'Accept: application/json' \
  -H 'Authorization: string'

```

```http
GET https://mixin-api.yield.dance/api/v2/rounds HTTP/1.1
Host: mixin-api.yield.dance
Accept: application/json
Authorization: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'string'
};

fetch('https://mixin-api.yield.dance/api/v2/rounds',
{
  method: 'GET',

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
  'Accept' => 'application/json',
  'Authorization' => 'string'
}

result = RestClient.get 'https://mixin-api.yield.dance/api/v2/rounds',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'string'
}

r = requests.get('https://mixin-api.yield.dance/api/v2/rounds', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://mixin-api.yield.dance/api/v2/rounds', array(
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
URL obj = new URL("https://mixin-api.yield.dance/api/v2/rounds");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
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
        "Accept": []string{"application/json"},
        "Authorization": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://mixin-api.yield.dance/api/v2/rounds", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /rounds`

Get a round list

<h3 id="get__rounds-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|vault_type|query|string|false|Type of vault|
|hide|query|boolean|false|hide state of round [true, false]|
|status|query|string|false|Status of round|
|page_current|query|integer|false|current page index|
|page_size|query|integer|false|size of page|
|Authorization|header|string|true|Authorization|

> Example responses

> 200 Response

```json
{
  "code": 0,
  "data": [
    {
      "insurances": [
        {
          "compensation_amount": "string",
          "compensation_asset_id": "string",
          "compensation_price": "string",
          "description": "string",
          "exercised": true,
          "id": 0,
          "label": "string",
          "type": "string"
        }
      ],
      "round_info": {
        "apy_max": "string",
        "apy_min": "string",
        "clearing_asset_id": "string",
        "clearing_at": "string",
        "created_at": "string",
        "exercised": true,
        "expiry": "string",
        "funding_asset_id": "string",
        "hide": true,
        "insurance_enable": true,
        "max_fund": "string",
        "min_fund": "string",
        "rid": "string",
        "status": "string",
        "strike": "string",
        "updated_at": "string",
        "vault_type": "string"
      }
    }
  ],
  "msg": "string",
  "pagination": {
    "current": 0,
    "size": 0,
    "total": 0
  }
}
```

<h3 id="get__rounds-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of round item wrapped in common response|[ListRoundSimpleResponse](#schemalistroundsimpleresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Common response|[commonResponse](#schemacommonresponse)|

<aside class="success">
 
</aside>

# Schemas

<h2 id="tocS_AuthReq">AuthReq</h2>

<a id="schemaauthreq"></a>
<a id="schema_AuthReq"></a>
<a id="tocSauthreq"></a>
<a id="tocsauthreq"></a>

```json
{
  "mixin_token": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mixin_token|string|true|none|none|

<h2 id="tocS_AuthResp">AuthResp</h2>

<a id="schemaauthresp"></a>
<a id="schema_AuthResp"></a>
<a id="tocSauthresp"></a>
<a id="tocsauthresp"></a>

```json
{
  "token": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|token|string|false|none|none|

<h2 id="tocS_CreateOrderResponse">CreateOrderResponse</h2>

<a id="schemacreateorderresponse"></a>
<a id="schema_CreateOrderResponse"></a>
<a id="tocScreateorderresponse"></a>
<a id="tocscreateorderresponse"></a>

```json
{
  "code": 0,
  "data": {
    "mixin_pay_url": "string",
    "mixin_transfer_trace_id": "string",
    "oid": "string",
    "order_amount": "string",
    "rid": "string",
    "status": "string"
  },
  "msg": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer|false|none|none|
|data|[OrderResp](#schemaorderresp)|false|none|none|
|msg|string|false|none|none|

<h2 id="tocS_GetOrderResponse">GetOrderResponse</h2>

<a id="schemagetorderresponse"></a>
<a id="schema_GetOrderResponse"></a>
<a id="tocSgetorderresponse"></a>
<a id="tocsgetorderresponse"></a>

```json
{
  "code": 0,
  "data": {
    "amount": "string",
    "apy_real": "string",
    "clearing_amount": "string",
    "clearing_asset_id": "string",
    "created_at": "string",
    "fraction_amount": "string",
    "fraction_asset_id": "string",
    "insurances": [
      {
        "compensation_amount": "string",
        "compensation_asset_id": "string",
        "compensation_price": "string",
        "description": "string",
        "exercised": true,
        "id": 0,
        "label": "string",
        "type": "string"
      }
    ],
    "mixin_user_id": "string",
    "mixin_user_name": "string",
    "oid": "string",
    "premium_amount": "string",
    "premium_asset_id": "string",
    "refund_amount": "string",
    "rid": "string",
    "round": {
      "apy_max": "string",
      "apy_min": "string",
      "clearing_asset_id": "string",
      "clearing_at": "string",
      "created_at": "string",
      "exercised": true,
      "expiry": "string",
      "funding_asset_id": "string",
      "hide": true,
      "insurance_enable": true,
      "max_fund": "string",
      "min_fund": "string",
      "rid": "string",
      "status": "string",
      "strike": "string",
      "updated_at": "string",
      "vault_type": "string"
    },
    "underlying_asset_id": "string",
    "underlying_price": "string",
    "updated_at": "string"
  },
  "msg": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer|false|none|none|
|data|[OrderItem](#schemaorderitem)|false|none|none|
|msg|string|false|none|none|

<h2 id="tocS_Insurance">Insurance</h2>

<a id="schemainsurance"></a>
<a id="schema_Insurance"></a>
<a id="tocSinsurance"></a>
<a id="tocsinsurance"></a>

```json
{
  "compensation_amount": "string",
  "compensation_asset_id": "string",
  "compensation_price": "string",
  "description": "string",
  "exercised": true,
  "id": 0,
  "label": "string",
  "type": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|compensation_amount|string|false|none|赔付金额|
|compensation_asset_id|string|false|none|赔付资产|
|compensation_price|string|false|none|赔付格价|
|description|string|false|none|赔付描述|
|exercised|boolean|false|none|赔付状态|
|id|integer|false|none|insurance id|
|label|string|false|none|赔付标签|
|type|string|false|none|赔付类型|

<h2 id="tocS_ListOrderResponse">ListOrderResponse</h2>

<a id="schemalistorderresponse"></a>
<a id="schema_ListOrderResponse"></a>
<a id="tocSlistorderresponse"></a>
<a id="tocslistorderresponse"></a>

```json
{
  "code": 0,
  "data": [
    {
      "amount": "string",
      "apy_real": "string",
      "clearing_amount": "string",
      "clearing_asset_id": "string",
      "created_at": "string",
      "fraction_amount": "string",
      "fraction_asset_id": "string",
      "insurances": [
        {
          "compensation_amount": "string",
          "compensation_asset_id": "string",
          "compensation_price": "string",
          "description": "string",
          "exercised": true,
          "id": 0,
          "label": "string",
          "type": "string"
        }
      ],
      "mixin_user_id": "string",
      "mixin_user_name": "string",
      "oid": "string",
      "premium_amount": "string",
      "premium_asset_id": "string",
      "refund_amount": "string",
      "rid": "string",
      "round": {
        "apy_max": "string",
        "apy_min": "string",
        "clearing_asset_id": "string",
        "clearing_at": "string",
        "created_at": "string",
        "exercised": true,
        "expiry": "string",
        "funding_asset_id": "string",
        "hide": true,
        "insurance_enable": true,
        "max_fund": "string",
        "min_fund": "string",
        "rid": "string",
        "status": "string",
        "strike": "string",
        "updated_at": "string",
        "vault_type": "string"
      },
      "underlying_asset_id": "string",
      "underlying_price": "string",
      "updated_at": "string"
    }
  ],
  "msg": "string",
  "pagination": {
    "current": 0,
    "size": 0,
    "total": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer|false|none|none|
|data|[[OrderItem](#schemaorderitem)]|false|none|none|
|msg|string|false|none|none|
|pagination|[Pagination](#schemapagination)|false|none|none|

<h2 id="tocS_ListRoundSimpleResponse">ListRoundSimpleResponse</h2>

<a id="schemalistroundsimpleresponse"></a>
<a id="schema_ListRoundSimpleResponse"></a>
<a id="tocSlistroundsimpleresponse"></a>
<a id="tocslistroundsimpleresponse"></a>

```json
{
  "code": 0,
  "data": [
    {
      "insurances": [
        {
          "compensation_amount": "string",
          "compensation_asset_id": "string",
          "compensation_price": "string",
          "description": "string",
          "exercised": true,
          "id": 0,
          "label": "string",
          "type": "string"
        }
      ],
      "round_info": {
        "apy_max": "string",
        "apy_min": "string",
        "clearing_asset_id": "string",
        "clearing_at": "string",
        "created_at": "string",
        "exercised": true,
        "expiry": "string",
        "funding_asset_id": "string",
        "hide": true,
        "insurance_enable": true,
        "max_fund": "string",
        "min_fund": "string",
        "rid": "string",
        "status": "string",
        "strike": "string",
        "updated_at": "string",
        "vault_type": "string"
      }
    }
  ],
  "msg": "string",
  "pagination": {
    "current": 0,
    "size": 0,
    "total": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer|false|none|none|
|data|[[RoundInfoWithInsurance](#schemaroundinfowithinsurance)]|false|none|none|
|msg|string|false|none|none|
|pagination|[Pagination](#schemapagination)|false|none|none|

<h2 id="tocS_OrderItem">OrderItem</h2>

<a id="schemaorderitem"></a>
<a id="schema_OrderItem"></a>
<a id="tocSorderitem"></a>
<a id="tocsorderitem"></a>

```json
{
  "amount": "string",
  "apy_real": "string",
  "clearing_amount": "string",
  "clearing_asset_id": "string",
  "created_at": "string",
  "fraction_amount": "string",
  "fraction_asset_id": "string",
  "insurances": [
    {
      "compensation_amount": "string",
      "compensation_asset_id": "string",
      "compensation_price": "string",
      "description": "string",
      "exercised": true,
      "id": 0,
      "label": "string",
      "type": "string"
    }
  ],
  "mixin_user_id": "string",
  "mixin_user_name": "string",
  "oid": "string",
  "premium_amount": "string",
  "premium_asset_id": "string",
  "refund_amount": "string",
  "rid": "string",
  "round": {
    "apy_max": "string",
    "apy_min": "string",
    "clearing_asset_id": "string",
    "clearing_at": "string",
    "created_at": "string",
    "exercised": true,
    "expiry": "string",
    "funding_asset_id": "string",
    "hide": true,
    "insurance_enable": true,
    "max_fund": "string",
    "min_fund": "string",
    "rid": "string",
    "status": "string",
    "strike": "string",
    "updated_at": "string",
    "vault_type": "string"
  },
  "underlying_asset_id": "string",
  "underlying_price": "string",
  "updated_at": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|amount|string|false|none|购币金(用户实际转账购币金)|
|apy_real|string|false|none|权利金年化收益率|
|clearing_amount|string|false|none|结算数量(如:C端BTC数量)|
|clearing_asset_id|string|false|none|结算类型|
|created_at|string|false|none|none|
|fraction_amount|string|false|none|资金修剪|
|fraction_asset_id|string|false|none|货币：USDT or BTC or ETH|
|insurances|[[Insurance](#schemainsurance)]|false|none|赔付信息|
|mixin_user_id|string|false|none|none|
|mixin_user_name|string|false|none|昵称|
|oid|string|false|none|none|
|premium_amount|string|false|none|权利金收益|
|premium_asset_id|string|false|none|标的资产: USDT or BTC or ETH|
|refund_amount|string|false|none|退回购币金|
|rid|string|false|none|none|
|round|[RoundInfo](#schemaroundinfo)|false|none|Round信息|
|underlying_asset_id|string|false|none|标的资产：USDT or BTC or ETH|
|underlying_price|string|false|none|标的价格(报价)|
|updated_at|string|false|none|none|

<h2 id="tocS_OrderReq">OrderReq</h2>

<a id="schemaorderreq"></a>
<a id="schema_OrderReq"></a>
<a id="tocSorderreq"></a>
<a id="tocsorderreq"></a>

```json
{
  "order_amount": "string",
  "proxy_info": {
    "manufacturer": "string",
    "mixin_user_id": "string"
  },
  "rid": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|order_amount|string|true|none|购买额|
|proxy_info|[ProxyInfo](#schemaproxyinfo)|false|none|订单提交支持 1. 用户自提交(default) 2. 第三方代理提交|
|rid|string|true|none|Round ID|

<h2 id="tocS_OrderResp">OrderResp</h2>

<a id="schemaorderresp"></a>
<a id="schema_OrderResp"></a>
<a id="tocSorderresp"></a>
<a id="tocsorderresp"></a>

```json
{
  "mixin_pay_url": "string",
  "mixin_transfer_trace_id": "string",
  "oid": "string",
  "order_amount": "string",
  "rid": "string",
  "status": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mixin_pay_url|string|false|none|转账状态|
|mixin_transfer_trace_id|string|false|none|本次订单trace_id|
|oid|string|true|none|none|
|order_amount|string|true|none|购买额|
|rid|string|true|none|Round ID|
|status|string|false|none|转账状态|

<h2 id="tocS_ProxyInfo">ProxyInfo</h2>

<a id="schemaproxyinfo"></a>
<a id="schema_ProxyInfo"></a>
<a id="tocSproxyinfo"></a>
<a id="tocsproxyinfo"></a>

```json
{
  "manufacturer": "string",
  "mixin_user_id": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|manufacturer|string|false|none|第三方服务名称|
|mixin_user_id|string|true|none|被代理提交的用户mixin ID|

<h2 id="tocS_Pagination">Pagination</h2>

<a id="schemapagination"></a>
<a id="schema_Pagination"></a>
<a id="tocSpagination"></a>
<a id="tocspagination"></a>

```json
{
  "current": 0,
  "size": 0,
  "total": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|current|integer|false|none|none|
|size|integer|false|none|none|
|total|integer|false|none|none|

<h2 id="tocS_RoundInfo">RoundInfo</h2>

<a id="schemaroundinfo"></a>
<a id="schema_RoundInfo"></a>
<a id="tocSroundinfo"></a>
<a id="tocsroundinfo"></a>

```json
{
  "apy_max": "string",
  "apy_min": "string",
  "clearing_asset_id": "string",
  "clearing_at": "string",
  "created_at": "string",
  "exercised": true,
  "expiry": "string",
  "funding_asset_id": "string",
  "hide": true,
  "insurance_enable": true,
  "max_fund": "string",
  "min_fund": "string",
  "rid": "string",
  "status": "string",
  "strike": "string",
  "updated_at": "string",
  "vault_type": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|apy_max|string|false|none|最大年化收益率|
|apy_min|string|false|none|最小年化收益率|
|clearing_asset_id|string|false|none|结算货币：USDT or BTC or ETH|
|clearing_at|string|false|none|结算时间|
|created_at|string|false|none|募资开始时间|
|exercised|boolean|false|none|行权状态|
|expiry|string|false|none|(C端显示)到期时间|
|funding_asset_id|string|false|none|募资货币：USDT or BTC or ETH|
|hide|boolean|false|none|可见状态(是否隐藏该round)|
|insurance_enable|boolean|false|none|是否开启保险赔付|
|max_fund|string|false|none|最高募资金额|
|min_fund|string|false|none|最低募资金额|
|rid|string|false|none|round id|
|status|string|false|none|项目状态|
|strike|string|false|none|(C端显示)执行价格|
|updated_at|string|false|none|none|
|vault_type|string|false|none|Round类型|

<h2 id="tocS_commonResponse">commonResponse</h2>

<a id="schemacommonresponse"></a>
<a id="schema_commonResponse"></a>
<a id="tocScommonresponse"></a>
<a id="tocscommonresponse"></a>

```json
{
  "code": 0,
  "data": null,
  "msg": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer|false|none|none|
|data|any|false|none|none|
|msg|string|false|none|none|

<h2 id="tocS_RoundInfoWithInsurance">RoundInfoWithInsurance</h2>

<a id="schemaroundinfowithinsurance"></a>
<a id="schema_RoundInfoWithInsurance"></a>
<a id="tocSroundinfowithinsurance"></a>
<a id="tocsroundinfowithinsurance"></a>

```json
{
  "insurances": [
    {
      "compensation_amount": "string",
      "compensation_asset_id": "string",
      "compensation_price": "string",
      "description": "string",
      "exercised": true,
      "id": 0,
      "label": "string",
      "type": "string"
    }
  ],
  "round_info": {
    "apy_max": "string",
    "apy_min": "string",
    "clearing_asset_id": "string",
    "clearing_at": "string",
    "created_at": "string",
    "exercised": true,
    "expiry": "string",
    "funding_asset_id": "string",
    "hide": true,
    "insurance_enable": true,
    "max_fund": "string",
    "min_fund": "string",
    "rid": "string",
    "status": "string",
    "strike": "string",
    "updated_at": "string",
    "vault_type": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|insurances|[[Insurance](#schemainsurance)]|false|none|none|
|round_info|[RoundInfo](#schemaroundinfo)|false|none|none|

