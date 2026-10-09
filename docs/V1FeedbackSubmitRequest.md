# V1FeedbackSubmitRequest

Feedback the user wants to send to the Hostinger mail team. The message is scrubbed of tokens, JWTs and key/secret/password values before validation and storage, so the length limit applies to the scrubbed text.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**score** | **number** | The user\&#39;s rating of the Hostinger Email API: 1 (poor) to 10 (excellent). | [default to undefined]
**message** | **string** | The user\&#39;s feedback in their own words. Never include tokens, passwords or email contents. | [default to undefined]

## Example

```typescript
import { V1FeedbackSubmitRequest } from '@hostinger/mail-sdk';

const instance: V1FeedbackSubmitRequest = {
    score,
    message,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
