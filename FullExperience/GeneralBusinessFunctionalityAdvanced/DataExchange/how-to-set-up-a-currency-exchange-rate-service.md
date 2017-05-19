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
  
 The service that provides updated currency exchange rates is enabled by a data exchange definition. Accordingly, the **\($ N\_1651 Exch. Rate Update Setup Card $\)** window is a condensed view of the **\($ N\_1210 Data Exchange Definition $\)** window for the data exchange definition in question. For more information, see [How to: Set Up Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md).  
  
### To set up a currency exchange rate service  
  
1.  In the **Search** box, enter **Currency Exchange Rate Services**, and then choose the related link.  
  
2.  Alternatively, in the **Currencies** window, on the **Home** tab, in the **Exchange Rate Service** group, choose **Exchange Rate Services**.  
  
3.  On the **Home** tab, in the **New** group, choose **New**.  
  
4.  On the **General** FastTab in the **\($ N\_1651 Curr. Exch. Rate Service Card $\)** window, fill the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_1650\_1 Code $\)**|Identify the currency exchange rate service.|  
    |**\($ T\_1650\_2 Description $\)**|Describe the currency exchange rate service.|  
    |**\($ T\_1650\_5 Enabled $\)**|Specify if this currency exchange rate service is enabled.<br /><br /> Only one currency exchange rate service can be enabled at a time.|  
  
5.  On the **Service** FastTab, fill the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_1650\_3 Service URL $\)**|Specify the URL of the currency exchange rate service.<br /><br /> Example: The ECB service: http:\/\/www.ecb.europa.eu\/stats\/eurofxref\/eurofxref\-daily.xml|  
    |**\($ T\_1650\_10 Service Provider $\)**|Specify the name of the service provider.|  
    |**\($ T\_1650\_11 Terms of Service $\)**|Specify the URL of the service provider’s terms of use.|  
  
     The other fields are filled automatically.  
  
6.  On the **Field Mapping** FastTab, fill the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_1265\_20 Caption $\)**|Specify the caption of a field in [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] that a node in the currency exchange rate file must map to. **Note:**  The four most common fields are automatically entered when you fill the **\($ T\_1650\_3 Web Service URL $\)** field.|  
    |**\($ T\_1265\_13 Source $\)**|Specify the XPath to the XML node that should be mapped to the field specified in the **\($ T\_1265\_20 Caption $\)** field.<br /><br /> When you choose the **\($ T\_1265\_13 Source $\)** field, the **Select Source** window opens where you see and select nodes according to the XML structure of the file.|  
    |**\($ T\_1265\_11 Default Value $\)**|Specify a value that will be used if the currency exchange rate service does not provide a value.|  
    |**\($ T\_1265\_23 Transformation Rule $\)**|Specify a rule for transforming imported text to a supported value before it can be mapped to the specified field.|  
  
7.  To make additional changes to the underlying data exchange definition, on the **Field Mapping** FastTab, choose **Data Exchange Definition**.  
  
8.  To test the setup of the currency exchange rate service, on the **Home** tab, in the **Setup** group, choose **Preview**.  
  
## See Also  
 [\($ N\_5 Currencies $\)](assetId:///c41486d9-65f9-416a-b138-8de3ded8333b)   
 [\($ N\_1651 Exch. Rate Update Setup Card $\)](../Topic/\($%20N_1651%20Exch.%20Rate%20Update%20Setup%20Card%20$\).md)   
 [\($ T\_1265 Data Exch. Field Mapping Buf. $\)](../Topic/\($%20T_1265%20Data%20Exch.%20Field%20Mapping%20Buf.%20$\).md)   
 [How to: Set Up a Currency Exchange Rate Service](../../BusinessFunctionality/DataExchange/how-to-set-up-a-currency-exchange-rate-service.md)   
 [How to: Set Up Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md)   
 [Data Exchange](../../BusinessFunctionality/DataExchange/data-exchange.md)