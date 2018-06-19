<h1 align="center">Fax-REST-API</h1>
<p align="center">This is the Fax REST API documentation for Fax.to Fax API</p>
<br>

# USER MANAGEMENT

## 1. User Register API

You can use the User Register API to register a user

1. Create a <a href='/docs/user-management/user-register/request.md' id='user-register-request' class='anchor' aria-hidden='true'>request</a> and register a user

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl  -d  '{"email":"USER_EMAIL", "password":"USER_PASSWORD"}' -H  'Content-Type: application/json'  -X POST 'https://fax.to/api/v2/user'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
  CURLOPT_URL => 'https://fax.to/api/v2/user'
];

$post     = array('email' => 'USER_EMAIL','password'=> 'USER_PASSWORD');
$ch       = curl_init();
curl_setopt_array($ch, $defaults);
curl_setopt($ch, CURLOPT_POST,1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $post);
$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params   = {
    'email': 'USER_EMAIL',
    'password': 'USER_PASSWORD'
}

url      = 'https://fax.to/api/v2/user'
response = urllib.urlopen(url, urllib.urlencode(params))
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

params       = {'email' => 'USER_EMAIL', 'password' => 'USER_PASSWORD'}
json_headers = {"Content-Type" => "application/json"}

uri          = URI.parse("https://fax.to/api/v2/user")
http         = Net::HTTP.new(uri.host, uri.port)
response     = http.post(uri.path, params.to_json, json_headers)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "api_key": "f1a99500-7ce0-11e7-9fb1-0580e1fcb90c"
}
```

## 2. User Login API

You can use the User Login API to return the api key of the user

1. Create a <a href='/docs/user-management/user-login/request.md' id='user-login-request' class='anchor' aria-hidden='true'>request</a> and log on to a user account

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl  -d  '{"email":"USER_EMAIL", "password":"USER_PASSWORD"}' -H  'Content-Type: application/json'  -X POST 'https://fax.to/api/v2/user/login'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
  CURLOPT_URL => 'https://fax.to/api/v2/user/login'
];

$post     = array('email' => 'USER_EMAIL','password'=> 'USER_PASSWORD');
$ch       = curl_init();
curl_setopt_array($ch, $defaults);
curl_setopt($ch, CURLOPT_POST,1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $post);
$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params   = {
    'email': 'USER_EMAIL',
    'password': 'USER_PASSWORD'
}

url      = 'https://fax.to/api/v2/user/login'
response = urllib.urlopen(url, urllib.urlencode(params))
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

params       = {'email' => 'USER_EMAIL', 'password' => 'USER_PASSWORD'}
json_headers = {"Content-Type" => "application/json"}

uri          = URI.parse("https://fax.to/api/v2/user/login")
http         = Net::HTTP.new(uri.host, uri.port)
response     = http.post(uri.path, params.to_json, json_headers)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "api_key": "f1a99500-7ce0-11e7-9fb1-0580e1fcb90c"
}
```

## 3. Sub User API

You can use the Sub User API to create a subuser

1. Create a <a href='/docs/user-management/sub-user/request.md' id='sub-user-request' class='anchor' aria-hidden='true'>request</a> and create a subuser

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl  -d  '{"email":"SUBUSER_EMAIL", "password":"SUBUSER_PASSWORD"}' -H  'Content-Type: application/json'  -X POST 'https://fax.to/api/v2/subuser?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
  CURLOPT_URL => 'https://fax.to/api/v2/subuser?api_key=API_KEY'
];

$post     = array('email' => 'SUBUSER_EMAIL','password'=> 'SUBUSER_PASSWORD');
$ch       = curl_init();
curl_setopt_array($ch, $defaults);
curl_setopt($ch, CURLOPT_POST,1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $post);
$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params   = {
    'email': 'SUBUSER_EMAIL',
    'password': 'SUBUSER_PASSWORD'
}

url      = 'https://fax.to/api/v2/subuser?api_key=API_KEY'
response = urllib.urlopen(url, urllib.urlencode(params))
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

params       = {'email' => 'SUBUSER_EMAIL', 'password' => 'SUBUSER_PASSWORD'}
json_headers = {"Content-Type" => "application/json"}

uri          = URI.parse("https://fax.to/api/v2/subuser?api_key=API_KEY")
http         = Net::HTTP.new(uri.host, uri.port)
response     = http.post(uri.path, params.to_json, json_headers)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "api_key": "94a126a0-9940-11e7-ac09-f55a41e16868"
}
```

## 4. Cash Balance API

To use the Cash Balance API:

1. Create a <a href='/docs/user-management/cash-balance/request.md' id='cash-balance-request' class='anchor' aria-hidden='true'>request</a> and get the cash balance:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/balance?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
	CURLOPT_URL => 'https://fax.to/api/v2/balance?api_key=API_KEY'
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
}

url = 'https://fax.to/api/v2/balance?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/balance?api_key=API_KEY")

response = Net::HTTP.get(uri)

puts response.body
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "balance": 100.10
}
```
<br>

# FAX SENDING

## 1. Send Fax API

### Overview

You use the FAX API to send fax in any fax numbers anywhere in the world. The workflow for sending fax messages using the Fax API is:

