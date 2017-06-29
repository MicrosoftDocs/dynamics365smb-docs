---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Petty Cash Management
The petty cash management feature enables you to:  
  
-   Create multiple cash account cards.  
  
-   Create ingoing and outgoing cash order documents with the following specifications:  
  
    -   Number them using special numbering rules.  
  
    -   Create printing forms of the documents in the required format.  
  
    -   Post the documents.  
  
-   Void posted cash documents \(checks\).  
  
-   Print the following required forms:  
  
    -   Cash Ingoing Order CO-1  
  
    -   Cash Outgoing Order CO-2  
  
-   Print the following required reports:  
  
    -   Cash Order Journal CO-3  
  
    -   Cash Additional Sheet  
  
    -   Cash Additional Sheet \(Curr.\)  
  
    -   Cash Report CO-4.  
  
    -   Cash Register \(Month\)  
  
## Ingoing Cash Orders  
 To use the ingoing cash order feature, create one general journal template with the Cash Order Payment type. There can be several cash accounts in the company, and several cash points \(for example cashiers\) for each cash account. For each cash account, you must create a cash account with the Cash Account Card feature.  
  
 For each cash point, create a General Journal batch. The value of the **Balance Account Type** field of the batch line should be chosen as Bank Account, and the appropriate cash account should be entered in the **Balance Account Number** field.  
  
 The following procedure shows how to access the Ingoing Cash Order form.  
  
-   In **Financial Management**, click **Cash Management**, and then click **Ingoing Cash Orders**.  
  
 To create a new ingoing cash order, or to work with an existing unposted cash order, choose the correct batch name \(and accordingly the cash point\) in the **Cash** field. This field is required and matches the **Batch Name** field in financial journal forms. The Ingoing Cash Order form contains the fields listed in the following table.  
  
|Field|Description|  
|-----------|-----------------|  
|**Posting Date**|Enter the **Posting Date** field in general journals.|  
|**Document Type**|Enter the **Document Type** field in general journals. The options are:<br /><br /> -   \<blank\><br />-   Payment<br />-   Refund<br /><br /> If the value of the **Account Type** field is Client or Vendor, then the **Document Type** field is not editable, and is automatically filled in depending on the value in the **Account Type** field and the sign of the amount in the **Income** field.|  
|**Prepayment**|In some cases, the financial posting of payments is different in relation to the date of payment, depending on whether if it is before or after the appropriate invoice financial posting. This field should be selected in case of prepayment.|  
|**Document No.**|Enter the **Document Number** field in general journals.<br /><br /> If the value of the **Bank Payment Type** field is Computer Check, then the value of the **Document Number** field is automatically filled in after printing the ingoing cash order. The field is filled in with the next number from the number series that is specified in the **Debit Cash Order Number Series** field in the appropriate cash card. In this case, if you use the Void Check Print function on the card, clear the field.<br /><br /> The document number of the posted ingoing cash order is equal to the document number of the unposted ingoing cash order.|  
|**Account Type**|Enter the **Account Type** field in general journals. This is the type of the object that is the posting source of a cash payment.|  
|**Account Code**|Enter the **Account Code** field in general journals. This is the account code of the object that is the posting source of a cash payment.|  
|**Posting Group**|Enter the **Posting Group** field in general journals. This field is not editable.|  
|**Currency Code**|Enter the **Currency Code** field in general journals.|  
|**Income**|Enter the amount of the payment. Enter the **Credit Amount** field in general journals. If it is positive, then it is an income to the cash account.|  
|**Bank Payment Type**|Enter the **Bank Payment Type** field in general journals. If the value is Computer Check, the order cannot be posted before printing.|  
|**From to**|Enter the **Description** field in general journals. It is used in the printing form of an order as a payment source description.|  
|**Reason**, **Supplement**, **Including**|These fields are transferred to Check Ledger entries during posting and used in printing forms of posted and unposted ingoing cash orders. They can be filled in manually or with the Text Codes functionality.|  
|**Debit Account**|This field indicates the general ledger account that is debited as a result of order posting. It is automatically shown according to the posting group's setup of the account \(or balance account if the Income field contains a negative value\). It is also used in the printing form. This field is not editable.|  
|**Credit Account**|This field indicates the general ledger account that is credited as a result of order posting. It is automatically shown according to the posting group's setup of the balance account \(or account if the **Income** field contains a negative value\). It is used in printing forms. This field is not editable.|  
|**Reason Code**, **Applies-to Doc. Type**, **Applies-to Doc. No**.,<br /><br /> **Global Dimension 1 Code**, **Global Dimension 2 Code**|Enter these fields in general journals.|  
  
