# CalendarEventsApi

All URIs are relative to *https://api.mail.hostinger.com*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**createCalendarEvent**](#createcalendarevent) | **POST** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events | Create calendar event|
|[**deleteCalendarEvent**](#deletecalendarevent) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid} | Delete calendar event|
|[**getCalendarEvent**](#getcalendarevent) | **GET** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid} | Get calendar event|
|[**listCalendarEvents**](#listcalendarevents) | **GET** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events | List calendar events|
|[**replyToCalendarEvent**](#replytocalendarevent) | **POST** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid}/reply | Reply to calendar event|
|[**rescheduleCalendarEvent**](#reschedulecalendarevent) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid}/reschedule | Reschedule calendar event|
|[**updateCalendarEvent**](#updatecalendarevent) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid} | Update calendar event|

# **createCalendarEvent**
> V1CalendarEventsResource createCalendarEvent(v1CalendarEventsCreateRequest)

Create an event in one calendar of the mailbox. `calendarUuid` comes from `listCalendars`: use the calendar with `default` true unless another one is named. A calendar the mailbox can only read is rejected with `403` and code `ERR_EVENT_NOT_EDITABLE`. The mailbox becomes the organizer and every address in `attendees` immediately receives an email invitation, which cannot be recalled. Without attendees no email is sent. A timed event needs `allDay` false, `start`, `end` and `timeZone`. An all-day event needs `allDay` true and a `start` date; `end` is optional. Set `recurrenceRule` for a repeating event and `reminder` for an alarm. Returns the created event. Its `uuid` is the `eventUuid` for `getCalendarEvent`, `updateCalendarEvent`, `rescheduleCalendarEvent` and `deleteCalendarEvent`.

### Example

```typescript
import {
    CalendarEventsApi,
    Configuration,
    V1CalendarEventsCreateRequest
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new CalendarEventsApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let calendarUuid: string; //Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`. (default to undefined)
let v1CalendarEventsCreateRequest: V1CalendarEventsCreateRequest; //

const { status, data } = await apiInstance.createCalendarEvent(
    mailboxResourceId,
    calendarUuid,
    v1CalendarEventsCreateRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1CalendarEventsCreateRequest** | **V1CalendarEventsCreateRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **calendarUuid** | [**string**] | Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | defaults to undefined|


### Return type

**V1CalendarEventsResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**201** | Event created. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteCalendarEvent**
> deleteCalendarEvent()

Delete an event, one occurrence of a recurring event, or a recurring event from one occurrence on. This cannot be undone. `calendarUuid` and `eventUuid` come from `listCalendarEvents`. For a one-off event omit `scope` and `recurrenceId`. For a recurring event, `scope` `this` removes only the occurrence at `recurrenceId`, `future` removes it and every later one, `all` (the default) deletes the whole series. An event with `editable` true can be deleted with any scope, and its attendees receive a cancellation or the updated series by email. An invitation from someone else on the own calendar of the mailbox can be deleted with `all` or `this`: the organizer receives a decline for the removed occurrences. Any other event is rejected with `403` and code `ERR_EVENT_NOT_EDITABLE`. `notifyAttendees` false deletes without sending any email.

### Example

```typescript
import {
    CalendarEventsApi,
    Configuration
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new CalendarEventsApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let calendarUuid: string; //Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`. (default to undefined)
let eventUuid: string; //Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence. (default to undefined)
let scope: 'this' | 'future' | 'all'; //For a recurring event: `this` removes the occurrence at `recurrenceId`, `future` removes it and every later one, `all` deletes the whole series. Omitted means `all`. Required when `recurrenceId` is sent. (optional) (default to undefined)
let recurrenceId: string; //`recurrenceId` of one occurrence, copied unchanged from a `listCalendarEvents` item. Required when `scope` is `this` or `future`. A value that matches no occurrence, or any value on a one-off event, returns `404`. (optional) (default to undefined)
let notifyAttendees: 'true' | 'false' | '1' | '0'; //`false` deletes without emailing attendees a cancellation or update, or the organizer a decline. Omitted means `true`. (optional) (default to 'true')
let ifMatch: string; //Optional `etag` from `getCalendarEvent`. When the event changed since that call, nothing is deleted and the request fails with `412`: fetch the event again and retry. Omit it to apply the request to the current version. (optional) (default to undefined)

const { status, data } = await apiInstance.deleteCalendarEvent(
    mailboxResourceId,
    calendarUuid,
    eventUuid,
    scope,
    recurrenceId,
    notifyAttendees,
    ifMatch
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **calendarUuid** | [**string**] | Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | defaults to undefined|
| **eventUuid** | [**string**] | Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | defaults to undefined|
| **scope** | [**&#39;this&#39; | &#39;future&#39; | &#39;all&#39;**]**Array<&#39;this&#39; &#124; &#39;future&#39; &#124; &#39;all&#39;>** | For a recurring event: &#x60;this&#x60; removes the occurrence at &#x60;recurrenceId&#x60;, &#x60;future&#x60; removes it and every later one, &#x60;all&#x60; deletes the whole series. Omitted means &#x60;all&#x60;. Required when &#x60;recurrenceId&#x60; is sent. | (optional) defaults to undefined|
| **recurrenceId** | [**string**] | &#x60;recurrenceId&#x60; of one occurrence, copied unchanged from a &#x60;listCalendarEvents&#x60; item. Required when &#x60;scope&#x60; is &#x60;this&#x60; or &#x60;future&#x60;. A value that matches no occurrence, or any value on a one-off event, returns &#x60;404&#x60;. | (optional) defaults to undefined|
| **notifyAttendees** | [**&#39;true&#39; | &#39;false&#39; | &#39;1&#39; | &#39;0&#39;**]**Array<&#39;true&#39; &#124; &#39;false&#39; &#124; &#39;1&#39; &#124; &#39;0&#39;>** | &#x60;false&#x60; deletes without emailing attendees a cancellation or update, or the organizer a decline. Omitted means &#x60;true&#x60;. | (optional) defaults to 'true'|
| **ifMatch** | [**string**] | Optional &#x60;etag&#x60; from &#x60;getCalendarEvent&#x60;. When the event changed since that call, nothing is deleted and the request fails with &#x60;412&#x60;: fetch the event again and retry. Omit it to apply the request to the current version. | (optional) defaults to undefined|


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
|**204** | Event deleted. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**412** | The resource changed since the etag sent in &#x60;If-Match&#x60; was read. Nothing was changed: fetch the resource again and retry. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getCalendarEvent**
> V1CalendarEventsResource getCalendarEvent()

Retrieve the full details of one event: title, times, description, location, meeting link, recurrence rule, reminder, organizer, attendees with their answers, and its `etag`. `calendarUuid` and `eventUuid` come from `listCalendarEvents` (the `calendarUuid` and `uuid` of an item). For one occurrence of a recurring event pass the `recurrenceId` of the item; without it the whole series is returned and `recurrenceId` is null. A `recurrenceId` that matches no occurrence returns `404`. Call it before `updateCalendarEvent`, which replaces every field, so the values that should stay can be sent back. `replyable` true means the mailbox was invited by someone else and can answer with `replyToCalendarEvent`. `editable` true means the event can be changed or moved.

### Example

```typescript
import {
    CalendarEventsApi,
    Configuration
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new CalendarEventsApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let calendarUuid: string; //Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`. (default to undefined)
let eventUuid: string; //Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence. (default to undefined)
let recurrenceId: string; //`recurrenceId` of one occurrence, copied unchanged from a `listCalendarEvents` item. Omit it for a one-off event or for the whole series. (optional) (default to undefined)

const { status, data } = await apiInstance.getCalendarEvent(
    mailboxResourceId,
    calendarUuid,
    eventUuid,
    recurrenceId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **calendarUuid** | [**string**] | Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | defaults to undefined|
| **eventUuid** | [**string**] | Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | defaults to undefined|
| **recurrenceId** | [**string**] | &#x60;recurrenceId&#x60; of one occurrence, copied unchanged from a &#x60;listCalendarEvents&#x60; item. Omit it for a one-off event or for the whole series. | (optional) defaults to undefined|


### Return type

**V1CalendarEventsResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Event payload. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listCalendarEvents**
> V1CalendarEventsCollection listCalendarEvents()

List the events of one calendar that overlap a time range. It covers one calendar only: get the calendars from `listCalendars` and call it for each. The range runs from `start` (inclusive) to `end` (exclusive), at most 32 days; for a longer period call it again with the next range. Recurring events are expanded: each occurrence is a separate item with the same `uuid` and its own `recurrenceId`. Results are not paginated. Items hold summary fields only. For description, location, attendees and organizer call `getCalendarEvent` with the `calendarUuid`, `uuid` (as `eventUuid`) and `recurrenceId` of the item. Times are in UTC; `timeZone` is the zone the event was created in. `participationStatus` is the answer of the mailbox to an invitation from someone else, null for its own events. `status` CANCELLED means the organizer cancelled the event.

### Example

```typescript
import {
    CalendarEventsApi,
    Configuration
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new CalendarEventsApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let calendarUuid: string; //Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`. (default to undefined)
let start: string; //Start of the range, inclusive. ISO 8601 date-time with offset. (default to undefined)
let end: string; //End of the range, exclusive. ISO 8601 date-time after `start` and at most 32 days after it. (default to undefined)
let timeZone: string; //IANA time zone used to place all-day events and events without a time zone on days, also across a daylight saving change. Defaults to the fixed offset of `start`. (optional) (default to undefined)

const { status, data } = await apiInstance.listCalendarEvents(
    mailboxResourceId,
    calendarUuid,
    start,
    end,
    timeZone
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **calendarUuid** | [**string**] | Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | defaults to undefined|
| **start** | [**string**] | Start of the range, inclusive. ISO 8601 date-time with offset. | defaults to undefined|
| **end** | [**string**] | End of the range, exclusive. ISO 8601 date-time after &#x60;start&#x60; and at most 32 days after it. | defaults to undefined|
| **timeZone** | [**string**] | IANA time zone used to place all-day events and events without a time zone on days, also across a daylight saving change. Defaults to the fixed offset of &#x60;start&#x60;. | (optional) defaults to undefined|


### Return type

**V1CalendarEventsCollection**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Events overlapping the range. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **replyToCalendarEvent**
> V1CalendarEventsResource replyToCalendarEvent(v1CalendarEventsReplyRequest)

Answer an invitation from someone else: accept, decline or tentatively accept. It saves the answer on the event and emails it to the organizer, which cannot be recalled. `calendarUuid` and `eventUuid` come from `listCalendarEvents`. It works only when `getCalendarEvent` returns `replyable` true. An event the mailbox organizes or is not invited to is rejected with `403` and code `ERR_EVENT_NOT_REPLYABLE`, an event the organizer cancelled with `409` and code `ERR_EVENT_CANCELLED`. Send the `recurrenceId` of an item to answer one occurrence of a recurring event, or omit it to answer the whole series. Returns the event with the new `participationStatus`.

### Example

```typescript
import {
    CalendarEventsApi,
    Configuration,
    V1CalendarEventsReplyRequest
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new CalendarEventsApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let calendarUuid: string; //Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`. (default to undefined)
let eventUuid: string; //Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence. (default to undefined)
let v1CalendarEventsReplyRequest: V1CalendarEventsReplyRequest; //
let ifMatch: string; //Optional `etag` from `getCalendarEvent`. When the event changed since that call, the answer is not saved and the request fails with `412`: fetch the event again and retry. Omit it to apply the request to the current version. (optional) (default to undefined)

const { status, data } = await apiInstance.replyToCalendarEvent(
    mailboxResourceId,
    calendarUuid,
    eventUuid,
    v1CalendarEventsReplyRequest,
    ifMatch
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1CalendarEventsReplyRequest** | **V1CalendarEventsReplyRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **calendarUuid** | [**string**] | Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | defaults to undefined|
| **eventUuid** | [**string**] | Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | defaults to undefined|
| **ifMatch** | [**string**] | Optional &#x60;etag&#x60; from &#x60;getCalendarEvent&#x60;. When the event changed since that call, the answer is not saved and the request fails with &#x60;412&#x60;: fetch the event again and retry. Omit it to apply the request to the current version. | (optional) defaults to undefined|


### Return type

**V1CalendarEventsResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Event with the saved answer. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**409** | Conflict with the target resource. |  -  |
|**412** | The resource changed since the etag sent in &#x60;If-Match&#x60; was read. Nothing was changed: fetch the resource again and retry. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **rescheduleCalendarEvent**
> V1CalendarEventsResource rescheduleCalendarEvent(v1CalendarEventsRescheduleRequest)

Move an event to another time or change its length, keeping everything else (title, attendees, description and so on) as stored, so the event does not have to be fetched first. To change other fields use `updateCalendarEvent`. `calendarUuid` and `eventUuid` come from `listCalendarEvents`. Only an event with `editable` true can be moved; any other is rejected with `403` and code `ERR_EVENT_NOT_EDITABLE`. For a recurring event, `scope` `this` moves only the occurrence at `recurrenceId`, `future` ends the series before that occurrence and starts a new one with a new `uuid`, `all` (the default) moves the whole series: only the time of day and the length apply and the series keeps the date of its first occurrence. Attendees receive an email update unless `notifyAttendees` is false. Returns the moved event, or the moved occurrence for `scope` `this`.

### Example

```typescript
import {
    CalendarEventsApi,
    Configuration,
    V1CalendarEventsRescheduleRequest
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new CalendarEventsApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let calendarUuid: string; //Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`. (default to undefined)
let eventUuid: string; //Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence. (default to undefined)
let v1CalendarEventsRescheduleRequest: V1CalendarEventsRescheduleRequest; //
let ifMatch: string; //Optional `etag` from `getCalendarEvent`. When the event changed since that call, nothing is changed and the request fails with `412`: fetch the event again and retry. Omit it to apply the request to the current version. (optional) (default to undefined)

const { status, data } = await apiInstance.rescheduleCalendarEvent(
    mailboxResourceId,
    calendarUuid,
    eventUuid,
    v1CalendarEventsRescheduleRequest,
    ifMatch
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1CalendarEventsRescheduleRequest** | **V1CalendarEventsRescheduleRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **calendarUuid** | [**string**] | Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | defaults to undefined|
| **eventUuid** | [**string**] | Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | defaults to undefined|
| **ifMatch** | [**string**] | Optional &#x60;etag&#x60; from &#x60;getCalendarEvent&#x60;. When the event changed since that call, nothing is changed and the request fails with &#x60;412&#x60;: fetch the event again and retry. Omit it to apply the request to the current version. | (optional) defaults to undefined|


### Return type

**V1CalendarEventsResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Rescheduled event. |  -  |
|**400** | The change would leave the event with more unique attendees across all of its occurrences than allowed. &#x60;params.maxAttendees&#x60; holds the limit. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**412** | The resource changed since the etag sent in &#x60;If-Match&#x60; was read. Nothing was changed: fetch the resource again and retry. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **updateCalendarEvent**
> V1CalendarEventsResource updateCalendarEvent(v1CalendarEventsUpdateRequest)

Change the details of an event: title, times, description, location, attendees, recurrence and so on. Every field replaces the stored value and an omitted optional field is cleared, so call `getCalendarEvent` first and send back the values that should stay. To only move an event in time, use `rescheduleCalendarEvent`. Only an event with `editable` true can be changed; any other is rejected with `403` and code `ERR_EVENT_NOT_EDITABLE`. For a recurring event, `scope` `this` changes only the occurrence at `recurrenceId`, `future` ends the series before that occurrence and starts a new one with a new `uuid`, `all` (the default) changes the whole series, keeping the date of its first occurrence. Attendees receive an email update, added attendees an invitation and removed ones a cancellation, unless `notifyAttendees` is false. Returns the changed event, or the changed occurrence for `scope` `this`.

### Example

```typescript
import {
    CalendarEventsApi,
    Configuration,
    V1CalendarEventsUpdateRequest
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new CalendarEventsApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the bearer token is authorized for. (default to undefined)
let calendarUuid: string; //Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`. (default to undefined)
let eventUuid: string; //Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence. (default to undefined)
let v1CalendarEventsUpdateRequest: V1CalendarEventsUpdateRequest; //
let ifMatch: string; //Optional `etag` from `getCalendarEvent`. When the event changed since that call, nothing is changed and the request fails with `412`: fetch the event again and retry. Omit it to apply the request to the current version. (optional) (default to undefined)

const { status, data } = await apiInstance.updateCalendarEvent(
    mailboxResourceId,
    calendarUuid,
    eventUuid,
    v1CalendarEventsUpdateRequest,
    ifMatch
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1CalendarEventsUpdateRequest** | **V1CalendarEventsUpdateRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the bearer token is authorized for. | defaults to undefined|
| **calendarUuid** | [**string**] | Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | defaults to undefined|
| **eventUuid** | [**string**] | Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | defaults to undefined|
| **ifMatch** | [**string**] | Optional &#x60;etag&#x60; from &#x60;getCalendarEvent&#x60;. When the event changed since that call, nothing is changed and the request fails with &#x60;412&#x60;: fetch the event again and retry. Omit it to apply the request to the current version. | (optional) defaults to undefined|


### Return type

**V1CalendarEventsResource**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Updated event. |  -  |
|**400** | The change would leave the event with more unique attendees across all of its occurrences than allowed. &#x60;params.maxAttendees&#x60; holds the limit. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**404** | Resource not found. |  -  |
|**412** | The resource changed since the etag sent in &#x60;If-Match&#x60; was read. Nothing was changed: fetch the resource again and retry. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

