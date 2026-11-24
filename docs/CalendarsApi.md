# CalendarsApi

All URIs are relative to *https://api.mail.hostinger.com*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**createCalendar**](#createcalendar) | **POST** /api/v1/mailboxes/{mailboxResourceId}/calendars | Create calendar|
|[**deleteCalendar**](#deletecalendar) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid} | Delete calendar|
|[**getCalendar**](#getcalendar) | **GET** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid} | Get calendar|
|[**listCalendars**](#listcalendars) | **GET** /api/v1/mailboxes/{mailboxResourceId}/calendars | List calendars|
|[**updateCalendar**](#updatecalendar) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid} | Update calendar|

# **createCalendar**
> V1CalendarsResource createCalendar(v1CalendarsCreateRequest)

Create a calendar owned by the mailbox. The number of calendars a mailbox can own is limited; when the limit is reached the request fails with `400` and code `ERR_CALENDAR_LIMIT_REACHED`.

### Example

```typescript
import {
    CalendarsApi,
    Configuration,
    V1CalendarsCreateRequest
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new CalendarsApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let v1CalendarsCreateRequest: V1CalendarsCreateRequest; //

const { status, data } = await apiInstance.createCalendar(
    mailboxResourceId,
    v1CalendarsCreateRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1CalendarsCreateRequest** | **V1CalendarsCreateRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|


### Return type

**V1CalendarsResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**201** | Calendar created. |  -  |
|**400** | The mailbox already owns as many calendars as allowed. Calendars shared with the mailbox are not counted. &#x60;params.maxCalendars&#x60; holds the limit. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteCalendar**
> deleteCalendar()

Delete a calendar owned by the mailbox together with all its events, or remove a calendar shared with the mailbox from its list. This cannot be undone. A calendar that cannot be deleted is rejected with `403` and code `ERR_CALENDAR_NOT_DELETABLE`.

### Example

```typescript
import {
    CalendarsApi,
    Configuration
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new CalendarsApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let calendarUuid: string; //Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`. (default to undefined)

const { status, data } = await apiInstance.deleteCalendar(
    mailboxResourceId,
    calendarUuid
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **calendarUuid** | [**string**] | Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | defaults to undefined|


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
|**204** | Calendar deleted. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getCalendar**
> V1CalendarsResource getCalendar()

Retrieve one calendar of a mailbox: its name, description, color, whether it is the default calendar and whether it is shown in the calendar view. It does not return events; use `listCalendarEvents` for those.

### Example

```typescript
import {
    CalendarsApi,
    Configuration
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new CalendarsApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let calendarUuid: string; //Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`. (default to undefined)

const { status, data } = await apiInstance.getCalendar(
    mailboxResourceId,
    calendarUuid
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **calendarUuid** | [**string**] | Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | defaults to undefined|


### Return type

**V1CalendarsResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Calendar payload. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listCalendars**
> V1CalendarsCollection listCalendars()

List the calendars of a mailbox: its own calendars and the calendars shared with it, in display order. Call it first to get the `calendarUuid` every calendar event operation needs: the `uuid` of each calendar. The calendar with `default` true is where new events go unless another one is named. `visible` false means the calendar is hidden in the calendar view; its events still exist.

### Example

```typescript
import {
    CalendarsApi,
    Configuration
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new CalendarsApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let page: number; //Page number (1-based). (optional) (default to 1)
let perPage: number; //Items per page (max 200). (optional) (default to 25)

const { status, data } = await apiInstance.listCalendars(
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
| **perPage** | [**number**] | Items per page (max 200). | (optional) defaults to 25|


### Return type

**V1CalendarsCollection**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Paginated list of calendars. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **updateCalendar**
> V1CalendarsResource updateCalendar(v1CalendarsUpdateRequest)

Update the name, description, color and visibility of a calendar. Name, description and color replace the stored values: an omitted `description` is cleared and an omitted `color` resets to the default color. An omitted `visible` keeps the current value.

### Example

```typescript
import {
    CalendarsApi,
    Configuration,
    V1CalendarsUpdateRequest
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new CalendarsApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let calendarUuid: string; //Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`. (default to undefined)
let v1CalendarsUpdateRequest: V1CalendarsUpdateRequest; //

const { status, data } = await apiInstance.updateCalendar(
    mailboxResourceId,
    calendarUuid,
    v1CalendarsUpdateRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1CalendarsUpdateRequest** | **V1CalendarsUpdateRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **calendarUuid** | [**string**] | Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | defaults to undefined|


### Return type

**V1CalendarsResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Updated calendar. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

