---
title: "How to: Set Up a Currency Exchange Rate Service"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: d3af5948-3337-4905-bac8-731967f3e674
caps.latest.revision: 9
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Set Up a Currency Exchange Rate Service
You can use an external service to keep your for currency exchange rates up to date. For more information, see [How to: Update Currency Exchange Rates from a Service](../../BusinessFunctionality/DataExchange/how-to-update-currency-exchange-rates-from-a-service.md).  
  
 To update currency exchange rates, for example with the service provided by the European Central Bank, you must first set up the service.  
  
 The service that provides updated currency exchange rates is enabled by a data exchange definition. Accordingly, the **Exch. Rate Update Setup Card** window is a condensed view of the **Data Exchange Definition** window for the data exchange definition in question. For more information, see [How to: Set Up Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md).  
  
### To set up a currency exchange rate service  
  
1.  In the **Search** box, enter **Currency Exchange Rate Services**, and then choose the related link.  
  
2.  Alternatively, in the **Currencies** window, on the **Home** tab, in the **Exchange Rate Service** group, choose **Exchange Rate Services**.  
  
3.  On the **Home** tab, in the **New** group, choose **New**.  
  
4.  On the **General** FastTab in the **Curr. Exch. Rate Service Card** window, fill the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Identify the currency exchange rate service.|  
    |**Description**|Describe the currency exchange rate service.|  
    |**Enabled**|Specify if this currency exchange rate service is enabled.<br /><br /> Only one currency exchange rate service can be enabled at a time.|  
  
5.  On the **Service** FastTab, fill the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Service URL**|Specify the URL of the currency exchange rate service.<br /><br /> Example: The ECB service: http:\/\/www.ecb.europa.eu\/stats\/eurofxref\/eurofxref\-daily.xml|  
    |**Service Provider**|Specify the name of the service provider.|  
    |**Terms of Service**|Specify the URL of the service provider’s terms of use.|  
  
     The other fields are filled automatically.  
  
6.  On the **Field Mapping** FastTab, fill the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Caption**|Specify the caption of a field in ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)]--> that a node in the currency exchange rate file must map to. **Note:**  The four most common fields are automatically entered when you fill the **Web Service URL** field.|  
    |**Source**|Specify the XPath to the XML node that should be mapped to the field specified in the **Caption** field.<br /><br /> When you choose the **Source** field, the **Select Source** window opens where you see and select nodes according to the XML structure of the file.|  
    |**Default Value**|Specify a value that will be used if the currency exchange rate service does not provide a value.|  
    |**Transformation Rule**|Specify a rule for transforming imported text to a supported value before it can be mapped to the specified field.|  
  
7.  To make additional changes to the underlying data exchange definition, on the **Field Mapping** FastTab, choose **Data Exchange Definition**.  
  
8.  To test the setup of the currency exchange rate service, on the **Home** tab, in the **Setup** group, choose **Preview**.  
  
## See Also  
 Currencies   
 Exch. Rate Update Setup Card   
 Data Exch. Field Mapping Buf.   
 [How to: Set Up a Currency Exchange Rate Service](../../BusinessFunctionality/DataExchange/how-to-set-up-a-currency-exchange-rate-service.md)   
 [How to: Set Up Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md)   
 [Data Exchange](../../BusinessFunctionality/DataExchange/data-exchange.md)