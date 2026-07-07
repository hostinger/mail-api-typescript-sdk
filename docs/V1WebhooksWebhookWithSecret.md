# V1WebhooksWebhookWithSecret

Webhook payload that includes the one-time `secret`. Returned at creation and after secret regeneration. The secret is delivered as a bearer token on every webhook request (`Authorization: Bearer <secret>`); store it securely as it is not returned again.

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
**secret** | **string** |  | [default to undefined]

## Example

```typescript
import { V1WebhooksWebhookWithSecret } from 'hostinger-email-api-sdk';

const instance: V1WebhooksWebhookWithSecret = {
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
    secret,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
