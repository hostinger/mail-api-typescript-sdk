# ModelError

Standard error envelope. Frontend translations key off `code`, never off `error`.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**error** | **string** | Human-readable error message. | [default to undefined]
**code** | **string** | Machine-readable error code in SCREAMING_SNAKE_CASE. | [default to undefined]
**params** | **{ [key: string]: any; }** | Additional structured context for the error. May be omitted. | [optional] [default to undefined]

## Example

```typescript
import { ModelError } from 'hostinger-email-api-sdk';

const instance: ModelError = {
    error,
    code,
    params,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
