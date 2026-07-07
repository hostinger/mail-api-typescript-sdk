# V1FolderMessagesMessageAttachment

Attachment metadata attached to a message.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Opaque attachment identifier. Use as the {attachmentId} path parameter on the download endpoint. | [default to undefined]
**contentType** | **string** |  | [default to undefined]
**sizeBytes** | **number** |  | [default to undefined]
**inline** | **boolean** |  | [default to undefined]
**filename** | **string** |  | [default to undefined]
**contentId** | **string** |  | [default to undefined]

## Example

```typescript
import { V1FolderMessagesMessageAttachment } from 'hostinger-email-api-sdk';

const instance: V1FolderMessagesMessageAttachment = {
    id,
    contentType,
    sizeBytes,
    inline,
    filename,
    contentId,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
