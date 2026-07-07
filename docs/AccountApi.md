# AccountApi

All URIs are relative to *https://api.mail.hostinger.com*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getCurrentAccount**](#getcurrentaccount) | **GET** /api/v1/me | Get the authenticated account|

# **getCurrentAccount**
> V1MeResource getCurrentAccount()

Returns the authenticated account and the mailboxes it can manage.

### Example

```typescript
import {
    AccountApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new AccountApi(configuration);

const { status, data } = await apiInstance.getCurrentAccount();
```

### Parameters
This endpoint does not have any parameters.


### Return type

**V1MeResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Authenticated account with the mailboxes the API key can manage. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

