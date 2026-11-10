---
title: Gather information for an audit
description: Match year-end audit PBC requests to Business Central reports and pages, reconcile balances, and identify the supporting documents to gather separately.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: reference
ms.date: 11/09/2026
ms.search.keywords: audit, PBC, prepared by client, year-end, reconciliation, audit evidence
ms.service: dynamics-365-business-central
ms.custom: bap-template
ai-usage: ai-assisted
---

# Prepare for an audit with Business Central reports

Use reports and pages in [!INCLUDE[prod_short](includes/prod_short.md)] to gather financial records for your year-end audit. This article maps typical *prepared by client (PBC)* checklist requests to reports, ledger entries, and setup information that you can use as supporting evidence.

The mapping covers the general ledger, cash and banking, accounts receivable, accounts payable, inventory, and controls that apply across these areas. Some requests need separate documents, such as bank-issued statements, accounting policies, and management's estimate calculations.

## Business roles in the data collection process

Accountants or financial controllers typically gather the data for audits, but the process can also involve other business roles, as described in the following table.

| Business role | Checklist responsibilities |
| --- | --- |
| Accountant or financial controller | Coordinate the package; prepare trial balances, G/L detail, financial statements, fixed-asset reconciliations, and year-end evidence. |
| Accounts receivable and accounts payable specialists | Prepare aging reports, customer/vendor reconciliations, invoices, credit memos, and subsequent-payment evidence. |
| Cash-management or treasury specialist | Prepare bank reconciliations, bank activity, statements, signatory information, and restricted-cash evidence. |
| Inventory or cost accountant, supported by warehouse/manufacturing staff | Prepare valuations, count evidence, cost reconciliations, revaluations, BOMs, and manufacturing WIP. |
| Approval administrator or process owner | Gather approval history, workflow configuration, and approval-limit evidence. |
| Business Central administrator | Arrange access and help retrieve setup and change-log evidence. |

### Permissions to gather data from reports and pages

For ordinary evidence gathering, users need permission to run the relevant reports and pages and read their underlying data, in each company in scope. Setup information also needs appropriate read access. Typically, the roles listed in the previous section have the required permissions. However, the exact permission sets depend on your organization's configuration. If someone can't open a page or run a report, an administrator can use the **Effective Permissions** page to verify access, including security filters that might restrict access.

For example, analysis mode and working with data in Excel might be restricted. The following table lists the permissions you need to use those features.

| Action | Permission you might need |
| --- | --- |
| Use analysis mode on the **General Ledger Entries** page. | Ask your administrator for the **DATA ANALYSIS - EXEC** permission set if you can't turn on analysis mode. |
| Export a list by using the **Open in Excel** action. | Ask your administrator for the **D365 Excel Export Action** permission set if the action isn't available. |
| Export report data by using the **Microsoft Excel Document (data only)** action. | Ask your administrator for the **Export Report Excel** permission set if this export option isn't available. This permission is different from the permission to run an Excel-layout report. |

## Plan your evidence package

Confirm the required evidence, reporting dates, currencies, and file formats with your auditor before you run reports. Use your fiscal year-end, which might differ from the calendar year-end.

For each output, record the company, report or page name, date filters, other filters, report options, and date you generated it. Keep these details with the file so that you can explain its scope and reproduce it. If you rerun a report after an adjustment, keep the versions clearly identified. Learn more about report filters and output formats in [Run and print reports](ui-work-report.md).

To find a report or page, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter its name, and then select the related link. Report availability and options can differ by country or region, installed apps, and permissions.

Learn more about exporting lists in [View and edit in Excel from Business Central](across-work-with-excel.md) and [Export data for auditing](finance-how-to-export-audit-files.md).

> [!IMPORTANT]
> A current list isn't necessarily a record of the position at year-end. For historical balances, use a report that calculates amounts as of the required date. For example, use the **Aged Accounts Receivable** or **Aged Accounts Payables** Excel reports, and set the **Aged As Of** field to your fiscal year-end. For setup and master data, distinguish the current configuration from evidence of changes during the year.

The tables in the following sections map typical PBC checklist requests to reports that can satisfy them, and describe the information you can gather. Select the links for the report or page names in the **Report or page** column to open them in [!INCLUDE[prod_short](includes/prod_short.md)] online. You might need to sign in and select a company.

## General ledger and financial statements

Start with the trial balance and detailed entries. Use the same reporting period and currency when you compare them with supporting schedules.