1. Create a request to send fax.
2. Check the response codes and ensure that you sent the request correctly.
3. Your fax is delivered to the fax number.
4. If you set callback in the request, check that your app received the callback correctly.

### Implementing the Fax API workflow

#### To use the Fax API:

1. Create a <a href='/docs/fax-sending/send-fax/api-reference.md#request' id='send-fax-request' class='anchor' aria-hidden='true'>request</a> and send the fax:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash

base_url='https://fax.to/api/v1'
action='/fax'
key='API_KEY'
fax_number='+441224459292'
document_id='112601'

curl -X POST "$base_url$action" \
-d api_key=$key \
-d fax_number=$fax_number \
-d document_id="$document_id"
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$params = [
	'fax_number' => '+441224459292',
	'document_id' => '112601'
];

$defaults = [
	CURLOPT_URL => 'https://fax.to/api/v1/fax?api_key=API_KEY',
	CURLOPT_POST => true,
	CURLOPT_POSTFIELDS => $params
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

echo $response;
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib
import urllib2

params = {
    'api_key': 'API_KEY',
    'fax_number': '+441224459292',
    'document_id': '112601'
}

url = 'https://fax.to/api/v1/fax?' + urllib.urlencode(params)

request = urllib2.Request(url)
request.add_header('Accept', 'application/json')
request.add_header('Content-Type', 'multipart/form-data')
request.add_data('')
response = urllib2.urlopen(request)
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v1/fax")
params = {
    'api_key' => 'API_KEY',
    'fax_number' => '+441224459292',
    'document_id' => '112601',
}

response = Net::HTTP.post_form(uri, params)

puts response.body
```
</p></details></ul>

<ul><details><summary><strong>C#</strong></summary><p>

For setting up the libraries please checkout
```c#
using System;
using System.Diagnostics;
using IO.Swagger.Api;
using IO.Swagger.Client;
using IO.Swagger.Model;

namespace Example
{
    public class FaxPostExample
    {
        public void main
        {
            var apiInstance = new FaxApi();
            var apiKey = API_KEY;
            var faxNumber = +441224459292;
            var documentId = 56;
            var tsiNumber = +441224459292;
            var file = new System.IO.Stream();
            var deleteFile = 1;  // int? | Whether to delete file after fax transaction. (put 1 to delete) (optional)

            try
            {
                apiInstance.FaxPost(apiKey, faxNumber, documentId, tsiNumber, file, deleteFile);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling FaxApi.FaxPost: " + e.Message );
            }
        }
    }
}
```
</p></details></ul>
<br>

2. Check the [response](/docs/fax-sending/send-fax/api-reference.md#response) to ensure that you sent the request to Fax.to correctly:

<ul><details><summary><strong>PHP</strong></summary><p>

For setting up the libraries please checkout
```php
<?php
  // Decode the json object you retrieved when you ran the request.
  $decodedResponse = json_decode($response, true);
  var_dump($decodedResponse);
?>
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

For setting up the libraries please checkout
```python
import json

# Using the response object from the request

if response.code == 200 :
    data = response.read()
    # Decode JSON response from UTF-8
    decoded_response = json.loads(data.decode('utf-8'))
    # Check if your messages are succesful
    status = decoded_response["status"]
    fax_job_id = decoded_response["fax_job_id"]
    user_cash_balance = decoded_response["user_cash_balance"]
    cost = decoded_response["cost"]

else :
    # Check the errors
    print "unexpected http {code} response from Fax.to api". response.code
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

For setting up the libraries please checkout
```ruby
require 'json'

# Decode the json object from the response object you retrieved from the request.
if response.kind_of? Net::HTTPOK
  decoded_response = JSON.parse(response.body )


  status = decoded_response["status"]
  fax_job_id = decoded_response["fax_job_id"]
  user_cash_balance = decoded_response["user_cash_balance"]
  cost = decoded_response["cost"]

else
  puts response.code + " error sending fax"
end
```
</p></details></ul>

3. Your fax is delivered to the fax number.

4. If you set <a href='/docs/fax-sending/send-fax/api-reference.md#webhook' id='callback' class='anchor' aria-hidden='true'>callback</a> in the API settings, use the <a href='/docs/fax-sending/send-fax/api-reference.md#webhook' id='data' class='anchor' aria-hidden='true'>data</a> sent to your [webhook endpoint](https://api.fax.to/settings) to update your own record:

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php
// Work with get or post
$request = $_POST;

// Check that this is a delivery receipt.
if (!isset($request['fax_job_id']) OR !isset($request['fax_job_id'])) {
    error_log('This is not a delivery receipt');
    return;
}

//Check if your message has been delivered correctly.
if ($request['status'] == 'success') {
    error_log("Success {$request['msg_code']} {$request['message']}");
} elseif ($request['status'] == 'failed') {
    error_log("Failed {$request['msg_code']} {$request['message']}");
} else {
    error_log("Failed {$request['msg_code']} {$request['message']}");
}
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
#To run this code, replace the MyHandler in
# https://wiki.python.org/moin/BaseHttpServer With the following code,
from urlparse import urlparse, parse_qs
class MyHandler(BaseHTTPServer.BaseHTTPRequestHandler):
    def do_GET(s):
        """Tell Fax.to that you have recieved the GET request."""
        s.send_response(200)
        s.send_header("Content-type", "text/html")
        s.end_headers()
        """Parse parameters in the GET request"""
        parsed_path = urlparse(s.path)
        try:
                delivery_receipt = dict(
                [p.split('=') for p in parsed_path[4].split('&')])
        except:
                delivery_receipt = {}

            """Check the is a delivery receipt"""
        if 'text' in delivery_receipt:
            print ("This is not a delivery receipt")
        elif delivery_receipt['status'] != "success":
            print "Fail:" + delivery_receipt['status']
            + ": " + delivery_receipt['msg_code'] +  ".\n"
        else:
            print "success"
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require 'socket'
require 'uri'

def handle_delivery_receipt(request_line)
#Parse the parameters and check if the message was delivered
  params = URI::decode_www_form(request_line).to_h
  if params["status"].nil? or params["fax_job_id"].nil?
    p ('This is not a delivery receipt')
  elsif params["status"] != 'success'
    p ("Your request " + params["status"] +
    "because of " + params["msg_code"] );
  else
    p ("Success for request " + params['fax_job_id'] )
  end
end
```
</p></details></ul>

## 2. Fax Cost API

To use the Fax Cost API:

1. Create a <a href='/docs/fax-sending/fax-cost/request.md' id='fax-cost-request' class='anchor' aria-hidden='true'>request</a> and get the fax cost:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/fax/{document_id}/costs?api_key=API_KEY&fax_number=+161242252602'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
	CURLOPT_URL => 'https://fax.to/api/v2/fax/{document_id}/costs?api_key=API_KEY&fax_number=+161242252602'
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY',
    'fax_number': '+161242252602'
}

