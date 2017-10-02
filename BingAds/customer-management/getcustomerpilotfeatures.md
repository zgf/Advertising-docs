---
title: GetCustomerPilotFeatures Service Operation
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# GetCustomerPilotFeatures Service Operation
Gets a list of the pilot programs in which the specified customer participates.

## <a name="request"></a>Request Elements
The *GetCustomerPilotFeaturesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customerid"></a>CustomerId|The identifier of the customer whose list of pilot programs you want to get.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetCustomerPilotFeaturesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="featurepilotflags"></a>FeaturePilotFlags|A list of integers that identifies the pilot programs in which the customer participates.<br /><br />For example the following values correspond to active feature pilots. For more information about pilot participation please contact your account manager.<br /><br />253 - Sitelink 2 Migration<br /><br />268 - Dynamic Search Ads<br /><br />288 - Ad Group Remarketing List Exclusions<br /><br />295 - Maximize Clicks Bid Strategy Type<br /><br />296 - Maximize Conversions Bid Strategy Type<br /><br />297 - Target CPA Bid Strategy Type<br /><br />310 - Campaign Languages<br /><br />340 - Bing Shopping Enhanced CPC Bid Strategy Type<br /><br />351 - Local Inventory Ads|**int**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">GetCustomerPilotFeatures</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetCustomerPilotFeaturesRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <CustomerId>ValueHere</CustomerId>
    </GetCustomerPilotFeaturesRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetCustomerPilotFeaturesResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <FeaturePilotFlags d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:int>ValueHere</a1:int>
      </FeaturePilotFlags>
    </GetCustomerPilotFeaturesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
protected async Task<GetCustomerPilotFeaturesResponse> GetCustomerPilotFeaturesAsync(
	long customerId)
{
	var request = new GetCustomerPilotFeaturesRequest
	{
		CustomerId = customerId
	};

	return (await CustomerManagement.CallAsync((s, r) => s.GetCustomerPilotFeaturesAsync(r), request));
}
```
```java
static GetCustomerPilotFeaturesResponse getCustomerPilotFeatures(
	long customerId)
{
	GetCustomerPilotFeaturesRequest request = new GetCustomerPilotFeaturesRequest();

	request.setCustomerId(customerId);

	return CustomerManagement.getService().getCustomerPilotFeatures(request);
}
```
```php
static function GetCustomerPilotFeatures(
	$customerId)

	$getCustomerPilotFeaturesRequest = new GetCustomerPilotFeaturesRequest();

	$request->CustomerId = $customerId;

	return $CustomerManagementProxy->GetService()->GetCustomerPilotFeatures($request);
}
```
```python
response=customermanagement.GetCustomerPilotFeatures(
	CustomerId=CustomerIdHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  
