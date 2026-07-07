# V1MeResourceData


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**orderResourceId** | **string** | Identifier of the order this API token is scoped to. | [default to undefined]
**mailboxes** | [**Array&lt;V1MeMailbox&gt;**](V1MeMailbox.md) | Mailboxes that the authenticated API token can manage. | [default to undefined]

## Example

```typescript
import { V1MeResourceData } from 'hostinger-email-api-sdk';

const instance: V1MeResourceData = {
    orderResourceId,
    mailboxes,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