## Ingoing Cash Order Form Functions  
 The following functions in the table can be executed from the **Document** button.  
  
|Functions|Description|  
|---------------|-----------------|  
|Check List \(F5 Hot Key\)|Shows the list of ingoing cash orders \(filtered by the current General Journal batch name from the value of the Cash field\).|  
|Dimensions \(Shift-Ctrl-D Hot Key\)|Standard access to Journal Line Dimensions.|  
  
 The following functions in the table can be executed from the **Functions** button.  
  
|Functions|Description|  
|---------------|-----------------|  
|Copy Document|Runs a report that copies information to the current order from any check ledger entry \(posted cash order\). Select the check ledger entry from which to copy and a new posting date.|  
|Void Check Print|This function changes the status of the ingoing cash order from Check Printed to No, and if there is a corresponding record in a check ledger entries table, then it changes the value in the Entry Status field in that record from Printed to Voided.|  
  
 Click **Posting** from the **Posting** button \(Hot Key F11\) to make posting to ledger entries similar to standard posting from payment journals and cash receipt journals.  
  
 Click the **Print** button to run the Cash Ingoing Order CO-1 report, which shows the printing form of the ingoing cash order. Select the **Printing Test** field to run the preview mode.  
  
 The report shows the printing form of the ingoing cash order. To meet requirements, it can also change some database data. If the cash order is not printed, if the **Printing Test** field is not selected, and the **Bank Payment Type** field is set to Computer Check, then the report carries out the following functions:  
  
-   Creates a record in Check Ledger Entries according to the ingoing cash order with the value printed in the **Entry Status** field.  
  
-   If the **Document Number** field is empty, then this field is filled in with the next number from the number series indicated in the appropriate cash account.  
  
-   Changes the status of the ingoing cash order from Check Printed to Yes.  
  
## Posted Cash Debit Order Report  
 To print the ingoing cash order form after it has been posted, you can run a report that prints the same report from Check Ledger Entries using **Print**. The report has no parameters. Before printing, the report ensures that this is really an ingoing cash order, and not an outgoing cash order or bank payment.  
  
## Outgoing Cash Orders  
 To use the outgoing cash order feature, create one general journal template with the Outgoing Cash Order type. The other basic setup of the functionality is the same as that for ingoing cash orders.  
  
 To access the Outgoing Cash Order form  
  
-   In **Financial management**, click **Cash Management**, and then click **Outgoing Cash Orders**.  
  
 To create a new outgoing cash order, or to work with an existing unposted cash order, choose the appropriate batch name \(and accordingly the cash point\) in the **Cash** field. This field is required and matches the **Batch Name** field in financial journal forms. The Outgoing Cash Order form contains the fields listed in the following table.  
  
|Field|Definition|  
|-----------|----------------|  
|**Posting Date**|Enter the **Posting Date** field in general journals.|  
|**Document Type**|Enter the **Document Type** field in general journals. The options are:<br /><br /> -   **Payment**<br />-   **Refund**<br /><br /> If the value of the **Account Type** field is Client or Vendor, then the **Document Type** field is not editable and is automatically filled in depending on the **Account Type** field and the sign of the value in the **Expenses** field.|  
|**Prepayment**|In some cases, the financial posting of payments is different in relation to the date of payment, depending on whether if it is before or after the appropriate invoice financial posting. This field should be selected in case of prepayment.|  
|**Document No.**|Enter the **Document Number** field in general journals. If the value of the **Bank Payment Type** field is Computer Check, then the value of the **Document Number.** field is automatically filled in after printing the outgoing cash order. The field is filled in with the next number from the number series that is specified in the **Credit Cash Order No. Series** field in the appropriate cash card. In this case, if you use the Void Check Print function on the card, the field is cleared.<br /><br /> The document number of a posted outgoing cash order is equal to the document number of the unposted outgoing cash order.|  
|**Account Type**|Enter the **Account Type** field in general journals. This is the type of the object that is the posting source of a cash payment.|  
|**Account Code**|Enter the **Account Code** field in general journals. This is the account code of the object that is the posting source of a cash payment.|  
|**Posting Group**|Enter the **Posting Group** field in general journals. It is automatically filled. This field is not editable.|  
|**Currency Code**|Enter the **Currency Code** field in general journals.|  
|**Expenses**|Enter the amount of the payment. Enter the **Debit Amount** field in general journals. If it is positive, then it is an expense from the cash account.|  
|**Bank Payment Type**|Enter the **Bank Payment Type** field in general journals.|  
|**Given**|Enter the **Description** field in general journals. It is used in the printing form of an order as a payment recipient description.|  
|**Reason**, **Supplement**, **Per**|These fields are transferred to Check Ledger entries during posting and used in printing forms of posted and unposted ingoing cash orders. They can be filled in manually or with the Text Codes.|  
|**Analitic Code**|This field is not editable. This field is equal to the value of the **Account Number** field.|  
|**Debit Account**|This field indicates the general ledger account that is debited as a result of order posting. It is automatically shown according to the posting group's setup of the account \(or balance account if the Income field contains a negative value\). It is also used in the printing form. This field is not editable.|  
|**Credit Account**|This field indicates the general ledger account that is credited as a result of order posting. It is automatically shown according to the posting group's setup of the balance account \(or account if the Income field contains a negative value\). It is used in printing forms. This field is not editable.|  
|**Reason Code**, **Applies-to Doc. Type**, **Applies-to Doc. No.**,<br /><br /> **Global Dimension 1 Code**, **Global Dimension 2 Code**|Enter these fields in general journals.|  
  
 The functions executed from the form are the same as those for the Ingoing Cash Order form.  
  
