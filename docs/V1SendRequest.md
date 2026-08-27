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
**inReplyTo** | [**V1SendMessageRef**](V1SendMessageRef.md) | Source message this is a reply to. Copies its Message-Id/References into In-Reply-To/References and flags it \\Answered. Mutually exclusive with forwardOf. | [optional] [default to undefined]
**forwardOf** | [**V1SendMessageRef**](V1SendMessageRef.md) | Source message this forwards. Copies its Message-Id/References into In-Reply-To/References and flags it $forwarded. Mutually exclusive with inReplyTo. | [optional] [default to undefined]

## Example

```typescript
import { V1SendRequest } from '@hostinger/mail-sdk';

const instance: V1SendRequest = {
    to,
    displayName,
    cc,
    bcc,
    subject,
    text,
    html,
    attachments,
    inReplyTo,
    forwardOf,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
