---
title: GetSharedEntityAssociationsBySharedEntityIds Service Operation
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# GetSharedEntityAssociationsBySharedEntityIds Service Operation
Gets shared entity associations for the specified negative keyword lists.

## <a name="request"></a>Request Elements
The *GetSharedEntityAssociationsBySharedEntityIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entitytype"></a>EntityType|The type of entity corresponding to the specified *EntityIds* element.<br /><br />Currently the only supported value is *Campaign*.|**string**|
|<a name="sharedentityids"></a>SharedEntityIds|The list of negative keyword list identifiers to return associations with campaigns.<br /><br />This array can contain a maximum of one element.|**long**|
|<a name="sharedentitytype"></a>SharedEntityType|The type of shared entity to get associations from the account's library.<br /><br />Currently the only supported value is *NegativeKeywordList*.|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetSharedEntityAssociationsBySharedEntityIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="associations"></a>Associations|An array of [SharedEntityAssociation](../campaign-management/sharedentityassociation.md) objects that corresponds directly to the shared entity identifiers that you specified in the request. Items of the list may be returned as null. For each list index where an association was not retrieved, the corresponding element will be null.|[SharedEntityAssociation](sharedentityassociation.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](../campaign-management/batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetSharedEntityAssociationsBySharedEntityIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetSharedEntityAssociationsBySharedEntityIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <EntityType i:nil="false">ValueHere</EntityType>
      <SharedEntityIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </SharedEntityIds>
      <SharedEntityType i:nil="false">ValueHere</SharedEntityType>
    </GetSharedEntityAssociationsBySharedEntityIdsRequest>
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
    <GetSharedEntityAssociationsBySharedEntityIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <Associations d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <SharedEntityAssociation>
          <EntityId>ValueHere</EntityId>
          <EntityType d4p1:nil="false">ValueHere</EntityType>
          <SharedEntityId>ValueHere</SharedEntityId>
          <SharedEntityType d4p1:nil="false">ValueHere</SharedEntityType>
        </SharedEntityAssociation>
      </Associations>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e256="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e256:KeyValuePairOfstringstring>
              <e256:key d4p1:nil="false">ValueHere</e256:key>
              <e256:value d4p1:nil="false">ValueHere</e256:value>
            </e256:KeyValuePairOfstringstring>
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
    </GetSharedEntityAssociationsBySharedEntityIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
protected async Task<GetSharedEntityAssociationsBySharedEntityIdsResponse> GetSharedEntityAssociationsBySharedEntityIdsAsync(
	string entityType,
	IList<long> sharedEntityIds,
	string sharedEntityType)
{
	var request = new GetSharedEntityAssociationsBySharedEntityIdsRequest
	{
		EntityType = entityType,
		SharedEntityIds = sharedEntityIds,
		SharedEntityType = sharedEntityType
	};

	return (await CampaignManagement.CallAsync((s, r) => s.GetSharedEntityAssociationsBySharedEntityIdsAsync(r), request));
}
```
```java
static GetSharedEntityAssociationsBySharedEntityIdsResponse getSharedEntityAssociationsBySharedEntityIds(
	string entityType,
	ArrayOflong sharedEntityIds,
	string sharedEntityType)
{
	GetSharedEntityAssociationsBySharedEntityIdsRequest request = new GetSharedEntityAssociationsBySharedEntityIdsRequest();

	request.setEntityType(entityType);
	request.setSharedEntityIds(sharedEntityIds);
	request.setSharedEntityType(sharedEntityType);

	return CampaignManagement.getService().getSharedEntityAssociationsBySharedEntityIds(request);
}
```
```php
static function GetSharedEntityAssociationsBySharedEntityIds(
	$entityType,
	$sharedEntityIds,
	$sharedEntityType)

	$getSharedEntityAssociationsBySharedEntityIdsRequest = new GetSharedEntityAssociationsBySharedEntityIdsRequest();

	$request->EntityType = $entityType;
	$request->SharedEntityIds = $sharedEntityIds;
	$request->SharedEntityType = $sharedEntityType;

	return $CampaignManagementProxy->GetService()->GetSharedEntityAssociationsBySharedEntityIds($request);
}
```
```python
response=campaignmanagement.GetSharedEntityAssociationsBySharedEntityIds(
	EntityType=EntityTypeHere,
	SharedEntityIds=SharedEntityIdsHere,
	SharedEntityType=SharedEntityTypeHere
)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  
