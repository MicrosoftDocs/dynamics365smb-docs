---
title: Cess Calculation
description: Cess Calculation

    
author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Cess Calculation


- GST Compensation Cess is leviable on both interstate and intrastate supply of goods. It is also applicable on imports and goods transactions which are subject to reverse charge.
- It is applicable only on notified goods. These goods as on date are pan masala, tobbaco and tobacco products, coal, aerated waters, motor cars & motor vehicles and any other supplies.
- GST Compensation Cess is calculated on taxable value. Though it is coined as Cess, it is similar to tax. It is independent of IGST, CGST and SGST.
- Input Tax Credit availed on GST Compensation Cess can be utilized only towards discharging Output tax liability of Compensation Cess and not otherwise.

## Calculation types of Cess

There are five different calculation types for cess calculation

- Cess %
- Threshold
- Cess % + Amount / Unit Factor
- Cess % Or Amount / Unit Factor Whichever Higher
- Amount / Unit Factor

## Method of calculation for type Cess%

If the Cess is applicable for any commodity, based on the GST group code then system will pick the Cess% defined on it.

In this scenario, invoice has been issued for INR 800 on which 18% IGST (9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction), 10% Cess has to be charged.

- GST calculation will appear in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|
    |**Quantity**|2|
    |**Unit Amount**|400|
    |**GST Base Amount**|800|  
    |**CGST**|72 (800*9/100)|  
    |**SGST**|72 (800*9/100)|
    |**IGST**|144 (800*18/100)|
    |**CESS**|80 (800*10/100)|

## Method of calculation for type Threshold

For Threshold calculation type user will define **Threshold Amount**, **Before Threshold %** and **Cess %** (considered after crossing threshold amount). Note that Threshold amount defined in **GST CESS** setup for a particular GST Group Code will be applicable line wise.

Suppose, **Before Threshold %** is 2% and **Threshold Amount** is INR 1,000. An invoice has been issued for INR 800. In this scenario as the amount is less than the threshold amount, 2% Cess has to be charged.

- GST calculation will appear in the Fact Box, as following:
    
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

- GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Quantity**|2|
    |**Unit Amount**|5000|
    |**GST Base Amount**|10000|  
    |**CGST**|900 (10000*9/100)|  
    |**SGST**|900 (10000*9/100)|
    |**IGST**|1800 (10000*18/100)|
    |**CESS**|1000 (10000*10/100)|

## Method of calculation for type Cess% + Amount per Unit Factor

For component calculation type - ‘Cess % + Amount/Unit Factor’, system will consider ‘Cess %’ along with ‘Amount/Unit Factor’ defined on GST Setup fields i.e. **Cess UOM (Unit of Measure)**, **Cess Amount Per Unit Factor** and **Cess Factor Quantity**.

Suppose, **Cess %** is 10%, **Cess Amount per Unit Factor** is INR 130 and  **Cess Factor Quantity** is 1. An invoice has been issued for INR 10000. In this scenario 10% Cess and INR 260 has to be charged.



- GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Quantity**|2|
    |**Unit Amount**|5000|
    |**GST Base Amount**|10000|  
    |**CGST**|900 (10000*9/100)|  
    |**SGST**|900 (10000*9/100)|
    |**IGST**|1800 (10000*18/100)|
    |**CESS**|1260 [{1000=(10000*10/100)}+{260=(130x2)}]|

## Method of calculation for type Cess% Or Amount/Unit Factor Whichever Higher

For component calculation type - ‘Cess or Amount/Unit Factor whichever is higher’ system will consider ‘Cess %’ or ‘Amount/Unit Factor’ whichever is higher based on values defined on GST Setup fields i.e. **Cess UOM (Unit of Measure)**, **Cess Amount Per Unit Factor** and **Cess Factor Quantity**.

Suppose, **Cess %** is 10%, **Cess Amount per Unit Factor** is INR 130 and  **Cess Factor Quantity** is 1. An invoice has been issued for INR 10000. In this case cess amount will be INR 1000 which is higher than the quantity multiplied by the Cess Amount per Unit Factor, hence system will consider INR 1000 as Cess Amount.

- GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Quantity**|2|
    |**Unit Amount**|5000|
    |**GST Base Amount**|10000|  
    |**CGST**|900 (10000*9/100)|  
    |**SGST**|900 (10000*9/100)|
    |**IGST**|1800 (10000*18/100)|
    |**CESS**|1000 [{1000=(10000*10/100)} > {260=(130x2)}]|

Suppose, **Cess %** is 5%, **Cess Amount per Unit Factor** is INR 1000 and  **Cess Factor Quantity** is 1. An invoice has been issued for INR 10000. In this case the quantity multiplied by the Cess Amount per Unit Factor is INR 2000 which is higher than the rate defined in Cess%, hence system will consider INR 2000 as Cess Amount.

- GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|
    |**Quantity**|2|
    |**Unit Amount**|5000|
    |**GST Base Amount**|10000|  
    |**CGST**|900 (10000*9/100)|  
    |**SGST**|900 (10000*9/100)|
    |**IGST**|1800 (10000*18/100)|
    |**CESS**|2000 [{2000=(1000x2)} > {500=(10000*5/100)}]|

## Method of calculation for type Amount/Unit Factor

For component calculation type as ‘Amount/Unit Factor’ system will consider Cess value based on values defined GST Group Code in fields **Cess UOM**, **Cess Amount Per Unit Factor** and **Cess Factor Quantity**.

Suppose, **Cess Amount per Unit Factor** is INR 140 and  **Cess Factor Quantity** is 1. An invoice has been issued for INR 10000. In this scenario INR 280 has to be charged.


- GST calculation will appear in the Fact Box, as following:
    
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