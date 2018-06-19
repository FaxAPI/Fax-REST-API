<a href="#"><img width="15px" height="15px" src="https://image.flaticon.com/icons/svg/1/1453.svg" /> <a href="./../../../README.md#3-fax-status-api"> Go back</a></a>

<h1 align="center">Fax Status API Reference</h1>

This defines the Fax Status API:

* [Request](#request) - Get fax status.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/fax/{fax_job_id}/status?api_key=xxxxx
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
| fax_job_id    | Fax Job ID. The id that you get when you request FAX API                                             | Yes          |

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
  "message": "Sent! Fax Has Been Answered.",
  "user_cash_balance": 100.20
}
```

## Keys and Values

| **Key**           | **Value**                                             | **Response Type** |
| ----------------- | ----------------------------------------------------- | ----------------- |
| status            | The status of the API request                         | string            |
| message           | The message about the fax job                         | string            |
| user_cash_balance | Remaining cash balance                                | decimal           |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
