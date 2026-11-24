# V1CalendarEventsReplyRequest

Body for answering an invitation.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**participationStatus** | **string** | The answer to the invitation. | [default to undefined]
**recurrenceId** | **string** | &#x60;recurrenceId&#x60; of one occurrence, copied unchanged from a &#x60;listCalendarEvents&#x60; item, to answer only that occurrence. Omitted or null answers the whole event. | [optional] [default to undefined]

## Example

```typescript
import { V1CalendarEventsReplyRequest } from '@hostinger/mail-sdk';

const instance: V1CalendarEventsReplyRequest = {
    participationStatus,
    recurrenceId,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
