---
title: VAT returns in the Czech version
description: Learn how to use the features to submit a VAT return and comply with regulations in the Czech version.
author: v-jiurxo
ms.reviewer: bholtorf
ms.author: v-pejano
ms-service: dynamics-365-business-central
ms.topic: concept-article
ms.search.keywords: Czech, Finance, VAT, VAT Return, Localization, CZ
ms.date: 01/15/2026

---
# VAT returns in the Czech version

The VAT return feature in [!INCLUDE [prod_short](../../includes/prod_short.md)] lets you generate and submit VAT returns to the “Moje daně” portal. The lines on the VAT return are created based on the settings in the VAT statement. [!INCLUDE [prod_short](../../includes/prod_short.md)] verifies whether a regular VAT return was already created for the period. However, because there can be multiple corrective and other returns for a given period, this data isn't checked. This feature allows you to save the VAT return, and you have immediate access to it for future reference.  

On VAT return lines, you must fill in the **Mailbox No.** field. Lines with the same mailbox number are generated into one VAT return line and, according to the parameterization of the VAT attribute code of the transferred VAT return line, the values are filled into the **Basis**, **Amount**, or **Reduced Amount** columns. You can print the generated return as a report.

## To set up VAT reports

1. [!INCLUDE[open-search](../../includes/open-search.md)], enter **VAT Report Setup**, and then choose the related link.
2. Choose **Report Version CZ**.  

![VAT Report Setup](Media/vat-report-setup.png "VAT Report Setup")

### To set up VAT return periods

1. [!INCLUDE[open-search](../../includes/open-search.md)], enter **VAT Return Periods**, and then choose the related link.  
2. On the **VAT Return Periods** page, fill in the fields to set up the first period. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)].  
3. Repeat step 2 for any other periods that you want to add.

![VAT Return Periods](Media/vat-return-period.png "VAT Return Periods")

## To set up VAT Statement 

1. [!INCLUDE[open-search](../../includes/open-search.md)], enter **VAT Statement**, and then choose the related link.
2. Set **Box Nos.** and **Attribute Codes** in the VAT statement lines.
3. You must define a **VAT Return Amount Type** (Base, Amount, Reduced Amount) on the **VAT Attribute Codes** page.

![VAT Statement](Media/vat-statement-line.png "VAT Statement")
![VAT Attribute Code](Media/vat-attribute-code.png "VAT Attribute Code")

## To prepare and submit a VAT report

1. Choose the ![Lightbulb icon to open the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Returns**, and then choose the related link.  
2. Choose **New**, and then fill in the required fields. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
3. Select the VAT report type, either **Standard**, **Corrective**, or **Supplementary**.
4. Select Version - CZ and period.
5. To generate the content of the report, choose the **Suggest Lines** action.  
6. To validate and prepare the report for submission, choose the **Release** action.
7. To create XML, choose the **Generate XML** action.
8. To submit the report, choose the **Submit** action.
9. To mark VAT Return as Submitted, choose the **Mark as Submitted** action.

> [!Note]  
> The **VAT Statement Lines** page is enhanced with drill-down links in the **Base**, **Amount**, and **Reduced Amount** fields. These links let you open a the **VAT Statement Formula Drill-Down** page. The data is filtered according to the attribute code on the given line, indicating whether it is the base, amount, or reduced amount.  

> [!Note]  
> Previously, Czech legislation handled VAT with a functional currency only through the VAT statement. The VAT statement shows the VAT amount in either the local currency or another reporting currency. The VAT return now shows amounts in both the local and extra reporting currencies. It also generates files for submitting the VAT return with the correct amounts according to Czech legislation. This feature is part of the extended option for reporting VAT through VAT returns.  

> [!Note]
> To find the XML, see **Attachments**.

## Related information

[Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
[Czech local functionality](czech-local-functionality.md)  
[VAT Control Report](vat-control-report.md)  
[VAT Date](how-to-setup-vat-date.md)  
[Finance](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
