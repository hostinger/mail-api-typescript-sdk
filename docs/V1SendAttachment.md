# V1SendAttachment

Attachment payload for outgoing mail. Supports regular attachments and inline images linked via Content-ID.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**filename** | **string** |  | [default to undefined]
**content** | **string** | Attachment body. Base64-encoded by default; set encoding to switch. | [default to undefined]
**contentType** | **string** |  | [optional] [default to undefined]
**cid** | **string** | Content-ID for inline images. Reference from HTML as &lt;img src&#x3D;\&quot;cid:logo\&quot;&gt;. | [optional] [default to undefined]
**encoding** | **string** | Encoding of content. Defaults to base64. | [optional] [default to undefined]

## Example

```typescript
import { V1SendAttachment } from 'hostinger-email-api-sdk';

const instance: V1SendAttachment = {
    filename,
    content,
    contentType,
    cid,
    encoding,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
