---
title: "How to: Set Up Responsible Employees and Advance Statements"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "responsible employees, setting up"
ms.assetid: 0a16ab2e-cd77-4b70-b192-912d5312f984
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Set Up Responsible Employees and Advance Statements
The **Advance Statement** report enables you to print and view information about payments made to and from responsible employees. This report also enables you to print and view primary documents of responsible employee expenses.  
  
## Creating the Responsible Employee Card  
 The **Resp. Employee Card** window is created for each responsible employee on the basis of the **Employee Card** window, but it can also be created independently.  
  
 It provides the following information:  
  
1.  Responsible Employee card number  
  
2.  Data of the responsible employee \(address, postal code or city, and telephone\)  
  
3.  Contacts \(telephone, e\-mail address, Internet address\)  
  
4.  General ledger entry postings of the responsible employee on the **Posting** tab \(**Gen. Bus. Posting Group**, **VAT Bus. Posting Group**, and **Vendor Posting Group**\)  
  
5.  Documents of the responsible employee \(unposted and posted advance statements\), which can be opened using the **Documents** button.  
  
 The following procedure shows how to access the **Resp. Employee Card** window.  
  
#### To create a Responsible Employee card  
  
1.  In the **Search** box, enter **Resp. Employees**, and then choose the related link.  
  
2.  Create a new card.  
  
3.  Choose the **OK** button.  
  
#### To create a Responsible Employee Card from an Employee card  
  
1.  In the **Search** box, enter **Employees**, and then choose the related link.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Create Resp. Employee**.  
  
3.  The **Resp. Employee Card** window contains the following information entered manually or from the corresponding glossary and settings.  
  
    |FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] --> --> --> --> --> -->|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] --> --> --> -->|  
    |---------------------------------|---------------------------------------|  
    |**No.**|Specifies the value that is filled automatically from the **Employee Card** window, or is entered manually.|  
    |**Name, \($ T\_23\_4 Name2 $\)**|Specifies the value that is filled automatically from similar fields in the **Employee Card** window or is entered manually.|  
    |**Address, \($ T\_23\_6 Address 2 $\)**|Specifies the value that is filled automatically from similar fields in the **Employee Card** window or is entered manually.|  
    |**Post Code**|Specifies the value that is filled automatically from similar fields in the **Employee Card** window or is entered manually.|  
    |**Country\/Region Code**|Specifies the value that is filled automatically from similar fields in the **Employee Card** window or is entered manually.|  
    |**Phone No.**|Specifies the value that is filled automatically from similar fields in the **Employee Card** window or is entered manually.|  
    |**Search Name**|Specifies the value of the **Name** field is entered from the displayed **Resp. Employee Card** window.|  
    |**Communication \(E\-Mail, Home Page\)**|Specifies the values that are filled automatically from similar fields in the **Employee Card** window or is entered manually.|  
    |**Currency Code**|Specifies a blank by default.|  
    |**Gen. Bus. Posting Group**|Specifies the value of the **Adv. Stmt. Gen. Bus. Posting Gr** field from the Purchases and Payables setup on the **Advance Statement** tab.|  
    |**VAT Bus. Posting Group**|Specifies the value of the **Adv. Stmt. VAT Bus. Posting Gr** field from the Purchases and Payables setup on the **Advance Statement** tab.|  
    |**Vendor Posting Group**|Specifies the value of the **Adv. Stmt. Vendor Posting Gr** field from the Purchases and Payables setup on the **Advance Statement** tab.|  
  
## Creating the Advance Statement  
 The **Advance Statement** is created by the responsible employees. This statement contains information about payments received by the employees and about primary documents that are provided to confirm the expenses.  
  
 The **Advance Statement** contains the following information:  
  
-   Advance Statement number  
  
-   Posting date and document date  
  
-   Responsible employee data \(code and name\)  
  
-   Advance purpose and posting description  
  
-   Number of documents and pages  
  
-   Remainder or overdraft document to register the payment document for the advance statement  
  
