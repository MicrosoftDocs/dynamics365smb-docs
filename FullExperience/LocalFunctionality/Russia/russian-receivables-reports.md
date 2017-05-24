---
title: "Russian Receivables Reports"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "receivables"
  - "official reports in Russia, receivables"
  - "receivables, reports"
  - "reports, receivables"
ms.assetid: ff85a97b-c503-4803-8d19-bd8561e54977
caps.latest.revision: 3
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# Russian Receivables Reports
The receivables report feature enables you to view the customer general ledger turnover for finance entries of general ledger accounts with the source type Customer. The following reports are also provided:  
  
-   Customer General Ledger Turnover \(report 12450\)  
  
-   Customer Accounting Card \(report 12441\)  
  
-   Customer Turnover \(report 12439\)  
  
-   Customer Posting Group Turnover \(report 12440\)  
  
-   Customer Entries Analysis \(report 12442\)  
  
-   Customer Reconciliation Act \(report 14910\)  
  
## Customer General Ledger Turnover Report \(Report 12450\)  
 The Customer General Ledger Turnover report is used to analyze the turnover and to analyze customer account balances. It is usually printed monthly, but it can be printed for any given period.  
  
 The **Customer** tab of the request form contains fields with the information listed in the following table.  
  
|Field|Definition|  
|-----------|----------------|  
|**No.**|Select this field to define the customer number or a number range, depending on whether you want to print a Customer General Ledger Turnover report for one customer or for a group of customers.|  
|**Customer Posting Group**|Select this field to specify one customer posting group or a range of groups, according to the filtering rules that you set.|  
|**Global Dimension 1 Filter**|Select this field to define a filter value for data analysis on Global Dimension 1.|  
|**Global Dimension 2 Filter**|Select this field to define a filter value for data analysis on Global Dimension 2.|  
|**Date Filter**|Select this field to specify the period that the report is to be printed for.|  
  
 The **Options** tab contains the fields listed in the following table.  
  
|Field|Description|  
|-----------|-----------------|  
|**Rounding Precision**|Select this field to choose the required rounding precision: 0.001, 0.01, 1, or 1000.|  
|**Replace zero values by blanks**|Select this field to replace zero values with blanks during printing.|  
|**Skip accounts without net changes**|Select this field to exclude lines without net changes within the period.|  
|**Skip accounts with zero ending balance**|Select this field to exclude lines with zero ending balances at the end of the period.|  
|**Skip zero lines**|Select this field to exclude lines with zero values.|  
|**Print horizontal grid**|Select this field to print the horizontal grid.|  
  
## Customer Accounting Card Report \(Report 12441\)  
 The Customer Accounting Card report provides the following information for all of a customer's entries for a specific period:  
  
-   Starting balance  
  
-   Posting date  
  
-   Document number  
  
-   Description  
  
-   Net change debit  
  
-   Net change credit  
  
-   Document type  
  
-   Ending balance  
  
 It is printed monthly and on the date of inventory, but can be printed for any given period.  
  
 The following procedure shows how to access the Customer Accounting Card report.  
  
1.  In **Financial Management**, choose **Receivables**, and then choose **Turnover**.  
  
2.  Choose **Customer G\/L Turnover**, choose **Print**, and then choose **Customer Accounting Card**.  
  
 The **Customer** tab of the request form contains the same fields as the **Customer** tab of the Customer General Ledger Turnover report. On the **Options** tab, you can select the **New page per Customer** field to print the information for each customer on a separate sheet.  
  
## Customer Turnover Report \(Report 12439\)  
 The Customer Turnover report is used to print the data about a customer's entries for a specific period. It can also be created for customers separately for agreements. The printed data contains the following information:  
  
-   Number  
  
-   Name  
  
-   Starting balance \(debit or credit at beginning of the period\)  
  
-   Net change \(debit or credit\)  
  
-   Ending balance \(debit or credit at end of the period\)  
  
 To access the Customer Turnover report  
  
-   In **Financial Management**, choose **Receivables**, choose **Reports**, and then choose **Customer Turnover**.  
  
 The **Customer** tab of the request form contains the same fields as the **Customer** tab of the Customer General Ledger Turnover report. On the **Options** tab, specify the same format options as the **Options** tab of the Customer General Ledger Turnover report. It also contains the Print by Agreements option, if it is selected, all amounts in reports will be calculated and shown in the section of agreements.  
  
## Customer Posting Group Turnover Report \(Report 12440\)  
 The Customer Posting Group Turnover report is used to print information on the customer's entries that are accumulated in the customer posting groups. The printed data contains the following information:  
  
-   Customer posting group code  
  
-   Customer posting group name  
  
-   Starting balance \(debit or credit\)  
  
-   Net change \(debit or credit\)  
  
-   Ending balance \(debit or credit\)  
  
 To access the Customer Posting Group Turnover report  
  
