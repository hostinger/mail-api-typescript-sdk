# V1FolderMessagesMoveBulkRequest

Body for moving multiple messages to a target folder.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uids** | **Array&lt;number&gt;** | Message UIDs to move. 1-100 entries, each &gt; 0. | [default to undefined]
**targetFolder** | **string** | Destination folder path. | [default to undefined]

## Example

```typescript
import { V1FolderMessagesMoveBulkRequest } from 'hostinger-email-api-sdk';

const instance: V1FolderMessagesMoveBulkRequest = {
    uids,
    targetFolder,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
