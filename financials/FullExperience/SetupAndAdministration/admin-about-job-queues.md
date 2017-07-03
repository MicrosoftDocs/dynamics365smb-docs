---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# About Data Tables
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] data tables come in two basic types: Master and Setup. When you are setting up a company configuration, you can use these types to focus your configuration strategy.  
  
## Master Data Tables  
 The following table lists a some example [!INCLUDE[d365fin](../../includes/d365fin_md.md)] master data tables. When you initialize a new company, these tables are empty.  
  
### Master Data Tables  
  
|**Table No.**|**Table Name**|  
|-------------------|--------------------|  
|15|G/L Account|  
|18|Customer|  
|23|Vendor|  
|27|Item|  
|5050|Contact|  
  
## Setup Data Tables  
 The following table provides examples of the setup data tables, in which you capture setup information in the configuration questionnaire. These tables contain baseline information when the company is created.  
  
|**Table No.**|**Table Name**|  
|-------------------|--------------------|  
|98|General Ledger Setup|  
|311|Sales & Receivables Setup|  
|312|Purchases & Payables Setup|  
|313|Inventory Setup|  
  
 In addition to setup data tables, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] also has data tables that specify core information about the company and its business processes. The following table provides some examples.  
  
###  
  
|**Table No.**|**Table Name**|  
|-------------------|--------------------|  
|3|Payment Terms|  
|4|Currency|  
|6|Customer Price Groups|  
|5700|Stockkeeping Unit|  
  
## See Also  
 [How to: Manage Company Configuration in a Worksheet](../how-to-manage-company-configuration-in-a-worksheet.md)   
 [How to: Customize a Package or Worksheet](../how-to-customize-a-package-or-worksheet.md)