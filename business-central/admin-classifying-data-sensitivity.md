---
title: Classify Data Sensitivity in Business Central
description: Classify personal and sensitive data in Business Central, manage field sensitivity levels, and understand the limits of masking values in the user interface.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.form: 1751, 1752
ms.date: 11/12/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
ai-usage: ai-assisted
---

# Classify data sensitivity in Business Central

To classify the fields that hold sensitive or personal data, a developer can set the `DataClassification` property on fields in AL code.

As a customer, you can add a second level of classification by specifying sensitivity levels for the data you store in standard and custom fields. Classifying data sensitivity helps ensure that you know where you keep personal data in your system, and makes it easier to respond to requests from data subjects. For example, if a contact or customer asks you to export their personal data. Learn more in [Responding to requests about personal data](admin-responding-to-requests-about-personal-data.md).

> [!IMPORTANT]  
> Microsoft is providing this Data Sensitivity Classification feature as a matter of convenience only. It's your responsibility to classify the data appropriately and comply with any laws and regulations that are applicable to you. Microsoft disclaims all responsibility towards any claims related to your classification of the data.  

The following table describes data sensitivity levels you can assign.

|Sensitivity|Description|
|----|----|
|Unclassified | A sensitivity level hasn't been assigned to the field. |
|Sensitive | Information about a data subject's racial or ethnic origin, political opinions, religious beliefs, involvement with trade unions, physical or mental health, sexuality, or details about criminal offenses. |
|Personal | Information that can be used to identify a data subject, either directly or in combination with other data or information.|
|Company Confidential | Business data that you use for accounting or other business purposes, and don't want to expose to other entities. For example, data such as ledger entries.|
|Normal | General data that doesn't belong to any other categories.|

## Classify fields in the data classification worksheet

Classifying the sensitivity of a large number of fields one by one takes a long time. To speed up the process, classify fields in bulk, and then fine-tune classifications for specific fields. Use the **Data Classification Worksheet** page. Your permissions must allow you to view and change data sensitivity classifications.

[!INCLUDE[open-search](includes/open-search.md)], enter **Data Classification Worksheet**, and then choose the related link.

> [!IMPORTANT]  
> When you first open the **Data Classification Worksheet** page, Business Central populates the fields for the current company. Evaluation companies can have sample classifications. To classify fields with the assisted setup guide, choose **Set Up Data Classifications**. To add fields introduced after the last synchronization, choose **Find New Fields**.

For example, the **Data Classification Worksheet** page lets you do things like:

* Use the Data Classification assisted setup guide to export your fields to an Excel worksheet where you can bulk classify them. Using the Excel worksheet is useful if you're collaborating with a Microsoft partner. After you update the worksheet, use the guide to import and apply the classifications. You can also use the guide to classify fields manually.  
* Choose a field and then filter the list to find similar fields that are likely to belong to the same classification as the field you based the search on.  
* Investigate a field by viewing its contents. Select a single `Code` or `Text` field, and then choose **Show Field Content**.

> [!TIP]  
> We defined sample sensitivity classifications for the tables and fields in the Cronus demonstration company. You can use those classifications as inspiration when you classify your own tables and fields.

## Mask or show sensitive data in fields

You can protect sensitive information by masking field values on the screen. Masking helps protect sensitive data, such as personal identifiers, financial details, or confidential notes, from casual observation or shoulder surfing. For example, you might want to mask values when people work in shared or open work environments.

The following image shows a masked field value and highlights the reveal button.

:::image type="content" source="media/masked-field.png" alt-text="Screenshot that shows a masked field value and the reveal button.":::

> [!NOTE]
> Masking provides lightweight, UI-layer-only information protection only. The unmasked data transfers to the web browser anyway.

Additional information:

* Masking isn't supported in repeater controls or on `ConfigurationDialog` pages.
* The reveal button renders on the control that lets you toggle between mask and show states.
* Masking works on desktop and mobile devices.

> [!NOTE]
> In versions where masking is optional, enable **Introduce UI support for masking sensitive data** on the **Feature Management** page. Learn more in [Introduce UI support for masking sensitive data feature key](/dynamics365/business-central/dev-itpro/developer/devenv-mask-type-feature-key).
>
> Masking was introduced in 2025 release wave 2. The availability of the feature key depends on your version.

### Information about masking for developers

The `MaskType` field-level property allows you to hide values in supported fields. Learn more in [MaskType property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-masktype-property).

When you apply the property, [!INCLUDE [prod_short](includes/prod_short.md)] masks the field's value by default, and only shows the value when you choose the reveal button in the field.

The `MaskType` property is a field-level property. You can use the property on the following types of fields:

* `Code`
* `Text`
* `Decimal`
* `Integer`
* `BigInteger`

You define the property as an `enum MaskType` with the following values:

* `None` - Shows the field value by default. Masking isn't applied.
* `Concealed` - Masks the field value in the user interface by default.

> [!NOTE]
> You can't define the `MaskType` property together with the `ExtendedDatatype` property set to `Masked`.

## Related information

[Respond to requests about personal data](admin-responding-to-requests-about-personal-data.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
