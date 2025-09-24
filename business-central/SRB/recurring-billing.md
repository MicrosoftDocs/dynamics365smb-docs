---
title: Recurring billing
description: You can use recurring billing in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 8067_Primary, 
ms.date: 05/02/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Recurring billing

You bill contracts from the **Recurring Billing** page. First you create a billing proposal, based on which the posting documents such as invoices and credit memos, in a second step. To learn more about posting documents, go to [Posting documents](posting-documents.md). The billing or the creation of the billing proposal is based on the contract lines, taking into account the date in the **Next Billing Date** field. To learn more, go to [Managing contracts, subscriptions, and subscription lines](working-with-contracts/contracts-services-mgmt.md).

## Work with billing proposals

The following tables explain the fields and actions on the **Recurring Billing** page.

### Filter

|Field  |Description  |
|---------|---------|
|**Billing Template**  |  Select a billing template. To learn more about billing templates, go to [Billing templates](#billing-templates).   |
|**Billing Date**     | Use the date to suggest the appropriate contract lines for billing based on the **Next Billing Date** field from the contract line. The date is predefined by the billing template, but you can change it.  |
|**Billing to Date**     | Via the **Billing Rhythm**, each contract line brings the information up to which date it should be billed by default. Via the **Billing to Date** field, this can be specified (differently) for all lines to be created. This can result in shortening or extending the billing period. The field is also predefined via the billing template and can also change it. By means of a limitation it could be achieved, for example, that contract items added during a fiscal year are only invoiced until the end of the year/fiscal year in order to have a uniform billing rhythm again for the next billing period.        |

### Actions

|Action  |Description  |
|---------|---------|
|**Create Billing Proposal**     |  Goes through all contract lines and suggests the subscription lines to be billed based on the **Next Billing Date** and the **Billing to Date**. By changing the billing template and running the action again, you can add lines to the billing proposal.<br><br>If the **Next Billing Date** is greater than the billing date, this line will be ignored. If the **Next Billing Date** is smaller than the Billing Date, the corresponding period (taking the billing rhythm into account) must be invoiced.       |
|**Create Documents**  | Creates subscription contract invoices or credit memos for lines for which no documents exist. To learn more about documents, go to [Create posting documents](#create-posting-documents). |
|**Clear Billing Proposal**     |  Deletes the billing proposal. A query follows asking whether to delete the entire billing proposal or only the lines added by the currently selected billing template.       |
|**Delete Documents**     | Deletes all contract invoices or credit memos for the lines.        |
|**Change Billing To Date**     |  Adjusts the date in the **Billing To** field for all selected lines, and recalculates the value in the **Amount** field. |
|**Delete Billing Line**| Deletes all selected lines. |
|**Refresh**| Updates the lines, for example, if there are warnings. If you resolved the cause of the warning, the warning is removed.|
|**Navigate**| Opens the customer or vendor selected on the line.|
|**Contract**| Opens the contract selected on the line.|
|**Subscription**|Opens the subscription on the line.|
|**Contract Line Dimensions**|Opens the dimensions stored on the associated contract line.|

### Billing proposal lines

Billing proposal lines show the details of the lines to be billed. In addition to the vendor and the contract, information about the subscription and the subscription lines to bill also displays.

When you use the **Create Billing Proposal** action, one or more lines are created for each subscription line based on the **Next Billing Date** and the **Billing to Date**. Multiple lines are always created if the **Billing Rhythm** of the contract line fits several times into the period between **Next Billing Date** and **Billing to Date**. Each line displays information regarding the billing period (**Billing from** and **Billing to** fields) and the prices (**Amount**, **Price**, **Quantity** and **Discount** fields). All past contract lines are automatically part of the filter.

You can use the **Group by** field to create groups for the billing proposal in the billing template. To learn more about groups, go to ([Billing templates](#billing-templates)). If a grouping is set, you can use the double arrow next to the **Partner Name** field to expand or collapse the groups. 

If an invoice or credit memo was already created, it displays in the **Document Type** and **Document No.** fields. To open the document, choose the value in the **Document No.** field.

> [!TIP]
> By changing the billing template and reopening the **Create Billing Proposal** page, you can extend the billing proposal piece by piece. For example, you can create a collective invoice for contracts that are included in different billing proposals.

## Billing templates

By choosing the AssistEdit :::image type="content" source="../media/assist-edit-icon.png" alt-text="AssistEdit icon"::: in the **Billing Template** field, all available billing templates display. Each billing template requires a unique code and description as well as filter criteria and date calculation defaults. The date calculation defaults are specified in the form of date formulas. The actual date values are then calculated based on the working date when a billing template is selected/applied. This allows the defaults to be used over and over again.

Use the **Partner** field to specify whether the template is for customer or vendor subscription lines.

To use a billing template, you must enter filter criteria. The criteria determines the subscription lines to bill. To define the filters, use the **Edit List** action. In addition to the pre-set criteria, you can add criteria such as the contract type, the responsible user, or the salesperson. When you choose **OK**, the criteria are saved in the billing template.

In the **Billing Date Formula** field, enter a dateformula that's taken into account when the billing template is used in the **Billing Date** field. This field is then used to filter the subscription lines to bill, based on **Next Billing Date**, when creating the proposal lines. If you don't specify a dateformula, recurring billing uses the work date.

Optionally, you can use the **Billing to Date Formula** field to enter a dateformula that's taken into accountwhen the billing template is used in the **Billing to Date** field. This field is then used to set the end date of the billing in the subscription lines. If you don't specify a dateformula, the field on the **Recurring Billing** page remains empty and lines are proposed based on the information in the contract line.

You can use the **My Suggestions Only** field to filter the billing proposal to lines that you created.

The **Group by** field controls whether the lines in the billing proposal display in groups. In addition to no grouping, the **Contract** and **Contract Partner** options are available. The **Contract** option groups all billing lines of a contract. The grouping level is displayed in bold. In addition, the **Billing from** and **Billing to** fields display the total (grouped) period and the **Amount** field displays the total of the amounts.

> [!NOTE]
> Each contract line can be included in a billing proposal only one time per billing period. If a billing line for a period was already created by another user, and the current billing proposal uses a default in which the **My Suggestions Only** checkbox is selected, you can't create the line again for yourself.

## Create posting documents

After you create the billing proposal, you can use the **Create Documents** action to create the invoices or credit memos for the displayed lines for which no documents exist yet. The **Create Documents** page opens, where you can specify how to create the documents. For example, you can specify the **Document Date** and the **Posting Date**. Optionally, the created documents can also be posted directly (**Post documents**). Use the **Documents per** field to specify whether to create the posting documents per contract, contract partner, or invoice recipient.

* **Contract**: Create a separate invoice for each contract. All defaults from the respective contract are taken over.
* **Contract Partner**: Create invoices for each contract partner. The payment terms, payment methods, and so on, are taken from the customer. Invoices are only created separately for the contracts if the currency or the [Details for contract invoices](working-with-contracts/customer-contracts.md#details-for-contract-invoices) differ.
* **Invoice Recipient**: Create invoices for each invoice recipient. The payment terms, payment methods, and so on, are taken from the customer. Invoices are only created separately for the contracts if the currency or the [Details for contract invoices](working-with-contracts/customer-contracts.md#details-for-contract-invoices) differ.

To learn more about posting documents, go to [Posting documents](posting-documents.md).

> [!TIP]
> You can use different billing templates to propose invoices for contract lines in advance and in arrears. Use a combination of **Next Billing Date** and the **Billing Date**, provided that no **Billing to** date is specified. Alternatively, or additionally, you can distinguish between the contracts to bill differently by using different types of contracts. To learn more, go to [Subscription contract types](setup/contract-types.md). You can use the contract type as a filter in the billing templates.

## Need to update

**Recurring Billing** has a multi-level mechanism to prevent data inconsistencies. If changes of any kind are made to a subscription line or contract line while lines are already created in the billing proposal, those lines are highlighted in the billing proposal. The lines display in red and bold font, and they have an indicator in the **Update Required** field. When updating, the changed values are taken from the subscription lines or the contract lines. You can run the update by using the **Create Billing Proposal** or **Refresh** actions. As long as the update isn't done, you can't create invoices or credit memos.

If an unposted document already exists, you can't change the subscription lines or contract lines.

You can only make changes that aren't relevant for billing in the posting document. For example, you can change the descriptions of the lines or add new lines. For all other changes, you must delete the posting document, make the changes to the contract lines or subscription lines, and then recreate the updated billing lines and the document.

Also, you can't create multiple posting documents for the same billing line.

> [!NOTE]
> The moment you create a billing proposal for a contract line, the **Next Billing Date** field updates to show show the current status. If you delete the billing line or change the billing period, the field is automatically reset or set based on the changed billing period.

A credit memo for a contract invoice also resets the **Next Billing Date** field. To ensure consistency of the contract line and subscription lines, credits must be chronological when you credit multiple contract invoices.

## Related information

[Managing contracts, subscriptions, and subscription lines](working-with-contracts/contracts-services-mgmt.md)  
