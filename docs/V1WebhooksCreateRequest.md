# V1WebhooksCreateRequest

Body for creating a webhook.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** |  | [default to undefined]
**description** | **string** |  | [optional] [default to undefined]
**events** | **Array&lt;string&gt;** |  | [default to undefined]
**status** | **string** |  | [optional] [default to StatusEnum_Active]
**url** | **string** |  | [default to undefined]

## Example

```typescript
import { V1WebhooksCreateRequest } from 'hostinger-email-api-sdk';

const instance: V1WebhooksCreateRequest = {
    name,
    description,
    events,
    status,
    url,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
