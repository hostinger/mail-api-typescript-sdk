# V1SendMessageRef

Reference to a source message by UID within a folder, used for reply/forward threading. Both fields are required.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uid** | **number** | UID of the source message. | [default to undefined]
**folder** | **string** | Folder containing the source message. | [default to undefined]

## Example

```typescript
import { V1SendMessageRef } from '@hostinger/mail-sdk';

const instance: V1SendMessageRef = {
    uid,
    folder,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