-   Currency code to register currency expenses  
  
-   Expense lines, which are registered according to the value selected in the **Type in Advance Statement lines** field – **G\/L Account**, **Item**, **Fixed Asset**, **Charge \(Item\)**, and **Employee Purchase** values  
  
 The following expense lines are registered according to the value selected in the **Type** field and **No.** or **Employee Purchase Vendor No.** fields, in the lines of Advance Statement:  
  
-   To write off the expense:  
  
    -   **Type** \- G\/L Account  
  
    -   **No.** \- General ledger account number  
  
-   To account for the purchased items or materials:  
  
    -   **Type** \- Item  
  
    -   **No.** \- Item cardnumber  
  
-   To account for the purchased fixed asset:  
  
    -   **Type** \- Fixed Asset  
  
    -   **No.** \- Fixed Asset card number  
  
-   To account for additional charges for purchased items:  
  
    -   **Type** \- Charge \(Item\)  
  
    -   **No**. \- Item charge code  
  
-   To register the primary documents received from the vendor \(in case primary documents have been received from the vendor for items, fixed assets, or expenses by responsible employee\):  
  
    -   **Type** \- Empl. Purchase  
  
    -   **Employee Purchase Vendor No.** \- Vendor number  
  
#### To access the Advance Statement  
  
1.  In the **Search** box, enter **Advance Statements**, and then choose the related link.  
  
     The **Advance Statement** window contains the following information in the **General** FastTab, in the header, entered manually or filled in from the corresponding glossary and settings.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**No.**|Specifies the number of the advance statement, which is calculated automatically. The number depends on the value of the **Advance Statement Nos.** field that was specified in the **Purchases & Payables Setup** window on the **Advance Statement** FastTab.|  
    |**Posting Date**,<br /><br /> **Document Date**|Specifies the posting date and document date. By default, these fields are filled in with the value from the work date. It can also be filled in manually.|  
    |**Employee No.**|Specifies the number of responsible employee. The value is selected manually from the vendor list.|  
    |**Employee Name**|Specifies the name of responsible employee. This field is filled in automatically with the values of the **Name** and **Name2** fields of the **Resp. Employee Card** window.|  
    |**Advance Purpose**|Specifies the purpose of advance.|  
    |**Posting Description**|Specifies the posting description of the document. This field is filled in automatically with the value from the **Invoice No.** field. The field can be edited manually.|  
    |**Vendor Invoice No.**|Specifies the number of an external document. This field is filled in automatically.|  
    |||  
  
2.  The **Advance Statement** window contains the following information in the **Statement** FastTab in the header, entered manually or filled in from the corresponding glossary and settings.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**No. of Documents**, **No. of Pages**|Specifies the number of documents that confirm expenses and number of pages of these documents. The fields are filled in manually with numeric values.|  
    |**Remaining or Overdraft Doc. No.**|Specifies the cash document that closes the remaining or overdraft amount for this advance statement. A payment document is selected from the vendor ledger entries of the responsible employee.|  
  
     The **Advance statement** window contains the following information from the expense lines that are created.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Type**|Select G\/L Account, Item, Fixed Asset, Charge \(Item\), Empl. Purchase depending on the type of expenses.|  
    |**No.**|If Type \= **G\/L Account**:<br /><br /> In the **No.** field, select a general ledger account from the General Ledger Account List glossary.<br /><br /> If Type \= **Item**:<br /><br /> In the **No.** field, select an Item card from the Item List glossary.<br /><br /> If Type \= **Fixed Asset**:<br /><br /> In the **No.** field, select a Fixed Asset card from the Fixed Asset List glossary.<br /><br /> If Type \= **Charge \(Item\)**:<br /><br /> In the **No.** field, select an item charge from the Item Charges and Fixed Asset Charges glossary.|  
    |**Empl. Purchase Vendor No.**|If Type \= **Empl. Purchase**:<br /><br /> In the **Empl. Purchase Vendor No.** field, select a Vendor card from the Vendor List glossary.|  
    |**Empl. Purchase Entry No**|If Type \= **Empl. Purchase**:<br /><br /> In the **Empl. Purchase Entry No.** field, select a posted vendor entry from the vendor ledger entries. **Note:**  You must post an invoice from the vendor before registering in advance statement, in case a responsible employee receives primary documents \(invoice\-facture for example\) from the vendor.|  
    |**Empl.Purchase Document No,**<br /><br /> **Empl. Purchase Document Date**|The fields are filled in manually. In the **Empl.Purchase Document No**. field, enter the number of the document that confirmed expenses in the current line.<br /><br /> In the **Empl. Purchase Document Date** field, enter the date of the document that confirmed expenses in the current line.|  
    |**Description**|Description of expenses in the current line. The **Description** field is filled in with the value of the **Name** or **Description** field from the selected card by default.|  
    |**Quantity**<br /><br /> **Direct Cost Excl. VAT**|Quantity and cost of expenses \(items and fixed assets\). The fields are filled in with numeric values manually.|  
  
     The **Created Document Status** field reflects the current document status. To change the current document status from **Open** to **Released**.  
  
