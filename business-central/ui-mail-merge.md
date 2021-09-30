---
title: Using Word Templates for Bulk Communications | Microsoft Docs
description: Word templates can make it easy to bulk create documents that are personalized for specific entities.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: document, mail, merge, Word, template, email
ms.date: 04/01/2021
ms.author: bholtorf

---

# Using Word Templates for Bulk Communication
Microsoft Word templates can make it easier to mass communicate in print or email with entities such as contacts, customers, and vendors. For example, you can create brochures to alert customers about a sales campaign, letters to inform vendors about a new purchasing policy, or invitations to attract contacts to an upcoming event.

> [!NOTE]
> You can use Word templates only on devices with Microsoft Word 2019 and the Windows operating system installed.

You can use entities in [!INCLUDE[prod_short](includes/prod_short.md)] as the data source for the template, and add merge fields to personalize documents for each entity. The merge fields come from the entity in [!INCLUDE[prod_short](includes/prod_short.md)]. When you apply a Word template to an entity, data from the merge fields is inserted in the document.

On the **Word Templates** page, when you create a new template you use an assisted setup guide to download a ZIP file that contains a DataSource.xlsx and a Word template file for the entity. The data source file provides the fields that you can use in the template. Do not edit the data source file. You can only use the Word template and data source files that you download from [!INCLUDE[prod_short](includes/prod_short.md)], and you must store the files in the same location.

After you set up the template and add merge fields, you use the same guide to upload the template.

## Setting Up the Template in Word
When you are setting up a template in Word, on the **Mailings** tab you can add merge fields by choosing **Insert Merge Field**. The merge fields that are available come from the data source file that you downloaded for the entity. They act as placeholders that tell Word where in the document to put the information about the entity. 

:::image type="content" source="media/word-tmpl-merge-field.PNG" alt-text="Adding merge fields in Microsoft Word":::

## Adding Related Entities
In addition to adding data for the source entity, that is, the entity for which you're creating the template, you can also merge data from entities that are related to it. For example, if the source is the Customer entity, you can also merge data from fields on the Customer/Purchaser entity because both the entities have a field in common.

Related entities share a field, which is often an identifier such as a name, code, or ID, with the source entity. When you set up a template there are simple and advanced options for choosing related entities:

* Simple - Add known relations that [!INCLUDE[prod_short](includes/prod_short.md)] makes available by default.
* Advanced - Add non-standard relations, such as those that have been added by extensions or customizations. This requires that you know the fields that the entities share.

When you add a related entity, you must specify a prefix for the field name. When you're adding fields to the template, the prefix can make it easier to distinguish between fields from the source entity and fields from related entities.

## To create a Word template in Business Central
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Word Templates**, and then choose the related link.
2. Choose **New**, then **Create a Template**, and then follow the steps in the assisted setup guide. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]
> You can also create a template directly from the page for an entity by choosing the **Apply Word Template** action to open the assisted setup guide, and then **New Template**. When you do, the data source is chosen for you based on the type of entity.

## Applying a template
When your Word template is ready, on the **Word Templates** page you can choose **Apply** to generate the documents. When you apply a Word template to an entity, data from the merge fields is inserted in the document. You can either create one document that contains sections for each entity, or choose **Split** to create a new document for each entity.

You can apply templates to one or more of the same type of entity, such as a contact, directly in the context of that page, or from the Word Templates page to apply the template to all of the entities of that type.

## Using Word Templates with Email
You can use Word templates to add content to email messages. When you compose an email, you can choose the **Use Word Template** action to apply the content of a template to the message. This requires that you have created one or more template for the entity. You can use one template at a time, and when you switch between templates the message changes to reflect the content from the chosen template.

Additionally, you can use the **Add File from Word Template** action to attach the content of the template to the email as a file. The file will use the format you specified for the template output.

:::image type="content" source="media/email-word-tmpl.PNG" alt-text="Options for using content from a Word template in an email":::

## See Also
[Managing Report and Document Layouts](ui-manage-report-layouts.md)  
