---
title: About Copilot in Business Central
description: This article answers common questions about Copilot in Business Central.
author: mikebc
ms.author: mikebc
ms.reviewer: jswymer
ms.topic: overview 
ms.collection:
  - bap-ai-copilot
  - get-started
ms.date: 01/29/2026
ms.update-cycle: 180-days
ms.custom: bap-template
---

# Copilot in Business Central overview

This article answers common questions about Microsoft Copilot in Dynamics 365 Business Central.

## What is Copilot in Business Central?

[!INCLUDE[bc-app-agents](../bc-shared/bc-app-agents.md)]

## Where can I find the list of Copilot features in Business Central?

Copilot includes a constantly expanding set of capabilities that help users in different roles and tasks. Find an overview at [Work smarter with Microsoft Copilot in Dynamics 365 Business Central](https://aka.ms/BCAI). And find details here in the documentation by choosing links in the navigation panel to the left.

## How does Copilot approach security, privacy, and compliance?

Copilot is built on the Microsoft cloud and designed for enterprise use, with the security, privacy, and compliance controls that our customers expect. Here are some key points to common questions:

- When a user interacts with Copilot, it inherits their data permissions and can't read any more data than the user already has access to.
- Microsoft doesn't read your prompts or use your data to train AI models without your explicit permission.
- For customers within the EU Data Boundary, data doesn't move outside that boundary. 

Learn about Copilot data security and privacy in [FAQ for Copilot data security and privacy for Dynamics 365 and Power Platform](/dynamics365/faqs-copilot-data-security-privacy). Learn about data movement across geographies in [Copilot data movement across geographies](ai-copilot-data-movement.md).

## How does Copilot approach AI safety?

Generative AI within Copilot in Business Central aligns with Microsoft's responsible AI principles, including: fairness, reliability, safety, privacy and security, inclusiveness, transparency, and accountability. Learn more in [Responsible AI FAQs for Business Central](responsible-ai-overview.md) or explore our [Responsible AI transparency report](https://aka.ms/RAITransparencyReport2025).

## Is Copilot free?

Yes, Copilot in Business Central is included with your Business Central license at no extra cost. However, fair-use policies, quotas, or pricing might be introduced later.

## Is Copilot in Business Central available worldwide?

Copilot includes a constantly expanding set of capabilities that help users in different roles and tasks. Each Copilot capability defines its own list of supported regions and supported languages. Although most features might be available only in English at first, we aim to unlock more languages and regions over time. Learn more at [Copilot international availability](https://aka.ms/bapcopilot-intl-report-external).

## Is Copilot available for Business Central online only?

Yes, Copilot is exclusive to Business Central online. Therefore, it isn't available for other deployment types, such as on-premises or private cloud.

## Is Copilot aware of my environment customizations?

Some but not all Copilot features can work with your custom pages, tables, and other content from the apps that you installed. For example, you can use [analysis assist](analysis-assist.md) on your custom lists, or you can use [chat with Copilot](chat-with-copilot.md) to find records in custom tables. Learn more about how each Copilot feature works with your customizations in [Analyze data in lists with help from Copilot](analysis-assist.md) and [Chat with Copilot](chat-with-copilot.md).

The accuracy and user experience of Business Central's AI-powered features might vary based on the apps that you installed.

## Does Copilot have to be trained on my data?

Copilot in Business Central relies on powerful AI foundation models that are coupled with data management features of the Business Central platform. No expensive or time-consuming training is needed before your organization can start to use Copilot with your own company data.

## Is Copilot connected to the web?

As of update 26.3, some Copilot features in Business Central can search the web for additional information. Allowing Copilot to search the web improves the quality of Copilot responses by grounding them in the latest information from public website content and saves our customers time from having to switch apps to manually find things themselves.  

At Microsoft, we're committed to ensuring that Copilot is built for enterprise use with the security, privacy, compliance, and responsible AI controls that our customers expect. Learn more about how Copilot searches the web, how it's designed for safety, and how administrators can configure it in [Searching the web with Copilot](ai-search-web-copilot.md).

## Can I develop my own copilots for Business Central?

You can extend and enhance Copilot in Business Central by using tools that are part of Business Central's standard development platform. Learn more in [Integrating AI using Developer Tools for Copilot](/dynamics365/business-central/dev-itpro/developer/ai-integration-landing-page).

You can also connect copilots by using Copilot Studio. In addition, you can implement your own stand-alone AI-powered apps and services that connect to Business Central. Learn more in [Adopt, extend, and build Copilot experiences across the Microsoft Cloud](/microsoft-cloud/dev/copilot/overview).

## How do I stay up to date with the latest news about Copilot in Business Central?

For news about Copilot and other AI innovation in Business Central, you can follow [the release plans](https://aka.ms/BCReleasePlan).

## As a Business Central partner, how easily can I demonstrate Copilot in Business Central to my customers?

Copilot in Business Central is automatically available when you provision a Microsoft Entra tenant with a Business Central environment on the [Customer Digital Experiences (CDX)](https://aka.ms/CDX) site. Learn more about how to prepare demonstrations in [Prepare demonstration environments of Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/administration/demo-environment).

Depending on the environment that you provision, extra setup might be required. Learn more in [Configure Copilot and agent capabilities](/dynamics365/business-central/enable-ai).

## Is there a difference between Copilot in Business Central and Microsoft 365 Copilot?

Microsoft empowers people to achieve more through copilots that are adapted to different situations. For example, Microsoft 365 Copilot is the general AI assistant that is intended for working with Microsoft Teams, Excel, and other productivity apps. Copilot in Business Central is the AI assistant that is intended specifically for the Business Central app.

## Does Copilot in Business Central work with Copilot for Microsoft 365?

Currently, there's no direct connection between Copilot in Business Central and Microsoft 365 Copilot. Copilot features inside Business Central are unaware of your Microsoft 365 data.

Conversely, when working in the Microsoft 365 suite of applications there are options for Copilot to use Business Central data. One such option is Microsoft 365 Copilot for Finance, a stand-alone product that uses general GPT training data, Microsoft 365 Graph data, and ERP information. Microsoft 365 Copilot for Finance can connect to Business Central and work with ERP data useful to specific contexts and scenarios, like collections management.

Learn more about Microsoft 365 Copilot for Finance with Business Central in [Collect outstanding balances](receivables-collect-outstanding-balances.md). Learn more general information at [Microsoft 365 Copilot for Finance](https://www.microsoft.com/microsoft-365/copilot/copilot-for-finance).

## Does Copilot in Business Central require a minimum number of users?

Currently, no minimum number of users is required to start to use Copilot in Business Central.

## How does Copilot use the Azure AI time quota that is included with licenses?

Business Central offers numerous AI-powered features. Some features, such as sales and inventory forecasting, use specific machine learning models. These features rely on Azure AI and aren't related to Copilot. As the Dynamics 365 licensing guide indicates, 30 minutes of Azure AI time are included with Business Central licenses. This quota refers to non-Copilot features, where consumption of Azure AI time has no effect on Copilot in Business Central.

## Is Copilot available to Embed applications?

Currently, because of technical limitations, we can't offer Copilot to customers who run independent software vendor (ISV) Embed apps. ISVs can extend Copilot with their own functionality or provide alternative uses of generative AI.

## Related information

[Configure Copilot and agent capabilities](enable-ai.md)  
[Analyze data in lists with Copilot](analysis-assist.md)  
[Autofill with Copilot](autofill-fields-with-copilot.md)  
[Chat with Copilot](chat-with-copilot.md)  
[Create marketing text with Copilot](item-marketing-text.md)  
[Find item substitutions with Copilot](suggest-item-substitutions-copilot.md)  
[Map e-documents to purchase order lines with Copilot](map-edocuments-with-copilot.md)  
[Payables Agent](payables-agent.md)  
[Reconcile bank accounts with Copilot](bank-reconciliation-with-copilot.md)  
[Sales Order Agent](sales-order-agent.md)  
[Suggest lines on sales orders with Copilot](sales-suggest-sales-lines-with-copilot.md)  
[Suggest number series with Copilot](suggest-number-series-copilot.md)  
[Summarize with Copilot](summarize-with-copilot.md)  
