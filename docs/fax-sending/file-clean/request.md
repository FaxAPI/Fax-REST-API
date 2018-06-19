<a href="#"><img width="15px" height="15px" src="https://image.flaticon.com/icons/svg/1/1453.svg" /> <a href="./../../../README.md#6-clean-file-api"> Go back</a></a>

<h1 align="center">File Clean API Reference</h1>

This defines the File Clean API:

* [Request](#request) - to clean file.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/file-clean?document_id=DOCUMENT_ID&api_key=API_KEY
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
| document_id   | Your document_id. For example **```document_id=327```**.                                             | Yes          |

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
  "user_id":1,
  "created date": "2017-08-29 07:18:05",
  "id": 327,
  "filename": "59a5152b95cc1.pdf.tiff",
  "orig_filename": "59a5152b95cc1.pdf",
  "preview_file": "9a5152b95cc1.pdf.preview.jpg",
  "preview_image":null,
  "preview_in_storage":1,
  "file_extension":"pdf",
  "filename_uploaded":"pdf-sample.pdf",
  "filesize":"485432",
  "s3": null,
  "server_document_id": null,
  "team_user_id": null,
  "total_pages":1,
  "updated_at":"2017-08-29 07:18:05"
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
