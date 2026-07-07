# MessagesApi

All URIs are relative to *https://api.mail.hostinger.com*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**deleteAllMessages**](#deleteallmessages) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages | Delete all messages|
|[**deleteMessage**](#deletemessage) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Delete message|
|[**deleteMessages**](#deletemessages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/delete | Delete messages|
|[**getMessage**](#getmessage) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Get message|
|[**getMessageAttachment**](#getmessageattachment) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/attachments/{attachmentId} | Download message attachment|
|[**getMessageSource**](#getmessagesource) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/source | Get message source|
|[**getMessageText**](#getmessagetext) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/text | Get message text content|
|[**listMessages**](#listmessages) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages | List messages|
|[**moveMessage**](#movemessage) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/move | Move message|
|[**moveMessages**](#movemessages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/move | Move messages|
|[**patchMessage**](#patchmessage) | **PATCH** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Update message flags|
|[**searchMessages**](#searchmessages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/search | Search messages|
|[**updateMessageFlags**](#updatemessageflags) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/flags | Update message flags|

# **deleteAllMessages**
> deleteAllMessages()

Permanently delete every message in a folder (empty the folder).

### Example

```typescript
import {
    MessagesApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Folder path (URL-encoded). (default to undefined)

const { status, data } = await apiInstance.deleteAllMessages(
    mailboxResourceId,
    folder
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Folder path (URL-encoded). | defaults to undefined|


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
|**204** | Messages deleted successfully. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteMessage**
> deleteMessage()

Permanently delete a single message.

### Example

```typescript
import {
    MessagesApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Folder path (URL-encoded). (default to undefined)
let uid: number; //Message UID. (default to undefined)

const { status, data } = await apiInstance.deleteMessage(
    mailboxResourceId,
    folder,
    uid
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Folder path (URL-encoded). | defaults to undefined|
| **uid** | [**number**] | Message UID. | defaults to undefined|


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
|**204** | Message deleted successfully. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteMessages**
> deleteMessages(v1FolderMessagesDeleteBulkRequest)

Permanently delete multiple messages from a folder.

### Example

```typescript
import {
    MessagesApi,
    Configuration,
    V1FolderMessagesDeleteBulkRequest
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Folder path (URL-encoded). (default to undefined)
let v1FolderMessagesDeleteBulkRequest: V1FolderMessagesDeleteBulkRequest; //

const { status, data } = await apiInstance.deleteMessages(
    mailboxResourceId,
    folder,
    v1FolderMessagesDeleteBulkRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1FolderMessagesDeleteBulkRequest** | **V1FolderMessagesDeleteBulkRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Folder path (URL-encoded). | defaults to undefined|


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
|**204** | Messages deleted successfully. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getMessage**
> V1FolderMessagesResource getMessage()

Retrieve a single message by UID.

### Example

```typescript
import {
    MessagesApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Folder path (URL-encoded). (default to undefined)
let uid: number; //Message UID. (default to undefined)

const { status, data } = await apiInstance.getMessage(
    mailboxResourceId,
    folder,
    uid
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Folder path (URL-encoded). | defaults to undefined|
| **uid** | [**number**] | Message UID. | defaults to undefined|


### Return type

**V1FolderMessagesResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Message payload. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getMessageAttachment**
> File getMessageAttachment()

Download a message attachment as `application/octet-stream`.

### Example

```typescript
import {
    MessagesApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Folder path (URL-encoded). (default to undefined)
let uid: number; //Message UID. (default to undefined)
let attachmentId: string; //Attachment ID (opaque, returned by GET message). (default to undefined)

const { status, data } = await apiInstance.getMessageAttachment(
    mailboxResourceId,
    folder,
    uid,
    attachmentId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Folder path (URL-encoded). | defaults to undefined|
| **uid** | [**number**] | Message UID. | defaults to undefined|
| **attachmentId** | [**string**] | Attachment ID (opaque, returned by GET message). | defaults to undefined|


### Return type

**File**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream, application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Decoded attachment body. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getMessageSource**
> File getMessageSource()

Retrieve raw RFC822 source of a message as `message/rfc822` attachment.

### Example

```typescript
import {
    MessagesApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Folder path (URL-encoded). (default to undefined)
let uid: number; //Message UID. (default to undefined)

const { status, data } = await apiInstance.getMessageSource(
    mailboxResourceId,
    folder,
    uid
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Folder path (URL-encoded). | defaults to undefined|
| **uid** | [**number**] | Message UID. | defaults to undefined|


### Return type

**File**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: message/rfc822, application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Raw RFC822 source. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getMessageText**
> V1FolderMessagesMessageTextResource getMessageText()

Retrieve rendered text (plain + HTML) of a message. Marks message as `\\Seen`.

### Example

```typescript
import {
    MessagesApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Folder path (URL-encoded). (default to undefined)
let uid: number; //Message UID. (default to undefined)

const { status, data } = await apiInstance.getMessageText(
    mailboxResourceId,
    folder,
    uid
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Folder path (URL-encoded). | defaults to undefined|
| **uid** | [**number**] | Message UID. | defaults to undefined|


### Return type

**V1FolderMessagesMessageTextResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Rendered text and HTML payload. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listMessages**
> V1FolderMessagesCollection listMessages()

List messages in a folder. Use POST /search for filtering. Sort fields: uid, date, size (prefix with `-` for descending). Default `-uid`.

### Example

```typescript
import {
    MessagesApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Folder path (URL-encoded). (default to undefined)
let page: number; //Page number (1-based). (optional) (default to 1)
let perPage: number; //Items per page (max 100). (optional) (default to 25)
let sort: string; //Sort field with optional `-` prefix for descending. Allowed: uid, date, size. (optional) (default to '-uid')

const { status, data } = await apiInstance.listMessages(
    mailboxResourceId,
    folder,
    page,
    perPage,
    sort
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Folder path (URL-encoded). | defaults to undefined|
| **page** | [**number**] | Page number (1-based). | (optional) defaults to 1|
| **perPage** | [**number**] | Items per page (max 100). | (optional) defaults to 25|
| **sort** | [**string**] | Sort field with optional &#x60;-&#x60; prefix for descending. Allowed: uid, date, size. | (optional) defaults to '-uid'|


### Return type

**V1FolderMessagesCollection**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Paginated list of messages. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **moveMessage**
> moveMessage(v1FolderMessagesMoveRequest)

Move a single message to a target folder.

### Example

```typescript
import {
    MessagesApi,
    Configuration,
    V1FolderMessagesMoveRequest
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Source folder path (URL-encoded). (default to undefined)
let uid: number; //Message UID. (default to undefined)
let v1FolderMessagesMoveRequest: V1FolderMessagesMoveRequest; //

const { status, data } = await apiInstance.moveMessage(
    mailboxResourceId,
    folder,
    uid,
    v1FolderMessagesMoveRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1FolderMessagesMoveRequest** | **V1FolderMessagesMoveRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Source folder path (URL-encoded). | defaults to undefined|
| **uid** | [**number**] | Message UID. | defaults to undefined|


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
|**204** | Message moved successfully. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **moveMessages**
> moveMessages(v1FolderMessagesMoveBulkRequest)

Move multiple messages from a source folder to a target folder.

### Example

```typescript
import {
    MessagesApi,
    Configuration,
    V1FolderMessagesMoveBulkRequest
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Source folder path (URL-encoded). (default to undefined)
let v1FolderMessagesMoveBulkRequest: V1FolderMessagesMoveBulkRequest; //

const { status, data } = await apiInstance.moveMessages(
    mailboxResourceId,
    folder,
    v1FolderMessagesMoveBulkRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1FolderMessagesMoveBulkRequest** | **V1FolderMessagesMoveBulkRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Source folder path (URL-encoded). | defaults to undefined|


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
|**204** | Messages moved successfully. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **patchMessage**
> V1FolderMessagesResource patchMessage(v1FolderMessagesFlagsRequest)

Add and/or remove flags on a single message. Returns the updated message.

### Example

```typescript
import {
    MessagesApi,
    Configuration,
    V1FolderMessagesFlagsRequest
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Folder path (URL-encoded). (default to undefined)
let uid: number; //Message UID. (default to undefined)
let v1FolderMessagesFlagsRequest: V1FolderMessagesFlagsRequest; //

const { status, data } = await apiInstance.patchMessage(
    mailboxResourceId,
    folder,
    uid,
    v1FolderMessagesFlagsRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1FolderMessagesFlagsRequest** | **V1FolderMessagesFlagsRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Folder path (URL-encoded). | defaults to undefined|
| **uid** | [**number**] | Message UID. | defaults to undefined|


### Return type

**V1FolderMessagesResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Updated message. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **searchMessages**
> V1FolderMessagesCollection searchMessages()

Search messages in a folder. Filters in body; pagination and sort via query (`page`, `perPage`, `sort`).

### Example

```typescript
import {
    MessagesApi,
    Configuration,
    V1FolderMessagesSearchRequest
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Folder path (URL-encoded). (default to undefined)
let page: number; // (optional) (default to 1)
let perPage: number; // (optional) (default to 25)
let sort: string; // (optional) (default to '-uid')
let v1FolderMessagesSearchRequest: V1FolderMessagesSearchRequest; // (optional)

const { status, data } = await apiInstance.searchMessages(
    mailboxResourceId,
    folder,
    page,
    perPage,
    sort,
    v1FolderMessagesSearchRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1FolderMessagesSearchRequest** | **V1FolderMessagesSearchRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Folder path (URL-encoded). | defaults to undefined|
| **page** | [**number**] |  | (optional) defaults to 1|
| **perPage** | [**number**] |  | (optional) defaults to 25|
| **sort** | [**string**] |  | (optional) defaults to '-uid'|


### Return type

**V1FolderMessagesCollection**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Paginated list of matching messages. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **updateMessageFlags**
> V1FolderMessagesUpdateFlagsResult updateMessageFlags(v1FolderMessagesFlagsBulkRequest)

Add and/or remove flags on multiple messages. Returns 200 when all UIDs succeed, 207 with per-UID outcome when some fail.

### Example

```typescript
import {
    MessagesApi,
    Configuration,
    V1FolderMessagesFlagsBulkRequest
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new MessagesApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Folder path (URL-encoded). (default to undefined)
let v1FolderMessagesFlagsBulkRequest: V1FolderMessagesFlagsBulkRequest; //

const { status, data } = await apiInstance.updateMessageFlags(
    mailboxResourceId,
    folder,
    v1FolderMessagesFlagsBulkRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1FolderMessagesFlagsBulkRequest** | **V1FolderMessagesFlagsBulkRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Folder path (URL-encoded). | defaults to undefined|


### Return type

**V1FolderMessagesUpdateFlagsResult**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | All UIDs updated successfully. |  -  |
|**207** | Some UIDs failed; see body for per-UID outcome. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

