# Fax-REST-API
This is the Fax REST API documentation for Fax.to Fax API

## Delete Files API Reference

This defines the Delete File API:

* [Request](#request) - Delete a file.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/files/{document_id}?api_key=xxxxx
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
| document_id   | The document ID you wish to delete.                                                                  | Yes          |

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
  "status":  "success"
}
```

## Keys and Values

| **Key**           | **Value**                                                               | **Response Type** |
| ----------------- | ----------------------------------------------------------------------- | ----------------- |
| status            | The status of the API request                                           | string            |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
