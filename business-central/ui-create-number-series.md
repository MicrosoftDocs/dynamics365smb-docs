---
title: Create Number Series
description: Learn how to set up number series that assign unique ID codes to accounts and documents in Business Central.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: numbers, numbering
ms.search.form: 456, 457, 458, 459, 460, 461, 21, 22, 26, 27, 31
ms.date: 03/24/2022
ms.author: bholtorf

---
# Create Number Series

For each company that you set up, you need to assign unique identification codes to things such as general ledger accounts, customer and vendor accounts, invoices, and other documents. Numbering is important not only for identification. A well-designed numbering system also makes the company more manageable and easy to analyze, and can reduce the number of errors that occur in data entry.

> [!Important]
> By default, gaps are not allowed in number series because the exact history of financial transactions must be available for auditing, by law, and therefore must follow an unbroken sequence with no deleted numbers.
> 
> If you want to allow gaps in certain number series, then first consult with your auditor or accounting manager to ensure that you adhere to the legal requirements in your country/region. For more information, see the [Gaps in Number Series](#gaps-in-number-series) section.

> [!NOTE]  
> We recommend that you use the same number series codes as you see listed on the **No. Series List** page in the CRONUS demonstration company. Codes such as *P-INV+* might not make immediate sense to you, but [!INCLUDE[prod_short](includes/prod_short.md)] has a number of default settings that depend on these number series codes.

You create a numbering system by setting up one or more codes for each type of master data or document. For example, you can set up one code for numbering customers, another code for numbering sales invoices, and another code for numbering documents in general journals. After you have set up a code, you must set up at least one number series line. The number series line contains information such as the first and last number in the series and the starting date. You can set up more than one number series line per number series code, with a different starting date for each line. The series will be used consecutively, starting each series on the respective starting date.

> [!NOTE]
> The maximum length of a number in a number series is 20 characters. There are some situations where [!INCLUDE[prod_short](includes/prod_short.md)] will append a number with a system-generated ID. For example, when documents such as invoices are used to apply transactions, such as payments, [!INCLUDE[prod_short](includes/prod_short.md)] generates identifiers for the applied transactions. The identifier is comprised of a number from a number series and a six character system-assigned ID, such as -12345. If you expect to process more than 9999 documents in bank or GIRO journals, or cash receipt journals, set up number series for those types of documents to include fewer than 14 characters.

You typically set up your number series to automatically insert the next consecutive number on new cards or documents that you create. However, you can also set a number series up to allow that you manually enter the new number. You specify this with the **Manual Nos.** check box.

If you want to use more than one number series code for one type of master data - for example, if you want to use different number series for different categories of items - you can use number series relationships.

## Gaps in Number Series
Not all records that you create in [!INCLUDE[prod_short](includes/prod_short.md)] are financial transactions that must use sequential numbering. Customer cards, sales quotes, and warehouse activities are examples of records that are assigned a number from a number series, but are not subject to financial auditing and/or can be deleted. For such number series, you can select the **Allow Gaps in Nos.** check box on the **No. Series Lines** page. This setting can also be changed after creating the number series. For more information, see [To create a new number series](ui-create-number-series.md#to-create-a-new-number-series).

## Behavior of the No. field on documents and cards

On sales, purchase, and transfer documents and on all cards, the **No.** field can be filled in automatically from a predefined number series, or you can add it manually. However, under certain circumstances, the **No.** field is invisible to prevent you from editing it.  

The **No.** field can be filled in three ways:

1. If only one number series for the type of document or card exists, and the **Default Nos.** field is selected and the **Manual Nos.** field is not selected for that number series, then the field is automatically filled with the next number in the series. The **No.** field will not be visible on the card or document.  

    Even if you define templates with various number series for customers, if the number series that is defined in the **Sales & Receivables Setup** page is set up in this way, the **No.** field will be invisible on the customer card, no matter which template you use. The same applies to other types of cards and documents.  

    > [!NOTE]  
    > If the number series does not function, for example because it has run out of numbers, then the **No.** field will be visible and you can manually enter a number or resolve the issues on the **No. Series** page.

2. If more than one number series for the type of document or card exist, and the **Default Nos.** check box is not selected for the number series that is currently assigned, then the **No.** field is visible, and you can look up to the **No. Series** page and select the number series you want to use. The next number in the series is then inserted in the **No.** field.

3. If you have not set up a number series for the type of document or card, or if the **Manual Nos.** field is selected for the number series, then the **No.** field is visible and you must enter any number manually. You can enter a maximum of 20 characters, both numbers and letters.

When you open a new document or card that a number series exists for, then the relevant **No. Series Setup** page opens so that you can set up a number series for that type of document or card before you proceed with other data entry.

> [!NOTE]  
> If you need to enable manual numbering on, for example, new item cards that have been created with a data migration process that has hidden the **No.** by default, then go to the **Inventory Setup** page and choose the **Item Nos.** field to open and set the related number series to **Manual Nos.**.

## To create a new number series

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **No. Series**, and then choose the related link.
2. Choose the **New** action.  
3. On the new line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
4. Choose the **Lines** action.  
5. On the **No. Series Lines** page, fill in the fields to define the actual use and content of the number series that you created in step 2.  
6. Repeat step 5 for as many different uses of the number series that you need. The **Starting Date** field defines which number series line is active.  

> [!TIP]
> To allow users to specify numbers manually when they register a new customer or vendor, for example, choose the **Manual Nos.** field on the number series itself. To disallow manual number, clear the field.

You can assign number series to the templates that you set up for the different types of customers and vendors that your sales people and purchasers most often add to your [!INCLUDE [prod_short](includes/prod_short.md)]. In that case, set up the relevant number series, link them through relationships, and then add the first number series in the relevant relationship to the relevant setup page. Then, when a user creates a customer, they choose the relevant template, and the new customer gets a number assigned from the number series that is defined for that template.  

## To create relationships between number series

If you have set up more than one number series code for the same kind of basic information or transactions, you can create relationships between the codes. This feature can assist you in deciding among the codes when you use a number. When you set up a relationship between a group of number series, you associate all of the related series to one number series code. Then you can enter that code in a field on the **Numbering** FastTab in one of the relevant setup page, such as **Sales & Receivables Setup**.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **No. Series**, and then choose the related link.
2. Select the line with the number series you want to create relationships for and then choose **Relationships**.
3. In the **Series Code** field, enter the code for the number series that you want to relate to the series you selected in step 2.
4. Add a line for each code that you want to relate to the selected number series.
5. Close the page.

Now when you set up something that requires a number, you can use the relationships you created to select among the related number series.

## To set up where a number series is used

The following procedure shows how to set number series up for the Sales area. The steps are similar for other areas.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables**, and then choose the related link.
2. On the **Sales & Receivables** page, on the **Number Series** FastTab, select the desired number series for each sales card or document.

The selected number will now be used to fill in the **No.** field on the card or document in question, according to the settings you made on the number series line.  

## See also

[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
