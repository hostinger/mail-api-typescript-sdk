# Pagination

Pagination metadata for paginated collections.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**page** | **number** | Current page number (1-based). | [default to undefined]
**perPage** | **number** | Items per page. | [default to undefined]
**total** | **number** | Total number of items across all pages. | [default to undefined]
**totalPages** | **number** | Total number of pages. | [default to undefined]

## Example

```typescript
import { Pagination } from 'hostinger-email-api-sdk';

const instance: Pagination = {
    page,
    perPage,
    total,
    totalPages,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
