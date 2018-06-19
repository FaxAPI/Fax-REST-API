<a href="#"><img width="15px" height="15px" src="https://image.flaticon.com/icons/svg/1/1453.svg" /> <a href="./../../../README.md#2-user-login-api"> Go back</a></a>

<h1 align="center">User Login API Reference</h1>

This defines the User Login API:

* [Request](#request) - Login a user.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/user/login
```
This request contains:

* [Parameters](#parameters)
* [Security](#security)
* [Encoding](#encoding)

## Parameters

The following table shows the parameters you use in the request:

| **Parameter** | **Description**                                                                                      | **Required** |
| ------------- | ---------------------------------------------------------------------------------------------------- | ------------ |
| email         | The unique email of the user.                                                                        | Yes          |
| password      | The password of the registered user                                                                  | Yes          |

## Security

To ensure privacy, you must use HTTPS for all Fax.to API requests.

## Encoding

You submit all requests with a POST or GET call using UTF-8 encoding and URL encoded values.

## Response

We support JSON ONLY responses

```json
{
  "status": "success",
  "api_key": "f1a99500-7ce0-11e7-9fb1-0580e1fcb90c"
}
```

## Keys and Values

| **Key** | **Value**                           | **Response Type** |
| ------- | ----------------------------------- | ----------------- |
| status  | The status of the API request       | string            |
| api_key | The API key of the registered user  | string            |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
