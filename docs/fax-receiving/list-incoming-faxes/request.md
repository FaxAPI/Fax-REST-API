<a href="#"><img width="15px" height="15px" src="https://image.flaticon.com/icons/svg/1/1453.svg" /> <a href="./../../../README.md#3-list-incoming-faxes"> Go back</a></a>

<h1 align="center">List Incoming Faxes API Reference</h1>

This defines the List of Incoming Faxes API:

* [Request](#request) - Get list of incoming faxes.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/numbers?api_key=xxxxx
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
| limit         | The number of record to return. For example, **```limit=10```**.                                      | No           |
| page          | The page you want to get. Basically its pagination. For example, **```page=1```**.                    | No           |

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
  "inbox": [
   {
    "id": 772,
      "did_id": 7745147,
      "filename": "597ef3a78a2dd.pdf",
      "filesize": "120.45 KB",
      "number": "+918111922344",
      "sender": "919245657633",
      "total_pages": 5,
      "created_at": {
	  	"date": "2017-08-01 00:00:00.000000",
		"timezone_type": 3,
		"timezone": "UTC"
		},
	 "preview_file": "https://fax.to/receivefax/api/v1/inbox/4/preview?api_key=abd1ebe0-62d5-11e7-91c7-8590f436fefa",
	  "file_url": "https://fax.to/receivefax/api/v1/inbox/4/file?api_key=abd1ebe0-62d5-11e7-91c7-8590f436fefa"
    },
    {
      "id": 771,
      "did_id": 7745147,
      "filename": "597ef3a78a2dd.pdf",
      "filesize": "120.45 KB",
      "number": "+918111922344",
      "sender": "919245657633",
      "total_pages": 5,
      "created_at": {
	  	"date": "2017-08-01 00:00:00.000000",
		"timezone_type": 3,
		"timezone": "UTC"
		},
	  "preview_file": "https://fax.to/receivefax/api/v1/inbox/4/preview?api_key=abd1ebe0-62d5-11e7-91c7-8590f436fefa",
	  "file_url": "https://fax.to/receivefax/api/v1/inbox/4/file?api_key=abd1ebe0-62d5-11e7-91c7-8590f436fefa"
    }
  ],
  "meta": {
    "pagination": {
      "total": 7,
      "count": 2,
      "per_page": 2,
      "current_page": 2,
      "total_pages": 4,
      "links": {
        "previous": "https://fax.to/api/v2/incoming-faxes?page=1",
        "next": "https://fax.to/api/v2/incoming-faxes?page=3"
      }
    }
  }
}
```

## Keys and Values

| **Key**           | **Value**                                                               | **Response Type** |
| ----------------- | ----------------------------------------------------------------------- | ----------------- |
| status            | The status of the API request                                           | string            |
| inbox             | Array containing the faxes received by a certain user                   | array             |
| meta	            | Object containing paginations links                                     | object            |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
