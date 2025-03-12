---
title: Chart of sustainability accounts and ledger
description: Learn how to manage the chart of sustainability accounts, categories and subcategories, and details about sustainability ledger entries.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, CoA, Chart, Account, Ledger
ms.search.form: 6210, 6213, 6214, 6220
ms.date: 01/30/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Chart of sustainability accounts and ledger

This article explains how to manage the chart of sustainability accounts (CoSA), categories and subcategories, and details about sustainability ledger entries.

## Chart of sustainability accounts

The CoSA forms the foundational structured list that is used to record all emissions, water, and waste data. It serves as a framework that categorizes and organizes sustainability accounts based on their attributes, such as the scope or other groupings. Each account is typically assigned a unique code or number for easy reference and tracking. It has the same structure as a traditional chart of accounts but is customized specifically to monitor sustainability-related data and metrics in an organization.  

Users can add sustainability account categories and sustainability account subcategories to define how the system behaves. In this way, they can select dedicated emissions, water, or waste for tracking, emission factors, formulas, and similar configurations.

> [!NOTE]
> Based on the greenhouse gas (GHG) standards, there are three emission scopes:
>
> - **Scope 1 emissions** include emissions from stationary and mobile combustion, and from inadvertent fugitive emissions.
> - **Scope 2 emissions** include indirect emissions from the generation of energy that is purchased from utility providers.
> - **Scope 3 emissions** include a wide spectrum of emissions, from purchased goods and services and capital goods, to fuel and energy–related activities, to upstream and downstream transportation, to generated waste, to business travel and employee commuting, and so on.
> - **Out of scope** is for situations where you can't assign a specific emission to the transaction.

> [!NOTE]
> You can also select **Water/Waste** as one of options in the **Emission Scope** when they want to post transactions related to the water and waste management.  

From the CoSA, you can do things such as:

- View reports that show sustainability ledger entries and balances.
- Open the sustainability account card to add or change settings.
- View the category and subcategory for the account.
- View separate balances for each emission for a single account.
- Add single or multiple dimensions to each account and set dimension filters.

You can add, change, or delete sustainability accounts. However, to prevent discrepancies, you can't delete a sustainability account if one or more ledger entries are associated with it.

### Add or change accounts

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Sustainability Accounts**, and then select the related link.
2. On the **Chart of Sustainability Accounts** page, you can open each sustainability account, and then add or change settings. Hover over a field to read a short description.

For accounts of the **Total** account type, you must set the **Totaling** field.

For accounts of the **End-Total** type, the **Indent** action automatically sets the **Totaling** field. After you set up all the accounts, select the **Indent Chart of Sustainability Accounts** action to run the **Indent** action and set the **Totaling** field.

> [!IMPORTANT]
> The **Indent Chart of Sustainability Accounts** action overwrites the value of all fields for **End-Total** accounts. Therefore, if you entered definitions in the **Totaling** field for **End-Total** accounts before you ran the **Indent Chart of Sustainability Accounts** action, you must enter them again after you run it.  

### Delete accounts

You can delete a sustainability account. However, you must first make sure that no ledger entries are associated with it. Business Central prevents you from deleting a sustainability account if one or more ledger entries are associated with it.

## Account categories

You must add a sustainability account category to each sustainability account to define how the system behaves. You can select emission scopes (gas, water, or waste), dedicated to type of transaction to track, formulas, and similar configurations.  

To review sustainability account categories, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Account Categories**, and then select the related link.
2. On the **Sustainability Account Categories** page, you can edit the existing list or create a new category. To create a new category, select the **New** action.
3. Fill in the **Code** and **Description** fields.
4. In the **Emission Scope** field, select one of the scope options related to gas emissions or water or waste intensity.
5. Select the gas emissions, or water or waste intensity, that you want to track. Currently, the following options are available: **CO2**, **CH4**, **N2O**, **Water Intensity**, **Discharged Into Water**, and **Waste Intensity**. You can select any combination that you want to track, but you must select at least one of them.

    > [!NOTE]
    > If you choose one of gas emissions scopes as the **Emission Scope** you can select the **CO2**, **CH4**, or **N2O**, but you can't select the **Water Intensity**, **Discharged Into Water**, or **Waste Intensity**. Also, if you select **Water/Waste** as the **Emission Scope**, you can select only the  **Water Intensity**, **Discharged Into Water**, or **Waste Intensity**, but you can't select **CO2**, **CH4**, or **N2O**.

6. In the **Calculation Foundation** field, select the calculation foundation (formula) to use for emission calculations if you don't know the accurate emission or water or waste intensity amount.

    > [!NOTE]
    > If the formulas in the **Calculation Foundation** field aren't enough, you can extend the field and add more calculations for use in sustainability journals.

7. If you selected **Custom** in the **Calculation Foundation** field, you can configure a custom description in the **Custom Value** field.

If you set the **Calculation Foundation** field, the following table explains how [!INCLUDE [prod_short](includes/prod_short.md)] calculates emissions based on the option that you selected. In the table, **EF** represents the **Emission Factor** value that you can configure on the **Sustainability Account Subcategory** page.

