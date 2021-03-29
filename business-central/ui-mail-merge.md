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
Microsoft Word templates can make it easier to mass communicate with entities such as customers and vendors. For example, you can create brochures to alert customers about a sales campaign, letters to inform vendors about a new purchasing policy, or invitations to attract contacts to an upcoming event.

You can use entities in [!INCLUDE[prod_short](includes/prod_short.md)] as the data source for the template, and add merge fields to personalize documents for each entity. The merge fields come from the entity in [!INCLUDE[prod_short](includes/prod_short.md)]. When you apply a Word template to an entity, data from the merge fields is inserted in the document.

On the **Word Templates** page, you can use an assisted setup guide to download a ZIP file that contains a DataSource.txt and a Word template file for an entity. After you set up the template and add merge fields, you use the same guide to upload the template. You can only use the Word template and data source files that you download from [!INCLUDE[prod_short](includes/prod_short.md)], and you must store the files in the same location.

> [!NOTE]
> When you choose an entity for which to create a template, the list shows all entities in [!INCLUDE[prod_short](includes/prod_short.md)]. However, you cannot create templates for all entities. If the name of an entity contains special characters, such as **/**, **.**, **_**, or **-**, you cannot create a template for it. The name of the entity is shown in the **Object Caption** column.

When you are setting up the template in Word, on the **Mailings** tab you can add merge fields by choosing **Insert Merge Field**.

> [!NOTE]
> You cannot use merge fields if the name of the field contains 40 characters or more. For example, you cannot use the Company__Information_Customs_Permit_Date field because it has 40 characters. 

When your Word template is ready, on the **Word Templates** page you can choose **Apply** to generate the documents. You can either create one document that contains sections for each entity, or split the operation to create a new document for each entity.

## To create a Word template
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Word Templates**, and then choose the related link.
2. Follow the steps in the assisted setup guide. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## See Also
[Managing Report and Document Layouts](ui-manage-report-layouts.md)  
