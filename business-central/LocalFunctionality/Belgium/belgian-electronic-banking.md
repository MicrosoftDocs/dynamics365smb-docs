---
    title: Electronic Banking (BE)
    description: Electronic banking allows you to electronically exchange data with Belgian financial institutions. Learn how to set up Business Central for electronic banking, electronic payments, and IBLC/BLWI transaction codes.
    author: edupont04

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 10/01/2020
    ms.author: edupont

---
# Electronic Banking in the Belgian Version

In the Belgian version of [!INCLUDE[prod_short](../../includes/prod_short.md)], the electronic banking functionality is extended so that you can exchange data with Belgian financial institutions electronically, either on disk or via Interbanks Standards Association Belgium (Isabel). This speeds up processing time and helps avoid errors caused by manual data entry or processing.  

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can use electronic banking to perform the following functions:  

- Send [electronic payments](belgian-electronic-payments.md).  
- Process bank statements with [CODA](coda-bank-statements.md).  
- Process [direct debits with domiciliations](direct-debit-using-domiciliation.md).  

## Set up electronic banking

With electronic banking, you can make electronic payments to domestic, international, SEPA, and non-Euro SEPA vendors and customers. Before you can use electronic banking, you must set up the following information:  

- Electronic banking setup  
- IBLC/BLWI codes

> [!TIP]
> For an overview of how to add bank accounts in [!INCLUDE[prod_short](../../includes/prod_short.md)], see [Set Up Bank Accounts](../../bank-how-setup-bank-accounts.md).  

### To set up electronic banking  

1. Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Electronic Banking Setup**, and then choose the related link.  
2. On the **Electronic Banking Setup** page, fill in the fields as described in the following table.  

    | Field | Description |
    |--|--|
    | **Summarize Gen. Jnl. Lines** | Specifies if you want to group the payment journal lines for each vendor. |
    | **Cut off Payment Message Texts** | Specifies if you want to truncate long payment messages. Messages will be truncated if greater than 106 characters for domestic payments and less than 140 characters for international payments. |

[!INCLUDE[summarize-gen-journal-lines](../includes/BE/summarize-gen-journal-lines.md)]

For more information, see [Summarizing Payment Lines and General Journal Lines](summarizing-payment-lines-and-general-journal-lines.md).  

Next, you must set up export protocols that define the file format that is generated when you export payment history to be processed by the bank. For more information, see [Set Up Export Protocols](how-to-set-up-export-protocols.md).  

## IBLC-BLWI transaction codes

In order to process electronic payments, you must set up transaction codes according to the requirements of the Belgian-Luxembourg Exchange Institute. These are international identification codes for the different types of payment transactions. The IBLC/BLWI codes are used only for international payments.  

### To set up IBLC/BLWI transaction codes  

1. Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IBLC/BLWI Transaction Codes**, and then choose the related link.  
2. Choose the **New** action.  
3. Enter the **Transaction Code** and **Description**. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]  

## See Also

[Belgian Electronic Payments](belgian-electronic-payments.md)  
[CODA Bank Statements](coda-bank-statements.md)  
[Direct Debit Using Domiciliation](direct-debit-using-domiciliation.md)
[Belgium Local Functionality](belgium-local-functionality.md)  
[Setting Up Banking](../../bank-setup-banking.md)  
[Managing Payables](../../payables-manage-payables.md)  
[Isabel website](https://go.microsoft.com/fwlink/?LinkId=210323)  
