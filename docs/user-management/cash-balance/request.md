# Fax-REST-API
This is the Fax REST API documentation for Fax.to Fax API

## Cash Balance API Reference

This defines the Cash Balance API:

* [Request](#request) - Get Cash Balance.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/balance?api_key=xxxxx
```
This request contains:

* [Authentication information](#authentication-information)
* [Security](#security)
* [Encoding](#encoding)

## Authentication information

The following table shows the information for authentication:

| **Parameter** | **Description**                                                                                      | **Required** |
| ------------- | ---------------------------------------------------------------------------------------------------- | ------------ |
| api_key       | Your Key. For example, **```api_key=f@x2r0ckkz```**.                                                     | Yes          |

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
  "balance": 100.00
}
```

## Keys and Values

| **Key** | **Value**                           | **Response Type** |
| ------- | ----------------------------------- | ----------------- |
| status  | The status of the API request       | string            |
| balance | The remaining cash balance          | decimal           |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
