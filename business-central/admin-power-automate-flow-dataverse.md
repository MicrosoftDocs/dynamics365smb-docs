---
title: Use a Power Automate flow to timely synchronize Dataverse entity changes
description: Learn how to create a flow in Power Automate that will alert you when an entity is changed in Dataverse environment. 
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Power Automate, Flow, Dataverse
ms.search.form: 
ms.date: 09/05/2022
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Use a Power Automate flow to timely synchronize Dataverse entity changes

Administrators can create an automated flow in Power Automate that notifies your [!INCLUDE[prod_short](includes/prod_short.md)] about changes to records in your [!INCLUDE [cds_long_md](includes/cds_long_md.md)] organization.

> [!NOTE]
> This article assumes you've connected your online version of [!INCLUDE[prod_short](includes/prod_short.md)] with [!INCLUDE [cds_long_md](includes/cds_long_md.md)] and scheduled synchronization between the two applications.

## Import the Flow Template

> [!TIP]
> To make it easier to set up the flow, we've created a template that will define the flow trigger and flow condition for you. To use the template, follow the steps in this section. To create the flow yourself, skip this section and start with the steps in [Define the Flow Trigger](#define-the-flow-trigger).

1. Sign in to [Power Automate](https://powerautomate.microsoft.com).
2. Choose **Templates**, and then search for **Notify Business Central**.

:::image type="content" source="media/power-automate-import-template.png" alt-text="Keywords to find the flow template.":::
3. Choose the **Notify Business Central when an account changes** template.
4. Continue with the steps in the [Notify Business Central about a change](#notify-business-central-about-a-change) section.

## Define the Flow Trigger

1. Sign in to [Power Automate](https://flow.microsoft.com).
2. Create an automated cloud flow that starts when a row for a [!INCLUDE [cds_long_md](includes/cds_long_md.md)] entity is added, modified, or deleted. For more information, see [Trigger flows when a row is added, modified, or deleted](/power-automate/dataverse/create-update-delete-trigger). This example uses the **Accounts** entity. The following image shows the settings for the first step in defining a flow trigger.

:::image type="content" source="media/power-automate-flow-dataverse-trigger.png" alt-text="Settings for the flow's trigger":::
3. Use the **AssistEdit (...)** button in the upper right corner to add the connection to your [!INCLUDE [cds_long_md](includes/cds_long_md.md)] environment.
4. Choose **Show advanced options**, and in the **Filter Rows** field, enter **customertypecode eq 3** or **customertypecode eq 11** and **statecode eq 0**. These values mean that the trigger will react only when changes are made to active accounts of the type **customer** or **vendor**.

## Define the Flow Condition

Data is synchronized between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE [cds_long_md](includes/cds_long_md.md)] through an integration user account. To ignore the changes made by the synchronization, create a condition step in your flow that excludes changes made by the integration user account.  

1. Add a **Get a row by ID from Dataverse** step after the flow trigger with the following settings. For more information, see [Get a row by ID from Dataverse](/power-automate/dataverse/get-row-id).

    1. In the **Table name** field, choose **Users**
    2. In the **Row ID** field, choose the **Modified By (Value)** from the flow trigger.  

2. Add a condition step with the following **or** settings to identify the integration user account.
    1. The user's **Primary Email Address** contains **contoso.com**
    2. The user's **Full Name** contains **[!INCLUDE[prod_short](includes/prod_short.md)]**.

3. Add a Terminate control to stop the flow if the entity was changed by the integration user account.

The following image shows how to define the flow trigger and the flow condition.

:::image type="content" source="media/power-automate-flow-dataverse.png" alt-text="Overview of flow trigger and condition settings":::

## Notify Business Central About a Change

If the flow isn't stopped by the condition, you must notify [!INCLUDE[prod_short](includes/prod_short.md)] that a change occurred. Use the [!INCLUDE[prod_short](includes/prod_short.md)] Connector to do that.

1. In the **No** fork of the condition step, add an action and search for **Dynamics 365 [!INCLUDE[prod_short](includes/prod_short.md)]**. Choose the connector icon in the list.
2. Choose the **Create record (V3)** action.

:::image type="content" source="media/power-automate-flow-dataverse-connector.png" alt-text="Settings for the [!INCLUDE[prod_short](includes/prod_short.md)] Connector":::

3. Use the **assist edit (...)** button in the upper right corner to add the connection to your [!INCLUDE[prod_short](includes/prod_short.md)].
4. When connected, fill in the **Environment name** and **Company name** fields.
5. In the **API category** field, enter **microsoft/dataverse/v1.0**.
6. In the **Table name** field, enter **dataverseEntityChanges**.
7. In the **entityName** field, enter **account**.
8. Save the flow.

The following image shows how your flow should look.

:::image type="content" source="media/power-automate-flow-dataverse-summary.png" alt-text="Overview of all settings for the flow":::

When you add, delete, or modify an account in your [!INCLUDE [cds_long_md](includes/cds_long_md.md)] environment, this flow will do the following actions:

1. Call the [!INCLUDE[prod_short](includes/prod_short.md)] environment that you specified in the [!INCLUDE[prod_short](includes/prod_short.md)] Connector.
2. Use the [!INCLUDE[prod_short](includes/prod_short.md)] API to insert a record with the **entityName** set to **account** in the **Dataverse Entry Change** table. This parameter is the exact name of the Dataverse entity that you're creating the flow for.
3. [!INCLUDE[prod_short](includes/prod_short.md)] will start the job queue entry that synchronizes customers with accounts.

## Related information

[Use Business Central in Power Automate Flows](across-how-use-financials-data-source-flow.md)  
[Set Up Automated Workflows](/dynamics365/business-central/dev-itpro/powerplatform/automate-workflows)  
[Integrating with Microsoft Dataverse](admin-common-data-service.md)  
[Synchronizing Data in Business Central with Microsoft Dataverse](admin-synchronizing-business-central-and-sales.md)  
