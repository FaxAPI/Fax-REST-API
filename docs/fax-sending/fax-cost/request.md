# Fax-REST-API
This is the Fax REST API documentation for Fax.to Fax API

## Fax Cost API Reference

This defines the Fax Cost API:

* [Request](#request) - Get the cost of fax.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/fax/{document_id}/costs?api_key=xxxxx&fax_number+123456789
```
This request contains:

* [Parameters](#parameters)
* [Authentication information](#authentication-information)
* [Security](#security)
* [Encoding](#encoding)

## Parameters

The following table shows the parameters you use in the request:

| **Parameter** | **Description**                                                                                            | **Required** |
| ------------- | ---------------------------------------------------------------------------------------------------------- | ------------ |
| fax_number    | Fax Number. For example, **```fax_number=+123456789```**.                                                  | Yes          |
| document_id   | If you want to use existing document you need to specify the document_id. For example, **```document_id=10```**. | Yes    |

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
  "cost": 0.10
}
```

## Keys and Values

| **Key** | **Value**                                             | **Response Type** |
| ------- | ----------------------------------------------------- | ----------------- |
| status  | The status of the API request                         | string            |
| cost    | The cost of fax for the fax number specified          | decimal           |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