url = 'https://fax.to/api/v2/fax/{document_id}/costs?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/fax/{document_id}/costs?api_key=API_KEY&fax_number=+161242252602")

response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "cost": 0.15
}
```

## 3. Fax Status API

To use the Fax Status API:

1. Create a <a href='/docs/fax-sending/fax-status/request.md' id='fax-status-request' class='anchor' aria-hidden='true'>request</a> and get the fax status:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/fax/{fax_job_id}/status?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
	CURLOPT_URL => 'https://fax.to/api/v2/fax/{fax_job_id}/status?api_key=API_KEY'
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
}

url = 'https://fax.to/api/v2/fax/{fax_job_id}/status?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/fax/{fax_job_id}/status?api_key=API_KEY")
response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "message": "Sent! Fax Has Been Answered.",
  "user_cash_balance": 100.20
}
```

## 4. Fax History API

To use the Fax History API:

1. Create a <a href='/docs/fax-sending/fax-history/request.md' id='fax-history-request' class='anchor' aria-hidden='true'>request</a> and get the fax history:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/fax-history?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
	CURLOPT_URL => 'https://fax.to/api/v2/fax-history?api_key=API_KEY'
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
}

url = 'https://fax.to/api/v2/fax-history?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/fax-history?api_key=API_KEY")
response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "history": [
    {
      "id": 92334,
      "created": {
        "date": "2017-03-09 15:35:28.000000",
        "timezone_type": 3,
        "timezone": "UTC"
      },
      "document_id": 112601,
      "document": "FAX11920.pdf",
      "recipient": "441224459292",
      "status": "success"
    }
  ]
}
```

## 5. Upload File API (Upload Local or Remote File)

You use the Upload File API to upload remote file or local file:

### Upload Remote File

1. Create a <a href='/docs/fax-sending/upload-file/request-remote.md' id='upload-remote-request' class='anchor' aria-hidden='true'>request</a> and upload a file:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -F AddRemoteFile={REMOTE_FILE_URL} 'https://fax.to/api/v2/files?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$targetUrl       = 'https://fax.to/api/v2/files?api_key=API_KEY';

//for local file upload
if (function_exists('curl_file_create'))  // php 5.5+
      $cFile     = curl_file_create('LOCAL_FILE_PATH');
else
      $cFile     = '@' . realpath('LOCAL_FILE_PATH');

$post            = array('AddRemoteFile' => 'REMOTE_FILE_URL');
$ch              = curl_init();
curl_setopt($ch, CURLOPT_URL,$targetUrl);
curl_setopt($ch, CURLOPT_POST,1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $post);
$response        = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

url         = {'api_key': 'API_KEY'}
data        = {'file': 'REMOTE_FILE_URL'}

url_params  = 'https://fax.to/api/v2/files?' + urllib.urlencode(url)
data_params = urllib.urlencode(data);
response    = urllib.urlopen(url_params,data_params)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

params       = {'file' => 'REMOTE_FILE_URL'}
json_headers = {"Content-Type" => "application/json"}

uri          = URI.parse("https://fax.to/api/v2/files?api_key=API_KEY")
http         = Net::HTTP.new(uri.host, uri.port)
response     = http.post(uri.path, params.to_json, json_headers)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "document_id": 11,
  "document": {
  "filename": "598317a8404bd.pdf.tiff",
  "filename_uploaded": "verify.txt",
  "orig_filename": "598317a8404bd.pdf",
  "file_extension": "txt",
  "total_pages": 1,
  "filesize": 3650,
  "preview_in_storage": 1,
  "preview_file": "598317a8404bd.pdf.preview.jpg",
  "preview_image": null,
  "s3": null,
  "user_id": 2,
  "updated_at": "2017-08-03 12:31:38",
  "created_at": "2017-08-03 12:31:38",
  "id": 300,
  }
}
```

