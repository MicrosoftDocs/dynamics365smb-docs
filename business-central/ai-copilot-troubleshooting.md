---
title: Troubleshoot Copilot and AI capabilities
description: Learn how to fix common issues that you might encounter while working with Copilot and AI capabilities in Business Central.
author: jswymer
ms.author: jswymer 
ms.reviewer: jswymer 
ms.topic: troubleshooting 
ms.collection:
ms.date: 11/15/2023
ms.custom: bap-template 
---
# Troubleshoot Copilot and AI capabilities

Copilot is an AI-powered functionality in Business Central that assists in various tasks like drafting marketing text and reconciling bank accounts. If you're experiencing trouble with Copilot or other AI capabilities, this article can help you identify and fix common issues.

## Copilot doesn't appear on pages

If Copilot functionality, such as the **Draft with Copilot** action for marketing text suggestions or the **Reconcile with Copilot** action for bank account reconciliation assist, doesn't appear on a page as expected, check the following:

- If the feature is controlled under Feature Management, make sure that it's enabled. [Learn more about feature management](admin-feature-management.md).

- Make sure that the functionality isn't hidden by personalization. [Learn more about personalization](ui-personalization-user.md).

## Copilot appears on pages, but you get an error that it's not activated

When you try to use Copilot and you get an error similar to **Sorry, Copilot is not activated for \[feature\]**, there are a couple things to check:

- First, make sure that the feature is activated on the **Copilot & AI capabilities** page. [Learn more about activating Copilot and AI capabilities](enable-ai.md#activate-features). 
- Next, make sure that privacy notice statement for Azure OpenAI integration isn't set to **Disagree for everyone**. If it is, change it to **Agree for everyone**. [Learn more about privacy notices](privacy-notices-status.md).

## See also

[Configure Copilot and AI capabilities](enable-ai.md)  
[Marketing text suggestions with Copilot](ai-overview.md)  
[Reconcile bank accounts with Copilot](bank-reconciliation-with-copilot.md)  
