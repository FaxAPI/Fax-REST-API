<a href="#"><img width="15px" height="15px" src="https://image.flaticon.com/icons/svg/1/1453.svg" /> <a href="./../../../README.md#1-send-fax-api"> Go back</a></a>

<h1 align="center">API Reference</h1>

This defines the Fax API:

* [Request](#request) - send a fax.
* [Response](#response) - ensure that your request to the Fax API was successful.
* [Webhook](#webhook) - check that your user received your message.

## Request

A Fax API request looks like:
```diff
- https://fax.to/api/v2/fax?api_key=xxxxx&fax_number=xxxxxx&document_id=xxxxxxx
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
| fax_number    | Fax Number. For example, **```fax_number=+123456789```**.                                            | Yes          |
| document_id   | If you want to use existing document you need to specify the document_id. For example, **```document_id=10```**. | Yes  |

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
  "status": "executed",
  "fax_job_id": 200,
  "user_cash_balance": 100,
  "cost": 0.15
}
```

## Keys and Values

<table>
    <tr>
        <th><strong>Key</strong></th>
        <th><strong>Value</strong></th>
        <th><strong>Response Type</strong></th>
    </tr>
    <tr>
        <td>status</td>
        <td>
            <table>
                <tr>
                    <td><strong>Text</strong></td>
                    <td><strong>Meaning</strong></td>
                </tr>
                <tr>
                    <td>executed</td>
                    <td>The fax job is executed and in the process of sending</td>
                </tr>
                <tr>
                    <td>failed</td>
                    <td>Failed to send the fax</td>
                </tr>
            </table>
        </td>
        <td>string</td>
    </tr>
    <tr>
      <td>fax_job_id</td>
      <td>The Fax Job ID. You can use the fox_job_id to check the status of the fax job.</td>
      <td>integer</td>
    </tr>
    <tr>
      <td>user_cash_balance</td>
      <td>The remaining cash balance</td>
      <td>decimal</td>
    </tr>
    <tr>
      <td>cost</td>
      <td>The cost of sending fax</td>
      <td>decimal</td>
    </tr>
</table>

## Webhook

Notifications are delivered via HTTP POST request to Callback URL you specified in [API Settings](/docs/api-reference/api-settings.md). Fax.to will be expecting response 200 OK in return, or it will keep retrying every 15 minutes until the Delivery Receipt expires (up to 48 hours) . Fax.to send POST data with the following information:

<table>
    <tr>
        <th><strong>Key</strong></th>
        <th><strong>Value</strong></th>
    </tr>
    <tr>
      <td>fax_job_id</td>
      <td>The Fax Job ID. You can use the fox_job_id to check the status of the fax job.</td>
    </tr>
    <tr>
      <td>status</td>
      <td>The Status of the Fax Job. Either <strong>```success```</strong> or <strong>```failed```</strong></td>
    </tr>
    <tr>
        <td>msg_code</td>
        <td>
            <table>
                <tr>
                    <td><strong>Text</strong></td>
                    <td><strong>Meaning</strong></td>
                </tr>
                <tr>
                    <td>ok</td>
                    <td>Success! Your fax has been sent!</td>
                </tr>
                <tr>
                    <td>unknown</td>
                    <td>Fax Failed - Unknown Error ( We don’t know exactly what went wrong - contact us for more info )</td>
                </tr>
                <tr>
                    <td>no_answer</td>
                    <td>Fax Failed - No Answer from Fax machine</td>
                </tr>
                <tr>
                    <td>busy</td>
                    <td>Fax Failed - Line Busy ( The fax machine could be busy )</td>
                </tr>
                <tr>
                    <td>file_error</td>
                    <td>Fax Failed - File conversion failed. Re-upload and Retry</td>
                </tr>
                <tr>
                    <td>hangup</td>
                    <td>Fax Failed - Early Hangup</td>
                </tr>
            </table>
        </td>
    </tr>
</table>
