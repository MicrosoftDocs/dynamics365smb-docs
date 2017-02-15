---
title: 'How to: Update Currency Exchange Rates | Microsoft Docs'
description: Working with multiple currencies
services: project-madeira
documentationcenter: ''
author: edupont04

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/16/2017
ms.author: edupont

---
# How to: Update Currency Exchange Rates
You must set up a code for each currency you use if you buy or sell in currencies other than your local currency, have receivables or payables in other currencies, or record G/L transactions in different currencies.  

**Note**: This functionality requires that your experience is set to **Suite**. For more information, see [Customizing Your [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] Experience](ui-experiences.md).

You can use an external service to keep your currency exchange rates up to date. The Yahoo Currency Exchange Rates service is preinstalled and ready to enable.

## To set up a currency exchange rate service
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Currency Exchange Rate Services**, and then choose the related link.
2. Choose the **New** action.
3. In the **Currency Exchange Rate Service** window, fill in the fields as necessary. Choose a field to read a short description of the field or link to more information.
4. Choose the **Enabled** check box to enable the service.

## To update currency exchange rates through a service
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Currencies**, and then choose the related link.
2. Choose the **Update Exchange Rates** action.

The value in the **Exchange Rate** field in the **Currencies** window is updated with the latest currency exchange rate.

## See Also
[Closing Years and Periods](year-close-years-periods.md)  
[Working With [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](ui-work-product.md)