### Upload Local File

1. Create a <a href='/docs/fax-sending/upload-file/request-local.md' id='upload-local-request' class='anchor' aria-hidden='true'>request</a> and upload a file:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl  -F file=@{LOCAL_FILE_PATH} 'https://fax.to/api/v2/files?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$targetUrl       = 'https://fax.to/api/v2/files?api_key=API_KEY';

//for local file upload
if (function_exists('curl_file_create'))  // php 5.5+
      $cFile     = curl_file_create('LOCAL_FILE_PATH');
else
      $cFile     = '@' . realpath('LOCAL_FILE_PATH');

$post            = array('file'=> $cFile);
$ch              = curl_init();
curl_setopt($ch, CURLOPT_URL,$targetUrl);
curl_setopt($ch, CURLOPT_POST,1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $post);
$response        = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

url         = {'api_key': 'API_KEY'}
data        = {'file': 'LOCAL_FILE_PATH'}

url_params  = 'https://fax.to/api/v2/files?' + urllib.urlencode(url)
data_params = urllib.urlencode(data);
response    = urllib.urlopen(url_params,data_params)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

params       = {'file' => 'LOCAL_FILE_PATH'}
json_headers = {"Content-Type" => "application/json"}

uri          = URI.parse("https://fax.to/api/v2/files?api_key=API_KEY")
http         = Net::HTTP.new(uri.host, uri.port)
response     = http.post(uri.path, params.to_json, json_headers)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "document_id": 11,
  "document": {
  "filename": "598317a8404bd.pdf.tiff",
  "filename_uploaded": "verify.txt",
  "orig_filename": "598317a8404bd.pdf",
  "file_extension": "txt",
  "total_pages": 1,
  "filesize": 3650,
  "preview_in_storage": 1,
  "preview_file": "598317a8404bd.pdf.preview.jpg",
  "preview_image": null,
  "s3": null,
  "user_id": 2,
  "updated_at": "2017-08-03 12:31:38",
  "created_at": "2017-08-03 12:31:38",
  "id": 300,
  }
}
```

## 6. Clean File API

You use the Clean File API to clean the document:

1. Create a <a href='/docs/fax-sending/file-clean/request.md' id='file-clean-request' class='anchor' aria-hidden='true'>request</a> and clean the file:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/file-clean?document_id=DOCUMENT_ID&api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$targetUrl       = 'https://fax.to/api/v2/file-clean?document_id=DOCUMENT_ID&api_key=API_KEY';

$ch              = curl_init();
curl_setopt($ch, CURLOPT_URL,$targetUrl);
curl_setopt($ch, CURLOPT_POST,0);
$response        = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
    'document_id': 'DOCUMENT_ID'
}

url = 'https://fax.to/api/v2/file-clean?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/file-clean?document_id=DOCUMENT_ID&api_key=API_KEY")

response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
 "status": "success",
  "file_extension": "pdf",
  "filename": "59a5152b95cc1.pdf.tiff",
  "filename_uploaded": "pdf-sample.pdf",
  "filesize": 485432,
  "id": 327,
  "orig_filename": "59a5152b95cc1.pdf",
  "preview_file": "59a5152b95cc1.pdf.preview.jpg",
  "preview_image": null,
  "preview_in_storage": 1,
  "s3": null,
  "server_document_id": null,
  "team_user_id": null,
  "total_pages": 1,
  "updated_at": "2017-08-29 07:18:05",
  "user_id": 1,
  "created_at": "2017-08-29 07:18:05",
}
```

## 7. Preview Generate File API

You use the Preview Generate File API to generate preview of the document:

1. Create a <a href='/docs/fax-sending/file-preview/request.md' id='file-preview-request' class='anchor' aria-hidden='true'>request</a> generate preview of the file:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'http://fax.to/api/v2/file-generate-preview?document_id=DOCUMENT_ID&api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$targetUrl       = 'http://fax.to/api/v2/file-generate-preview?document_id=DOCUMENT_ID&api_key=API_KEY';

$ch              = curl_init();
curl_setopt($ch, CURLOPT_URL,$targetUrl);
curl_setopt($ch, CURLOPT_POST,0);
$response        = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
    'document_id': 'DOCUMENT_ID'
}

url = 'http://fax.to/api/v2/file-generate-preview?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("http://fax.to/api/v2/file-generate-preview?document_id=DOCUMENT_ID&api_key=API_KEY")

