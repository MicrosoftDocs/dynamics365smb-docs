---
title: Setting up GST Compensation Cess
description: Describes the essential configurations needed to set up GST Compensation Cess.
author: v-debapd  
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, GST compensation cess, GST posting setup, tax rates, GST groups
ms.date: 19/06/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up GST compensation cess

Business Central has included GST Compensation Cess feature to Indian Localization.

**“GST Compensation Cess”** is levied by the Goods and Services Tax (Compensation to States) Act 2017. The object of levying this cess is to compensate the states for the loss of revenue arising due to the implementation of GST on 1st July 2017 for five years or such period as recommended by the GST Council. GST, being a consumption-based tax, would result in loss of revenue for manufacturing-heavy states.

All taxpayers who are engaged in the supply of selected goods or services other than exporters and composition taxpayers collect compensation cess. This also includes compensation cess chargeable on certain goods imported to India. In case compensation cess is paid on exports, the exporter can claim refund of the same.

## Process

The following is the list of setups that are pre-configured with the help of Tax Engine

- Tax Types
- Component
- Rate Setup
- Attributes

For more information about Automatic Setup, see **Tax Engine** information.

The following is the list of setups that are required to be configured manually

- [Tax Rate](gst-cess-basic-setup.md#to-set-up-tax-rates)
- [HSN/SAC](gst-cess-basic-setup.md#to-set-up-hsnsac)
- [GST Groups](gst-cess-basic-setup.md#to-set-up-gst-groups)
- [GST Posting Setup](gst-cess-basic-setup.md#to-set-up-gst-posting-setup)

## Set up tax rates

Rate of GST is defined in combination of GST Group Code, HSN/SAC. States and Date.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Tax Type** -> **GST CESS** -> **Action** -> **Tax Rates**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**GST Group Code**|Specifies the GST group code.|
    |**HSN/SAC**|Specifies the HSN/SAC code.|
    |**From State**|Specifies the vendor state code.|
    |**Location State Code**|Specifies the location state code.|
    |**Date From**|Specifies the starting date.|
    |**Date To**|Specifies the ending date.|
    |**CESS %**|Specifies the Cess rate.|
    |**Before Threshold %**|Specifies the Cess rate if the amount doesn't cross defined threshold amount.|
    |**Threshold Amount**|Specifies the threshold amount.|
    |**Cess Amount per Unit Factor %**|Specifies the cess amount, which is levied on per unit of goods.|
    |**Cess Factor Quantity**|Specifies the Cess factor, which decides the base of per unit.|

## Set up HSN/SAC

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Tax Type** -> **HSN/SAC**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**GST Group Code**|Specifies the GST group code.|
    |**Code**|Specifies the HSN or SAC Code.|
    |**Description**|Specifies the location state code.|
    |**Type**|Specifies whether the code is an HSN or SAC.|

## Set up GST groups

List of GST Cess groups need to be defined. A group can be of two types, **Goods** or **Service**.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **GST Groups**, and then choose the related link.
1. Fill in the fields as described in the following table. 

    |Field|Description|
    |---------------------------------|---------------------------------------|
    |**Code**|Specifies the group code.|
    |**Description**|Specifies the name of the group.|
    |**GST Group Type**|Specifies whether the group is defined as goods or service.|
    |**GST Place of Supply**|Specifies GST place of supply of the GST group.|
    |**Component Calculation Type**|Specifies the calculation method of Cess.|
    |**Cess UOM**|Specifies the unit of measure to be considered for this group.|
    |**Cess Credit**|Specifies whether the input credit for cess of this group is availment or non availment.|
    |**Reverse Charge**|Specifies whether the group is defined as reverse charge or not.|

## Set up GST posting setup

General Ledger Account for each component and state combination is defined state-wise.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **GST Posting Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description| 
    |---------------------------------|---------------------------------------|  
    |**State Code**|Specifies the state code of company that has valid GST registration number.|
    |**GST Component Code**|Specifies the relevant component code.|
    |**Receivable Account**|Specifies the general ledger account for which Cess receivable amount for this state and component is to be posted.|
    |**Payable Account**|Specifies the general ledger account for which Cess Payable amount for this state and component is to be posted.|
    |**Receivable Account (Interim)**|Specifies the general ledger account for which Cess receivable interim amount for this state and component is to be posted.|
    |**Payable Account (Interim)**|Specifies the general ledger account for which Cess payable interim amount for this state and component is to be posted.|

## Related information

[GST Cess Calculation](GST-Cess-Calculations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
