<a href="#"><img width="15px" height="15px" src="https://image.flaticon.com/icons/svg/1/1453.svg" /> <a href="./../../../README.md#8-get-files-api"> Go back</a></a>

<h1 align="center">Get Files API Reference</h1>

This defines the Get Files API:

* [Request](#request) - Get list of files.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/files?api_key=xxxxx&limit=xx&page=xx
```
This request contains:

* [Parameters](#parameters)
* [Authentication information](#authentication-information)
* [Security](#security)
* [Encoding](#encoding)

## Parameters

The following table shows the parameters you use in the request:

| **Parameter** | **Description**                                                                                      | **Required** |
| ------------- | ---------------------------------------------------------------------------------------------------- | ------------ |
| limit         | The number of record to return. For example, **```limit=10```**.                                     | No           |
| page          | The page you want to get. Basically its pagination. For example, **```page=1```**.                   | No           |

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
[
  {
    "id": 6530,
    "filename": "Invoice_60037308.pdf",
    "pages": 2,
    "size": 156681,
    "uploaded": "2016-01-22"
  },
  {
    "id": 19046,
    "filename": "Certificate.PDF",
    "pages": 1,
    "size": 53665,
    "uploaded": "2016-04-11"
  }
]
```

## Keys and Values

| **Key**           | **Value**                                                               | **Response Type** |
| ----------------- | ----------------------------------------------------------------------- | ----------------- |
|                   | Array containing files                                                  | array             |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
