# V1FolderMessagesSearchRequest

Search criteria. All fields optional; combine to narrow results.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**since** | **string** |  | [optional] [default to undefined]
**before** | **string** |  | [optional] [default to undefined]
**flags** | **Array&lt;string&gt;** |  | [optional] [default to undefined]
**uid** | **string** |  | [optional] [default to undefined]
**subject** | **string** |  | [optional] [default to undefined]
**from** | **string** |  | [optional] [default to undefined]
**to** | **string** |  | [optional] [default to undefined]
**cc** | **string** |  | [optional] [default to undefined]
**body** | **string** |  | [optional] [default to undefined]
**header** | **string** |  | [optional] [default to undefined]
**larger** | **number** |  | [optional] [default to undefined]
**smaller** | **number** |  | [optional] [default to undefined]
**text** | **string** |  | [optional] [default to undefined]

## Example

```typescript
import { V1FolderMessagesSearchRequest } from 'hostinger-email-api-sdk';

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
