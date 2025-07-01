---
title: Set Up intercompany transaction posting
description: Learn how to set up an intercompany partnership. 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 09/19/2024
ms.custom: bap-template
ms.search.keywords: IC, group, consolidation, affiliate, subsidiary
ms.search.form: 605, 613, 617, 620, 602, 603, 601, 600, 652, 653, 606, 607, 609, 608, 621, 653_Primary
ms.service: dynamics-365-business-central
---
# Set up intercompany transactions

Intercompany partnerships make it easier to handle accounting processes when two or more subsidiaries of a company frequently do business with each other. Partners can exchange transactions, such as sales and purchases, and handle them either manually or automatically. For example, when a partner sends a sales journal line to another partner, a purchase journal line is created for the receiving partner.

The intercompany chart of accounts can be, for example, a version of the synchronization partner's chart of accounts. Each partner maps their accounts to the intercompany chart of accounts. Each partner also maps their dimensions and dimension values to the intercompany dimensions.

## Before you start

Before you start to set up your intercompany partnership, there are a few decisions to make.

|Decision  |Description  |
|---------|---------|
|Which chart of accounts should be the basis for the intercompany chart of accounts?     | All companies in the partnership must use the same intercompany chart of accounts. You can base your intercompany chart of accounts on the chart of accounts from one of the companies in the partnership, or create a new intercompany chart of accounts. You map the accounts to use in the partnership in both ways, so that each partner both sends and receives transactions in the correct accounts. Learn more about setting up the intercompany chart of accounts at [Set up the intercompany charts of accounts](#set-up-the-intercompany-charts-of-accounts).         |
|Which dimensions should be the basis for the intercompany dimensions?     | If you use intercompany dimensions, they must be the same for all companies in the partnership. After you specify your intercompany dimensions, map their dimension values. Learn more about mapping dimension values at [Set up intercompany dimensions](#set-up-intercompany-dimensions).        |
|Which partners are customers or vendors, or both?     |  Learn more about setting up customers and vendor companies in an intercompany partnership at [Set up intercompany partners as customers and vendors](#set-up-intercompany-partners-as-customers-and-vendors).       |
|Do you want to specify bank accounts to use in the partnership?| You can speed up the process of registering payment transactions by specifying the bank account to use for each partner company. Learn more at [Specify bank accounts for intercompany partners](#specify-bank-accounts-for-intercompany-partners). |
|How do you want to identify the companies in the partnership?     | All parties must agree on a unique intercompany partner identification code for each company. You assign the code to customer and vendor cards to identify related transactions. Learn more about identifiers at [Create Number Series](ui-create-number-series.md).        |
|How do you want to handle item numbers?     | If intercompany lines contain items, you can either use your own item numbers, or you can set up your partner's item numbers for each item, either in the **Vendor Item No.** field or in the **Common Item No.** field on the item card. You can also use the **Item Reference** action to map your items' numbers to your intercompany partners descriptions of the items. To learn more about item references, go to [Use Item References](inventory-how-use-item-cross-refs.md).        |
|Are resources involved?     | If intercompany sales transactions include resources, fill in the **IC Partner Purch. G/L Acc. No.** field on the resource card for each resource. The field contains the number of the intercompany general ledger account that the amount for this resource posts to in the partner company. To learn more about resources, go to [Set Up Resources](projects-how-setup-resources.md).<br><br>**NOTE**<br>Intercompany purchase transactions that include resources, fixed assets, and item charges aren't fully supported. In the partner company, the **Line Type** field is blank on purchase document lines that include these entities. You must manually update the field.        |

## Overview of the steps to get started

Use the **Intercompany Setup** page to set up the following components of intercompany transactions:

* Your company's intercompany settings.
* The company that is the synchronization partner.
* The intercompany chart of accounts that all partners use to exchange transactions.
* The mappings between accounts in the chart of accounts and intercompany chart of accounts for inbound and outbound transactions for each partner.
* The intercompany dimensions and dimension values to use, and how they're mapped to dimensions for each partner.
* The companies that are the intercompany partners.
* The companies that are vendors or customers, or both.

## Set up a synchronization partner

All partners must use the same intercompany chart of accounts and, if needed, the same intercompany dimensions. You can save time when you set up the partnership by using the chart of accounts and dimensions for one of the partners as a baseline for the intercompany chart of accounts and dimensions. The company that you use as the baseline is called the *synchronization partner*. Typically, the synchronization partner is the headquarter company, but it doesn't have to be.

On the **Intercompany Setup** page, each partner specifies the synchronization partner in the **Synchronization Partner** field. Afterward, the intercompany chart of accounts and intercompany dimensions are automatically specified for them, based on the setup for the synchronization partner. The partners then use the **Intercompany Chart of Accounts Mapping** and **Intercompany Dimension Mapping** pages to map their chart of accounts and dimensions to the intercompany chart of accounts and dimensions, and vice versa. 

> [!NOTE]
> It's important to map accounts and dimensions in both directions. That is, both to the intercompany chart of accounts and dimensions, and from them to your own accounts and dimensions.

### Connect with partners in another tenant or environment

If one or more partners' [!INCLUDE [prod_short](includes/prod_short.md)] is in another tenant or environment, there are a few extra steps to create the connection. The steps apply to all partners in another tenant or environment.

* Set up [!INCLUDE [prod_short](includes/prod_short.md)] as a registered app in Azure portal.
* Add and enable the app registration in [!INCLUDE [prod_short](includes/prod_short.md)].
* Exchange information about their intercompany setups. Each partner can get this information from the **Intercompany Setup**, **Actions**, **Connection Details**.

   |Copy from the partner's setup  |Copy to your setup  |
   |---------|---------|
   |Current Connection URL     |IC Partner's Connection URL         |
   |Current Company ID     |IC Partner's Company ID         |
   |Intercompany ID     |IC Partner's Intercompany ID         |
   |Company Name     |IC Partner's Company Name         |

* Exchange the following authentication settings so that [!INCLUDE [prod_short](includes/prod_short.md)] can authenticate when it connects. Each partner can get this information from their registered app. To learn more about how to create a registered app, go to [Create a registered app in Azure portal](#create-a-registered-app-in-azure-portal).  

  * Client ID
  * Client secret
  * Token endpoint
  * Redirect URL

Run the **Intercompany Setup**, **Actions**, **Connection Details** in all companies to specify the information.

#### Create a registered app in Azure portal

This process is only necessary if you want to connect with a partner whose [!INCLUDE [prod_short](includes/prod_short.md)] is in a different tenant or environment.

> [!TIP]
> It's a good idea to have a text editor open, such as Notepad, while you create your registered app. You'll need some of the information when you run the **Intercompany Setup**, **Actions**, **Connection Details**, so it's nice to have the information handy.

1. Go to [Azure portal](https://portal.azure.com/#home).
2. Choose the **Microsoft Entra ID** service.
3. In the navigation pane, choose **App registrations**.
4. On the **App registrations** page, choose **new registration**.
5. Give the application a name.
6. Choose the **Accounts in any organizational directory (Any Microsoft Entra ID tenant - Multitenant)** account type.
7. For the redirect URI, in the **Select a platform** field, choose **Web**, and then provide the URI. For example, \**https://businesscentral.dynamics.com/OAuthLanding.htm**.

  If you're working with an embed ISV, you might need a different URI.

8. Register the app.
9. On the **Intercompany App** page, on the navigation pane, choose **API permissions**.
10. Choose the **Add a permission** action.
11. On the **Microsoft APIs** tab, choose **Dynamics 365 Business Central**.
12. On the **Request API Permissions** pane, choose **Application permissions**, and then choose the **API.ReadWrite.All** permission.
13. On the **Intercompany App | API permissions** page, choose the **Grant admin consent for Contoso** action, and then grant consent.
14. On the navigation pane, choose **Certificates & secrets**.
15. Choose the **Client secrets** tab, and then choose **New client secret**.
16. On the **Add a client secret** pane, enter a name for the secret, and specify when it expires.

  > [!NOTE]
  > All partners who are in different environments must renew the secret before it expires.

  > [!IMPORTANT]
  > Copy the ID in the **Value** field before you leave the **Intercompany App | Certificates & secrets** page. You'll need it in a later step, and it won't be available after you leave the page. For example, paste the value in a text editor.

17. On the navigation pane, choose **Overview**.
18. Copy the value in the **Application (client) ID** field. For example, paste the value in a text editor.
19. Choose the **Endpoints** action, and then copy the value in the **OAuth 2.0 token endpoint (v2)** field. For example, paste the value in a text editor.
20. Copy the value in the **Directory (tenant) ID** field. For example, paste the value in a text editor.
21. In the token value you copied, replace **organizations** with the value you copied from the **Directory (tenant) ID** field in the previous step.

#### Add and enable your registered app in Business Central

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Microsoft Entra Application Card**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
3. In the **State** field, choose **Enabled**. 
4. Choose the **Grant Consent** action. 
5. In the **Permission Set** field, choose **D365 INTERCOMPANY CE & DATA ACCESS IC CE** permission sets.

## Set up the intercompany charts of accounts

All partners must use the same intercompany chart of accounts, and map the accounts in their own chart of accounts to it. If the chart of accounts for your company defines the intercompany chart of accounts for your partner companies, follow the steps in this section.

If you're using an XML file that contains the intercompany chart of accounts, follow the steps in [Import or export an intercompany chart of accounts](intercompany-how-setup.md#import-or-export-an-intercompany-chart-of-accounts).  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Setup**, and then choose the related link.
2. Choose the **IC Chart of Accounts** action.
3. To add accounts, do one of the following on the **Intercompany Chart of Accounts** page:
    * Choose **New**, and then enter each account on a line on the page.  
    * If your intercompany chart of accounts is identical or similar to your regular chart of accounts, you can fill on the page automatically by choosing the **Copy from Chart of Accounts** action. You can edit the new lines as needed.
    * If you set up an intercompany chart of accounts for a synchronization partner, use the **Synchronization Setup** action to copy those accounts.

    > [!TIP]
    > If you copy the intercompany chart of accounts from a synchronization partner, you can use the **Synchronization Setup** action to update your intercompany accounts with any changes the partner makes to theirs.

The next step is to map your chart of accounts to the intercompany chart of accounts. Learn more at [Map the intercompany chart of accounts to your company's chart of accounts](#map-the-intercompany-chart-of-accounts-to-your-companys-chart-of-accounts).

### Import or export an intercompany chart of accounts

The synchronization company can share its chart of accounts with partners by exporting it to a file. Partners can import the file to get the chart of accounts.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Setup**, and then choose the related link.
2. Choose the **IC Chart of Accounts** action.
3. On the **Intercompany Chart of Accounts** page, choose the **Import/Export** action, and then choose either **Import** or **Export**.
4. Choose the file to import or export.  

The **Intercompany Chart of Accounts** page is filled with new or edited G/L account lines according to the intercompany chart of accounts in the file. Any existing, unrelated lines on the page remain unchanged.

## Map the intercompany chart of accounts to your company's chart of accounts  

After you define or import the intercompany chart of accounts, map each intercompany account with one of your accounts. On the **Intercompany Chart of Accounts** page, you specify how intercompany G/L accounts on incoming transactions map to G/L accounts from your company's chart of accounts.

If the intercompany accounts and your accounts have the same numbers, you can map the accounts automatically.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Setup**, and then choose the related link.  
2. Choose the **IC Chart of Accounts** action.

    > [!TIP]
    > To access the actions on the page, you might need to expand the page to the wide layout view.

3. On the **Intercompany Chart of Accounts** page, choose the **Chart of Accounts Mapping** action.
4. You can map the accounts manually, or automatically.

    * To manually create the mapping, on the **Intercompany Chart of Account** and **G/L Chart of Accounts** panes, choose an account, and then choose an account in the **G/L No.** and **IC No.** fields.
    * To automatically map accounts that have the same numbers, select the lines that you want to map, choose the **Map to Acc. with Same No** action, and then choose the chart of accounts to update.

    > [!TIP]
    > If you want to map many or perhaps all accounts, choose a line, choose :::image type="icon" source="media/show-more-options-icon.png" border="false":::, and then choose **Select More**.

## Set up intercompany dimensions

If partners exchange transactions with dimensions linked to them, agree on the dimensions that all of you use. For example, the synchronization company can create a simplified version of their dimensions, export them to an XML file, and then distribute the file to each partner. Each partner can import the XML file on the **Intercompany Dimensions** page and then map the intercompany dimensions to their dimensions. Learn more at [Map intercompany dimensions to your company's dimensions](#map-intercompany-dimensions-to-your-companys-dimensions).

> [!NOTE]
> Each company must map their dimensions to the intercompany dimensions for outgoing documents and incoming documents. Mapping accounts in both directions is important, and helps maintain consistency across the companies.

If partners use the synchronization partner's intercompany dimensions, follow the steps in this section. If you want to share using an XML file that contains the intercompany dimensions, follow the steps in [Import or export intercompany dimensions](#import-or-export-intercompany-dimensions).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Setup**, and then choose the related link.  
2. Choose the **IC Dimensions** action.
3. To add dimensions, do one of the following on the **Intercompany Dimensions** page:
    * Choose **New**, and then enter each dimension on a line.  
    * If your intercompany dimensions are identical or similar to your regular dimensions, you can fill on the page automatically by choosing the **Copy from Dimensions** action. Afterward, you can edit the lines as needed.
    * If you specify intercompany dimensions for a synchronization partner, use the **Synchronization Setup** action to copy those dimensions.

    > [!TIP]
    > If you copy the intercompany dimensions from a synchronization partner, you can use the **Synchronization Setup** action to update your intercompany dimensions with any changes the partner makes to theirs.  

### Import or export intercompany dimensions  

The synchronization company can share its dimensions with partners by exporting them to a file. Partners can import the file to get the dimensions.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Setup**, and then choose the related link.
2. Choose the **IC Dimensions** action.  
3. On the **Intercompany Dimensions** page, choose the **Import/Export** action, and then choose either **Import** or **Export**.
4. Choose the file to import or export.

The next step is to map the dimensions with the intercompany dimensions. Learn more at [Map intercompany dimensions to your company's dimensions](#map-intercompany-dimensions-to-your-companys-dimensions).

### Map intercompany dimensions to your company's dimensions

After you specify the dimensions you use, map each intercompany dimension with one of your company's dimensions, and vice versa. Use the **Intercompany Dimensions Mapping** page to specify the mapping. Afterward, repeat the process for the dimension values.

* Specify how intercompany dimensions on incoming transactions map to dimensions from your company's list of dimensions.
* Specify how your dimensions translate to intercompany dimensions on *outgoing transactions*.

If any of the intercompany dimensions have the same code as the corresponding dimensions in your company, you can automatically map the dimensions.  

In the following steps, you first map intercompany dimensions to dimensions for incoming documents in the **Intercompany Dimensions** pane. Then, you map dimensions to intercompany dimensions for outgoing documents on the **Current Company Dimensions** pane.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Setup**, and then choose the related link.
2. Choose the **IC Dimensions** action.
3. On the **Intercompany Dimensions** page, choose the **Dimensions Mapping** action.
4. You can map the dimensions manually, or automatically.

    * To manually create the mapping, on the **Intercompany Dimensions** and **Current Company Dimensions** panes, choose a dimension, and then choose a dimension in the **Dim. Code** and **IC Dim. Code** fields.
    * To automatically map dimensions that have the same code, select the lines that you want to map, choose the **Map dimensions with same code** action, and then choose the dimensions to update. 

    > [!TIP]
    > If you want to map many or perhaps all dimensions, choose a line, choose :::image type="icon" source="media/show-more-options-icon.png" border="false":::, and then choose **Select More**.

5. Choose the **Dimension Values Mapping** action.
6. On the **Intercompany Dimension Values Mapping** page, the steps to create the mapping are similar to what you just did for dimensions.

## Set up intercompany general journal templates and batches

You must set up a general journal template and a general journal batch to use by default for intercompany transactions. The template and batch are especially important if you automatically accept intercompany transactions from your partners. To learn more about autoaccepting transactions, go to [Autoaccept transactions from intercompany partners](#autoaccept-transactions-from-intercompany-partners).

* General journals are used to post to general ledger accounts and other accounts, such as bank, customer, and vendor accounts. Posting with a general journal always creates entries on general ledger accounts. Use the **Intercompany General Journal** page to set up the general journal batch to use. The settings that are specific to intercompany transactions are the accounts you specify in the **IC Account Type** and **IC Account No** fields.
* Journal templates give you a journal page designed for a specific purpose. That is, the fields in journal templates are exactly the ones needed for a particular part of the program. Use the **General Journal Templates** page to set up a template to use for intercompany transactions.

To learn more about general journal templates and batches, go to [Use journal templates and batches](ui-work-general-journals.md#use-journal-templates-and-batches).

## Set up a company for intercompany transactions

The following steps assume that a synchronization partner is set up with the chart of accounts and dimensions on which you base the intercompany chart of accounts and dimensions. You can set them up yourself, but it's typically faster to get started, and maintenance is easier, to you use a synchronization partner. To learn more about the synchronization partner, go to [Set up a synchronization partner](#set-up-a-synchronization-partner).

> [!TIP]
> It's a good idea to fill in the fields on the **General** FastTab on the **Intercompany Setup** page for each partner before you add their partners. When you add partner companies that are in the same tenant, [!INCLUDE [prod_short](includes/prod_short.md)] gets their IC code and company name from their setup on the General FastTab. The **Company Name** field will verify that their IC code is unique.

> [!NOTE]
> If you'll use a synchronization partner, leave the **Synchronization Partner** field blank when you set that company up for the partnership.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Setup**, and then choose the related link.  
2. On the **Intercompany Setup** page, fill in the fields on the **General** FastTab. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> In [!INCLUDE[prod_short](includes/prod_short.md)] online, you can't use file locations to transfer transactions to your partners because [!INCLUDE[prod_short](includes/prod_short.md)] can't access your local network. Therefore, if you choose **File Location** in the **Transfer Type** field, the **Folder Path** field is not available. Instead, the file will be downloaded to the **Downloads** folder on your computer. You then send the file to someone in the partner company, for example, by email. For a more direct process, we recommend that you choose **Email**.

The next step is to set up the partner companies.

## Set up intercompany partners

Each partner must add all other companies in the partnership as a partner.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Setup**, and then choose the related link.
2. On the **Intercompany Partners** FastTab, choose **Add**.
3. In the **Transfer Type** field, specify how you send data to the partner.

   > [!NOTE]
   > The **File Location** option works only for [!INCLUDE [prod_short](includes/prod_short.md)] on-premises.

4. Fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. Repeat steps 3 and 4 for all companies in the partnership.

> [!NOTE]
> For intercompany posting, if you turn on the **Auto. Accept Transaction** toggle on the **Intercompany Partner** page [!INCLUDE[prod_short](includes/prod_short.md)] suppresses messages that warn about purchase invoices duplicating the original purchase order. It's important to have a business process for managing duplicates. For example, by deleting such purchase orders when the purchase invoice is received from the intercompany partner.

### Set up intercompany partners as customers and vendors

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Setup**, and then choose the related link.
2. On the **Intercompany Partners** FastTab, open the card page for the partner.
3. Depending on what you want to do, choose the customer or partner in the **Customer No.** or **Vendor No.** fields.

    > [!NOTE]
    > If the customer or vendor hasn't been created, you can choose **+New** in the drop-down menu to set them up. To learn more about creating customers and vendors, go to [Register New Customers](sales-how-register-new-customers.md) and [Register New Vendors](purchasing-how-register-new-vendors.md).

    > [!TIP]
    > You can also specify a customer or vendor as an intercompany partner by filling in the **IC Partner Code** field on the **Customer Card** and **Vendor Card** pages.

### Set up default intercompany partner general ledger accounts  

On the **G/L Account Card** page, for accounts that you regularly use on outgoing intercompany sales or purchase lines, you can specify a default intercompany partner general ledger account. For example, for your receivables accounts, you can enter the corresponding payables accounts from the intercompany chart of accounts. The receivables and payables accounts are used as the off-setting account for the intercompany partner when you post transactions on intercompany general journals.  

Then, when you enter a general ledger account in the **Bal. Account No.** field on an intercompany line with **Intercompany Partner** in the **Account Type** field, the **IC Partner G/L Account** field is automatically filled in.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
2. Open the G/L account that's used for intercompany transactions, and in the **Default IC Partner G/L Account** field, enter the intercompany general ledger account that your partner post to when you post to the general ledger account on the line.
3. Repeat step 2 for each account that you often enter in the **Bal. Account No.** field on a line in an intercompany journal or document.

### Autoaccept transactions from intercompany partners

To make it faster to process intercompany transactions, you can specify that you want to automatically create journal lines based on an intercompany partner's posts from the **IC General Journal** page. To autocreate incoming and outgoing transactions, you must turn on the following toggles for each partner:

* On the **Intercompany Setup** page, turn on the **Auto. Send Transactions** toggle for the synchronization partner. Then specify where to create received intercompany journal transactions by filling in the **Default IC Gen. Jnl. Template** and **Default IC Gen. Jnl. Batch** fields.

    > [!TIP]
    > If the **Default IC Gen. Jnl. Template** field is blank, you need to set up a general journal template to use for your intercompany general journals. To learn more about templates and batches, go to [Set up intercompany general journal templates and batches](#set-up-intercompany-general-journal-templates-and-batches)    

* On the **Intercompany Partner** page, turn on the **Auto Accept Transactions** toggle.

The journal lines are created for you, but not posted.

### Specify bank accounts for intercompany partners

To facilitate fast payments, specify one or more bank accounts to use for intercompany partners. When a partner uses an intercompany general journal to make a payment, they can specify the bank account on the line. The bank account is used as the balancing account in the receiving company, which minimizes the need to manually enter transactions.

* To specify the bank account to use, on the **Intercompany Partners** page, choose the **Bank Accounts** action. On the **Intercompany Bank Account Card**, enter the account information.

## Troubleshoot your intercompany setup

On the **Intercompany Setup** page, the **Intercompany Setup Diagnostics** pane contains tiles that indicate whether all of the components needed to exchange intercompany transactions are set up. The tiles are also available on the Business Manager Role Center. Choose the tiles to find out what's missing. For an overview of the required components, go to [Overview of the steps to get started](#overview-of-the-steps-to-get-started).

## See Also

[Managing Intercompany Transactions](intercompany-manage.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
