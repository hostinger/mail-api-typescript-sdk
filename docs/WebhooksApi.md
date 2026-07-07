# WebhooksApi

All URIs are relative to *https://api.mail.hostinger.com*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**createWebhook**](#createwebhook) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks | Create webhook|
|[**deleteWebhook**](#deletewebhook) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Delete webhook|
|[**getWebhook**](#getwebhook) | **GET** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Get webhook|
|[**listWebhooks**](#listwebhooks) | **GET** /api/v1/mailboxes/{mailboxResourceId}/webhooks | List webhooks|
|[**regenerateWebhookSecret**](#regeneratewebhooksecret) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook}/regenerate-secret | Regenerate webhook secret|
|[**testWebhook**](#testwebhook) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook}/test | Test webhook|
|[**updateWebhook**](#updatewebhook) | **PATCH** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Update webhook|

# **createWebhook**
> V1WebhooksResourceWithSecret createWebhook(v1WebhooksCreateRequest)

Create a webhook. The response includes the one-time `secret` — store it securely as it is never returned again.

### Example

```typescript
import {
    WebhooksApi,
    Configuration,
    V1WebhooksCreateRequest
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new WebhooksApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let v1WebhooksCreateRequest: V1WebhooksCreateRequest; //

const { status, data } = await apiInstance.createWebhook(
    mailboxResourceId,
    v1WebhooksCreateRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1WebhooksCreateRequest** | **V1WebhooksCreateRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|


### Return type

**V1WebhooksResourceWithSecret**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**201** | Webhook created. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteWebhook**
> deleteWebhook()

Delete a webhook.

### Example

```typescript
import {
    WebhooksApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new WebhooksApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox. (default to undefined)
let webhook: string; //Webhook identifier (UUID v7). (default to undefined)

const { status, data } = await apiInstance.deleteWebhook(
    mailboxResourceId,
    webhook
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox. | defaults to undefined|
| **webhook** | [**string**] | Webhook identifier (UUID v7). | defaults to undefined|


### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**204** | Webhook deleted. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getWebhook**
> V1WebhooksResource getWebhook()

Retrieve a single webhook by id.

### Example

```typescript
import {
    WebhooksApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new WebhooksApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox. (default to undefined)
let webhook: string; //Webhook identifier (UUID v7). (default to undefined)

const { status, data } = await apiInstance.getWebhook(
    mailboxResourceId,
    webhook
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox. | defaults to undefined|
| **webhook** | [**string**] | Webhook identifier (UUID v7). | defaults to undefined|


### Return type

**V1WebhooksResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Webhook payload. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listWebhooks**
> V1WebhooksCollection listWebhooks()

List webhooks for a mailbox.

### Example

```typescript
import {
    WebhooksApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new WebhooksApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let status: 'active' | 'paused' | 'disabled'; // (optional) (default to undefined)
let page: number; // (optional) (default to 1)
let perPage: number; // (optional) (default to 15)

const { status, data } = await apiInstance.listWebhooks(
    mailboxResourceId,
    status,
    page,
    perPage
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **status** | [**&#39;active&#39; | &#39;paused&#39; | &#39;disabled&#39;**]**Array<&#39;active&#39; &#124; &#39;paused&#39; &#124; &#39;disabled&#39;>** |  | (optional) defaults to undefined|
| **page** | [**number**] |  | (optional) defaults to 1|
| **perPage** | [**number**] |  | (optional) defaults to 15|


### Return type

**V1WebhooksCollection**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Paginated list of webhooks. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **regenerateWebhookSecret**
> V1WebhooksResourceWithSecret regenerateWebhookSecret()

Regenerate the webhook secret. The previous secret is immediately invalidated. The new secret is returned once.

### Example

```typescript
import {
    WebhooksApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new WebhooksApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox. (default to undefined)
let webhook: string; //Webhook identifier (UUID v7). (default to undefined)

const { status, data } = await apiInstance.regenerateWebhookSecret(
    mailboxResourceId,
    webhook
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox. | defaults to undefined|
| **webhook** | [**string**] | Webhook identifier (UUID v7). | defaults to undefined|


### Return type

**V1WebhooksResourceWithSecret**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Webhook with new secret. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **testWebhook**
> V1WebhooksTestResult testWebhook()

Send a test delivery to the webhook URL and return the upstream response.

### Example

```typescript
import {
    WebhooksApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new WebhooksApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox. (default to undefined)
let webhook: string; //Webhook identifier (UUID v7). (default to undefined)

const { status, data } = await apiInstance.testWebhook(
    mailboxResourceId,
    webhook
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox. | defaults to undefined|
| **webhook** | [**string**] | Webhook identifier (UUID v7). | defaults to undefined|


### Return type

**V1WebhooksTestResult**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Test delivery result. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **updateWebhook**
> V1WebhooksResource updateWebhook(v1WebhooksUpdateRequest)

Partially update a webhook.

### Example

```typescript
import {
    WebhooksApi,
    Configuration,
    V1WebhooksUpdateRequest
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new WebhooksApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox. (default to undefined)
let webhook: string; //Webhook identifier (UUID v7). (default to undefined)
let v1WebhooksUpdateRequest: V1WebhooksUpdateRequest; //

const { status, data } = await apiInstance.updateWebhook(
    mailboxResourceId,
    webhook,
    v1WebhooksUpdateRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1WebhooksUpdateRequest** | **V1WebhooksUpdateRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox. | defaults to undefined|
| **webhook** | [**string**] | Webhook identifier (UUID v7). | defaults to undefined|


### Return type

**V1WebhooksResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Updated webhook. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

