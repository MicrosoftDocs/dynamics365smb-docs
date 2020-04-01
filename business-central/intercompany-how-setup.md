---
title: Set Up Intercompany Transaction Posting| Microsoft Docs
description: Create your intercompany vendors and customers as so-called intercompany partners, and set up an intercompany chart of accounts.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: IC, group, consolidation, affiliate, subsidiary
ms.date: 04/01/2020
ms.author: sgroespe

---
# Set Up Intercompany
To send a transaction (such as a sales journal line) from one company and have the corresponding transaction (such as a purchase journal line) automatically created in the partner company, the companies involved must agree on a common chart of accounts and set of dimensions for use on intercompany transactions. The intercompany chart of accounts can be, for example, a simplified version of the parent company's chart of accounts. Each company maps their full chart of accounts to the shared intercompany chart of accounts, and each company maps their dimensions to the intercompany dimensions.  

You must also set up an intercompany partner code for each partner company, which is agreed upon by all of the companies, and then assign them to customer and vendor cards respectively by filling in the **Intercompany Partner Code** field.  

If you create or receive intercompany lines with items, you can either use your own item numbers, or you can set up your partner's item numbers for each relevant item, either in the **Vendor Item No.** field or in the **Common Item No.** field on the item card. You can also use the **Item Cross Reference** function: To map your items' numbers to your intercompany partners descriptions of the items, open the card of each item, and then choose the **Cross References** action to set up cross-references between your item descriptions and those of the intercompany partner.  

If you will make intercompany sales transactions that include resources, you must fill in the **IC Partner Purch. G/L Acc. No.** field on the resource card for each relevant resource. This is the number of the intercompany general ledger account that the amount for this resource will be posted to in your partner's company. For more information, see [Set Up Resources](projects-how-setup-resources.md).

## To set up companies for intercompany transactions
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.  
2. On the **Company Information** page, fill in the **Intercompany Partner Code**, **Intercompany Inbox Type**. and **Intercompany Inbox Details** fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To set intercompany partners
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Partners**, and then choose the related link.
2. Choose the **New** action.
3. On the **Intercompany Partner** page, fill in the fields as necessary.

## To set up intercompany vendors and intercompany customers
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Alternatively, access the vendor from the **Vendor No.** field on the **Intercompany Partner** page.
3. Open the card for a vendor that is an intercompany partner. For more information, see [Register New Vendors](purchasing-how-register-new-vendors.md).
4. In the **Intercompany Partner Code** field, select the relevant intercompany partner code.
5. Repeat steps 1 through 4 for customers.

## To set up intercompany charts of accounts
In order for a group of companies to make intercompany transactions, they must agree on a chart of accounts to use as a common reference. You must agree with your partner companies on the account numbers that all of you will use when you create intercompany transactions. For example, the parent company of the group creates a simplified version of their own chart of accounts, exports this intercompany chart of accounts from their database into an XML file and distributes it to each of the companies in the group.  

