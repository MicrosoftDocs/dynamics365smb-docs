---
title: Recurring billing
description: You can use recurring billing in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Recurring billing

Contracts are billed via the **Recurring Billing** page. First a Billing Proposal is created, based on which the **[Posting Documents](/docs/srb/posting-documents.md)** (invoices and credit memos) are created in a second step. The billing or the creation of the Billing Proposal is based on the contract lines, taking into account the **Next Billing Date** field (see [Overview of Fields in Service Commitments/Contract Lines](/docs/srb/working-with-contracts/contracts-services-mgmt.md)).


## Structure of the working area
The page is structured as follows:
1. **Filter area**
    - A **Billing Template** can be selected here.
    - The **Billing Date** is predefined by the Billing Template, but can be changed. It is used to suggest the appropriate contract lines for billing based on the **Next Billing Date** field (from the contract line).
    - Via the **Billing Rhythm**, each contract line brings the information up to which date it should be billed by default. Via the **Billing to Date** field, this can be specified (differently) for all lines to be created. This can result in the period to be billed being shortened or also extended. The field is also predefined via the Billing Template and can also be changed. By means of a limitation it could be achieved, for example, that contract items added during a fiscal year are only invoiced until the end of the year/fiscal year in order to have a uniform Billing Rhythm again for the next billing period.
2. **Actions**
    - **Create Billing Proposal** <br/>
    The action runs through all contract lines and suggests the Service Commitments to be billed based on the **Next Billing Date** and the **Billing to Date**. By changing the Billing Template and calling it again, additional lines can be added to the Billing Proposal. <br/>
    If the **Next Billing Date** is greater than the billing date, this line will be ignored. If the **Next Billing Date** is smaller than the Billing Date, the corresponding period (taking into account the Billing Rhythm) must be invoiced.
    - **Create Documents** <br/>
    The action creates Contract invoices or credit memos for the displayed lines for which no documents exist yet.
    - **Clear Billing Proposal** <br/>
    By calling this action, the Billing Proposal can be deleted. A query follows asking whether the entire Billing Proposal or only the lines added by the currently selected Billing Template should be deleted.
    - **Delete Documents** <br/>
    The action deletes all generated Contract invoices or credit memos for the displayed lines.
    - **Change Billing To Date** <br/>
    Via this action, the date in the **Billing To** field can be individually adjusted. At the same time, the **Service Amount** will be recalculated. The action is executed for all selected lines.
    - **Delete Billing Line** <br/>
    This action is used to delete all selected lines.
    - **Refresh** <br/>
    This action updates the lines, e.g. if warnings are displayed there. If the reason for the warning is not given anymore, the warning is withdrawn.
    - **Navigate** <br/>
        - *Customer / Vendor* <br/>
        The action opens the customer or vendor card of the current line.
        - *Contract* <br/>
        The action opens the contract card of the current line.
        - *Service Object* <br/>
        The action opens the Service Object of the current line.
        - *Contract Line Dimensions* <br/>
        This action can be used to view the dimensions stored on the associated contract line.
