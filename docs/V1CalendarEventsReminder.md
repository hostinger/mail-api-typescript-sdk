# V1CalendarEventsReminder

Alarm of an event: how long before the start it fires.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**value** | **number** | How many units before the start. 0 is at the start time. At most 1000 when writing. | [default to undefined]
**unit** | **string** |  | [default to undefined]

## Example

```typescript
import { V1CalendarEventsReminder } from '@hostinger/mail-sdk';

const instance: V1CalendarEventsReminder = {
    value,
    unit,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
