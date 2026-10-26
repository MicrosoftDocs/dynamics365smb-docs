---
title: Set Up GST Compensation Cess
description: Set up GST Compensation Cess components and item classifications for applicable transactions in the India localization of Business Central.
author: v-debapd  
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, GST compensation cess, GST posting setup, tax rates, GST groups
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Set up GST compensation cess

Business Central supports GST compensation cess for India.

**“GST Compensation Cess”** is levied by the Goods and Services Tax (Compensation to States) Act 2017. The object of levying this cess is to compensate the states for the loss of revenue arising due to the implementation of GST on 1st July 2017 for five years or such period as recommended by the GST Council. GST, being a consumption-based tax, would result in loss of revenue for manufacturing-heavy states.

All taxpayers who are engaged in the supply of selected goods or services other than exporters and composition taxpayers collect compensation cess. This also includes compensation cess chargeable on certain goods imported to India. In case compensation cess is paid on exports, the exporter can claim refund of the same.

## Plan the cess setup

The following is the list of setups that are pre-configured with the help of Tax Engine

- Tax Types
- Component
- Rate Setup
- Attributes

For more information about Automatic Setup, see **Tax Engine** information.

The following is the list of setups that are required to be configured manually

- [Tax Rate](gst-cess-basic-setup.md#set-up-tax-rates)
- [HSN/SAC](gst-cess-basic-setup.md#set-up-hsnsac)
- [GST Groups](gst-cess-basic-setup.md#set-up-gst-groups)
- [GST Posting Setup](gst-cess-basic-setup.md#set-up-gst-posting-setup)

## Set up tax rates

Rate of GST is defined in combination of GST Group Code, HSN/SAC. States and Date.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Tax Types**, and then choose the related link.
1. Select **GST CESS**, and then choose **Tax Rates**.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**GST Group Code**|Specifies the GST group code.|
    |**HSN/SAC Code**|Specifies the HSN/SAC code.|
    |**From State**|Specifies the vendor state code.|
    |**Location State Code**|Specifies the location state code.|
    |**Date From**|Specifies the starting date.|
    |**Date To**|Specifies the ending date.|
    |**CESS**|Specifies the cess percentage.|
    |**Before Threshold Cess**|Specifies the cess percentage when the line amount is less than or equal to **Threshold Amount**.|
    |**Threshold Amount**|Specifies the threshold amount.|
    |**Cess Amount per Unit Factor**|Specifies the cess amount for the quantity defined by **Cess Factor Quantity**. This value is an amount, not a percentage.|
    |**Cess Factor Quantity**|Specifies the Cess factor, which decides the base of per unit.|

## Set up HSN/SAC

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **HSN/SAC**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**GST Group Code**|Specifies the GST group code.|
    |**Code**|Specifies the HSN or SAC Code.|
    |**Description**|Specifies the description of the HSN/SAC code.|
    |**Type**|Specifies whether the code is an HSN or SAC.|

## Set up GST groups

List of GST Cess groups need to be defined. A group can be of two types, **Goods** or **Service**.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **GST Group**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|---------------------------------------|
    |**Code**|Specifies the group code.|
    |**Description**|Specifies the name of the group.|
    |**GST Group Type**|Specifies whether the group is defined as goods or service.|
    |**GST Place of Supply**|Specifies GST place of supply of the GST group.|
    |**Component Calc. Type**|Specifies the calculation method of cess.|
    |**Cess UOM**|Specifies the unit of measure to be considered for this group.|
    |**Cess Credit**|Specifies whether the input credit for cess of this group is availment or non availment.|
    |**Reverse Charge**|Specifies whether the group is defined as reverse charge or not.|

For calculation methods that use an amount per unit, fill in **Cess UOM**, **Cess Factor Quantity**, and **Cess Amount per Unit Factor**. The calculation validates these values before calculating cess.

## Set up GST posting setup

Define G/L accounts for each component and state combination.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **GST Posting Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|---------------------------------------|  
    |**State Code**|Specifies the state code of company that has valid GST registration number.|
    |**GST Component Code**|Specifies the relevant component code.|
    |**Receivable Account**|Specifies the general ledger account for which Cess receivable amount for this state and component is to be posted.|
    |**Payable Account**|Specifies the general ledger account for which Cess Payable amount for this state and component is to be posted.|
    |**Receivable Account (Interim)**|Specifies the general ledger account for which Cess receivable interim amount for this state and component is to be posted.|
    |**Payables Account (Interim)**|Specifies the general ledger account for which Cess payable interim amount for this state and component is to be posted.|

## Related information

[GST Cess Calculation](GST-Cess-Calculations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
