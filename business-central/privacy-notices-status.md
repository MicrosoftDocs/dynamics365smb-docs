---
title: Privacy Notices Status in Business Central
description: Review and manage privacy notice approvals for connected services in Business Central, including decisions for all users and individual user responses.
author: brentholtorf
ms.service: dynamics-365-business-central
ms.topic: reference
ms.search.form: 1565
ms.author: bholtorf
ms.date: 11/12/2026
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Privacy notices status in Business Central

This article discusses what a privacy notice is and explains the purpose of the **Privacy Notices Status** page in [!INCLUDE[prod_short](includes/prod_short.md)]. You'll also learn how administrators can use this page.

## Understand privacy notices

A privacy notice states the data collection, data processing, and data privacy policies followed by the organization's data controller. It's a document that describes what data is collected and for what purposes, how the user's data is processed, how it's being stored, and who to contact if a user wants to ask something about their data.

## Manage privacy notices for all users

Connected features in [!INCLUDE[prod_short](includes/prod_short.md)] can require a privacy notice. Users can accept a notice for themselves, or an administrator can accept it for all users. Some notices can be accepted automatically, such as in evaluation companies. An administrator's decision takes precedence over individual user decisions.

Administrators can review the notices on the **Privacy Notices Status** page. To manage approvals, you need permissions such as those in the **Privacy Notice - Admin** permission set.

[!INCLUDE[open-search](includes/open-search.md)], enter **Privacy Notices Status**, and then choose the related link.

The page lists the privacy notices for connected services and the decision for each notice.

| Column | Description |
| ----------- | ----------- | 
| **Integration Name** | Name of the service, such as Microsoft OneDrive. |
| **Agree for Everyone** | An administrator accepts the privacy notice for all users. The notice can also be accepted automatically where the service permits it. |
| **Disagree for Everyone** | An administrator declines the privacy notice for all users, preventing them from using the integration that requires it. |
| **Let Users Decide** | Users decide whether to accept the privacy notice for themselves. This choice clears the administrator's decision for all users but doesn't clear existing individual decisions. |

> [!NOTE]
> To change the decisions on the **Privacy Notices Status** page, choose **Edit List**. The **Approve All** action accepts every privacy notice in the list for all users.

## Review individual privacy notice approvals

On the **Privacy Notices Status** page, choose **Show individual approvals** to open the **Privacy Notice Approvals** page. Administrators can review individual and organization-wide decisions. The fields on this page are read-only.

The page lists the recorded decisions.

| Column | Description |
| ----------- | ----------- | 
| **Integration Name** | Name of the service, such as Microsoft OneDrive. |
| **User Name** | The user whose decision is recorded. **\<Organization\>** indicates a decision for all users. |
| **Agree** | The privacy notice is accepted for the user or organization. |
| **Disagree** | The privacy notice is declined for the user or organization. |
| **Approver User Name** | The user who recorded the agreement or disagreement. |

## Related information

[Compliance Overview  ](/dynamics365/business-central/compliance/compliance-overview)  
[Respond to requests about personal data](admin-responding-to-requests-about-personal-data.md)  
[Privacy Policy and Terms of Use ](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-checklist-i-privacypolicy-termsofuse)  
[Data retention policies](admin-data-retention-policies.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
