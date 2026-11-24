# V1CalendarEventsUpdateRequest

Body for updating a calendar event. Every field replaces the stored value and an omitted optional field is cleared.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**title** | **string** | Title of the event. | [default to undefined]
**start** | **string** | ISO 8601 date-time with offset; without an offset it is read as UTC. For an all-day event a date is enough (2026-09-28). | [default to undefined]
**end** | **string** | Exclusive end, same format as &#x60;start&#x60;. Required for a timed event and not before &#x60;start&#x60;. For an all-day event the day after the last day (2026-09-29 for one day on 2026-09-28); omitted means one day. | [optional] [default to undefined]
**allDay** | **boolean** | &#x60;true&#x60; for an all-day event (dates only, &#x60;timeZone&#x60; ignored), &#x60;false&#x60; for an event at a time of day. | [default to undefined]
**timeZone** | **string** | IANA time zone of the event. Required when &#x60;allDay&#x60; is false, ignored when &#x60;allDay&#x60; is true. | [optional] [default to undefined]
**description** | **string** | Notes of the event. Omitted or null clears it. | [optional] [default to undefined]
**location** | **string** | Place of the event. Omitted or null clears it. | [optional] [default to undefined]
**meetingLink** | **string** | http or https URL of the online meeting. Omitted or null clears it. | [optional] [default to undefined]
**color** | **string** | Color of the event as #RRGGBB or #RRGGBBAA. Omitted or null uses the calendar color. | [optional] [default to undefined]
**recurrenceRule** | [**V1CalendarEventsRecurrenceRule**](V1CalendarEventsRecurrenceRule.md) | Omitted or null makes it a one-off event. A repeating event sends every field of the rule, null when unused: &#x60;frequency&#x60; DAILY, WEEKLY, MONTHLY or YEARLY, &#x60;interval&#x60; 1 to 1000, and &#x60;count&#x60; or &#x60;until&#x60; to end it, not both. | [optional] [default to undefined]
**reminder** | [**V1CalendarEventsReminder**](V1CalendarEventsReminder.md) | Alarm before the start: &#x60;value&#x60; 0 to 1000 and &#x60;unit&#x60;. Omitted or null clears it. | [optional] [default to undefined]
**attendees** | [**Array&lt;V1CalendarEventsAttendeeInput&gt;**](V1CalendarEventsAttendeeInput.md) | Full list of invited people. Added addresses receive an invitation and removed ones a cancellation. Unique addresses, at most 100 not counting the mailbox itself, across all occurrences. The own address of the mailbox is stored as accepted and not invited. Omitted, null or empty for none. | [optional] [default to undefined]
**scope** | **string** | For a recurring event: &#x60;this&#x60; changes the occurrence at &#x60;recurrenceId&#x60;, &#x60;future&#x60; changes it and every later one, &#x60;all&#x60; changes the whole series. Omitted or null means &#x60;all&#x60;. Required when &#x60;recurrenceId&#x60; is sent. | [optional] [default to undefined]
**recurrenceId** | **string** | &#x60;recurrenceId&#x60; of one occurrence, copied unchanged from a &#x60;listCalendarEvents&#x60; item. Required when &#x60;scope&#x60; is &#x60;this&#x60; or &#x60;future&#x60;, ignored for &#x60;all&#x60;. | [optional] [default to undefined]
**notifyAttendees** | **boolean** | &#x60;false&#x60; saves the change without emailing attendees, and copies of the event in the calendars of other Hostinger mailboxes are not updated. Omitted or null means &#x60;true&#x60;. | [optional] [default to undefined]

## Example

```typescript
import { V1CalendarEventsUpdateRequest } from '@hostinger/mail-sdk';

const instance: V1CalendarEventsUpdateRequest = {
    title,
    start,
    end,
    allDay,
    timeZone,
    description,
    location,
    meetingLink,
    color,
    recurrenceRule,
    reminder,
    attendees,
    scope,
    recurrenceId,
    notifyAttendees,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
