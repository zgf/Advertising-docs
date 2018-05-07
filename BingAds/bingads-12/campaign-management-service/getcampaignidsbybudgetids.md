---
title: GetCampaignIdsByBudgetIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the campaign identifiers that share each specified budget.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetCampaignIdsByBudgetIds Service Operation - Campaign Management
Gets the campaign identifiers that share each specified budget.

## <a name="request"></a>Request Elements
The *GetCampaignIdsByBudgetIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="budgetids"></a>BudgetIds|A list of unique budget identifiers that identify the campaign identifiers to get. You can specify a maximum of 1,000 IDs budget IDs, and each budget could be shared by up to 10,000 campaign identifiers. For each budget ID that you specify in the request, an [IdCollection](idcollection.md) that contains between 1 and 10,000 campaign identifers will be returned. <br/><br/>The budget IDs must be in the same account that you specified in the required *CustomerAccountId* header element.|**long** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetCampaignIdsByBudgetIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignidcollection"></a>CampaignIdCollection|The list of campaign id collections that corresponds directly to the budget identifiers that you specified in the request. Items of the list may be returned as null. For each list index where an id collection was not retrieved, the corresponding element will be null.|[IdCollection](idcollection.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
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
    <GetCampaignIdsByBudgetIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
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
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetCampaignIdsByBudgetIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
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
          <ForwardCompatibilityMap xmlns:e1046="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1046:KeyValuePairOfstringstring>
              <e1046:key d4p1:nil="false">ValueHere</e1046:key>
              <e1046:value d4p1:nil="false">ValueHere</e1046:value>
            </e1046:KeyValuePairOfstringstring>
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
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetCampaignIdsByBudgetIdsResponse> GetCampaignIdsByBudgetIdsAsync(
	IList<long> budgetIds)
{
	var request = new GetCampaignIdsByBudgetIdsRequest
	{
		BudgetIds = budgetIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetCampaignIdsByBudgetIdsAsync(r), request));
}
```
```java
static GetCampaignIdsByBudgetIdsResponse getCampaignIdsByBudgetIds(
	ArrayOflong budgetIds) throws RemoteException, Exception
{
	GetCampaignIdsByBudgetIdsRequest request = new GetCampaignIdsByBudgetIdsRequest();

	request.setBudgetIds(budgetIds);

	return CampaignManagementService.getService().getCampaignIdsByBudgetIds(request);
}
```
```php
static function GetCampaignIdsByBudgetIds(
	$budgetIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetCampaignIdsByBudgetIdsRequest();

	$request->BudgetIds = $budgetIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetCampaignIdsByBudgetIds($request);
}
```
```python
response=campaignmanagement_service.GetCampaignIdsByBudgetIds(
	BudgetIds=BudgetIds)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  