## Posted Cash Credit Order Report  
 To print an outgoing cash order form after it has been posted; you can run a report that prints the same form from Check Ledger Entries using **Print**. It has no parameters. Before printing, the report ensures that this is really an outgoing cash order, and not an ingoing cash order or bank payment.  
  
## Cash Order Journal CO-3 Report  
 The Cash Order Journal CO-3 shows the register of posted ingoing and outgoing cash orders during some reporting period in the unified standard printing form that is certified by Russian accounting legislation. For more information, see [How to: Print the Cash Order Journal CO-3 Report](../FullExperience/how-to-print-the-cash-order-journal-co-3-report.md).  
  
## Cash Additional Sheet Reports  
 The Cash Additional Sheet and Cash Additional Sheet \(Curr.\) reports show the unified standard printing forms for the cash booking register for one operational day of the cash account. These reports are usually printed every day, and their numbering continues according to the value of the **Last Cash Report Page No.** field in the corresponding cash account card. The reports increase that number by one and use this number as a page number of the report \(but only if the report parameter Repeat Printing is not selected\). They can only be printed per day.  
  
 They both show the opening balance of all the posted ingoing and outgoing cash orders, and the closing balance of an operational day for one cash account. The difference between them is that the Cash Additional Sheet \(Curr.\) report is for cash accounts in a currency other than the local currency.  
  
 To access the reports  
  
-   In **Financial Management**, click **Cash Management**, click **Reports**, and then click Ieither **Cash Additional Sheet** or Cash **Additional Sheet \(Curr.\).**  
  
 The parameters of the reports are listed in the following table.  
  
|Parameter|Description|  
|---------------|-----------------|  
|Bank Account|Enter the codes of the cash accounts that the cash additional pages are printed for \(one page for one cash account\).|  
|Date|Enter the operation date of the cash account for printing in the report.|  
|Repeat printing|Select this field to ensure that the printing process does not increase the value of the **Last Cash Report Page No.** field in the corresponding cash account card and that the report is printed with this number \(indicated in the cash account card\). This serves repeated printing.|  
  
## Cash Report CO-4  
 The **\($ R\_14902 Cash Report CO-4 $\)** report shows mandatory daily cash transactions in standard format as required by Russian accounting legislation. For more information, see[How to: Print the Cash Report CO-4 Report](../FullExperience/how-to-print-the-cash-report-co-4-report.md).  
  
## See Also  
 [Bank Management](../FullExperience/bank-management.md)   
 [How to: Create Cash Account Cards](../FullExperience/how-to-create-cash-account-cards.md)   
 [How to: Print the Cash Order Journal CO-3 Report](../FullExperience/how-to-print-the-cash-order-journal-co-3-report.md)   
 [How to: Print the Cash Report CO-4 Report](../FullExperience/how-to-print-the-cash-report-co-4-report.md)   
 [How to: Print the Ingoing Cash Order Report](../FullExperience/how-to-print-the-ingoing-cash-order-report.md)   
 [How to: Print the Cash Register \(Month\) Report](assetId:///10a26052-053a-408e-9015-9ef26ebb2b8d)   
 [How to: Print the Outgoing Cash Order Report](../FullExperience/how-to-print-the-outgoing-cash-order-report.md)   
 Cash Report CO-4   
 Cash Order Journal CO-3