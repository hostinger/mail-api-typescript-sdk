# V1WebhooksUpdateRequest

Body for partially updating a webhook. All fields optional; only present fields are applied.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Human-readable webhook name. | [optional] [default to undefined]
**description** | **string** | Free-text note about the webhook purpose. Send null to clear. | [optional] [default to undefined]
**events** | **Array&lt;string&gt;** | Event types that trigger a delivery. Replaces the current list. | [optional] [default to undefined]
**status** | **string** | Delivery state. Only active webhooks receive events; paused keeps config but stops deliveries. | [optional] [default to undefined]
**url** | **string** | HTTPS endpoint that receives POST deliveries, authenticated with the webhook secret as &#x60;Authorization: Bearer &lt;secret&gt;&#x60;. Must be a public domain name (no IPs or internal hosts). | [optional] [default to undefined]

## Example

```typescript
import { V1WebhooksUpdateRequest } from '@hostinger/mail-sdk';

const instance: V1WebhooksUpdateRequest = {
    name,
    description,
    events,
    status,
    url,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
