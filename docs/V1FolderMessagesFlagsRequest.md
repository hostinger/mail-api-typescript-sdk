# V1FolderMessagesFlagsRequest

Add and/or remove flags on a message. At least one of addFlags or removeFlags must be set.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**addFlags** | **Array&lt;string&gt;** |  | [optional] [default to undefined]
**removeFlags** | **Array&lt;string&gt;** |  | [optional] [default to undefined]

## Example

```typescript
import { V1FolderMessagesFlagsRequest } from 'hostinger-email-api-sdk';

const instance: V1FolderMessagesFlagsRequest = {
    addFlags,
    removeFlags,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
