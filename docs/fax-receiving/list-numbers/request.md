<a href="#"><img width="15px" height="15px" src="https://image.flaticon.com/icons/svg/1/1453.svg" /> <a href="./../../../README.md#2-list-numbers"> Go back</a></a>

<h1 align="center">List Numbers API Reference</h1>

This defines the List Numbers API:

* [Request](#request) - Get list of numbers.
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
  "numbers": [
    {
      "id": 775,
      "order_reference": null,
      "country_code": "CAN",
      "country": "CANADA",
      "city_name": null,
      "area_code": "204",
      "did_group_id": 67,
      "did_number": "+12048134699",
      "expiration_date": "2017-07-30",
      "status": "Active"
    },
    {
      "id": 776,
      "order_reference": null,
      "country_code": "CAN",
      "country": "CANADA",
      "city_name": null,
      "area_code": "204",
      "did_group_id": 67,
      "did_number": "+12048134700",
      "expiration_date": "2017-07-30",
      "status": "Active"
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
        "previous": "https://fax.to/api/v2/numbers?page=1",
        "next": "https://fax.to/api/v2/numbers?page=3"
      }
    }
  }
}
```

## Keys and Values

| **Key**           | **Value**                                                               | **Response Type** |
| ----------------- | ----------------------------------------------------------------------- | ----------------- |
| status            | The status of the API request                                           | string            |
| numbers           | Array containing numbers                                                | array             |
| meta	            | Object containing paginations links                                     | object            |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
