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
# Russian Payables Reports
The payables report feature enables you to view the vendor general ledger turnover for general ledger accounts for finance entries with the source type Vendor on the screen and in the form of a printed report. The following reports are also provided:  
  
-   Vendor General Ledger Turnover \(form 12407\)  
  
-   Vendor General Ledger Turnover \(report 12451\)  
  
-   Vendor Accounting Card \(report 12445\)  
  
-   Vendor Turnover \(report 12444\)  
  
-   Vendor Posting Group Turnover \(report 12443\)  
  
-   Vendor Entries Analysis \(report 12446\)  
  
-   Vendor Reconciliation Act \(report 14911\)  
  
## Vendor General Ledger Turnover \(Form 12407\)  
 The Vendor General Ledger Turnover form is an electronic form that shows the vendor turnover for general ledger accounts in the context of vendors.  
  
 To access this form, in **Financial Management**, choose **Payables**, and then choose **Turnover**. This form contains all the information about a vendor's entries such as the general ledger entries with the source type Vendor with the amounts in local currency \(LCY\).  
  
 The **Options** tab contains the fields listed in the following table.  
  
|Field|Description|  
|-----------|-----------------|  
|**Date Filter**|Select this field to specify the period that the data is analyzed for. You can use the buttons on the lower\-left corner of the form, or you can enter the dates manually.|  
|**General Ledger Account Filter**|Select this field to filter the data by general ledger accounts.|  
|**Global Dimension 1 Filter**|Select this field to define a value for the Global Dimension 1 filter.|  
|**Global Dimension 2 Filter**|Select this field to define a value for the Global Dimension 2 filter.|  
  
 The lines of the form contain the information listed in the following table.  
  
|Column|Description|  
|------------|-----------------|  
|No.|Select this column to enter the vendor number. This column is not editable.|  
|Name|Select this column to enter the vendor name. This column is not editable.|  
|Vendor Posting Group|Select this column to enter the vendor posting group. This column is not editable.|  
|Starting Balance LCY,<br /><br /> Debit Amount \(LCY\),<br /><br /> Credit Amount \(LCY\),<br /><br /> Ending Balance LCY,<br /><br /> Net Change \(LCY\).|Select this column to enter the balance at the beginning and the end of the period, debit amount, credit amount, and net change for the period. All amounts are shown in the local currency.<br /><br /> The values of these columns are calculated for all the general ledger entries with the source type Vendor.<br /><br /> These columns are not editable.|  
  
 The following procedure shows how to access the form with the option for the **Vendor** button.  
  
-   In the **Vendor** button, choose **Vendor G\/L Turnover**, and then choose **Card** \(SHIFT\+F5 Hot Key\) to view the vendor card for the selected line.  
  
 The following procedure shows how to access the form that has the **Print** button with the following reports:  
  
1.  Choose **Vendor G\/L Turnover**, and then choose **G\/L Turnover** to access the Vendor G\/L Turnover report.  
  
2.  Choose **Vendor G\/L Turnover**, and then choose **Accounting Period** to access the Vendor Accounting Card report.  
  
## Vendor General Ledger Turnover Report \(Report 12451\)  
 The Vendor General Ledger Turnover report is used to analyze turnover as well as for analysis of the vendor account balances. It is usually printed monthly, but can be printed for any given period.  
  
 The following procedure shows how to access the Vendor General Ledger Turnover report.  
  
1.  In **Financial Management**, choose **Payables**, and then choose **Turnover**.  
  
2.  Choose **Vendor G\/L Turnover**, choose **Print**, and then choose **G\/L Turnover**.  
  
 The **Vendor** tab of the request form contains the fields listed in the following table.  
  
|Field|Description|  
|-----------|-----------------|  
|**No.**|Select this field to define the vendor number or a number range, depending on whether you want to print a Vendor General Ledger Turnover report of one vendor or of a group of vendors.|  
|**Vendor Posting Group**|Select this field to specify one vendor posting group or a range of groups, according to the filtering rules that you set.|  
|**Global Dimension 1 Filter**|Select this field to define a filter value for data analysis on Global Dimension 1.|  
|**Global Dimension 2 Filter**|Select this field to define a filter value for data analysis on Global Dimension 2.|  
|**Date Filter**|Select this field to specify the period that the report is to be printed for.|  
  
 The **Options** tab contains the fields listed in the following table.  
  
