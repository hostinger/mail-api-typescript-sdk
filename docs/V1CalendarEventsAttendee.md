# V1CalendarEventsAttendee

Attendee of an event with their answer to the invitation.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** |  | [default to undefined]
**email** | **string** |  | [default to undefined]
**participationStatus** | **string** | Answer of the attendee. NEEDS-ACTION means no answer yet. | [default to undefined]

## Example

```typescript
import { V1CalendarEventsAttendee } from '@hostinger/mail-sdk';

const instance: V1CalendarEventsAttendee = {
    name,
    email,
    participationStatus,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
