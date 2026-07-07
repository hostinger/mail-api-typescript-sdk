# V1SendRequest

Outgoing message payload. At least one of to, cc, or bcc must be present.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**to** | **Array&lt;string&gt;** |  | [optional] [default to undefined]
**displayName** | **string** |  | [optional] [default to undefined]
**cc** | **Array&lt;string&gt;** |  | [optional] [default to undefined]
**bcc** | **Array&lt;string&gt;** |  | [optional] [default to undefined]
**subject** | **string** |  | [optional] [default to undefined]
**text** | **string** |  | [optional] [default to undefined]
**html** | **string** |  | [optional] [default to undefined]
**attachments** | [**Array&lt;V1SendAttachment&gt;**](V1SendAttachment.md) |  | [optional] [default to undefined]

## Example

```typescript
import { V1SendRequest } from 'hostinger-email-api-sdk';

const instance: V1SendRequest = {
    to,
    displayName,
    cc,
    bcc,
    subject,
    text,
    html,
    attachments,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
