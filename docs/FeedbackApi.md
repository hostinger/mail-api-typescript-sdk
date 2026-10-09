# FeedbackApi

All URIs are relative to *https://api.mail.hostinger.com*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**submitFeedback**](#submitfeedback) | **POST** /api/v1/mailboxes/{mailboxResourceId}/feedback | Submit feedback|

# **submitFeedback**
> submitFeedback(v1FeedbackSubmitRequest)

Send the user\'s feedback about the Hostinger Email API to the Hostinger mail team.  Only call this when the user explicitly asks to send feedback, report a problem, or request a feature. Send the user\'s own words; never include tokens, passwords or email contents. The message is capped at 2000 characters.  A `429` (`ERR_FEEDBACK_RATE_LIMIT`) means feedback for this customer was submitted less than ten seconds ago; wait and retry.

### Example

```typescript
import {
    FeedbackApi,
    Configuration,
    V1FeedbackSubmitRequest
} from '@hostinger/mail-sdk';

const configuration = new Configuration();
const apiInstance = new FeedbackApi(configuration);

let mailboxResourceId: string; //Resource ID of the managed mailbox the feedback is about, as returned by `GET /api/v1/me`. (default to undefined)
let v1FeedbackSubmitRequest: V1FeedbackSubmitRequest; //

const { status, data } = await apiInstance.submitFeedback(
    mailboxResourceId,
    v1FeedbackSubmitRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **v1FeedbackSubmitRequest** | **V1FeedbackSubmitRequest**|  | |
| **mailboxResourceId** | [**string**] | Resource ID of the managed mailbox the feedback is about, as returned by &#x60;GET /api/v1/me&#x60;. | defaults to undefined|


### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**204** | Feedback accepted. |  -  |
|**401** | Missing or invalid credentials. |  -  |
|**403** | Token is not authorized to manage the requested mailbox. |  -  |
|**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
|**429** | Feedback for this customer was submitted less than ten seconds ago. Wait and retry. |  -  |
|**500** | Server-side failure. |  -  |
|**502** | Upstream service is unavailable or returned an unexpected response. |  -  |
|**504** | Upstream service did not respond within the configured timeout. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

