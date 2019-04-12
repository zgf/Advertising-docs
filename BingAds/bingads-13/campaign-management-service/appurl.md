---
title: AppUrl Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the operating system platform and URL of the app store download webpage.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# AppUrl Data Object - Campaign Management
Defines the operating system platform and URL of the app store download webpage.

> [!NOTE]
> Reserved for future use.

## Syntax
```xml
<xs:complexType name="AppUrl" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="OsType" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Url" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ostype"></a>OsType|Reserved for future use.|**string**|
|<a name="url"></a>Url|Reserved for future use.|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[Ad](ad.md)  
[AppAdExtension](appadextension.md)  
[BiddableAdGroupCriterion](biddableadgroupcriterion.md)  
[ImageAdExtension](imageadextension.md)  
[Keyword](keyword.md)  
[SitelinkAdExtension](sitelinkadextension.md)  