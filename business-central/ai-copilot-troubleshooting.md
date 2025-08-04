---
title: Troubleshoot Copilot and agent capabilities
description: Learn how to fix common issues that you might encounter while working with Copilot and agent capabilities in Business Central.
author: jswymer
ms.author: jswymer 
ms.reviewer: jswymer
ms.topic: troubleshooting 
ms.collection:
  - bap-ai-copilot
ms.date: 04/01/2025
ms.update-cycle: 180-days
ms.custom: bap-template 
ms.service: dynamics-365-business-central
---
# Troubleshoot Copilot and agent capabilities

Copilot is an AI-powered functionality in Business Central that assists in various tasks like drafting marketing text and reconciling bank accounts. If you're experiencing trouble with Copilot or other agent capabilities, this article can help you identify and fix common issues.

## Copilot doesn't appear on pages

If Copilot functionality, such as the **Draft with Copilot** action for marketing text suggestions or the **Reconcile with Copilot** action for bank account reconciliation assist, doesn't appear on a page as expected, check the following:

- Make sure that the feature is enabled if it's controlled under Feature Management. [Learn more about feature management](admin-feature-management.md).

- Make sure that the functionality isn't hidden by personalization. [Learn more about personalization](ui-personalization-user.md).

## Copilot appears on pages, but you get an error that it's not activated

When you try to use Copilot and you get an error similar to **Sorry, Copilot is not activated for \[feature\]**, there are a couple things to check:

- First, make sure that the feature is activated on the **Copilot & agent capabilities** page. [Learn more about activating Copilot and agent capabilities](enable-ai.md#activate-features). 
- Next, make sure that privacy notice statement for Azure OpenAI integration isn't set to **Disagree for everyone**. If it is, change it to **Agree for everyone**. [Learn more about privacy notices](privacy-notices-status.md).

## Copilot capabilities from Microsoft not listed on Copilot & agent capabilities page

If none of the AI features from Microsoft are shown in the **Copilot & agent capabilities** page, it's likely because you have one or more embed apps installed on your environment. Embed apps can offer their own Copilot capabilities, but capabilities published by Microsoft aren't compatible with environments having embed apps.

## Related information

[Configure Copilot and agent capabilities](enable-ai.md)  
[Marketing text suggestions with Copilot](ai-overview.md)  
[Reconcile bank accounts with Copilot](bank-reconciliation-with-copilot.md)  
