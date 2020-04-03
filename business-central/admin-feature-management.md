---
title: Enabling upcoming features ahead of time
description: Learn how to enable select features ahead of time. 
author: mikebcMSFT

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.workload: na
ms.reviewer: na
ms.search.keywords: administration, tenant, admin, environment, key, optional, feature management, early access, preview
ms.date: 04/03/2020
ms.author: mikebc
---

# Enabling upcoming features ahead of time

This document describes how administrators can turn on new features using the Feature Management page.


## About Feature Management

Some new features can be enabled ahead of time on sandbox and production environments, allowing you to benefit as early as possible, and giving you the time you need to test and prepare your organization for change.

When Microsoft releases features or feature design improvements as part of minor updates, some of these are not immediately enabled. Administrators can learn about these features and independently enable each feature from the **Feature Management** page. When a feature is enabled, it becomes available for all users on that environment no matter how they access [!INCLUDE[prodshort](includes/prodshort.md)]. Features can be safely turned off again.

These features are only optional for a period of time, typically starting from the minor update in which they are made generally available until they become mandatory and automatically enabled in a later major upate. The approximate date and service update when each feature is expected to become mandatory is described in the **Automatically enabled from** field in the Feature Management page. After this date, the feature will no longer appear in the Feature Management page and can no longer be turned off.

> [!IMPORTANT]
> The projected timeline for a feature is subject to change (see [Microsoft policy](https://go.microsoft.com/fwlink/p/?linkid=2007332)).


### Example timeline for an optional feature

> [!div class="mx-imgBorder"]
> ![Example timeline for an optional feature](../media/timeline-optional-features.png "An example timeline for an optional feature in the Feature Management page")

Learn about [What's new and planned](https://aka.ms/dynamics365releaseplan).  
Learn about [new features available in the last minor update](https://aka.ms/bclastminorupdate).  

> [!TIP]
> To prepare for an upcoming feature, consider enabling the feature on a sandbox environment that has a copy of production data. Inviting business users to test out the change using real-world tasks. Once you and your users are satisfied with the change, you can then enable it on production environments where they can immediately benefit from that feature.  


## How to enable an optional feature
1. Sign in to your environment and navigate to the **Feature Management** page, or use this link: [https://businesscentral.dynamics.com/?page=2610](https://businesscentral.dynamics.com/?page=2610).  
2. If the page is not editable, choose **Edit List** from the action menu.
3. For any row in the list, set the **Enabled for** field to *All users*.

As soon as you enable the feature for all users, any user that signs in to that environment will be able to experience the change. You will not experience the change yourself until you sign out and sign in again, or start a new session.

> [!TIP]
> You can try out the feature for yourself without enabling it for all users by choosing the **Try it out** link. This will open a new browser tab with the feature enabled for that session. Any new sessions in your browser will also have the feature temporarily turned on. To stop trying the feature, close your browser window or sign out.  


## Frequently Asked Questions about Feature Management

#### There are no features listed as optional. Did I do something wrong?
There may be periods of time where no optional features have been made available and this is perfectly normal. There will likely be no features listed in the Feature Management page immediately after a major update.

#### Will all new features eventually be listed on the Feature Management list?
No. We carefully select applicable features based on a variety of criteria so that only a manageable subset of new features will appear in the list. Selected features are primarily those that change the visuals or behaviours of the user interface and which require significant effort for business users to adjust to.

#### Are these features still under development or in beta/preview?
No. Features listed in the Feature Management page are considered ready and generally available. These features are already enabled for new customers to benefit from.

#### Does Microsoft provide support for optional features?
Yes. Features listed in the Feature Management page are considered ready and follow the standard support lifecycle for the service update in which they are first made available.

#### Will Business Central notify me closer to the date when a feature becomes mandatory?
No. Users and administrators do not receive any in-app or email notifications about approaching dates for features becoming automatically enabled.  

#### How is this different to the Early Access program?
The Early Access program used by some Dynamics 365 apps makes a large set of new features available two months prior to a major update and allows customers to enable those in production. The most significant difference, is that these are always two months before the major update.

#### How is this different to preview environments?
Preview environments are [!INCLUDE[prodshort](includes/prodshort.md)] online sandbox environments that include all new platform and application features that will later be made available with the major update. The most significant difference, is that this includes all new features bundled together without the opportunity for you to be selective about which feature to enable and test. 

#### How is this different to Application Areas?
Application areas are a concept where developers can specify differentiated user experiences in the business application by showing or hiding individual controls on a page. While this also puts administrators in control of selecting the preferred experience tier, application areas are not optional for a period of time before becoming mandatory and only apply to business application controls.  

#### Can resellers, ISVs and developers contribute to the list of features?
No. At this time, feature management is only for features released by Microsoft.

#### Can I enable a feature for a single user?
No. Business Central does not provide the ability to enable a feature for a single user or group of users. Enabled features apply to all users of an environment.  

#### Are optional features also optional on new environments?
Yes. All optional features are enabled by default on new environments for new customers to benefit from. Administrators can still turn any of these features off from the Feature Management page.

#### Is this applicable to on premises deployments of Business Central?
Yes. You can turn optional features on or off in a similar way. 



## See also

[New and planned features](https://aka.ms/Dynamics365ReleasePlan)  
[Administration of [!INCLUDE[prodshort](includes/prodshort.md)] Online](tenant-administration.md)  
[Major updates of [!INCLUDE[prodshort](includes/prodshort.md)] Online](update-rollout-timelime.md)  
