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
# How to: Set Up Sales Tax Details
The **Tax Details** window contains a matrix table that uses different combinations of sales tax jurisdictions and sales tax groups to establish sales tax rates. For each tax jurisdiction, you are advised to set up one tax group for normal sales tax, another tax group for items or services that are not taxed, and an additional tax group for every type of item or service that is handled with a different sales tax rate in that jurisdiction.  
  
 In the United States, when you sell to a customer at a location where you do not have a *situs*—or a legal location in that state—you do not collect sales tax. For locations in which you do not have a situs, ensure that both the **Tax Below Minimum** and **Tax Above Maximum** fields are 0.00.  
  
### To set up sales tax details  
  
1.  In the **Search** box, enter **Tax Details**, and then choose the related link.  
  
2.  In the **Tax Details** window, on the **Home** tab, in the **New** group, choose **New**.  
  
3.  In the **New \- Tax Details** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Tax Jurisdiction Code**|The tax jurisdiction code for the tax detail entry.|  
    |**Tax Group Code**|The tax group code for the tax detail entry.|  
    |**Tax Type**|**Sales and Use Tax** – To apply both sales tax and use tax to the tax detail entry.<br /><br /> –or–<br /><br /> **Excise Tax** – To apply excise tax to the tax detail entry.<br /><br /> –or–<br /><br /> **Sales Tax Only** – To apply only sales tax to the tax detail entry.<br /><br /> –or–<br /><br /> **Use Tax Only** – To apply only use tax to the tax detail entry.|  
    |**Effective Date**|The date from which the tax detail entry is effective.|  
    |**Tax Below Maximum**|The percentage that will be used to calculate tax for all amounts or quantities below the maximum amount\/quantity in the **Maximum Amount\/Qty** field.|  
    |**Maximum Amount\/Qty**|The maximum amount or quantity.|  
    |**Tax Above Maximum**|The percentage that will be used to calculate tax for all amounts or quantities above the maximum amount\/quantity in the **Maximum Amount\/Qty** field.|  
  
4.  Choose the **OK** button.  
  
### To set up sales tax for a customer  
  
1.  In the **Search** box, enter **Customers**, and then choose the related link.  
  
2.  Select the required customer. On the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **Invoicing** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Tax Liable**|Select to set up tax liability.|  
    |**Tax Area Code**|The tax area code of the customer.|  
    |**Tax Identification Type**|The tax identification type of the customer.|  
  
4.  Choose the **OK** button.  
  
 For customers with ship\-to addresses, you can select whether sales to each alternative address are tax liable, and you can enter a tax area code for each alternative address. This allows you to select the tax area that corresponds to the ship\-to location.  
  
## See Also  
 Sales Tax Detail by Area   
 Sales Tax Detail List   
 [How to: Set Up Sales Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-sales-tax.md)   
 [How to: Set Up Sales Tax Groups](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-sales-tax-groups.md)   
 [How to: Set Up Sales Tax Jurisdictions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-sales-tax-jurisdictions.md)   
 [How to: Set Up Unrealized Sales Tax and Sales Payment Discounts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-unrealized-sales-tax-and-sales-payment-discounts.md)   
 [How to: Set Up Use Tax and Purchase Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-use-tax-and-purchase-tax.md)