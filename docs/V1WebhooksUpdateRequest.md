# V1WebhooksUpdateRequest

Body for partially updating a webhook. All fields optional; only present fields are applied.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** |  | [optional] [default to undefined]
**description** | **string** |  | [optional] [default to undefined]
**events** | **Array&lt;string&gt;** |  | [optional] [default to undefined]
**status** | **string** |  | [optional] [default to undefined]
**url** | **string** |  | [optional] [default to undefined]

## Example

```typescript
import { V1WebhooksUpdateRequest } from 'hostinger-email-api-sdk';

const instance: V1WebhooksUpdateRequest = {
    name,
    description,
    events,
    status,
    url,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
