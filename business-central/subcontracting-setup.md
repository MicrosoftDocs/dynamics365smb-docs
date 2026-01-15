---
title: Subcontract manufacturing
description: This article gives an extended overview of the extended functionality of subcontracting, including work center fields and routing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: 99000886,
ms.date: 06/22/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Basic Setup

To effectively use Subcontracting, the following basic setups must be made. First, call up the "Subcontracting Setup" via the search.

## General

Specify which information from a subcontracting order should be transferred to your purchase documents. Activate/deactivate the corresponding switch or fill in the associated field.

|Field|Description|
|:--|:--|
|**Additional Information Line**|Specify whether an additional information line should be created in the subcontracting order.|
|**Operation Comment**|Specify whether the operation comment should be transferred to the purchase order.|
|**Subcontracting Inbound Whse. Handling Time**|Specify the time for calculating the receipt date in the transfer line.|

## Subcontracting

|Field|Description|
|:--|:--|
|**Subcontracting Suggestion Journal Template Name**|Select the name of the subcontracting journal template to be used for direct creation of subcontracting from a released operation.|
|**Components Purchase Price**|Select which purchase price of a subcontracting component should be used in the subcontracting order. You have the choice between: </br>**- Standard:** Standard price finding is used when procuring the component.</br> **- Subcontracting Component:** The calculated purchase price of the subcontracting component is transferred to the subcontracting order.|
|**Item Charge to Subcontracting Purch. Receipt Lines**|Activates item charge assignment for purchase receipt lines with subcontracting. When activated, an additional option becomes visible in the charge assignment in purchasing.|

## Purchase Provisions

|Field|Description|
|:--|:--|
|**Routing Link Code for Purchase Provision**|Specifies which routing link code should be used for purchase provision BOMs.|
|**Default Component Item No.**|Specifies the predefined component item number for purchase provisions.|
|**Work Center Group No. General**|Specifies the work center group no. to be used for purchase provisions.|
|**Work Center Put-away**|Specifies the work center for put-away in purchase provisions.|
|**Default Flushing Method**|Specifies the default provision flushing method to be used for purchase provisions.|
|**Always Save Changed Versions**|Specifies whether changed BOM and routing versions should always be saved in the provision wizard.|
|**Allow Edit UI Selection**|Specifies whether users may edit the UI selection in the provision wizard.|

### Provision Wizard Configuration

For the provision wizard, you can specify how the wizard should behave for different scenarios:

|Scenario|Description|
|:--|:--|
|**Both Available**|Configuration when both BOM and routing are available|
|**Partially Available**|Configuration when only BOM or only routing is available|
|**Nothing Available**|Configuration when neither BOM nor routing is available|

For each scenario, you can set the following options:

- **Operation/BOM Selection:** How the wizard handles the selection of routing and BOM
- **Production Operation/Components Selection:** How the wizard handles the preview of components and operations

**Available Options:**
- **Hide:** Step is skipped, automatic processing
- **Show:** Step is displayed, only display/selection possible
- **Edit:** Step is displayed, full editing possible

## Set Up Work Center Group for Subcontracting

To use a work center group for Subcontracting, it must be assigned to a vendor number.

1. Enter the corresponding number in your work center groups in the "Posting" tab. Read more about this [topic](https://docs.microsoft.com/en-us/dynamics365/business-central/production-how-to-set-up-work-and-machine-centers) in Microsoft's documentation.

1. Then open the vendor card and navigate to the "Shipping" tab.
Assign a "Subcontracting Location Code". This specifies the subcontracting location. Component items provided to the vendor are posted from this location by default after execution of the subcontracting.
Additionally, you can see from the "Linked to Work Center Group No." field whether a vendor is connected to a work center group.

> [!NOTE]
> It is recommended to define a separate location for each vendor.

## Advanced Setup Options

### Transfer Operation Comments
If you activate the "Operation Comment" field, comments from the production order routing lines are automatically transferred to the purchase order. This enables better communication with the subcontractor about special requirements or notes.

### Components Purchase Price Configuration
The "Components Purchase Price" field determines which unit cost is used for components in subcontracting purchase orders:

- **Standard:** Uses normal price finding based on purchase prices and discounts
- **Subcontracting Component:** Uses the calculated unit cost directly from the production order component

This setting influences cost calculation and should be chosen according to your calculation strategy.

### Subcontracting Inbound Whse. Handling Time
This field defines the time used for calculating the receipt date in transfer lines. The calculation follows the formula:

**Receipt Date = Due Date of Subcontracting Component - Whse. Handling Time**

This enables realistic planning of material provision at the subcontractor.