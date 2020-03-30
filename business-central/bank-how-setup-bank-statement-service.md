---
title: Set Up Yodlee Bank Feeds| Microsoft Docs'
description: You can convert payment information to any data format that your bank requires and enable the export or import of bank files.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Yodlee, feed, stream, payment process
ms.date: 04/01/2020
ms.author: sgroespe

---
# Set Up the Envestnet Yodlee Bank Feeds Service
You can import electronic bank statements from your bank to quickly fill on the **Payment Reconciliation Journal** page so you can apply payments and reconcile the bank account. For more information, see [Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).

> [!IMPORTANT]
> Due to the new Payment Services Directive in Europe (PSD2), after September 14, 2019, you will no longer be able to automatically import bank statements from banks in the United Kingdom into [!INCLUDE[d365fin](includes/d365fin_md.md)]. We are looking into the possibility of offering this feature again in the future.

> [!NOTE]
> The Envestnet Yodlee Bank Feeds service is only supported in the online version of Business Central. To use this functionality on-premises, you must obtain a cobrand account from Envestnet Yodlee.<br /><br />
> The Envestnet Yodlee Bank Feeds service is only supported in the United States and Canada.
> Only banks residing in these countries are supported, even though banks from other countries may appear in the Envestnet Yodlee Bank Feeds bank selection window in [!INCLUDE[d365fin](includes/d365fin_md.md)].

> [!IMPORTANT]
> For technical assistance with the Envestnet Yodlee functionality, contact Microsoft Support. Do not contact Envestnet Yodlee. For more information, see [Configuring Technical Support for Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/technical-support).

The Envestnet Yodlee Bank Feeds service is installed as an extension to [!INCLUDE[d365fin](includes/d365fin_md.md)] online and is ready to be enabled in the supported countries. For more information, see [Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md).

After you enable the bank feed service, you must link a bank account to the online bank account that the feed will come from. You link bank accounts to online bank accounts in the following different scenarios:

* A bank account does not exist in [!INCLUDE[d365fin](includes/d365fin_md.md)] for your online bank account. Therefore, you create the bank account by linking from the online bank account.
* A bank account exists in [!INCLUDE[d365fin](includes/d365fin_md.md)], which you want to link to an online bank account.
* A linked bank account must be unlinked because you want to stop using the bank feed service for the account.
* Online bank accounts have changed and you want to update the information on bank accounts in [!INCLUDE[d365fin](includes/d365fin_md.md)].

When the bank feed service is enabled, you can set a bank account up to automatically import new bank statements into the **Payment Reconciliation Journal** page every two hour. Transactions for payments that have already been posted as applied and/or reconciled on the **Payment Reconciliation Journal** page will not be imported. For more information, see the “To enable automatic import of bank statements” section.

> [!NOTE]  
> If you use the Set Up Company assisted setup guide, some of the steps in the following procedures happen automatically when you get to the company bank account setup. For more information, see [Getting Started](product-get-started.md).

## To enable the bank feed service
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. Open the bank account that you will use for the bank feed service.
3. On the **Bank Account** page, in the **Bank Statement Import Format** field, select YODLEEBANKFEED.  

The bank feed service will be enabled when you link a bank account to its related online bank account. See the next procedure.  

> [!NOTE]
> If you use the **Company Setup** assisted setup guide, then you enable the service by selecting the **Use a bank feed service** check box. For more information, see [Creating New Companies in Business Central](about-new-company.md).

## To create a new linked bank account
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. Select the relevant bank account, and then choose the **Create New Linked Bank Account**. The **Bank Account Linking** page opens after a few moments.

    > [!NOTE]  
    > This page shows the actual web page of the Envestnet Yodlee Bank Feeds service. Terminology and functionality on the page may not match instructions provided in this topic.  
