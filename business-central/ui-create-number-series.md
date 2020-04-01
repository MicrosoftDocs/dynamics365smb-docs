---
title: 'Create Number Series | Microsoft Docs'
description: Learn how to set up number series that assign unique ID codes to accounts and documents in Business Central .
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: numbers, numbering
ms.date: 04/01/2020
ms.author: sgroespe

---
# Create Number Series
For each company that you set up, you need to assign unique identification codes to things such as general ledger accounts, customer and vendor accounts, invoices, and other documents. Numbering is important not only for identification. A well-designed numbering system also makes the company more manageable and easy to analyze, and can reduce the number of errors that occur in data entry.

> [!Important]
> By default, gaps are not allowed in number series because the exact history of financial transactions must be available for auditing, by law, and therefore must follow an unbroken sequence with no deleted numbers.<br /><br />
If you want to allow gaps in certain number series, then first consult with your auditor or accounting manager to ensure that you adhere to the legal requirements in your country/region. For more information, see [Gaps in Number Series](ui-create-number-series.md#gaps-in-number-series).

> [!NOTE]  
>   We recommend that you use the same number series codes as you see listed on the **No. Series List** page in the CRONUS demonstration company. Codes such as *P-INV+* might not make immediate sense to you, but [!INCLUDE[d365fin](includes/d365fin_md.md)] has a number of default settings that depend on these number series codes.

You create a numbering system by setting up one or more codes for each type of master data or document. For example, you can set up one code for numbering customers, another code for numbering sales invoices, and another code for numbering documents in general journals. After you have set up a code, you must set up at least one number series line. The number series line contains information such as the first and last number in the series and the starting date. You can set up more than one number series line per number series code, with a different starting date for each line. The series will be used consecutively, starting each series on the respective starting date.

You typically set up your number series to automatically insert the next consecutive number on new cards or documents that you create. However, you can also set a number series up to allow that you manually enter the new number. You specify this with the **Manual Nos.** check box.

If you want to use more than one number series code for one type of master data - for example, if you want to use different number series for different categories of items - you can use number series relationships.

## Gaps in Number Series
Not all records that you create in [!INCLUDE[d365fin](includes/d365fin_md.md)] are financial transactions that must use sequential numbering. Customer cards, sales quotes, and warehouse activities are examples of records that are assigned a number from a number series, but are not subject to financial auditing and/or can be deleted. For such number series, you can select the **Allow Gaps in Nos.** check box on the **No. Series Lines** page. This setting can also be changed after creating the number series. For more information, see [To create a new number series](ui-create-number-series.md#to-create-a-new-number-series).

## Behavior of the No. field on Documents and Cards
On sales, purchase, and transfer documents and on all cards, the **No.** can be filled in automatically from a number series or manually, and it can be set up to be invisible.

The **No.** field can be filled in three ways:

1. If only one number series for the type of document or card exists where the **Default Nos.** check box is selected and the **Manual Nos.** check box is not selected, then the field is automatically filled with the next number in the series, and the **No.** field will not be visible.

    > [!NOTE]  
    > If the number series does not function, for example because it has run out of numbers, then the **No.** field will be visible and you can manually enter a number or resolve the issues on the **No. Series** page.

2. If more than one number series for the type of document or card exist, and the **Default Nos.** check box is not selected for the number series that is currently assigned, then the **No.** field is visible, and you can look up to the **No. Series** page and select the number series you want to use. The next number in the series is then inserted in the **No.** field.

3. If you have not set up a number series for the type of document or card, or if the **Manual Nos.** field is selected for the number series, then the **No.** field is visible and you must enter any number manually. You can enter a maximum of 20 characters, both numbers and letters.

When you open a new document or card that a number series exists for, then the relevant **No. Series Setup** page opens so that you can set up a number series for that type of document or card before you proceed with other data entry.

> [!NOTE]  
> If you need to enable manual numbering on, for example, new item cards that have been created with a data migration process that has hidden the **No.** by default, then go to the **Inventory Setup** page and choose the **Item Nos.** field to open and set the related number series to **Manual Nos.**.

## To create a new number series
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **No. Series**, and then choose the related link.
2. Choose the **New** action.
3. On the new line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Choose the **Lines** action.
5. On the **No. Series Lines** page, fill in the fields to define the actual use and content of the number series that you created in step 2.
6. Repeat step 5 for as many different uses of the number series that you need. The **Starting Date** field defines which number series line is active.

## To set up where a number series is used
The following procedure shows how to set number series up for the Sales area. The steps are similar for other areas.
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables**, and then choose the related link.
2. On the **Sales & Receivables** page, on the **Number Series** FastTab, select the desired number series for each sales card or document.

The selected number will now be used to fill in the **No.** field on the card or document in question, according to the settings you made on the number series line.

## To create relationships between number series
If you have set up more than one number series code for the same kind of basic information or transactions, you can create relationships between the codes. This feature can assist you in deciding among the codes when you use a number.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **No. Series**, and then choose the related link.
2. Select the line with the number series you want to create relationships for and then choose **Relationships**.
3. In the **Series Code** field, enter the code for the number series that you want to relate to the series you selected in step 2.
4. Add a line for each code that you want to relate to the selected number series.
5. Close the page.

Now when you set up something that requires a number, you can use the relationships you created to select among the related number series.

## See Related Training at [Microsoft Learn](/learn/modules/number-series-trail-codes-dynamics-365-business-central/index)

## See Also
[Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
