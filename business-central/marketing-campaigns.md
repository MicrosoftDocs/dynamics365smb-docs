---
title: Set up marketing campaigns in Business Central
description: Describes how you can set up and conduct marketing campaigns in Business Central to help you identify and attract prospects and retain customers.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: marketing, campaign, promo, prospect
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ms.custom: bap-template
---

# Manage marketing campaigns

Having a strong marketing plan in place enables you to identify, attract, and retain customers. A marketing plan consists of various campaigns and other interactions with your sales and marketing activities. While you plan a campaign, you make a few decisions:

- Which contacts to target
- What type campaign you want to run (such as trade shows or direct mail)
- What tasks salespeople perform

Each campaign has various activities or tasks. You can combine multiple tasks in activities. For example, when each task represents a step. Activity tasks are related to each other by a date formula. Individual tasks can only be assigned to salespeople. Activities can be assigned to opportunities, salespeople, groups of sales people, and contacts. Learn more at [Set Up Opportunity Sales Cycles and Cycle Stages](marketing-how-setup-opportunity-sales-cycles-stages.md).

## Define individual campaigns

Before you can create a campaign, you must set up *campaign status codes*. Using these codes help you manage your campaigns by assigning a status to the campaign. As you work through the stages of a campaign, you're able to see what step a campaign is at and what step comes next. You set up campaign status codes on the **Campaign Status** page.

You can create a campaign card for each campaign that you want to keep track of. You can also view these campaign cards to view general information about your campaigns.
You can delete campaign entries, such as if the entry records an action that is canceled. Only canceled campaign entries can be deleted.

### Select the target audience

After you create a campaign, you can create segments that specify its target audience. Learn more at [Managing Segments](marketing-segments.md).

### Register discount percentages

After you set up your campaign, you can register a discount percentage that the customer receives. You register the discount percentage on individual items on the **Sales Line Discounts** page. You can also register the sales prices for the individual items on the lines on the **Sales Prices** page. You can access both pages from the campaign card.

After you set up the sales prices/line discounts and the segments on the campaign card, you must activate them so that the campaign prices/discounts are reflected on the lines.

> [!NOTE]  
> In order to activate the sales prices/line discounts, you must specify if the whole segment or only some contacts are targets of the campaign. If the sales prices/line discounts covers all the contacts in the segment, select the **Campaign Target** field on the **Campaign** FastTab of the **Segment** card.

If the sales prices/line discounts aren't to be offered to all the contacts in the segment, you can clear the **Campaign Target** field for the relevant contacts. If you can't see this field, you can add it to your view. Learn more in [Personalize Your Workspace](ui-personalization-user.md).

## Conduct campaigns

As a campaign runs, all interactions with your contacts, or segment, are recorded so that you can get statistics and other information about the costs and success rates of the campaign.

Salespeople run campaigns, and you must create activities to represent each task and assign them to the relevant salespeople. Learn more at [Set Up Opportunity Sales Cycles and Cycle Stages](marketing-how-setup-opportunity-sales-cycles-stages.md).

## Related information

[Manage Contacts](marketing-contacts.md)  
[ManageSegments](marketing-segments.md)  
[Manage Sales Opportunities](marketing-manage-sales-opportunities.md)  
[Work with Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
