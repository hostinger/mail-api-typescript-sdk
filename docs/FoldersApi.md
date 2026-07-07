# FoldersApi

All URIs are relative to *https://api.mail.hostinger.com*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**createFolder**](#createfolder) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders | Create folder|
|[**deleteFolder**](#deletefolder) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder} | Delete folder|
|[**listFolders**](#listfolders) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders | List folders|
|[**updateFolder**](#updatefolder) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder} | Update folder|

# **createFolder**
> V1FoldersResource createFolder(v1FoldersCreateRequest)

Create a new folder in the managed mailbox.

### Example

```typescript
import {
    FoldersApi,
    Configuration,
    V1FoldersCreateRequest
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new FoldersApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let v1FoldersCreateRequest: V1FoldersCreateRequest; //

const { status, data } = await apiInstance.createFolder(
    mailboxResourceId,
    v1FoldersCreateRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1FoldersCreateRequest** | **V1FoldersCreateRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|


### Return type

**V1FoldersResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**201** | Folder created. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**409** | Conflict with the target resource. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteFolder**
> deleteFolder()

Delete a folder and all of its subfolders.

### Example

```typescript
import {
    FoldersApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new FoldersApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Folder path to delete (URL-encoded). (default to undefined)

const { status, data } = await apiInstance.deleteFolder(
    mailboxResourceId,
    folder
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Folder path to delete (URL-encoded). | defaults to undefined|


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
|**204** | Folder and all subfolders deleted. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**409** | Conflict with the target resource. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listFolders**
> V1FoldersCollection listFolders()

Retrieve a paginated list of folders in the managed mailbox.

### Example

```typescript
import {
    FoldersApi,
    Configuration
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new FoldersApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let page: number; //Page number (1-based). (optional) (default to 1)
let perPage: number; //Items per page (max 100). (optional) (default to 25)

const { status, data } = await apiInstance.listFolders(
    mailboxResourceId,
    page,
    perPage
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **page** | [**number**] | Page number (1-based). | (optional) defaults to 1|
| **perPage** | [**number**] | Items per page (max 100). | (optional) defaults to 25|


### Return type

**V1FoldersCollection**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Paginated list of folders. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **updateFolder**
> V1FoldersResource updateFolder(v1FoldersUpdateRequest)

Rename an existing folder.

### Example

```typescript
import {
    FoldersApi,
    Configuration,
    V1FoldersUpdateRequest
} from 'hostinger-email-api-sdk';

const configuration = new Configuration();
const apiInstance = new FoldersApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let folder: string; //Current folder path (URL-encoded). (default to undefined)
let v1FoldersUpdateRequest: V1FoldersUpdateRequest; //

const { status, data } = await apiInstance.updateFolder(
    mailboxResourceId,
    folder,
    v1FoldersUpdateRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1FoldersUpdateRequest** | **V1FoldersUpdateRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **folder** | [**string**] | Current folder path (URL-encoded). | defaults to undefined|


### Return type

**V1FoldersResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Folder renamed. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**409** | Conflict with the target resource. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

