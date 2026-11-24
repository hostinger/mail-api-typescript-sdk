# V1CalendarEventsRecurrenceRule

How an event repeats. Every field is always present, null when unused.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**frequency** | **string** | Unit of repetition. Only DAILY, WEEKLY, MONTHLY and YEARLY can be written; SECONDLY, MINUTELY and HOURLY appear only on events created by other calendar applications. | [default to undefined]
**interval** | **number** | Repeat every this many units of &#x60;frequency&#x60;. 1 to 1000 when writing. | [default to undefined]
**byDay** | [**Array&lt;V1CalendarEventsRecurrenceDay&gt;**](V1CalendarEventsRecurrenceDay.md) | Weekdays the event repeats on. Null when unused. | [default to undefined]
**byMonthDay** | **Array&lt;number&gt;** | Days of the month, 1 to 31. Negative values count from the end of the month: -1 is the last day. Always null for a WEEKLY rule. | [default to undefined]
**byMonth** | **Array&lt;number&gt;** | Months, 1 is January. Null when unused. | [default to undefined]
**count** | **number** | Number of occurrences after which the series ends, at most 1000 when writing. Never set together with &#x60;until&#x60;. | [default to undefined]
**until** | **string** | Moment after which the series ends, not before the start of the event. Never set together with &#x60;count&#x60;. | [default to undefined]
**weekStart** | **string** | First day of the week used by the rule. Null when not set. | [default to undefined]

## Example

```typescript
import { V1CalendarEventsRecurrenceRule } from '@hostinger/mail-sdk';

const instance: V1CalendarEventsRecurrenceRule = {
    frequency,
    interval,
    byDay,
    byMonthDay,
    byMonth,
    count,
    until,
    weekStart,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
