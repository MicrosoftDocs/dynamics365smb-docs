---
title: Maintain Fixed Assets| Microsoft Docs
description: You keep a maintenance record of any repairs and service on a fixed asset.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: repair, service
ms.date: 04/01/2020
ms.author: sgroespe

---
# Maintain Fixed Assets
Maintenance expenses are routine periodic costs undertaken to preserve the value of fixed assets. Unlike capital improvements, they do not increase values.

You can record and maintain an up-to-date file on maintenance and service of your fixed assets to have complete maintenance records on a fixed asset easily accessible. Each time a fixed asset is sent to service, you record all relevant information such as date of service, vendor number and service agent's phone number. Maintenance registration is recorded for each fixed asset from the relevant fixed asset card.

Indexation is used to adjust values for general price-level changes. The **Index Fixed Assets** batch job can be used to recalculate the maintenance costs.

## To record maintenance work on a fixed asset
Every time maintenance has been performed, such as a service visit, you can record it for the relevant fixed asset on the **Maintenance Registrations** page.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then choose the related link.  
2. Select the fixed asset that you want to record maintenance for, and then choose the **Maintenance Registration** action.
3. On the **Maintenance Registration** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## To post maintenance costs from a fixed asset G/L journal
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Depreciation Book List**, and then choose the related link.  
2. Select the depreciation book that is assigned to the fixed asset, and then choose the **Edit** action.
3. On the **Depreciation Book Card** page, make sure the **Maintenance** check box is not selected. This ensures that maintenance costs are not posted to the general ledger.
4. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA G/L Journals**, and then choose the related link.  
5. Create an initial journal line and fill in the fields as necessary.
6. In the **FA Posting Type** field, select **Maintenance**.
7. Choose the **Insert FA Bal. Account** action. A second journal line is created for the balancing account that is set up for maintenance posting.

    > [!NOTE]  
    >   Step 7 only works if you have set up the following: On the **FA Posting Group Card** page for the posting group of the fixed asset, the **Maintenance Account** field contains the general ledger debit account and the **Maintenance Bal. Account** field contains the general ledger account to which you want to post balancing entries for appreciation. For more information, see [To set up fixed asset posting groups](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).
8. Choose the **Post** action.

## To follow up on fixed assets service visits
You can print the **Maintenance - Next Service** report to see which assets you have scheduled a service visit for. You can also use this report when you are updating the **Next Service Date** field on fixed asset cards.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Maintenance Next Service**, and then choose the related link.  
2. Fill in the **Starting Date** and **Ending Date** fields.  
3. Choose the **Print** or **Preview** button.

## To monitor maintenance costs
You can view the maintenance costs when you look at the statistics of a fixed asset.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then choose the related link.
2. Select the fixed asset you want to view maintenance costs for, and then choose the **Depreciation Books** action.
3. On the **FA Depreciation Books** page, select the relevant fixed asset depreciation book, and then choose the **Statistics** action.
4. On the **Fixed Asset Statistics** page, choose the **Maintenance** field.

The **Maintenance Ledger Entries** page opens showing the entries that make up the amount in the **Maintenance** field.

## To view or print maintenance costs for multiple fixed assets
In the **Maintenance - Analysis** report, you can select to see maintenance based on one, two, or three maintenance codes for a specified date or period. You can see the total of all selected assets or a total for each asset.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Maintenance Analysis**, and then choose the related link.
2. Fill in the fields as necessary.
3. Choose the **Print** or **Preview** button.

## To view maintenance ledger entries
You can also study maintenance costs by viewing the maintenance ledger entries.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then choose the related link.
2. Select the fixed asset that you want to view ledger entries for, and then choose the **Depreciation Books** action.
3. On the **FA Depreciation Books** page, select the relevant fixed asset depreciation book, and then choose the **Maintenance Ledger Entries** action.

## To view or print maintenance ledger entries for multiple fixed assets
In the **Maintenance - Details** report, you can view or print maintenance ledger entries for one or many fixed assets.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Maintenance Details**, and then choose the related link.
2. Fill in the fields as necessary.
3. Choose the **Print** or **Preview** button.

## See Also
[Fixed Assets](fa-manage.md)  
[Setting Up Fixed Assets](fa-setup.md)  
[Finance](finance.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
