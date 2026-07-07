# V1FolderMessagesFlagsBulkRequest

Add and/or remove flags on multiple messages. At least one of addFlags or removeFlags must be set.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uids** | **Array&lt;number&gt;** | Message UIDs to update. 1-100 entries, each &gt; 0. | [default to undefined]
**addFlags** | **Array&lt;string&gt;** |  | [optional] [default to undefined]
**removeFlags** | **Array&lt;string&gt;** |  | [optional] [default to undefined]

## Example

```typescript
import { V1FolderMessagesFlagsBulkRequest } from 'hostinger-email-api-sdk';

const instance: V1FolderMessagesFlagsBulkRequest = {
    uids,
    addFlags,
    removeFlags,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
