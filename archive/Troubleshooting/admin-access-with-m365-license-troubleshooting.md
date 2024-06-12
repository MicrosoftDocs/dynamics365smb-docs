---
title: Troubleshoot Access with Microsoft 365 Licenses
description: Learn how you can fix problems accessing Business Central with only a Microsoft 365 license. 
author: mikebc 
ms.author: mikebc
ms.reviewer: bholtorf
ms.topic: troubleshooting
ms.date: 02/07/2023
ms.custom: bap-template
ms.search.keywords: License, access, Microsoft 365, collaborate, collaboration, Teams, Microsoft Teams
ms.service: dynamics-365-business-central
---

# Troubleshoot Access with Microsoft 365 Licenses

## "This page uses data from related tables that you do not have access to" error message

### Symptoms

When accessing a record in Teams, you're shown an error message in a tab or card details similar to:

"This page uses data from related tables that you don't have access to. To work with all features of this page, contact your administrator."

### Cause

You're most likely missing object permissions for tables that the current page or record links to.

## Microsoft 365 access has been enabled, but users get a permission error

### Symptoms

Access with Microsoft 365 has been enabled in Business Central admin center, but users get a permission error when accessing any record.

### Cause

If you enable access in the Business Central admin center, but don't assign permissions in the **License Configuration** page, anyone that attempts to access Business Central records in Teams will have their user record provisioned without permission to any objects. Business Central is secure by design: administrators must first configure what data can be accessed in Teams. 

### Resolution

Customizing permissions in the License Configuration page will only affect newly created users. You must also assign the missing permissions to users that have already been created through the Users list page. 

## You shared a link in Teams, but users get a message that they can only view data

### Symptoms

When you share a link in Teams as a Business Central user, others get the error "When accessing Business Central with a Microsoft 365 license, you can only view data in Microsoft Teams".

### Cause

When sharing a Business Central link to a Teams chat or channels, navigating a link will always navigate out of Microsoft Teams where the data no longer becomes accessible to a person having a Microsoft 365 license.

### Resolution

When sharing pages or records, either include the link preview as a card, or share data as a tab in the chat or channel.

## Card from shared link is minimal and doesn't include Details button

### Symptoms 

When a Microsoft 365 license holder without a Business Central license shares a Business Central link in Teams, it automatically expands into a card that has no useful information and only shows Business Central with no **Details** button.

### Cause

Users who have a Microsoft 365 license but no Business Central license aren't allowed to share links as cards. If the user has the Business Central app for Teams installed and pastes a link into the compose area, then only a minimal card is displayed. 

## See also

[Business Central Access with Microsoft 365 licenses](admin-access-with-m365-license.md#minimum-requirements)  
[Set Up Access with Microsoft 365 Licenses](admin-access-with-m365-license-setup.md)  
[Business Central and Microsoft Teams Integration](across-teams-overview.md)
[Sharing Business Central Records and Page Links in Microsoft Teams](across-working-with-teams.md)  
[Troubleshoot Teams Integration](admin-teams-troubleshooting.md)  