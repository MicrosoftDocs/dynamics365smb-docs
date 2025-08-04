---
title: Set Up and Publish KPI Web Services Based on Financial Reports
description: This article describes how to show the financial-report KPI data based on specific financial reports.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 12/16/2022
ms.custom: bap-template
ms.search.form: 103, 104, 108, 195, 196, 197, 198, 489, 490, 764, 765, 766
---
# Set Up and Publish KPI Web Services Based on Financial Reports

On the **Financial Report KPI Web Service Setup** page, you set up how to show the financial report key performance indicator (KPI) data and which specific financial reports to base the KPIs on. When you choose **Publish Web Service**, the specified financial report KPI data is added to the list of published web services on the **Web Services** page.

> [!NOTE]
> When you use this web service, closing dates are not included in your data set. You can use filters in Power BI to analyze various time periods.

## Set up and publish a KPI web service based on financial reports
  
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Report KPI Web Service Setup**, then choose the related link.
2. On the **General** FastTab, fill in the fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. On the **Row Definitions** FastTab, fill in the fields.
4. Repeat step 3 for all financial reports you want to base the financial report KPI web service on.  
5. To view or edit the selected financial report, on the **Row definitions** FastTab, choose the **Edit Row Definition** action.
6. To view the financial report KPI data you've set up, choose the **Financial Report KPI Web Service** action.
7. To publish the financial report KPI web service, choose the **Publish Web Service** action.

You can now create financial reports in Power BI based on the web service, or services, that you created.

> [!NOTE]  
> You can also publish the KPI web service by pointing to the **Financial Report KPI Web Service Setup** page object from the **Web Services** page. Learn more at [Publish a Web Service](across-how-publish-web-service.md).

## Related information

[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
