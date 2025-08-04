---
title: WIP methods for calculating and recording project progress
description: Describes the different work in process (WIP) methods you can use to post, monitor, and calculate financial information for projects that are in progress.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: work in process, work in progress, calculate project WIP
ms.search.form: 1010,
ms.date: 08/19/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Understanding WIP methods in project management

As a project progresses, materials, resources, and other expenses are consumed and must be posted to the project. Work in Process (WIP) is a feature that enables you to estimate the financial value of projects in the general ledger while the projects are ongoing. In many cases, you might post expenses for a project before invoicing a project. When only expenses are posted, your financial statement is inaccurate.

To track the value in the general ledger, you can calculate WIP and post the value to the general ledger. For more information, see [Monitor Project Progress and Performance](projects-how-monitor-progress-performance.md).

Out of the box, [!INCLUDE[prod_short](includes/prod_short.md)] supports the following methods of calculating and recording the value of work in process.

| WIP Method | Description | Recognized Costs | Recognized Sales |
| --- | ------- |--- | --- |
| Cost Value |Recognizes cost when the customer is invoiced. Recognizes sales based on the invoiced sales. |Cost Value|Contract (Invoice Price)|
| Cost of Sales |Recognizes cost when the customer is invoiced. Recognizes sales based on the invoiced sales.|Cost of Sales|Contract (Invoiced Price)|
| Sales Value |Recognizes costs as they're reported. Recognizes sales proportionally to the reported costs.|Usage (Total Cost)|Sales Value|
| Percentage of Completion |Recognizes costs as they're reported. Recognizes sales proportionally to the reported costs.|Usage (Total Cost)|Percentage of Completion|
| Completed Contract |No sales or costs are part of the WIP calculation. Completed contract doesn't recognize revenue and costs until the project is complete. For example, this option is useful when there's high uncertainty around the estimates of costs and revenue for the project.|At Completion|At Completion|

