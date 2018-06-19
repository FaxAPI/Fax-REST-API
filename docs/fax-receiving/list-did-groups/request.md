<a href="#"><img width="15px" height="15px" src="https://image.flaticon.com/icons/svg/1/1453.svg" /> <a href="./../../../README.md#8-list-did-groups"> Go back</a></a>

<h1 align="center">List DID Groups API Reference</h1>

This defines the List DID Groups API:

* [Request](#request) - Get list of DID groups.
* [Response](#response) - ensure that your request to the Fax API was successful.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/countries/{COUNTRY_CODE}/didgroups?api_key=xxxxx&didGroupIds=12,34,67&stateId=12&cityNamePattern=New York%&areaCode=204
```
This request contains:

* [Parameters](#parameters)
* [Authentication information](#authentication-information)
* [Security](#security)
* [Encoding](#encoding)

## Parameters

The following table shows the parameters you use in the request:

| **Parameter**   | **Description**                                                                                     | **Required** |
| --------------- | --------------------------------------------------------------------------------------------------- | ------------ |
| COUNTRY_CODE    | Indicates the country code in its ISO 3166-1 alpha-3 format (e.g. “GBR” for United Kingdom, “USA” for United States of America, “BEL” for Belgium, etc.). For example, **```CAN```** for Canada.                                                                                               | Yes          |
| didGroupIds     | Can be used if you want information about specific DID groups. Note that you can specify multiple ids by supplying comma separated didGroupIds in the query parameter. For example, **```didGroupIds=123,1245,456```**.                                                                        | No           |
| stateId         | The numerical identifier for the didGroup's state. Please see the listState operation to retrieve a valid state identifier. For example, **```stateId=10```**.                                                                                                   | No           |
| cityNamePattern | A string pattern for the beginning of city name: "New York%" will return all New York DID groups. On the contrary, "w York%" will return none. For example, **```cityNamePattern=New York%```**.                                                                                    | No           |
| areaCode        | The area code of the DID group. For example, **```areaCode=204```**.                                | No           |

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
  "data": [
    {
      "did_group_id": 67,
      "area_code": "204",
      "city_name": "WINNIPEG"
    },
    {
      "did_group_id": 13868,
      "area_code": "226",
      "city_name": "WINDSOR"
    },
    {
      "did_group_id": 9581,
      "area_code": "289",
      "city_name": "WOODBRIDGE"
    },
    {
      "did_group_id": 20287,
      "area_code": "306",
      "city_name": "SASKATOON"
    }
  ]
}
```

## Keys and Values

| **Key**           | **Value**                                                               | **Response Type** |
| ----------------- | ----------------------------------------------------------------------- | ----------------- |
| status            | The status of the API request                                           | string            |
| data              | Array containing DID groups                                             | array             |

## Response Messages

| **HTTP Status Code** | **Reason**            |
| -------------------- | --------------------- |
| 200                  | Successful Response   |
| 401                  | Unauthorized          |
| 403                  | Rate Limit Exceeded   |
| 404                  | Resource Not Found    |
| 500                  | Internal Server Error |
