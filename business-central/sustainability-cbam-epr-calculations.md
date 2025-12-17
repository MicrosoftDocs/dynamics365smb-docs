---
title: Use CBAM and EPR calculations
description: Learn how to calculate carbon-related costs based on the origin of your products and carbon pricing rules in the European Union.
author: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, carbon, credit, CO2
ms.search.form: 
ms.date: 12/17/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Use CBAM and EPR calculations

[!INCLUDE [prod_short](includes/prod_short.md)] offers support for the European Union's (EU) Carbon Border Adjustment Mechanism (CBAM) by helping you track and manage the carbon footprint of the goods you purchase and import from outside the EU. You can automatically calculate carbon-related costs based on the origin of your products and EU carbon pricing rules by using the **Carbon Pricing** page and fields on the **Item Card** page, such as:

- **Source of Emission Data**
- **Emission Verified**
- **CBAM Compliance**

[!INCLUDE [prod_short](includes/prod_short.md)] monitors emission data, verifies compliance, and ensures that all purchases reflect the required carbon adjustments. This mechanism helps you avoid regulatory risks and gives you clear insight into your sustainability costs for each product and vendor.

Use the Extended Producer Responsibility (EPR) feature to track product materials and apply the right environmental fees to the items you produce or sell. Whether your products include packaging, electronics, or batteries, the system calculates fees for things like collection and recycling based on the material composition and their weights. To set up this feature, use the **EPR Material Setup** and **Item Material Composition** pages, along with extra fields on the **Item Card** page and sales documents. These tools help you comply with local regulations, improve cost accuracy, and support environmentally responsible product design and reporting.

## Prerequisites

There are a few things to set up before you start using CBAM or EPR.

For CBAM, set up the following:

- Carbon pricing. Learn more at [Set up carbon pricing](#set-up-carbon-pricing).
- Items. Learn more at [Set up items for CBAM](#set-up-items-for-cbam).
- An excise journal batch where the type is **CBAM**.

For EPR, set up the following:

- EPR materials. Learn more at [Set up EPR materials](#set-up-epr-materials).
- Item material composition. Learn more at [Set up item material composition for EPR](#set-up-item-material-composition-for-epr).
- Items
- An excise journal batch where the type is **EPR**.

## Built on excise taxes framework

Both the CBAM and EPR features use the **Excise Taxes** framework to enable the necessary calculations. However, these features don't support all documents that some authorities require. 

## Set up CBAM

The following sections describe the setups that must be in place to use the CBAM features, and how to calculate CBAM entries. 

### Set up carbon pricing

1. On the **Carbon Pricing** page, in **Country/Region of Origin** field, specify a country that is outside the EU from which you import goods. Create a new line for each country.
1. In the **Starting Date** and **Ending Date** fields, enter the first and last date of the period for which you want to specify carbon prices.
1. In the **Unit of Measure Code** field, specify the measure to which the carbon price applies.
1. In the **Threshold Quantity** field, the minimum quantity for which you report carbon prices. Quantities below this threshold aren't included in the report.   
1. In the **Rounding Type** field, specify how you want to round integers to the nearest whole number.

### Set up items for CBAM

1. Open the **Item Card** page for an item, and expand the **Sustainability** FastTab
1. In the **Default Sust. Account** field, select the general ledger account to which you post sustainability values.
1. In the **Default CO2e for CO2 Emissions**, **Default CO2e for CH4 Emissions**, and **Default CO2e for N20 Emissions** fields, specify the minimum amounts to use for each gas.

   > [!NOTE]
   > You can specify values for each type of gas, but only CO2 is required.

1. In the **Source of Emission Data** field, specify where your data is verified.
1. To specify that your emissions data is verified, turn on the **Emissions Verified** toggle.
1. To specify that your emissions data is compliant, turn on the **CBAM Compliance** toggle. Calculation includes only items that are CBAM compliant.

### Post your CBAM entries

1. Open the **Purchase Invoice** page for a purchase invoice. 
1. For each relevant line, choose the **Emissions Verified** and **CBAM Compliant** checkboxes.
1. Post the document.
1. Open the **Excise Journal** page. 
1. In the **Journal Batch Name** field, select the batch that you created for CBAM.
1. To create lines in the journal, choose the **Calculate** action, and then confirm.

  > [!TIP]
  > To determine the country of origin, [!INCLUDE [prod_short](includes/prod_short.md)] uses the value from the item first. If one isn't specified for the item, it uses the value from the vendor.  

1. Choose the **Register** action, and then confirm.

   > [!TIP]
   > After you register your CBAM entries, you can use the **Excise Taxes Transaction Logs** page to review them. You can export the list for reporting.

## Set up EPR and its calculation

The following sections describe the setups that must be in place to use the EPR features, and how to calculate EPR entries. 

### Set up EPR materials

The set up for EPR materials is simple. On the **EPR Materials** page, create a new line for each type of material. Specify a unit of measure for each material, and the EPR fee rate that you use for that measure of the material. Finally, specify the date from which the rate is effective.

### Set up item material composition for an item for EPR

Material composition is similar to a bill of materials. It's a list of the materials that make up an item, the weights of the materials, and the collection fee to charge for each material. [!INCLUDE [prod_short](includes/prod_short.md)] uses this information to calculate EPR fees.

1. Open the **Item Card** page for a relevant item.
1. In the **EPR Category** field, select an EPR category.

   > [!NOTE]
   > EPR categories are predefined, and might not apply to all items.

1. In the **Material Composition No.** field, select the drop-down, and then choose **+New**.
1. On the **Item Material Composition** page, on the **General** FastTab, enter information about the item.
1. On the **Lines** FastTab, in the **Material Type No.** field, select a material.
1. In the **Weight** field, specify the weight of the material in the unit of measure you specify in the next step.
1. In the **Unit of Measure Code** field, specify the measure you use for the material.
1. In the **EPR Fee Rate** field, specify the fee you charge for the material in the unit of measure.  
1. Optional: You can also specify additional fees for collection, sorting, administration, and environmental.
1. In the **Status** field, select **Certified**, and then choose **OK**.
1. On the **Item Card** page, on the **Sustainability** FastTab, the following fields show the calculated values for the item:

   - **Material Composition No.**
   - **Total EPR Weight**
   - **EPR Fees Per Unit**

1. Optional: If you must report your method of disposal for the item, enter a short description of 50 characters or less in the **End-of-Life Disposal Requirement** field. 

### Post your EPR entries

1. Open the **Sales Invoice** page for a relevant invoice.
1. [!INCLUDE [prod_short](includes/prod_short.md)] automatically fills in the **Total EPR Fee** on sales invoice lines that contain the item.
1. Post the invoice.
1. 1. Open the **Excise Journal** page. 
1. In the **Journal Batch Name** field, select the batch that you created for EPR.
1. To create lines in the journal, choose the **Calculate** action, and then confirm.
1. Choose the **Register** action, and then confirm.

   > [!TIP]
   > After you register your EPR entries, you can use the **Excise Taxes Transaction Logs** page to review your CBAM entries. You can export the list for reporting.

## Related information

[Sustainability management overview](finance-manage-sustainability.md)  


