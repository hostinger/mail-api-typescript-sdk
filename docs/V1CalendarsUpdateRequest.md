# V1CalendarsUpdateRequest

Body for updating a calendar. Name, description and color replace the stored values.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**displayName** | **string** | Name of the calendar. | [default to undefined]
**description** | **string** | Free-text note about the calendar. Omitted or null clears it. | [optional] [default to undefined]
**color** | **string** | Hex color as #RRGGBB or #RRGGBBAA. Omitted or null resets it to the default color. | [optional] [default to undefined]
**visible** | **boolean** | Whether the mailbox shows the calendar in its calendar view. Omitted or null keeps the current value. | [optional] [default to undefined]

## Example

```typescript
import { V1CalendarsUpdateRequest } from '@hostinger/mail-sdk';

const instance: V1CalendarsUpdateRequest = {
    displayName,
    description,
    color,
    visible,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
