---
title: Add contacts to segments
description: Add contacts to a segment after creating it to target specific customers or clients as part of a marketing campaign.
author: jswymer
ms.topic: how-to
ms.devlang: al
ms.search.keywords: marketing, campaign, promo, prospect, contact, client, customer
ms.search.form: 5091, 5093
ms.date: 10/03/2025
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ms.custom: bap-template
---

# Add contacts to segments

After you create a segment, you might want to add contacts to it. You can add contacts by filling in the lines on the **Segment** page manually, but it's easier and faster to use the **Add Contacts** action.

## Add a contact to a segment

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Segments**, and then choose the related link.  
2. Select the segment, and then choose the **Add Contacts** action. The **Add Contacts** batch job page opens.
3. In the **Contact** section, set filters to specify the information by which you want to select contacts.

To enter more filters, repeat this procedure on each of the remaining sections, and then choose the **OK** button.

If you added contacts by mistake and want to go back one step, then choose the **Go Back** action.

## Refine the number of contacts

After selecting the contacts within a segment, you might decide to remove some but keep others. You can manually remove contacts from the lines on the **Segment** page, but it's easier and faster to use the **Refine Contacts** action.

1. Open the segment.
2. Choose **Contacts**, and then choose the **Refine Contacts** action. The **Remove Contacts - Refine** page opens.
3. In the **Contact** section, enter filters to specify the information that you want to use to select the contacts to be removed from the segment.
4. Add more filters as needed, and then choose the **OK** button.

You can refine a segment as many times as you want. If you refined the segment by mistake and want to go back one step, choose the **Go Back**.

To review a list of the segment criteria that you used, in the **General** section, choose the **No. of Criteria Actions** field.

## Reduce the number of contacts

After you select the contacts within a segment, you might want to remove some of them. You can remove them manually from the lines on the **Segment** page. However, it's easier and faster to use the **Reduce Contacts** action to specify the contacts to remove, and to use the **Refine Contacts** action to specify the contacts to keep.

1. Open the segment.
2. Choose **Contacts**, and then choose the **Reduce Contacts** action. The **Remove Contacts - Reduce** page opens.
3. In the **Contact** section, enter filters to specify the information that you want to use to select the contacts to be removed from the segment.
4. Add more filters as needed, and then choose the **OK** button.

You can reduce a segment as many times as you want. If you refined the segment by mistake and want to go back one step, choose the **Go Back** action.

## Related information

[Create a Segment](marketing-how-create-segment.md)  
[Manage Segments](marketing-segments.md)  
[Manage Sales Opportunities](marketing-manage-sales-opportunities.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
