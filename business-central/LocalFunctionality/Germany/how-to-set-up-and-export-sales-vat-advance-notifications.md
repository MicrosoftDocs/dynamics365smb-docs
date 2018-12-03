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
A Sales VAT Advance Notification in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] is an XML document that contains tax and base amounts, along with company information. The XML document is set up using the layout that is defined in the tax authorities' style sheet.  <!-- Do they need to get the stylesheet from the tax authorities, or is that something we've done for them? -->

## Set Up and Export Sales VAT Advance Notifications
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] can create files used to report VAT to the German authorities. These files will be created as XML files in the format specified by the German tax authorities and can be saved to your computer when created. From here you must submit them to the authorities on the Elektronische Steuererklärungen (ELSTER) online portal.

To create valid sales VAT advance notifications, you must set up the following:  

- The company registration information and tax office information.  
- Basic sales VAT advance notification in the **Electronic VAT Decl. Setup**. <!--Does "Decl." stand for "declaration?"-->
- The VAT statement.  

### To set up company information  
1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Company Information**, and then choose the related link.  
2. On the **Company Information** page, in the **VAT Representative** field, enter the contact person for VAT related information.  
3. Choose the **OK** button.  

### To set up the Electronic VAT Decl. Setup
1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Electronic VAT Decl. Setup**, and then choose the related link.
2. Fill in the fields as described in the following table.

|Field|Description|
|-----|-----|
|**Sales VAT Adv. Notif. Nos.**|Choose the number series to use to assign identification numbers to new sales VAT advance notifications.|
|**Sales VAT Adv. Notif. Path**|Enter the path and name of the folder where you want to store the XML files. <!--Do they provide the name of the folder, or are they just specifying the full path?-->|
|**XML File Default Name**|Enter the name of the file what you want to store the XML files. <!-- Don't understand this sentence. Should it just be "enter the name of the file?"-->|

### To set up a VAT statement for sales VAT advance notifications  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Statement**, and then choose the related link.  
2.  On the **VAT Statement** page, in the **Name** field, choose the drop-down arrow.  
3.  On the **VAT Statement Names** page, in the line for the appropriate VAT statement name select the **Sales VAT Adv. Notification** field. <!--Field, or check box? --> 

> [!NOTE]  
 >  You can choose only one VAT statement name for sales VAT advance notification. <!--why is this important?--> The VAT statement must have a VAT statement line for each key figure required by the tax authority, where the **Row No.** field contains the key figure and the **Amount Type** field specifies whether this is a base amount or a tax amount. Ask your tax office if you have questions concerning the key figures and their definition. 

4. Choose the **OK** button.  

## To create an XML document for Sales VAT advance notification  
1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Vat Advanced Notification List**, and then choose the related link.  
2. On the **Sales Vat Advanced Notification List** page, choose the **New** action.  
3. On the **Sales VAT Adv. Notif. Card** page, fill in the fields. <!--need to verify the name of this page. Not sure if the name should include "Card."-->
4. Choose **Process**, and then choose the **Create XML-File** action.  
5. On **Create XML - VAT Adv. Notif.** page, in the **XML-File** field, choose either the **Create** or the **Create and Export** option.  
6. Choose the **OK** button.  

## See Also
[Germany Local Functionality](germany-local-functionality.md)