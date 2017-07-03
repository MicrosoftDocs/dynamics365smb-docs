---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# User-Defined Method
The program has a facility that allows you to set up user-defined depreciation methods.  
  
 With a user-defined method, you use the **Depreciation Tables** window, where you must enter a depreciation percentage for each period (month, quarter, year, or accounting period).  
  
 The formula for calculating the depreciation amounts is:  
  
 Depreciation Amount = (Depreciation % * Number of Depreciation Days * Depr. Basis) / (100 * 360)  
  
## Depreciation Based on Number of Units  
 This user-defined method can also be used to depreciate based on number of units, for example, in the case of production machines with an established lifetime capacity. In the **Depreciation Tables** window, you can enter the number of units that can be produced in each period (month, quarter, year, or accounting period).  
  
 For an example, see [Example - User-Defined Depreciation Method](../example-user-defined-depreciation-method.md) for more information.  
  
## See Also  
 [How to: Set Up User-Defined Depreciation Methods](../how-to-set-up-user-defined-depreciation-methods.md)   
 [Depreciation Methods](../depreciation-methods.md)   
 [Depreciate or Amortize Assets](../depreciate-or-amortize-assets.md)   
 [Set Up Depreciation](../set-up-depreciation.md)