<a href="#"><img width="15px" height="15px" src="https://image.flaticon.com/icons/svg/1/1453.svg" /> <a href="./../../../README.md#4-fax-history-api"> Go back</a></a>

<h1 align="center">Fax History API Reference</h1>

This defines the Fax History API:

* [Request](#request) - Get fax history.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/fax?api_key=xxxxx&limit=xx&page=xx
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
    },
    {
      "id": 92322,
      "created": {
        "date": "2017-03-09 15:05:36.000000",
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

## Keys and Values

| **Key**           | **Value**                                             | **Response Type** |
| ----------------- | ----------------------------------------------------- | ----------------- |
| status            | The status of the API request                         | string            |
| history           | Array containing the fax jobs requested               | array             |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
