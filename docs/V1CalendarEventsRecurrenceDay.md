# V1CalendarEventsRecurrenceDay

One weekday of a recurrence rule.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**day** | **string** |  | [default to undefined]
**position** | **number** | Which such weekday in the month or year, for a MONTHLY or YEARLY rule only: 1 is the first, -1 the last, never 0. Null means every such weekday and is the only value allowed for other frequencies. | [default to undefined]

## Example

```typescript
import { V1CalendarEventsRecurrenceDay } from '@hostinger/mail-sdk';

const instance: V1CalendarEventsRecurrenceDay = {
    day,
    position,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
