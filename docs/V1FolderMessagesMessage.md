# V1FolderMessagesMessage

A message in a folder of the managed mailbox.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uid** | **number** |  | [default to undefined]
**path** | **string** |  | [default to undefined]
**date** | **string** |  | [default to undefined]
**flags** | **Array&lt;string&gt;** |  | [default to undefined]
**unseen** | **boolean** |  | [default to undefined]
**size** | **number** |  | [default to undefined]
**subject** | **string** |  | [default to undefined]
**from** | [**V1FolderMessagesMessageAddress**](V1FolderMessagesMessageAddress.md) |  | [default to undefined]
**to** | [**Array&lt;V1FolderMessagesMessageAddress&gt;**](V1FolderMessagesMessageAddress.md) |  | [default to undefined]
**cc** | [**Array&lt;V1FolderMessagesMessageAddress&gt;**](V1FolderMessagesMessageAddress.md) |  | [default to undefined]
**bcc** | [**Array&lt;V1FolderMessagesMessageAddress&gt;**](V1FolderMessagesMessageAddress.md) |  | [default to undefined]
**messageId** | **string** |  | [default to undefined]
**inReplyTo** | **string** |  | [default to undefined]
**attachments** | [**Array&lt;V1FolderMessagesMessageAttachment&gt;**](V1FolderMessagesMessageAttachment.md) |  | [default to undefined]

## Example

```typescript
import { V1FolderMessagesMessage } from 'hostinger-email-api-sdk';

const instance: V1FolderMessagesMessage = {
    uid,
    path,
    date,
    flags,
    unseen,
    size,
    subject,
    from,
    to,
    cc,
    bcc,
    messageId,
    inReplyTo,
    attachments,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