3. **Billing Proposal Lines**
    - The Billing Proposal lines show the details of the lines to be billed.
    - In addition to the contractor and the contract, information about the Service Object and the Service Commitments to be billed is also displayed.
    - When **Create Billing Proposal** is called, one or more lines are created for each Service Commitments based on the **Next Billing Date** and the **Billing to Date**. Multiple lines are always created if the **Billing Rhythm** of the contract line fits several times into the period between **Next Billing Date** and **Billing to Date**. Each line displays information regarding the billing period (**Billing from** and **Billing to** fields) and the prices (**Service Amount**, **Price**, **Quantity** and **Discount** fields). Using this method, no contract line to be billed can be overlooked (as long as the filter criteria from the Billing Template are correct), as all past contract lines are automatically part of the filter.
    - It is possible to define a grouping for the Billing Proposal in the **Billing Template** ([see next section](#billing-templates)). If a grouping is set in the currently selected Default, the Billing Proposal lines can be expanded and collapsed based on this criterion. This is done using the double arrow next to the **Partner Name** heading. In addition, individual blocks can also be expanded and collapsed. This is done using the single arrow next to the **Partner Name** field in the line.
    - If a posting document (invoice or credit memo) has already been created, it is displayed via **Document Type** and **Document No.**. A click on the Document No. opens the posting document. 

:::tip Extend Billing Proposal
By changing the Billing Template and calling **Create Billing Proposal** again, the Billing Proposal can be extended piece by piece. In this way, for example, collective invoices can be created for several contracts, although the contracts are found via different Billing Proposals.
:::


## Billing Templates
By clicking on the AssistEdit in the **Billing Template** field, all available Billing Templates will be displayed. Each Billing Template requires a unique code and description as well as filter criteria and date calculation defaults. The date calculation defaults are specified in the form of date formulas. The actual date values are then calculated based on the working date when a Billing Template is selected/applied. This allows the defaults to be used over and over again. <br/>
The **Partner** field is used to specify whether this default is used to bill customer (*Customer* value) or vendor (*Vendor* value) Service Commitments. <br/>
In order to use a Billing Template, filter criteria must be entered, which will then be used to determine the Service Commitments to be billed. To define the filters, the **Edit Filter** action is called. A *filter page* opens where the criteria can be defined. In addition to the pre-set criteria, further criteria like the Contract Type, the responsible officer or the salesperson can be added (via *+ Filter...*). If the *filter page* is left via *OK*, the criteria are saved in the Billing Template. This is to be recognized by the fact that in the field **Contract filter** a hook is set. <br/>
In the **Billing Date Formula** field, a Dateformula is entered that will be interpreted when the Billing Template is used in the **Billing Date** field. This field is then used to filter the Service Commitments to be billed (based on **Next Billing Date**) when creating the proposal lines. If no Dateformula is specified, the **Recurring Billing** will use the Work Date. <br/>
The **Billing To Date Formula** field can optionally be used to enter a Dateformula which, if present, will be interpreted when the Billing Template is used in the **Billing To Date** field. This field is then used to set the end date of the billing in the Service Commitments to be billed. If no Dateformula is specified, the field in **Recurring Billing** will also remain empty and the lines will be proposed based on the information in the contract line. <br/>
The **My Suggestions Only** field can be used to filter the Billing Proposal to those lines created by the user. <br/>
The **Group by** field controls whether the lines in the Billing Proposal are displayed in groups. In addition to no grouping, the *Contract* and *Contract Partner* selections are available. If *Contract* is selected, all billing lines of a contract will be displayed grouped. The grouping level is displayed in bold. In addition, the **Billing From** and **Billing To** fields display the total (grouped) period and the **Service Amount** field displays the total of the associated Service Amounts. <br/>

:::important Billing Proposals with multiple users
Each contract line can be included in a Billing Proposal only once per billing period. If a billing line for a period has already been created by *another* user and the current Billing Proposal uses a default in which the **My Suggestions Only** indicator is set, the *current* user cannot create that line again for *themselves*.
:::


## Create Posting Documents
Once the Billing Proposal has been created, the **Create Documents** action can be used to create the invoices or credit memos for the displayed lines for which no documents exist yet. The page of the same name opens, where specifications for the documents to be created can be made. For example, both the **Document Date** and the **Posting Date** can be specified. Optionally, the created documents can also be posted directly (**Post documents**). In addition, **Documents per** can be used to specify whether the Posting Documents are to be created per *Contract*, per *contract Partner* or per *Invoice recipient*. <br/>
* **Contract** <br/>
A separate invoice is created for each *contract*. Thereby all defaults from the respective contract are taken over.
* **Contract Partner** <br/>
Invoices are created for each *Contract Partner*. Payment Terms, Payment Method etc. are taken from the Customer. Invoices are only created separately for the contracts if the currency or the *[Detail Overview](/docs/srb/working-with-contracts/customer-contracts.md#details-for-contract-invoices)* in the contracts differ.
* **Invoice Recipient** <br/>
Invoices are created for each *Invoice Recipient*. Payment Terms, Payment Method etc. are taken from the Customer. Invoices are only created separately for the contracts if the currency or the *[Detail Overview](/docs/srb/working-with-contracts/customer-contracts.md#details-for-contract-invoices)* in the contracts differ.

Further details on the Posting Documents created are explained in more detail [here](/docs/srb/posting-documents.md).

:::tip In-advance and post-invoicing
Contract lines to be invoiced in advance and in arrears can be proposed for invoicing via different Billing Templates, if required. This is possible through the interaction of **Next Billing Date** and the **Billing Date**, provided that no **Billing To** date is used. Alternatively or additionally, the contracts to be billed differently can also be distinguished from each other using different **[Contract Types](/docs/srb/setup/contract-types.md)**. The Contract Type can be used as a filter criterion in the Billing Templates.
:::


## Need to update
The **Recurring Billing** is equipped with a multi-level mechanism to prevent data inconsistencies. <br/>
If changes of any kind are made to a Service Commitment or contract line while lines are already created in the Billing Proposal, those lines will be highlighted twice in the Billing Proposal. On the one hand, the lines are displayed in red and bold and, on the other hand, they receive an indicator in the **Update Required** field, which shows that an update of the lines is necessary. When updating, the changed values are taken from the Service Commitments or the contract lines. The update can be done by executing one of the actions **Create Billing Proposal** or **Refresh**. As long as the update has not been performed, no Posting Documents (invoice / credit memo) can be created. <br/>
If an unposted document already exists, no changes can be made to the Service Commitments or contract lines. A corresponding error message will appear. <br/>
Only changes that are *not billing relevant* can be made in the posting document itself. For example, changes can be made to the description of the lines or new lines can be added. For all other changes, the posting document must first be deleted, the changes made to the contract line (or Service Commitments), then the billing lines updated and the document recreated. <br/>
In addition, it is not possible to create multiple Posting Documents for the same billing line.

:::note Updating the contract lines
The moment a Billing Proposal is created for a contract line, the **Next Billing Date** field is immediately updated. It therefore *always* shows the current status. If the billing line is deleted (or the billing period is changed), the field is automatically reset (or set based on the changed billing period). <br/>
A credit memo to a contract invoice will also reset the **Next Billing Date** field. To ensure consistency of the contract line and Service Commitments, when crediting multiple contract invoices, the credits must be chronological.
:::