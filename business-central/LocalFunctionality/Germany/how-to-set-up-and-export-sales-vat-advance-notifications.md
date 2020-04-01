---
    title: How to Set Up and Export Sales VAT Advance Notifications
    description: In Business Central, to create valid sales VAT advance notifications, you must perform certain setup.

    author: sorenfriisalexandersen

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: soalex

---

# Sales VAT Advance Notifications  
A Sales VAT Advance Notification in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] is an XML file that you can use to report VAT to the German tax authorities on the Elektronische Steuererklärungen (ELSTER) online portal. The XML file includes tax and base amounts, and information about your company, and is created in the format and layout that German tax authorities require.    

> [!NOTE]
 >  Most of the functionality is included in the **ELSTER VAT Localization for Germany** Extension. Make sure that this is installed in your [!INCLUDE [prodshort](../../includes/prodshort.md)].
 
 
## Set Up and Export Sales VAT Advance Notifications
To create valid sales VAT advance notifications, you must set up the following:  

- The company registration information and tax office information.  
- Basic sales VAT advance notification on the **Electronic VAT Decl. Setup** page.
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
|**Sales VAT Adv. Notif. Path**|Enter the path and name of the folder where you want to store the XML files.|
|**XML File Default Name**|Enter the name of the file.|

### To set up a VAT statement for sales VAT advance notifications  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Statement**, and then choose the related link.  
2.  On the **VAT Statement** page, in the **Name** field, choose the drop-down arrow.  
3.  On the **VAT Statement Names** page, in the line for the appropriate VAT statement name, select the **Sales VAT Adv. Notification** check box.

> [!NOTE]  
 >  The VAT statement must have a VAT statement line for each key figure required by the tax authority, where the **Row No.** field contains the key figure and the **Amount Type** field specifies whether this is a base amount or a tax amount. Ask your tax office if you have questions concerning the key figures and their definition.

4. Choose the **OK** button.  

## To create an XML document for Sales VAT advance notification  
1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Vat Advanced Notification List**, and then choose the related link.  
2. On the **Sales Vat Advanced Notification List** page, choose the **New** action.  
3. On the **Sales VAT Adv. Notif. Card** page, fill in the fields.
4. Choose **Process**, and then choose the **Create XML-File** action.  
5. On the **Create XML - VAT Adv. Notif.** page, in the **XML-File** field, choose either the **Create** or the **Create and Export** option.  
6. Choose the **OK** button.  

## See Also
[VAT Reporting](vat-reporting.md)  
[Germany Local Functionality](germany-local-functionality.md)  
[Customizing Business Central Using Extensions](../../ui-extensions.md)  
