---
title: API Reference
language_tabs: # must be one of https://git.io/vQNgJ
  - shell: curl
  - http: HTTP
  - javascript: JS
  - javascript--nodejs: Node
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go

toc_footers:
  - <div class="header-soc-icons"><ul class="soc-icons"><li><a href="https://www.facebook.com/geniuslink" class="soc-icon"><i class="fab fa-facebook-f"></i></a></li><li><a href="https://www.instagram.com/geniuslink/" class="soc-icon"><i class="fab fa-instagram"></i></a></li><li><a href="https://twitter.com/geniuslink" class="soc-icon"><i class="fab fa-twitter"></i></a></li><li><a href="https://www.geni.us/" class="soc-icon"><i class="fas fa-globe-americas"></i></a></li></ul></div>
  - <a href='https://kb.geni.us/geniusapi'>Visit our Knowledge Base</a>
  - <a href='mailto:help@geni.us'>Questions? Contact us</a>

includes:
  - errors

search: true
highlight_theme: darkula
---

# Introduction
In order to make API requests, the following headers need to be provided:<br />
<code>X-Api-Key</code><br />
<code>X-Api-Secret</code>


[Optional] Pass your sub-account username as the <code>X-Impersonate</code> header value to make requests as the sub-account.<br />
<a href="">(What's a sub-account?)</a>


We support and highly recommend using the URL scheme 'https' for all requests.<br />
For more information, visit <a href="https://kb.geni.us/geniusapi">our Knowledge Base</a>.

####[WARNING] v1 and v2 will deprecated by the beginning of 2019

# Authentication

* API Key (X-Api-Secret)
    - Parameter Name: **X-Api-Secret**, in: header. 

* API Key (X-Api-Key)
    - Parameter Name: **X-Api-Key**, in: header. 

# Tracking Pixels

## Add a tracking pixel

> Code samples

```shell
# You can also use wget
curl -X POST https://stage-api.geni.us/v3/tracking-pixels \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
POST https://stage-api.geni.us/v3/tracking-pixels HTTP/1.1
Host: stage-api.geni.us
Content-Type: application/json
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/tracking-pixels',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "name": "string",
  "javaScript": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/tracking-pixels',
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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.post 'https://stage-api.geni.us/v3/tracking-pixels',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.post('https://stage-api.geni.us/v3/tracking-pixels', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/tracking-pixels");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://stage-api.geni.us/v3/tracking-pixels", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /v3/tracking-pixels`

*Add a tracking pixel to your account*

While you may add any type of pixel, only [supported pixels](https://kb.geni.us/pixels) may be used with geni.us domain.<br />
                                        <b>Note that you must provide the tracker code in the request payload.</b><br />
                                        <b>Successful request returns 200 with new tracking pixel details.</b>

> Body parameter

```json
{
  "name": "string",
  "javaScript": "string"
}
```

<h3 id="addtrackingpixelrequesttracking-pixels_post-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|name|query|string|false|Pixel name must be unique per account|
|body|body|[AddTrackingPixelRequest](#schemaaddtrackingpixelrequest)|false|<b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
|
|Accept|header|string|true|Accept Header|

#### Detailed descriptions

**body**: <b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
                                          <b>+</b> Don't forget to <i>escape</i> double quotes (\")

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "trackingPixel": {
    "typeString": "string",
    "displayName": "string",
    "renderAs": "string",
    "id": "string",
    "js": "string",
    "name": "string",
    "type": "string",
    "url": "string",
    "metadata": {
      "username": "string",
      "disabled": true,
      "updatedUtc": "2018-10-02T04:10:23Z",
      "createdUtc": "2018-10-02T04:10:23Z"
    },
    "params": {
      "property1": {},
      "property2": {}
    }
  }
}
```

<h3 id="addtrackingpixelrequesttracking-pixels_post-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[AddTrackingPixelResponse](#schemaaddtrackingpixelresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|You must provide X-Api-Key and X-Api-Secret headers, and have tracking pixel feature added to your account; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## GetSubAccountsRequestsub-accounts_Get

<a id="opIdGetSubAccountsRequestsub-accounts_Get"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://stage-api.geni.us/v3/sub-accounts \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
GET https://stage-api.geni.us/v3/sub-accounts HTTP/1.1
Host: stage-api.geni.us
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/sub-accounts',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/sub-accounts',
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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.get 'https://stage-api.geni.us/v3/sub-accounts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.get('https://stage-api.geni.us/v3/sub-accounts', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/sub-accounts");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://stage-api.geni.us/v3/sub-accounts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /v3/sub-accounts`

*Retrieve list of sub-account usernames*

Retrieve usernames of all sub-accounts under your account.<br />
                                        Only primary account can retrieve sub-accounts information. A sub-account isn't allowed to manage, add, or delete its siblings.<br />
                                        <b>Successful request returns 200 and a list of sub-account usernames.</b><br />

<h3 id="getsubaccountsrequestsub-accounts_get-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|Accept|header|string|true|Accept Header|

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "subAccounts": [
    "string"
  ]
}
```

<h3 id="getsubaccountsrequestsub-accounts_get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[GetSubAccountsResponse](#schemagetsubaccountsresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|You must provide X-Api-Key and X-Api-Secret headers, and have team account feature added to your account; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## AddSubAccountRequestsub-accounts_Post

<a id="opIdAddSubAccountRequestsub-accounts_Post"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://stage-api.geni.us/v3/sub-accounts \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
POST https://stage-api.geni.us/v3/sub-accounts HTTP/1.1
Host: stage-api.geni.us
Content-Type: application/json
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/sub-accounts',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "username": "string",
  "password": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/sub-accounts',
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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.post 'https://stage-api.geni.us/v3/sub-accounts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.post('https://stage-api.geni.us/v3/sub-accounts', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/sub-accounts");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://stage-api.geni.us/v3/sub-accounts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /v3/sub-accounts`

*Add a sub-account under your account*

Adds a sub-account under your account, and you will be invoiced per sub-account added--refer to [our pricing page](https://www.geni.us/pricing/).<br />
                                        Only primary account can add a sub-account. A sub-account isn't allowed to manage, add, or delete its siblings.<br />
                                        Note that the primary account is responsible for all billing/invoicing-related matters.<br />
                                        <b>Successful request returns 200 and registration confirmation email will be sent.</b><br />
                                        [Contact us](mailto:help@geni.us) if confirmation email is not delivered.

> Body parameter

```json
{
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "username": "string",
  "password": "string"
}
```

<h3 id="addsubaccountrequestsub-accounts_post-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|firstName|query|string|false|First name for sub-account|
|lastName|query|string|false|Last name for sub-account|
|email|query|string|false|Sub-account email; must be in valid format|
|username|query|string|false|Sub-account username; must be between 3-16 characters in length, only contain numbers and letters, and start with a letter|
|password|query|string|false|Sub-account password; must be between 6-1024 characters in length|
|body|body|[AddSubAccountRequest](#schemaaddsubaccountrequest)|false|<b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
|
|Accept|header|string|true|Accept Header|

#### Detailed descriptions

**body**: <b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
                                          <b>+</b> Don't forget to <i>escape</i> double quotes (\")

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "confirmationEmailSent": true
}
```

<h3 id="addsubaccountrequestsub-accounts_post-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[AddSubAccountResponse](#schemaaddsubaccountresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|You must provide X-Api-Key and X-Api-Secret headers, and have team account feature added to your account; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## AddSupportedDomainRequestcustom-domains_Post

<a id="opIdAddSupportedDomainRequestcustom-domains_Post"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://stage-api.geni.us/v3/custom-domains \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
POST https://stage-api.geni.us/v3/custom-domains HTTP/1.1
Host: stage-api.geni.us
Content-Type: application/json
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/custom-domains',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "domain": "string",
  "aliasOf": "string",
  "autoGrantChildAccess": true,
  "rootRedirectUrl": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/custom-domains',
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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.post 'https://stage-api.geni.us/v3/custom-domains',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.post('https://stage-api.geni.us/v3/custom-domains', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/custom-domains");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://stage-api.geni.us/v3/custom-domains", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /v3/custom-domains`

*Add a new custom domain to your account*

Adds a new custom domain to your account, and you will be invoiced for this domain--refer to [our pricing page](https://www.geni.us/pricing/).<br />
                                        Note that you need to grant your account access to this domain before you can start using it, or you can grant access to another account at no additional cost.<br />
                                        You can configure SSL and DNS as desired using another endpoint.<br />
                                        <b>Successful request returns 200 with new domain details.</b>

> Body parameter

```json
{
  "domain": "string",
  "aliasOf": "string",
  "autoGrantChildAccess": true,
  "rootRedirectUrl": "string"
}
```

<h3 id="addsupporteddomainrequestcustom-domains_post-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|domain|query|string|false|Desired domain name, e.g.: sample.com|
|aliasOf|query|string|false|If the domain is an alias of another domain, input the other domain|
|autoGrantChildAccess|query|boolean|false|Default is false. Set to true to grant child accounts access to this domain|
|rootRedirectUrl|query|string|false|Where you want the base address to go to|
|body|body|[AddSupportedDomainRequest](#schemaaddsupporteddomainrequest)|false|<b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
|
|Accept|header|string|true|Accept Header|

#### Detailed descriptions

**body**: <b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
                                          <b>+</b> Don't forget to <i>escape</i> double quotes (\")

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "domain": {
    "name": "string",
    "subjectAlternativeNames": [
      "string"
    ],
    "owner": "string",
    "usersAllowedAccess": [
      "string"
    ],
    "allowedDestinationDomains": [
      "string"
    ],
    "letsencrypt": true,
    "letsencryptMethod": "string",
    "dnsProvider": "string",
    "dnsimpleUserName": "string",
    "aliasOf": "string",
    "startDateUtc": "2018-10-02T04:10:23Z",
    "endDateUtc": "2018-10-02T04:10:23Z",
    "rootRedirectUrl": "string",
    "automaticallyGrantChildAccountAccess": true
  }
}
```

<h3 id="addsupporteddomainrequestcustom-domains_post-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[SupportedDomainResponse](#schemasupporteddomainresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|You must provide X-Api-Key and X-Api-Secret headers, and have custom domain feature added to your account; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## GetTrackingPixelByIdRequesttracking-pixelsid_Get

<a id="opIdGetTrackingPixelByIdRequesttracking-pixelsid_Get"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://stage-api.geni.us/v3/tracking-pixels/{id} \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
GET https://stage-api.geni.us/v3/tracking-pixels/{id} HTTP/1.1
Host: stage-api.geni.us
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/tracking-pixels/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/tracking-pixels/{id}',
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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.get 'https://stage-api.geni.us/v3/tracking-pixels/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.get('https://stage-api.geni.us/v3/tracking-pixels/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/tracking-pixels/{id}");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://stage-api.geni.us/v3/tracking-pixels/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /v3/tracking-pixels/{id}`

*Get details of a tracking pixel under your account*

To retrieve details of a tracking pixel, <b>you must provide the pixel ID</b>.<br />
                                        <b>Successful request returns 200 with specified tracking pixel details.</b>

<h3 id="gettrackingpixelbyidrequesttracking-pixelsid_get-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|ID of pixel to retrieve|
|Accept|header|string|true|Accept Header|

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "trackingPixel": {
    "typeString": "string",
    "displayName": "string",
    "renderAs": "string",
    "id": "string",
    "js": "string",
    "name": "string",
    "type": "string",
    "url": "string",
    "metadata": {
      "username": "string",
      "disabled": true,
      "updatedUtc": "2018-10-02T04:10:23Z",
      "createdUtc": "2018-10-02T04:10:23Z"
    },
    "params": {
      "property1": {},
      "property2": {}
    }
  }
}
```

<h3 id="gettrackingpixelbyidrequesttracking-pixelsid_get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[GetTrackingPixelResponse](#schemagettrackingpixelresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Feature missing or authorization failure; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## DeleteTrackingPixelRequesttracking-pixelsid_Delete

<a id="opIdDeleteTrackingPixelRequesttracking-pixelsid_Delete"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://stage-api.geni.us/v3/tracking-pixels/{id} \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
DELETE https://stage-api.geni.us/v3/tracking-pixels/{id} HTTP/1.1
Host: stage-api.geni.us
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/tracking-pixels/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/tracking-pixels/{id}',
{
  method: 'DELETE',

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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.delete 'https://stage-api.geni.us/v3/tracking-pixels/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.delete('https://stage-api.geni.us/v3/tracking-pixels/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/tracking-pixels/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://stage-api.geni.us/v3/tracking-pixels/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /v3/tracking-pixels/{id}`

*Delete a tracking pixel under your account*

Pixel ID consists of 24 hexadecimal digits and is required to delete a specific tracking pixel.<br />
                                        <b>Successful request returns 200 with state of deletion.</b>

<h3 id="deletetrackingpixelrequesttracking-pixelsid_delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|ID of pixel to delete. ID consists of 24 hexadecimal digits and must be provided|
|Accept|header|string|true|Accept Header|

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

<h3 id="deletetrackingpixelrequesttracking-pixelsid_delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[DeleteTrackingPixelResponse](#schemadeletetrackingpixelresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Feature missing or authorization failure; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## UpdateTrackingPixelRequesttracking-pixelsid_Update

<a id="opIdUpdateTrackingPixelRequesttracking-pixelsid_Update"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://stage-api.geni.us/v3/tracking-pixels/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
PATCH https://stage-api.geni.us/v3/tracking-pixels/{id} HTTP/1.1
Host: stage-api.geni.us
Content-Type: application/json
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/tracking-pixels/{id}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "javaScript": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/tracking-pixels/{id}',
{
  method: 'PATCH',
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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.patch 'https://stage-api.geni.us/v3/tracking-pixels/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.patch('https://stage-api.geni.us/v3/tracking-pixels/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/tracking-pixels/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://stage-api.geni.us/v3/tracking-pixels/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /v3/tracking-pixels/{id}`

*Update a tracking pixel under your account*

To update a tracking pixel, you must provide the pixel ID.<br />
                                        Pixel ID consists of 24 hexadecimal digits, and it is unique and permanent (non-editable).<br />
                                        You  may only edit the pixel name and tracker code.<br />
                                        While you may add any type of pixel, only [supported pixels](https://kb.geni.us/pixels) may be used with geni.us domain.<br />
                                        <b>Note that to edit the tracker code, you must provide the code in the request payload.</b><br />
                                        <b>Successful request returns 200 with updated tracking pixel details.</b>

> Body parameter

```json
{
  "javaScript": "string"
}
```

<h3 id="updatetrackingpixelrequesttracking-pixelsid_update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|ID of pixel to edit. ID consists of 24 hexadecimal digits and must be provided|
|name|query|string|false|What to change the pixel name to; ignored if empty|
|body|body|[UpdateTrackingPixelRequest](#schemaupdatetrackingpixelrequest)|false|<b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
|
|Accept|header|string|true|Accept Header|

#### Detailed descriptions

**body**: <b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
                                          <b>+</b> Don't forget to <i>escape</i> double quotes (\")

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "trackingPixel": {
    "typeString": "string",
    "displayName": "string",
    "renderAs": "string",
    "id": "string",
    "js": "string",
    "name": "string",
    "type": "string",
    "url": "string",
    "metadata": {
      "username": "string",
      "disabled": true,
      "updatedUtc": "2018-10-02T04:10:23Z",
      "createdUtc": "2018-10-02T04:10:23Z"
    },
    "params": {
      "property1": {},
      "property2": {}
    }
  }
}
```

<h3 id="updatetrackingpixelrequesttracking-pixelsid_update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[UpdateTrackingPixelResponse](#schemaupdatetrackingpixelresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Feature missing or authorization failure; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## AddApiKeyRequestteamapi-keys_Post

<a id="opIdAddApiKeyRequestteamapi-keys_Post"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://stage-api.geni.us/v3/team/api-keys \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
POST https://stage-api.geni.us/v3/team/api-keys HTTP/1.1
Host: stage-api.geni.us
Content-Type: application/json
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/team/api-keys',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "apiNotes": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/team/api-keys',
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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.post 'https://stage-api.geni.us/v3/team/api-keys',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.post('https://stage-api.geni.us/v3/team/api-keys', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/team/api-keys");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://stage-api.geni.us/v3/team/api-keys", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /v3/team/api-keys`

*Generate a new pair of API key and secret*

Once generated, you can retrieve your API keys from [your tools page](https://my.geni.us/tools).<br />
                                        <b>Successful request returns 200 with newly-generated API key and secret pair.</b>

> Body parameter

```json
{
  "apiNotes": "string"
}
```

<h3 id="addapikeyrequestteamapi-keys_post-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|apiNotes|query|string|false|(Optional) Short description of the API key, must be 32 characters or less|
|body|body|[AddApiKeyRequest](#schemaaddapikeyrequest)|false|<b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
|
|Accept|header|string|true|Accept Header|

#### Detailed descriptions

**body**: <b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
                                          <b>+</b> Don't forget to <i>escape</i> double quotes (\")

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "apiKey": {
    "userName": "string",
    "secret": "string",
    "key": "string",
    "notes": "string",
    "id": "string"
  }
}
```

<h3 id="addapikeyrequestteamapi-keys_post-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[AddApiKeyResponse](#schemaaddapikeyresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Feature missing or authorization failure; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## ReplaceSupportedDomainRequestcustom-domainsdomain_Create

<a id="opIdReplaceSupportedDomainRequestcustom-domainsdomain_Create"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://stage-api.geni.us/v3/custom-domains/{domain} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
PUT https://stage-api.geni.us/v3/custom-domains/{domain} HTTP/1.1
Host: stage-api.geni.us
Content-Type: application/json
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/custom-domains/{domain}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "aliasOf": "string",
  "autoGrantChildAccess": true,
  "rootRedirectUrl": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/custom-domains/{domain}',
{
  method: 'PUT',
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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.put 'https://stage-api.geni.us/v3/custom-domains/{domain}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.put('https://stage-api.geni.us/v3/custom-domains/{domain}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/custom-domains/{domain}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://stage-api.geni.us/v3/custom-domains/{domain}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /v3/custom-domains/{domain}`

*Replace existing custom domain details belonging to user*

Replace an existing domain. Note that this endpoint will <b>replace, not edit</b> domain details.<br />
                                        This means that if you leave a field empty, the field value will be deleted if it was previously filled.<br />
                                        If you need to update specific fields, we recommend using the PATCH operation which will edit (instead of replace) your domain details.<br />
                                        Note that you cannot replace your domain name. If you wish to do so, please <a href="mailto:help@geni.us">contact us</a> for assistance.<br />
                                        <b>Successful request returns 200 with new domain details.</b>

> Body parameter

```json
{
  "aliasOf": "string",
  "autoGrantChildAccess": true,
  "rootRedirectUrl": "string"
}
```

<h3 id="replacesupporteddomainrequestcustom-domainsdomain_create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|domain|path|string|true|Domain to replace details of; must be provided|
|aliasOf|query|string|false|If the domain is an alias of another domain, input the other domain<br />If empty, previous value will be deleted|
|autoGrantChildAccess|query|boolean|false|Set to true to automatically grant child accounts access to this domain<br />If empty, previous value will be replaced by the default value 'false'|
|rootRedirectUrl|query|string|false|Where you want the base address to go to<br />If empty, previous value will be deleted|
|body|body|[ReplaceSupportedDomainRequest](#schemareplacesupporteddomainrequest)|false|<b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
|
|Accept|header|string|true|Accept Header|

#### Detailed descriptions

**body**: <b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
                                          <b>+</b> Don't forget to <i>escape</i> double quotes (\")

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "domain": {
    "name": "string",
    "subjectAlternativeNames": [
      "string"
    ],
    "owner": "string",
    "usersAllowedAccess": [
      "string"
    ],
    "allowedDestinationDomains": [
      "string"
    ],
    "letsencrypt": true,
    "letsencryptMethod": "string",
    "dnsProvider": "string",
    "dnsimpleUserName": "string",
    "aliasOf": "string",
    "startDateUtc": "2018-10-02T04:10:23Z",
    "endDateUtc": "2018-10-02T04:10:23Z",
    "rootRedirectUrl": "string",
    "automaticallyGrantChildAccountAccess": true
  }
}
```

<h3 id="replacesupporteddomainrequestcustom-domainsdomain_create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[SupportedDomainResponse](#schemasupporteddomainresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Feature missing or authorization failure; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## UpdateSupportedDomainRequestcustom-domainsdomain_Update

<a id="opIdUpdateSupportedDomainRequestcustom-domainsdomain_Update"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://stage-api.geni.us/v3/custom-domains/{domain} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
PATCH https://stage-api.geni.us/v3/custom-domains/{domain} HTTP/1.1
Host: stage-api.geni.us
Content-Type: application/json
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/custom-domains/{domain}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "aliasOf": "string",
  "autoGrantChildAccess": true,
  "rootRedirectUrl": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/custom-domains/{domain}',
{
  method: 'PATCH',
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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.patch 'https://stage-api.geni.us/v3/custom-domains/{domain}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.patch('https://stage-api.geni.us/v3/custom-domains/{domain}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/custom-domains/{domain}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://stage-api.geni.us/v3/custom-domains/{domain}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /v3/custom-domains/{domain}`

*Edit existing custom domain belonging to user*

Update an existing domain. Note that this endpoint will <b>edit, not replace</b> domain details.<br />
                                        Empty fields will be ignored, i.e. we will only update fields that you filled.<br />
                                        If you need to delete a field value, we recommend using the PUT operation which will replace (instead of edit) your domain details.<br />
                                        Note that you cannot edit your domain name. If you wish to do so, please <a href="mailto:help@geni.us">contact us</a> for assistance.<br />
                                        <b>Successful request returns 200 with updated domain details.</b>

> Body parameter

```json
{
  "aliasOf": "string",
  "autoGrantChildAccess": true,
  "rootRedirectUrl": "string"
}
```

<h3 id="updatesupporteddomainrequestcustom-domainsdomain_update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|domain|path|string|true|Domain to edit; must be provided as query parameter or in request payload|
|aliasOf|query|string|false|If the domain is an alias of another domain, input the other domain<br/ >Ignored if empty|
|autoGrantChildAccess|query|boolean|false|Set to true to automatically grant child accounts access to this domain<br />Ignored if empty|
|rootRedirectUrl|query|string|false|Where you want the base address to go to<br />Ignored if empty|
|body|body|[UpdateSupportedDomainRequest](#schemaupdatesupporteddomainrequest)|false|<b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
|
|Accept|header|string|true|Accept Header|

#### Detailed descriptions

**body**: <b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
                                          <b>+</b> Don't forget to <i>escape</i> double quotes (\")

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "domain": {
    "name": "string",
    "subjectAlternativeNames": [
      "string"
    ],
    "owner": "string",
    "usersAllowedAccess": [
      "string"
    ],
    "allowedDestinationDomains": [
      "string"
    ],
    "letsencrypt": true,
    "letsencryptMethod": "string",
    "dnsProvider": "string",
    "dnsimpleUserName": "string",
    "aliasOf": "string",
    "startDateUtc": "2018-10-02T04:10:23Z",
    "endDateUtc": "2018-10-02T04:10:23Z",
    "rootRedirectUrl": "string",
    "automaticallyGrantChildAccountAccess": true
  }
}
```

<h3 id="updatesupporteddomainrequestcustom-domainsdomain_update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[SupportedDomainResponse](#schemasupporteddomainresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Feature missing or authorization failure; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## DeleteApiKeyRequestteamapi-keysapiKey_Delete

<a id="opIdDeleteApiKeyRequestteamapi-keysapiKey_Delete"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://stage-api.geni.us/v3/team/api-keys/{apiKey} \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
DELETE https://stage-api.geni.us/v3/team/api-keys/{apiKey} HTTP/1.1
Host: stage-api.geni.us
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/team/api-keys/{apiKey}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/team/api-keys/{apiKey}',
{
  method: 'DELETE',

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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.delete 'https://stage-api.geni.us/v3/team/api-keys/{apiKey}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.delete('https://stage-api.geni.us/v3/team/api-keys/{apiKey}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/team/api-keys/{apiKey}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://stage-api.geni.us/v3/team/api-keys/{apiKey}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /v3/team/api-keys/{apiKey}`

*Delete an API key and secret pair from your account*

To delete an API key and secret pair, you must provide the key.<br />
                                        Note that the API key and secret currently used for authorization cannot be deleted.<br />
                                        <b>Successful request returns 200 with state of deletion.</b>

<h3 id="deleteapikeyrequestteamapi-keysapikey_delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|apiKey|path|string|true|API key you wish to delete from your account|
|Accept|header|string|true|Accept Header|

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

<h3 id="deleteapikeyrequestteamapi-keysapikey_delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[DeleteApiKeyResponse](#schemadeleteapikeyresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Feature missing or authorization failure; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## GetDomainAllowedUsersRequestcustom-domainsdomainusers_Get

<a id="opIdGetDomainAllowedUsersRequestcustom-domainsdomainusers_Get"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://stage-api.geni.us/v3/custom-domains/{domain}/users \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
GET https://stage-api.geni.us/v3/custom-domains/{domain}/users HTTP/1.1
Host: stage-api.geni.us
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/custom-domains/{domain}/users',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/custom-domains/{domain}/users',
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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.get 'https://stage-api.geni.us/v3/custom-domains/{domain}/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.get('https://stage-api.geni.us/v3/custom-domains/{domain}/users', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/custom-domains/{domain}/users");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://stage-api.geni.us/v3/custom-domains/{domain}/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /v3/custom-domains/{domain}/users`

*Get list of users who previously have been granted access to use specified domain*

To get a list of users who previously have been granted permissions to use a certain domain, you must be the owner of specified domain.<br />
                                        <b>Successful request returns 200 with a list of users allowed access.</b>

<h3 id="getdomainallowedusersrequestcustom-domainsdomainusers_get-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|domain|path|string|true|Domain to get users allowed access from|
|Accept|header|string|true|Accept Header|

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "usersAllowedAccess": [
    "string"
  ]
}
```

<h3 id="getdomainallowedusersrequestcustom-domainsdomainusers_get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[DomainAllowedUsersResponse](#schemadomainallowedusersresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Feature missing or authorization failure; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## AddDomainAllowedUserRequestcustom-domainsdomainusers_Post

<a id="opIdAddDomainAllowedUserRequestcustom-domainsdomainusers_Post"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://stage-api.geni.us/v3/custom-domains/{domain}/users \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
POST https://stage-api.geni.us/v3/custom-domains/{domain}/users HTTP/1.1
Host: stage-api.geni.us
Content-Type: application/json
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/custom-domains/{domain}/users',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "username": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/custom-domains/{domain}/users',
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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.post 'https://stage-api.geni.us/v3/custom-domains/{domain}/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.post('https://stage-api.geni.us/v3/custom-domains/{domain}/users', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/custom-domains/{domain}/users");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://stage-api.geni.us/v3/custom-domains/{domain}/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /v3/custom-domains/{domain}/users`

*Grant specified user access to use your custom domain*

If you currently manage multiple accounts/sub-accounts, you can grant specified user access to use your custom domain.<br />
                                      Note that you aren't automatically granted access to use your domain after you add a new domain; you must grant yourself access to use your domain to create links.<br />
                                      To grant user access to a domain, you must be the owner of the domain.<br />
                                      <b>Successful request returns 200 with a new list of users with access</b>.

> Body parameter

```json
{
  "username": "string"
}
```

<h3 id="adddomainalloweduserrequestcustom-domainsdomainusers_post-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|domain|path|string|true|Domain name you wish to grant a specific user access to|
|username|query|string|false|User to grant access to. Input your username if you want to grant yourself access|
|body|body|[AddDomainAllowedUserRequest](#schemaadddomainalloweduserrequest)|false|<b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
|
|Accept|header|string|true|Accept Header|

#### Detailed descriptions

**body**: <b>+</b> If you wish to use query parameters only (and the request doesn't require specific payload), you may leave this field empty<br />
                                          <b>+</b> Don't forget to <i>escape</i> double quotes (\")

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "usersAllowedAccess": [
    "string"
  ]
}
```

<h3 id="adddomainalloweduserrequestcustom-domainsdomainusers_post-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[DomainAllowedUsersResponse](#schemadomainallowedusersresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Feature missing or authorization failure; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

## DeleteDomainAllowedUserRequestcustom-domainsdomainusersusername_Delete

<a id="opIdDeleteDomainAllowedUserRequestcustom-domainsdomainusersusername_Delete"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://stage-api.geni.us/v3/custom-domains/{domain}/users/{username} \
  -H 'Accept: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY' \
  -H 'X-Api-Secret: API_KEY'

```

```http
DELETE https://stage-api.geni.us/v3/custom-domains/{domain}/users/{username} HTTP/1.1
Host: stage-api.geni.us
Accept: application/json
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

$.ajax({
  url: 'https://stage-api.geni.us/v3/custom-domains/{domain}/users/{username}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY',
  'X-Api-Secret':'API_KEY'

};

fetch('https://stage-api.geni.us/v3/custom-domains/{domain}/users/{username}',
{
  method: 'DELETE',

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
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY',
  'X-Api-Secret' => 'API_KEY'
}

result = RestClient.delete 'https://stage-api.geni.us/v3/custom-domains/{domain}/users/{username}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY',
  'X-Api-Secret': 'API_KEY'
}

r = requests.delete('https://stage-api.geni.us/v3/custom-domains/{domain}/users/{username}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://stage-api.geni.us/v3/custom-domains/{domain}/users/{username}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        "X-Api-Secret": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://stage-api.geni.us/v3/custom-domains/{domain}/users/{username}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /v3/custom-domains/{domain}/users/{username}`

*Revoke permission to use your domain from a specified user*

If you currently manage multiple accounts/sub-accounts, you can deny a user access to use your domain if you're the owner of the specified domain.<br />
                                        If you're the owner of the domain and deny yourself access, you'll still be invoiced for the domain, but you can no longer create links with it.<br />
                                        <b>Successful request returns 200 with a new list of users with access.</b>

<h3 id="deletedomainalloweduserrequestcustom-domainsdomainusersusername_delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|domain|path|string|true|Domain name you wish to revoke a specific user access from|
|username|path|string|true|User to revoke access from. Input your username if you want to deny yourself access|
|Accept|header|string|true|Accept Header|

#### Enumerated Values

|Parameter|Value|
|---|---|
|Accept|application/json|

> Example responses

> 200 Response

```json
{
  "usersAllowedAccess": [
    "string"
  ]
}
```

<h3 id="deletedomainalloweduserrequestcustom-domainsdomainusersusername_delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[DomainAllowedUsersResponse](#schemadomainallowedusersresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid or missing argument|[GenericErrorResponse](#schemagenericerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Feature missing or authorization failure; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Feature missing, feature limit exceeded, or user role mismatch; [contact us](mailto:help@geni.us) for assistance|[GenericErrorResponse](#schemagenericerrorresponse)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Server unexpectedly closed connection; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Error occurred on the server; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Bad response received, not returned; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service temporarily down; please try again later and check [status.geni.us](http://status.geni.us/) for updates|[ServiceUnavailable503ResponseAttribute](#schemaserviceunavailable503responseattribute)|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Server timed out; please try again|[GenericErrorResponse](#schemagenericerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
X-Api-Key & X-Api-Secret & X-Impersonate
</aside>

# Schemas

<h2 id="tocSobject">Object</h2>

<a id="schemaobject"></a>

```json
{}

```

*Object*

### Properties

*None*

<h2 id="tocSremoveaffiliateparameterrequest">RemoveAffiliateParameterRequest</h2>

<a id="schemaremoveaffiliateparameterrequest"></a>

```json
{
  "affiliateNetworkName": "string"
}

```

*RemoveAffiliateParameterRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|affiliateNetworkName|string|false|none|none|

<h2 id="tocSaffiliateparameterinforequest">AffiliateParameterInfoRequest</h2>

<a id="schemaaffiliateparameterinforequest"></a>

```json
{}

```

*AffiliateParameterInfoRequest*

### Properties

*None*

<h2 id="tocSremovegroupaffiliateparameterrequest">RemoveGroupAffiliateParameterRequest</h2>

<a id="schemaremovegroupaffiliateparameterrequest"></a>

```json
{
  "tsid": 0,
  "affiliateNetworkName": "string"
}

```

*RemoveGroupAffiliateParameterRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tsid|integer(int32)|false|none|none|
|affiliateNetworkName|string|false|none|none|

<h2 id="tocSaffiliategroupparameterinforequest">AffiliateGroupParameterInfoRequest</h2>

<a id="schemaaffiliategroupparameterinforequest"></a>

```json
{
  "tsid": 0
}

```

*AffiliateGroupParameterInfoRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tsid|integer(int32)|false|none|none|

<h2 id="tocSaddorupdategroupaffiliateparameterrequest">AddOrUpdateGroupAffiliateParameterRequest</h2>

<a id="schemaaddorupdategroupaffiliateparameterrequest"></a>

```json
{
  "affiliateNetworkName": "string",
  "tsid": 0,
  "parameters": [
    {
      "parameter": "string",
      "value": "string"
    }
  ]
}

```

*AddOrUpdateGroupAffiliateParameterRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|affiliateNetworkName|string|false|none|none|
|tsid|integer(int32)|false|none|none|
|parameters|[[ParameterAndValue](#schemaparameterandvalue)]|false|none|[ParameterAndValue]|

<h2 id="tocSparameterandvalue">ParameterAndValue</h2>

<a id="schemaparameterandvalue"></a>

```json
{
  "parameter": "string",
  "value": "string"
}

```

*ParameterAndValue*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parameter|string|false|none|none|
|value|string|false|none|none|

<h2 id="tocSaddorupdateaffiliateparameterrequest">AddOrUpdateAffiliateParameterRequest</h2>

<a id="schemaaddorupdateaffiliateparameterrequest"></a>

```json
{
  "affiliateNetworkName": "string",
  "parameters": [
    {
      "parameter": "string",
      "value": "string"
    }
  ]
}

```

*AddOrUpdateAffiliateParameterRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|affiliateNetworkName|string|false|none|none|
|parameters|[[ParameterAndValue](#schemaparameterandvalue)]|false|none|[ParameterAndValue]|

<h2 id="tocSusersummaryrequest">UserSummaryRequest</h2>

<a id="schemausersummaryrequest"></a>

```json
{
  "reportName": "string",
  "advertiserType": "string",
  "end": "2018-10-02T04:10:23Z",
  "start": "2018-10-02T04:10:23Z",
  "includeBots": true
}

```

*UserSummaryRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|reportName|string|false|none|none|
|advertiserType|string|false|none|none|
|end|string(date-time)|false|none|none|
|start|string(date-time)|false|none|none|
|includeBots|boolean|false|none|none|

<h2 id="tocSgetallpostprocessingrulesrequest">GetAllPostProcessingRulesRequest</h2>

<a id="schemagetallpostprocessingrulesrequest"></a>

```json
{
  "username": "string",
  "postProcessingRulesCategory": "string"
}

```

*GetAllPostProcessingRulesRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|none|
|postProcessingRulesCategory|string|false|none|none|

<h2 id="tocSgetallutmcompatibledomainsrequest">GetAllUtmCompatibleDomainsRequest</h2>

<a id="schemagetallutmcompatibledomainsrequest"></a>

```json
{
  "username": "string"
}

```

*GetAllUtmCompatibleDomainsRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|none|

<h2 id="tocSnewshorturlrequest">NewShortUrlRequest</h2>

<a id="schemanewshorturlrequest"></a>

```json
{
  "url": "string",
  "groupId": 0,
  "trackingCode": "string",
  "vanityCode": "string",
  "domain": "string",
  "additionalParameters": "string"
}

```

*NewShortUrlRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|url|string|false|none|none|
|groupId|integer(int32)|false|none|none|
|trackingCode|string|false|none|none|
|vanityCode|string|false|none|none|
|domain|string|false|none|none|
|additionalParameters|string|false|none|none|

<h2 id="tocSlinkhealtherrorrequest">LinkHealthErrorRequest</h2>

<a id="schemalinkhealtherrorrequest"></a>

```json
{
  "showHidden": true,
  "excludeArchivedLinks": true,
  "spfInput": {
    "pageSize": 0,
    "desiredPage": 0,
    "pagesBefore": 0,
    "pagesAfter": 0,
    "filterBy": [
      "string"
    ],
    "sortBy": "string",
    "sortReversed": true,
    "keyword": "string"
  }
}

```

*LinkHealthErrorRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|showHidden|boolean|false|none|none|
|excludeArchivedLinks|boolean|false|none|none|
|spfInput|[SpfInput](#schemaspfinput)|false|none|SpfInput|

<h2 id="tocSspfinput">SpfInput</h2>

<a id="schemaspfinput"></a>

```json
{
  "pageSize": 0,
  "desiredPage": 0,
  "pagesBefore": 0,
  "pagesAfter": 0,
  "filterBy": [
    "string"
  ],
  "sortBy": "string",
  "sortReversed": true,
  "keyword": "string"
}

```

*SpfInput*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pageSize|integer(int32)|false|none|none|
|desiredPage|integer(int32)|false|none|none|
|pagesBefore|integer(int32)|false|none|none|
|pagesAfter|integer(int32)|false|none|none|
|filterBy|[string]|false|none|none|
|sortBy|string|false|none|none|
|sortReversed|boolean|false|none|none|
|keyword|string|false|none|none|

<h2 id="tocSlinkhealtherrorhideorshowrequest">LinkHealthErrorHideOrShowRequest</h2>

<a id="schemalinkhealtherrorhideorshowrequest"></a>

```json
{
  "ids": [
    "string"
  ],
  "hide": true
}

```

*LinkHealthErrorHideOrShowRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ids|[string]|false|none|none|
|hide|boolean|false|none|none|

<h2 id="tocSaddorupdatepostprocessingrulesrequest">AddOrUpdatePostProcessingRulesRequest</h2>

<a id="schemaaddorupdatepostprocessingrulesrequest"></a>

```json
{
  "postProcessingLevel": "string",
  "conditions": {
    "property1": [
      "string"
    ],
    "property2": [
      "string"
    ]
  },
  "parameterKeyValues": {
    "property1": "string",
    "property2": "string"
  },
  "shortCodes": [
    "string"
  ],
  "id": "string"
}

```

*AddOrUpdatePostProcessingRulesRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|postProcessingLevel|string|false|none|none|
|conditions|[Dictionary_String_List_String_](#schemadictionary_string_list_string_)|false|none|Dictionary<String,List<String>>|
|parameterKeyValues|[Dictionary_String_String_](#schemadictionary_string_string_)|false|none|Dictionary<String,String>|
|shortCodes|[string]|false|none|none|
|id|string|false|none|none|

<h2 id="tocSdeletepostprocessingrulesrequest">DeletePostProcessingRulesRequest</h2>

<a id="schemadeletepostprocessingrulesrequest"></a>

```json
{
  "postProcessingRulesCategory": "string",
  "shortCodes": [
    "string"
  ],
  "id": "string"
}

```

*DeletePostProcessingRulesRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|postProcessingRulesCategory|string|false|none|none|
|shortCodes|[string]|false|none|none|
|id|string|false|none|none|

<h2 id="tocSgetshortcodepostprocessingrulesrequest">GetShortCodePostProcessingRulesRequest</h2>

<a id="schemagetshortcodepostprocessingrulesrequest"></a>

```json
{
  "shortCodes": [
    "string"
  ],
  "id": "string"
}

```

*GetShortCodePostProcessingRulesRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|shortCodes|[string]|false|none|none|
|id|string|false|none|none|

<h2 id="tocSaddorupdateutmcompatibledomainsrequest">AddOrUpdateUtmCompatibleDomainsRequest</h2>

<a id="schemaaddorupdateutmcompatibledomainsrequest"></a>

```json
{
  "username": "string",
  "level": "string",
  "domains": [
    "string"
  ]
}

```

*AddOrUpdateUtmCompatibleDomainsRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|none|
|level|string|false|none|none|
|domains|[string]|false|none|none|

<h2 id="tocSdeleteutmcompatibledomainsrequest">DeleteUtmCompatibleDomainsRequest</h2>

<a id="schemadeleteutmcompatibledomainsrequest"></a>

```json
{
  "username": "string",
  "level": "string",
  "domains": [
    "string"
  ]
}

```

*DeleteUtmCompatibleDomainsRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|none|
|level|string|false|none|none|
|domains|[string]|false|none|none|

<h2 id="tocSgetutmcompatibledomainsrequest">GetUtmCompatibleDomainsRequest</h2>

<a id="schemagetutmcompatibledomainsrequest"></a>

```json
{
  "username": "string",
  "level": "string",
  "domains": [
    "string"
  ]
}

```

*GetUtmCompatibleDomainsRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|none|
|level|string|false|none|none|
|domains|[string]|false|none|none|

<h2 id="tocSaddtrackingpixelrequest">AddTrackingPixelRequest</h2>

<a id="schemaaddtrackingpixelrequest"></a>

```json
{
  "name": "string",
  "javaScript": "string"
}

```

*AddTrackingPixelRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Pixel name must be unique per account|
|javaScript|string|true|none|none|

<h2 id="tocSaddsubaccountrequest">AddSubAccountRequest</h2>

<a id="schemaaddsubaccountrequest"></a>

```json
{
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "username": "string",
  "password": "string"
}

```

*AddSubAccountRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|firstName|string|false|none|First name for sub-account|
|lastName|string|false|none|Last name for sub-account|
|email|string|false|none|Sub-account email; must be in valid format|
|username|string|false|none|Sub-account username; must be between 3-16 characters in length, only contain numbers and letters, and start with a letter|
|password|string|false|none|Sub-account password; must be between 6-1024 characters in length|

<h2 id="tocSgetsubaccountsrequest">GetSubAccountsRequest</h2>

<a id="schemagetsubaccountsrequest"></a>

```json
{}

```

*GetSubAccountsRequest*

### Properties

*None*

<h2 id="tocSaddsupporteddomainrequest">AddSupportedDomainRequest</h2>

<a id="schemaaddsupporteddomainrequest"></a>

```json
{
  "domain": "string",
  "aliasOf": "string",
  "autoGrantChildAccess": true,
  "rootRedirectUrl": "string"
}

```

*AddSupportedDomainRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|domain|string|false|none|Desired domain name, e.g.: sample.com|
|aliasOf|string|false|none|If the domain is an alias of another domain, input the other domain|
|autoGrantChildAccess|boolean|false|none|Default is false. Set to true to grant child accounts access to this domain|
|rootRedirectUrl|string|false|none|Where you want the base address to go to|

<h2 id="tocSdeletetrackingpixelrequest">DeleteTrackingPixelRequest</h2>

<a id="schemadeletetrackingpixelrequest"></a>

```json
{}

```

*DeleteTrackingPixelRequest*

### Properties

*None*

<h2 id="tocSgettrackingpixelbyidrequest">GetTrackingPixelByIdRequest</h2>

<a id="schemagettrackingpixelbyidrequest"></a>

```json
{}

```

*GetTrackingPixelByIdRequest*

### Properties

*None*

<h2 id="tocSupdatetrackingpixelrequest">UpdateTrackingPixelRequest</h2>

<a id="schemaupdatetrackingpixelrequest"></a>

```json
{
  "javaScript": "string"
}

```

*UpdateTrackingPixelRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|javaScript|string|true|none|none|

<h2 id="tocSaddapikeyrequest">AddApiKeyRequest</h2>

<a id="schemaaddapikeyrequest"></a>

```json
{
  "apiNotes": "string"
}

```

*AddApiKeyRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|apiNotes|string|false|none|(Optional) Short description of the API key, must be 32 characters or less|

<h2 id="tocSreplacesupporteddomainrequest">ReplaceSupportedDomainRequest</h2>

<a id="schemareplacesupporteddomainrequest"></a>

```json
{
  "aliasOf": "string",
  "autoGrantChildAccess": true,
  "rootRedirectUrl": "string"
}

```

*ReplaceSupportedDomainRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|aliasOf|string|false|none|If the domain is an alias of another domain, input the other domain<br />If empty, previous value will be deleted|
|autoGrantChildAccess|boolean|false|none|Set to true to automatically grant child accounts access to this domain<br />If empty, previous value will be replaced by the default value 'false'|
|rootRedirectUrl|string|false|none|Where you want the base address to go to<br />If empty, previous value will be deleted|

<h2 id="tocSupdatesupporteddomainrequest">UpdateSupportedDomainRequest</h2>

<a id="schemaupdatesupporteddomainrequest"></a>

```json
{
  "aliasOf": "string",
  "autoGrantChildAccess": true,
  "rootRedirectUrl": "string"
}

```

*UpdateSupportedDomainRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|aliasOf|string|false|none|If the domain is an alias of another domain, input the other domain<br/ >Ignored if empty|
|autoGrantChildAccess|boolean|false|none|Set to true to automatically grant child accounts access to this domain<br />Ignored if empty|
|rootRedirectUrl|string|false|none|Where you want the base address to go to<br />Ignored if empty|

<h2 id="tocSdeleteapikeyrequest">DeleteApiKeyRequest</h2>

<a id="schemadeleteapikeyrequest"></a>

```json
{}

```

*DeleteApiKeyRequest*

### Properties

*None*

<h2 id="tocSadddomainalloweduserrequest">AddDomainAllowedUserRequest</h2>

<a id="schemaadddomainalloweduserrequest"></a>

```json
{
  "username": "string"
}

```

*AddDomainAllowedUserRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|User to grant access to. Input your username if you want to grant yourself access|

<h2 id="tocSgetdomainallowedusersrequest">GetDomainAllowedUsersRequest</h2>

<a id="schemagetdomainallowedusersrequest"></a>

```json
{}

```

*GetDomainAllowedUsersRequest*

### Properties

*None*

<h2 id="tocSdeletedomainalloweduserrequest">DeleteDomainAllowedUserRequest</h2>

<a id="schemadeletedomainalloweduserrequest"></a>

```json
{}

```

*DeleteDomainAllowedUserRequest*

### Properties

*None*

<h2 id="tocSgroupmetadatarequest">GroupMetadataRequest</h2>

<a id="schemagroupmetadatarequest"></a>

```json
{
  "groups": [
    "string"
  ],
  "startPage": 0,
  "advertiserId": 0,
  "startDate": "2018-10-02T04:10:23Z",
  "endDate": "2018-10-02T04:10:23Z",
  "filters": [
    {
      "type": "string",
      "name": "string",
      "formattedName": "string"
    }
  ]
}

```

*GroupMetadataRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|groups|[string]|false|none|none|
|startPage|integer(int32)|false|none|none|
|advertiserId|integer(int32)|false|none|none|
|startDate|string(date-time)|false|none|none|
|endDate|string(date-time)|false|none|none|
|filters|[[ReportFilter](#schemareportfilter)]|false|none|[ReportFilter]|

<h2 id="tocSreportfilter">ReportFilter</h2>

<a id="schemareportfilter"></a>

```json
{
  "type": "string",
  "name": "string",
  "formattedName": "string"
}

```

*ReportFilter*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|name|string|false|none|none|
|formattedName|string|false|none|none|

<h2 id="tocSisconversiontrackingonforthisprogramrequest">IsConversionTrackingOnForThisProgramRequest</h2>

<a id="schemaisconversiontrackingonforthisprogramrequest"></a>

```json
{
  "advertiserId": 0
}

```

*IsConversionTrackingOnForThisProgramRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|advertiserId|integer(int32)|false|none|none|

<h2 id="tocSshorturlmetadatarequest">ShorturlMetadataRequest</h2>

<a id="schemashorturlmetadatarequest"></a>

```json
{
  "shorturls": [
    "string"
  ],
  "startPage": 0,
  "advertiserId": 0,
  "startDate": "2018-10-02T04:10:23Z",
  "endDate": "2018-10-02T04:10:23Z",
  "filters": [
    {
      "type": "string",
      "name": "string",
      "formattedName": "string"
    }
  ]
}

```

*ShorturlMetadataRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|shorturls|[string]|false|none|none|
|startPage|integer(int32)|false|none|none|
|advertiserId|integer(int32)|false|none|none|
|startDate|string(date-time)|false|none|none|
|endDate|string(date-time)|false|none|none|
|filters|[[ReportFilter](#schemareportfilter)]|false|none|[ReportFilter]|

<h2 id="tocSinvoicesrequest">InvoicesRequest</h2>

<a id="schemainvoicesrequest"></a>

```json
{
  "username": "string",
  "idList": [
    "string"
  ],
  "invoicesWanted": 0,
  "invoiceStatus": "string",
  "keyword": "string",
  "start": "string"
}

```

*InvoicesRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|username for the invoice to build.|
|idList|[string]|false|none|Ids of invoices to return|
|invoicesWanted|integer(int32)|false|none|The number of invoices to return (most recent first)|
|invoiceStatus|string|false|none|Status of the invoices desired|
|keyword|string|false|none|Search terms|
|start|string(int32)|false|none|Search terms|

<h2 id="tocSpaymentsrequest">PaymentsRequest</h2>

<a id="schemapaymentsrequest"></a>

```json
{
  "username": "string",
  "paymentsWanted": 0,
  "paymentStatus": "string"
}

```

*PaymentsRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|username for the payments to pull.|
|paymentsWanted|integer(int32)|false|none|The number of payments to return (most recent first)|
|paymentStatus|string|false|none|Status of the payments desired|

<h2 id="tocSreportingwizardrequest">ReportingWizardRequest</h2>

<a id="schemareportingwizardrequest"></a>

```json
{
  "attributes": [
    "string"
  ],
  "advertiserId": 0,
  "end": "2018-10-02T04:10:23Z",
  "start": "2018-10-02T04:10:23Z",
  "spfData": {
    "start": 0,
    "quantity": 0,
    "filter": [
      "string"
    ],
    "keyword": "string",
    "sortAttribute": "string",
    "reverse": true
  },
  "username": "string",
  "filters": [
    {
      "type": "string",
      "name": "string",
      "formattedName": "string"
    }
  ]
}

```

*ReportingWizardRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|attributes|[string]|false|none|none|
|advertiserId|integer(int32)|false|none|none|
|end|string(date-time)|false|none|none|
|start|string(date-time)|false|none|none|
|spfData|[SortPageFilterRequestData](#schemasortpagefilterrequestdata)|false|none|SortPageFilterRequestData|
|username|string|false|none|none|
|filters|[[ReportFilter](#schemareportfilter)]|false|none|[ReportFilter]|

<h2 id="tocSsortpagefilterrequestdata">SortPageFilterRequestData</h2>

<a id="schemasortpagefilterrequestdata"></a>

```json
{
  "start": 0,
  "quantity": 0,
  "filter": [
    "string"
  ],
  "keyword": "string",
  "sortAttribute": "string",
  "reverse": true
}

```

*SortPageFilterRequestData*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|start|integer(int32)|false|none|none|
|quantity|integer(int32)|false|none|none|
|filter|[string]|false|none|none|
|keyword|string|false|none|none|
|sortAttribute|string|false|none|none|
|reverse|boolean|false|none|none|

<h2 id="tocSusertrackingpixelsrequest">UserTrackingPixelsRequest</h2>

<a id="schemausertrackingpixelsrequest"></a>

```json
{}

```

*UserTrackingPixelsRequest*

### Properties

*None*

<h2 id="tocSexportdatarequest">ExportDataRequest</h2>

<a id="schemaexportdatarequest"></a>

```json
{
  "attributes": [
    "string"
  ],
  "advertiserId": 0,
  "end": null,
  "start": null,
  "spfData": {
    "start": 0,
    "quantity": 0,
    "filter": [
      "string"
    ],
    "keyword": "string",
    "sortAttribute": "string",
    "reverse": true
  },
  "filters": [
    {
      "type": "string",
      "name": "string",
      "formattedName": "string"
    }
  ],
  "includeBots": true,
  "username": "string"
}

```

*ExportDataRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|attributes|[string]|false|none|none|
|advertiserId|integer(int32)|false|none|none|
|end|dateTime(date-time)|false|none|End date for the report required. Date format YYYY-MM-DD|
|start|dateTime(date-time)|false|none|Start date for the report required. Date format YYYY-MM-DD|
|spfData|[SortPageFilterRequestData](#schemasortpagefilterrequestdata)|false|none|SortPageFilterRequestData|
|filters|[[ReportFilter](#schemareportfilter)]|false|none|[ReportFilter]|
|includeBots|boolean|false|none|none|
|username|string|false|none|none|

<h2 id="tocSsupporteddomainsrequest">SupportedDomainsRequest</h2>

<a id="schemasupporteddomainsrequest"></a>

```json
{}

```

*SupportedDomainsRequest*

### Properties

*None*

<h2 id="tocSaddnewlinkrequest">AddNewLinkRequest</h2>

<a id="schemaaddnewlinkrequest"></a>

```json
{
  "url": "string",
  "tsid": 0,
  "trackingCode": "string",
  "skipAffiliateRedirect": 0,
  "vanityCode": "string",
  "placeholderCode": "string",
  "bulkMode": 0,
  "overrides": "string",
  "domain": "string",
  "note": "string",
  "trackingPixels": "string",
  "applePreference": 0,
  "linkCreatorSetting": "string"
}

```

*AddNewLinkRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|url|string|false|none|none|
|tsid|integer(int32)|false|none|none|
|trackingCode|string|false|none|none|
|skipAffiliateRedirect|integer(int32)|false|none|none|
|vanityCode|string|false|none|none|
|placeholderCode|string|false|none|none|
|bulkMode|integer(int32)|false|none|none|
|overrides|string|false|none|none|
|domain|string|false|none|none|
|note|string|false|none|none|
|trackingPixels|string|false|none|none|
|applePreference|integer(int32)|false|none|none|
|linkCreatorSetting|string|false|none|none|

<h2 id="tocSaddnewgroupwithnotesrequest">AddNewGroupWithNotesRequest</h2>

<a id="schemaaddnewgroupwithnotesrequest"></a>

```json
{
  "groupName": "string",
  "notes": "string",
  "id": "string"
}

```

*AddNewGroupWithNotesRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|groupName|string|false|none|Name desired for the new group.|
|notes|string|false|none|Notes that need to be attached to the group.|
|id|string(int32)|false|none|Only provide ID when editing existing group.|

<h2 id="tocSlinkclicksbycountryrequest">LinkClicksByCountryRequest</h2>

<a id="schemalinkclicksbycountryrequest"></a>

```json
{
  "shortCode": "string",
  "start": null,
  "end": null,
  "advertiserId": 0,
  "doPreviousPeriod": 0,
  "dataResolution": "hour"
}

```

*LinkClicksByCountryRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|shortCode|string|false|none|Short code for the request. Required.|
|start|dateTime(date-time)|false|none|Start date for the report required. Date format YYYY-MM-DD|
|end|dateTime(date-time)|false|none|End date for the report required. Date format YYYY-MM-DD|
|advertiserId|integer(int32)|false|none|Id of the advertiser to show for. 0 for all, 1 for itunes and 3 for amazon|
|doPreviousPeriod|integer(int32)|false|none|Indicates whether to return data of the last queried set with the new request|
|dataResolution|string|false|none|Resolution of the data.|

#### Enumerated Values

|Property|Value|
|---|---|
|dataResolution|hour|
|dataResolution|day|
|dataResolution|month|
|dataResolution|lifetime|

<h2 id="tocSclicksbycountryrequest">ClicksByCountryRequest</h2>

<a id="schemaclicksbycountryrequest"></a>

```json
{
  "start": null,
  "end": null,
  "advertiserId": 0,
  "doPreviousPeriod": 0,
  "dataResolution": "hour"
}

```

*ClicksByCountryRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|start|dateTime(date-time)|false|none|Start date for the report required. Date format YYYY-MM-DD|
|end|dateTime(date-time)|false|none|End date for the report required. Date format YYYY-MM-DD|
|advertiserId|integer(int32)|false|none|Id of the advertiser to show for. 0 for all, 1 for itunes and 3 for amazon|
|doPreviousPeriod|integer(int32)|false|none|Indicates whether to return data of the last queried set with the new request|
|dataResolution|string|false|none|Resolution of the data.|

#### Enumerated Values

|Property|Value|
|---|---|
|dataResolution|hour|
|dataResolution|day|
|dataResolution|month|
|dataResolution|lifetime|

<h2 id="tocSinvoicecurrentperiodrequest">InvoiceCurrentPeriodRequest</h2>

<a id="schemainvoicecurrentperiodrequest"></a>

```json
{
  "username": "string"
}

```

*InvoiceCurrentPeriodRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|username for the invoice to build.|

<h2 id="tocSaffiliateprogramsperuserrequest">AffiliateProgramsPerUserRequest</h2>

<a id="schemaaffiliateprogramsperuserrequest"></a>

```json
{}

```

*AffiliateProgramsPerUserRequest*

### Properties

*None*

<h2 id="tocSallgroupsrequest">AllGroupsRequest</h2>

<a id="schemaallgroupsrequest"></a>

```json
{}

```

*AllGroupsRequest*

### Properties

*None*

<h2 id="tocSallgroupswithdetailsrequest">AllGroupsWithDetailsRequest</h2>

<a id="schemaallgroupswithdetailsrequest"></a>

```json
{}

```

*AllGroupsWithDetailsRequest*

### Properties

*None*

<h2 id="tocSarchiveagrouprequest">ArchiveAGroupRequest</h2>

<a id="schemaarchiveagrouprequest"></a>

```json
{
  "ids": "string",
  "restoreFlag": null
}

```

*ArchiveAGroupRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ids|string|false|none|Ids of groups to archive|
|restoreFlag|int(int32)|false|none|1 for restore, 0 for archival|

<h2 id="tocSgroupsummarybyattributerequest">GroupSummaryByAttributeRequest</h2>

<a id="schemagroupsummarybyattributerequest"></a>

```json
{
  "groupId": 0,
  "start": null,
  "end": null,
  "advertiserId": "0",
  "attributeName": "product",
  "doPreviousPeriod": "0",
  "resolution": "hour"
}

```

*GroupSummaryByAttributeRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|groupId|integer(int32)|false|none|groupid for the group that you want to retrieve info for.|
|start|dateTime(date-time)|false|none|Start date for the report required.|
|end|dateTime(date-time)|false|none|End date for the report required|
|advertiserId|integer(int32)|false|none|Id of the advertiser to show for. 0 for all, 1 for itunes and 3 for amazon|
|attributeName|string|false|none|Indicated the different Reports available.|
|doPreviousPeriod|integer(int32)|false|none|Indicates whether to return data of the last queried set with the new request|
|resolution|string|false|none|Resolution of the data.|

#### Enumerated Values

|Property|Value|
|---|---|
|advertiserId|0|
|advertiserId|1|
|advertiserId|3|
|attributeName|product|
|attributeName|destination|
|attributeName|referrer|
|attributeName|tag|
|attributeName|os|
|attributeName|device|
|attributeName|browser|
|attributeName|shorturl|
|attributeName|group|
|doPreviousPeriod|0|
|doPreviousPeriod|1|
|resolution|hour|
|resolution|day|
|resolution|month|
|resolution|lifetime|

<h2 id="tocSgrouprequest">GroupRequest</h2>

<a id="schemagrouprequest"></a>

```json
{
  "groupId": 0,
  "group": "string"
}

```

*GroupRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|groupId|integer(int32)|false|none|tsid for the group that you want to retrieve info for. Note you only need either the tsid or the group|
|group|string|false|none|name of the group that you want to retrieve info for. Note you only need either the tsid or the groupname|

<h2 id="tocSlinkclicksbyresolutionrequest">LinkClicksByResolutionRequest</h2>

<a id="schemalinkclicksbyresolutionrequest"></a>

```json
{
  "shortCode": "string",
  "start": null,
  "end": null,
  "advertiserId": "0",
  "resolution": "hour",
  "doPreviousPeriod": "0"
}

```

*LinkClicksByResolutionRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|shortCode|string|false|none|shortcode for the link that you want to retrieve info for.|
|start|dateTime(date-time)|false|none|Start date for the report required. Date format YYYY-MM-DD|
|end|dateTime(date-time)|false|none|End date for the report required. Date format YYYY-MM-DD|
|advertiserId|integer(int32)|false|none|Id of the advertiser to show for. 0 for all, 1 for itunes and 3 for amazon|
|resolution|string|false|none|Resolution of the data.|
|doPreviousPeriod|integer(int32)|false|none|Indicates whether to return data of the last queried set with the new request|

#### Enumerated Values

|Property|Value|
|---|---|
|advertiserId|0|
|advertiserId|1|
|advertiserId|3|
|resolution|hour|
|resolution|day|
|resolution|month|
|resolution|lifetime|
|doPreviousPeriod|0|
|doPreviousPeriod|1|

<h2 id="tocSlinksummarybyattributerequest">LinkSummaryByAttributeRequest</h2>

<a id="schemalinksummarybyattributerequest"></a>

```json
{
  "shortCode": "string",
  "start": null,
  "end": null,
  "advertiserId": "0",
  "attributeName": "product",
  "doPreviousPeriod": "0",
  "resolution": "hour"
}

```

*LinkSummaryByAttributeRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|shortCode|string|false|none|shortcode for the link that you want to retrieve info for.|
|start|dateTime(date-time)|false|none|Start date for the report required.|
|end|dateTime(date-time)|false|none|End date for the report required|
|advertiserId|integer(int32)|false|none|Id of the advertiser to show for. 0 for all, 1 for itunes and 3 for amazon|
|attributeName|string|false|none|Indicated the different Reports available.|
|doPreviousPeriod|integer(int32)|false|none|Indicates whether to return data of the last queried set with the new request|
|resolution|string|false|none|Resolution of the data.|

#### Enumerated Values

|Property|Value|
|---|---|
|advertiserId|0|
|advertiserId|1|
|advertiserId|3|
|attributeName|product|
|attributeName|destination|
|attributeName|referrer|
|attributeName|tag|
|attributeName|os|
|attributeName|device|
|attributeName|browser|
|attributeName|shorturl|
|attributeName|group|
|doPreviousPeriod|0|
|doPreviousPeriod|1|
|resolution|hour|
|resolution|day|
|resolution|month|
|resolution|lifetime|

<h2 id="tocSlistlinksrequest">ListLinksRequest</h2>

<a id="schemalistlinksrequest"></a>

```json
{
  "groupId": 0,
  "numberOfLinks": 0,
  "linksCreatedStart": "2018-10-02T04:10:23Z",
  "linksCreatedEnd": "2018-10-02T04:10:23Z",
  "baseShortCodes": [
    "string"
  ]
}

```

*ListLinksRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|groupId|integer(int32)|false|none|tsid for the group that you want to retrieve info for. Use 0 for the default group.|
|numberOfLinks|integer(int32)|false|none|Number Of Links desired|
|linksCreatedStart|string(date-time)|false|none|none|
|linksCreatedEnd|string(date-time)|false|none|none|
|baseShortCodes|[string]|false|none|none|

<h2 id="tocSupdateshorturlrequest">UpdateShortUrlRequest</h2>

<a id="schemaupdateshorturlrequest"></a>

```json
{
  "shortUrlCode": "string",
  "tsid": 0,
  "overrides": "string",
  "trackingTag": "string",
  "note": "string",
  "newUrl": "string",
  "domain": "string",
  "trackingPixels": "string",
  "applePreference": 0,
  "linkCreatorSetting": "string"
}

```

*UpdateShortUrlRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|shortUrlCode|string|true|none|none|
|tsid|integer(int32)|true|none|none|
|overrides|string|false|none|none|
|trackingTag|string|false|none|none|
|note|string|false|none|none|
|newUrl|string|true|none|none|
|domain|string|false|none|none|
|trackingPixels|string|false|none|none|
|applePreference|integer(int32)|false|none|none|
|linkCreatorSetting|string|false|none|none|

<h2 id="tocSclicksbyresolutionrequest">ClicksByResolutionRequest</h2>

<a id="schemaclicksbyresolutionrequest"></a>

```json
{
  "username": "string",
  "start": null,
  "end": null,
  "advertiserId": "0",
  "resolution": "hour",
  "doPreviousPeriod": "0"
}

```

*ClicksByResolutionRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|none|
|start|dateTime(date-time)|false|none|Start date for the report required. Date format YYYY-MM-DD|
|end|dateTime(date-time)|false|none|End date for the report required. Date format YYYY-MM-DD|
|advertiserId|integer(int32)|false|none|Id of the advertiser to show for. 0 for all, 1 for itunes and 3 for amazon|
|resolution|string|false|none|Resolution of the data.|
|doPreviousPeriod|integer(int32)|false|none|Indicates whether to return data of the last queried set with the new request|

#### Enumerated Values

|Property|Value|
|---|---|
|advertiserId|0|
|advertiserId|1|
|advertiserId|3|
|resolution|hour|
|resolution|day|
|resolution|month|
|resolution|lifetime|
|doPreviousPeriod|0|
|doPreviousPeriod|1|

<h2 id="tocSshorturlarchivingrequest">ShortUrlArchivingRequest</h2>

<a id="schemashorturlarchivingrequest"></a>

```json
{
  "unarchiveMode": null,
  "codeToArchive": "string"
}

```

*ShortUrlArchivingRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|unarchiveMode|int(int32)|false|none|0 for archive 1 for restoring|
|codeToArchive|string|false|none|short url code for member being archived or restore|

<h2 id="tocSremoveaffiliateparameterresponse">RemoveAffiliateParameterResponse</h2>

<a id="schemaremoveaffiliateparameterresponse"></a>

```json
{
  "responseStatus": {
    "errorCode": "string",
    "message": "string",
    "stackTrace": "string",
    "errors": [
      {
        "errorCode": "string",
        "fieldName": "string",
        "message": "string",
        "meta": {
          "property1": "string",
          "property2": "string"
        }
      }
    ],
    "meta": {
      "property1": "string",
      "property2": "string"
    }
  }
}

```

*RemoveAffiliateParameterResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|responseStatus|[ResponseStatus](#schemaresponsestatus)|false|none|ResponseStatus|

<h2 id="tocSresponsestatus">ResponseStatus</h2>

<a id="schemaresponsestatus"></a>

```json
{
  "errorCode": "string",
  "message": "string",
  "stackTrace": "string",
  "errors": [
    {
      "errorCode": "string",
      "fieldName": "string",
      "message": "string",
      "meta": {
        "property1": "string",
        "property2": "string"
      }
    }
  ],
  "meta": {
    "property1": "string",
    "property2": "string"
  }
}

```

*ResponseStatus*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errorCode|string|false|none|none|
|message|string|false|none|none|
|stackTrace|string|false|none|none|
|errors|[[ResponseError](#schemaresponseerror)]|false|none|[ResponseError]|
|meta|[Dictionary_String_String_](#schemadictionary_string_string_)|false|none|Dictionary<String,String>|

<h2 id="tocSresponseerror">ResponseError</h2>

<a id="schemaresponseerror"></a>

```json
{
  "errorCode": "string",
  "fieldName": "string",
  "message": "string",
  "meta": {
    "property1": "string",
    "property2": "string"
  }
}

```

*ResponseError*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errorCode|string|false|none|none|
|fieldName|string|false|none|none|
|message|string|false|none|none|
|meta|[Dictionary_String_String_](#schemadictionary_string_string_)|false|none|Dictionary<String,String>|

<h2 id="tocSaffiliateparameterinforesponse">AffiliateParameterInfoResponse</h2>

<a id="schemaaffiliateparameterinforesponse"></a>

```json
{
  "affiliateNetworks": [
    {
      "advertiserName": "string",
      "affiliateToken": "string",
      "affiliateNetworkName": "string",
      "affiliateNetworkDisplayName": "string"
    }
  ]
}

```

*AffiliateParameterInfoResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|affiliateNetworks|[[AffiliateTokenByAffiliateNetwork](#schemaaffiliatetokenbyaffiliatenetwork)]|false|none|[AffiliateTokenByAffiliateNetwork]|

<h2 id="tocSaffiliatetokenbyaffiliatenetwork">AffiliateTokenByAffiliateNetwork</h2>

<a id="schemaaffiliatetokenbyaffiliatenetwork"></a>

```json
{
  "advertiserName": "string",
  "affiliateToken": "string",
  "affiliateNetworkName": "string",
  "affiliateNetworkDisplayName": "string"
}

```

*AffiliateTokenByAffiliateNetwork*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|advertiserName|string|false|none|none|
|affiliateToken|string|false|none|none|
|affiliateNetworkName|string|false|none|none|
|affiliateNetworkDisplayName|string|false|none|none|

<h2 id="tocSgroupaffiliateparameterinforesponse">GroupAffiliateParameterInfoResponse</h2>

<a id="schemagroupaffiliateparameterinforesponse"></a>

```json
{
  "groupAffiliateTokens": {
    "property1": [
      {
        "advertiserName": "string",
        "affiliateToken": "string",
        "affiliateNetworkName": "string",
        "affiliateNetworkDisplayName": "string"
      }
    ],
    "property2": [
      {
        "advertiserName": "string",
        "affiliateToken": "string",
        "affiliateNetworkName": "string",
        "affiliateNetworkDisplayName": "string"
      }
    ]
  }
}

```

*GroupAffiliateParameterInfoResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|groupAffiliateTokens|[Dictionary_Int32_List_AffiliateTokenByAffiliateNetwork_](#schemadictionary_int32_list_affiliatetokenbyaffiliatenetwork_)|false|none|Dictionary<Int32,List<AffiliateTokenByAffiliateNetwork>>|

<h2 id="tocSaddorupdateaffiliateparameterresponse">AddOrUpdateAffiliateParameterResponse</h2>

<a id="schemaaddorupdateaffiliateparameterresponse"></a>

```json
{
  "responseStatus": {
    "errorCode": "string",
    "message": "string",
    "stackTrace": "string",
    "errors": [
      {
        "errorCode": "string",
        "fieldName": "string",
        "message": "string",
        "meta": {
          "property1": "string",
          "property2": "string"
        }
      }
    ],
    "meta": {
      "property1": "string",
      "property2": "string"
    }
  }
}

```

*AddOrUpdateAffiliateParameterResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|responseStatus|[ResponseStatus](#schemaresponsestatus)|false|none|ResponseStatus|

<h2 id="tocSexportreportdataresponse">ExportReportDataResponse</h2>

<a id="schemaexportreportdataresponse"></a>

```json
{
  "data": [
    {
      "clicks": 0,
      "clientAffiliated": 0,
      "conv": 0,
      "earnings": 0,
      "epc": 0,
      "group": "string",
      "name": "string",
      "overflow": 0,
      "sharedActive": 0,
      "sharedPassive": 0,
      "user": "string"
    }
  ]
}

```

*ExportReportDataResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[SummaryDataRow](#schemasummarydatarow)]|false|none|[SummaryDataRow]|

<h2 id="tocSsummarydatarow">SummaryDataRow</h2>

<a id="schemasummarydatarow"></a>

```json
{
  "clicks": 0,
  "clientAffiliated": 0,
  "conv": 0,
  "earnings": 0,
  "epc": 0,
  "group": "string",
  "name": "string",
  "overflow": 0,
  "sharedActive": 0,
  "sharedPassive": 0,
  "user": "string"
}

```

*SummaryDataRow*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|clicks|integer(int64)|false|none|none|
|clientAffiliated|integer(int64)|false|none|none|
|conv|number(float)|false|none|none|
|earnings|number(double)|false|none|none|
|epc|number(float)|false|none|none|
|group|string|false|none|none|
|name|string|false|none|none|
|overflow|integer(int64)|false|none|none|
|sharedActive|integer(int64)|false|none|none|
|sharedPassive|integer(int64)|false|none|none|
|user|string|false|none|none|

<h2 id="tocSgetallpostprocessingrulesresponse">GetAllPostProcessingRulesResponse</h2>

<a id="schemagetallpostprocessingrulesresponse"></a>

```json
{
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "postProcessingRulesCategory": "string",
  "teamRules": [
    {
      "conditions": [
        {}
      ],
      "actions": [
        {}
      ]
    }
  ],
  "userRules": [
    {
      "conditions": [
        {}
      ],
      "actions": [
        {}
      ]
    }
  ],
  "shortCodeRules": {
    "property1": [
      {
        "conditions": [
          {}
        ],
        "actions": [
          {}
        ]
      }
    ],
    "property2": [
      {
        "conditions": [
          {}
        ],
        "actions": [
          {}
        ]
      }
    ]
  }
}

```

*GetAllPostProcessingRulesResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isError|[Result](#schemaresult)|false|none|Result|
|postProcessingRulesCategory|string|false|none|none|
|teamRules|[[ConditionalPostProcessingActions](#schemaconditionalpostprocessingactions)]|false|none|[ConditionalPostProcessingActions]|
|userRules|[[ConditionalPostProcessingActions](#schemaconditionalpostprocessingactions)]|false|none|[ConditionalPostProcessingActions]|
|shortCodeRules|[Dictionary_String_List_ConditionalPostProcessingActions_](#schemadictionary_string_list_conditionalpostprocessingactions_)|false|none|Dictionary<String,List<ConditionalPostProcessingActions>>|

<h2 id="tocSresult">Result</h2>

<a id="schemaresult"></a>

```json
{
  "errorMessage": "string",
  "errorTitle": "string"
}

```

*Result*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errorMessage|string|false|none|none|
|errorTitle|string|false|none|none|

<h2 id="tocSconditionalpostprocessingactions">ConditionalPostProcessingActions</h2>

<a id="schemaconditionalpostprocessingactions"></a>

```json
{
  "conditions": [
    {}
  ],
  "actions": [
    {}
  ]
}

```

*ConditionalPostProcessingActions*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|conditions|[[PostProcessingCondition](#schemapostprocessingcondition)]|false|none|[PostProcessingCondition]|
|actions|[[PostProcessingAction](#schemapostprocessingaction)]|false|none|[PostProcessingAction]|

<h2 id="tocSpostprocessingcondition">PostProcessingCondition</h2>

<a id="schemapostprocessingcondition"></a>

```json
{}

```

*PostProcessingCondition*

### Properties

*None*

<h2 id="tocSpostprocessingaction">PostProcessingAction</h2>

<a id="schemapostprocessingaction"></a>

```json
{}

```

*PostProcessingAction*

### Properties

*None*

<h2 id="tocSgetallutmcompatibledomainsresponse">GetAllUtmCompatibleDomainsResponse</h2>

<a id="schemagetallutmcompatibledomainsresponse"></a>

```json
{
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "domains": [
    {}
  ],
  "statusCode": 0
}

```

*GetAllUtmCompatibleDomainsResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isError|[Result](#schemaresult)|false|none|Result|
|domains|[[Tuple_String_PostProcessingActionLevel_](#schematuple_string_postprocessingactionlevel_)]|false|none|[Tuple<String,PostProcessingActionLevel>]|
|statusCode|integer(int32)|false|none|none|

<h2 id="tocSnewshorturlresponse">NewShortUrlResponse</h2>

<a id="schemanewshorturlresponse"></a>

```json
{
  "code": "string",
  "newLink": "string"
}

```

*NewShortUrlResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|
|newLink|string|false|none|none|

<h2 id="tocSlinkhealtherrorresponse">LinkHealthErrorResponse</h2>

<a id="schemalinkhealtherrorresponse"></a>

```json
{
  "totalHidden": 0,
  "totalShown": 0
}

```

*LinkHealthErrorResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalHidden|integer(int32)|false|none|none|
|totalShown|integer(int32)|false|none|none|

<h2 id="tocSlinkhealtherrorhideorshowresponse">LinkHealthErrorHideOrShowResponse</h2>

<a id="schemalinkhealtherrorhideorshowresponse"></a>

```json
{
  "httpStatusCode": "string"
}

```

*LinkHealthErrorHideOrShowResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|httpStatusCode|string|false|none|none|

<h2 id="tocSaddorupdatepostprocessingrulesresponse">AddOrUpdatePostProcessingRulesResponse</h2>

<a id="schemaaddorupdatepostprocessingrulesresponse"></a>

```json
{
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "id": "string",
  "postProcessingRules": "string",
  "deleteResponse": {
    "isError": {
      "errorMessage": "string",
      "errorTitle": "string"
    },
    "rowRemoved": true,
    "postProcessingActionsRemoved": true
  }
}

```

*AddOrUpdatePostProcessingRulesResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isError|[Result](#schemaresult)|false|none|Result|
|id|string|false|none|none|
|postProcessingRules|string|false|none|none|
|deleteResponse|[DeletePostProcessingRulesResponse](#schemadeletepostprocessingrulesresponse)|false|none|DeletePostProcessingRulesResponse|

<h2 id="tocSdeletepostprocessingrulesresponse">DeletePostProcessingRulesResponse</h2>

<a id="schemadeletepostprocessingrulesresponse"></a>

```json
{
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "rowRemoved": true,
  "postProcessingActionsRemoved": true
}

```

*DeletePostProcessingRulesResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isError|[Result](#schemaresult)|false|none|Result|
|rowRemoved|boolean|false|none|none|
|postProcessingActionsRemoved|boolean|false|none|none|

<h2 id="tocSgetshortcodepostprocessingrulesresponse">GetShortCodePostProcessingRulesResponse</h2>

<a id="schemagetshortcodepostprocessingrulesresponse"></a>

```json
{
  "shortCode": "string",
  "postProcessingActions": {
    "property1": {
      "shorturl": [
        {
          "conditions": [
            {}
          ],
          "actions": [
            {}
          ]
        }
      ],
      "team": [
        {
          "conditions": [
            {}
          ],
          "actions": [
            {}
          ]
        }
      ],
      "user": [
        {
          "conditions": [
            {}
          ],
          "actions": [
            {}
          ]
        }
      ]
    },
    "property2": {
      "shorturl": [
        {
          "conditions": [
            {}
          ],
          "actions": [
            {}
          ]
        }
      ],
      "team": [
        {
          "conditions": [
            {}
          ],
          "actions": [
            {}
          ]
        }
      ],
      "user": [
        {
          "conditions": [
            {}
          ],
          "actions": [
            {}
          ]
        }
      ]
    }
  },
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  }
}

```

*GetShortCodePostProcessingRulesResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|shortCode|string|false|none|none|
|postProcessingActions|[Dictionary_String_PostProcessingActionsShorturl_](#schemadictionary_string_postprocessingactionsshorturl_)|false|none|Dictionary<String,PostProcessingActionsShorturl>|
|isError|[Result](#schemaresult)|false|none|Result|

<h2 id="tocSpostprocessingactionsshorturl">PostProcessingActionsShorturl</h2>

<a id="schemapostprocessingactionsshorturl"></a>

```json
{
  "shorturl": [
    {
      "conditions": [
        {}
      ],
      "actions": [
        {}
      ]
    }
  ],
  "team": [
    {
      "conditions": [
        {}
      ],
      "actions": [
        {}
      ]
    }
  ],
  "user": [
    {
      "conditions": [
        {}
      ],
      "actions": [
        {}
      ]
    }
  ]
}

```

*PostProcessingActionsShorturl*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|shorturl|[[ConditionalPostProcessingActions](#schemaconditionalpostprocessingactions)]|false|none|[ConditionalPostProcessingActions]|
|team|[[ConditionalPostProcessingActions](#schemaconditionalpostprocessingactions)]|false|none|[ConditionalPostProcessingActions]|
|user|[[ConditionalPostProcessingActions](#schemaconditionalpostprocessingactions)]|false|none|[ConditionalPostProcessingActions]|

<h2 id="tocSaddorupdateutmcompatibledomainsresponse">AddOrUpdateUtmCompatibleDomainsResponse</h2>

<a id="schemaaddorupdateutmcompatibledomainsresponse"></a>

```json
{
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "executedDelete": true,
  "executedAddOrUpdate": true,
  "statusCode": 0
}

```

*AddOrUpdateUtmCompatibleDomainsResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isError|[Result](#schemaresult)|false|none|Result|
|executedDelete|boolean|false|none|none|
|executedAddOrUpdate|boolean|false|none|none|
|statusCode|integer(int32)|false|none|none|

<h2 id="tocSdeleteutmcompatibledomainsresponse">DeleteUtmCompatibleDomainsResponse</h2>

<a id="schemadeleteutmcompatibledomainsresponse"></a>

```json
{
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "numDomainsRemoved": 0,
  "statusCode": 0
}

```

*DeleteUtmCompatibleDomainsResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isError|[Result](#schemaresult)|false|none|Result|
|numDomainsRemoved|integer(int32)|false|none|none|
|statusCode|integer(int32)|false|none|none|

<h2 id="tocSgetutmcompatibledomainsresponse">GetUtmCompatibleDomainsResponse</h2>

<a id="schemagetutmcompatibledomainsresponse"></a>

```json
{
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "domains": [
    "string"
  ],
  "statusCode": 0
}

```

*GetUtmCompatibleDomainsResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isError|[Result](#schemaresult)|false|none|Result|
|domains|[string]|false|none|none|
|statusCode|integer(int32)|false|none|none|

<h2 id="tocSaddtrackingpixelresponse">AddTrackingPixelResponse</h2>

<a id="schemaaddtrackingpixelresponse"></a>

```json
{
  "trackingPixel": {
    "typeString": "string",
    "displayName": "string",
    "renderAs": "string",
    "id": "string",
    "js": "string",
    "name": "string",
    "type": "string",
    "url": "string",
    "metadata": {
      "username": "string",
      "disabled": true,
      "updatedUtc": "2018-10-02T04:10:23Z",
      "createdUtc": "2018-10-02T04:10:23Z"
    },
    "params": {
      "property1": {},
      "property2": {}
    }
  }
}

```

*AddTrackingPixelResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|trackingPixel|[TrackingPixel](#schematrackingpixel)|false|none|TrackingPixel|

<h2 id="tocStrackingpixel">TrackingPixel</h2>

<a id="schematrackingpixel"></a>

```json
{
  "typeString": "string",
  "displayName": "string",
  "renderAs": "string",
  "id": "string",
  "js": "string",
  "name": "string",
  "type": "string",
  "url": "string",
  "metadata": {
    "username": "string",
    "disabled": true,
    "updatedUtc": "2018-10-02T04:10:23Z",
    "createdUtc": "2018-10-02T04:10:23Z"
  },
  "params": {
    "property1": {},
    "property2": {}
  }
}

```

*TrackingPixel*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|typeString|string|false|none|none|
|displayName|string|false|none|none|
|renderAs|string|false|none|none|
|id|string|false|none|none|
|js|string|false|none|none|
|name|string|false|none|none|
|type|string|false|none|none|
|url|string|false|none|none|
|metadata|[PixelMetadata](#schemapixelmetadata)|false|none|PixelMetadata|
|params|[IDictionary_String_Object_](#schemaidictionary_string_object_)|false|none|IDictionary<String,Object>|

<h2 id="tocSpixelmetadata">PixelMetadata</h2>

<a id="schemapixelmetadata"></a>

```json
{
  "username": "string",
  "disabled": true,
  "updatedUtc": "2018-10-02T04:10:23Z",
  "createdUtc": "2018-10-02T04:10:23Z"
}

```

*PixelMetadata*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|none|
|disabled|boolean|false|none|none|
|updatedUtc|string(date-time)|false|none|none|
|createdUtc|string(date-time)|false|none|none|

<h2 id="tocSgenericerrorresponse">GenericErrorResponse</h2>

<a id="schemagenericerrorresponse"></a>

```json
{
  "responseStatus": {
    "errorCode": "string",
    "message": "string",
    "stackTrace": "string",
    "errors": [
      {
        "errorCode": "string",
        "fieldName": "string",
        "message": "string",
        "meta": {
          "property1": "string",
          "property2": "string"
        }
      }
    ],
    "meta": {
      "property1": "string",
      "property2": "string"
    }
  }
}

```

*GenericErrorResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|responseStatus|[ResponseStatus](#schemaresponsestatus)|false|none|ResponseStatus|

<h2 id="tocSserviceunavailable503responseattribute">ServiceUnavailable503ResponseAttribute</h2>

<a id="schemaserviceunavailable503responseattribute"></a>

```json
{
  "statusCode": 0,
  "description": "string",
  "isDefaultResponse": true,
  "responseType": {},
  "typeId": {}
}

```

*ServiceUnavailable503ResponseAttribute*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|statusCode|integer(int32)|false|none|none|
|description|string|false|none|none|
|isDefaultResponse|boolean|false|none|none|
|responseType|[Type](#schematype)|false|none|Type|
|typeId|[Object](#schemaobject)|false|none|Object|

<h2 id="tocStype">Type</h2>

<a id="schematype"></a>

```json
{}

```

*Type*

### Properties

*None*

<h2 id="tocSaddsubaccountresponse">AddSubAccountResponse</h2>

<a id="schemaaddsubaccountresponse"></a>

```json
{
  "confirmationEmailSent": true
}

```

*AddSubAccountResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|confirmationEmailSent|boolean|false|none|none|

<h2 id="tocSgetsubaccountsresponse">GetSubAccountsResponse</h2>

<a id="schemagetsubaccountsresponse"></a>

```json
{
  "subAccounts": [
    "string"
  ]
}

```

*GetSubAccountsResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|subAccounts|[string]|false|none|none|

<h2 id="tocSsupporteddomainresponse">SupportedDomainResponse</h2>

<a id="schemasupporteddomainresponse"></a>

```json
{
  "domain": {
    "name": "string",
    "subjectAlternativeNames": [
      "string"
    ],
    "owner": "string",
    "usersAllowedAccess": [
      "string"
    ],
    "allowedDestinationDomains": [
      "string"
    ],
    "letsencrypt": true,
    "letsencryptMethod": "string",
    "dnsProvider": "string",
    "dnsimpleUserName": "string",
    "aliasOf": "string",
    "startDateUtc": "2018-10-02T04:10:23Z",
    "endDateUtc": "2018-10-02T04:10:23Z",
    "rootRedirectUrl": "string",
    "automaticallyGrantChildAccountAccess": true
  }
}

```

*SupportedDomainResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|domain|[SupportedDomain](#schemasupporteddomain)|false|none|SupportedDomain|

<h2 id="tocSsupporteddomain">SupportedDomain</h2>

<a id="schemasupporteddomain"></a>

```json
{
  "name": "string",
  "subjectAlternativeNames": [
    "string"
  ],
  "owner": "string",
  "usersAllowedAccess": [
    "string"
  ],
  "allowedDestinationDomains": [
    "string"
  ],
  "letsencrypt": true,
  "letsencryptMethod": "string",
  "dnsProvider": "string",
  "dnsimpleUserName": "string",
  "aliasOf": "string",
  "startDateUtc": "2018-10-02T04:10:23Z",
  "endDateUtc": "2018-10-02T04:10:23Z",
  "rootRedirectUrl": "string",
  "automaticallyGrantChildAccountAccess": true
}

```

*SupportedDomain*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|subjectAlternativeNames|[string]|false|none|none|
|owner|string|false|none|none|
|usersAllowedAccess|[string]|false|none|none|
|allowedDestinationDomains|[string]|false|none|none|
|letsencrypt|boolean|false|none|none|
|letsencryptMethod|string|false|none|none|
|dnsProvider|string|false|none|none|
|dnsimpleUserName|string|false|none|none|
|aliasOf|string|false|none|none|
|startDateUtc|string(date-time)|false|none|none|
|endDateUtc|string(date-time)|false|none|none|
|rootRedirectUrl|string|false|none|none|
|automaticallyGrantChildAccountAccess|boolean|false|none|none|

<h2 id="tocSdeletetrackingpixelresponse">DeleteTrackingPixelResponse</h2>

<a id="schemadeletetrackingpixelresponse"></a>

```json
{
  "success": true
}

```

*DeleteTrackingPixelResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|success|boolean|false|none|none|

<h2 id="tocSgettrackingpixelresponse">GetTrackingPixelResponse</h2>

<a id="schemagettrackingpixelresponse"></a>

```json
{
  "trackingPixel": {
    "typeString": "string",
    "displayName": "string",
    "renderAs": "string",
    "id": "string",
    "js": "string",
    "name": "string",
    "type": "string",
    "url": "string",
    "metadata": {
      "username": "string",
      "disabled": true,
      "updatedUtc": "2018-10-02T04:10:23Z",
      "createdUtc": "2018-10-02T04:10:23Z"
    },
    "params": {
      "property1": {},
      "property2": {}
    }
  }
}

```

*GetTrackingPixelResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|trackingPixel|[TrackingPixel](#schematrackingpixel)|false|none|TrackingPixel|

<h2 id="tocSupdatetrackingpixelresponse">UpdateTrackingPixelResponse</h2>

<a id="schemaupdatetrackingpixelresponse"></a>

```json
{
  "trackingPixel": {
    "typeString": "string",
    "displayName": "string",
    "renderAs": "string",
    "id": "string",
    "js": "string",
    "name": "string",
    "type": "string",
    "url": "string",
    "metadata": {
      "username": "string",
      "disabled": true,
      "updatedUtc": "2018-10-02T04:10:23Z",
      "createdUtc": "2018-10-02T04:10:23Z"
    },
    "params": {
      "property1": {},
      "property2": {}
    }
  }
}

```

*UpdateTrackingPixelResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|trackingPixel|[TrackingPixel](#schematrackingpixel)|false|none|TrackingPixel|

<h2 id="tocSaddapikeyresponse">AddApiKeyResponse</h2>

<a id="schemaaddapikeyresponse"></a>

```json
{
  "apiKey": {
    "userName": "string",
    "secret": "string",
    "key": "string",
    "notes": "string",
    "id": "string"
  }
}

```

*AddApiKeyResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|apiKey|[ApiKey](#schemaapikey)|false|none|ApiKey|

<h2 id="tocSapikey">ApiKey</h2>

<a id="schemaapikey"></a>

```json
{
  "userName": "string",
  "secret": "string",
  "key": "string",
  "notes": "string",
  "id": "string"
}

```

*ApiKey*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userName|string|false|none|none|
|secret|string|false|none|none|
|key|string|false|none|none|
|notes|string|false|none|none|
|id|string|false|none|none|

<h2 id="tocSdeleteapikeyresponse">DeleteApiKeyResponse</h2>

<a id="schemadeleteapikeyresponse"></a>

```json
{
  "success": true
}

```

*DeleteApiKeyResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|success|boolean|false|none|none|

<h2 id="tocSdomainallowedusersresponse">DomainAllowedUsersResponse</h2>

<a id="schemadomainallowedusersresponse"></a>

```json
{
  "usersAllowedAccess": [
    "string"
  ]
}

```

*DomainAllowedUsersResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|usersAllowedAccess|[string]|false|none|none|

<h2 id="tocSgroupmetadataresponse">GroupMetadataResponse</h2>

<a id="schemagroupmetadataresponse"></a>

```json
{
  "data": [
    {
      "name": "string",
      "description": "string",
      "userName": "string",
      "id": 0,
      "dateCreated": "2018-10-02T04:10:23Z",
      "noCreatedDateFlag": 0,
      "enabled": 0
    }
  ],
  "isMasterUser": true
}

```

*GroupMetadataResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[Group](#schemagroup)]|false|none|[Group]|
|isMasterUser|boolean|false|none|none|

<h2 id="tocSgroup">Group</h2>

<a id="schemagroup"></a>

```json
{
  "name": "string",
  "description": "string",
  "userName": "string",
  "id": 0,
  "dateCreated": "2018-10-02T04:10:23Z",
  "noCreatedDateFlag": 0,
  "enabled": 0
}

```

*Group*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|description|string|false|none|none|
|userName|string|false|none|none|
|id|integer(int32)|false|none|none|
|dateCreated|string(date-time)|false|none|none|
|noCreatedDateFlag|integer(int32)|false|none|none|
|enabled|integer(int32)|false|none|none|

<h2 id="tocSisconversiontrackingonforthisprogramresponse">IsConversionTrackingOnForThisProgramResponse</h2>

<a id="schemaisconversiontrackingonforthisprogramresponse"></a>

```json
{
  "isOn": true
}

```

*IsConversionTrackingOnForThisProgramResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isOn|boolean|false|none|none|

<h2 id="tocSshorturlmetadataresponse">ShorturlMetadataResponse</h2>

<a id="schemashorturlmetadataresponse"></a>

```json
{
  "data": [
    {
      "id": 0,
      "destinationUrl": "string",
      "shortUrlCode": "string",
      "domain": "string",
      "hasOverride": true,
      "productUrl": "string",
      "trackingCode": "string",
      "skipAffiliateRedirect": true,
      "createdUtc": "2018-10-02T04:10:23Z",
      "updatedUtc": "2018-10-02T04:10:23Z",
      "notes": "string",
      "createdUserTime": "2018-10-02T04:10:23Z",
      "updatedUserTime": "2018-10-02T04:10:23Z",
      "tsid": 0,
      "group": "string",
      "username": "string",
      "jsonMetadata": "string",
      "jsonItemMetadata": "string",
      "jsonPostProcessingRules": "string",
      "jsonOverrides": "string",
      "totalClicks": 0,
      "advertiser": "string",
      "advertiserId": 0,
      "percentChangePeriodOverPeriod": 0,
      "previousPeriodTotalClicks": 0,
      "isArchived": 0,
      "isArchivedInt": 0,
      "productDisplayName1": "string",
      "productDisplayName2": "string",
      "productDisplayName3": "string",
      "productArtworkThumbnailUrl": "string",
      "productArtworkThumbnailUrl100": "string",
      "advertiserIcon": "string",
      "advertiserIconCssClass": "string",
      "isGenius": true,
      "advertiserIconTitle": "string",
      "trackingPixelIds": "string",
      "applePreference": 0,
      "productArtworkThumbnailUrl150": "string",
      "aliases": [
        {
          "baseCode": "string",
          "code": "string",
          "domain": "string",
          "lastUpdatedUtc": "2018-10-02T04:10:23Z"
        }
      ],
      "linkCreatorSetting": "string"
    }
  ],
  "isMasterUser": true
}

```

*ShorturlMetadataResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[UserShortLink](#schemausershortlink)]|false|none|[UserShortLink]|
|isMasterUser|boolean|false|none|none|

<h2 id="tocSusershortlink">UserShortLink</h2>

<a id="schemausershortlink"></a>

```json
{
  "id": 0,
  "destinationUrl": "string",
  "shortUrlCode": "string",
  "domain": "string",
  "hasOverride": true,
  "productUrl": "string",
  "trackingCode": "string",
  "skipAffiliateRedirect": true,
  "createdUtc": "2018-10-02T04:10:23Z",
  "updatedUtc": "2018-10-02T04:10:23Z",
  "notes": "string",
  "createdUserTime": "2018-10-02T04:10:23Z",
  "updatedUserTime": "2018-10-02T04:10:23Z",
  "tsid": 0,
  "group": "string",
  "username": "string",
  "jsonMetadata": "string",
  "jsonItemMetadata": "string",
  "jsonPostProcessingRules": "string",
  "jsonOverrides": "string",
  "totalClicks": 0,
  "advertiser": "string",
  "advertiserId": 0,
  "percentChangePeriodOverPeriod": 0,
  "previousPeriodTotalClicks": 0,
  "isArchived": 0,
  "isArchivedInt": 0,
  "productDisplayName1": "string",
  "productDisplayName2": "string",
  "productDisplayName3": "string",
  "productArtworkThumbnailUrl": "string",
  "productArtworkThumbnailUrl100": "string",
  "advertiserIcon": "string",
  "advertiserIconCssClass": "string",
  "isGenius": true,
  "advertiserIconTitle": "string",
  "trackingPixelIds": "string",
  "applePreference": 0,
  "productArtworkThumbnailUrl150": "string",
  "aliases": [
    {
      "baseCode": "string",
      "code": "string",
      "domain": "string",
      "lastUpdatedUtc": "2018-10-02T04:10:23Z"
    }
  ],
  "linkCreatorSetting": "string"
}

```

*UserShortLink*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|destinationUrl|string|false|none|none|
|shortUrlCode|string|false|none|none|
|domain|string|false|none|none|
|hasOverride|boolean|false|none|none|
|productUrl|string|false|none|none|
|trackingCode|string|false|none|none|
|skipAffiliateRedirect|boolean|false|none|none|
|createdUtc|string(date-time)|false|none|none|
|updatedUtc|string(date-time)|false|none|none|
|notes|string|false|none|none|
|createdUserTime|string(date-time)|false|none|none|
|updatedUserTime|string(date-time)|false|none|none|
|tsid|integer(int32)|false|none|none|
|group|string|false|none|none|
|username|string|false|none|none|
|jsonMetadata|string|false|none|none|
|jsonItemMetadata|string|false|none|none|
|jsonPostProcessingRules|string|false|none|none|
|jsonOverrides|string|false|none|none|
|totalClicks|number(double)|false|none|none|
|advertiser|string|false|none|none|
|advertiserId|integer(int32)|false|none|none|
|percentChangePeriodOverPeriod|number(double)|false|none|none|
|previousPeriodTotalClicks|number(double)|false|none|none|
|isArchived|integer(int32)|false|none|none|
|isArchivedInt|integer(int32)|false|none|none|
|productDisplayName1|string|false|none|none|
|productDisplayName2|string|false|none|none|
|productDisplayName3|string|false|none|none|
|productArtworkThumbnailUrl|string|false|none|none|
|productArtworkThumbnailUrl100|string|false|none|none|
|advertiserIcon|string|false|none|none|
|advertiserIconCssClass|string|false|none|none|
|isGenius|boolean|false|none|none|
|advertiserIconTitle|string|false|none|none|
|trackingPixelIds|string|false|none|none|
|applePreference|integer(int32)|false|none|none|
|productArtworkThumbnailUrl150|string|false|none|none|
|aliases|[[ShortUrlAlias](#schemashorturlalias)]|false|none|[ShortUrlAlias]|
|linkCreatorSetting|string|false|none|none|

<h2 id="tocSshorturlalias">ShortUrlAlias</h2>

<a id="schemashorturlalias"></a>

```json
{
  "baseCode": "string",
  "code": "string",
  "domain": "string",
  "lastUpdatedUtc": "2018-10-02T04:10:23Z"
}

```

*ShortUrlAlias*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|baseCode|string|false|none|none|
|code|string|false|none|none|
|domain|string|false|none|none|
|lastUpdatedUtc|string(date-time)|false|none|none|

<h2 id="tocSinvoiceresponse">InvoiceResponse</h2>

<a id="schemainvoiceresponse"></a>

```json
{
  "invoices": [
    {
      "id": "string",
      "invoiceDate": "2018-10-02T04:10:23Z",
      "createdUtc": "2018-10-02T04:10:23Z",
      "netPaymentTerms": 0,
      "periodStartUtc": "2018-10-02T04:10:23Z",
      "periodEndUtc": "2018-10-02T04:10:23Z",
      "paymentDueUtc": "2018-10-02T04:10:23Z",
      "trialPeriodStartUtc": "2018-10-02T04:10:23Z",
      "trialPeriodEndUtc": "2018-10-02T04:10:23Z",
      "lineItems": [
        {
          "notes": "string",
          "quantity": 0,
          "quantityUnit": "string",
          "rateUnit": "string",
          "amount": 0,
          "type": "string",
          "name": "string",
          "rate": 0
        }
      ],
      "details": {
        "property1": {},
        "property2": {}
      },
      "amount": 0,
      "amountDue": 0,
      "currency": "string",
      "status": "string",
      "forgiven": true,
      "username": "string",
      "statusChanges": [
        {
          "changedUtc": "2018-10-02T04:10:23Z",
          "newStatus": "string"
        }
      ],
      "paymentId": "string",
      "paymentIds": [
        "string"
      ],
      "planName": "string",
      "hasUserDetails": true
    }
  ],
  "page": {
    "totalPages": 0,
    "pages": [
      {
        "previous": 0,
        "next": 0,
        "page": [
          {
            "id": "string",
            "invoiceDate": "2018-10-02T04:10:23Z",
            "createdUtc": "2018-10-02T04:10:23Z",
            "netPaymentTerms": 0,
            "periodStartUtc": "2018-10-02T04:10:23Z",
            "periodEndUtc": "2018-10-02T04:10:23Z",
            "paymentDueUtc": "2018-10-02T04:10:23Z",
            "trialPeriodStartUtc": "2018-10-02T04:10:23Z",
            "trialPeriodEndUtc": "2018-10-02T04:10:23Z",
            "lineItems": [
              {
                "notes": "string",
                "quantity": 0,
                "quantityUnit": "string",
                "rateUnit": "string",
                "amount": 0,
                "type": "string",
                "name": "string",
                "rate": 0
              }
            ],
            "details": {
              "property1": {},
              "property2": {}
            },
            "amount": 0,
            "amountDue": 0,
            "currency": "string",
            "status": "string",
            "forgiven": true,
            "username": "string",
            "statusChanges": [
              {
                "changedUtc": "2018-10-02T04:10:23Z",
                "newStatus": "string"
              }
            ],
            "paymentId": "string",
            "paymentIds": [
              "string"
            ],
            "planName": "string",
            "hasUserDetails": true
          }
        ]
      }
    ],
    "activePage": {
      "previous": 0,
      "next": 0,
      "page": [
        {
          "id": "string",
          "invoiceDate": "2018-10-02T04:10:23Z",
          "createdUtc": "2018-10-02T04:10:23Z",
          "netPaymentTerms": 0,
          "periodStartUtc": "2018-10-02T04:10:23Z",
          "periodEndUtc": "2018-10-02T04:10:23Z",
          "paymentDueUtc": "2018-10-02T04:10:23Z",
          "trialPeriodStartUtc": "2018-10-02T04:10:23Z",
          "trialPeriodEndUtc": "2018-10-02T04:10:23Z",
          "lineItems": [
            {
              "notes": "string",
              "quantity": 0,
              "quantityUnit": "string",
              "rateUnit": "string",
              "amount": 0,
              "type": "string",
              "name": "string",
              "rate": 0
            }
          ],
          "details": {
            "property1": {},
            "property2": {}
          },
          "amount": 0,
          "amountDue": 0,
          "currency": "string",
          "status": "string",
          "forgiven": true,
          "username": "string",
          "statusChanges": [
            {
              "changedUtc": "2018-10-02T04:10:23Z",
              "newStatus": "string"
            }
          ],
          "paymentId": "string",
          "paymentIds": [
            "string"
          ],
          "planName": "string",
          "hasUserDetails": true
        }
      ]
    }
  }
}

```

*InvoiceResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|invoices|[[Invoice](#schemainvoice)]|false|none|[Invoice]|
|page|[SpfResponse_Invoice_](#schemaspfresponse_invoice_)|false|none|SpfResponse<Invoice>|

<h2 id="tocSinvoice">Invoice</h2>

<a id="schemainvoice"></a>

```json
{
  "id": "string",
  "invoiceDate": "2018-10-02T04:10:23Z",
  "createdUtc": "2018-10-02T04:10:23Z",
  "netPaymentTerms": 0,
  "periodStartUtc": "2018-10-02T04:10:23Z",
  "periodEndUtc": "2018-10-02T04:10:23Z",
  "paymentDueUtc": "2018-10-02T04:10:23Z",
  "trialPeriodStartUtc": "2018-10-02T04:10:23Z",
  "trialPeriodEndUtc": "2018-10-02T04:10:23Z",
  "lineItems": [
    {
      "notes": "string",
      "quantity": 0,
      "quantityUnit": "string",
      "rateUnit": "string",
      "amount": 0,
      "type": "string",
      "name": "string",
      "rate": 0
    }
  ],
  "details": {
    "property1": {},
    "property2": {}
  },
  "amount": 0,
  "amountDue": 0,
  "currency": "string",
  "status": "string",
  "forgiven": true,
  "username": "string",
  "statusChanges": [
    {
      "changedUtc": "2018-10-02T04:10:23Z",
      "newStatus": "string"
    }
  ],
  "paymentId": "string",
  "paymentIds": [
    "string"
  ],
  "planName": "string",
  "hasUserDetails": true
}

```

*Invoice*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|invoiceDate|string(date-time)|false|none|none|
|createdUtc|string(date-time)|false|none|none|
|netPaymentTerms|integer(int32)|false|none|none|
|periodStartUtc|string(date-time)|false|none|none|
|periodEndUtc|string(date-time)|false|none|none|
|paymentDueUtc|string(date-time)|false|none|none|
|trialPeriodStartUtc|string(date-time)|false|none|none|
|trialPeriodEndUtc|string(date-time)|false|none|none|
|lineItems|[[InvoiceLineItem](#schemainvoicelineitem)]|false|none|[InvoiceLineItem]|
|details|[Dictionary_String_InvoiceDetail_](#schemadictionary_string_invoicedetail_)|false|none|Dictionary<String,InvoiceDetail>|
|amount|integer(int32)|false|none|none|
|amountDue|integer(int32)|false|none|none|
|currency|string|false|none|none|
|status|string|false|none|none|
|forgiven|boolean|false|none|none|
|username|string|false|none|none|
|statusChanges|[[InvoiceStatusChange](#schemainvoicestatuschange)]|false|none|[InvoiceStatusChange]|
|paymentId|string|false|none|none|
|paymentIds|[string]|false|none|none|
|planName|string|false|none|none|
|hasUserDetails|boolean|false|none|none|

<h2 id="tocSinvoicelineitem">InvoiceLineItem</h2>

<a id="schemainvoicelineitem"></a>

```json
{
  "notes": "string",
  "quantity": 0,
  "quantityUnit": "string",
  "rateUnit": "string",
  "amount": 0,
  "type": "string",
  "name": "string",
  "rate": 0
}

```

*InvoiceLineItem*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|notes|string|false|none|none|
|quantity|number(double)|false|none|none|
|quantityUnit|string|false|none|none|
|rateUnit|string|false|none|none|
|amount|integer(int32)|false|none|none|
|type|string|false|none|none|
|name|string|false|none|none|
|rate|integer(int32)|false|none|none|

<h2 id="tocSinvoicedetail">InvoiceDetail</h2>

<a id="schemainvoicedetail"></a>

```json
{}

```

*InvoiceDetail*

### Properties

*None*

<h2 id="tocSinvoicestatuschange">InvoiceStatusChange</h2>

<a id="schemainvoicestatuschange"></a>

```json
{
  "changedUtc": "2018-10-02T04:10:23Z",
  "newStatus": "string"
}

```

*InvoiceStatusChange*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|changedUtc|string(date-time)|false|none|none|
|newStatus|string|false|none|none|

<h2 id="tocSpaymentsresponse">PaymentsResponse</h2>

<a id="schemapaymentsresponse"></a>

```json
{
  "payments": [
    {
      "id": "string",
      "createdUtc": "2018-10-02T04:10:23Z",
      "username": "string",
      "amount": 0,
      "currency": "string",
      "status": "string",
      "type": "string",
      "notes": "string",
      "receiptNumber": "string",
      "failureReason": "string",
      "declineCode": "string",
      "invoiceIds": [
        "string"
      ]
    }
  ]
}

```

*PaymentsResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payments|[[Payment](#schemapayment)]|false|none|[Payment]|

<h2 id="tocSpayment">Payment</h2>

<a id="schemapayment"></a>

```json
{
  "id": "string",
  "createdUtc": "2018-10-02T04:10:23Z",
  "username": "string",
  "amount": 0,
  "currency": "string",
  "status": "string",
  "type": "string",
  "notes": "string",
  "receiptNumber": "string",
  "failureReason": "string",
  "declineCode": "string",
  "invoiceIds": [
    "string"
  ]
}

```

*Payment*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|createdUtc|string(date-time)|false|none|none|
|username|string|false|none|none|
|amount|integer(int32)|false|none|none|
|currency|string|false|none|none|
|status|string|false|none|none|
|type|string|false|none|none|
|notes|string|false|none|none|
|receiptNumber|string|false|none|none|
|failureReason|string|false|none|none|
|declineCode|string|false|none|none|
|invoiceIds|[string]|false|none|none|

<h2 id="tocSreportingwizardresponse">ReportingWizardResponse</h2>

<a id="schemareportingwizardresponse"></a>

```json
{
  "sortBy": "string",
  "data": [
    {
      "header": "string",
      "dataWithBots": [
        {
          "clicks": 0,
          "clientAffiliated": 0,
          "conv": 0,
          "earnings": 0,
          "epc": 0,
          "group": "string",
          "name": "string",
          "overflow": 0,
          "sharedActive": 0,
          "sharedPassive": 0,
          "user": "string"
        }
      ],
      "dataWithoutBots": [
        {
          "clicks": 0,
          "clientAffiliated": 0,
          "conv": 0,
          "earnings": 0,
          "epc": 0,
          "group": "string",
          "name": "string",
          "overflow": 0,
          "sharedActive": 0,
          "sharedPassive": 0,
          "user": "string"
        }
      ],
      "totalRows": 0,
      "totalPages": 0
    }
  ],
  "bigHeaderTabs": [
    {
      "name": "string",
      "active": true,
      "attribute": "string"
    }
  ],
  "subMenuHeaderTabs": [
    {
      "name": "string",
      "active": true,
      "attribute": "string"
    }
  ]
}

```

*ReportingWizardResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sortBy|string|false|none|none|
|data|[[ReportDataTable](#schemareportdatatable)]|false|none|[ReportDataTable]|
|bigHeaderTabs|[[TableHeaderTab](#schematableheadertab)]|false|none|[TableHeaderTab]|
|subMenuHeaderTabs|[[TableHeaderTab](#schematableheadertab)]|false|none|[TableHeaderTab]|

<h2 id="tocSreportdatatable">ReportDataTable</h2>

<a id="schemareportdatatable"></a>

```json
{
  "header": "string",
  "dataWithBots": [
    {
      "clicks": 0,
      "clientAffiliated": 0,
      "conv": 0,
      "earnings": 0,
      "epc": 0,
      "group": "string",
      "name": "string",
      "overflow": 0,
      "sharedActive": 0,
      "sharedPassive": 0,
      "user": "string"
    }
  ],
  "dataWithoutBots": [
    {
      "clicks": 0,
      "clientAffiliated": 0,
      "conv": 0,
      "earnings": 0,
      "epc": 0,
      "group": "string",
      "name": "string",
      "overflow": 0,
      "sharedActive": 0,
      "sharedPassive": 0,
      "user": "string"
    }
  ],
  "totalRows": 0,
  "totalPages": 0
}

```

*ReportDataTable*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|header|string|false|none|none|
|dataWithBots|[[SummaryDataRow](#schemasummarydatarow)]|false|none|[SummaryDataRow]|
|dataWithoutBots|[[SummaryDataRow](#schemasummarydatarow)]|false|none|[SummaryDataRow]|
|totalRows|integer(int32)|false|none|none|
|totalPages|integer(int32)|false|none|none|

<h2 id="tocStableheadertab">TableHeaderTab</h2>

<a id="schematableheadertab"></a>

```json
{
  "name": "string",
  "active": true,
  "attribute": "string"
}

```

*TableHeaderTab*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|active|boolean|false|none|none|
|attribute|string|false|none|none|

<h2 id="tocStrackingpixelresponse">TrackingPixelResponse</h2>

<a id="schematrackingpixelresponse"></a>

```json
{
  "trackingPixels": [
    {
      "typeString": "string",
      "displayName": "string",
      "renderAs": "string",
      "id": "string",
      "js": "string",
      "name": "string",
      "type": "string",
      "url": "string",
      "metadata": {
        "username": "string",
        "disabled": true,
        "updatedUtc": "2018-10-02T04:10:23Z",
        "createdUtc": "2018-10-02T04:10:23Z"
      },
      "params": {
        "property1": {},
        "property2": {}
      }
    }
  ]
}

```

*TrackingPixelResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|trackingPixels|[[TrackingPixel](#schematrackingpixel)]|false|none|[TrackingPixel]|

<h2 id="tocSsupporteddomainsresponse">SupportedDomainsResponse</h2>

<a id="schemasupporteddomainsresponse"></a>

```json
{
  "domains": [
    {
      "name": "string",
      "subjectAlternativeNames": [
        "string"
      ],
      "owner": "string",
      "usersAllowedAccess": [
        "string"
      ],
      "allowedDestinationDomains": [
        "string"
      ],
      "letsencrypt": true,
      "letsencryptMethod": "string",
      "dnsProvider": "string",
      "dnsimpleUserName": "string",
      "aliasOf": "string",
      "startDateUtc": "2018-10-02T04:10:23Z",
      "endDateUtc": "2018-10-02T04:10:23Z",
      "rootRedirectUrl": "string",
      "automaticallyGrantChildAccountAccess": true
    }
  ]
}

```

*SupportedDomainsResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|domains|[[SupportedDomain](#schemasupporteddomain)]|false|none|[SupportedDomain]|

<h2 id="tocSbulkaddshortlinkresponse">BulkAddShortLinkResponse</h2>

<a id="schemabulkaddshortlinkresponse"></a>

```json
{
  "linkResponses": [
    {
      "isError": {
        "errorMessage": "string",
        "errorTitle": "string"
      },
      "errorMessage": "string",
      "code": "string",
      "newLink": {
        "id": 0,
        "destinationUrl": "string",
        "shortUrlCode": "string",
        "domain": "string",
        "hasOverride": true,
        "productUrl": "string",
        "trackingCode": "string",
        "skipAffiliateRedirect": true,
        "createdUtc": "2018-10-02T04:10:23Z",
        "updatedUtc": "2018-10-02T04:10:23Z",
        "notes": "string",
        "createdUserTime": "2018-10-02T04:10:23Z",
        "updatedUserTime": "2018-10-02T04:10:23Z",
        "tsid": 0,
        "group": "string",
        "username": "string",
        "jsonMetadata": "string",
        "jsonItemMetadata": "string",
        "jsonPostProcessingRules": "string",
        "jsonOverrides": "string",
        "totalClicks": 0,
        "advertiser": "string",
        "advertiserId": 0,
        "percentChangePeriodOverPeriod": 0,
        "previousPeriodTotalClicks": 0,
        "isArchived": 0,
        "isArchivedInt": 0,
        "productDisplayName1": "string",
        "productDisplayName2": "string",
        "productDisplayName3": "string",
        "productArtworkThumbnailUrl": "string",
        "productArtworkThumbnailUrl100": "string",
        "advertiserIcon": "string",
        "advertiserIconCssClass": "string",
        "isGenius": true,
        "advertiserIconTitle": "string",
        "trackingPixelIds": "string",
        "applePreference": 0,
        "productArtworkThumbnailUrl150": "string",
        "aliases": [
          {
            "baseCode": "string",
            "code": "string",
            "domain": "string",
            "lastUpdatedUtc": "2018-10-02T04:10:23Z"
          }
        ],
        "linkCreatorSetting": "string"
      },
      "itunesMetadataJsonUrl": "string",
      "itemMetadataJson": "string"
    }
  ],
  "request": {
    "url": "string",
    "tsid": 0,
    "trackingCode": "string",
    "skipAffiliateRedirect": 0,
    "vanityCode": "string",
    "placeholderCode": "string",
    "bulkMode": 0,
    "overrides": "string",
    "domain": "string",
    "note": "string",
    "trackingPixels": "string",
    "applePreference": 0,
    "linkCreatorSetting": "string"
  }
}

```

*BulkAddShortLinkResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|linkResponses|[[AddNewLinkResponse](#schemaaddnewlinkresponse)]|false|none|[AddNewLinkResponse]|
|request|[AddNewLinkRequest](#schemaaddnewlinkrequest)|false|none|Save a new short link|

<h2 id="tocSaddnewlinkresponse">AddNewLinkResponse</h2>

<a id="schemaaddnewlinkresponse"></a>

```json
{
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "errorMessage": "string",
  "code": "string",
  "newLink": {
    "id": 0,
    "destinationUrl": "string",
    "shortUrlCode": "string",
    "domain": "string",
    "hasOverride": true,
    "productUrl": "string",
    "trackingCode": "string",
    "skipAffiliateRedirect": true,
    "createdUtc": "2018-10-02T04:10:23Z",
    "updatedUtc": "2018-10-02T04:10:23Z",
    "notes": "string",
    "createdUserTime": "2018-10-02T04:10:23Z",
    "updatedUserTime": "2018-10-02T04:10:23Z",
    "tsid": 0,
    "group": "string",
    "username": "string",
    "jsonMetadata": "string",
    "jsonItemMetadata": "string",
    "jsonPostProcessingRules": "string",
    "jsonOverrides": "string",
    "totalClicks": 0,
    "advertiser": "string",
    "advertiserId": 0,
    "percentChangePeriodOverPeriod": 0,
    "previousPeriodTotalClicks": 0,
    "isArchived": 0,
    "isArchivedInt": 0,
    "productDisplayName1": "string",
    "productDisplayName2": "string",
    "productDisplayName3": "string",
    "productArtworkThumbnailUrl": "string",
    "productArtworkThumbnailUrl100": "string",
    "advertiserIcon": "string",
    "advertiserIconCssClass": "string",
    "isGenius": true,
    "advertiserIconTitle": "string",
    "trackingPixelIds": "string",
    "applePreference": 0,
    "productArtworkThumbnailUrl150": "string",
    "aliases": [
      {
        "baseCode": "string",
        "code": "string",
        "domain": "string",
        "lastUpdatedUtc": "2018-10-02T04:10:23Z"
      }
    ],
    "linkCreatorSetting": "string"
  },
  "itunesMetadataJsonUrl": "string",
  "itemMetadataJson": "string"
}

```

*AddNewLinkResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isError|[Result](#schemaresult)|false|none|Result|
|errorMessage|string|false|none|none|
|code|string|false|none|none|
|newLink|[UserShortLink](#schemausershortlink)|false|none|UserShortLink|
|itunesMetadataJsonUrl|string|false|none|none|
|itemMetadataJson|string|false|none|none|

<h2 id="tocSaddnewgroupwithnotesresponse">AddNewGroupWithNotesResponse</h2>

<a id="schemaaddnewgroupwithnotesresponse"></a>

```json
{
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "newGroupId": 0,
  "now": "2018-10-02T04:10:23Z",
  "request": {
    "groupName": "string",
    "notes": "string",
    "id": "string"
  }
}

```

*AddNewGroupWithNotesResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isError|[Result](#schemaresult)|false|none|Result|
|newGroupId|integer(int32)|false|none|none|
|now|string(date-time)|false|none|none|
|request|[AddNewGroupWithNotesRequest](#schemaaddnewgroupwithnotesrequest)|false|none|AddNewGroupWithNotesRequest|

<h2 id="tocSlinkclicksbycountryresponse">LinkClicksByCountryResponse</h2>

<a id="schemalinkclicksbycountryresponse"></a>

```json
{
  "countryNameWithClicksTopItems": [
    {
      "Key": {
        "iso2": "string",
        "name": "string"
      },
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "countryNameWithCommTopItems": [
    {
      "Key": {
        "iso2": "string",
        "name": "string"
      },
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "countryNameWithConvTopItems": [
    {
      "Key": {
        "iso2": "string",
        "name": "string"
      },
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "countryNameWithEpcTopItems": [
    {
      "Key": {
        "iso2": "string",
        "name": "string"
      },
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "iso2WithClicks": [
    {
      "Key": "string",
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "request": {
    "shortCode": "string",
    "start": null,
    "end": null,
    "advertiserId": 0,
    "doPreviousPeriod": 0,
    "dataResolution": "hour"
  }
}

```

*LinkClicksByCountryResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|countryNameWithClicksTopItems|[[KeyValuePair_CountryDescription_BasicStats_](#schemakeyvaluepair_countrydescription_basicstats_)]|false|none|[KeyValuePair<CountryDescription,BasicStats>]|
|countryNameWithCommTopItems|[[KeyValuePair_CountryDescription_BasicStats_](#schemakeyvaluepair_countrydescription_basicstats_)]|false|none|[KeyValuePair<CountryDescription,BasicStats>]|
|countryNameWithConvTopItems|[[KeyValuePair_CountryDescription_BasicStats_](#schemakeyvaluepair_countrydescription_basicstats_)]|false|none|[KeyValuePair<CountryDescription,BasicStats>]|
|countryNameWithEpcTopItems|[[KeyValuePair_CountryDescription_BasicStats_](#schemakeyvaluepair_countrydescription_basicstats_)]|false|none|[KeyValuePair<CountryDescription,BasicStats>]|
|iso2WithClicks|[[KeyValuePair_String_BasicStats_](#schemakeyvaluepair_string_basicstats_)]|false|none|[KeyValuePair<String,BasicStats>]|
|request|[LinkClicksByCountryRequest](#schemalinkclicksbycountryrequest)|false|none|LinkClicksByCountryRequest|

<h2 id="tocScountrydescription">CountryDescription</h2>

<a id="schemacountrydescription"></a>

```json
{
  "iso2": "string",
  "name": "string"
}

```

*CountryDescription*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|iso2|string|false|none|none|
|name|string|false|none|none|

<h2 id="tocSbasicstats">BasicStats</h2>

<a id="schemabasicstats"></a>

```json
{
  "clicks": 0,
  "clicksMinusBot": 0,
  "clicksMinusSharedAndBot": 0,
  "baseClicks": 0,
  "activeShare": 0,
  "passiveShare": 0,
  "clientAffiliated": 0,
  "spider": 0,
  "overflow": 0,
  "advancedTargeting": 0,
  "trackingPixel": 0,
  "translated": 0,
  "sharedTranslated": 0,
  "sharedAffiliated": 0,
  "previousPeriod": null,
  "currencyForConsolidated": "string",
  "commissionForConsolidated": 0,
  "valueForConsolidated": 0,
  "itemsForConsolidated": 0,
  "epcNoBots": 0,
  "epcWithBots": 0,
  "convForConsolidated": 0,
  "convPercent": 0,
  "attributeValue": "string",
  "date": "2018-10-02T04:10:23Z",
  "prefetch": 0,
  "duplicates": 0,
  "junkTraffic": 0
}

```

*BasicStats*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|clicks|integer(int64)|false|none|none|
|clicksMinusBot|integer(int64)|false|none|none|
|clicksMinusSharedAndBot|integer(int64)|false|none|none|
|baseClicks|integer(int64)|false|none|none|
|activeShare|integer(int64)|false|none|none|
|passiveShare|integer(int64)|false|none|none|
|clientAffiliated|integer(int64)|false|none|none|
|spider|integer(int64)|false|none|none|
|overflow|integer(int64)|false|none|none|
|advancedTargeting|integer(int32)|false|none|none|
|trackingPixel|integer(int32)|false|none|none|
|translated|integer(int64)|false|none|none|
|sharedTranslated|integer(int64)|false|none|none|
|sharedAffiliated|integer(int64)|false|none|none|
|previousPeriod|[BasicStats](#schemabasicstats)|false|none|BasicStats|
|currencyForConsolidated|string|false|none|none|
|commissionForConsolidated|number(double)|false|none|none|
|valueForConsolidated|number(double)|false|none|none|
|itemsForConsolidated|integer(int64)|false|none|none|
|epcNoBots|number(double)|false|none|none|
|epcWithBots|number(double)|false|none|none|
|convForConsolidated|number(double)|false|none|none|
|convPercent|number(double)|false|none|none|
|attributeValue|string|false|none|none|
|date|string(date-time)|false|none|none|
|prefetch|integer(int64)|false|none|none|
|duplicates|integer(int64)|false|none|none|
|junkTraffic|integer(int64)|false|none|none|

<h2 id="tocSuserclicksbycountryresponse">UserClicksByCountryResponse</h2>

<a id="schemauserclicksbycountryresponse"></a>

```json
{
  "countryNameWithClicksTopItems": [
    {
      "Key": {
        "iso2": "string",
        "name": "string"
      },
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "countryNameWithCommTopItems": [
    {
      "Key": {
        "iso2": "string",
        "name": "string"
      },
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "countryNameWithConvTopItems": [
    {
      "Key": {
        "iso2": "string",
        "name": "string"
      },
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "countryNameWithEpcTopItems": [
    {
      "Key": {
        "iso2": "string",
        "name": "string"
      },
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "iso2WithClicks": [
    {
      "Key": "string",
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "request": {
    "start": null,
    "end": null,
    "advertiserId": 0,
    "doPreviousPeriod": 0,
    "dataResolution": "hour"
  }
}

```

*UserClicksByCountryResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|countryNameWithClicksTopItems|[[KeyValuePair_CountryDescription_BasicStats_](#schemakeyvaluepair_countrydescription_basicstats_)]|false|none|[KeyValuePair<CountryDescription,BasicStats>]|
|countryNameWithCommTopItems|[[KeyValuePair_CountryDescription_BasicStats_](#schemakeyvaluepair_countrydescription_basicstats_)]|false|none|[KeyValuePair<CountryDescription,BasicStats>]|
|countryNameWithConvTopItems|[[KeyValuePair_CountryDescription_BasicStats_](#schemakeyvaluepair_countrydescription_basicstats_)]|false|none|[KeyValuePair<CountryDescription,BasicStats>]|
|countryNameWithEpcTopItems|[[KeyValuePair_CountryDescription_BasicStats_](#schemakeyvaluepair_countrydescription_basicstats_)]|false|none|[KeyValuePair<CountryDescription,BasicStats>]|
|iso2WithClicks|[[KeyValuePair_String_BasicStats_](#schemakeyvaluepair_string_basicstats_)]|false|none|[KeyValuePair<String,BasicStats>]|
|request|[ClicksByCountryRequest](#schemaclicksbycountryrequest)|false|none|GET total clicks by country for range and advertiser|

<h2 id="tocSinvoicebuilderresponse">InvoiceBuilderResponse</h2>

<a id="schemainvoicebuilderresponse"></a>

```json
{
  "invoice": {
    "id": "string",
    "invoiceDate": "2018-10-02T04:10:23Z",
    "createdUtc": "2018-10-02T04:10:23Z",
    "netPaymentTerms": 0,
    "periodStartUtc": "2018-10-02T04:10:23Z",
    "periodEndUtc": "2018-10-02T04:10:23Z",
    "paymentDueUtc": "2018-10-02T04:10:23Z",
    "trialPeriodStartUtc": "2018-10-02T04:10:23Z",
    "trialPeriodEndUtc": "2018-10-02T04:10:23Z",
    "lineItems": [
      {
        "notes": "string",
        "quantity": 0,
        "quantityUnit": "string",
        "rateUnit": "string",
        "amount": 0,
        "type": "string",
        "name": "string",
        "rate": 0
      }
    ],
    "details": {
      "property1": {},
      "property2": {}
    },
    "amount": 0,
    "amountDue": 0,
    "currency": "string",
    "status": "string",
    "forgiven": true,
    "username": "string",
    "statusChanges": [
      {
        "changedUtc": "2018-10-02T04:10:23Z",
        "newStatus": "string"
      }
    ],
    "paymentId": "string",
    "paymentIds": [
      "string"
    ],
    "planName": "string",
    "hasUserDetails": true
  }
}

```

*InvoiceBuilderResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|invoice|[Invoice](#schemainvoice)|false|none|Invoice|

<h2 id="tocSgetaffiliateprogramsperuserresponse">GetAffiliateProgramsPerUserResponse</h2>

<a id="schemagetaffiliateprogramsperuserresponse"></a>

```json
{
  "totalProgramsAvailable": 0,
  "availablePrograms": [
    "string"
  ],
  "totalProgramsEnrolled": 0,
  "programsEnrolled": [
    "string"
  ],
  "programsMissingToEnroll": [
    "string"
  ]
}

```

*GetAffiliateProgramsPerUserResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalProgramsAvailable|integer(int32)|false|none|none|
|availablePrograms|[string]|false|none|none|
|totalProgramsEnrolled|integer(int32)|false|none|none|
|programsEnrolled|[string]|false|none|none|
|programsMissingToEnroll|[string]|false|none|none|

<h2 id="tocSallgroupsresponse">AllGroupsResponse</h2>

<a id="schemaallgroupsresponse"></a>

```json
{
  "groups": [
    {
      "name": "string",
      "description": "string",
      "userName": "string",
      "id": 0,
      "dateCreated": "2018-10-02T04:10:23Z",
      "noCreatedDateFlag": 0,
      "enabled": 0
    }
  ],
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "request": {}
}

```

*AllGroupsResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|groups|[[Group](#schemagroup)]|false|none|[Group]|
|isError|[Result](#schemaresult)|false|none|Result|
|request|[AllGroupsRequest](#schemaallgroupsrequest)|false|none|GET the top traffic sources for the given parameters|

<h2 id="tocSallgroupswithdetailsresponse">AllGroupsWithDetailsResponse</h2>

<a id="schemaallgroupswithdetailsresponse"></a>

```json
{
  "groups": [
    {
      "totalClicks": 0,
      "totalCountries": 0,
      "totalClicksPreviousPeriod": 0,
      "percentChangePoP": 0,
      "totalShortLinks": 0,
      "totalOverrides": 0,
      "name": "string",
      "description": "string",
      "userName": "string",
      "id": 0,
      "dateCreated": "2018-10-02T04:10:23Z",
      "noCreatedDateFlag": 0,
      "enabled": 0
    }
  ],
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "request": {}
}

```

*AllGroupsWithDetailsResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|groups|[[GroupWithDetails](#schemagroupwithdetails)]|false|none|[GroupWithDetails]|
|isError|[Result](#schemaresult)|false|none|Result|
|request|[AllGroupsWithDetailsRequest](#schemaallgroupswithdetailsrequest)|false|none|GET the top traffic sources for the given parameters, including details about number of links, etc.|

<h2 id="tocSgroupwithdetails">GroupWithDetails</h2>

<a id="schemagroupwithdetails"></a>

```json
{
  "totalClicks": 0,
  "totalCountries": 0,
  "totalClicksPreviousPeriod": 0,
  "percentChangePoP": 0,
  "totalShortLinks": 0,
  "totalOverrides": 0,
  "name": "string",
  "description": "string",
  "userName": "string",
  "id": 0,
  "dateCreated": "2018-10-02T04:10:23Z",
  "noCreatedDateFlag": 0,
  "enabled": 0
}

```

*GroupWithDetails*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalClicks|number(double)|false|none|none|
|totalCountries|number(double)|false|none|none|
|totalClicksPreviousPeriod|number(double)|false|none|none|
|percentChangePoP|number(double)|false|none|none|
|totalShortLinks|integer(int32)|false|none|none|
|totalOverrides|integer(int32)|false|none|none|
|name|string|false|none|none|
|description|string|false|none|none|
|userName|string|false|none|none|
|id|integer(int32)|false|none|none|
|dateCreated|string(date-time)|false|none|none|
|noCreatedDateFlag|integer(int32)|false|none|none|
|enabled|integer(int32)|false|none|none|

<h2 id="tocSarchiveagroupresponse">ArchiveAGroupResponse</h2>

<a id="schemaarchiveagroupresponse"></a>

```json
{
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "request": {
    "ids": "string",
    "restoreFlag": null
  }
}

```

*ArchiveAGroupResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isError|[Result](#schemaresult)|false|none|Result|
|request|[ArchiveAGroupRequest](#schemaarchiveagrouprequest)|false|none|Archive *or* restore a group|

<h2 id="tocSsummarybyattributeresponse">SummaryByAttributeResponse</h2>

<a id="schemasummarybyattributeresponse"></a>

```json
{
  "attributeNameToClicks": [
    {
      "Key": "string",
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "attributeNameToComms": [
    {
      "Key": "string",
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "attributeNameToConv": [
    {
      "Key": "string",
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "attributeNameToEpc": [
    {
      "Key": "string",
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "request": {
    "start": null,
    "end": null,
    "advertiserId": "0",
    "attributeName": "product",
    "doPreviousPeriod": "0",
    "resolution": "hour"
  }
}

```

*SummaryByAttributeResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|attributeNameToClicks|[[KeyValuePair_String_BasicStats_](#schemakeyvaluepair_string_basicstats_)]|false|none|[KeyValuePair<String,BasicStats>]|
|attributeNameToComms|[[KeyValuePair_String_BasicStats_](#schemakeyvaluepair_string_basicstats_)]|false|none|[KeyValuePair<String,BasicStats>]|
|attributeNameToConv|[[KeyValuePair_String_BasicStats_](#schemakeyvaluepair_string_basicstats_)]|false|none|[KeyValuePair<String,BasicStats>]|
|attributeNameToEpc|[[KeyValuePair_String_BasicStats_](#schemakeyvaluepair_string_basicstats_)]|false|none|[KeyValuePair<String,BasicStats>]|
|request|[SummaryByAttributeRequest](#schemasummarybyattributerequest)|false|none|SummaryByAttributeRequest|

<h2 id="tocSsummarybyattributerequest">SummaryByAttributeRequest</h2>

<a id="schemasummarybyattributerequest"></a>

```json
{
  "start": null,
  "end": null,
  "advertiserId": "0",
  "attributeName": "product",
  "doPreviousPeriod": "0",
  "resolution": "hour"
}

```

*SummaryByAttributeRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|start|dateTime(date-time)|false|none|Start date for the report required.|
|end|dateTime(date-time)|false|none|End date for the report required|
|advertiserId|integer(int32)|false|none|Id of the advertiser to show for. 0 for all, 1 for itunes and 3 for amazon|
|attributeName|string|false|none|Indicated the different Reports available.|
|doPreviousPeriod|integer(int32)|false|none|Indicates whether to return data of the last queried set with the new request|
|resolution|string|false|none|Resolution of the data.|

#### Enumerated Values

|Property|Value|
|---|---|
|advertiserId|0|
|advertiserId|1|
|advertiserId|3|
|attributeName|product|
|attributeName|destination|
|attributeName|referrer|
|attributeName|tag|
|attributeName|os|
|attributeName|device|
|attributeName|browser|
|attributeName|shorturl|
|attributeName|group|
|doPreviousPeriod|0|
|doPreviousPeriod|1|
|resolution|hour|
|resolution|day|
|resolution|month|
|resolution|lifetime|

<h2 id="tocSgroupresponse">GroupResponse</h2>

<a id="schemagroupresponse"></a>

```json
{
  "group": {
    "name": "string",
    "description": "string",
    "userName": "string",
    "id": 0,
    "dateCreated": "2018-10-02T04:10:23Z",
    "noCreatedDateFlag": 0,
    "enabled": 0
  },
  "isError": {
    "errorMessage": "string",
    "errorTitle": "string"
  },
  "request": {
    "groupId": 0,
    "group": "string"
  }
}

```

*GroupResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|group|[Group](#schemagroup)|false|none|Group|
|isError|[Result](#schemaresult)|false|none|Result|
|request|[GroupRequest](#schemagrouprequest)|false|none|GET the group matching tsid or group name|

<h2 id="tocSsummarybyresolutionresponse">SummaryByResolutionResponse</h2>

<a id="schemasummarybyresolutionresponse"></a>

```json
{
  "clicksByDate": [
    {
      "Key": {
        "dateTime": "2018-10-02T04:10:23Z",
        "jsDate": 0
      },
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "clicksByDatePP": [
    {
      "Key": {
        "dateTime": "2018-10-02T04:10:23Z",
        "jsDate": 0
      },
      "Value": {
        "clicks": 0,
        "clicksMinusBot": 0,
        "clicksMinusSharedAndBot": 0,
        "baseClicks": 0,
        "activeShare": 0,
        "passiveShare": 0,
        "clientAffiliated": 0,
        "spider": 0,
        "overflow": 0,
        "advancedTargeting": 0,
        "trackingPixel": 0,
        "translated": 0,
        "sharedTranslated": 0,
        "sharedAffiliated": 0,
        "previousPeriod": null,
        "currencyForConsolidated": "string",
        "commissionForConsolidated": 0,
        "valueForConsolidated": 0,
        "itemsForConsolidated": 0,
        "epcNoBots": 0,
        "epcWithBots": 0,
        "convForConsolidated": 0,
        "convPercent": 0,
        "attributeValue": "string",
        "date": "2018-10-02T04:10:23Z",
        "prefetch": 0,
        "duplicates": 0,
        "junkTraffic": 0
      }
    }
  ],
  "request": {
    "start": null,
    "end": null,
    "advertiserId": "0",
    "resolution": "hour",
    "doPreviousPeriod": "0"
  },
  "resolutionOverride": "string"
}

```

*SummaryByResolutionResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|clicksByDate|[[KeyValuePair_GraphableDateTime_BasicStats_](#schemakeyvaluepair_graphabledatetime_basicstats_)]|false|none|[KeyValuePair<GraphableDateTime,BasicStats>]|
|clicksByDatePP|[[KeyValuePair_GraphableDateTime_BasicStats_](#schemakeyvaluepair_graphabledatetime_basicstats_)]|false|none|[KeyValuePair<GraphableDateTime,BasicStats>]|
|request|[SummaryByResolutionRequest](#schemasummarybyresolutionrequest)|false|none|SummaryByResolutionRequest|
|resolutionOverride|string|false|none|none|

<h2 id="tocSgraphabledatetime">GraphableDateTime</h2>

<a id="schemagraphabledatetime"></a>

```json
{
  "dateTime": "2018-10-02T04:10:23Z",
  "jsDate": 0
}

```

*GraphableDateTime*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|dateTime|string(date-time)|false|none|none|
|jsDate|number(double)|false|none|none|

<h2 id="tocSsummarybyresolutionrequest">SummaryByResolutionRequest</h2>

<a id="schemasummarybyresolutionrequest"></a>

```json
{
  "start": null,
  "end": null,
  "advertiserId": "0",
  "resolution": "hour",
  "doPreviousPeriod": "0"
}

```

*SummaryByResolutionRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|start|dateTime(date-time)|false|none|Start date for the report required. Date format YYYY-MM-DD|
|end|dateTime(date-time)|false|none|End date for the report required. Date format YYYY-MM-DD|
|advertiserId|integer(int32)|false|none|Id of the advertiser to show for. 0 for all, 1 for itunes and 3 for amazon|
|resolution|string|false|none|Resolution of the data.|
|doPreviousPeriod|integer(int32)|false|none|Indicates whether to return data of the last queried set with the new request|

#### Enumerated Values

|Property|Value|
|---|---|
|advertiserId|0|
|advertiserId|1|
|advertiserId|3|
|resolution|hour|
|resolution|day|
|resolution|month|
|resolution|lifetime|
|doPreviousPeriod|0|
|doPreviousPeriod|1|

<h2 id="tocSlistlinksresponse">ListLinksResponse</h2>

<a id="schemalistlinksresponse"></a>

```json
{
  "allLinksLoaded": 0,
  "defaultNumberOfHistoricalLinksToShow": 0,
  "errorMessage": "string",
  "results": [
    {
      "id": 0,
      "destinationUrl": "string",
      "shortUrlCode": "string",
      "domain": "string",
      "hasOverride": true,
      "productUrl": "string",
      "trackingCode": "string",
      "skipAffiliateRedirect": true,
      "createdUtc": "2018-10-02T04:10:23Z",
      "updatedUtc": "2018-10-02T04:10:23Z",
      "notes": "string",
      "createdUserTime": "2018-10-02T04:10:23Z",
      "updatedUserTime": "2018-10-02T04:10:23Z",
      "tsid": 0,
      "group": "string",
      "username": "string",
      "jsonMetadata": "string",
      "jsonItemMetadata": "string",
      "jsonPostProcessingRules": "string",
      "jsonOverrides": "string",
      "totalClicks": 0,
      "advertiser": "string",
      "advertiserId": 0,
      "percentChangePeriodOverPeriod": 0,
      "previousPeriodTotalClicks": 0,
      "isArchived": 0,
      "isArchivedInt": 0,
      "productDisplayName1": "string",
      "productDisplayName2": "string",
      "productDisplayName3": "string",
      "productArtworkThumbnailUrl": "string",
      "productArtworkThumbnailUrl100": "string",
      "advertiserIcon": "string",
      "advertiserIconCssClass": "string",
      "isGenius": true,
      "advertiserIconTitle": "string",
      "trackingPixelIds": "string",
      "applePreference": 0,
      "productArtworkThumbnailUrl150": "string",
      "aliases": [
        {
          "baseCode": "string",
          "code": "string",
          "domain": "string",
          "lastUpdatedUtc": "2018-10-02T04:10:23Z"
        }
      ],
      "linkCreatorSetting": "string"
    }
  ],
  "username": "string"
}

```

*ListLinksResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|allLinksLoaded|integer(int32)|false|none|none|
|defaultNumberOfHistoricalLinksToShow|integer(int32)|false|none|none|
|errorMessage|string|false|none|none|
|results|[[UserShortLink](#schemausershortlink)]|false|none|[UserShortLink]|
|username|string|false|none|none|

<h2 id="tocSupdateshorturlresponse">UpdateShortUrlResponse</h2>

<a id="schemaupdateshorturlresponse"></a>

```json
{
  "responseStatus": {
    "errorCode": "string",
    "message": "string",
    "stackTrace": "string",
    "errors": [
      {
        "errorCode": "string",
        "fieldName": "string",
        "message": "string",
        "meta": {
          "property1": "string",
          "property2": "string"
        }
      }
    ],
    "meta": {
      "property1": "string",
      "property2": "string"
    }
  }
}

```

*UpdateShortUrlResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|responseStatus|[ResponseStatus](#schemaresponsestatus)|false|none|ResponseStatus|

<h2 id="tocSshorturlarchivingresponse">ShortUrlArchivingResponse</h2>

<a id="schemashorturlarchivingresponse"></a>

```json
{
  "request": {
    "unarchiveMode": null,
    "codeToArchive": "string"
  }
}

```

*ShortUrlArchivingResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|request|[ShortUrlArchivingRequest](#schemashorturlarchivingrequest)|false|none|GET hourly click data for a link by country|

<h2 id="tocSlist_string_">List_String_</h2>

<a id="schemalist_string_"></a>

```json
[
  "string"
]

```

*List<String>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|List<String>|[string]|false|none|none|

<h2 id="tocSdictionary_string_list_string_">Dictionary_String_List_String_</h2>

<a id="schemadictionary_string_list_string_"></a>

```json
{
  "property1": [
    "string"
  ],
  "property2": [
    "string"
  ]
}

```

*Dictionary<String,List<String>>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[string]|false|none|none|

<h2 id="tocSdictionary_string_string_">Dictionary_String_String_</h2>

<a id="schemadictionary_string_string_"></a>

```json
{
  "property1": "string",
  "property2": "string"
}

```

*Dictionary<String,String>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|string|false|none|none|

<h2 id="tocSlist_affiliatetokenbyaffiliatenetwork_">List_AffiliateTokenByAffiliateNetwork_</h2>

<a id="schemalist_affiliatetokenbyaffiliatenetwork_"></a>

```json
[
  {
    "advertiserName": "string",
    "affiliateToken": "string",
    "affiliateNetworkName": "string",
    "affiliateNetworkDisplayName": "string"
  }
]

```

*List<AffiliateTokenByAffiliateNetwork>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|List<AffiliateTokenByAffiliateNetwork>|[[AffiliateTokenByAffiliateNetwork](#schemaaffiliatetokenbyaffiliatenetwork)]|false|none|[AffiliateTokenByAffiliateNetwork]|

<h2 id="tocSdictionary_int32_list_affiliatetokenbyaffiliatenetwork_">Dictionary_Int32_List_AffiliateTokenByAffiliateNetwork_</h2>

<a id="schemadictionary_int32_list_affiliatetokenbyaffiliatenetwork_"></a>

```json
{
  "property1": [
    {
      "advertiserName": "string",
      "affiliateToken": "string",
      "affiliateNetworkName": "string",
      "affiliateNetworkDisplayName": "string"
    }
  ],
  "property2": [
    {
      "advertiserName": "string",
      "affiliateToken": "string",
      "affiliateNetworkName": "string",
      "affiliateNetworkDisplayName": "string"
    }
  ]
}

```

*Dictionary<Int32,List<AffiliateTokenByAffiliateNetwork>>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[[AffiliateTokenByAffiliateNetwork](#schemaaffiliatetokenbyaffiliatenetwork)]|false|none|[AffiliateTokenByAffiliateNetwork]|

<h2 id="tocSlist_conditionalpostprocessingactions_">List_ConditionalPostProcessingActions_</h2>

<a id="schemalist_conditionalpostprocessingactions_"></a>

```json
[
  {
    "conditions": [
      {}
    ],
    "actions": [
      {}
    ]
  }
]

```

*List<ConditionalPostProcessingActions>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|List<ConditionalPostProcessingActions>|[[ConditionalPostProcessingActions](#schemaconditionalpostprocessingactions)]|false|none|[ConditionalPostProcessingActions]|

<h2 id="tocSdictionary_string_list_conditionalpostprocessingactions_">Dictionary_String_List_ConditionalPostProcessingActions_</h2>

<a id="schemadictionary_string_list_conditionalpostprocessingactions_"></a>

```json
{
  "property1": [
    {
      "conditions": [
        {}
      ],
      "actions": [
        {}
      ]
    }
  ],
  "property2": [
    {
      "conditions": [
        {}
      ],
      "actions": [
        {}
      ]
    }
  ]
}

```

*Dictionary<String,List<ConditionalPostProcessingActions>>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[[ConditionalPostProcessingActions](#schemaconditionalpostprocessingactions)]|false|none|[ConditionalPostProcessingActions]|

<h2 id="tocStuple_string_postprocessingactionlevel_">Tuple_String_PostProcessingActionLevel_</h2>

<a id="schematuple_string_postprocessingactionlevel_"></a>

```json
{}

```

*Tuple`2*

### Properties

*None*

<h2 id="tocSdictionary_string_postprocessingactionsshorturl_">Dictionary_String_PostProcessingActionsShorturl_</h2>

<a id="schemadictionary_string_postprocessingactionsshorturl_"></a>

```json
{
  "property1": {
    "shorturl": [
      {
        "conditions": [
          {}
        ],
        "actions": [
          {}
        ]
      }
    ],
    "team": [
      {
        "conditions": [
          {}
        ],
        "actions": [
          {}
        ]
      }
    ],
    "user": [
      {
        "conditions": [
          {}
        ],
        "actions": [
          {}
        ]
      }
    ]
  },
  "property2": {
    "shorturl": [
      {
        "conditions": [
          {}
        ],
        "actions": [
          {}
        ]
      }
    ],
    "team": [
      {
        "conditions": [
          {}
        ],
        "actions": [
          {}
        ]
      }
    ],
    "user": [
      {
        "conditions": [
          {}
        ],
        "actions": [
          {}
        ]
      }
    ]
  }
}

```

*Dictionary<String,PostProcessingActionsShorturl>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[PostProcessingActionsShorturl](#schemapostprocessingactionsshorturl)|false|none|PostProcessingActionsShorturl|

<h2 id="tocSidictionary_string_object_">IDictionary_String_Object_</h2>

<a id="schemaidictionary_string_object_"></a>

```json
{
  "property1": {},
  "property2": {}
}

```

*IDictionary<String,Object>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[Object](#schemaobject)|false|none|Object|

<h2 id="tocSdictionary_string_invoicedetail_">Dictionary_String_InvoiceDetail_</h2>

<a id="schemadictionary_string_invoicedetail_"></a>

```json
{
  "property1": {},
  "property2": {}
}

```

*Dictionary<String,InvoiceDetail>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[InvoiceDetail](#schemainvoicedetail)|false|none|InvoiceDetail|

<h2 id="tocSspfresponse_invoice_">SpfResponse_Invoice_</h2>

<a id="schemaspfresponse_invoice_"></a>

```json
{
  "totalPages": 0,
  "pages": [
    {
      "previous": 0,
      "next": 0,
      "page": [
        {
          "id": "string",
          "invoiceDate": "2018-10-02T04:10:23Z",
          "createdUtc": "2018-10-02T04:10:23Z",
          "netPaymentTerms": 0,
          "periodStartUtc": "2018-10-02T04:10:23Z",
          "periodEndUtc": "2018-10-02T04:10:23Z",
          "paymentDueUtc": "2018-10-02T04:10:23Z",
          "trialPeriodStartUtc": "2018-10-02T04:10:23Z",
          "trialPeriodEndUtc": "2018-10-02T04:10:23Z",
          "lineItems": [
            {
              "notes": "string",
              "quantity": 0,
              "quantityUnit": "string",
              "rateUnit": "string",
              "amount": 0,
              "type": "string",
              "name": "string",
              "rate": 0
            }
          ],
          "details": {
            "property1": {},
            "property2": {}
          },
          "amount": 0,
          "amountDue": 0,
          "currency": "string",
          "status": "string",
          "forgiven": true,
          "username": "string",
          "statusChanges": [
            {
              "changedUtc": "2018-10-02T04:10:23Z",
              "newStatus": "string"
            }
          ],
          "paymentId": "string",
          "paymentIds": [
            "string"
          ],
          "planName": "string",
          "hasUserDetails": true
        }
      ]
    }
  ],
  "activePage": {
    "previous": 0,
    "next": 0,
    "page": [
      {
        "id": "string",
        "invoiceDate": "2018-10-02T04:10:23Z",
        "createdUtc": "2018-10-02T04:10:23Z",
        "netPaymentTerms": 0,
        "periodStartUtc": "2018-10-02T04:10:23Z",
        "periodEndUtc": "2018-10-02T04:10:23Z",
        "paymentDueUtc": "2018-10-02T04:10:23Z",
        "trialPeriodStartUtc": "2018-10-02T04:10:23Z",
        "trialPeriodEndUtc": "2018-10-02T04:10:23Z",
        "lineItems": [
          {
            "notes": "string",
            "quantity": 0,
            "quantityUnit": "string",
            "rateUnit": "string",
            "amount": 0,
            "type": "string",
            "name": "string",
            "rate": 0
          }
        ],
        "details": {
          "property1": {},
          "property2": {}
        },
        "amount": 0,
        "amountDue": 0,
        "currency": "string",
        "status": "string",
        "forgiven": true,
        "username": "string",
        "statusChanges": [
          {
            "changedUtc": "2018-10-02T04:10:23Z",
            "newStatus": "string"
          }
        ],
        "paymentId": "string",
        "paymentIds": [
          "string"
        ],
        "planName": "string",
        "hasUserDetails": true
      }
    ]
  }
}

```

*SpfResponse`1*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalPages|integer(int32)|false|none|none|
|pages|[[SpfPage_Invoice_](#schemaspfpage_invoice_)]|false|none|[SpfPage<Invoice>]|
|activePage|[SpfPage_Invoice_](#schemaspfpage_invoice_)|false|none|SpfPage<Invoice>|

<h2 id="tocSspfpage_invoice_">SpfPage_Invoice_</h2>

<a id="schemaspfpage_invoice_"></a>

```json
{
  "previous": 0,
  "next": 0,
  "page": [
    {
      "id": "string",
      "invoiceDate": "2018-10-02T04:10:23Z",
      "createdUtc": "2018-10-02T04:10:23Z",
      "netPaymentTerms": 0,
      "periodStartUtc": "2018-10-02T04:10:23Z",
      "periodEndUtc": "2018-10-02T04:10:23Z",
      "paymentDueUtc": "2018-10-02T04:10:23Z",
      "trialPeriodStartUtc": "2018-10-02T04:10:23Z",
      "trialPeriodEndUtc": "2018-10-02T04:10:23Z",
      "lineItems": [
        {
          "notes": "string",
          "quantity": 0,
          "quantityUnit": "string",
          "rateUnit": "string",
          "amount": 0,
          "type": "string",
          "name": "string",
          "rate": 0
        }
      ],
      "details": {
        "property1": {},
        "property2": {}
      },
      "amount": 0,
      "amountDue": 0,
      "currency": "string",
      "status": "string",
      "forgiven": true,
      "username": "string",
      "statusChanges": [
        {
          "changedUtc": "2018-10-02T04:10:23Z",
          "newStatus": "string"
        }
      ],
      "paymentId": "string",
      "paymentIds": [
        "string"
      ],
      "planName": "string",
      "hasUserDetails": true
    }
  ]
}

```

*SpfPage`1*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|previous|integer(int32)|false|none|none|
|next|integer(int32)|false|none|none|
|page|[[Invoice](#schemainvoice)]|false|none|[Invoice]|

<h2 id="tocSkeyvaluepair_countrydescription_basicstats_">KeyValuePair_CountryDescription_BasicStats_</h2>

<a id="schemakeyvaluepair_countrydescription_basicstats_"></a>

```json
{
  "Key": {
    "iso2": "string",
    "name": "string"
  },
  "Value": {
    "clicks": 0,
    "clicksMinusBot": 0,
    "clicksMinusSharedAndBot": 0,
    "baseClicks": 0,
    "activeShare": 0,
    "passiveShare": 0,
    "clientAffiliated": 0,
    "spider": 0,
    "overflow": 0,
    "advancedTargeting": 0,
    "trackingPixel": 0,
    "translated": 0,
    "sharedTranslated": 0,
    "sharedAffiliated": 0,
    "previousPeriod": null,
    "currencyForConsolidated": "string",
    "commissionForConsolidated": 0,
    "valueForConsolidated": 0,
    "itemsForConsolidated": 0,
    "epcNoBots": 0,
    "epcWithBots": 0,
    "convForConsolidated": 0,
    "convPercent": 0,
    "attributeValue": "string",
    "date": "2018-10-02T04:10:23Z",
    "prefetch": 0,
    "duplicates": 0,
    "junkTraffic": 0
  }
}

```

*KeyValuePair<CountryDescription,BasicStats>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Key|[CountryDescription](#schemacountrydescription)|false|none|CountryDescription|
|Value|[BasicStats](#schemabasicstats)|false|none|BasicStats|

<h2 id="tocSkeyvaluepair_string_basicstats_">KeyValuePair_String_BasicStats_</h2>

<a id="schemakeyvaluepair_string_basicstats_"></a>

```json
{
  "Key": "string",
  "Value": {
    "clicks": 0,
    "clicksMinusBot": 0,
    "clicksMinusSharedAndBot": 0,
    "baseClicks": 0,
    "activeShare": 0,
    "passiveShare": 0,
    "clientAffiliated": 0,
    "spider": 0,
    "overflow": 0,
    "advancedTargeting": 0,
    "trackingPixel": 0,
    "translated": 0,
    "sharedTranslated": 0,
    "sharedAffiliated": 0,
    "previousPeriod": null,
    "currencyForConsolidated": "string",
    "commissionForConsolidated": 0,
    "valueForConsolidated": 0,
    "itemsForConsolidated": 0,
    "epcNoBots": 0,
    "epcWithBots": 0,
    "convForConsolidated": 0,
    "convPercent": 0,
    "attributeValue": "string",
    "date": "2018-10-02T04:10:23Z",
    "prefetch": 0,
    "duplicates": 0,
    "junkTraffic": 0
  }
}

```

*KeyValuePair<String,BasicStats>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Key|string|false|none|none|
|Value|[BasicStats](#schemabasicstats)|false|none|BasicStats|

<h2 id="tocSkeyvaluepair_graphabledatetime_basicstats_">KeyValuePair_GraphableDateTime_BasicStats_</h2>

<a id="schemakeyvaluepair_graphabledatetime_basicstats_"></a>

```json
{
  "Key": {
    "dateTime": "2018-10-02T04:10:23Z",
    "jsDate": 0
  },
  "Value": {
    "clicks": 0,
    "clicksMinusBot": 0,
    "clicksMinusSharedAndBot": 0,
    "baseClicks": 0,
    "activeShare": 0,
    "passiveShare": 0,
    "clientAffiliated": 0,
    "spider": 0,
    "overflow": 0,
    "advancedTargeting": 0,
    "trackingPixel": 0,
    "translated": 0,
    "sharedTranslated": 0,
    "sharedAffiliated": 0,
    "previousPeriod": null,
    "currencyForConsolidated": "string",
    "commissionForConsolidated": 0,
    "valueForConsolidated": 0,
    "itemsForConsolidated": 0,
    "epcNoBots": 0,
    "epcWithBots": 0,
    "convForConsolidated": 0,
    "convPercent": 0,
    "attributeValue": "string",
    "date": "2018-10-02T04:10:23Z",
    "prefetch": 0,
    "duplicates": 0,
    "junkTraffic": 0
  }
}

```

*KeyValuePair<GraphableDateTime,BasicStats>*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Key|[GraphableDateTime](#schemagraphabledatetime)|false|none|GraphableDateTime|
|Value|[BasicStats](#schemabasicstats)|false|none|BasicStats|

