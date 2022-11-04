---
title: Access with Microsoft 365 Licenses FAQ
description: Get answers to common questions about accessing Business Central with Microsoft 365 licenses. 
author: mikebcs
ms.author: mikebc
ms.reviewer: jswymer 
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 11/03/2022
ms.custom: bap-template 
---
# Access with Microsoft 365 Licenses FAQ

This article answers some of common questions about accessing Business Central with Microsoft 365 licenses.

## Is Business Central on-premises supported?

No. <!-- The setting in tac is not enabled or is hidden: environment is not on v21.1 or later -->

<!--What about ISVs? -->

## Can I use this feature on Teams for iOS or Teams for Android?

Not yet. 

## How do users change their personal settings in My Settings?

They can't, only admins can. 

## What determines the choice of language when you sign in for the first time?

Depends on your Teams client. With Teams for web, the browser language is used. With Teams desktop, iOS, and Android, the OS language is used. 

## The list of licenses shows a Microsoft 365 license. Is that new?

Yes. It supports this feature.

## Do I need to acquire a new Microsoft 365 license for this to work?

No. Microsoft has not created new licenses or new plans to power this experience. This capability relies entirely on existing Microsoft 365 plans and licenses. If you already subscribe to one of the supported Microsoft 365 plans, then you already have this new use right. If you do not subscribe to Microsoft 365 today, you can sign up for Microsoft 365 Business Premium or similar plans here. 

## Can I configure BC to provision different sets of starting permissions based on role?

Not at this time.

## Where can I find which users have only a Microsoft 365 license?

 BC vs M365 

## How do I filter my users list to only see those that have an Microsoft 365?

Not possible.

## After the initial permissions are assigned, can I change them? 

Yes, individually per user. Changing permission set on the license configuration will only affect newly added users.

## What is the Employee profile used for?

For people that don't have a specific role in Business Central. Sure, you can use it outside of the Teams context! 

## What is the Teams Users user group used for?

People who are internal to the organization and access Business Central data in Teams. 

## How do I prevent access to sensitive tables?

Apply custom permission sets.

## When any user shares Business Central data, does sharing assign permissions?

No. Only administrators have the ability and responsibility to assign permissions. 

## Does this feature support row-level security?

Yes.

## Instead of relying on JIT provisioning, can I sync the applicable users to provision user records?

Yes.

## If I configure Business Central to apply a permission set that includes some table object write access, will the user be able to write?

No, read-only is enforced by the Business Central service. 

## What happens if a user accesses data from Teams and has both a Microsoft 365 license and a Business Central license? 

## Do Microsoft 365 users show in up in the Users list in Business Central?

Yes, but only after they sign in the first time

## Does this work with Microsoft 365 trials and Business Central trials?

Yes. 

## Can this help me manage licensing costs across my organization?

Yes. SMBs sensitive cost. Microsoft offers the flexibility to pay for what you need through licenses that match simple, readonly data collaboration all the way to full capability with Essentials and Premium licensing. 

## Some links are teal but unclickable. Why?

By design. Hyperlinked fields can't be clicked.

## Page notification actions are unclickable. Why? 

By design.  

## When I remove a tab in Teams, is data deleted?

No.

## Can Microsoft #65 users remove tabs?

Yes 

<!-- How does this work with Shared Channels? TBD -->

## See also

[Business Central Access with Microsoft 365 licenses](admin-access-with-m365-license.md#minimum-requirements)  
[Set Up Access with Microsoft 365 Licenses](admin-access-with-m365-license-setup.md)  