|Field|Description|  
|-----------|-----------------|  
|**Rounding Precision**|Select this field to choose the required rounding precision such as 0.001, 0.01, 1, or 1000.|  
|**Replace zero values by blanks**|Select this field to replace zero values with blanks during printing.|  
|**Skip accounts without net changes**|Select this field to exclude lines without net changes within the period.|  
|**Skip accounts with zero ending balance**|Select this field to exclude lines with zero ending balances at the end of the period.|  
|**Skip zero lines**|Select this field to exclude lines with zero values.|  
|**Print horizontal grid**|Select this field to print the horizontal grid.|  
  
## Vendor Accounting Card Report \(Report 12445\)  
 The Vendor Accounting Card report provides the following information for all of a vendor's entries for a specific period:  
  
-   Starting balance  
  
-   Posting date  
  
-   Document number  
  
-   Description  
  
-   Net change debit  
  
-   Net change credit  
  
-   Document type  
  
-   Ending balance  
  
 This report is usually printed monthly and on the date of inventory, but can be printed for any given period.  
  
 The following procedure shows how to access the Vendor Accounting Card report.  
  
1.  In **Financial Management**, choose **Payables**, and then choose **Turnover**.  
  
2.  Choose **Vendor G\/L Turnover**, choose**Print**, and then choose **Vendor Accounting Card**.  
  
 The **Vendor** tab of the request form contains the same fields as the **Vendor** tab of the Vendor General Ledger Turnover report. On the **Options** tab, you can select the **New page for Vendor** field to print the information for each vendor on a separate page.  
  
## Vendor Turnover Report \(Report 12444\)  
 The Vendor Turnover report is used to print the data about a vendor's entries for a specific period in the context of separate contracts \(agreements\). The report prints the vendor's number and name. If the vendor has an agreement, then the name of the agreement is entered. The system fills in the following information about the vendor \(if there are agreements, then the information is entered in the context of the agreements\):  
  
-   Starting balance \(debit or credit at the start of the period\)  
  
-   Net change \(debit or credit\)  
  
-   Ending balance \(debit or credit at the end of the period\)  
  
 To access the Vendor Turnover report  
  
-   In **Financial Management**, choose **Payables**, choose **Reports**, and then choose **Vendor Turnover**.  
  
 The **Vendor** tab of the request form contains the same fields as the **Vendor** tab of the Vendor General Ledger Turnover report. On the **Options** tab, you can specify the same format options as on the **Options** tab of the Vendor General Ledger report.  
  
## Vendor Posting Group Turnover Report \(Report 12443\)  
 The Vendor Posting Group Turnover report is used to print information on the vendor's entries that are accumulated in the vendor posting groups. The printed data contains the following information:  
  
-   Vendor posting group code  
  
-   Vendor posting group name  
  
-   Starting balance \(debit or credit\)  
  
-   Net change \(debit or credit\)  
  
-   Ending balance \(debit or credit\)  
  
 To access the Vendor Posting Group Turnover report  
  
-   In **Financial Management**, choose **Payables**, choose **Reports**, and then choose **Vendor Posting Group Turnover**.  
  
 On the **Vendor Posting Group** tab of the request form, you can specify the vendor posting group code or a range of vendor posting group codes, depending on whether you want to print the report for one vendor posting group, or for a range of vendor posting groups.  
  
 The **Vendor** tab contains the fields listed in the following table.  
  
|Field|Definition|  
|-----------|----------------|  
|**Global Dimension 1 Filter**|Select this field to can define a filter value for analysis on Global Dimension 1.|  
|**Global Dimension 2 Filter**|Select this field to define a filter value for analysis on Global Dimension 2.|  
|**Date Filter**|Select this field to specify the period that the report is to be printed for.|  
  
 On the **Options** tab, you can specify the same format options as on the **Options** tab of the Vendor General Ledger Turnover report.  
  
## Vendor Entries Analysis Report \(Report 12446\)  
 The Vendor Entries Analysis report shows the vendor's liabilities at the beginning and at the end of the period, entry analysis, and invoice discharging. The printed data contains the following information:  
  
