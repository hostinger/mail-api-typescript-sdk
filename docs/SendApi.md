# SendApi

All URIs are relative to *https://api.mail.hostinger.com*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**sendEmail**](#sendemail) | **POST** /api/v1/mailboxes/{mailboxResourceId}/send | Send email|

# **sendEmail**
> sendEmail(v1SendRequest)

Send a message from the managed mailbox. Saves a copy to INBOX.Sent.

### Example

```typescript
import {
    SendApi,
    Configuration,
    V1SendRequest
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new SendApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let v1SendRequest: V1SendRequest; //

const { status, data } = await apiInstance.sendEmail(
    mailboxResourceId,
    v1SendRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1SendRequest** | **V1SendRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|


### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**204** | Message sent and saved to sent folder. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

