---
title: How to Set Up VAT Reports [DE]
description: Learn how to set up report parameters in Business Central to file a VAT report under the ELMA5 system.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: report parameters, ELMA5 system, VAT report setup, German version
ms.date: 03/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up VAT reports in the German version

Information from various invoice types is used to feed data into the EU Sales List report. To file a VAT report under the ELMA5 system from [!INCLUDE[prod_short](../../includes/prod_short.md)], you need to set up report parameters.  

## Set up a VAT report  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Report Setup**, and then choose the related link.  
1. On the **General** FastTab, select the **Modify Submitted Reports** checkbox to let users modify VAT reports that are submitted to the tax authorities.  

   If the field is left blank, users must create a corrective VAT report instead.  

1. Select the **Export Cancellation Lines** checkbox if you want to include information about cancellation lines when you export data for the VAT report of EU sales. Learn more in [Correct VAT Reports](how-to-correct-vat-reports.md).  
1. On the **Numbering** FastTab, specify the number series to be used for standard VAT reports. This will be the default numbering series that is used on any VAT Report that you then create.  

   Depending on the requirements, you can use the same number series for all VAT reports, or separate number series for each type of VAT report.

   For example, if your company uses separate number series for standard and corrective VAT reports, this number series is the default number series. Users can select a different number series in the **No.** field when they create corrective reports.  

1. On the **ZIVIT** FastTab, specify information for the fields.  
1. Choose the **OK** button.  

## Related information

- [VAT Reporting](vat-reporting.md)
- [Create VAT Reports](how-to-create-vat-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
