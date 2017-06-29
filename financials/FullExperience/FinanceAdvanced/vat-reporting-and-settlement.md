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
# VAT Reporting and Settlement
FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> --> contains some special tables to manage the tasks necessary for settling VAT and reporting to the customs and tax authorities.  
  
## VAT Reporting  
 You can use tables to calculate the VAT due for a period. [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] creates an entry in the **VAT Entries** window for each posted transaction that involves VAT. These entries are used to calculate the VAT that must be settled for a given period. Then you can prepare and print the VAT statement report.  
  
### VAT Statement  
 You use a VAT statement to specify the basis for calculating the VAT payable to the tax authorities. In the **VAT Statement** window, you define the VAT statement based on the accounts in the **Chart of Accounts** window or based on entries in the **VAT Entries** window. The advantage of using the VAT entries option is that you can close these entries by posting the VAT Settlement. It is easier to locate VAT correction entries in previous accounting periods, where the VAT statement has been done, by working with VAT entries.  
  
 The VAT statement is normally defined when you initially set up the company in the program. It is recommended that you set up the statement with the format that is required by the tax authorities. After the statement has been defined, it can be previewed and printed.  
  
 For more information on VAT statements, see [How to: Define VAT Statements](../Finance/how-to-define-vat-statements.md), [How to: Preview VAT Statements](../Finance/how-to-preview-vat-statements.md), and [How to: Print VAT Statements](../Finance/how-to-print-vat-statements.md).  
  
## VAT Settlement  
 Periodically, you must remit the net VAT to the tax authorities. You can use a batch job as often as you want if you need to settle VAT frequently. After you have approved the VAT statement, you can run the **Calc. and Post VAT Settlement** batch job to close the open VAT entries and transfer purchase and sales VAT amounts to the VAT settlement account.  
  
 For more information on transferring VAT amounts, see [How to: Transfer VAT Amounts to the Settlement Account](../Finance/how-to-transfer-vat-amounts-to-the-settlement-account.md).  
  
> [!NOTE]  
>  As soon as the VAT entries have been posted and their status is closed, they cannot be opened again. However, you can still create VAT reports from these closed entries.  
  
## See Also  
 [Recording VAT](../Finance/recording-vat.md)   
 [How to: Record VAT](../Finance/how-to-record-vat.md)   
 [Import VAT](../Finance/import-vat.md)   
 [How to: Enter VAT\-liable Amounts Without VAT in General Journals](../Finance/how-to-enter-vat-liable-amounts-without-vat-in-general-journals.md)   
 [How to: Set Up and Record Intrastat](../Finance/how-to-set-up-and-record-intrastat.md)   
 [How to: Create a VAT Combination Setup](../Finance/how-to-create-a-vat-combination-setup.md)   
 [How to: View VAT Entries](../Finance/how-to-view-vat-entries.md)