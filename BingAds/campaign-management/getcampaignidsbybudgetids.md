---
title: GetCampaignIdsByBudgetIds Service Operation
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# GetCampaignIdsByBudgetIds Service Operation
Gets the campaign identifiers that share each specified budget.

## <a name="request"></a>Request Elements
The *GetCampaignIdsByBudgetIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="budgetids"></a>BudgetIds|A list of unique budget identifiers that identify the campaign identifiers to get. You can specify a maximum of 1,000 IDs budget IDs, and each budget could be shared by up to 10,000 campaign identifiers. For each budget ID that you specify in the request, an [IdCollection](../campaign-management/idcollection.md) that contains between 1 and 10,000 campaign identifers will be returned. <br/><br/>The budget IDs must be in the same account that you specified in the required *CustomerAccountId* header element.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetCampaignIdsByBudgetIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignidcollection"></a>CampaignIdCollection|The list of campaign id collections that corresponds directly to the budget identifiers that you specified in the request. Items of the list may be returned as null. For each list index where an id collection was not retrieved, the corresponding element will be null.|[IdCollection](idcollection.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](../campaign-management/batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetCampaignIdsByBudgetIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetCampaignIdsByBudgetIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <BudgetIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </BudgetIds>
    </GetCampaignIdsByBudgetIdsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetCampaignIdsByBudgetIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <CampaignIdCollection d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <IdCollection>
          <Ids d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </Ids>
        </IdCollection>
      </CampaignIdCollection>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e225="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e225:KeyValuePairOfstringstring>
              <e225:key d4p1:nil="false">ValueHere</e225:key>
              <e225:value d4p1:nil="false">ValueHere</e225:value>
            </e225:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Index>ValueHere</Index>
          <Message d4p1:nil="false">ValueHere</Message>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to EditorialError-->
          <Appealable d4p1:nil="false">ValueHere</Appealable>
          <DisapprovedText d4p1:nil="false">ValueHere</DisapprovedText>
          <Location d4p1:nil="false">ValueHere</Location>
          <PublisherCountry d4p1:nil="false">ValueHere</PublisherCountry>
          <ReasonCode>ValueHere</ReasonCode>
        </BatchError>
      </PartialErrors>
    </GetCampaignIdsByBudgetIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
protected async Task<GetCampaignIdsByBudgetIdsResponse> GetCampaignIdsByBudgetIdsAsync(
	IList<long> budgetIds)
{
	var request = new GetCampaignIdsByBudgetIdsRequest
	{
		BudgetIds = budgetIds
	};

	return (await CampaignManagement.CallAsync((s, r) => s.GetCampaignIdsByBudgetIdsAsync(r), request));
}
```
```java
static GetCampaignIdsByBudgetIdsResponse getCampaignIdsByBudgetIds(
	ArrayOflong budgetIds)
{
	GetCampaignIdsByBudgetIdsRequest request = new GetCampaignIdsByBudgetIdsRequest();

	request.setBudgetIds(budgetIds);

	return CampaignManagement.getService().getCampaignIdsByBudgetIds(request);
}
```
```php
static function GetCampaignIdsByBudgetIds(
	$budgetIds)

	$getCampaignIdsByBudgetIdsRequest = new GetCampaignIdsByBudgetIdsRequest();

	$request->BudgetIds = $budgetIds;

	return $CampaignManagementProxy->GetService()->GetCampaignIdsByBudgetIds($request);
}
```
```python
response=campaignmanagement.GetCampaignIdsByBudgetIds(
	BudgetIds=BudgetIdsHere
)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  