response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "url": "http://api.fax.dev/member/my-documents/show-file/preview.png",
}
```

## 8. Get Files API

To use the Get Files API:

1. Create a <a href='/docs/fax-sending/get-files/request.md' id='get-files-request' class='anchor' aria-hidden='true'>request</a> and get list of files:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/files?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
  CURLOPT_URL => 'https://fax.to/api/v2/files?api_key=API_KEY'
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
}

url = 'https://fax.to/api/v2/files?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/files?api_key=API_KEY")

response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
[
  {
    "id": 2,
    "filename": "faxto.pdf",
    "pages": 1,
    "size": 39942,
    "uploaded": "2017-03-10"
  }
]
```

## 9. Delete Files API

To use the Delete Files API:

1. Create a <a href='/docs/fax-sending/delete-files/request.md' id='delete-files-request' class='anchor' aria-hidden='true'>request</a> and delete specific file:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X DELETE --header 'Content-Type: application/json' 'https://fax.to/api/v2/files/{document_id}?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'https://fax.to/api/v2/files/{document_id}?api_key=API_KEY');
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "DELETE");
$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib
import urllib2

params = {
    'api_key': 'API_KEY'
}

url = 'https://fax.to/api/v2/files/{document_id}?' + urllib.urlencode(params)
opener = urllib2.build_opener(urllib2.HTTPHandler)
req = urllib2.Request(url, None)
req.get_method = lambda: 'DELETE'  # creates the delete method
response = urllib2.urlopen(req)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/files/{document_id}?api_key=API_KEY")
response = Net::HTTP.delete(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status":  "success"
}
```
<br>

# FAX RECEIVING

## 1. Provision Numbers

To use the Provision Numbers API:

1. Create a <a href='/docs/fax-receiving/provision-numbers/request.md' id='provision-numbers-request' class='anchor' aria-hidden='true'>request</a> and provision a fax number:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X POST --header 'Content-Type: application/json' 'https://fax.to/api/v2/provision-numbers?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
  CURLOPT_URL => 'https://fax.to/api/v2/countries/didgroups/{did_group_id}/provision?api_key=API_KEY',
  CURLOPT_POST => 1
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
}

url = 'https://fax.to/api/v2/countries/didgroups/{did_group_id}/provision?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/countries/didgroups/{did_group_id}/provision?api_key=API_KEY")

response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "message": "Number has been provisioned.",
  "data":
    {
      "id": 49,
      "didid": 6988136,
      "did_group_id": 5598,
      "country_code": "CAN",
      "city_name": "ST. JOHN'S",
      "area_code": "709",
      "number": "+17097023976",
      "type": "GEOGRAPHIC",
      "trunk_id": 8934
    }
}
```

## 2. List Numbers

List Numbers is a method related to your own inventory. This method allows you to search for numbers within your own inventory. This method can be useful to get the current configuration of one or multiple numbers.

To use the List Numbers API:

1. Create a <a href='/docs/fax-receiving/list-numbers/request.md' id='list-numbers-request' class='anchor' aria-hidden='true'>request</a> and get list of numbers:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/numbers?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
  CURLOPT_URL => 'https://fax.to/api/v2/numbers?api_key=API_KEY'
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
}

url = 'https://fax.to/api/v2/numbers?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/numbers?api_key=API_KEY")

response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "numbers": [
    {
      "id": 775,
      "order_reference": null,
      "country_code": "CAN",
      "country": "CANADA",
      "city_name": null,
      "area_code": "204",
      "did_group_id": 67,
      "did_number": "+12048134699",
      "expiration_date": "2017-07-30",
      "status": "Active"
    },
    {
      "id": 776,
      "order_reference": null,
      "country_code": "CAN",
      "country": "CANADA",
      "city_name": null,
      "area_code": "204",
      "did_group_id": 67,
      "did_number": "+12048134700",
      "expiration_date": "2017-07-30",
      "status": "Active"
    }
  ],
  "meta": {
    "pagination": {
      "total": 7,
      "count": 2,
      "per_page": 2,
      "current_page": 2,
      "total_pages": 4,
      "links": {
        "previous": "https://fax.to/api/v2/numbers?page=1",
        "next": "https://fax.to/api/v2/numbers?page=3"
      }
    }
  }
}
```

## 3. List Incoming Faxes

List Incoming Faxes is a method that allows you to retrieve the list of incoming faxes

1. Create a <a href='/docs/fax-receiving/list-incoming-faxes/request.md' id='incoming-faxes-request' class='anchor' aria-hidden='true'>request</a> and get list of incoming faxes:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/incoming-faxes?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
  CURLOPT_URL => 'https://fax.to/api/v2/incoming-faxes?api_key=API_KEY'
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
}

url = 'https://fax.to/api/v2/incoming-faxes?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/incoming-faxes?api_key=API_KEY")

response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "inbox": [
   {
      "id": 772,
      "did_id": 7745147,
      "filename": "597ef3a78a2dd.pdf",
      "filesize": "120.45 KB",
      "number": "+918111922344",
      "sender": "919245657633",
      "total_pages": 5,
      "created_at": {
      "date": "2017-08-01 00:00:00.000000",
      "timezone_type": 3,
      "timezone": "UTC"
      },
      "preview_file": "https://fax.to/receivefax/api/v1/inbox/4/preview?api_key=abd1ebe0-62d5-11e7-91c7-8590f436fefa",
      "file_url": "https://fax.to/receivefax/api/v1/inbox/4/file?api_key=abd1ebe0-62d5-11e7-91c7-8590f436fefa"
    },
    {
      "id": 771,
      "did_id": 7745147,
      "filename": "597ef3a78a2dd.pdf",
      "filesize": "120.45 KB",
      "number": "+918111922344",
      "sender": "919245657633",
      "total_pages": 5,
      "created_at": {
      "date": "2017-08-01 00:00:00.000000",
      "timezone_type": 3,
      "timezone": "UTC"
        },
      "preview_file": "https://fax.to/receivefax/api/v1/inbox/4/preview?api_key=abd1ebe0-62d5-11e7-91c7-8590f436fefa",
      "file_url": "https://fax.to/receivefax/api/v1/inbox/4/file?api_key=abd1ebe0-62d5-11e7-91c7-8590f436fefa"
    }
  ],
  "meta": {
    "pagination": {
      "total": 7,
      "count": 2,
      "per_page": 2,
      "current_page": 2,
      "total_pages": 4,
      "links": {
        "previous": "https://fax.to/api/v2/incoming-faxes?page=1",
        "next": "https://fax.to/api/v2/incoming-faxes?page=3"
      }
    }
  }
}
```

