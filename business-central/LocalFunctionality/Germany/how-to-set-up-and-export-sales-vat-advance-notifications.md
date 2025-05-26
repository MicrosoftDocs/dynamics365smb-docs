---
title: Set up and export sales VAT advance notifications
description: Learn how to set up and export sales VAT advance notifications in Business Central by configuring the necessary declaration and setup pages.
author: sorenfriisalexandersen
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT advance notifications, sales VAT notifications, export VAT notifications, German version
ms.date: 03/12/2025
ms.author: soalex
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up and export sales VAT advance notifications

A sales VAT advance notification is an XML file that you can use to report VAT to the German tax authorities on the Elektronische Steuererklärungen (ELSTER) online portal. [!INCLUDE [prod_short](../../includes/prod_short.md)] generates an XML file with tax and base amounts, and information about your company in the format and layout that German tax authorities require.

> [!NOTE]
> Most of the functionality is included in the **ELSTER VAT Localization for Germany** extension. Make sure that this is installed in your [!INCLUDE[prod_short](../../includes/prod_short.md)]. Learn more in [Customizing Business Central Online Using Extensions](../../ui-extensions.md).

## Process

To create valid sales VAT advance notification, you must set up the following information:  

- The company registration information and tax office information.  
- Basic sales VAT advance notification on the **Electronic VAT Decl. Setup** page.
- The VAT statement.  

### Set up company information

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.  
1. On the **Company Information** page, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

   Specifically for sales VAT advance notifications, in the **VAT Representative** field, enter the contact person for VAT-related information.  
1. Choose the **OK** button.  

### Set up the electronic VAT declaration

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Electronic VAT Decl. Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

|Field|Description|
|-----|-----|
|**Sales VAT Adv. Notif. Nos.**|Choose the number series to assign identification numbers to new sales VAT advance notifications.|
|**Sales VAT Adv. Notif. Path**|Enter the path and name of the folder where you want to store the XML files.|
|**XML File Default Name**|Enter the name of the file.|

### Set up a VAT statement

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statement**, and then choose the related link.  
1. On the **VAT Statement** page, in the **Name** field, choose the dropdown arrow.  
1. On the **VAT Statement Names** page, in the line for the appropriate VAT statement name, select the **Sales VAT Adv. Notification** field.

    > [!NOTE]
    > The VAT statement must have a VAT statement line for each key figure required by the tax authority, where the **Row No.** field contains the key figure and the **Amount Type** field specifies whether this is a base amount or a tax amount. Ask your tax office if you have questions concerning the key figures and their definition.

1. Choose the **OK** button.  

## Create an XML document

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Vat Advanced Notification List**, and then choose the related link.  
1. On the **Sales Vat Advanced Notification List** page, choose the **New** action.  
1. On the **Sales VAT Adv. Notif. Card** page, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

    > [!CAUTION]
    > If you submitted a sales VAT advance notification as a test notification by selecting the **Testversion** field, you can't change it into a real notification later. The tax authority doesn't accept the same XML file if it's submitted with the **Testversion** field cleared.

    Optionally, choose the **Preview statement** action to see a VAT statement that shows the data that is in the XML that you submit to the ELSTER portal. This view shows an amount for each element in the XML file in a human-readable format.  

    > [!NOTE]
    > In versions older than version 19.3 and other updates that are made available in January and February 2022, the **Sales VAT Adv. Notif. Card** page shows fields and actions based on deprecated functionality in both the ELSTER portal and [!INCLUDE [prod_short](../../includes/prod_short.md)]. Specifically fields that are tied to stylesheets are no longer in use, because the ELSTER portal no longer provides such stylesheets.
1. Choose the **Create XML-File** action.
1. On the **Create XML - VAT Adv. Notif.** page, in the **XML-File** field, choose either the **Create** or the **Create and Export** option.  

    If you choose the **Create and Export** option, the XML file is generated and saved to your device. If you choose the **Create** option, data is generated in [!INCLUDE [prod_short](../../includes/prod_short.md)] as an XML file when you choose the **Export** action on the **Sales VAT Adv. Notif. Card** page.  
1. Choose the **OK** button.  

After the sales VAT advance notification document is created, all fields in the **Sales VAT Adv. Notif. Card** page can no longer be modified, except the **Description** field, because they define the content of the XML document. If you created an XML document and want to create a new XML document for the same period without transmitting the existing document to the tax authority, you must delete the existing XML file. Then, create the new document.

## Related information

- [VAT Reporting](vat-reporting.md)  
- [Germany Local Functionality](germany-local-functionality.md)  
- [Customizing Business Central Using Extensions](../../ui-extensions.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
