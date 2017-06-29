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
# Service Order Statistics
The service order statistics feature gives you a quick overview of the contents of the entire service order, the details on the specific service lines, and information related to invoicing, shipping and consuming, and the customer's balance.  
  
 The statistical data is displayed for a service order in the **Service Order Statistics** window for the relevant order. You can open the relevant statistics window from a service order. In the **Service Orders** window, on the **Home** tab, in the **Process** group, choose **Statistics**. The FastTabs in this window show information such as quantity, amount, VAT, cost, profit, and customer credit limit. The amounts in the window are in the currency of the service order, unless otherwise indicated.  
  
## General FastTab  
 Use this FastTab to see the totals of the service order. The data captures the total amount on the service lines, including and excluding VAT, VAT part, cost, and profit on the service lines. The FastTab also displays specific item-related information about the items indicated on the service lines, such as weight, volume, and the quantity of parcels.  
  
## Shipping FastTab  
 Use this FastTab to display information about the items, resources, or costs to be shipped. To provide the information, the values specified in the **Qty. to Ship** field are used on each service line in the order.  
  
## Details FastTab  
 Use this FastTab to view information about the items, resource hours, and costs to be invoiced and consumed. The following table describes the information about the FastTab, which is presented in three columns.  
  
|Column|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
|------------|---------------------------------------|  
|**Invoicing**|Displays amounts that are to be posted as invoiced from the service order.|  
|**Consuming**|Displays the quantity and cost of items, or resources that will be posted as consumed.|  
|**Total**|Displays the total amounts on the service order that result from adding the invoicing amounts to the consuming amounts.|  
  
## Service Line FastTab  
 Use this FastTab to analyze the information presented on the **General** FastTab by the types of service lines included in the service order. Therefore, the amounts are shown separately for:  
  
-   Items  
  
-   Resources  
  
-   Costs and general ledger accounts  
  
## Customer FastTab  
 Use this FastTab to see the balance on the customer's account, in addition to the maximum credit that can be endued to the customer who you created the service document for.  
  
 The lines in the lower part of the **Service Statistics** window show the VAT details on the amounts in the service document.  
  
## See Also  
 [Service Statistics](../Service/service-statistics.md)   
 [How to: View Service Order Statistics](../Service/how-to-view-service-order-statistics.md)