## 4. List Faxes for a Recipient

This method allows you to retrieve the list of incoming faxes for a specific recipient.

1. Create a <a href='/docs/fax-receiving/list-faxes-recipient/request.md' id='recipient-faxes-request' class='anchor' aria-hidden='true'>request</a> and get list of faxes for a specific recipient:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/incoming-faxes/{recipient}?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
  CURLOPT_URL => 'https://fax.to/api/v2/incoming-faxes/{recipient}?api_key=API_KEY'
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
}

url = 'https://fax.to/api/v2/incoming-faxes/{recipient}?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/incoming-faxes/{recipient}?api_key=API_KEY")

response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "inbox": [
    {
      "id": 775,
      "did_id": 7745147,
      "filename": "597ef3a78a2dd.pdf",
      "filesize": "120.45 KB",
      "number": "+918111922344",
      "sender": "919245657633",
      "total_pages": 5,
      "created_at": {
      "date": "2017-08-01 00:00:00.000000",
      "timezone_type": 3,
      "timezone": "UTC"
      },
     "preview_file": "https://fax.to/receivefax/api/v1/inbox/4/preview?api_key=abd1ebe0-62d5-11e7-91c7-8590f436fefa",
     "file_url": "https://fax.to/receivefax/api/v1/inbox/4/file?api_key=abd1ebe0-62d5-11e7-91c7-8590f436fefa"
    },
    {
      "id": 776,
      "did_id": 7745147,
      "filename": "597ef3a78a2dd.pdf",
      "filesize": "120.45 KB",
      "number": "+918111922344",
      "sender": "919245657633",
      "total_pages": 5,
      "created_at": {
      "date": "2017-08-01 00:00:00.000000",
      "timezone_type": 3,
      "timezone": "UTC"
      },
      "preview_file": "https://fax.to/receivefax/api/v1/inbox/4/preview?api_key=abd1ebe0-62d5-11e7-91c7-8590f436fefa",
      "file_url": "https://fax.to/receivefax/api/v1/inbox/4/file?api_key=abd1ebe0-62d5-11e7-91c7-8590f436fefa"
    }
  ],
  "meta": {
    "pagination": {
      "total": 7,
      "count": 2,
      "per_page": 2,
      "current_page": 2,
      "total_pages": 4,
      "links": {
        "previous": "https://fax.to/api/v2/incoming-faxes/918111922311?page=1",
        "next": "https://fax.to/api/v2/incoming-faxes/918111922311?page=3"
      }
    }
  }
}
```

## 5. List Countries

The list Countries operation allows you to search for countries available in the Fax.to coverage.

To use the List Countries API:

1. Create a <a href='/docs/fax-receiving/list-countries/request.md' id='list-countries-request' class='anchor' aria-hidden='true'>request</a> and get list of countries:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/countries?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
  CURLOPT_URL => 'https://fax.to/api/v2/countries?api_key=API_KEY'
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
}

url = 'https://fax.to/api/v2/countries?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/countries?api_key=API_KEY")

response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "data": [
    {
      "country": "ARGENTINA",
      "slug": "ARGENTINA",
      "a2_code": "ARG",
      "dial_code": 54
    },
    {
      "country": "AUSTRALIA",
      "slug": "AUSTRALIA",
      "a2_code": "AUS",
      "dial_code": 61
    }
  ]
}
```

## 6. List States

The List States operation allows you to search for states of the given country available in the Fax.to coverage.

To use the List States API:

1. Create a <a href='/docs/fax-receiving/list-states/request.md' id='list-states-request' class='anchor' aria-hidden='true'>request</a> and get list of states:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/states/{COUNTRY_CODE}?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
  CURLOPT_URL => 'https://fax.to/api/v2/states/{COUNTRY_CODE}?api_key=API_KEY'
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
}

url = 'https://fax.to/api/v2/states/{COUNTRY_CODE}?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/states/{COUNTRY_CODE}?api_key=API_KEY")

