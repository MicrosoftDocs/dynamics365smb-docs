---
title: Record and Adjust Resource Usage and Prices
description: Describes how you can record the resource usage or consumption associated with a project, to keep track and manage costs, prices, and work types.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: project management, capacity, staff
ms.search.form: 201,206, 207, 271, 493
ms.date: 02/22/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.custom: bap-template
ms.reviewer: bholtorf
---
# Use resources for projects

You record the usage of resources in the project journal to keep track of costs, prices, and the work types that are linked to projects. For more information, see [Record Usage for Projects](projects-how-record-job-usage.md).

> [!NOTE]
> You can also purchase external resources, for example, to invoice a vendor for work delivered. For more information, see [Record Purchases](purchasing-how-record-purchases.md).

You can also post the usage of a resource in a resource journal. Entries posted in a resource journal have no effect on the general ledger.

## To assign resources to projects

You assign resources to projects by creating project planning lines for the project. For more information, see [Create Projects](projects-how-create-jobs.md).

## To record resource usage for a project

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Project Journals**, and then choose the related link.
2. Open a relevant project journal batch, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. When the journal is complete, choose the **Post** action.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## To adjust resource prices

If you want to change costs or prices for a large number of resources, you can use a batch job.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Adjust Resource Costs/Prices**, and then choose the related link.
2. Fill in the fields on a line as necessary, and then choose the **OK** button.

> [!NOTE]  
> This batch job does not create or adjust alternate costs or prices for resources. It only changes the contents of the field on the resource card for the **Adjust Field** field that you selected in the batch job. The adjustment will take effect immediately for resources, so check your adjustment factors before you run the batch job.

## To get resource price change suggestions based on existing alternate prices

If you have already set up alternate resource price for some resources, you can use a batch job to set up multiple alternate resource prices.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resource Price Changes**, and then choose the related link.
2. Choose the **Suggest Res. Price Chg. (Price)** action, and then fill in the fields as necessary.
3. Choose the **OK** button.  
4. When the batch job is finished, the **Resource Price Changes** page shows the results of the batch job.

## To get resource price change suggestions based on standard prices

If you want to set up multiple alternate resource prices based on the standard prices on the resource cards, you can use a batch job.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resource Price Changes**, and then choose the related link.
2. Choose the **Suggest Res. Price Chg. (Res.)** action, and then fill in the fields as necessary.  
3. Choose the **OK** button.  
4. When the batch job is finished, open the **Resource Price Changes** page to see the results of the batch job.

## To get resource price change suggestions based on alternate prices

If you have already set up alternate resource price for some resources, you can use a batch job to set up multiple alternate resource prices.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Suggest Res. Price Chg. (Price)**, and then choose the related link.  
2. Fill in the fields as necessary.
3. Choose the **OK** button.  
4. When the batch job is finished, open the **Resource Price Changes** page to see the results of the batch job.

## See Also

[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)         
[Sales](sales-manage-sales.md)     
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]