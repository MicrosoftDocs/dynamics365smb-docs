---
title: Chart of sustainability accounts and ledger
description: Learn how to manage Chart of Sustainability Accounts, Categories, and Subcategories and details about Sustainability Ledger Entries.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, CoA, Chart, Account, Ledger
ms.search.form: 6210, 6213, 6214, 6220
ms.date: 04/02/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# Chart of sustainability accounts and ledger 

## Chart of sustainability accounts  

The **Chart of Sustainability Accounts** (CoSA) forms the foundational structured list used for recording all emissions data. It functions as a framework that categorizes and organizes sustainability accounts based on their attributes, such as scope or other groupings. Each account is typically assigned a unique code or number for easy reference and tracking, following the same structure as a traditional **Chart of Accounts** but customized specifically for monitoring sustainability-related data and metrics within an organization. 
 
Users can add **Account Categories** and **Subcategories** to define how the system behaves, selecting dedicated emissions for tracking, emission factors, formulas, and similar configurations.  

>[!NOTE]
>To be familarized with scopes, based on the GHG (Greenhouse gases) standards, there are three emissions scopes:  
>- **Scope 1 emissions**: include emissions that are emitted from stationery and mobile combustion, and from inadvertent fugitive emissions. 
>- **Scope 2 emissions**: include indirect emissions from the generation of energy that is purchased from utility providers. 
>- **Scope 3 emissions**: include a wide spectrum of emissions, from purchased goods, and services and capital goods, fuel and energy related activities, upstream and downstream transportation, generated waste, business travel and employee commuting, etc. 

From the **Chart of Sustainability Accounts** (CoSA), you can do things like:  

-	View reports that show sustainability ledger entries and balances. 
-	Open the **Sustainability Account Card** to add or change settings.  
-	See the category and subcategory for that account.   
-	View separate balances for each of the emissions for a single account. 
-	Add single or multiple **Dimensions** to each of the accounts and set dimension filter. 
	
You can add, change, or delete **Sustainability Accounts**. However, to prevent discrepancies, you can't delete a **Sustainability Account** if there are one or more ledger entries associated with this account.  

### Add or change accounts  

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Sustainability Accounts**, and then select the related link. 
2. On the **Chart of Sustainability Accounts** (CoSA) page, you can open each **Sustainability Account**, and then add or change settings. Hover over a field to read a short description. 

For accounts of the **Total** account type, you must fill in the **Totaling** field. For **End-Total** accounts, this field is filled in automatically by the Indent function. After you have set up all the accounts, choose the **Indent Chart of Sustainability Accounts** action to do that.  

>[!IMPORTANT]
>If you have entered definitions in the **Totaling** fields for **End-Total** accounts before executing the indent function, you must enter them again because the function overwrites the values in all **End-Total** fields.  

### Delete accounts  

You can delete a **Sustainability Account**. However, before you delete it, you must be sure that there are one or more ledger entries associated with this account, as Business Central will prevent you from deleting a **Sustainability Account** in this situation.  

## Account categories   

Users need to add the **Sustainability Account Category** to each of **Sustainability Accounts**, to define how the system behaves, selecting emission scopes, dedicated emissions for tracking, formulas, and similar configurations.  

To review **Sustainability Account Categories**, follow the steps: 

1.	Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Account Categories**, and then select the related link. 
2.	On the **Sustainability Account Categories** page, you can edit the existing list or create a new category. For creating new category, select the **New** action.  
3.	Fill in the **Code** and **Description** fields.   
4.	Set up the **Emission Scope** field, choosing one of scope options.  
5.	Select the gas emissions that you want to track. Currently, you can use one of the options: **CO2**, **CH4**, or **N2O**. You can choose any combination that you want to track, but, you must have minimum one emission for tracking.  
6.	In the **Calculation Foundation** field, you can choose any one of formulas that you want to use, in case you don't know the accurate emission amount. Here, you can specify the calculation foundation (formula) for emission calculation. You can choose one of the following options: **Fuel/Electricity**, **Distance**, **Installation**, or **Custom**. 
7.	If you choose **Custom** formula, you can configure custom description in the **Custom Value** field.  

>[!NOTE]
>If this set of offered formulas in the **Calculation Foundation** field is not enough, you can extend this field and add more calculations to the system to be used in the **Sustainability Journals**.  

If you use the **Calculation Foundation** (formulas), there's an explanation, how system will calculate based on the option you have chosen (**EF** is the **Emission Factor** that you can configure in the **Sustainability Account Subcategory** page): 

