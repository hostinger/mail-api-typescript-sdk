# V1FolderMessagesDeleteBulkRequest

Body for permanently deleting multiple messages.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uids** | **Array&lt;number&gt;** | Message UIDs to delete. 1-100 entries, each &gt; 0. | [default to undefined]

## Example

```typescript
import { V1FolderMessagesDeleteBulkRequest } from 'hostinger-email-api-sdk';

const instance: V1FolderMessagesDeleteBulkRequest = {
    uids,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
