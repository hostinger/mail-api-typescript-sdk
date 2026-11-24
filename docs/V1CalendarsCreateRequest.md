# V1CalendarsCreateRequest

Body for creating a calendar.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**displayName** | **string** | Name of the calendar. | [default to undefined]
**description** | **string** | Optional free-text note about the calendar. | [optional] [default to undefined]
**color** | **string** | Hex color as #RRGGBB or #RRGGBBAA. Omitted or null uses the default color. | [optional] [default to undefined]
**visible** | **boolean** | Whether the mailbox shows the calendar in its calendar view. Omitted or null means true. | [optional] [default to undefined]

## Example

```typescript
import { V1CalendarsCreateRequest } from '@hostinger/mail-sdk';

const instance: V1CalendarsCreateRequest = {
    displayName,
    description,
    color,
    visible,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
