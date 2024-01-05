---
title: Sharing Business Central records in Microsoft Teams
description: Learn how to use the Business Central app for Microsoft Teams.
author: jswymer
ms.topic: how-to
ms.service: dynamics365-business-central
ms.reviewer: jswymer
ms.search.keywords: Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork, share records
ms.date: 12/12/2023
ms.author: jswymer
ms.custom: bap-template
---

# Sharing Business Central records and page links in Microsoft Teams

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

[![Teams integration with Business Central.](media/teams-intro-vBC20.png)](media/teams-intro-vBC20.png#lightbox)

### Prerequisites

- You have access to Microsoft Teams.
- You've installed the [!INCLUDE [prod_short](includes/prod_short.md)] app in Teams. For more information, see [Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md)

> [!NOTE]
> All participants in a Teams conversation will be able to view cards for Business Central records that you submit to the conversation. But to view more details about records, by using the **Details** or **Pop out** buttons on a card, they'll need access to [!INCLUDE [prod_short](includes/prod_short.md)]. For more information, see [Managing Microsoft Teams Integration](admin-teams-integration.md#minimum-requirements-1).

### Include a Business Central card in a Teams conversation

1. Sign in to [!INCLUDE [prod_short](includes/prod_short.md)] using your browser.
2. Open the record that you want to share.

    The app is designed to display a card for almost any type of [!INCLUDE [prod_short](includes/prod_short.md)] page. But it provides the best experience when used for pages that display a single record, such as an item, customer, or sales order.
3. Copy the link to the page.

    There are two ways to copy the link. The easiest and preferred way is to select  **Share** ![Share icon in Business Central](media/share-icon.png) > **Copy Link**. The other way is to, copy the entire URL from the browser's address bar.

    [![Copy Business Central URL from browser.](media/teams-copy-link.png)](media/teams-copy-link.png#lightbox)
4. Go to Teams and start a conversation, which can be chat with a person, group of persons, or a team channel.
5. Paste the link (URL) in the message box where you compose a message.

    ![Paste Business Central URL in Teams.](media/teams-paste-url-v2.png)

    > [!TIP]
    > If you get a message like: *Business Central wants to show a preview of this link.*, it means that you don't have the Business Central app for Teams installed. To install the app, select **Show Preview** and follow the instructions.

    > [!NOTE]
    > Depending on you're Business Central version, the first time you paste a link into a conversation, you may be asked to sign in to [!INCLUDE [prod_short](includes/prod_short.md)] and give consent for the app to retrieve data. Just follow the on-screen instructions.You'll only have to do this step once.
6. Wait a moment while a card is generated in the message box.
7. When the card appears, review the contents of the card carefully for any sensitive information before sending the message. This step is important because once you send the message, everyone in the conversation can see the card.
8. If the card looks good, select **Send** to submit it to the conversation.

    > [!TIP]
    > After the card appears, and before you select **Send**, you can delete the pasted URL if you like.
9. To view more details or make changes to the record shown in the card, select **Details**. For more information, see the next section.

### View card details

Once a card's been sent to a conversation, all participants with the [proper permissions](admin-teams-integration.md#permissions) can select **Details** to open a window that displays more information about the record&mdash;and possibly make changes to the record. It doesn't matter if you're the one sending the card or the one receiving the card. The **Details** feature is especially useful to recipients, because it quickly provides them with concise, targeted information about the record.

The details window is similar to what you'd see in [!INCLUDE [prod_short](includes/prod_short.md)], but it's focused on the page or record that the card is about. When you're finished viewing and making changes, close the window to return to the Teams conversation.

Here are a couple things to keep in mind when working with the card details:

- To open the card details, users must have permission on the page and its data in [!INCLUDE [prod_short](includes/prod_short.md)]\.
- Cards in Teams chats aren't automatically updated to changes. Any changes you save to a record in the details window are saved in [!INCLUDE [prod_short](includes/prod_short.md)]\. But the card in Teams won't show the changes in the conversion, until you paste the link again.

To learn more about working with cards and card details, see [Teams FAQ](teams-faq.md).

## <a name="share-link"></a>Share a link to page from Business Central to Teams

Directly from most collection pages, like the **Items** page, and details pages, like the **Items** card, you can send a link to the page to specific recipients in a Teams conversation. For example, you can share a link to a filtered view of your records. Recipients can then select the link to open the page in [!INCLUDE [prod_short](includes/prod_short.md)]\.

[![!The Share menu displayed on a card.](media/teams-share-link-v2.png "The Share menu displayed on a card.")](media/teams-share-link-v2.png#lightbox)

### Prerequisites

- You have access to Microsoft Teams.
- (Optional) You've installed the [!INCLUDE [prod_short](includes/prod_short.md)] app in Teams. 

  With the app installed, messages you send with the link will also include a compact card for the page. For more information about how to install the app, see [Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md).

### Share a link

1. In [!INCLUDE [prod_short](includes/prod_short.md)]\, open the page that you want to share.
2. At the top of the page, choose the ![!Share to other apps action on pages.](media/share-icon.png) icon, then **Share to Teams**.
3. If you're asked, sign in to Teams with your user name and password.
4. In the **Share to Teams** page, type a name of a person, group, or channel that you want send the message to.
5. The message box includes a link to the page. If the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams is installed, a card for the linked record or page will also appear in the message box.

   Add any more information if you like, then choose **Share**.
6. The link has now been shared. If you want to go to the conversation, choose **Go to Teams**.

## See also

[Business Central and Microsoft Teams Integration Overview](across-teams-overview.md)  
[Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md)  
[Teams FAQ](teams-faq.md)  
[Searching for Customers, Vendors, and Other Contacts from Microsoft Teams](across-search-contacts-teams.md)  
[Changing Company and Other Settings in Teams](across-teams-settings.md)  
[Troubleshooting Teams](admin-teams-troubleshooting.md)  
[Developing for Teams Integration](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
