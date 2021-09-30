---
title: Sharing Business Central Records in Microsoft Teams
description: Learn how to use the Business Central app for Microsoft Teams.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork, share records
ms.date: 05/19/2021
ms.author: jswymer
---

# Sharing Business Central Records and Page Links in Microsoft Teams

[!INCLUDE [online_only](includes/online_only.md)]

[!INCLUDE [prod_short](includes/prod_short.md)] offers a couple ways to share data from Business Central directly in a Microsoft Teams conversation:

<!-- 
## Overview
In this article, you'll learn how to use the app to share [!INCLUDE [prod_short](includes/prod_short.md)] records, like a customer, sales order, or invoice, with coworkers in a Teams conversation.
The [!INCLUDE [prod_short](includes/prod_short.md)] app lets you:
[!INCLUDE [prod_short](includes/prod_short.md)] offers an app that connects Microsoft Teams to your business data in [!INCLUDE [prod_short](includes/prod_short.md)], so you can quickly share details across team members and respond faster to inquiries. In this article, you'll learn how to use the app to share [!INCLUDE [prod_short](includes/prod_short.md)] records, like a customer, sales order, or invoice, with coworkers in a Teams conversation.

-->
- With the [!INCLUDE [prod_short](includes/prod_short.md)] app installed in Teams, you can include an interactive card of Business Central record in a Teams conversation.

<!--   Copy a link from any Business Central record, like a customer or sales order, then paste the link into a Teams conversation. The app connects Microsoft Teams to your business data in [!INCLUDE [prod_short](includes/prod_short.md)]. It then expands the link into a compact, interactive card that displays information about the record. Once in the conversation, you and coworkers can view more details about the record, edit data, and take action&mdash;without leaving Teams.

  [![Teams integration with Business Central.](media/teams-intro-v3.png)](media/teams-intro-v3.png#lightbox)-->

- With or without the [!INCLUDE [prod_short](includes/prod_short.md)] app installed, you can share a link from pages in Business Central to a Teams conversation.

  <!-- ![!The Share menu displayed on a card.](media/teams-share-link.png "The Share menu displayed on a card.")-->

The following sections describe the different ways in detail.

## Include and view a Business Central card in a Teams conversation

With the Business Central app for Teams, you can copy a link from any Business Central record, like a customer or sales order, and paste the link into a Teams conversation. The app connects Microsoft Teams to your business data in [!INCLUDE [prod_short](includes/prod_short.md)]\. It then expands the link into a compact, interactive card that displays information about the record. Once in the conversation, you and coworkers can view more details about the record, edit data, and take action&mdash;without leaving Teams.

[![Teams integration with Business Central.](media/teams-intro-v3.png)](media/teams-intro-v3.png#lightbox)

### Prerequisites

- You have access to Microsoft Teams.
- You've installed the [!INCLUDE [prod_short](includes/prod_short.md)] app in Teams. For more information, see [Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md)

> [!NOTE]
> All participants in a Teams conversation will be able to view cards for Business Central records that you submit to the conversation. But to view more details about records, by using the **Details** or **Pop out** buttons on a card, they'll need access to [!INCLUDE [prod_short](includes/prod_short.md)]. For more information, see [Managing Microsoft Teams Integration](admin-teams-integration.md#minimum-requirements-1).

### Include a Business Central card in a Teams conversation

1. Sign in to [!INCLUDE [prod_short](includes/prod_short.md)] using your browser.
2. Open the record that you want to share.

    The app is designed to display card type pages from [!INCLUDE [prod_short](includes/prod_short.md)]\. So open a page that displays a single record, like an item, customer, or sales order. You can't use it for role centers or pages that display several records in a list.

3. Copy the entire URL from the browser's address bar.

   ![Copy Business Central URL from browser.](media/teams-url-v2.png)
4. Go to Teams and start a conversation, which can be chat with a person, group of persons, or a team channel.

    <!--Teams imposes a few limitations here eg. you cannot unfurl a link during a Voice/Video call :/ We should probably only mention this in a Troubleshooting section (and i hope it will also be fixed soon)-->
5. Paste the URL in the message box where you compose a message.

   ![Paste Business Central URL in Teams.](media/teams-paste-url-v2.png)
6. The first time you paste a link into a conversation, you'll be asked to sign in to [!INCLUDE [prod_short](includes/prod_short.md)] and give consent for the app to retrieve data. Just follow the on-screen instructions.

    > [!NOTE]
    > You'll only have to do this step once.

7. Wait a moment while a card is generated in the message box.

8. When the card appears, review the contents of the card carefully for any sensitive information before sending the message. This step is important because once you send the message, everyone in the conversation can see the card.

9. If the card looks good, select **Send** to submit it to the conversation.

    > [!TIP]
    > After the card appears, and before you select **Send**, you can delete the pasted URL if you like.

10. To view more details or make changes to the record shown in the card, select **Details**. For more information, see the next section.

### View card details

Once a card's been sent to a conversation, all participants with the [proper permissions](admin-teams-integration.md#permissions) can select **Details** to open a window that displays more information about the record&mdash;and possibly make changes to the record. It doesn't matter if you're the one sending the card or the one receiving the card. The **Details** feature is especially useful to recipients, because it quickly provides them with concise, targeted information about the record, as opposed to having to scan the full record.

The details window is similar to what you'd see in [!INCLUDE [prod_short](includes/prod_short.md)] the record. But it's slightly trimmed for Teams. When you're finished viewing and making changes, close the window to return to the Teams conversation.

Here are a couple things to keep in mind when working with the card details:

- To open the card details, users must have permission on the page and its data in [!INCLUDE [prod_short](includes/prod_short.md)]\.
- Cards in Teams chats aren't automatically updated to changes. Any changes you save to a record in the details window are saved in [!INCLUDE [prod_short](includes/prod_short.md)]\. But the card in Teams won't show the changes in the conversion, until you paste the link again.

To learn more about working with cards and card details, see [Teams FAQ](teams-faq.md).

## <a name="share-link"></a>Share a link to page from Business Central to Teams

Directly from most collection pages, like the **Items** page, and details pages, like the **Items** card, you can send a link to the page to specific recipients in a Teams conversation. For example, you can share a link to a filtered view of your records. Recipients can then select the link to open the page in [!INCLUDE [prod_short](includes/prod_short.md)]\.

 ![!The Share menu displayed on a card.](media/teams-share-link.png "The Share menu displayed on a card.")

### Prerequisites
You have access to Microsoft Teams.

### Share a link

1. In [!INCLUDE [prod_short](includes/prod_short.md)]\, open the page that you want to share.
2. At the top of the page, choose the ![!Share to other apps action on pages.](media/share-icon.png) icon, then **Share to Teams**.
3. If you're asked, sign in to Teams with your user name and password.
4. In the **Share to Teams** page, type a name of a person, group, or channel that you want send the message to. 
5. The message box will include a link to the page. Add any more information if you like, then choose **Share**.
6. The link has now been shared. If you want to go to the conversation, choose **Go to Teams**.

## See Also

[Business Central and Microsoft Teams Integration Overview](across-teams-overview.md)  
[Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md)  
[Teams FAQ](teams-faq.md)  
[Searching for Customers, Vendors, and Other Contacts from Microsoft Teams](across-search-contacts-teams.md)  
[Changing Company and Other Settings in Teams](across-teams-settings.md)  
[Troubleshooting Teams](admin-teams-troubleshooting.md)  
[Developing for Teams Integration](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]