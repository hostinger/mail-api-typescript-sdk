# QuotaApi

All URIs are relative to *https://api.mail.hostinger.com*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getQuota**](#getquota) | **GET** /api/v1/mailboxes/{mailboxResourceId}/quota | Get mailbox quota|

# **getQuota**
> V1QuotaResource getQuota()

Retrieve storage and message quota usage for the managed mailbox.

### Example

```typescript
import {
    QuotaApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new QuotaApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)

const { status, data } = await apiInstance.getQuota(
    mailboxResourceId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|


### Return type

**V1QuotaResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Mailbox quota usage. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

