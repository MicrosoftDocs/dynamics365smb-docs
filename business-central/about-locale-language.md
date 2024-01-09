---
title: Multilanguage and Localization
description: Learn how language and region influence your experience in Business Central. Change the language of the user interface in My Settings.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: language, locale, localization, culture, region, regional settings
ms.search.form: 9020, 9022, 9026, 9027, 9030, 9000, 9009, 9004, 9005, 9024, 9006, 9007, 9010, 9016, 9017
ms.date: 04/01/2021
ms.author: bholtorf
---
# Changing Language and Region

[!INCLUDE[prod_short](includes/prod_short.md)] is available in many markets and languages around the World. In the markets where [!INCLUDE[prod_short](includes/prod_short.md)] is available, regulatory features are available to assist companies with regulatory burdens. [!INCLUDE[prod_short](includes/prod_short.md)] can display in different languages. You can even change the language that is used to display texts. The change is immediate, once you've been automatically signed out and in again. The setting applies to you and not to everyone else in your company.  

[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]

For example, you're using the Canadian version of [!INCLUDE[prod_short](includes/prod_short.md)]. That means that you can see the user interface in English, German, French, or another language, but it's still the Canadian version of [!INCLUDE[prod_short](includes/prod_short.md)]. It isn't the same as [!INCLUDE[prod_short](includes/prod_short.md)] in Germany where functionality has been adapted towards that market's requirements.  

To change the language of the user interface, go to the **My Settings** page. For more information, see [Change Basic Settings](ui-change-basic-settings.md#language). 

> [!NOTE]  
> The choice of languages will be reset to your setting on your Microsoft 365 profile if your administrator synchronizes users from Microsoft 365 to [!INCLUDE[prod_short](includes/prod_short.md)].

You can't change the texts that are stored as application data. Examples of such texts are the names of items in the inventory, or the comments for a customer. In other words, these types of text aren't translated.  

> [!NOTE]  
> [!INCLUDE[prod_short](includes/prod_short.md)] only supports a single character set for data. Therefore, some characters may not be supported in your environment, and you may experience problems when retrieving data that was entered using a different character set. For instance, your environment may support only English and Russian characters. In this case, if you enter data in a different language, it may not be stored correctly. You should contact your system administrator to make sure you understand which languages are supported by your [!INCLUDE[prod_short](includes/prod_short.md)].  

## Changing your region setting

Region is different from both language and legal requirements in local markets. Region determines how your data presents itself, such as the decimal separator, and how text aligns to the left or to the right. The region also determines some of the system elements in the browser, such as the action to create a new item in a list.  

You can change the region in the browser tab that you're using to work in [!INCLUDE[prod_short](includes/prod_short.md)]. The change applies only to you and not to the other users in your company.  The choice of region will be reset to your setting on your Microsoft 365 profile if your administrator synchronizes users from Microsoft 365 into [!INCLUDE[prod_short](includes/prod_short.md)].

> [!IMPORTANT]  
> When you change the region, you will see a long list of languages and regions. However, the language is not influenced by the choice of region.  

To change the region, go to the **My Settings** page. For more information, see [Change Basic Settings](ui-change-basic-settings.md).  

## Changing the Region Setting for Customers, Contacts, and Vendors

Some businesses use an external service that validates address information in their country or region. However, when you need to update address information, the structured approach that these services use may not always be what's right for some scenarios. Business Central offers a more flexible means of entering address details.

On the **General Ledger Setup** page, if you turn on the **Require Country/Region Code in Address** toggle, changes to the **Country/Region Code** field on addresses for customers, contacts, or vendors will reset the values in other address fields.

## Application Version

In the **Help and Support** page, you can see the version of [!INCLUDE[prod_short](includes/prod_short.md)] that your company is based on. If you want to base a company on a different version, your administrator can create a new production environment. For more information, see [Create a new production environment](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments#create-a-new-production-environment) in the developer- and IT Pro content.  

## Languages of the [!INCLUDE[prod_short](includes/prod_short.md)] Help

The Help content for the default version of [!INCLUDE[prod_short](includes/prod_short.md)] publishes to Microsoft Learn. The content is available in different languages. If you access the documentation from inside [!INCLUDE[prod_short](includes/prod_short.md)], the content will display in your language. By default, if a particular page isn't available in your language yet, it will be shown in English.

### How do I change the language of the Microsoft Learn site?

It's simple - scroll to the bottom of the browser page and choose the globe symbol in the bottom left corner.

> [!NOTE]  
> The list shows all languages that are supported by the Microsoft Learn site. [!INCLUDE[prod_short](includes/prod_short.md)] is available in a limited number of countries/regions, and the [!INCLUDE [prod_short](includes/prod_short.md)] Help content is not available in all languages that the Microsoft Learn site supports.

## See Also

[Resources for Help and Support](product-help-and-support.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]