Exact formulas and general ledger transactions are defined by the selection in the [**Recognized Cost**](#recognized-cost) and [**Recognized Sales**](#recognized-sales) fields.

## Create a project WIP method

Create a project WIP method that meets the needs of your organization and set it as the default.  

> [!NOTE]
> After you use a method to create WIP entries, you can't modify or delete the method.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Project WIP Methods**, and then choose the related link.  
2. Choose the **New** action, select the appropriate values for the **Recognized Costs** and **Recognized Sales** fields, and then fill in the other fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Close the page.
4. To make this method the default, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **projects setup**, and then choose the related link.  
5. In the **Default WIP Method** field, choose the method from the list.

### Recognized cost

| Recognized Cost | Recognized Cost Calculation Formula | General Ledger Entries |
| --- | --- | ---------- |
|At Completion|0 (Zero)|Dt **Recognized Costs Account** Cr **WIP Costs Account** </br>Amount: RecognizedCost </br></br>Dt **WIP Costs Account** Cr **Project Costs Applied Account** </br>Amount: MAX[RecognizedCost; Actual (Total Cost)]|
|Cost of Sales|Actual (Total Cost) - Budget (Total Costs) * Invoiced%, where:</br></br> Invoiced% = Invoiced (Total Price) / Billable (Total Price)</br></br>**Note:** This calculation requires that the Billable (Total Price) and Budget (Total Costs) are correctly entered for the whole project.|Dt **Recognized Costs Account** Cr **WIP Costs Account** </br>Amount: RecognizedCost </br></br>Dt **WIP Costs Account** Cr **Project Costs Applied Account** </br>Amount: MAX[RecognizedCost; Actual (Total Cost)] </br></br>Dt **Project Costs Adjustment Account** Cr **WIP Accrued Costs Account** </br>Amount: RecognizedCost – Actual (Total Cost), If RecognizedCost > Actual (Total Cost)|
|Cost Value|Actual (Total Cost) – [Completion% – Invoiced%] * Billable (Total Price) * BudgetCostPriceRatio, where: </br></br> BudgetCostPriceRatio = Budget(Total Cost) / Budget (Total Price)</br>Invoiced% = Invoiced (Total Price) / Billable (Total Price)</br>Completion% = Actual (Total Cost)/Budget (Total Cost)</br></br>**Note:** This calculation requires that the Billable (Total Price), Budget ( Total Price), and Budget (Total Costs) be correctly entered for the whole project.|Dt **Recognized Costs Account** Cr **WIP Costs Account** </br>Amount: RecognizedCost</br></br>Dt **WIP Costs Account** Cr **Project Costs Applied Account** </br>Amount: MAX[RecognizedCost; Actual (Total Cost)] </br></br>Dt **Project Costs Adjustment Account** Cr **WIP Accrued Costs Account** </br>Amount:	RecognizedCost – Actual (Total Cost), If RecognizedCost > Actual (Total Cost)|
|Contract (Invoiced Cost)|Invoiced (Total Cost) |Dt **Recognized Costs Account** Cr **WIP Costs Account** </br>Amount: RecognizedCost </br></br> Dt **WIP Costs Account** Cr **Project Costs Applied Account** </br>Amount: MAX[RecognizedCost; Actual (Total Cost)] </br></br>Dt **Project Costs Adjustment Account** Cr **WIP Accrued Costs Account**	</br>Amount: RecognizedCost – Actual (Total Cost), If RecognizedCost > Actual (Total Cost)|
|Usage (Total Cost)|Actual (Total Cost) |Dt **Recognized Costs Account** Cr **WIP Costs Account** </br>Amount: RecognizedCost </br></br>Dt **WIP Costs Account** Cr **Project Costs Applied Account** </br>Amount: MAX[RecognizedCost; Actual (Total Cost)]|

When project status is changed to Completed, the **Calculate WIP** task reverts the WIP transaction and posts instead.

Dt **Recognized Cost Account** Cr **Project Cost Applied Account** , Amount: **Actual (Total Cost)**

> [!NOTE]
> Depending on the selection in the **WIP Posting Method Used** field, the **Item Cost Applied Account**, **Resource Cost Applied Account**, or **G/L Cost Applied Account** could be used instead of **Project Cost Applied Account**. For more information, see [Project posting groups](projects-how-setup-jobs.md#to-set-general-information-for-projects).

### Recognized sales

| Recognized Sales | Recognized Sales Calculation Formula | General Ledger Entries |
| --- | --- | ---------- |
|At Completion|0 (Zero)|Dt **WIP Invoiced Sales Account** Cr **Recognized Sales Account** </br>Amount: RecognizedSales</br></br>Dt **Project Sales Applied Account** Cr **WIP Invoiced Sales Account** </br>Amount: Invoiced (Total Price)|
|Contract (Invoiced Price)|Invoiced (Total Price)|Dt **WIP Invoiced Sales Account** Cr **Recognized Sales Account** </br>Amount: RecognizedSales</br></br>Dt **Project Sales Applied Account** Cr **WIP Invoiced Sales Account** </br>Amount: Invoiced (Total Price)|
|Usage (Total Cost)|Actual (Total Cost)|Dt **WIP Invoiced Sales Account** Cr **Recognized Sales Account** </br>Amount: RecognizedSales</br></br>Dt **Project Sales Applied Account** Cr **WIP Invoiced Sales Account** </br>Amount: Invoiced (Total Price)
|Percentage of Completion|MIN[Billable (Total Price) * Completion%; Billable (Total Price)], where:</br></br>Completion% = Actual (Total Cost)/Budget (Total Cost)</br></br>**Note:** This calculation requires that the Billable (Total Price) and Budget (Total Costs) are correctly entered for the whole project.|Dt **WIP Accrued Sales Account** Cr **Recognized Sales Account** </br>Amount: RecognizedSales</br></br>Dt **Project Sales Applied Account** Cr **WIP Invoiced Sales Account** </br>Amount: Invoiced (Total Price)|
|Usage (Total Price)|Actual (Total Price)|Dt **WIP Invoiced Sales Account** Cr **Recognized Sales Account** </br>Amount: RecognizedSales </br></br>Dt **Project Sales Applied Account** Cr **WIP Invoiced Sales Account** </br>Amount: MAX[RecognizedSales; Invoiced (Total Price)]</br></br>Dt **WIP Accrued Sales Account** Cr **Project Sales Adjustment Account** </br>Amount: MAX[RecognizedSales; Invoiced (Total Price)] - Invoiced (Total Price)|
|Sales Value| Actual (Total Price) * Billable (Total Price)/Budget (Total Price)</br></br>**Note:** This calculation requires that the Billable (Total Price) and Budget (Total Price) are correctly entered for the whole project.|Dt **WIP Invoiced Sales Account** Cr **Recognized Sales Account** </br>Amount: RecognizedSales</br></br>Dt **Project Sales Applied Account** Cr **WIP Invoiced Sales Account** </br>Amount: MAX[RecognizedSales; Invoiced (Total Price)]</br></br>Dt **WIP Accrued Sales Account** Cr **Project Sales Adjustment Account** </br>Amount: MAX[RecognizedSales; Invoiced (Total Price)] - Invoiced (Total Price)|

When the project status is changed to Completed, the **Calculate WIP** task reverts the WIP transaction and posts instead.

Dt **Project Sales Applied Account** Cr **Recognized Sales Account** , Amount: **Invoiced (Total Price)**

## Related information

[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
