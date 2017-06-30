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
# VAT and VIES Report Setup
Depending on the requirements of your country\/region, you must submit periodic VAT reports. In "[!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can define statutory reports such as periodic VAT reports and VIES declarations.  
  
## VAT and VIES Reports  
 In addition to the periodic VAT statements that you submit to settle VAT, the tax authorities can require that you submit periodic reports of transactions that include VAT. If you are a resident of a country\/region in the EU, you must also submit a VIES declaration for trade with other EU countries\/regions. In most cases, the required report must have general information about the company name and the reporting period, and it must have lines or groups of lines that describe the VAT-related transactions. In "[!INCLUDE[d365fin](../../includes/d365fin_md.md)], in the **VAT Report** window, you can define these reports much like you create documents such as orders, invoices, and credit memos. You can fill in the lines based on VAT entries, and then export the VAT report to the appropriate authorities. Depending on your country\/region and the type of VAT report that you have set up, the report can be exported in different formats.  
  
 For detailed information about how "[!INCLUDE[d365fin](../../includes/d365fin_md.md)] Help collection.  
  
### VAT and VIES Report Configuration  
 Before you can create VAT reports, you must specify a number series that will be used for VAT reports and you must specify if your company can make corrective VAT reports. For more information, see [How to: Set Up VAT Reports](../how-to-set-up-vat-reports.md).  
  
 You must also set up general information about how the VAT reports will be created. As part of this, you must specify which processes must be used to print or export the reports. This configuration is performed in preconfigured codeunits. For more information, see [How to: Configure VAT Reports](../how-to-configure-vat-reports.md).  
  
> [!IMPORTANT]  
>  You must be familiar with C\/AL development in order to configure how VAT reports are printed or exported.  
  
## See Also  
 [How to: Configure VAT Reports](../how-to-configure-vat-reports.md)