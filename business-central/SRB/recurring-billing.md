---
title: Recurring billing
description: You can use recurring billing in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Recurring billing

You bill contracts from the **Recurring Billing** page. First you create a billing proposal, based on which the posting documents such as invoices and credit memos, in a second step. To learn more about posting documents, go to [Posting documents](posting-documents.md). The billing or the creation of the billing proposal is based on the contract lines, taking into account the date in the **Next Billing Date** field. To learn more, go to [Managing contracts, service objects, and services commitments](working-with-contracts/contracts-services-mgmt.md).

## Work with billing proposals

The **Recurring Billing** page is structured as follows:

* **Filter area**
   * A **Billing Template** can be selected here.
   * The **Billing Date** is predefined by the billing template, but can be changed. Use it to suggest the appropriate contract lines for billing based on the **Next Billing Date** field (from the contract line).
   * Via the **Billing Rhythm**, each contract line brings the information up to which date it should be billed by default. Via the **Billing to Date** field, this can be specified (differently) for all lines to be created. This can result in the period to be billed being shortened or also extended. The field is also predefined via the billing template and can also be changed. By means of a limitation it could be achieved, for example, that contract items added during a fiscal year are only invoiced until the end of the year/fiscal year in order to have a uniform Billing Rhythm again for the next billing period.
* **Actions**
   * **Create Billing Proposal**
    The action runs through all contract lines and suggests the service commitments to be billed based on the **Next Billing Date** and the **Billing to Date**. By changing the billing template and calling it again, additional lines can be added to the billing proposal.
    If the **Next Billing Date** is greater than the billing date, this line will be ignored. If the **Next Billing Date** is smaller than the Billing Date, the corresponding period (taking into account the Billing Rhythm) must be invoiced.
   * **Create Documents**
    The action creates Contract invoices or credit memos for the displayed lines for which no documents exist yet.
   * **Clear Billing Proposal**
    By calling this action, the billing proposal can be deleted. A query follows asking whether the entire billing proposal or only the lines added by the currently selected billing template should be deleted.
   * **Delete Documents**
    The action deletes all generated Contract invoices or credit memos for the displayed lines.
   * **Change Billing To Date**
    Via this action, the date in the **Billing To** field can be individually adjusted. At the same time, the **Service Amount** will be recalculated. The action is executed for all selected lines.
   * **Delete Billing Line**
    This action is used to delete all selected lines.
   * **Refresh**
    This action updates the lines, e.g. if warnings are displayed there. If the reason for the warning is not given anymore, the warning is withdrawn.
   * **Navigate** 
   * **Customer / Vendor** 
    The action opens the customer or vendor card of the current line.
   * **Contract** 
    The action opens the contract card of the current line.
   * **Service Object** 
    The action opens the service object of the current line.
   * **Contract Line Dimensions** 
    Use to view the dimensions stored on the associated contract line.
