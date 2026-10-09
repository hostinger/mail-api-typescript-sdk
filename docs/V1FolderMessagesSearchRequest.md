# V1FolderMessagesSearchRequest

Search criteria. All fields optional. subject, from, to, cc and body are alternatives (a message matching any one of them qualifies); all other fields are combined with AND.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**since** | **string** | Only messages received on or after this date (YYYY-MM-DD). | [optional] [default to undefined]
**before** | **string** | Only messages received before this date (YYYY-MM-DD). | [optional] [default to undefined]
**flags** | **Array&lt;string&gt;** | Only messages carrying all of these IMAP flags, e.g. \\Seen, \\Flagged, \\Answered, $forwarded. | [optional] [default to undefined]
**uid** | **string** | IMAP UID set: single UID, range (1:100), open range (100:*), or comma-separated list. | [optional] [default to undefined]
**subject** | **string** | Case-insensitive substring match on the Subject header. OR-combined with from/to/cc/body. | [optional] [default to undefined]
**from** | **string** | Case-insensitive substring match on the From header. OR-combined with subject/to/cc/body. | [optional] [default to undefined]
**to** | **string** | Case-insensitive substring match on the To header. OR-combined with subject/from/cc/body. | [optional] [default to undefined]
**cc** | **string** | Case-insensitive substring match on the Cc header. OR-combined with subject/from/to/body. | [optional] [default to undefined]
**body** | **string** | Case-insensitive substring match on the message body only (headers excluded). OR-combined with subject/from/to/cc. | [optional] [default to undefined]
**header** | **string** | Match a specific header as Name:value, e.g. X-Custom-Header:value. Value match is a substring. | [optional] [default to undefined]
**larger** | **number** | Only messages larger than this size in bytes. | [optional] [default to undefined]
**smaller** | **number** | Only messages smaller than this size in bytes. | [optional] [default to undefined]
**text** | **string** | Case-insensitive substring match across headers and body. | [optional] [default to undefined]

## Example

```typescript
import { V1FolderMessagesSearchRequest } from '@hostinger/mail-sdk';

const instance: V1FolderMessagesSearchRequest = {
    since,
    before,
    flags,
    uid,
    subject,
    from,
    to,
    cc,
    body,
    header,
    larger,
    smaller,
    text,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