| PBC request | Report or page | Evidence to prepare |
|---|---|---|
| Year-end trial balance, including adjusted versions. | [Trial Balance](https://businesscentral.dynamics.com/?report=6) and [Closing Trial Balance](https://businesscentral.dynamics.com/?report=10) reports. | Save the balance and net change for each G/L account. The closing report compares this year's and last year's balances and shows income statement balances without closing entries. Check the treatment of closing entries when you label pre-closing and post-closing outputs.<br><br>Learn more about trial balance options in [Trial Balance](reports/report-6.md), [Closing Trial Balance](reports/report-10.md), and [Detail Trial Balance](reports/report-4.md). |
| Full-year general ledger detail. | [Detail Trial Balance](https://businesscentral.dynamics.com/?report=4) report or [General Ledger Entries](https://businesscentral.dynamics.com/?page=20) page. | Include opening balances, transactions, and closing balances. For an entry export, include the available account, posting date, document number, transaction number, entry number, amounts, source code, dimension fields, and system audit fields that the auditor requests. |
| Chart of accounts and financial statement mappings. | [Chart of Accounts](https://businesscentral.dynamics.com/?page=16) and [Financial Reports](https://businesscentral.dynamics.com/?page=108) pages. | Provide account names, categories, and account types. Include the row and column definitions used for requested financial statements. |
| Posting group mappings. | [General Posting Setup](https://businesscentral.dynamics.com/?page=314), [Customer Posting Groups](https://businesscentral.dynamics.com/?page=110), [Vendor Posting Groups](https://businesscentral.dynamics.com/?page=111), [Inventory Posting Setup](https://businesscentral.dynamics.com/?page=5826), [Bank Account Posting Groups](https://businesscentral.dynamics.com/?page=373), and [VAT Posting Setup](https://businesscentral.dynamics.com/?page=472) pages. | Provide the relevant mappings to G/L accounts. Include the posting groups assigned to the customer, vendor, item, or bank records in scope. |
| Dimension structures and usage. | [Dimensions](https://businesscentral.dynamics.com/?page=536), [Dimension Values](https://businesscentral.dynamics.com/?page=537), and [General Ledger Entries](https://businesscentral.dynamics.com/?page=20) pages. | Export the relevant dimensions and values. Use entry details or an analysis view to show how dimensions were used. A list of dimension definitions alone doesn't demonstrate their use on transactions. |
| Manual journals and posting users. | [General Ledger Entries](https://businesscentral.dynamics.com/?page=20) and [G/L Registers](https://businesscentral.dynamics.com/?page=116) pages. | Filter by the audit period and the journal source codes used in your company. Use register information to identify the posting user. Gather preparation and approval evidence separately where required; the posting user isn't necessarily the preparer or approver. |
| Reconciliation of customer and vendor ledgers to the G/L. | [Reconcile Cust. and Vend. Accs.](https://businesscentral.dynamics.com/?report=33) report. | Compare net changes for the same period and investigate highlighted differences. Supplement the report with year-end customer and vendor balances. |
| Reconciliation of fixed assets to the G/L. | Use fixed asset reports, such as[Fixed Asset Book Value 01](https://businesscentral.dynamics.com/?report=5605) and [Fixed Asset Book Value 02](https://businesscentral.dynamics.com/?report=5606), and [General Ledger Entries](https://businesscentral.dynamics.com/?page=20) page. | Compare acquisition costs, accumulated depreciation, and net book values for the relevant depreciation book with the mapped G/L accounts. Explain differences, including transactions that aren't integrated with the G/L.<br><br>Learn more about tracing transactions and reviewing fixed assets in [Analyze general ledger transactions](finance-how-to-analyze-gl-entries.md) and [Fixed asset reports](fa-reports.md). |
| Movement schedules for equity, retained earnings, and accruals. | [Trial Balance by Period](https://businesscentral.dynamics.com/?report=38) report and [Financial Reports](https://businesscentral.dynamics.com/?page=108) page. | Use starting balances and period-end balances to support a rollforward. Add transaction detail or a separate schedule when the auditor needs movements classified by type.<br><br>Learn more about reconciliation and account movements in [Reconcile Cust. and Vend. Accs.](reports/report-33.md) and [Trial Balance by Period](reports/report-38.md).|

For year-end cut-off checks, compare the dates in the **Posting Date**, **Created At**, and **Modified At** fields on the general ledger entries. The **Created At** and **Modified At** fields are system audit fields that record when an entry was created and last modified, rather than the accounting date assigned to it. You can't edit their values. Use them to identify entries created or changed after year-end with a posting date in the audit period. 

> [!NOTE]
> The **Created At** and **Modified At** fields don't display on the **General Ledger Entries** page. To access the fields, choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Screenshot of the Analysis Mode icon.":::, and then choose the fields on the **Columns** tab. To make the dates easier to compare, you can drag the fields to position them next to the **Posting Date** field. 

On the **General Ledger Entries** page, the **Transaction No.** field contains an automatically generated, sequential number that you can't edit. Use the sequence as supporting audit evidence that the entry population is complete, and investigate gaps that might indicate missing or deleted entries. Multiple entries can share a transaction number, so include the **Entry No.** value to identify individual entries. Check gaps against the full company ledger before drawing conclusions, because filters can exclude transactions from an export.

> [!NOTE]
> The **Document No.** field identifies the business document, not the system-generated transaction sequence. Don't use document numbers as the control for testing ledger completeness.

## Cash and banking

Use bank ledger entries and posted reconciliations to support cash balances. Gather the bank's own statements and confirmation evidence separately.

| PBC request | Report or page | Evidence to prepare |
|---|---|---|
| Year-end bank reconciliations, including outstanding payments and deposits. | [Bank Account Statement List](https://businesscentral.dynamics.com/?page=389) page and [Bank Account Statement](https://businesscentral.dynamics.com/?report=1407) report. | Open the posted year-end reconciliation and save the report. Use **Print Outstanding Transactions** when outstanding details are required. Follow the historical-report limitations in the linked guidance before using the output for an earlier period.<br><br>Learn more about completed reconciliations, outstanding transactions, and regional differences in [Review and analyze posted bank reconciliations](bank-review-posted-reconciliations.md).|
| List of bank accounts. | [Bank Accounts](https://businesscentral.dynamics.com/?page=371) page. | Include account identifiers, currencies, balances, and blocked status where relevant. Confirm closed or inactive accounts against treasury records rather than treating blocked status as proof of closure. Obtain authorized signatory lists separately. |
| Cash receipts and disbursements near year-end. | [Bank Account Ledger Entries](https://businesscentral.dynamics.com/?page=372) and [General Ledger Entries](https://businesscentral.dynamics.com/?page=20) pages. | Filter by bank or cash account and the requested posting dates. Include all accounts in scope, not just the main operating account. |
| Receipts and payments after year-end. | [Bank Account Ledger Entries](https://businesscentral.dynamics.com/?page=372), [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25), and [Vendor Ledger Entries](https://businesscentral.dynamics.com/?page=29) pages. | Filter for the subsequent period. For customer and vendor payments, review applied entries to identify the invoices settled. A payment date alone doesn't establish which year an invoice relates to. |
| Payment reconciliation activity. | [Bank Account Ledger Entries](https://businesscentral.dynamics.com/?page=372) and [G/L Registers](https://businesscentral.dynamics.com/?page=116) pages. | Trace posted payments from payment reconciliation journals to their ledger entries. An unposted journal isn't evidence that a payment was posted or a reconciliation completed. |
| Bank posting and electronic payment setup. | [Bank Account Posting Groups](https://businesscentral.dynamics.com/?page=373), [Bank Accounts](https://businesscentral.dynamics.com/?page=371), and [Data Exchange Definitions](https://businesscentral.dynamics.com/?page=1211) pages. | Document the G/L account mappings and the payment export configuration used by your company. Include related bank and payment method settings where relevant. |
| Restricted cash balances. | [Chart of Accounts](https://businesscentral.dynamics.com/?page=16) and the relevant ledger entries. | Identify separately tracked restricted amounts. Provide the agreements that explain the restrictions with the supporting balances. |

## Accounts receivable

Use reports calculated as of year-end for the receivables balance. Use posted documents and payment applications to support transaction samples and subsequent collections.

| PBC request | Report or page | Evidence to prepare |
|---|---|---|
| Year-end receivables aging. | [Aged Accounts Receivable Excel](https://businesscentral.dynamics.com/?report=4402) report. | Set the aging date to year-end and document the aging options. Reconcile the total in local currency with the relevant G/L control accounts. Investigate differences rather than assuming that the totals agree.<br><br>Learn more about aging and historical balances in [Aged Accounts Receivable Excel](reports/report-4402.md) and [Customer - Balance to Date](reports/report-121.md).|
| Customer master data, credit limits, and payment terms. | [Customers](https://businesscentral.dynamics.com/?page=22) page and customer cards. | Export the available fields requested by the auditor. Distinguish current master data and balances from historical year-end information. |
| Receivables reconciliation and rollforward. | [Customer - Balance to Date](https://businesscentral.dynamics.com/?report=121), [Customer - Detail Trial Balance](https://businesscentral.dynamics.com/?report=104), and [Reconcile Cust. and Vend. Accs.](https://businesscentral.dynamics.com/?report=33) reports. | Support opening balances, activity, and closing balances. Include detailed customer ledger entries when you need to explain applications or other movements. |
| Major customers and sales concentration. | [Customer - Top 10 List Excel](https://businesscentral.dynamics.com/?report=4409) report. | Specify the period and number of customers to rank. Provide additional transaction detail for selected customers if requested. |
| Significant invoices around year-end. | [Posted Sales Invoices](https://businesscentral.dynamics.com/?page=143) page. | Filter by posting date for the requested period before and after year-end. Provide selected invoice copies and related shipment or other supporting records needed to assess cut-off. |
| Credit memos and write-offs around year-end. | [Posted Sales Credit Memos](https://businesscentral.dynamics.com/?page=144) and [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25) pages. | Gather credit memo copies and relevant ledger entries, including write-offs that aren't represented by a credit memo. Include the reasons and available approval evidence. |
| Bad debt estimate support. | [Aged Accounts Receivable Excel](https://businesscentral.dynamics.com/?report=4402) report and [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25) page. | Supply aged balances, subsequent collections, and relevant account history. Provide management's calculation, assumptions, and approval separately. |
| Customer confirmation population. | [Customer Statement](https://businesscentral.dynamics.com/?report=1316) or [Customer - Balance to Date](https://businesscentral.dynamics.com/?report=121) report, with customer contact information. | Provide balances and supporting entries at the requested date. Coordinate external confirmation requests with your auditor; a customer statement isn't an independent confirmation. |
| Sales posting, deferrals, and dimension usage. | [General Posting Setup](https://businesscentral.dynamics.com/?page=314), [Sales & Receivables Setup](https://businesscentral.dynamics.com/?page=459), [Deferral Templates](https://businesscentral.dynamics.com/?page=1701), and relevant posted entries. | Document applicable sales account mappings and deferral settings. Use posted entry dimensions to support transaction analysis rather than relying only on master data defaults.<br><br>Learn more about customer movements and deferred amounts in [Customer - Detail Trial Balance](reports/report-104.md) and [Defer revenues and expenses](finance-how-defer-revenue-expenses.md).|

## Accounts payable

Prepare payable balances and supporting purchase activity for the same dates used in your general ledger package. Include subsequent payments and invoices when the auditor requests them.

| PBC request | Report or page | Evidence to prepare |
|---|---|---|
| Year-end payables aging. | [Aged Accounts Payables Excel](https://businesscentral.dynamics.com/?report=4403) report. | Set the aging date to year-end and document the aging options. Reconcile the total in local currency with the relevant G/L control accounts. |
| Vendor master data and payment terms. | [Vendors](https://businesscentral.dynamics.com/?page=27) page and vendor cards. | Provide requested payment terms, payment methods, posting groups, and other available fields. Use an as-of-date report for historical balances. |
| Payables reconciliation and rollforward. | [Vendor - Balance to Date](https://businesscentral.dynamics.com/?report=321), [Vendor - Detail Trial Balance](https://businesscentral.dynamics.com/?report=304), and [Reconcile Cust. and Vend. Accs.](https://businesscentral.dynamics.com/?report=33) reports. | Support opening balances, purchases, payments, credits, and closing balances. Investigate differences from the G/L.<br><br>Learn more about payable balances and movements in [Aged Accounts Payables Excel](reports/report-4403.md), [Vendor - Balance to Date](reports/report-321.md), and [Vendor - Detail Trial Balance](reports/report-304.md).|
| Significant purchase invoices around year-end. | [Posted Purchase Invoices](https://businesscentral.dynamics.com/?page=146) page. | Filter the requested periods before and after year-end. Gather selected invoice copies and related receipt or expense documentation to support cut-off testing. |
| Accrued expense schedules. | [Detail Trial Balance](https://businesscentral.dynamics.com/?report=4) report and [General Ledger Entries](https://businesscentral.dynamics.com/?page=20) page, filtered to accrual accounts. | Provide the posted accruals and subsequent reversals where relevant. Include separate calculations and supporting documents for the amounts accrued. |
| Vendor statements and confirmations. | [Vendor - Balance to Date](https://businesscentral.dynamics.com/?report=321) report. | Use the report as a listing of recorded vendor balances. Obtain vendor-issued statements separately and coordinate confirmation requests with your auditor. |
| Purchasing policies, posting setup, and approvals. | [Workflows](https://businesscentral.dynamics.com/?page=1500), [Approval User Setup](https://businesscentral.dynamics.com/?page=663), [General Posting Setup](https://businesscentral.dynamics.com/?page=314), and [Purchases & Payables Setup](https://businesscentral.dynamics.com/?page=460) pages. | Document the applicable setup and approval limits. Gather approval records for selected transactions and provide the written purchasing policy separately. For expected inventory cost posting, review **Inventory Setup**. |

## Inventory

Before you prepare final inventory valuation evidence, complete the applicable cost adjustments and inventory cost posting to the G/L. Review errors and unposted costs, and confirm the dates and filters used for reconciliation.

| PBC request | Report or page | Evidence to prepare |
|---|---|---|
| Year-end inventory quantities, values, and movements. | [Inventory Valuation](https://businesscentral.dynamics.com/?report=1001) report. | Specify the fiscal year date range to show opening balances, increases, decreases, and closing balances. Document whether you include expected costs and which item and location filters you use. |
| Costing methods and valuation support. | Item cards and [Inventory Valuation](https://businesscentral.dynamics.com/?report=1001) report. | Provide costing methods for the items in scope and supporting valuation entries. Don't use the current unit cost on an item card as a substitute for historical valuation.<br><br>Learn more about valuation and reconciliation in [Inventory Valuation](reports/report-1001.md) and [Reconcile inventory costs with the general ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md).|
| Inventory reconciliation to the G/L. | [Inventory - G/L Reconciliation](https://businesscentral.dynamics.com/?page=5845) page. | Compare inventory value entries with G/L totals for the same scope. Investigate differences, including unposted costs and interim account amounts.<br><br>Learn more about count evidence and cost adjustment logs in [Count, adjust, and reclassify inventory](inventory-how-count-adjust-reclassify.md) and [Track item cost adjustments](finance-track-inventory-costs.md).|
| Physical counts and cycle counts. | [Phys. Inventory Journal](https://businesscentral.dynamics.com/?page=392) or [physical inventory orders](https://businesscentral.dynamics.com/?page=5876) and [recordings](https://businesscentral.dynamics.com/?page=5880), depending on your process. | Keep count sheets, recorded counts, and posted results. Include the count date, locations, and the company's count instructions. |
| Count variances and adjustment approvals. | [Phys. Inventory Ledger Entries](https://businesscentral.dynamics.com/?page=390), [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38), [Value Entries](https://businesscentral.dynamics.com/?page=5802), and [Item Registers](https://businesscentral.dynamics.com/?page=117) pages. | Trace count results to posted quantity and value adjustments. Filter positive and negative adjustments as needed. Provide the review or approval evidence used by your company. |
| Standard cost changes and revaluations. | [Standard Cost Worksheet](https://businesscentral.dynamics.com/?page=5841), [Revaluation Journal](https://businesscentral.dynamics.com/?page=5803), and [Value Entries](https://businesscentral.dynamics.com/?page=5802) pages. | Retain the cost change support and trace implemented changes to posted revaluation entries. An unposted worksheet or journal doesn't establish that a revaluation was posted. |
| Cost adjustment runs and posting checks. | [Inventory Cost Adjustment](https://businesscentral.dynamics.com/?page=5801) page and [Post Invt. Cost to G/L - Test](https://businesscentral.dynamics.com/?report=1003) report. | Review available adjustment logs and resolve posting errors. Log coverage depends on the logging setup; automatic adjustments made during item posting aren't included in these logs. A test report doesn't itself post costs. |
| Bills of materials. | [Production BOM](https://businesscentral.dynamics.com/?page=99000787) and [Assembly BOM](https://businesscentral.dynamics.com/?page=36) pages. | Provide the requested component structures and relevant versions for manufactured or assembled items. |
| Manufacturing work in process (WIP). | [Production Order - WIP](https://businesscentral.dynamics.com/?report=5802) report. | Provide production order costs based on posted transactions for the requested date. Keep manufacturing WIP separate from project WIP schedules.<br><br>Learn more about WIP and stock aging in [Production Order - WIP](reports/report-5802.md) and [Item Age Composition by Quantity and Value](reports/report-5808.md).|
| Slow-moving or obsolete inventory. | [Item Age Composition by Quantity and Value](https://businesscentral.dynamics.com/?report=5808) report. | Use stock aging as supporting data. Provide management's separate assessment and calculation for any reserve or write-down. |
| Warehouse activity around year-end. | [Warehouse Entries](https://businesscentral.dynamics.com/?page=7318), [Warehouse Registers](https://businesscentral.dynamics.com/?page=7325), [Posted Whse. Receipts](https://businesscentral.dynamics.com/?page=7333), and [Posted Whse. Shipments](https://businesscentral.dynamics.com/?page=7340) pages. | Filter by the relevant dates and locations. Use warehouse records to support movement and cut-off testing, alongside item and value entries for financial amounts. |

## Evidence of controls and changes

Some evidence applies across multiple checklist areas. Gather it once and reference it from the related PBC requests.

| PBC request | Report or page | Evidence to prepare |
|---|---|---|
| Changes to customer, vendor, item, bank, or posting setup data. | [Change Log Entries](https://businesscentral.dynamics.com/?page=595) page. | Filter by the period and the relevant tables and fields. For vendor bank details, include the relevant vendor bank account data in the logging scope. The log only supports changes covered by the configuration and retained history. Enabling it now doesn't reconstruct earlier changes.<br><br>Learn more about logging scope in [Audit changes](across-log-changes.md).|
| Corrections to dimensions on posted G/L entries. | [General Ledger Entries](https://businesscentral.dynamics.com/?page=20) page, using **Correct Dimensions**. | Review correction history for the selected entries. Dimension corrections affect G/L entries, not the related subledger entries, so explain differences where relevant.<br><br>Learn more about dimension history in [Troubleshoot and correct dimensions](finance-troubleshooting-correcting-dimensions.md#view-historical-dimension-corrections).|
| Approvals for documents and journals. | [Approval Request Entries](https://businesscentral.dynamics.com/?page=662), [Workflows](https://businesscentral.dynamics.com/?page=1500), and [Approval User Setup](https://businesscentral.dynamics.com/?page=663) pages, with related approval records. | Gather the available request and approval history for the records in scope, including posted records where applicable. Distinguish the sender, approver, status, and timing. Current workflow setup alone doesn't prove that a particular transaction was approved.<br><br>Learn more about workflow records in [How to use approval workflows](across-how-use-approval-workflows.md) and year-end behavior in [Closing years and periods](year-close-years-periods.md).|
| Completion of year-end tasks. | [Accounting Periods](https://businesscentral.dynamics.com/?page=100), [General Ledger Setup](https://businesscentral.dynamics.com/?page=118), and relevant posted entries. | Document the completed tasks and supporting outputs, including closing entries and cost reconciliation. Review posting restrictions separately; closing a fiscal year doesn't by itself prevent further postings to that year. |
| Subsequent transactions and events. | Relevant bank, customer, vendor, and posted document pages. | Gather transactions after year-end for the requested review window. Trace them to prior-year balances or documents where relevant. Document management's assessment separately. |

## Documents to gather separately

Reports support the amounts in your evidence package, but they don't replace external evidence or management's explanations.

| PBC request | Separate evidence |
|---|---|
| Bank statements and confirmations. | Obtain bank-issued statements and coordinate independent confirmations with your auditor. |
| Authorized bank signatories and restrictions on cash. | Gather treasury records, bank mandates, and relevant agreements. |
| Accounting and purchasing policies. | Provide approved policy documents. Use setup information to explain how the policies are implemented. |
| Significant estimates, including bad debts, inventory reserves, and accruals. | Provide management's methodology, assumptions, calculations, and approval, supported by the relevant reports and entries. |
| Related parties and related-party transactions. | Prepare management's list of related parties. Use identified customers, vendors, accounts, or dimensions to gather transaction details. Don't assume that a standard customer or vendor list identifies all related parties. |

## Related information

[Overview of tasks to close accounting periods](year-how-complete-period-end-processes.md)  
[Prepare closing statements](year-prepare-close-statement.md)  
[Built-in finance reports](finance-reports.md)  
[Export data for auditing](finance-how-to-export-audit-files.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