response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "states" :[
    {
      "id": "1",
      "name": "Alabama",
      "code": "AL",
    },
    {
      "id": "2",
      "name": "Alaska",
      "code": "AK",
    }
  ]
}
```

## 7. List Area Codes

The List Area Codes operation allows you to search for countries available in the Fax.to coverage.

To use the List Area Codes API:

1. Create a <a href='/docs/fax-receiving/list-areacodes/request.md' id='list-areacodes-request' class='anchor' aria-hidden='true'>request</a> and get list of countries:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/areacodes/{COUNTRY_CODE}/{STATE_ID}?api_key=API_KEY'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
  CURLOPT_URL => 'https://fax.to/api/v2/areacodes/{COUNTRY_CODE}/{STATE_ID}?api_key=API_KEY'
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
}

url = 'https://fax.to/api/v2/areacodes/{COUNTRY_CODE}/{STATE_ID}?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/areacodes/{COUNTRY_CODE}/{STATE_ID}?api_key=API_KEY")

response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "areacodes": [
     {
          "country_code": "USA",
          "state_id": 1,
          "area_code": "205"
     },
     {
          "country_code": "USA",
          "state_id": 1,
          "area_code": "251"
     }
   ]
}
```

## 8. List DID Groups

List DID Groups is a method related to Fax.to’s inventory. It allows you to retrieve the list of DID groups. A DID group can be defined as the smallest set of DIDs which is usually DIDs that share the same city or area code attributes. It is a method which is useful to get pricing info on a DID and to get didGroupIds which is a required parameter when placing a Number order.

To use the List DID Groups API:

1. Create a <a href='/docs/fax-receiving/list-did-groups/request.md' id='list-didgroups-request' class='anchor' aria-hidden='true'>request</a> and get list of DID groups:

<ul><details><summary><strong>cURL</strong></summary><p>

```bash
#!/bin/bash
curl -X GET --header 'Content-Type: application/json' 'https://fax.to/api/v2/countries/{COUNTRY_CODE}/didgroups?api_key=API_KEY&didGroupIds=12,34,67&stateId=12&cityNamePattern=New York%&areaCode=204'
```
</p></details></ul>

<ul><details><summary><strong>PHP</strong></summary><p>

```php
<?php

$defaults = [
  CURLOPT_URL => 'https://fax.to/api/v2/countries/{COUNTRY_CODE}/didgroups?api_key=API_KEY&didGroupIds=12,34,67&stateId=12&cityNamePattern=New York%&areaCode=204'
];

$ch = curl_init();
curl_setopt_array($ch, $defaults);

$response = curl_exec($ch);

// Decode the json object you retrieved when you ran the request.
$decodedResponse = json_decode($response, true);
var_dump($decodedResponse);
```
</p></details></ul>

<ul><details><summary><strong>Python</strong></summary><p>

```python
import urllib

params = {
    'api_key': 'API_KEY'
    'didGroupIds': '12, 34, 67'
    'stateId': '12'
    'cityPattern': 'New York%'
    'areaCode': '204'
}

url = 'https://fax.to/api/v2/countries/{COUNTRY_CODE}/didgroups?' + urllib.urlencode(params)
response = urllib.urlopen(url)
print response.read()
```
</p></details></ul>

<ul><details><summary><strong>Ruby</strong></summary><p>

```ruby
require "net/http"
require "uri"

uri = URI.parse("https://fax.to/api/v2/countries/{COUNTRY_CODE}/didgroups?api_key=API_KEY&didGroupIds=12,34,67&stateId=12&cityNamePattern=New York%&areaCode=204")

response = Net::HTTP.get(uri)

puts response
```
</p></details></ul>

#### Example Response

```json
{
  "status": "success",
  "data": [
    {
      "did_group_id": 67,
      "area_code": "204",
      "city_name": "WINNIPEG"
    },
    {
      "did_group_id": 13868,
      "area_code": "226",
      "city_name": "WINDSOR"
    },
    {
      "did_group_id": 9581,
      "area_code": "289",
      "city_name": "WOODBRIDGE"
    },
    {
      "did_group_id": 20287,
      "area_code": "306",
      "city_name": "SASKATOON"
    }
  ]
}
```

<br>

# Fax Receive Callback

When your fax number received a fax message, We send a POST callback to the URL specified in your API settings:

Below is the table for keys and values we send on your URL

## Keys and Values

<table>
    <tr>
        <th><strong>Key</strong></th>
        <th><strong>Value</strong></th>
        <th><strong>Response Type</strong></th>
    </tr>
    <tr>
      <td>uuid</td>
      <td>Unique ID for request</td>
      <td>text</td>
    </tr>
    <tr>
      <td>from</td>
      <td>The sender of the fax</td>
      <td>text</td>
    </tr>
    <tr>
      <td>to</td>
      <td>The receiver of the fax(Your fax number itself)</td>
      <td>text</td>
    </tr>
    <tr>
      <td>time</td>
      <td>Time when the fax was received</td>
      <td>text</td>
    </tr>
    <tr>
      <td>file</td>
      <td>The file in PDF form</td>
      <td>text</td>
    </tr>
    <tr>
      <td>rsid</td>
      <td>RSID</td>
      <td>text</td>
    </tr>
    <tr>
      <td>speed</td>
      <td></td>
      <td>text</td>
    </tr>
    <tr>
      <td>duration</td>
      <td></td>
      <td>text</td>
    </tr>
    <tr>
      <td>ecm</td>
      <td></td>
      <td>text</td>
    </tr>
    <tr>
      <td>pages</td>
      <td>Number of pages of the fax</td>
      <td>text</td>
    </tr>
    <tr>
      <td>compression</td>
      <td>Type of compression</td>
      <td>text</td>
    </tr>
