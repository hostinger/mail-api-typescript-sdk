# V1CalendarEventsEventListItem

Summary of one calendar event or of one occurrence of a recurring event.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** | Event identifier, the &#x60;eventUuid&#x60; of the calendar event endpoints. Every occurrence of a recurring event has the same uuid. | [default to undefined]
**calendarUuid** | **string** | Identifier of the calendar the event is stored in. | [default to undefined]
**recurrenceId** | **string** | Identifies one occurrence of a recurring event. Null for a one-off event or for the series itself. | [default to undefined]
**title** | **string** |  | [default to undefined]
**start** | **string** | Start in UTC. When &#x60;allDay&#x60; is true, the date at midnight (2026-09-29T00:00:00.000000Z). An event stored without a time zone keeps its wall-clock time (09:00 is 09:00:00.000000Z). | [default to undefined]
**end** | **string** | Exclusive end, same form as &#x60;start&#x60;. When &#x60;allDay&#x60; is true, midnight of the day after the last day of the event (2026-09-30T00:00:00.000000Z for a one-day event on 2026-09-29). | [default to undefined]
**allDay** | **boolean** |  | [default to undefined]
**timeZone** | **string** | IANA time zone the event is stored in. Null when it has none. | [default to undefined]
**editable** | **boolean** | Whether &#x60;updateCalendarEvent&#x60;, &#x60;rescheduleCalendarEvent&#x60; and &#x60;deleteCalendarEvent&#x60; can change the event. | [default to undefined]
**color** | **string** | Color of the event. The calendar color when the event has none or is an invitation from someone else. | [default to undefined]
**participationStatus** | **string** | Answer of the mailbox to an invitation from someone else. Null for its own events. | [default to undefined]
**status** | **string** | CANCELLED when the organizer cancelled the event, CONFIRMED otherwise. | [default to undefined]

## Example

```typescript
import { V1CalendarEventsEventListItem } from '@hostinger/mail-sdk';

const instance: V1CalendarEventsEventListItem = {
    uuid,
    calendarUuid,
    recurrenceId,
    title,
    start,
    end,
    allDay,
    timeZone,
    editable,
    color,
    participationStatus,
    status,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