3. On the **Online Bank Account Linking** page, in the **Link Account** pane, use the Search function to find the bank where you have one or more online bank accounts.
4. Choose the bank name. The **Log In** pane opens.
5. Enter the username and password that you use to log on to the online bank, and then choose the **Next** button.  
6. The bank feed service prepares to link the first online bank account at the specified bank to a new bank account in [!INCLUDE[d365fin](includes/d365fin_md.md)].

    > [!NOTE]  
    > If you have more than one online bank account at the bank, you must create additional bank accounts in [!INCLUDE[d365fin](includes/d365fin_md.md)] for them. See steps 8 through 10.  

    After the process completes, the bank name will appear in the **My Accounts** pane on the **Linked** tab. The number in brackets indicates how many online bank accounts were linked.  
7. Choose the **OK** button.

    If you are only linking one online bank account, the **Bank Account Card** page opens and displays the name of the online bank account. In this case, the bank account linking task is completed. All that's left to do is to set up the bank account. For more information, see [Set Up Bank Accounts](bank-how-setup-bank-accounts.md).

    If you are linking more than one online bank accounts, the **Bank Account Linking** page opens and lists the online bank accounts that are not yet linked to bank accounts in [!INCLUDE[d365fin](includes/d365fin_md.md)]. In that case, follow the next step.  
8. On the **Bank Account Linking** page, select the line for an online bank account, and then choose the **Link to New Bank Account** action.  

    The **Bank Account Card** page for a new bank account opens and displays the name of the online bank account.

    If a bank account already exists in [!INCLUDE[d365fin](includes/d365fin_md.md)] that you want to link the additional online bank account to, follow the next step.  
9. On the **Bank Account Linking** page, select the line for an online bank account, and then choose the **Link to Existing Bank Account** action.
10. On the **Bank Account List** page, select the bank account that you want to link to, and then choose the **OK** button.

## To link a bank account to an online bank account
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. Select the line for a bank account that is not linked to an online bank account, and then choose the **Link to Online Bank Account** action. The **Online Bank Account Linking** page opens with the name of the bank prefilled in the **Link Account** pane.
3. Choose the bank name. The **Log In** pane opens.
4. Enter the username and password that you use to log on to the online bank, and then choose the **Next** button.  

    The bank feed service prepares to link your bank account in [!INCLUDE[d365fin](includes/d365fin_md.md)] to the related online bank account.  

    When the process has completed successfully, the bank name will appear in the **My Accounts** pane on the **Linked** tab. If the bank has more than one bank account, only the bank account that you selected in step 2 is linked.  
5. Choose the **OK** button.

On the **Bank Account List** page, the **Linked** check box is selected.

## To unlink a bank account
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.  
2. Select the line for a linked bank account that you want to unlink from its related online bank account, and the choose the **Unlink Online Bank Account** action.

> [!NOTE]  
> If you choose **Yes** on the confirmation dialog, the link to the online bank account is removed, and the log-in details are cleared. To link the bank account to the online bank account again, you must log on to the bank again. For more information, see the “To link a bank account to an online bank account“ section.

## To update bank account linking
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. Select the relevant bank account, and then choose the **Update Bank Account Linking** action.

If issues exist for any of the linked bank accounts on the **Bank Account List** page, the **Bank Account Linking** page opens specifying which bank accounts have issues. Issues can best be resolved by unlinking the online bank account and then re-creating the link. For more information, see the “To link a bank account to an online bank account“ section.

## To enable automatic import of bank statements
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. Select the line for a linked bank account, and then choose the **Automatic Bank Statement Import Setup** action.
3. On the **Automatic Bank Statement Import Setup** page, in the **Number of Days Included** field, specify how far back in time to get new bank transactions for.

    > [!NOTE]  
    > It is recommended that you set this value to 7 days or more.  
4. Select the **Enabled** check box.  

Every hour, the **Payment Reconciliation Journal** page will display new payments that are made on the online bank account.

> [!NOTE]  
> Transactions for payments that have already been posted as applied and/or reconciled on the **Payment Reconciliation Journal** page will not be imported.

## See Also
[Setting Up Banking](bank-setup-banking.md)  
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions ](ui-extensions.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
