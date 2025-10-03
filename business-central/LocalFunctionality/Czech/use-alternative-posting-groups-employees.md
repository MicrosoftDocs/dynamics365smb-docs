---
title: Alternative posting groups for Employees in the Czech Version
description: Learn how to set up and use alternative posting groups for employees in the Czech version of Business Central to manage payables and receivables effectively.
author: v-pejano
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: CZ, Czech, Employees, Payables, Finance
ms.date: 09/29/2025
ms.reviewer: v-soumramani
ms.author: v-pejano
---

# Alternative posting groups for employees in the Czech version

Sometimes businesses want to post payable and receivable transactions to a different general ledger (G/L) account than the one that's specified on the employee posting group. This can include scenarios where employee travel expenses need to be post to a different financial account than the one used for regular payroll transactions. Controllers can define policies for posting these transactions, and accountants can change them during posting.

## Setup of alternative posting groups for employees

You can allow users to change the default employee posting groups by turning on the **Allow Multiple Posting Groups** toggle on the **Human Resources Setup** page.

To set this up, follow these steps:

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter Human Resources Setup, and then choose the related link.
2. On the Human Resources Setup page, on the Numbering tab, turn on the Allow Multiple Posting Groups toggle.
3. When you're finished, close the page.

:::image type="content" source="media/employees-alt-posting-gr-setup.png" alt-text="Screenshot of the Human Resource Setup page.":::

On the **Employee Posting Group** page, select the **Alternative Groups** action to specify posting groups that users can choose as substitutes. Alternative posting groups can replace the default employee posting group assigned to an employee.

:::image type="content" source="media/employees-alt-posting-gr.png" alt-text="Screenshot of the page that shows alternative employee posting groups.":::

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Employee Posting Groups**, and then select the related link.
2. On the **Employee Posting Groups** page, select the employee posting group for which you want to define alternative posting groups.
3. On the **Employee Posting Group** page, choose the **Alternative Groups** action.
4. On the **Alternative Employee Posting Groups** page, choose the **New** action to create a new line.
5. In the **Alternative Employee Posting Group** field, select the posting group that you want to use as an alternative.
6. When you're finished, close the page.

After you set this up, you can choose alternative posting groups and change the employee posting group when you post journals. [!INCLUDE [d365fin](../../includes/d365fin_md.md)] copies the alternative employee posting group to posted journals, and posts payable or receivable G/L entries to the G/L accounts specified for the alternative groups.

After you complete this setup, you can select alternative posting groups and change the employee posting group when posting journals. [!INCLUDE [d365fin](../../includes/d365fin_md.md)] copies the alternative employee posting group to the posted journals and posts payable or receivable G/L entries to the G/L accounts specified for the alternative groups.

**If you want only certain people to edit posting groups**, turn on the **Allow Multiple Posting Groups** toggle for chosen employees on the **Employee Card** page.

## Use of alternative posting groups for employees

When all conditions are met, [!INCLUDE [d365fin](../../includes/d365fin_md.md)] allows you to change the posting group on journals and ensures that transactions are posted to the payables or receivables account specified at the time of posting.

:::image type="content" source="media/employees-alt-posting-gr-gl-journal.png" alt-text="Screenshot that shows the G/L journal posting with alternative posting groups.":::

If different employee posting groups are used in a general journal or payment document, the G/L entries are automatically reallocated among the accounts of each posting group when employee entries are applied.

The standard posting method for applying entries increases turnover on both the debit and credit sides by the same amount. In the Czech version of this functionality, the balancing is posted as a correction, which means that **postings are made to only one side**, either the debit or the credit account. This approach **prevents turnover from increasing on balance sheet accounts** and ensures that values remain accurate for analysis.

## Related information

- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
