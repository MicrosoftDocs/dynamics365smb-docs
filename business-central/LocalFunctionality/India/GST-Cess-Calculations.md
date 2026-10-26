---
title: Cess Calculation
description: Learn how GST Compensation Cess is calculated in Business Central for India, including calculation types, methods, and examples.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, Cess calculation, Cess calculation types, Cess ca;culation methods  
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Cess calculation

- GST Compensation Cess is leviable on both interstate and intrastate supply of goods. It's also applicable on imports and goods transactions that are subject to reverse charge.
- It's applicable only on notified goods. Examples include pan masala, tobacco products, coal, aerated waters, and motor vehicles. Confirm the applicable goods and rates for the transaction date.
- GST Compensation Cess is calculated on taxable value. Though it's coined as Cess, it's similar to tax. It's independent of IGST, CGST, and SGST.
- Input Tax Credit availed on GST Compensation Cess can be utilized only towards discharging Output tax liability of Compensation Cess and not otherwise.

The rates and amounts in the following examples illustrate the calculation methods. They aren't a statement of current rates. In the tables, use CGST and SGST for an intrastate transaction, or IGST for an interstate transaction—not all three components together.

## Calculation types of cess

There are five different calculation types for cess calculation

- Cess %
- Threshold
- Cess % + Amount / Unit Factor
- Cess % Or Amount / Unit Factor Whichever Higher
- Amount / Unit Factor

## Calculate cess by percentage

If the Cess is applicable for any commodity, based on the GST group code then system picks the Cess% defined on it.

In this scenario, invoice has been issued for INR 800 on which 18% IGST (9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction), 10% Cess has to be charged.

- GST calculation appears in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|
    |**Quantity**|2|
    |**Unit Amount**|400|
    |**GST Base Amount**|800|  
    |**CGST**|72 (800*9/100)|  
    |**SGST**|72 (800*9/100)|
    |**IGST**|144 (800*18/100)|
    |**CESS**|80 (800*10/100)|

## Calculate cess by threshold

For **Threshold**, define **Threshold Amount**, **Before Threshold Cess**, and **CESS** in the tax rates. The before-threshold percentage applies when the line amount is less than or equal to the threshold. The **CESS** percentage applies above the threshold. The comparison is per line, not for the invoice total.

Suppose **Before Threshold Cess** is 2% and **Threshold Amount** is INR 1,000. An invoice has been issued for INR 800. In this scenario, as the line amount is less than the threshold amount, 2% cess is charged.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Quantity**|2|
    |**Unit Amount**|400|
    |**GST Base Amount**|800|  
    |**CGST**|72 (800*9/100)|  
    |**SGST**|72 (800*9/100)|
    |**IGST**|144 (800*18/100)|
    |**CESS**|16 (800*2/100)|

Suppose, **Cess %** is 10% and **Threshold Amount** is INR 1,000. An invoice has been issued for INR 10000. In this scenario as the amount is greater than the threshold amount, 10% Cess has to be charged.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Quantity**|2|
    |**Unit Amount**|5000|
    |**GST Base Amount**|10000|  
    |**CGST**|900 (10000*9/100)|  
    |**SGST**|900 (10000*9/100)|
    |**IGST**|1800 (10000*18/100)|
    |**CESS**|1000 (10000*10/100)|

## Calculate cess by percentage plus amount per unit factor

For component calculation type - ‘Cess % + Amount/Unit Factor’, system considers ‘Cess %’ along with ‘Amount/Unit Factor’ defined on GST Setup fields, that is, **Cess UOM (Unit of Measure)**, **Cess Amount Per Unit Factor**, and **Cess Factor Quantity**.

Suppose, **Cess %** is 10%, **Cess Amount per Unit Factor** is INR 130 and  **Cess Factor Quantity** is 1. An invoice has been issued for INR 10000. In this scenario 10% Cess and INR 260 has to be charged.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Quantity**|2|
    |**Unit Amount**|5000|
    |**GST Base Amount**|10000|  
    |**CGST**|900 (10000*9/100)|  
    |**SGST**|900 (10000*9/100)|
    |**IGST**|1800 (10000*18/100)|
    |**CESS**|1260 [{1000=(10000*10/100)}+{260=(130x2)}]|

## Calculate the higher of percentage or amount per unit factor

For component calculation type - ‘Cess or Amount/Unit Factor whichever is higher’ system considers ‘Cess %’ or ‘Amount/Unit Factor’ whichever is higher based on values defined on GST Setup fields, that is, **Cess UOM (Unit of Measure)**, **Cess Amount Per Unit Factor**, and **Cess Factor Quantity**.

Suppose, **Cess %** is 10%, **Cess Amount per Unit Factor** is INR 130 and  **Cess Factor Quantity** is 1. An invoice has been issued for INR 10000. In this case, cess amount is INR 1000, which is higher than the quantity multiplied by the Cess Amount per Unit Factor, hence system considers INR 1000 as Cess Amount.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Quantity**|2|
    |**Unit Amount**|5000|
    |**GST Base Amount**|10000|  
    |**CGST**|900 (10000*9/100)|  
    |**SGST**|900 (10000*9/100)|
    |**IGST**|1800 (10000*18/100)|
    |**CESS**|1000 [{1000=(10000*10/100)} > {260=(130x2)}]|

Suppose, **Cess %** is 5%, **Cess Amount per Unit Factor** is INR 1000 and  **Cess Factor Quantity** is 1. An invoice has been issued for INR 10000. In this case, the quantity multiplied by the Cess Amount per Unit Factor is INR 2000, which is higher than the rate defined in Cess%, hence system considers INR 2000 as Cess Amount.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|
    |**Quantity**|2|
    |**Unit Amount**|5000|
    |**GST Base Amount**|10000|  
    |**CGST**|900 (10000*9/100)|  
    |**SGST**|900 (10000*9/100)|
    |**IGST**|1800 (10000*18/100)|
    |**CESS**|2000 [{2000=(1000x2)} > {500=(10000*5/100)}]|

## Calculate cess by amount per unit factor

For component calculation type as ‘Amount/Unit Factor’ system considers Cess value based on values defined GST Group Code in fields **Cess UOM**, **Cess Amount Per Unit Factor** and **Cess Factor Quantity**.

The quantity-based calculation converts the line quantity to **Cess UOM**, divides it by **Cess Factor Quantity**, and multiplies the result by **Cess Amount per Unit Factor**. The examples use a factor quantity of 1 and don't require a unit conversion.

Suppose, **Cess Amount per Unit Factor** is INR 140 and  **Cess Factor Quantity** is 1. An invoice has been issued for INR 10000. In this scenario, INR 280 has to be charged.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Quantity**|2|
    |**Unit Amount**|5000|
    |**GST Base Amount**|10000|  
    |**CGST**|900 (10000*9/100)|  
    |**SGST**|900 (10000*9/100)|
    |**IGST**|1800 (10000*18/100)|
    |**CESS**|280 (140x2)|

## Related information

[GST Cess Basic Setup](GST-Cess-Basic-Setup.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]