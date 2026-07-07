# V1QuotaQuotaResource

Usage and limit for a single IMAP quota resource.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**resourceName** | **string** | Name of the quota resource as reported by the IMAP server. | [default to undefined]
**usage** | **number** | Current usage of the resource (bytes for STORAGE, count for MESSAGE). | [default to undefined]
**limit** | **number** | Maximum allowed value for the resource (bytes for STORAGE, count for MESSAGE). | [default to undefined]
**percentage** | **number** | Usage as a percentage of the limit. | [default to undefined]

## Example

```typescript
import { V1QuotaQuotaResource } from 'hostinger-email-api-sdk';

const instance: V1QuotaQuotaResource = {
    resourceName,
    usage,
    limit,
    percentage,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
