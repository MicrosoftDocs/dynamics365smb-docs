---
title: Multilanguage and localization
description: Learn how language and region influence your experience in Business Central. Change the language of the user interface in My Settings.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: language, locale, localization, culture, region, regional settings
ms.search.form: 9020, 9022, 9026, 9027, 9030, 9000, 9009, 9004, 9005, 9024, 9006, 9007, 9010, 9016, 9017
ms.date: 12/19/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Changing your language and region settings

[!INCLUDE[prod_short](includes/prod_short.md)] is available in many markets and languages, and [!INCLUDE [prod_short](includes/prod_short.md)] offers features to help companies comply with local regulatory requirements. You can use [!INCLUDE[prod_short](includes/prod_short.md)] in different languages, and can change the language for display texts. If you change your language setting, sign out and sign in again to apply the change. The new setting applies only to you, and not to everyone else in your company.  

[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]

For example, you're using the Canadian version of [!INCLUDE[prod_short](includes/prod_short.md)]. You can use [!INCLUDE [prod_short](includes/prod_short.md)] in English, German, French, or another language, but it's still the Canadian version of [!INCLUDE[prod_short](includes/prod_short.md)]. It isn't the same as [!INCLUDE[prod_short](includes/prod_short.md)] in Germany, where features are adapted for German requirements.  

To change the language of the user interface, go to the **My Settings** page. To learn more, go to [Change Basic Settings](ui-change-basic-settings.md#language).

> [!NOTE]  
> The choice of languages resets to your setting on your Microsoft 365 profile if your administrator synchronizes users from Microsoft 365 to [!INCLUDE[prod_short](includes/prod_short.md)].

You can't change the texts that are stored as application data. Examples of such texts are the names of items in inventory, or the comments for a customer. In other words, these types of text aren't translated.  

> [!NOTE]  
> [!INCLUDE[prod_short](includes/prod_short.md)] only supports a single character set for data. Some characters might not be supported in your environment. You might experience problems when you try to view data that was entered using a different character set. For instance, your environment might support only English and Russian characters. In this case, if you enter data in a different language, [!INCLUDE [prod_short](includes/prod_short.md)] might not store it correctly. Contact your system administrator to make sure you understand which languages are supported by your [!INCLUDE[prod_short](includes/prod_short.md)].  

## Changing your region setting

Region is different from both language and legal requirements in local markets. Region determines how your data presents itself, such as the decimal separator, and how text aligns to the left or right. The region also determines some of the system elements in the browser, such as the action to create a new item in a list.  

You can change the region in the browser tab that you're using to work in [!INCLUDE[prod_short](includes/prod_short.md)]. The change applies only to you and not to the other users in your company. The choice of region is reset to your setting on your Microsoft 365 profile if your administrator synchronizes users from Microsoft 365 into [!INCLUDE[prod_short](includes/prod_short.md)].

> [!IMPORTANT]  
> When you change the region, you'll see a long list of languages and regions. However, the language isn't influenced by the choice of region.  

To change the region, go to the **My Settings** page. To learn more, go to [Change Basic Settings](ui-change-basic-settings.md).  

## Changing the region setting for customers, contacts, and vendors

Some businesses use an external service that validates address information in their country or region. However, when you need to update address information, the structured approach that these services use might not always be what's right for some scenarios. [!INCLUDE [prod_short](includes/prod_short.md)] offers a more flexible means of entering address details.

On the **General Ledger Setup** page, if you turn on the **Require Country/Region Code in Address** toggle, changes to the **Country/Region Code** field on addresses for customers, contacts, or vendors resets the values in other address fields.

## Custom address formats for countries/regions

The countries and regions in which you do business might have different formats for addresses. [!INCLUDE [prod_short](includes/prod_short.md)] lets you customize the format in which postal addresses show for each region. To define a custom format, on the **Countries/Regions** page, choose the **Custom Address Format** action. You can adjust the order of the address information by using the **Move Up** and **Move Down** actions. To change the field on a line, in the **Field ID** field, choose :::image type="content" source="media/assist-edit-icon.png" alt-text="The assist edit icon.":::, and then choose the field.

In some cases, you might need to add multiple fields on a line. By default, [!INCLUDE [prod_short](includes/prod_short.md)] lets you combine the city, postal code, and country. To add multiple fields on a line, enter **0** in the **Field ID** field, and then choose the value in the **Line Format** field to open the **Custom Address Format Lines** page. Add a new line for each piece of information.

## Application version

In the **Help and Support** page, you can see the version of [!INCLUDE[prod_short](includes/prod_short.md)] that your company is based on. If you want to base a company on a different version, your administrator can create a new production environment. For more information, see [Create a new production environment](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments#create-a-new-production-environment) in the developer- and IT Pro content.  

## Languages of the [!INCLUDE[prod_short](includes/prod_short.md)] Help

The Help content for the default version of [!INCLUDE[prod_short](includes/prod_short.md)] publishes to Microsoft Learn. The content is available in different languages. If you access the documentation while you're using [!INCLUDE[prod_short](includes/prod_short.md)], the content displays in your language. By default, if a particular page isn't available in your language yet, it shows in English.

### How do I change the language of the Microsoft Learn site?

Scroll to the bottom of the browser page and choose the globe symbol in the bottom left corner.

> [!NOTE]  
> The list shows all languages that are supported by the Microsoft Learn site. [!INCLUDE[prod_short](includes/prod_short.md)] is available in a limited number of countries/regions, and the [!INCLUDE [prod_short](includes/prod_short.md)] Help content is not available in all languages that the Microsoft Learn site supports.

## Related information

[Resources for Help and Support](product-help-and-support.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