* **Billing Proposal Lines**
   * The billing proposal lines show the details of the lines to be billed.
   * In addition to the contractor and the contract, information about the service object and the service commitments to be billed is also displayed.
   * When **Create Billing Proposal** is called, one or more lines are created for each service commitments based on the **Next Billing Date** and the **Billing to Date**. Multiple lines are always created if the **Billing Rhythm** of the contract line fits several times into the period between **Next Billing Date** and **Billing to Date**. Each line displays information regarding the billing period (**Billing from** and **Billing to** fields) and the prices (**Service Amount**, **Price**, **Quantity** and **Discount** fields). Using this method, no contract line to be billed can be overlooked (as long as the filter criteria from the billing template are correct), as all past contract lines are automatically part of the filter.
   * It is possible to define a grouping for the billing proposal in the **Billing Template** ([see next section](#billing-templates)). If a grouping is set in the currently selected Default, the billing proposal lines can be expanded and collapsed based on this criterion. This is done using the double arrow next to the **Partner Name** heading. In addition, individual blocks can also be expanded and collapsed. This is done using the single arrow next to the **Partner Name** field in the line.
   * If a posting document (invoice or credit memo) has already been created, it is displayed via **Document Type** and **Document No.**. A click on the Document No. opens the posting document.

> [!TIP]
> By changing the billing template and reopening the **Create Billing Proposal** page, you can extend the billing proposal piece by piece. In this way, for example, you can create collective invoices for several contracts, although the contracts are found via different billing proposals.

## Billing templates

By choosing the AssistEdit :::image type="content" source="../media/assist-edit-icon.png" alt-text="AssistEdit icon"::: in the **Billing Template** field, all available billing templates display. Each billing template requires a unique code and description as well as filter criteria and date calculation defaults. The date calculation defaults are specified in the form of date formulas. The actual date values are then calculated based on the working date when a billing template is selected/applied. This allows the defaults to be used over and over again.

Use the **Partner** field to specify whether this default is used to bill the customer (*Customer* value) or vendor (*Vendor* value) service commitments.

To use a billing template you must enter filter criteria. The criteria determines the service commitments to bill. To define the filters, use the **Edit Filter** action. A page opens where you can specify filter criteria. In addition to the pre-set criteria, you can add criteria such as the contract type, the responsible user, or the salesperson. When you choose **OK** on the filter page, the criteria are saved in the billing template. This is to be recognized by the fact that in the field **Contract filter** a hook is set.

In the **Billing Date Formula** field, a Dateformula is entered that will be interpreted when the billing template is used in the **Billing Date** field. This field is then used to filter the service commitments to be billed (based on **Next Billing Date**) when creating the proposal lines. If no Dateformula is specified, the **Recurring Billing** will use the Work Date.

The **Billing To Date Formula** field can optionally be used to enter a Dateformula which, if present, will be interpreted when the billing template is used in the **Billing To Date** field. This field is then used to set the end date of the billing in the service commitments to be billed. If no Dateformula is specified, the field in **Recurring Billing** will also remain empty and the lines will be proposed based on the information in the contract line.

The **My Suggestions Only** field can be used to filter the billing proposal to those lines created by the user.

The **Group by** field controls whether the lines in the billing proposal are displayed in groups. In addition to no grouping, the *Contract* and *Contract Partner* selections are available. If *Contract* is selected, all billing lines of a contract will be displayed grouped. The grouping level is displayed in bold. In addition, the **Billing From** and **Billing To** fields display the total (grouped) period and the **Service Amount** field displays the total of the associated Service Amounts.

> [!NOTE]
> Each contract line can be included in a billing proposal only once per billing period. If a billing line for a period has already been created by another user and the current billing proposal uses a default in which the **My Suggestions Only** indicator is set, the current user cannot create that line again for *themselves*.

## Create posting documents

After you create the billing proposal has been created, you can use the **Create Documents** action to create the invoices or credit memos for the displayed lines for which no documents exist yet. The page of the same name opens, where specifications for the documents to be created can be made. For example, both the **Document Date** and the **Posting Date** can be specified. Optionally, the created documents can also be posted directly (**Post documents**). In addition, **Documents per** can be used to specify whether the posting documents are to be created per contract, per contract partner, or per invoice recipient.

* **Contract**
A separate invoice is created for each *contract*. Thereby all defaults from the respective contract are taken over.
* **Contract Partner**
Invoices are created for each contract partner. Payment terms, payment methods, and so on are taken from the customer. Invoices are only created separately for the contracts if the currency or the [Details for contract invoices](working-with-contracts/customer-contracts.md#details-for-contract-invoices) differ.
* **Invoice Recipient**
Invoices are created for each *Invoice Recipient*. Payment Terms, Payment Method etc. are taken from the Customer. Invoices are only created separately for the contracts if the currency or the [Details for contract invoices](working-with-contracts/customer-contracts.md#details-for-contract-invoices) differ.

To learn more about the posting documents that are created, go to [Posting documents](posting-documents.md).

> [!TIP]
> Contract lines to be invoiced in advance and in arrears can be proposed for invoicing via different billing templates, if required. This is possible through the interaction of **Next Billing Date** and the **Billing Date**, provided that no **Billing To** date is used. Alternatively or additionally, the contracts to be billed differently can also be distinguished from each other using different types of contracts. To learn more, go to [Contract types](setup/contract-types.md). The contract type can be used as a filter in the billing templates.

## Need to update

**Recurring Billing** has a multi-level mechanism to prevent data inconsistencies.
If changes of any kind are made to a service commitment or contract line while lines are already created in the billing proposal, those lines will be highlighted twice in the billing proposal. On the one hand, the lines are displayed in red and bold and, on the other hand, they receive an indicator in the **Update Required** field, which shows that an update of the lines is necessary. When updating, the changed values are taken from the service commitments or the contract lines. The update can be done by running one of the **Create Billing Proposal** or **Refresh** actions. As long as the update has not been performed, no posting documents (invoice / credit memo) can be created.

If an unposted document already exists, no changes can be made to the service commitments or contract lines. A corresponding error message will appear.

Only changes that are *not billing relevant* can be made in the posting document itself. For example, changes can be made to the description of the lines or new lines can be added. For all other changes, the posting document must first be deleted, the changes made to the contract line (or service commitments), then the billing lines updated and the document recreated.

In addition, it is not possible to create multiple posting documents for the same billing line.

> [!NOTE]
> The moment a billing proposal is created for a contract line, the **Next Billing Date** field updates to show show the current status. If the billing line is deleted (or the billing period is changed), the field is automatically reset (or set based on the changed billing period).

A credit memo to a contract invoice will also reset the **Next Billing Date** field. To ensure consistency of the contract line and service commitments, when crediting multiple contract invoices, the credits must be chronological.

## Related information

[Managing contracts, service objects, and services commitments](working-with-contracts/contracts-services-mgmt.md)  
