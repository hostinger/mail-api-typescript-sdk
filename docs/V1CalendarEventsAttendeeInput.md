# V1CalendarEventsAttendeeInput

Person to invite to an event.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Display name of the attendee, null when unknown. | [optional] [default to undefined]
**email** | **string** | Email address of the attendee. | [default to undefined]

## Example

```typescript
import { V1CalendarEventsAttendeeInput } from '@hostinger/mail-sdk';

const instance: V1CalendarEventsAttendeeInput = {
    name,
    email,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
