# V1WebhooksCreateRequest

Body for creating a webhook.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Human-readable webhook name. | [default to undefined]
**description** | **string** | Optional free-text note about the webhook purpose. | [optional] [default to undefined]
**events** | **Array&lt;string&gt;** | Event types that trigger a delivery. | [default to undefined]
**status** | **string** | Initial delivery state. Only active webhooks receive events. | [optional] [default to StatusEnum_Active]
**url** | **string** | HTTPS endpoint that receives POST deliveries, authenticated with the webhook secret as &#x60;Authorization: Bearer &lt;secret&gt;&#x60;. Must be a public domain name (no IPs or internal hosts). | [default to undefined]

## Example

```typescript
import { V1WebhooksCreateRequest } from '@hostinger/mail-sdk';

const instance: V1WebhooksCreateRequest = {
    name,
    description,
    events,
    status,
    url,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
