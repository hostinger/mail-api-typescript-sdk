# V1CalendarsCalendar

Calendar of a managed mailbox: one it owns or one shared with it.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** | Calendar identifier, the &#x60;calendarUuid&#x60; of the calendar and calendar event endpoints. | [default to undefined]
**displayName** | **string** |  | [default to undefined]
**description** | **string** |  | [default to undefined]
**color** | **string** | Hex color as #RRGGBB or #RRGGBBAA. | [default to undefined]
**_default** | **boolean** | Whether this is the default calendar of the mailbox. New events go here unless another calendar is named. | [default to undefined]
**visible** | **boolean** | Whether the mailbox shows the calendar in its calendar view. A preference of this mailbox, not shared with other users of the calendar. Events of a hidden calendar still exist. | [default to undefined]

## Example

```typescript
import { V1CalendarsCalendar } from '@hostinger/mail-sdk';

const instance: V1CalendarsCalendar = {
    uuid,
    displayName,
    description,
    color,
    _default,
    visible,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
