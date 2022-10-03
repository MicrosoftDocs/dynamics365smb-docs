---
title: Use Power Automate Flows in Business Central
description: Set up and use Power Automate flows to create or modify Business Central data.
author: jswymer
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: workflow, OData, Power App, SOAP, Power Automate, 
ms.search.form: 1500, 
ms.date: 09/13/2022
ms.author: jswymer
---

# Use Power Automate Flows in [!INCLUDE[prod_short](includes/prod_short.md)]

You can use your [!INCLUDE[prod_short](includes/prod_short.md)] data as part of a workflow in Microsoft Power Automate. Create your own flows and connect to your data from internal and external sources with the [!INCLUDE [prod_short](includes/prod_short.md)] connector.

> [!NOTE]
> You must have a valid account with both [!INCLUDE[prod_short](includes/prod_short.md)] and Power Automate.  

> [!TIP]
> In addition to Power Automate, you can use approval workflow templates in [!INCLUDE[prod_short](includes/prod_short.md)]. Although they're two separate workflow systems, any approval workflow template you create with Power Automate is added to the list of workflows within [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more at [Workflows](across-workflow.md).

Power Automate flows are triggered by events such as record and document creation, modification, or deletion (automated flows). The flows can also run on a user-defined schedule (scheduled flows) or on demand (instant flows).

## Power Automate features in [!INCLUDE[prod_short](includes/prod_short.md)]

Flows expand on the built-in approval workflows features available in [!INCLUDE[prod_short](includes/prod_short.md)] without requiring coding knowledge, and can be associated with a wide range of events and responses, such as record changes, external files updates, posted documents, as well as different Microsoft and third-party services such as Microsoft Outlook, Microsoft Excel, Microsoft Dataverse, Microsoft Teams, Microsoft SharePoint, Microsoft Power Apps, and more.

So, for example, a new sales invoice can trigger a workflow for an approval request, which can have different events set depending on the approver's reply. A negative response sends a notification and email to the approval requester. A positive reply simultaneously updates an Excel spreadsheet located in a SharePoint folder and sends an update to a Teams chat.

Instant flows work similarly to batch shortcuts, performing multiple lengthy steps with a few button presses and are launched from specific pages or tables. For example, a flow can add a button to the action menu on the **Vendors** page to block payments to a vendor and, at the same time, send customizable emails to the vendor's contact and your company's purchasers as well as update the contact in Outlook.

## Get started

When you or any user sign in to the new company for the first time, this feature displays the **Get started with Power Automate** action in the **Automate" group**. 

![<!--alt text start -->Get started with Power Automate action<!--alt text end -->](media/get-started-power-automate-action.png "Get started with Power Automate action")

The **Get started with Power Automate** action opens a new wizard that consists of some onboarding information and links and the necessary privacy notice. When accepted by the administrator, all the users will be able to see the Automate group and actions coming from defined flows.

In addition, an individual user's access can be controlled by a new system permission **Allow Action Automate** and a ready-to-use permission set **AUTOMATE - EXEC**. Revoking this permission from a given user or role will hide the Automate group and prohibit running the actions created with Power Automate.

Additionally for admins who would decide to fully switch the feature off for all users, the easiest way is to use TellMe (Alt+Q) to navigate to "Privacy Notices Status" page, find "Power Automate" entry and select "Disagree for Everyone".

## Automated workflows

With Power Automate, you can create business flows directly in-house and rely on citizen developers. Automated workflows can be started by both internal and external events in [!INCLUDE[prod_short](includes/prod_short.md)], and also be set to run periodically. Learn more and get instructions on how to create workflows in the [Set Up Automated Workflows](/dynamics365/business-central/dev-itpro/powerplatform/automate-workflows) article in the administration content.

## Instant flows

[!INCLUDE [prod_short](includes/prod_short.md)] can run a Power Automate flow from most list, card, and document pages. Once the admin has connected [!INCLUDE [prod_short](includes/prod_short.md)] with Power Automate, you'll see any flows your organization has added when you choose the **Automate** action on the relevant pages. Instant flows are run without leaving [!INCLUDE [prod_short](includes/prod_short.md)]. Learn more in the [Set Up Automated Workflows](/dynamics365/business-central/dev-itpro/powerplatform/automate-workflows) article in the administration content.

These instant workflows open on a page inside [!INCLUDE [prod_short](includes/prod_short.md)] online so you can remain within the context of the business process you were in the middle of. Choose the **Automate** action—on some pages nested under the **More Options** menu—choose the **Power Automate** menu item, then choose the relevant link to trigger the workflow. The connection to Power Automate is already set up for you.

Most flows require you to fill in a field or two before you choose the **Run flow** action.

> [!TIP]
> If you don't see an **Automate** action, then your [!INCLUDE [prod_short](includes/prod_short.md)] probably hasn't yet been set up to use Power Automate. Learn more from your admin.

## Add more automated flows and instant flows

You can create flows through the [powerautomate.microsoft.com](https://powerautomate.microsoft.com) website. However, if your admin has switched on the capability to run Power Automate flows from inside [!INCLUDE [prod_short](includes/prod_short.md)] online, you can start the process of building a flow from the **Automate** action on the relevant pages, which can be found under the **More Options** menu depending on the page. Then choose the **Power Automate** menu item, and then choose the **Create a flow** action. Power Automate then opens in a new browser tab, and you're signed in automatically.

You can find sample templates to adapt to your company and all available trigger events, using both [!INCLUDE [prod_short](includes/prod_short.md)] and external tools, by choosing the **Connectors** menu on the Power Automate website. Learn more about available templates and triggers in the [Set Up Automated Workflows](/dynamics365/business-central/dev-itpro/powerplatform/automate-workflows) article in the administration content.

## Manage automated workflows

You can create new flows or manage existing Power Automate flows in [!INCLUDE [prod_short](includes/prod_short.md)] on the **Manage Power Automate Flows** page. Learn more in the [Manage Power Automate Flows](/dynamics365/business-central/dev-itpro/powerplatform/manage-power-automate-flows) article in the administration content.

You can also manage available Power Automate workflows on the **Workflows** page in [!INCLUDE[prod_short](includes/prod_short.md)]. The page lists both the built-in approval and Power Automate workflows, with options for the latter to enable/disable, delete, and view the workflow on the Power Automate website.

## See related [Microsoft training](/training/modules/use-power-automate/)

## See also

[Troubleshoot Your [!INCLUDE[prod_short](includes/prod_short.md)] Automated Workflows](across-flow-troubleshoot.md)  
[Get Ready for Doing Business](ui-get-ready-business.md)  
[Workflows](across-workflow.md)  
[Import Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Set Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Finance](finance.md)  
[Manage Power Automate Flows](/dynamics365/business-central/dev-itpro/powerplatform/manage-power-automate-flows)  
[Set Up Automated Workflows](/dynamics365/business-central/dev-itpro/powerplatform/automate-workflows)  
[Switch on Instant Flows](/dynamics365/business-central/dev-itpro/powerplatform/instant-flows)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
