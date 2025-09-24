---
title: Reconciling Bank Accounts [US]
description: This article describes how to reconcile bank account ledger entries with bank statements in the North American version.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.search.keywords: bank account ledger, bank reconciliation, reconciliation reports, bank account reconcile
ms.search.form: 389, 10120,10121,10122,10123,10124,10125,10126,10127,10128,10129,10130,10131,10133,10134
ms.date: 02/04/2025
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Reconciling bank accounts in the US version

> [!IMPORTANT]
> The bank reconciliation and deposits features are no longer available for the North American versions (US, CA, and MX) in 2023 release wave 2. The features are now part of the standard version of [!INCLUDE [prod_short](../../includes/prod_short.md)], so that more countries can benefit from them. To learn more about the standard features, go to [Manage and Reconcile Your Bank Accounts](../../bank-manage-bank-accounts.md).
>
> For details about what changed, go to [Standardizing the bank reconciliation process in North American versions](/dynamics365-release-plan/2022wave1/smb/dynamics365-business-central/standardizing-bank-reconciliation-process-north-american-versions).
>
> If you're still using the deprecated **Bank Reconciliation Worksheet** or **Deposits** pages, there are a few things you should do after you upgrade to 2023 release wave 2. For example, if you have open entries, you'll probably want to complete them. To learn more, go to [NA bank reconciliation and deposits are deprecated in the North American version](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-na-bank-rec).

Use the **Bank Rec. Worksheet** page to reconcile bank account ledger entries with bank statements.

## Reconcile bank accounts with bank statements

Follow these steps to reconcile bank accounts with bank statements:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Account Reconciliations**, and then choose the related link.
1. Choose the **New** action.  
1. On the **General** FastTab, fill in the required fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Bank Account No.**|The bank account number to reconcile.|  
    |**Statement No.**|The bank statement number to reconcile.|  
    |**Statement Date**|The bank statement date.|  
    |**Statement Balance**|The bank statement balance.|  

1. Choose the **Mark Lines** action.  
1. On the **Bank Rec. Process Lines** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Record type to process**|Specify the type as **Checks**, **Deposits**, or **Both**.|  
    |**Mark lines as cleared**|Select to process the option selected in the **Record type to process** field.|  

1. On the **Bank Rec. Line** FastTab, select the appropriate filters.  
1. Choose the **OK** button.  
1. On the **Bank Rec. Worksheet** page, on the **Bank Rec. Adj. Lines Subform** FastTab, enter information in the remaining fields to make adjustments.  

    > [!NOTE]  
    > If needed, you can also use the **Bank Rec. Worksheet** page to view the **Bank Reconciliation Comments** card or the **Bank Reconciliation** card.

## Post a bank reconciliation

You can post bank reconciliation if you reconciled the bank accounts on the **Bank Rec. Worksheet** page. After the bank reconciliation is posted, a bank account statement is created and can be viewed on the bank account card.  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Account Reconciliations**, and then choose the related link.
1. Choose the bank account reconciliation that you want to post, and then choose the **Edit** action.  

    > [!NOTE]  
    > On the **General** FastTab, the value in the **Difference** field be must be zero before you can post the bank reconciliation.  

    When the bank reconciliation is posted, all of the related files are posted to the historical **Post Bank Rec. Worksheet** table. Any adjustments are posted to the **G/L Entry** table.  

1. Choose the **Post** action.  
1. To review a preliminary draft of the bank reconciliation statement, choose the **Test Report** action. The **Bank Rec. Test Report** shows the entries that result if you post.  

## View the posted bank account reconciliations

Follow these steps to view the posted bank account reconciliations:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
1. Choose the bank account that you want to view the posted reconciliations for > **Related** action > **Bank Acc.** action > **Posted Reconciliations** action.  
1. Select the relevant statement that you want to view.  
1. In the worksheet that appears, choose the **Print** action or the **Send** action, and make the relevant selections in the report options page.  

    The bank reconciliation test report that was printed before you posted the reconciliation is printed again. This report can then be used for auditing purposes.  
1. Close the report request page.  

## Print a bank reconciliation test report

You can print the following bank reconciliation reports:  

- **Bank Rec. Test Report** - Displays the list of errors that are found in the bank reconciliation statement. You can generate this report before you post the bank reconciliation statement to make sure that there are no errors in the statement.  

- **Bank Account – Reconcile** - Displays the reconciliation details for each bank account. This report lists deposits, withdrawals, and adjustments for a bank account.

Follow these steps to print a bank reconciliation test report:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Account Reconciliations**, and then choose the related link.  
1. Choose the **Bank Rec. Test Report** action.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Print details**|Include reconciliation details in the report. If you select this check box, all of the other print check boxes are automatically selected. You can clear a check box if you don't want to include its details in the report.|  
    |**Print checks**|Print check details in the report.|  
    |**Print deposits**|Print deposit details in the report.|  
    |**Print adjustments**|Print adjustment details in the report.|  
    |**Print outstanding checks**|Print outstanding check details in the report.|  
    |**Print outstanding deposits**|Print outstanding deposit details in the report.|  

1. On the **Bank Rec. Header** FastTab, select the appropriate filters.  
1. Choose the **Print** button to print the report. Choose the **Preview** button to view it on the screen.  

## Print a bank reconciliation report

Follow these steps to print a bank reconciliation report:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Account Reconciliations**, and then choose the related link.  
1. Choose the **Bank Account – Reconcile** action.  
1. To print each bank account on a new page, choose the **New Page per Bank Account** check box.  
1. On the **Bank Account** FastTab, choose the appropriate filters.  
1. Choose the **Print** button to print the report. Choose the **Preview** button to view it.  

## Related information

- [United States Local Functionality](united-states-local-functionality.md)  
- [Finance](../../finance.md)  
- [Setting Up Finance](../../finance.md)  
- [Reconcile Bank Accounts](../../bank-how-reconcile-bank-accounts-separately.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