3.  On the **Home** tab, in the **Process** group, choose **Release**. The released advance statement will be accessible for printing.  
  
## Printing an Unposted Advance Statement  
 The following procedure shows how to print an unposted advance statement.  
  
#### To print an unposted Advance Statement  
  
1.  In the **Search** box, enter **Advance Statements**, and then choose the related link.  
  
2.  In the **Advance Statement** window, on the **Home** tab, in the **Process** group, choose **Print**.  
  
    > [!NOTE]  
    >  The report is usually printed after creating the document for signing and confirmation.  
  
3.  On the **Purchase Header** FastTab, apply the following filters.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|Filter|  
    |---------------------------------|------------|  
    |**No.**|This field contains the unposted advance statement number. By default, a value from the open document is entered.|  
    |**Document Type**|This field is filled in automatically.|  
  
4.  On the **Options** FastTab, specify the employees for signing the document as listed in the following table.  
  
    |Parameter|Description|  
    |---------------|-----------------|  
    |Accountant<br /><br /> \(Cashier\)|Select an employee code \(cashier\) from the Employee List table to fill in the corresponding fields in the statement.|  
    |Accountant|Select an employee code \(accountant\) from the Employee List table to fill in the corresponding fields in the statement.|  
  
5.  Choose the **Print** button.  
  
## Viewing the Posted Advance Statement  
 To following procedure demonstrates how to access the posted **Advance Statement**.  
  
#### To view the posted advance statement  
  
1.  In the **Search** box, enter **Posted Advance Statement**, and then choose the related link.  
  
 A posted **Advance Statement** reflects all the information entered in the document in the Advance statement.  
  
## Printing the Posted Advance Statement  
 The following procedure shows how to print the posted **Advance Statement**.  
  
#### To print a posted advance statement  
  
1.  In the **Search** box, enter **Posted Advance Statements** and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Print**. The **Posted Advance Statement** dialog box opens.  
  
    > [!NOTE]  
    >  The report is usually printed as an approved and confirmed document.  
  
3.  On the **Purch. Inv. Header** tab of the report, apply the following filters.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]Field|Filter|  
    |--------------------------------------|------------|  
    |**No.**|This field contains the number of the posted advance statement. By default, this value is entered from the open document.|  
  
4.  On the **Options** tab, specify the employees to sign the document as listed in the following table.  
  
    |Parameter|Description|  
    |---------------|-----------------|  
    |Accountant \(Cashier\)|Select the employee code \(cashier\) from the Employee List table to fill in the corresponding fields in the report.|  
    |Accountant|Select the employee code \(accountant\) from the Employee List table to fill in the corresponding fields in the report.|  
  
5.  Choose the **Print** button.  
  
## See Also  
 Employee Card   
 Advance Statement   
 Posted Advance Statement