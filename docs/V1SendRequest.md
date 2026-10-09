# V1SendRequest

Outgoing message payload. At least one of to, cc, or bcc must be present.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**to** | **Array&lt;string&gt;** | Primary recipient email addresses. | [optional] [default to undefined]
**displayName** | **string** | Sender display name shown in the From header alongside the mailbox address. | [optional] [default to undefined]
**cc** | **Array&lt;string&gt;** | Carbon-copy recipient email addresses. | [optional] [default to undefined]
**bcc** | **Array&lt;string&gt;** | Blind-carbon-copy recipient email addresses. Not visible to other recipients. | [optional] [default to undefined]
**subject** | **string** | Message subject line. | [optional] [default to undefined]
**text** | **string** | Plain-text body. Optional; if both text and html are omitted the message is sent without a body. | [optional] [default to undefined]
**html** | **string** | HTML body. Optional; if both text and html are omitted the message is sent without a body. Inline images are referenced via cid: URLs matching attachment cid values. | [optional] [default to undefined]
**attachments** | [**Array&lt;V1SendAttachment&gt;**](V1SendAttachment.md) | Files to attach. Inline images set cid; regular attachments omit it. | [optional] [default to undefined]
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
