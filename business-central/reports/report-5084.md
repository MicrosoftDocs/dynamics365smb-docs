---
title: Email Merge report
description: Generate personalized mail merge letters for contacts by using segment content, salutations, company details, and salesperson signatures.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_5084
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Email Merge (report)

The **Email Merge** report generates a personalized document for each contact in a segment. It combines company information, a formal or informal salutation, free-text content from the segment, and a closing signature with the salesperson's name and job title. You can run it from a marketing segment to produce letters for multiple contacts by using an RDLC or Word layout.

The segment data passed to the report determines the contact, language, salesperson, and document date. These values control the salutation, address details, content, and salesperson signature in each generated letter.

## Use cases

[!INCLUDE [report-5084-scenario](../includes/report-5084-scenario-include.md)]

Marketing and customer relationship management employees can use the report to:

* Produce personalized letters for all contacts in a marketing segment in one run.
* Use the correct formal or informal salutation based on each contact's language.
* Include campaign content from the segment without editing each letter.

Salespeople can use the report to:

* Send follow-up correspondence with their name and job title in the signature.
* Use the Word body-only layout with a standard company letterhead.
* Include the company address and logo from the company information.

## Try the report

Try the report here: [Email Merge](https://businesscentral.dynamics.com?report=5084)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Relationship management reports](../marketing-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
