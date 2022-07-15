---
title: Privacy Notices Status in Business Central
description: An overview of the Privacy Notices Status page in Business Central
author: javariya

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.search.form: 1565
audience: 
ms.author: a-jaaamir
ms.date: 07/15/2022

---

# Privacy Notices Status in [!INCLUDE[prod_long](includes/prod_long.md)]

This article discusses what a privacy notice is and explains the purpose of the **Privacy Notices Status** page in [!INCLUDE[prod_short](includes/prod_short.md)]. We'll also describe how administrators can use this page.

## Privacy notice

A privacy notice states the data collection, data processing, and data privacy policies that are followed by the data controller of the organization. It's a document that describes what data is being collected and for what purpose, how the user's data is being processed, how it's being stored, and who to contact if a user wants to ask something about their data. 

## Privacy Notices Status Page

In [!INCLUDE[prod_short](includes/prod_short.md)], if users want to integrate their data with the Microsoft Exchange, Microsoft OneDrive, and Microsoft Teams, they need to agree or disagree to the privacy notice for each entity. Or an admin can agree or disagree to the privacy notices on their behalf. Admins can see the status of privacy notices on **Privacy Notices Status** page. You can find the **Privacy Notices Status** page in the [!INCLUDE[prod_short](includes/prod_short.md)] by writing the name of the page in the search bar. <br>
On the page, you'll find a table with options to choose from for each of the services mentioned above. 

| Column | Description |
| ----------- | ----------- | 
| **Integration Name** | Name of the service, for example, Microsoft OneDrive. |
| **Agree for All** | An admin can agree the privacy notice for all users. |
| **Disagree for All** | An admin can disagree the privacy notice for all users. |
| **Let User Decide** | Users decide whether they agree to the privacy notice for the service or not. |

>[!NOTE]
> You can only view the status of privacy notices on the main **Privacy Notices Status** page. To edit the responses, you'll go to the **Edit List** on the action bar of the page. On the *Edit List*, you'll see that now the options are clickable and not greyed out.

## Privacy Notice Approvals

Administrators can see the individual approvals and manage them on the **Privacy Notice Approvals** sub-page. If you go to the *Action* bar of the **Privacy Notices Action** page, under the *Actions*, you'll find the *Show individual approvals* option. This option will take you to the **Privacy Notice Approvals** page.<br>
On the page, you'll find the table with the following columns: 

| Column | Description |
| ----------- | ----------- | 
| **Integration Name** | Name of the service, for example, Microsoft OneDrive. |
| **User Name** | The user who holds this approval. If *Organization* is written under the User Name column, that means the approval belongs to the whole organization. |
| **Agree** | The user agreed to the privacy notice. |
| **Disagree** | The user disagreed to the privacy notice. |
| **Approver User Name** | The one who approved the privacy notice. |

## See also

[Compliance Overview](/dynamics365/business-central/compliance/compliance-overview)  
[Respond to Requests about Personal Data ](/dynamics365/business-central/admin-responding-to-requests-about-personal-data)  
[Privacy Policy and Terms of Use ](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-checklist-i-privacypolicy-termsofuse)  
[Data retention policies](/dynamics365-release-plan/2020wave2/smb/dynamics365-business-central/define-retention-policies) 
