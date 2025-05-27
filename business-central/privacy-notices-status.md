---
title: Privacy Notices Status in Business Central
description: An overview of the Privacy Notices Status page in Business Central
author: brentholtorf
ms.service: dynamics-365-business-central
ms.topic: reference
ms.search.keywords:
ms.search.form: 1565
audience: 
ms.author: bholtorf
ms.date: 07/21/2022
ms.reviewer: bholtorf
---

# Privacy Notices Status in [!INCLUDE[prod_long](includes/prod_long.md)]

This article discusses what a privacy notice is and explains the purpose of the **Privacy Notices Status** page in [!INCLUDE[prod_short](includes/prod_short.md)]. You'll also learn how administrators can use this page.

## Privacy notice

A privacy notice states the data collection, data processing, and data privacy policies followed by the organizations's data controller. It's a document that describes what data is collected and for what purposes, how the user's data is processed, how it's being stored, and who to contact if a user wants to ask something about their data. 

## Privacy Notices Status page

In [!INCLUDE[prod_short](includes/prod_short.md)], if users want to integrate their data with Microsoft Exchange, Microsoft OneDrive, and Microsoft Teams, they must accept the privacy notice for each entity. Or an admin can approve the privacy notices on their behalf. Admins can see the status of privacy notices on the **Privacy Notices Status** page. You can find the **Privacy Notices Status** page in the [!INCLUDE[prod_short](includes/prod_short.md)] by typing the name of the page in the search bar.  

On that page, you'll find a table with approval options for each of the services mentioned above. 

| Column | Description |
| ----------- | ----------- | 
| **Integration Name** | Name of the service, such as Microsoft OneDrive. |
| **Agree for All** | An admin approves the privacy notice for all users. |
| **Disagree for All** | An admin does not approve the privacy notice for all users. |
| **Let User Decide** | Users decide to approve the privacy notice for the service or not. |

> [!NOTE]
> You can only view the status of privacy notices on the main **Privacy Notices Status** page. To edit the responses, go to **Edit List** on the action bar of the page where options are now clickable and not greyed out.

## Privacy Notice Approvals

Admins can see individual approvals and manage them on the **Privacy Notice Approvals** subpage. Go to the *Action* bar of the **Privacy Notices Action** page, under *Actions*, to find the *Show individual approvals* option. This option goes to the **Privacy Notice Approvals** page.<br>

On that page, you'll find a table with approval options. 

| Column | Description |
| ----------- | ----------- | 
| **Integration Name** | Name of the service, such as Microsoft OneDrive. |
| **User Name** | The user who holds this approval. If *Organization* is written in the User Name column, approval belongs to the whole organization. 
| **Agree** | The user approves the privacy notice. |
| **Disagree** | The user does not approve the privacy notice. |
| **Approver User Name** | The one who approves the privacy notice. |

## Related information

[Compliance Overview  ](/dynamics365/business-central/compliance/compliance-overview)  
[Respond to Requests about Personal Data  ](/dynamics365/business-central/admin-responding-to-requests-about-personal-data)  
[Privacy Policy and Terms of Use ](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-checklist-i-privacypolicy-termsofuse)  
[Data Retention Policies](/dynamics365-release-plan/2020wave2/smb/dynamics365-business-central/define-retention-policies) 
