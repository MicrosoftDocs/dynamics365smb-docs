---
title: Maintain fixed assets
description: Track and document repairs and maintenance for fixed assets to maintain their condition and value.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.search.keywords: repair, service, fixed assets, manage fixed assets, maintenance cost
ms.search.form: 5642, 5625
ms.date: 08/08/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Maintain fixed assets

Maintenance costs are operating expenses for the things you do to preserve the condition of your fixed assets. Unlike capital improvements, maintenance doesn't increase the value of your assets.

Each time you send a fixed asset for service, you record information such as the service date, the vendor who did the work, and the service agent's phone number. You enter maintenance information on several pages:

* Fixed Asset Card
* Purchase Order
* Purchase Invoice
* Fixed Asset G/L Journal

Indexation is used to adjust values for general price-level changes. Use the **Index Fixed Assets** action to recalculate maintenance costs.

## Record a maintenance cost directly on a fixed asset

Every time you do maintenance for an asset, such as a service visit, you can record it on the **Maintenance Registrations** page.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Assets**, and then choose the related link.  
2. Select the fixed asset that you want to record maintenance for, and then choose the **Maintenance Registration** action.
3. On the **Maintenance Registration** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## Post maintenance costs from a fixed asset G/L journal

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Depreciation Book List**, and then choose the related link.  
2. Select the depreciation book that is assigned to the fixed asset, and then choose the **Edit** action.
3. On the **Depreciation Book Card** page, make sure the **Maintenance** checkbox isn't selected so that you don't post maintenance costs to the general ledger.
4. [!INCLUDE[open-search](includes/open-search.md)], enter **FA G/L Journals**, and then choose the related link.  
5. Create an initial journal line and fill in the fields as necessary.
6. In the **FA Posting Type** field, select **Maintenance**.
7. Choose the **Insert FA Bal. Account** action. A second journal line is created for the balancing account that is set up for maintenance posting.

   > [!NOTE]  
   > Step 7 only works if you set up the following: On the **FA Posting Group Card** page for the posting group of the fixed asset, the **Maintenance Account** field contains the general ledger debit account and the **Maintenance Bal. Account** field contains the general ledger account to which you want to post balancing entries for appreciation. Learn more in [Set up fixed asset posting groups](fa-how-setup-general.md#set-up-fixed-asset-posting-groups).
8. Choose the **Post** action.

## Record maintenance cost from a purchase invoice

The following steps describe how to record maintenance costs for a fixed asset from a purchase invoice. The steps are similar for purchase orders.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Invoice**, and then choose the related link.
2. On the **General** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. On the **Lines** FastTab, in the **Type** field, choose **Fixed Asset**.
4. In the **No.** field, choose the asset, and then specify the quantity and cost.
5. In the **FA Posting Type** field, choose **Maintenance**.
6. Post the purchase invoice.

## Follow up on service visits

You can print the **Maintenance - Next Service** report to list the assets that are scheduled for service. You can also use this report when you want to update the **Next Service Date** field on fixed asset cards.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Maintenance Next Service**, and then choose the related link.  
2. Fill in the **Starting Date** and **Ending Date** fields.  
3. Choose the **Print** or **Preview** button.

## Monitor maintenance costs

[!INCLUDE[prod_short](includes/prod_short.md)] provides dedicated reports and statistics pages for use in analyzing fixed assets maintenance.  

Learn more in [Fixed assets maintenance reports](fa-reports.md#fixed-assets-maintenance-reports) for information about the built-in reports for fixed asset maintenance.

### Overview of maintenance costs

You can view statistics to monitor maintenance costs.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Assets**, and then choose the related link.
2. Select the fixed asset you want to view maintenance costs for, and then choose the **Depreciation Books** action.
3. On the **FA Depreciation Books** page, select the relevant fixed asset depreciation book, and then choose the **Statistics** action.
4. On the **Fixed Asset Statistics** page, choose the **Maintenance** field.

Use the **Maintenance Ledger Entries** page to view the entries that make up the amount in the **Maintenance** field.

### View or print maintenance costs for multiple fixed assets

In the **Maintenance - Analysis** report, you can select to examine maintenance based on one, two, or three maintenance codes for a specific date or period. The report can show the total for all selected assets, or a total for each asset.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Maintenance Analysis**, and then choose the related link.
2. Fill in the fields as necessary.
3. Choose the **Print** or **Preview** button.

Learn more in [Maintenance - Analysis](reports/report-5630.md).

## View maintenance ledger entries

You can also explore maintenance costs by viewing the maintenance ledger entries.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Assets**, and then choose the related link.
2. Select the fixed asset that you want to view ledger entries for, and then choose the **Depreciation Books** action.
3. On the **FA Depreciation Books** page, select the relevant fixed asset depreciation book, and then choose the **Maintenance Ledger Entries** action.

## View or print maintenance ledger entries for multiple fixed assets

In the **Maintenance - Details** report, you can view or print maintenance ledger entries for one or many fixed assets.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Maintenance Details**, and then choose the related link.
2. Fill in the fields as necessary.
3. Choose the **Print** or **Preview** button.

## Related information

- [Maintenance - Analysis](reports/report-5630.md)  
- [Fixed assets maintenance reports](fa-reports.md#fixed-assets-maintenance-reports)  
- [Fixed Assets](fa-manage.md)  
- [Setting Up Fixed Assets](fa-setup.md)  
- [Finance](finance.md)  
- [Getting Ready for Doing Business](ui-get-ready-business.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