-   Posting date  
  
-   Document number  
  
-   Document name  
  
-   Type \(payment, invoice\)  
  
-   Amount  
  
-   Amount closed  
  
-   Payment date  
  
 This report enables you to determine the invoice and payment interdependence, and it also shows closed entries, due invoices, partially discharged invoices, and vendor prepayment amounts.  
  
 To access the Vendor Entries Analysis report.  
  
-   In **Financial Management**, choose **Payables**, choose **Reports**, and then choose **Vendor Entries Analysis**.  
  
 On the **Vendor** tab of the request form, you can define the vendor number or a range of numbers, depending on whether you want to print the report for one vendor or for a number of vendors. On the **Options** tab, you can specify the format options listed in the following table.  
  
|Parameter|Description|  
|---------------|-----------------|  
|**Starting Date**|Select this option to specify the start date of the period.|  
|**Ending of period**|Select this option to specify the end date of the period.|  
|**Report Currency**|Select this option to specify the currency you want to use in the report. You can choose:<br /><br /> -   **Local currency**<br />-   **Transaction currency**|  
|**New Page For Vendor**|Select this option to print the data for each vendor on a separate page.|  
  
## Vendor Reconciliation Act Report \(Report 14911\)  
 The Vendor Reconciliation Act report shows the payments or liabilities of the vendor. It is used for the reconciliation of mutual payments of contractors.  
  
 To access the Vendor Reconciliation Act report  
  
-   In **Financial Management**, choose **Payables**, choose **Reports**, and then choose **Vendor Reconciliation Act**.  
  
 The following levels of details are possible:  
  
-   Full Detail  
  
-   Partial Detail  
  
-   None  
  
### Full Detail  
 If Full Detail is selected as the detail level, the report prints the following data for each document for the current and previous periods:  
  
-   Document number and the numbers of the documents connected with it.  
  
-   The balance on each document \(debit or credit\)  
  
-   Document date  
  
-   Description  
  
 The report prints the following on the right side of the form \(vendor's data\) if **Print Contactor Data** is active on the **Options** tab of the request form:  
  
-   Document amount  
  
-   Debit  
  
-   Credit  
  
### Partial Detail  
 If Partial Detail is selected as the detail level, the report displays the balance on each document for the current and previous periods, but does not display the connections to the invoices, credit notes, and payments.  
  
### None  
 If None is selected as the detail level, the report shows the following information for each vendor:  
  
-   The balance at the beginning of the period  
  
-   Net changes for the period  
  
-   The balance at the end of the period  
  
-   Amount of the vendor liabilities  
  
-   General managers' signatures  
  
### Selecting Print Vendor Data  
 When the **Print Contractor Data** field is selected, the right side of the report is filled in, based on data supplied by the vendor. Otherwise, the Vendor Reconciliation Act report is printed with the right side of the report not filled in.  
  
 To reconcile the mutual payments of contractors, you can print the Vendor Reconciliation Act forms with the left side filled in. These forms are supplied to vendors. The vendors fill in their data on the right side. Then the company's data is compared with the vendor's data, and if it is the same, the **Print Vendor Data** field is selected. A final Vendor Reconciliation Act document is printed, which is signed by general managers or other persons in charge of both parties.  
  
 On the **Vendor** tab of the request form, you can define the vendor number or a range of numbers, depending on whether you want to print a report for one vendor or for a number of vendors.  
  
 On the **Options** tab, you can specify the format options listed in the following table.  
  
|Parameter|Description|  
|---------------|-----------------|  
|**Starting Date**|Select this option to specify the start date of the period.|  
|**Ending Date of the Period**|Select this option to specify the end date of the period.|  
|**Report Currency**|Select this option to specify the currency that you want to use in the report. You can choose any currency from the glossary of currencies.|  
|**Detailed**|Select this option to select one of these values:<br /><br /> -   Full<br />-   Partial<br />-   None|  
|**Print Contractor Data**|Select this option to fill in the right side of the report with the vendor's data.|  
  
## See Also  
 [Russian Receivables Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/russian-receivables-reports.md)   
 [How to: Set Up Customer and Vendor Agreements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-customer-and-vendor-agreements.md)   
 [Payables and Receivables\-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/payables-and-receivables-duplicate.md)