---
title: Working with Business Central Data in Microsoft Teams| Microsoft Docs
description: Share Business Central records directly in a Teams conversation.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.date: 07/10/2020
ms.author: jswymer
---

# Using Microsoft Teams with Business Central

[!INCLUDE [prodshort](includes/2020rw_online_only.md)]

[Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/microsoft-teams) is a Microsoft 365 product that lets you meet, chat, call, and collaborate with people you work with. [!INCLUDE [prodshort](includes/prodshort.md)] offers an app that connects Microsoft Teams to your business data in [!INCLUDE [prodshort](includes/prodshort.md)], so you can quickly share details across team members and respond faster to inquiries.

## Overview

The [!INCLUDE [prodshort](includes/prodshort.md)] app lets you:

- Copy a link to any Business Central record and paste it into a Teams conversation to share with your coworkers. The link will expand that into a compact, interactive card that displays information about the record.
- Once in the conversation, you and coworkers can view more details about the record, edit data, and take action - without leaving Teams.

[![Teams integration with Business Central](media/teams-intro-v3.png)](media/teams-intro-v3.png#lightbox)

The app is available on the Teams marketplace, and you can use it with the Teams web, desktop, or mobile app.

## Prerequisites

- A Microsoft Teams (subscription

    I don't have a Microsoft 365 account. How do I access Microsoft Teams?
To use Microsoft Teams, you need a Microsoft 365 account with the appropriate Microsoft 365 license plan listed below. Talk to your company's IT administrator to get an account or sign your company up for Microsoft 365.
- Permissions in Business Central
  - To paste a [!INCLUDE [prodshort](includes/prodshort.md)] link into a Teams conversation and have it expand into a card, you have to have at least permission to read to the target page and its data.
  - Once a card is submitted into a conversation, any user in that conversation can view that card without permission to Business Central. However, to view more details for a card, you and other users must have read permission on the page and its data. If they want to change data, they'll need modify permissions.


## Add the Business Central app to Teams

1. Open and sign in to Teams.
2. In the left side, select **Apps**.
3. Search for **Dynamics 365 Business Central**.
4. Select the app when you find it.
5. Read read the information and select **Add**.

## Include a Business Central card in a Teams conversation

1. Sign in to [!INCLUDE [prodshort](includes/prodshort.md)] using your browser.
2. Open the record that you want to share.

    The app is designed to display card type pages from [!INCLUDE [prodshort](includes/prodshort.md)]. So open a page that displays a single record, like an item, customer, or sales order. You can't use it for role centers or pages that display several records in a list.

3. Copy the entire URL from the browser's address bar.
4. Go to Teams and start a conversation.
5. Paste the URL into the box where you add a message.
6. The first time you paste a link into a conversation, you'll be asked to sign in to [!INCLUDE [prodshort](includes/prodshort.md)] and give consent for the app to retrieve data. Just follow the on-screen instructions.

    > [!NOTE]
    > You'll only have to do this step once or until you change which [!INCLUDE [prodshort](includes/prodshort.md)] environment Teams connect to.

7. Wait a moment while a card is generated in the message box.

8. When the card appears, select **Send** to submit the card to the conversation.

    > [!TIP]
    > After the card appears, and before you select **Send**, you can delete the pasted URL if you like.

9. To view more details or make changes to the record, select **Details**.

    The details page is similar to what you'd see in [!INCLUDE [prodshort](includes/prodshort.md)]. But it's slightly trimmed down for Teams. When you're finished viewing and making changes, close the window to return to the Teams conversation.

## See Also

[Getting Started](product-get-started.md)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