|  Emission Type  |  Calculation Foundation  |  Formula         | Comment      |
|------------|--------------|------------------------------|---------------------------------|
| **SCOPE 1**  |
| Stationary combustion | Fuel/Electricity | Emission = Fuel * EF | _i.e.,  Fuel = Amount of fuel spent for Boilers, Heaters, Thermal oxidizers..._ |
| Mobile combustion | Fuel/Electricity | Emission = Fuel * EF | _i.e.,  Fuel = Amount of fuel spent for on-road or non-road vehicles, rail..._ |
|  |  |  Emission = Distance * EF | _i.e.,  Distance = Milleage of on-road or non-road vehicles, rail..._ |
| Fugitive emissions | Installation | Emission = Installation multiplier * Custom Amount / 100 * Time Factor | _i.e.,  Custom Amount = Assembly losses, Annual leak rate..._ |
| **SCOPE 2**  |
| Utillity providers | Fuel/Electricity | Emission = Electricity * EF | _i.e., Fuel/Electricity = Electricity quantity, Steam quantity, Heating unit..._ |
|  | Custom | Emission = Custom Amount * EF | _i.e., Custom Amount = Thermal unit, Ton-hour..._ |
| **SCOPE 3**  |
| Purchased goods and services, and capital goods | Custom | Emission = Custom Amount * EF | _i.e., Custom Amount = Cost (GL)..._ |
| Upstream transportation and distribution | Distance | Emission = Distance * EF |  |
|  | Distance | Emission = Distance * Multiplier * EF | _Multiplier = Toins of cargo_ |
| Downstream transportation and distribution | Distance | Emission = Distance * EF |  |
|  | Distance | Emission = Distance * Multiplier * EF | _Multiplier = Toins of cargo_ |
| Waste generated in operations and end-of-life treatment of sold products | Custom | Emission = Custom Amount * EF | _i.e., Custom Amount = Waste_ |
| Business travel and employee commuting | Distance | Emission = Distance * EF | _i.e., Distance = Milleage of the used company car, rental car, train, flight..._ |
|  | Custom | Emission = Custom Amount * EF | _i.e., Custom Amount = Hotel stays..._ |
|  | Fuel/Electricity | Emission = Fuel * EF | _i.e., Fuel = Amount of fuel spent in the company car, rental car..._ |

## Account subcategories  

Users need to add the **Sustainability Account Subcategory** to each of **Sustainability Accounts** to define emission factors that will be used in the formulas, but it's based on the emission tracking choice in the **Sustainability Account Category**.  

To review **Sustainability Account Subcategories**, follow the steps:  

1.	Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Account Subcategories**, and then select the related link. 
2.	On the **Sustainability Account Subcategories** page, you can edit the existing list or create a new category. For creating new category, select the **New** action.  
3.	Fill in the **Code** and **Description** fields.   
4.	Based on the gas emissions that you want to track in the **Sustainability Account Category**, and connect this subcategory with, you can also populate one or more emission factors: 

   - **Emission Factor CO2** - Specifies the emission factor for CO2 emission.  
   - **Emission Factor CH4** - Specifies the emission factor for CH4 emission. 
   - **Emission Factor N2O** - Specifies the emission factor for N2O emission.  

5.	If this subcategory is related to renewable energy, select the **Renewable Energy** field.   

>[!NOTE]
>**Import Data** and **Import From** fields are intended for potential integration with external systems that are used for collecting emission factors, but in **2024 release wave 1** they cannot be used as a feature by default.  

## Sustainability Ledger Entries  

**Sustainability Ledger** stores the history of all posted sustainability transactions, organizing all emission data according to the **Chart of Sustainability Accounts**. When a user posts the **Sustainability Journal**, all crucial data will be recorded there. All active reports are generated based on the **Sustainability Ledger Entries**.   

User can open this ledger for one specific account using the **Ledger Entries** action from the **Chart of Sustainability Account** page or, to open all the ledger entries, select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Ledger Entries**, and then select the related link. Hover over a field to read a short description.  

>[!IMPORTANT]
>Once you post your data into the Sustainability Ledger, you cannot delete them. In case you made a mistake, you can post the reverse trasaction using the same details, but using the negative sign for amount.  

## See also  
[Finance](finance.md)    
[Sustainability management overview](finance-manage-sustainability.md)
[Sustainability Setup](finance-sustainability-setup.md)
[How to record emissions](finance-sustainability-journal.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
