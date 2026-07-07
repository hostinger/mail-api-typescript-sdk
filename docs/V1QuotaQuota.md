# V1QuotaQuota

Storage and message quota usage for the managed mailbox.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**quotas** | [**Array&lt;V1QuotaQuotaResource&gt;**](V1QuotaQuotaResource.md) | Per-resource quota breakdown reported by the IMAP server. | [default to undefined]
**totalUsage** | **number** | Aggregate storage usage across all resources, in bytes. | [default to undefined]
**totalLimit** | **number** | Aggregate storage limit across all resources, in bytes. | [default to undefined]
**totalPercentage** | **number** | Aggregate storage usage as a percentage of the total limit. | [default to undefined]
**supported** | **boolean** | Whether the IMAP server reports quota information for this mailbox. | [default to undefined]

## Example

```typescript
import { V1QuotaQuota } from 'hostinger-email-api-sdk';

const instance: V1QuotaQuota = {
    quotas,
    totalUsage,
    totalLimit,
    totalPercentage,
    supported,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
