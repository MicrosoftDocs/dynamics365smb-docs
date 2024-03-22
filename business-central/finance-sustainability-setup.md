---
title: Sustainability Setup
description: Learn how to setup sustainability features.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD
ms.search.form: 
ms.date: 03/22/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# Sustainability Setup  

To have the Sustainability module working properly, you first need to set up some basic controls and instruction related to whole functionality.  

To set up a sustainability module, follow the next steps:  

1.	Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Setup**, and then choose the related link.  
2.	At the **General** FastTab, configure the next fields related with the basic functionality of module:   

|  Field  |  Description  |  
|--------|--------------| 
| **Emission Unit of Measure Code** | Specifies the unit of measure code that is used to register emission. |
| **Emission Decimal Places** | Specifies the number of decimal places that are shown for emission amounts. The default setting, 2:5, specifies that all amounts are shown with a minimum of 2 decimal places and a maximum of 5 decimal places. You can also enter a fixed number, such as 2, which also means that amounts are shown with two decimals. |
| **Country/Region Mandatory** | Specifies if country/region is mandatory. You can use this field in journals without this configuration, but if select it if you want to enfoce users to populate it before posting. |
| **Responsibility Center Mandatory** | Specifies if responsibility center is mandatory, as the responsibility center can be used as facility for measuring emissions separated from facility to facility. You can use this field in journals without this configuration, but if select it if you want to enfoce users to populate it before posting. |
| **Block Calculation Foundation Change If Ledger Entries Exist** | Specifies if the change of calculation foundation at the Account Category is blocked when sustainability entry where this formula has been used already exists. |
| **Enable Background Error Check** | Specifies if the background error check of sustainability journal lines is enabled. |

3.	At the **Calculations** FastTab configure the next fields related to formulas used for emissions’ calculations:  

|  Field  |  Description  |  
|--------|--------------| 
| **Fuel/Electricity Decimal Places** | Specifies the number of decimal places that are shown for fuel/electricity amounts. The default setting, 2:5, specifies that all amounts are shown with a minimum of 2 decimal places and a maximum of 5 decimal places. You can also enter a fixed number, such as 2, which also means that amounts are shown with two decimals. |
| **Distance Decimal Places** | Specifies the number of decimal places that are shown for distance measurements. The default setting, 2:5, specifies that all amounts are shown with a minimum of 2 decimal places and a maximum of 5 decimal places. You can also enter a fixed number, such as 2, which also means that amounts are shown with two decimals. |
| **Custom Amount Decimal Places** | Specifies the number of decimal places that are shown for custom amounts. The default setting, 2:5, specifies that all amounts are shown with a minimum of 2 decimal places and a maximum of 5 decimal places. You can also enter a fixed number, such as 2, which also means that amounts are shown with two decimals. |

4.	Finish the set up at the **Reporting** FastTab, related to specific reporting to authorities:   

|  Field  |  Description  |  
|--------|--------------| 
| **Emission Reporting Unit of Measure Code** | Specifies the unit of measure code that is used to report emission, as you can use different unit of measure for reporting to authorities. This field is not applicable to the standard reports. |
| **Reporting UOM Factor** | Specifies the unit of measure factor that is used to register emission if you use different unit of measure for reporting to authorities. |
| **Emission Rounding Precision** | Specifies the size of the interval to be used when rounding emission amounts for reporting to authorities purpose. |
| **Emission Rounding Type** | Specifies how the program will round emission amount for reporting to authorities purpose, using options Nearest, Up or Down. |

>[!NOTE]
> In version 24.0 Business Central does not support reporting to any authority. So, configuration fields in the **Reporting** FastTab will be used for future reporting capabilities, but it can be also used by partner localized versions.

## See also  
[Finance](finance.md)    
[Sustainability management overview](finance-manage-sustainability.md)
[Chart of Sustainability Accounts and Ledger](finance-sustainability-accounts-ledger.md)
[How to record emissions](finance-sustainability-journals.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
