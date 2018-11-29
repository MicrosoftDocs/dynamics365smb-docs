---
    title: How to Set Up and Export Sales VAT Advance Notifications
    description: In Business Central, to create valid sales VAT advance notifications, you must perform certain setup.

    services: project-madeira
    documentationcenter: ''
    author: sorenfriisalexandersen

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 11/30/2018
    ms.author: soalex

---

# Sales VAT Advance Notifications  
A Sales VAT Advance Notification in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] is a XML document containing tax and base amounts, along with company information. The XML document is set up using the layout that is defined in the tax authorities' style sheet.  

## Set Up and Export Sales VAT Advance Notifications
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] can create files used to report VAT to the German authorities. These files will be created as XML files in the format specified by the German Tax authorities and can be saved to your computer when created. From here you must submit them to the authorities manually to the Elektronische Steuererklärungen (ELSTER) online portal.

To create valid sales VAT advance notifications to, you must set up the following:  

- The company registration information and tax office information.  
- Basic sales VAT advance notification in the **Electronic VAT Decl. Setup**
- The VAT statement.  

## To set up company information  

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Company Information**, and then choose the related link.  
2. On the **Company Information** page, on the **General** FastTab, in the **VAT Representative** field, enter the contact person for VAT related information.  
 
3. Choose the **OK** button.  

## To set up the Electronic VAT Decl. Setup

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Electronic VAT Decl. Setup**, and then choose the related link.
2. Fill in the following fields:
- **Sales VAT Adv. Notif. Nos.** - Specifies the number series code used to assign numbers to sales VAT advance notifications.
- **Sales VAT Adv. Notif. Path** - Specifies the path and name of the folder where you want to store the XML files.
- **XML File Default Name** - Specifies the name of the file what you want to store the XML files.

## To set up a VAT statement for sales VAT advance notifications  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Statement**, and then choose the related link.  
2.  On the **VAT Statement** page, in the **Name** field, choose the drop-down arrow.  
3.  On the **VAT Statement Names** page, in the line for the appropriate VAT statement name select the **Sales VAT Adv. Notification** field.  

> [!NOTE]  
 >  Only one VAT statement name can be selected for sales VAT advance notification at one time. The VAT statement must have a VAT statement line for each key figure required by the tax authority, where the **Row No.** field contains the key figure and the **Amount Type** field specifies if this is a base amount or a tax amount. Ask your tax office if you have questions concerning the key figures and their definition. 

4. Choose the **OK** button.  

## To create an XML document for Sales VAT advance notification  

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Vat Advanced Notification List**, and then choose the related link.  

2. On the **Sales Vat Advanced Notification List** page, choose the **New** action.  

3. On the **Sales VAT Adv. Notif. Card** page and fill in the fields.

4. Choose **Process** and select the **Create XML-File** action.  

5. In **Create XML - VAT Adv. Notif.** page, on the **Options** FastTab, in the **XML-File** field, select the **Create** or the **Create and Export** option.  

6. Choose the **OK** button.  
