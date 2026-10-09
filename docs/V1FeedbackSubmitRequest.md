# V1FeedbackSubmitRequest

Feedback about the Mail API or the MCP server. The message is scrubbed of tokens, JWTs and key/secret/password values before validation and storage, so the length limit applies to the scrubbed text.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**score** | **number** | How well the API served the task: 1 (poor) to 10 (excellent). | [default to undefined]
**message** | **string** | What happened and what was expected, including the operation and status code involved. Never include tokens, passwords or email contents. | [default to undefined]

## Example

```typescript
import { V1FeedbackSubmitRequest } from '@hostinger/mail-sdk';

const instance: V1FeedbackSubmitRequest = {
    score,
    message,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
