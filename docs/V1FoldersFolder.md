# V1FoldersFolder

A folder (IMAP mailbox) in the managed mailbox.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**path** | **string** | Full hierarchical folder path including the delimiter. | [default to undefined]
**name** | **string** | Leaf name of the folder. | [default to undefined]
**delimiter** | **string** | Hierarchy delimiter used by the IMAP server. | [default to undefined]
**specialUse** | **string** | IMAP SPECIAL-USE attribute (RFC 6154). &#x60;null&#x60; for regular folders. | [default to undefined]
**messageCount** | **number** | Total number of messages in the folder. | [default to undefined]
**unreadCount** | **number** | Number of unread messages in the folder. | [default to undefined]

## Example

```typescript
import { V1FoldersFolder } from 'hostinger-email-api-sdk';

const instance: V1FoldersFolder = {
    path,
    name,
    delimiter,
    specialUse,
    messageCount,
    unreadCount,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
