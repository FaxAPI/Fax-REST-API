# Fax-REST-API
This is the Fax REST API documentation for Fax.to Fax API

## List States API Reference

This defines the List States API:

* [Request](#request) - Get list of states.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/states/{COUNTRY_CODE}?api_key=API_KEY
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
| COUNTRY_CODE  | Indicates the country code in its ISO 3166-1 alpha-3 format (e.g. “GBR” for United Kingdom, “USA” for United States of America, “BEL” for Belgium, etc.). For example, **```CAN```** for Canada.                                                                                              | Yes          |

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
  "states": [
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

## Keys and Values

| **Key**           | **Value**                                                               | **Response Type** |
| ----------------- | ----------------------------------------------------------------------- | ----------------- |
| status            | The status of the API request                                           | string            |
| states            | Array containing states                                                 | array             |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
