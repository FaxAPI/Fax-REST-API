# Fax-REST-API
This is the Fax REST API documentation for Fax.to Fax API

## Upload File API Reference

This defines the Upload File API:

* [Request](#request) - File upload.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/files?api_key=xxxxx
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
| AddRemoteFile | The Remote File URL                                                                                  | Yes          |

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
	"status": "Success",
	"document_id": 300,
	"total_pages": 1,
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
	"id": 300
	}
}
```

## Keys and Values

| **Key**           | **Value**                                                               | **Response Type** |
| ----------------- | ----------------------------------------------------------------------- | ----------------- |
| status            | The status of the API request                                           | string            |
| document_id       | The document ID stored. Use this document_id when sending Fax using API | integer           |
| total_pages       | The number of pages stored                                              | integer           |
| document          | Object containing document details                                      | object            |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
