---
title: Set up companies to synchronize master data
description: Learn how to set up one or more companies to synchronize master data.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 09/28/2026
ms.custom: bap-template
ms.search.form: 7230, 7233, 5338, 7236, 672, 7234, 7230_Primary, 7233_Primary, 7234_Primary, 7236_Primary
---

# Get ready to synchronize master data

When two or more companies use some of the same master data, you can synchronize the data rather than add it manually in each company. For example, synchronizing data is useful when you're setting up new subsidiary companies.

Master data includes settings and nontransactional information about business entities. For example, customers, vendors, items, and employees. The data provides context for business transactions. The following are a few examples of master data for a customer:

* Name
* Identification number
* Address
* Payment terms
* Credit limit

You set up synchronization in the subsidiary companies. Subidiaries use a pull model to pull the data from the source company that they need to do business with them. After you set up synchronization and synchronize data for the first time, you're all set. Job queue entries update coupled records in the subsidiaries when someone changes data in the source company.

## Uni-directional synchronization only

You can synchronize data only from the source company to the subsidiary companies in a pull fashion. Subsidiaries can't push data to the source company.

> [!NOTE]
> Although it's possible, we don't recommend that you set up bi-directional synchronization. That is, synchronizing data from the source company to the subsidiaries, and from the subsidiaries to the source company. Synchronizing data in both directions can lead to conflicts or unwanted overwrites.

## Before you start

You can synchronize master data in two ways:

* Same environment: the source and subsidiary companies are in the same [!INCLUDE [prod_short](includes/prod_short.md)] environment.
* Across environments: the source company is in a *different* environment in the same Microsoft Entra tenant. This option requires extra setup to create a secure connection. Learn more in [Specify the source company in a cross-environment scenario](#specify-the-source-company-in-a-cross-environment-scenario).

The following are requirements for setting up synchronization.

* All companies must be in the same environment.
* The user who sets up the subsidiary must have the Essential, Premium, or Basic ISV license. Team Member, Internal Administrator, and Delegated Admin licenses can't complete the setup.
* Cross-environment synchronization is available only in [!INCLUDE [prod_short](includes/prod_short.md)] online.
* To set up a cross-environment connection, you also need a Microsoft Entra admin who can access [!INCLUDE [prod_short](includes/prod_short.md)] in the source environment.

> [!NOTE]
> The Team Member and Internal Administrator licenses let you access but not modify records, so they can't be used to set up the synchronization. The Delegated Admin license doesn't let you schedule background tasks, so you can't complete the setup.

## Specify the source company in a single environment scenario

The first steps are to specify the company that is the data source and enable synchronization. Subsidiary companies pull data from the source company.

> [!NOTE]
> When you enable synchronization, [!INCLUDE [prod_short](includes/prod_short.md)] creates and schedules the job queue entries that synchronize the data. It might look like the entries immediately sync the data, but that isn't the case. The created job queue entries only sync coupled records, and at this point you don't yet have coupled records. Synchronization starts after you [Enable or disable tables and fields](#enable-or-disable-tables-and-fields) and [Synchronize for the first time](#synchronize-for-the-first-time).

1. In a subsidiary company, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Master Data Management Setup**, and then choose the related link.
1. In the **Source Company** field, specify the company that you want to pull changes from.
1. Turn on the **Enable Synchronization** toggle.
1. In the confirmation dialog, choose **OK**. [!INCLUDE [prod_short](includes/prod_short.md)] finds the tables and fields that are available from the source company.

The next step is to enable tables and fields for synchronization.

## Specify the source company in a cross-environment scenario

If the source company is in a different environment than the subsidiary, there are a few extra steps to create the connection. The connection uses a registered Microsoft Entra application to read data from the source environment. Because synchronization only connects to environments in the same Microsoft Entra tenant, you register a single-tenant application.

There are three parts:

1. Register an application in Microsoft Entra.
1. Grant the application read access in the source environment.
1. Connect the subsidiary to the source environment.

> [!NOTE]
> Someone who is both a Microsoft Entra tenant admin and has access to Business Central in the source environment must complete steps 1 and 2. Granting admin consent requires tenant admin rights, and enabling the app in the source environment requires Business Central access there.

### Register an application in Microsoft Entra

1. Go to the [Azure portal](https://portal.azure.com/#home), and then choose the Microsoft Entra ID service.
1. Choose **App registrations**, and then **New registration**.
1. Enter a name, such as *Master Data Management Cross-Environment*.
1. For the account type, choose **Accounts** in this organizational directory only (Single tenant).
1. For the redirect URI, choose **Web** as the platform and enter `https://businesscentral.dynamics.com/OAuthLanding.htm`. The redirect URI is used the first time an admin signs in to grant the app access in the source environment.
1. Choose **Register**.
1. On the app's API permissions page, choose **Add a permission**, then **Dynamics 365 Business Central**, then choose **Application permissions**, **API.ReadWrite.All**, and then add the permission.
1. Choose **Grant admin consent** for your organization, and then confirm.
1. On the **Certificates & secrets** page, choose **New client secret**, enter a description and expiry, and then add it.

   > [!IMPORTANT]
   > Copy the value in the secret's **Value** field immediately and store it safely. You can't retrieve it after you leave the page. Enter it in the cross-environment setup. Renew the secret before it expires, or synchronization stops.

1. On the **Overview** page, copy the **Application (client) ID**.

### Grant the application read access in the source environment

Complete these steps in the source environment's [!INCLUDE [prod_short](includes/prod_short.md)]. Sign in with an account that can access [!INCLUDE [prod_short](includes/prod_short.md)] and is a Microsoft Entra tenant admin.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Microsoft Entra Applications**, and then choose the related link.
1. Choose **New**, and in the **Client ID** field, enter the application (client) ID you copied.
1. In the **State** field, select **Enabled**, and then select the **Grant Consent** action. If prompted, sign in with the tenant admin account to grant consent. This sign-in uses the redirect URI from the app registration.
1. Assign the read-only permission set. You can change the permission sets only while the app is disabled, so follow these steps in order:

   1. In the **State** field, choose **Disabled**.
   1. Add the **Master Data Mgt. - Cross Environment** permission set. This read-only permission set lets the app read master data but not change anything in the source.
   1. In the **State** field, choose **Enabled**.

   > [!NOTE]
   > You must disable the app to edit its permission sets and then re-enable it. The permission sets are read-only while the app is enabled.

1. Consent to the cross-environment privacy notice. You're not prompted for it automatically, so consent to it explicitly:

   1. [!INCLUDE [open-search](includes/open-search.md)], enter **Privacy Notices**, and then choose the related link.
   1. Choose the privacy notice for **Master Data Management**, and then consent to it.

### Connect the subsidiary to the source environment

Complete these steps in the subsidiary environment.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Master Data Management Setup**, and then choose the related link.
1. Choose the **Cross-environment setup** action to open the **Cross-Environment Connection Setup** guide.
1. On the **Welcome** step, review and accept the privacy terms, and then choose **Next**.
1. On the connection step, enter the following information:

   * **Source Environment**: the name of the source [!INCLUDE [prod_short](includes/prod_short.md)] environment.
   * **Source Company**: the company in the source environment to read from.
   * **Client ID**: the application (client) ID of the registered app.
   * **Client Secret**: the secret value you copied. It's stored securely and isn't shown again.

1. Choose **Next**, and then optionally choose **Test connection** to verify that you can reach the source.
1. Choose **Finish** to save the connection. You can turn on Enable Data Synchronization right away.

After you set up the connection, the rest of the setup, including enabling tables and fields, coupling, initial synchronization, and import/export is the same as for same-environment synchronization.

To change the source or credentials later, run the **Cross-environment setup** action again. To remove the connection and its stored credentials and return to same-environment synchronization, choose **Clear cross-environment setup**.

## Enable or disable tables and fields

To save time, [!INCLUDE [prod_short](includes/prod_short.md)] provides a list of tables that businesses often synchronize. By default, these tables are enabled for synchronization. You can modify, disable, or delete them as you see fit. As an extra time-saver, some fields on the tables are already disabled because they probably aren't relevant for the subsidiary.

> [!NOTE]
> If one or more extensions are installed in the source company, when a subsidiary sets up synchronization the **Synchronization Tables** page includes tables from the extensions, and you can access their fields. However, if the source company adds an extension after synchronization is set up, each subsidiary must manually add the tables. To learn more about adding tables, go to [Add or delete tables from the synchronization tables list](#add-or-delete-tables-from-the-synchronization-tables-list). To learn more about extending [!INCLUDE [prod_short](includes/prod_short.md)], go to [Developing extensions in Visual Studio Code](/dynamics365/business-central/dev-itpro/developer/devenv-dev-overview#developing-extensions-in-visual-studio-code).

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Master Data Management Setup**, and then choose the related link.
1. Choose the **Synchronization Tables** action.
1. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

   > [!TIP]
> The **Table Filter** field is helpful for controlling what to synchronize for a table. Set up filters to synchronize only when certain conditions are met. For example, you can add filters that specify that you synchronize only vendors in a certain region. Or, customers that use a certain currency.
   >
   > If the subsidiary already has data in their tables, another good way to set criteria for synchronization is to set up match-based coupling. To learn more about matching, go to [Use match-based coupling](#use-match-based-coupling).

1. To enable fields for a table, choose the table, and then choose the **Fields** action.
1. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

> [!TIP]
> A fast way to enable or disable multiple fields at the same time is to select them in the list, and then use either the **Enable** or **Disable** actions.

### Use match-based coupling

You can specify the data to synchronize for a table by matching records based on criteria. On the **Master Data Management Setup** page, choose the **Match-Based Coupling** action to open the **Select Coupling Criteria** page. You can define the following criteria for your matching:

* Whether to synchronize after you couple records.
* Whether to create a new record in the subsidiary company if a unique, uncoupled match can be found by using the match criteria. To activate this capability, turn on the **Create New if Unable to Find a Match** action.
* The fields to use to match records, and whether the match is case-sensitive.
* Prioritize the order in which records are searched by specifying a match priority. [!INCLUDE [prod_short](includes/prod_short.md)] searches for a match in ascending order based on the match priority. A blank value equals priority 0, which is the highest priority. Fields with the 0 priority are considered first.

## Synchronize for the first time

When you're ready, on the **Master Data Management Setup** page, choose the **Start Initial Synchronization** action. On the **Master Data Initial Synchronization** page, choose the type of synchronization that you want to use for each table.

* If you already have records in both the source and the subsidiary companies, and you want to match existing records, choose the **Use Match-Based Coupling** action. [!INCLUDE [prod_short](includes/prod_short.md)] matches records in the subsidiary company with records in the source company. The matches are based on matching criteria that you define. For several default tables, [!INCLUDE [prod_short](includes/prod_short.md)] already matched existing records by using their primary key, but you can change that if you want. You can also let the synchronization create new records in the subsidiary for records in the source company that the subsidiary doesn't have. To learn more about matching, go to [Use match-based coupling](#use-match-based-coupling).
* If you choose **Run Full Synchronization**, synchronization creates new records for all records in the source company that aren't coupled yet. For example, this option is useful in the following scenarios:

    * The subsidiary doesn't have data in the table.
    * You want to add records from the source company without matching.  

After you choose the option to use, choose the **Start All** action to start the synchronization.

While synchronization is running, the **Job Status** column on the **Master Data Initial Full Synchronization** page shows the status of each job queue entry. Press **F5** on your keyboard to update the status.

> [!TIP]
> Tables synchronize in a predefined order. If synchronization is stuck on a table, select the table and then choose the **Restart** action to get it going again.

To access details, such as the number of records that are inserted or modified, choose the value in the **Job Status** column to open the **View - Integration Synchronization Jobs** page. For records that were inserted, you can choose the number in the **Inserted** column to access more details about the new records.

## Add or delete tables from the synchronization tables list

### Add a table

> [!IMPORTANT]
> Although tables that contain transactional data are available in the list, such as tables that contain ledger entries, you shouldn't choose them. Synchronization works only for tables that contain nontransactional data.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Synchronization tables**, and then choose the related link.
1. Choose **New**, and then choose the table to add.
1. If you're prompted to add related tables, consider adding them and respond accordingly.
1. All fields of the added table are disabled. Choose the **Fields** action and enable the synchronization of fields as necessary.
1. Depending on which fields of the main added table you enabled, consider enabling the corresponding related table. For example, if you add the **Item** table and you choose to synchronize the unit of measure fields, consider enabling the synchronization of related unit of measure tables too.

> [!IMPORTANT]
> Cross-environment synchronization only. The **Master Data Mgt. - Cross Environment** permission set grants the registered app read access to the default synchronization tables. If you add tables that aren't in the default set, the app can't read them in the source environment until you grant it access to those tables. Learn more about the steps in [Grant the app access to added tables (cross-environment)](#grant-the-app-access-to-added-tables-cross-environment).

#### Grant the app access to added tables (cross-environment)

When you add tables to synchronize across environments, you must also grant the registered app read access to those tables in the source environment. Do these steps in the source environment, and sign in with an account that can access [!INCLUDE [prod_short](includes/prod_short.md)] and is a Microsoft Entra tenant admin.

1. Create a permission set that grants read access to the tables you added:

   1. [!INCLUDE [open-search](includes/open-search.md)], enter **Permission Sets**, and then choose the related link.
   1. Choose **New**, and give the permission set a name. For example, MDM Additional Tables.
   1. Add `Read` access for each table that you added to the synchronization. Keep the permissions read-only so the app can't change data in the source.

   > [!TIP]
   > Reuse one permission set for all your extra tables. When you add more tables to synchronization later, add them to this same permission set instead of creating a new one each time.

1. Assign the permission set to the registered app. Because you can only change the app's permission sets while the app is disabled, follow these steps in this order:

   1. [!INCLUDE [open-search](includes/open-search.md)], enter **Microsoft Entra Applications**, choose the related link, and then open the registered app.
   1. In the **State** field, choose **Disabled**. 
   1. Add the permission set you created. For example, MDM Additional Tables.
   1. In the **State** field, choose **Enabled**.

   > [!NOTE]
   > If synchronization of an added table fails with an access-denied error from the source environment, confirm the registered app has a permission set that grants read access to that table.

### Delete a table

> [!NOTE]
> If you delete a record in the source company, it isn't also deleted in the subsidiary. Keeping the record in the subsidiary helps prevent unwanted loss of data. The subsidiary can decide to delete the table if they want.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Synchronization tables**, and then choose the related link.
1. Choose the **Delete** action.

## Use export and import to share a synchronization setup

If you're setting up several subsidiaries that use the same or similar synchronization settings, there's a time saver. Set up one subsidiary company and then export its setup to an .xml file. The file contains the entire setup, including table and field mappings and filter criteria. You can then import the file to the next subsidiary. To import or export a setup, on the **Master Data Management Setup** page, use the **Import** or **Export** actions.

## Related information

[Manage Master Data Synchronization](admin-sync-master-data.md)