| Emission Type | Calculation Foundation | Formula | Comment |
|---------------|------------------------|---------|---------|
| **Scope 1** | | | |
| Stationary combustion | Fuel/Electricity | *Emission* = *Fuel* &times; *EF* | *Fuel* = Amount of fuel that is spent for boilers, heaters, thermal oxidizers, and so on. |
| Mobile combustion | Fuel/Electricity | *Emission* = *Fuel* &times; *EF* | *Fuel* = Amount of fuel that is spent for on-road or off-road vehicles, rail, and so on. |
| | | *Emission* = *Distance* &times; *EF* | *Distance* = Mileage of on-road or off-road vehicles, rail, and so on. |
| Fugitive emissions | Installation | *Emission* = *Installation multiplier* &times; *Custom Amount* &divide; 100 &times; *Time Factor* &times; *EF* | *Custom Amount* = Assembly losses, annual leak rate, and so on. |
| **Scope 2** | | | |
| Utility providers | Fuel/Electricity | *Emission* = *Electricity* &times; *EF* | *Fuel/Electricity* = Electricity quantity, steam quantity, heating unit, and so on. |
| | Custom | *Emission* = *Custom Amount* &times; *EF* | *Custom Amount* = Thermal unit, ton-hour, and so on. |
| **Scope 3** | | | |
| Purchased goods and services, and capital goods | Custom | *Emission* = *Custom Amount* &times; *EF* | *Custom Amount* = Cost (GL), and so on. |
| Upstream transportation and distribution | Distance | *Emission* = *Distance* &times; *EF* | |
| | Distance | *Emission* = *Distance* &times; *Multiplier* &times; *EF* | *Multiplier* = Load Factor / Tons of cargo *|
| Downstream transportation and distribution | Distance | *Emission* = *Distance* &times; *EF* | |
| | Distance | *Emission* = *Distance* &times; *Multiplier* &times; *EF* | *Multiplier* = Load Factor / Tons of cargo *|
| Waste generated in operations and end-of-life treatment of sold products | Custom | *Emission* = *Custom Amount* &times; *EF* | *Custom Amount* = Waste |
| Business travel and employee commuting | Distance | *Emission* = *Distance* &times; *EF* | *Distance* = Mileage of the used company car, rental car, train, flight, and so on. |
| | Custom | *Emission* = *Custom Amount* &times; *EF* | *Custom Amount* = Hotel stays |
| | Fuel/Electricity | *Emission* = *Fuel* &times; *EF* | *Fuel* = Amount of fuel spent in the company car, rental car, and so on. This is the only formula used for water or waste intensity calculation. |

> [!IMPORTANT]
> This note applies to the formulas for **Upstream Transportation and Distribution** and **Downstream Transportation and Distribution** when you use the tons-of-cargo calculation model. While you can adapt the formulas, we recommend against using the exact number of tons of cargo as a multiplier. Instead, consult your sustainability advisor to ensure accurate calculations because emissions don't increase linearly with weight. A more accurate approach is to use the **Load Factor**, which represents the percentage of the truck's total capacity utilized (by weight or volume). The load factor can be calculated as **Weight of Cargo** / **Maximum Load Capacity of Truck**. But always confirm with your sustainability expert before you finalize calculations.

## Account subcategories

You must add a sustainability account subcategory to each sustainability account. This subcategory defines the emission factors that the formulas use, based on the emission tracking choice in the sustainability account category.

To review sustainability account subcategories, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Account Subcategories**, and then select the related link.
2. On the **Sustainability Account Subcategories** page, you can edit the existing list or create a new category. To create a new category, select the **New** action.
3. Fill in the **Code** and **Description** fields.
4. Based on the gas emissions that you track in the sustainability account category and connect this subcategory to, you can also set one or more emission factors:

    - **Emission Factor CO2** – The emission factor for carbon dioxide (CO<sub>2</sub>) emission.
    - **Emission Factor CH4** – The emission factor for methane (CH<sub>4</sub>) emission.
    - **Emission Factor N2O** – The emission factor for nitrous oxide (N<sub>2</sub>O) emission.
    - **Water Intensity Factor** - The intensity factor for Water.
    - **Discharged Into Water Factor** - The intensity factor for Discharged Into Water.
    - **Waste Intensity Factor** - The intensity factor for Waste.

5. If the subcategory is related to renewable energy, select the **Renewable Energy** field. However, you can select this field only if it's related to gas emissions and to water or waste.  

> [!NOTE]
> The **Import Data** and **Import From** fields are intended for integration with external systems that are used to collect emission factors. However, in **2024 release wave 1**, these fields can't be used as a feature by default.

You can have more than one account subcategory for a sustainability account, but only one can be set as the default value. You must set the default value for the account every time if you want to use it for posting.  

> [!TIP]
> For example, if you want to use one account for cars, but you have different types of cars with different emission factors. You can set up one account and create account subcategories for the different emission factors. When you work in a sustainability journal, you can change your account subcategory based on the car type.  

## Sustainability ledger entries

The sustainability ledger stores the history of all posted sustainability transactions and organizes all emission data according to the CoSA. When you post a sustainability journal, the data is recorded there. All active reports are generated based on the sustainability ledger entries.

To open this ledger for a specific account, use the **Ledger Entries** action on the **Chart of Sustainability Account** page. To open all the ledger entries, select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Ledger Entries**, and then select the related link. Hover over a field to read a short description.

> [!IMPORTANT]
> After you post your data to the sustainability ledger, you can't delete it. If you made a mistake, you can post a reverse transaction that has the same details but uses the negative sign for the amount.

> [!NOTE]
> If you posted entries before enabling **CO<sub>2</sub>e** in the **Emission Fees** page, you can run the **Update Carbon Fees** action from the **Emission Fees** page to recalculate carbon equivalent to in all transactions in the **Sustainability Ledger Entries**.  

## Related information

[Finance](finance.md)  
[Sustainability management overview](finance-manage-sustainability.md)  
[Sustainability Setup](finance-sustainability-setup.md)  
[How to record emissions](finance-sustainability-journal.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