-   In **Financial Management**, choose **Receivables**, choose **Reports**, and then choose **Customer Posting Group Turnover**.  
  
 On the **Customer Posting Group** tab of the request form, specify the customer posting group code or a range of customer posting group codes, depending on whether you want to print the report for one customer posting group or for a range of customer posting groups.  
  
 The **Customer** tab contains the fields listed in the following table.  
  
|Field|Description|  
|-----------|-----------------|  
|**Global Dimension 1 Filter**|Enter a filter value for analysis on Global Dimension 1.|  
|**Global Dimension 2 Filter**|Enter a filter value for analysis on Global Dimension 2.|  
|**Date Filter**|Enter the period that the report is to be printed for. The field is required.|  
  
 On the **Options** tab, you can specify the same format options as on the **Options** tab of the Customer General Ledger Turnover report.  
  
## Customer Entries Analysis \(Report 12442\)  
 The Customer Entries Analysis report shows the customer's liabilities at the beginning and at the end of the period, entry analysis, and invoice discharging. The printed data contains the following information  
  
-   Posting date  
  
-   Document number  
  
-   Document name  
  
-   Type \(payment, invoice\)  
  
-   Amount  
  
-   Amount closed  
  
-   Payment date  
  
 This report shows all the entries of the customer for a certain period. The analysis of the report enables you to determine the invoice and payment interdependence, shows closed entries, due invoices, partially discharged invoices, and customer prepayment amounts.  
  
 To access the Customer Entries Analysis report  
  
-   In **Financial Management**, choose **Receivables**, choose **Reports**, and then choose **Customer Entries Analysis**.  
  
 On the **Customer** tab of the request form, define the customer number or a range of numbers, depending on whether you want to print the report for one customer or for a range of customers. On the **Customer Ledger Entry** tab, you can enter a filter value for one document or for a range of documents.  
  
 On the **Options** tab, you can specify the format options listed in the following table.  
  
|Parameter|Description|  
|---------------|-----------------|  
|**Starting Date**|Enter the start date of the period.|  
|**Ending of period**|Enter the end date of the period|  
|**Report Currency**|Enter currency that you want to use in the report. You can choose:<br /><br /> -   Local currency<br />-   Transaction currency|  
|**New Page For Customer**|Select this field to print the data for each customer on a separate page.|  
  
## Customer \- Reconciliation Act \(Report 14910\)  
 The Customer – Reconciliation Act report shows the payments or liabilities of the customer. It is used for the reconciliation of mutual payments of contractors.  
  
 To access the Customer – Reconciliation Act report  
  
-   In **Financial Management**, choose **Receivables**, choose **Reports**, and then choose **Customer \- Reconciliation Act**.  
  
 The following levels of detail are possible:  
  
-   Full  
  
-   Partial  
  
-   None  
  
### Full Detail  
 If Full is selected as the detail level, the report prints the following data for each document for the current and previous periods:  
  
-   Document number and numbers of documents connected with it  
  
-   The balance on each document \(debit or credit\)  
  
-   Document date  
  
-   Description  
  
 The report prints the following information on the right side of the form \(customer's data\) in case **Print Contactor Data** is selected on the **Options** tab of the request form:  
  
-   Document amount  
  
-   Debit  
  
-   Credit  
  
### Partial Detail  
 If Partial Detail is selected as the detail level, the report shows the balance on each document for the current and previous periods, but no connections to the invoices, credit notes, and payments.  
  
### None  
 If None is selected as the detail level, the report shows, for each customer, the balance at the beginning of the period, net changes for the period, and the balance at the end of the period. It also shows the amount of the customer liabilities.  
  
### Selecting Print Contractor Data  
 When the **Print Contractor Data** field is selected, the right side of the report is filled in based on data supplied by the customer. Otherwise, the Customer Reconciliation Act report is printed with the right side not filled in. To reconcile the mutual payments of contractors, you can print Customer – Reconciliation Act forms with the left side filled in with your data. These forms are supplied to the customers. The customers fill in their data on the right side. Then the company's data is compared with the customer's data, and if it is the same, the **Print Contractor Data** field can be selected. A final Customer – Reconciliation Act document is printed, which is signed by general managers or other persons in charge of both parties.  
  
 On the **Customer** tab of the request form, define the customer number or a range of numbers, depending on whether you want to print a report for one customer or for a number of customers.  
  
 On the **Options** tab, you can specify the format options listed in the following table.  
  
|Parameter|Description|  
|---------------|-----------------|  
|**Starting Date**|Enter the start date of the period.|  
|**Ending Date of the Period**|Enter the end date of the period.|  
|**Report Currency**|Enter the currency that you want to use in the report. You can choose any currency from the glossary of currencies.|  
|**Detailed**|Select one of these values:<br /><br /> -   **Full**<br />-   **Partial**<br />-   **None**|  
|**Print Contractor Data**|Select this option to fill in the, the right side of the report with the customer's data.|  
  
## See Also  
 [Russian Payables Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/russian-payables-reports.md)   
 [How to: Set Up Customer and Vendor Agreements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-customer-and-vendor-agreements.md)   
 [Payables and Receivables\-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/payables-and-receivables-duplicate.md)