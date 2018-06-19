<a href="#"><img width="15px" height="15px" src="https://image.flaticon.com/icons/svg/1/1453.svg" /> <a href="./../../../README.md#1-provision-numbers"> Go back</a></a>

<h1 align="center">Provision Numbers API Reference</h1>

This defines the Provision Numbers API:

* [Request](#request) - Provision a Fax number.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/countries/didgroups/{did_group_id}/provision?api_key=API_KEY
```
This request contains:

* [Parameters](#parameters)
* [Authentication information](#authentication-information)
* [Security](#security)
* [Encoding](#encoding)

## Parameters

The following table shows the parameters you use in the request:

| **Parameter** | **Description**                                                                                       | **Required** |
| ------------- | ----------------------------------------------------------------------------------------------------- | ------------ |
| did_group_id  | To get a did_group_id, call API [List DID groups](../readme.md#list-did-groups)                       | Yes          |

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
  "message": "Number has been provisioned.",
  "data": {
    "id": 782,
    "didid": 6283433,
    "did_group_id": 67,
    "country_code": "CAN",
    "city_name": "WINNIPEG",
    "area_code": "204",
    "number": "+12048134698",
    "type": "GEOGRAPHIC",
    "trunk_id": 8934
  }
}
```

## Keys and Values

| **Key**           | **Value**                                                               | **Response Type** |
| ----------------- | ----------------------------------------------------------------------- | ----------------- |
| status            | The status of the API request                                           | string            |
| message           | The complete description of the status                                  | string            |
| data	            | Object containing the number data                                       | object            |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
