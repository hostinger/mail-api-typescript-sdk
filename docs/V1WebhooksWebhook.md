# V1WebhooksWebhook

Webhook configured for a managed mailbox.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Unique webhook identifier (UUID v7). | [default to undefined]
**accountResourceId** | **string** | Resource ID of the mailbox this webhook is attached to. | [default to undefined]
**mailbox** | **string** | Email address of the mailbox. | [default to undefined]
**name** | **string** |  | [default to undefined]
**description** | **string** |  | [default to undefined]
**events** | **Array&lt;string&gt;** |  | [default to undefined]
**status** | **string** |  | [default to undefined]
**url** | **string** |  | [default to undefined]
**createdAt** | **string** |  | [default to undefined]
**updatedAt** | **string** |  | [default to undefined]

## Example

```typescript
import { V1WebhooksWebhook } from 'hostinger-email-api-sdk';

const instance: V1WebhooksWebhook = {
    id,
    accountResourceId,
    mailbox,
    name,
    description,
    events,
    status,
    url,
    createdAt,
    updatedAt,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