</table>

[Checkout](#callback) how you can manage the POST data
<br>
You can also test the POST data so that you know how it looks [here](https://api.fax.to/settings)

<br>

# API Reference

This defines the Fax API:

* [Request](#request) - send a fax.
* [Response](#response) - ensure that your request to the Fax API was successful.
* [Webhook](#webhook) - check that your user received your message.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/fax?api_key=xxxxx&fax_number=xxxxxx&document_id=xxxxxxx
```
This request contains:

* [Parameters](#parameters)
* [Authentication information](#authentication-information)
* [Security](#security)
* [Encoding](#encoding)

## Parameters

| **Parameter** | **Description**                                                                                      | **Required** |
| ------------- | ---------------------------------------------------------------------------------------------------- | ------------ |
| fax_number    | Fax Number. For example, **```fax_number=+123456789```**.                                                | Yes          |
| document_id   | If you want to use existing document you need to specify the document_id. For example, **```document_id=10```**. | Yes  |

## Authentication information

The following table shows the information for authentication:

| **Parameter** | **Description**                                                                                      | **Required** |
| ------------- | ---------------------------------------------------------------------------------------------------- | ------------ |
| api_key       | Your Key. For example, **```api_key=f@x2r0ckkz```**.                                                 | Yes          |

<br>

You find your Key in [Dashboard](https://api.fax.to/dashboard).

## Security

To ensure privacy, you must use HTTPS for all Fax.to API requests.

## Encoding

You submit all requests with a POST or GET call using UTF-8 encoding and URL encoded values.

## Response

We support JSON ONLY responses

```json
{
  "status": "executed",
  "fax_job_id": 200,
  "user_cash_balance": 100,
  "cost": 0.15
}
```

## Keys and Values

<table>
    <tr>
        <th><strong>Key</strong></th>
        <th><strong>Value</strong></th>
        <th><strong>Response Type</strong></th>
    </tr>
    <tr>
        <td>status</td>
        <td>
            <table>
                <tr>
                    <td><strong>Text</strong></td>
                    <td><strong>Meaning</strong></td>
                </tr>
                <tr>
                    <td>executed</td>
                    <td>The fax job is executed and in the process of sending</td>
                </tr>
                <tr>
                    <td>failed</td>
                    <td>Failed to send the fax</td>
                </tr>
            </table>
        </td>
        <td>JSON</td>
    </tr>
    <tr>
      <td>fax_job_id</td>
      <td>The Fax Job ID. You can use the fox_job_id to check the status of the fax job.</td>
      <td>JSON</td>
    </tr>
    <tr>
      <td>user_cash_balance</td>
      <td>The remaining cash balance</td>
      <td>JSON</td>
    </tr>
    <tr>
      <td>cost</td>
      <td>The cost of sending fax</td>
      <td>JSON</td>
    </tr>
</table>

## Webhook

Notifications are delivered via HTTP POST request to Callback URL you specified in [API Settings](https://api.fax.to/settings). Fax.to will be expecting response 200 OK in return, or it will keep retrying every 15 minutes until the Delivery Receipt expires (up to 48 hours) . Fax.to send POST data with the following information:

<table>
    <tr>
        <th><strong>Key</strong></th>
        <th><strong>Value</strong></th>
    </tr>
    <tr>
      <td>fax_job_id</td>
      <td>The Fax Job ID. You can use the fox_job_id to check the status of the fax job.</td>
    </tr>
    <tr>
      <td>status</td>
      <td>The Status of the Fax Job. Either <code><strong>success</strong></code> or <code><strong>failed</strong></code></td>
    </tr>
    <tr>
        <td>msg_code</td>
        <td>
            <table>
                <tr>
                    <td><strong>Text</strong></td>
                    <td><strong>Meaning</strong></td>
                </tr>
                <tr>
                    <td>ok</td>
                    <td>Success! Your fax has been sent!</td>
                </tr>
                <tr>
                    <td>unknown</td>
                    <td>Fax Failed - Unknown Error (We don’t know exactly what went wrong - contact us for more info)</td>
                </tr>
                <tr>
                    <td>no_answer</td>
                    <td>Fax Failed - No Answer from Fax machine</td>
                </tr>
                <tr>
                    <td>busy</td>
                    <td>Fax Failed - Line Busy (The fax machine could be busy)</td>
                </tr>
                <tr>
                    <td>file_error</td>
                    <td>Fax Failed - File conversion failed. Re-upload and Retry</td>
                </tr>
                <tr>
                    <td>hangup</td>
                    <td>Fax Failed - Early Hangup</td>
                </tr>
            </table>
        </td>
    </tr>
</table>
<br>

[Checkout](#callback) how you can manage the POST data