If your company is the parent company and has the defining intercompany chart of accounts that your group will use as a common reference, follow the [To set up the defining intercompany chart of accounts](intercompany-how-setup.md#to-set-up-the-defining-intercompany-chart-of-accounts) procedure.  

If your company is a subsidiary company and you receive an XML file containing the common intercompany chart of accounts, follow the [To Import the intercompany chart of accounts](intercompany-how-setup.md#to-import-the-intercompany-chart-of-accounts) procedure.  

### To set up the defining intercompany chart of accounts
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Chart of Accounts**, and then choose the related link.
2. On the **Intercompany Chart of Accounts** page, enter each account on a line on the page.  
3. If your intercompany chart of accounts will be identical or similar to your regular chart of accounts, you can fill on the page automatically by choosing the **Copy from Chart of Accounts** action. You can edit the new lines as needed.

### To export an intercompany chart of accounts
To allow your intercompany partners to import the defining chart of accounts, you must export it to a file.      
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Chart of Accounts**, and then choose the related link.
2. On the **Intercompany Chart of Accounts** page, choose the **Export** action, and then choose the **Save** button.
3. Specify the file name and the location where you want to save the XML file, and then choose the **Save** button.  

### To import the intercompany chart of accounts  
When a file exists for the defining intercompany chart of accounts, intercompany partners can import it to make sure they have the same accounts.  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Chart of Accounts**, and then choose the related link.  
2. On the **Intercompany Chart of Accounts** page, choose the **Import** action.  
3. Select the file name and location of the XML file, and then choose the **Open** button.  

The **IC Chart of Accounts** page is filled with new or edited G/L account lines according to the intercompany chart of accounts in the file. Any existing, unrelated lines on the page remain unchanged.

### To map the intercompany chart of accounts to your company's chart of accounts  
When you have defined or imported the intercompany chart of accounts that you and your intercompany partners have agreed to use, you must associate each of the intercompany G/L accounts with one of your company's G/L accounts. On the **IC Chart of Accounts** page, you specify how intercompany G/L accounts on incoming transactions will be translated into G/L accounts from your company's chart of accounts.

If the accounts in the intercompany chart of accounts have the same numbers as the corresponding accounts in the chart of accounts, you can map the accounts automatically.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Chart of Accounts**, and then choose the related link.  
2. Select the lines that you want to map automatically, and then choose the **Map to Acc. with Same No** action.  
3. For each intercompany general ledger account that was not mapped automatically, fill in the **Map-to G/L Acc. No.** field.  

## To set up default intercompany partner general ledger accounts  
When you create an intercompany sales or purchase line to send as an outgoing transaction, you enter an account from the intercompany chart of accounts as a default for which account in your partner's company the amount is posted to. On the **Chart of Accounts** page, for accounts that you often use on outgoing intercompany sales or purchase lines, you can specify a default intercompany partner general ledger account. For example, for your receivables accounts, you can enter the corresponding payables accounts from the intercompany chart of accounts.  

Then, when you enter a general ledger account in the **Bal. Account No.** field on an intercompany line with **Intercompany Partner** in the **Account Type** field, the **IC Partner G/L Account** field is automatically filled in.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
2. On the line for a G/L account that is used for intercompany transactions, in the **Default IC Partner G/L Account** field, enter the intercompany general ledger account that your partner will post to when you post to the general ledger account on the line.  
3. Repeat step 2 for each account that you often enter in the **Bal. Account No.** field on a line in an intercompany journal or document.

## To set up intercompany dimensions
If you and your intercompany partners want to be able to exchange transactions with dimensions linked to them, then you must agree on the dimensions that all of you will use. For example, the parent company of the group creates a simplified version of their own set of dimensions, exports these intercompany dimensions into an XML file and distributes it to each of the companies in the group. Each of the subsidiaries then imports the XML file into the **Intercompany Dimensions** page and maps the intercompany dimensions to the dimensions in their own **Dimensions** page.  

If your company is the parent company and has the defining set of intercompany dimensions that your group will use as a common reference, follow the [To define the intercompany dimensions](intercompany-how-setup.md#to-define-the-intercompany-dimensions) procedure.

If your company is a subsidiary company and you receive an XML file containing the intercompany dimensions that your group will use as a common reference, follow the [To import intercompany dimensions](intercompany-how-setup.md#to-import-the-intercompany-dimensions) procedure.

### To define the intercompany dimensions
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Dimensions**, and then choose the related link.  
2. On the **Intercompany Dimensions** page, enter each dimension on a line on the page.

    If your intercompany dimensions will be similar or identical to your company dimensions, you can fill on the page automatically by using the **Copy from Dimensions** function, and then you can edit the resulting lines.  
3. To export the intercompany dimensions to an XML file for distribution to your partner companies, choose the **Export** action.  
4. Specify the file name and the location where you want to save the XML file, and then choose the **Save** button.  

### To import the intercompany dimensions  
When a file exists for the defining intercompany dimensions, intercompany partners can import it to make sure they have the same dimensions.  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Dimensions**, and then choose the related link.  
2. On the **Intercompany Dimensions** page, choose the **Import** action.  
3. Specify the file name and location of the XML file, and then choose the **Open** button.  

The lines on the **Intercompany Dimensions** page and the **Intercompany Dimension Values** page are imported.  

### To map intercompany dimensions to your company's dimensions
When you have defined or imported the dimensions that you and your intercompany partners have agreed to use, you must associate each of the intercompany dimensions with one of your company's dimensions, and vice versa. On the **Intercompany Dimensions** page, you specify how intercompany dimensions on incoming transactions will be translated into dimensions from your company's list of dimensions. On the **Dimensions** page, you specify how your dimensions will be translated into intercompany dimensions on outgoing transactions.

If any of the intercompany dimensions have the same code as the corresponding dimensions in your company's list of dimensions, then you can have application automatically map the dimensions, then you can map the accounts automatically.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Dimensions**, and then choose the related link.
2. On the **Intercompany Dimensions** page, select the lines that you want to automatically map, and then choose the **Map to Dim. with Same Code** action.'
3. For each intercompany dimension that is not mapped automatically, fill in the **Map-to Dimension Code** field.

    You may have to add the field to your view. For more information, see [Personalize Your Workspace](ui-personalization-user.md).
4. Choose the **Intercompany Dimension Values** action.
5. On the **Intercompany Dimension Values** page, fill in the **Map-to Dimension Value Code** field.

    Proceed to map dimensions to intercompany dimensions by performing similar steps.
6. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dimensions**, and then choose the related link.
7. On the **Dimensions** page, select the lines that you want to automatically map, and then choose the **Map to IC Dim. with Same Code** action.
8. For each intercompany dimension that is not mapped automatically, fill in the **Map-to IC Dimension Value Code** field.
9. Choose the **Dimension Values** action.
10. On the **Dimension Values** page, fill in the **Map-to IC Dimension Value Code** field.

## See Also
[Managing Intercompany Transactions](intercompany-manage.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Working with General Journals](ui-work-general-journals.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
