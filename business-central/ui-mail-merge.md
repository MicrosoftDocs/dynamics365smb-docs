---
title: Using Word templates for bulk communications
description: Word templates can make it easy to bulk create documents that are personalized for specific entities.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 11/13/2024
ms.custom: bap-template
ms.search.forms: 9989_Primary, 13, 9992_Primary, 9983_Primary
ms.service: dynamics-365-business-central
---

# Use Word templates for bulk communication

Microsoft Word templates can make it easier to mass communicate in print or by email with contacts, customers, and vendors. For example, you can create:

* Brochures to alert customers about a sales campaign
* Letters to inform vendors about a new purchasing policy
* Invitations to attract contacts to an upcoming event

> [!NOTE]
> When you set up Word templates, you must use a device with Microsoft Word 2019 or newer and have the Windows operating system installed.

## Set up the source of data

Use entities in [!INCLUDE[prod_short](includes/prod_short.md)] as the source of data for the template, and add merge fields to personalize documents for each entity. The merge fields come from the entity in [!INCLUDE[prod_short](includes/prod_short.md)]. When you apply a Word template to an entity, data from the merge fields is inserted in the document.

On the **Word Templates** page, when you create a new template an assisted setup guide helps you through the following steps:

1. Choose one or more entities to use as the source of the data. For example, if you want to create a brochure for a sales campaign, you'd probably choose the Customer entity as the source.
2. Choose other entities as extra sources of data. Learn more at [Add Entries that are Related or Unrelated to the Source Entity](#add-entries-that-are-related-or-unrelated-to-the-source-entity).
3. Download a blank template. You can set up the template in Word right away, or you can upload the blank template and finish the guide. When your template's ready, use the **Upload** action on the **Word Templates** page to replace the blank template with your finished template. Learn more at [Set Up the Template in Word](#set-up-the-template-in-word).
4. Upload the template you prepared.
5. Enter a code and a name that identifies the template.

When you download a template, you get a .zip file that includes two files.

|File  |Description  |
|---------|---------|
|DataSource.xlsx     | The data source file provides the fields that you can use in the template. Don't edit the data source file. You can only use the Word template and data source files that you download and you must store the files in the same location.     |
|Word template     | A .docx file to use as the template.        |

To learn about setting up a template in Word, go to [Set Up the Template in Word](#set-up-the-template-in-word).

## Add entries that are related or unrelated to the source entity

You can also merge data from other entities. To add other entities as data sources, use one of the following actions on the **Word Templates** page or when you're using the assisted setup guide:

|Action  |Description  |
|---------|---------|
|**Add related entity**  | Use data from entities that are related to the source entity. For example, for the Customer entity you can also merge data from the Contact entity. Entities are related when a field on one entity refers to another. A field on the Customer entity refers to a field on the Contact entity, so they're related. The shared field is often an identifier such as a name, code, or ID.        |
|**Add unrelated entity**| Use data from entities that aren't related to the source entity. For example, you're creating a template for the Customer entity. You might add the Company Information entity so you can include your contact details. A key benefit is that if you change your contact information, it automatically updates in your template. After you add an unrelated entity, you can add entities that are related to it.         |

For unrelated entries, you choose a specific record. Because you can only add an entity one time, to use a different record you must delete the entity and add it again with the new record.

You can create a hierarchy of entities, both related and unrelated. The relation is shown as a tree structure. The **Entity relation** field also shows information about the relation. For unrelated entities, the field shows the record that creates the relation.

When you add entities, use the **Field Prefix** field to specify a prefix for the field names. Later, when you add fields to the template, the prefix helps distinguish between fields from the source and other entities.

### Select the fields to include

For each entity, you can specify the fields that you want to be available for the template. Choose the number in the **Number of Selected fields** column to access a list of fields that are available. On the **Field Selection** page, use the **Include** checkbox to specify the fields. For some entities, fields that businesses typically use are included by default. You can edit the list, for example, to remove the default fields. Your changes apply only to the template you're working on.

> [!NOTE]
> The total number of fields that you can add from all entities is 250.

> [!NOTE]
> You or your Microsoft partner can add custom fields to entities. When you do, we prefix the name of the fields with **CALC** and give them the field type **Calculated**. The field type is called calculated to indicate the field can show different types of values, such as text, numbers, dates, and so on.

## To create a Word template in Business Central

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Word Templates**, and then choose the related link.
2. Choose **New**, then **Create a Template**, and then follow the steps in the assisted setup guide. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]
> You can also create a template directly from the page for an entity by choosing the **Apply Word Template** action to open the assisted setup guide, and then **New Template**. When you do, the data source is chosen for you based on the type of entity.

## Set up the template in Word

When you're setting up a template in Word, on the **Mailings** tab you can add merge fields by choosing **Insert Merge Field**. The merge fields come from the data source file that you downloaded for the entity. They act as placeholders that tell Word where in the document to put the information about the entity.

:::image type="content" source="media/word-tmpl-merge-field.PNG" alt-text="Adding merge fields in Microsoft Word":::

## Apply a template

When your Word template is ready, on the **Word Templates** page you can choose **Apply** to generate the documents. When you apply a Word template to an entity, data from the merge fields is inserted in the document. You can either create one document that contains sections for each entity, or choose **Split** to create a new document for each entity.

You can use the **Apply Word Templates** action to apply templates to one or more of the same type of entity, such as a customer, directly in the context of the page for the entity. For example, the **Customer** or **Vendor** pages.

## Use Word templates with email

You can use Word templates to add content to email messages. When you compose an email, you can choose the **Use Word Template** action to apply the content of a template to the message. You must already have templates for the entity. You can use one template at a time, and when you switch between templates the message changes to reflect the content from the chosen template.

Additionally, you can use the **Add File from Word Template** action to attach the content of the template to the email as a file. The file uses the format you specified for the template output.

:::image type="content" source="media/email-word-tmpl.PNG" alt-text="Options for using content from a Word template in an email":::

## Edit a Word template

You can make the following changes to your Word templates:

* To edit the body text or merge fields included in the template, use the **Download** action, make your changes, and then use the **Upload** action
* To change the sources of data, use the **Edit related entities** action
* To replace the Word template with a new template, use the **Upload** action
* Delete the template

## Related information

[Managing Report and Document Layouts](ui-manage-report-layouts.md)  
[Set Up Email](admin-how-setup-email.md)  
