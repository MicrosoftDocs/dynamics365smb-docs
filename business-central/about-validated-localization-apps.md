---
title: Development of validated localization apps
description: Comply with regulatory requirements in Business Central as a Validated Localization App.
author: altotovi
ms.date: 12/11/2024
ms.reviewer: bholtorf
ms.topic: article
ms.author: altotovi
ms.custom: references_regions
---

# Development of Validated Localization apps

This article describes the requirements and guidelines for developing a Validated Localization app for [!INCLUDE[prod_short](includes/prod_short.md)].

## What is a Validated Localization app?

[!INCLUDE[prod_short](includes/prod_short.md)] is available [globally in 170+ markets](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations?toc=/dynamics365/business-central/toc.json). In some markets, Microsoft works with independent software vendor (ISV) partners to localize [!INCLUDE[prod_short](includes/prod_short.md)] through localization apps that we make available on [Microsoft AppSource](https://go.microsoft.com/fwlink/?linkid=2081646). For those regions, localizations can be available through preferred localization app program. Preferred localization apps program recognizes those apps, which are built according to Microsoft quality guidelines. ISV partners who comply with those program requirements and guidelines can benefit technically and commercially to serve their resellers and customers.  

In the following sections, you can find requirements and guidelines. You can reach out to the program team if you want to participate in this program and comply with the below requirements by contacting us through [Microsoft localization team](mailto:d365bcloc@microsoft.com).

> [!IMPORTANT]
> The [!INCLUDE[prod_short](includes/prod_short.md)] Validated Localization apps initiative is currently being rolled out as a pilot program. The following requirements and benefits can change based upon the partner and customer feedback.  

Apps in the Validated Localization pilot program contain a set of functionalities addressing local regulatory requirements that fall within one of the categories in the following list.  

- **Regulatory requirements** - local functionality that helps businesses fulfill their legal requirements, such as tax reporting, local E-invoicing formats, local GAAP, and other regulatory requirements.
- **National standards requirement** – local functionality that addresses local standards, such as address formats, national banking formats, or local interpretations of global standards.
- **Local language** - local language in the localization app, but also for a base app if this language isn't currently on the list of [supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations?toc=/dynamics365/business-central/toc.json).

> [!NOTE]
> Local market needs or industry requirements should not be included in the preferred localization apps. If apps contain these functionalities, the apps can't be approved as Validated Localization apps.

> [!NOTE]
> Local functionality is beneficial to the productivity business processes in a country and thereby adds value to a business but isn't required from a regulatory perspective, such as specific banking and payment formats, expense reports, HR features, and payroll. Similar smaller or bigger, and nice-to-have features should be isolated into other apps. If apps contain these functionalities, they aren't approved as Validated Localization apps.

## Validated Localization app business requirements  

- The Validated Localization App provider complies with all requirements to be a CSP indirect provider.  
- The Validated Localization App provider brings to market a minimum of offerings across five countries/regions, which bundle Dynamics 365 Business Central with a Validated Localization App.
- The Validated Localization App provider has a minimum of 10 [!INCLUDE[prod_short](includes/prod_short.md)] online customers with production environments, which are actively using the Validated Localization App.
- The Validated Localization App provider submits a business plan on a yearly basis to the program v-team. The plan includes planned marketing and readiness activities to promote the bundled offering with the CSP Indirect Resellers in applicable countries/regions. Plan can be submitted at the start of each quarter to [Microsoft localization team](mailto:d365bcloc@microsoft.com).  
- The Validated Localization Apps are available to all customers and partners who want to benefit from them.
- The Validated Localization App provider engages in recurring workstreams with Microsoft.
- The Validated Localization App provider must maintain its status as an Embedded Localization Partner.  
- The Validated Localization App provider agrees to continuously adhere to the business, functional, and technical requirements outlined on this page.

## Validated Localization app functional and technical requirements  

### Functionality requirements

In addition to the technical requirements for the preferred localization app, the minimum viable product scope for preferred localization app is:  

- Local Regulatory Features:  
  - Legal requirements.
  - Officially mandatory features.
  - Horizontal only features (not industry-specific).  
  - Applicable in most businesses.  
  - Within the following blueprint:
    - Areas of the most frequent legislative changes.
    - Already tracked as a localization in Microsoft localizations.
    - Feature references – seldom new.  
    - No vendor or bank specific formats, payroll, or similar.
    - No global features not built by Microsoft.
- Translations:
  - Translation of a localization app to local languages.
  - Translation of a base app to local languages if the language isn't already [supported](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations?toc=/dynamics365/business-central/toc.json).  
  - Translation of the localization app's documentation to local languages.
- Even though they're both part of localization, we recommended that National Standard Features (local part) are built as separate apps from Local Regulatory Features.
- Demo data in the local language for the specific market.
- All features must be designed with a basic user interface. They're intended primarily for the SMB market.  
- Avoid building new features if the same or similar functionality is already in the base app. For example, electronic invoicing, audit exports, VAT features, data exchange, and others. Most of the functionality is common to all countries/regions, but there are local rules or business formats that are extensions of global frameworks or formats. Instead of building new features, extend existing ones.  
- Prepare setup guides (wizards) for areas that are complex to set up to help users enable, discover, and have good first experience using your localization app.  
- Partners must provide functional documentation for all aspects of their localization.  

### Technical requirements  

The following are requirements that you must meet before submitting the Validated Localization app as an extension for validation. This list doesn’t change the [technical validation list](/dynamics365/business-central/dev-itpro/developer/devenv-checklist-submission) and only extends requirements from there.  

- Providers must build the Validated Localization app based on the W1 base app.  
- Providers must follow Microsoft lifecycle and support policies.   
- Mandatory test automation must cover a minimum 80% of code and all business processes that change with the Validated Localization app must be covered by test automation.  
- Providers must update and/or test its Validated Localization app before the official launch of new release (minimum with the RC before new release) to confirm there are no issues. 
- All objects in the Validated Localization app code must be in English.   
- The Validated Localization app providers must follow Microsoft policy for obsolete objects and breaking changes and best practices for deprecation of the AL Code.  
- The Validated Localization app providers should add new events if required by the market (other implementation partners or customers) if it makes reasonable business sense. The events must follow Microsoft policy and practice. Otherwise, the validated localization app providers must provide a response to justify why it doesn't make reasonable business sense to add them.
- The Validated Localization app providers must provide written test scenarios in English and enable Microsoft to do manual testing if required by Microsoft.  
- If a Validated Localization app extends the [!INCLUDE[prod_short](includes/prod_short.md)] data model with new tables and/or fields, the Validated Localization app provider must set the **DataClassification** property correctly.

> [!NOTE]  
> You can also create an integration if you find it beneficial to have some functionality placed outside the [!INCLUDE[prod_short](includes/prod_short.md)] environment and instead connect to [!INCLUDE[prod_short](includes/prod_short.md)] using for example, APIs or web services.

## Related information

[Technical validation](/dynamics365/business-central/dev-itpro/developer/devenv-checklist-submission)  
[Development of a standard Localization Solution](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-develop-localization)  
[Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations)  
[What is Local Functionality in Dynamics 365 [!INCLUDE[prod_short](includes/prod_short.md)]?](about-localization.md)  
[International availability of Microsoft Dynamics 365](/dynamics365/get-started/availability)  
[Compliance overview](compliance/compliance-overview.md)  
[Geographical availability for Dynamics 365](https://releaseplans.microsoft.com/availability-reports/?report=productgeoreport/)  
