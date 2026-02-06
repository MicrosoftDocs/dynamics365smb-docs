---
title: Copilot Geographic and Language Availability
description: "Learn how geographic availability, language support, and environment localization determine access to Copilot and agent features in Business Central."
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: concept-article
ms.collection: get-started
ms.date: 02/05/2026
ms.custom: bap-template
---

# Copilot geographic and language availability

This article explains how geographic availability, language support, and environment localization work together to determine access to Copilot and agent features in Business Central. Understanding these dimensions helps you identify which AI-powered capabilities are available to your organization and how to configure your environments to use them effectively.

Use the [feature availability table](#feature-availability-by-countryregion-and-language) as a quick reference to check which Copilot features support your country/region and language. For a deeper understanding of how these dimensions interact to control feature access, see [Understanding Copilot availability](#understanding-copilot-availability-geography-languages-and-localization).

## Feature availability by country/region and language

The following table lists Copilot features in Business Central, along with the Business Central country/region versions in which they're available and languages they support. Learn more about how geography, localization, and languages affect availability in the sections after the table.

|Feature|Countries/regions|Languages|
|---|---|---|
|[Analysis assist](analysis-assist.md)|[All](https://aka.ms/bccountries)|Chinese Simplified (zh-CN)<br>Czech (cs-CZ)<br>Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)<br>Finnish (fi-FI)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Greek (el-GR)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Korean (ko-KR)<br>Norwegian Bokmål (nb-NO)<br>Polish (pl-PL)<br>Portuguese Brazil (pt-BR)<br>Russian (ru-RU)<br>Spanish (es-CO, es-ES, es-MX, es-PE)<br>Swedish (sv-SE)<br>Thai (th-TH)<br>Turkish (tr-TR)|
|[Autofill fields](autofill-fields-with-copilot.md)|[All](https://aka.ms/bccountries)|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|
|[Bank account reconciliation assist](bank-reconciliation-with-copilot.md)|[All](https://aka.ms/bccountries)|Chinese Simplified (zh-CN)<br>Czech (cs-CZ)<br>Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)<br>Finnish (fi-FI)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Greek (el-GR)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Korean (ko-KR)<br>Norwegian Bokmål (nb-NO)<br>Polish (pl-PL)<br>Portuguese Brazil (pt-BR)<br>Russian (ru-RU)<br>Spanish (es-CO, es-ES, es-MX, es-PE)<br>Swedish (sv-SE)<br>Thai (th-TH)<br>Turkish (tr-TR)|
|[Map e-documents to purchase order lines](map-edocuments-with-copilot.md)|[All](https://aka.ms/bccountries)|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|
|[Marketing text suggestions](item-marketing-text.md)|[All](https://aka.ms/bccountries)|Chinese Simplified (zh-CN)<br>Czech (cs-CZ)<br>Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)<br>Finnish (fi-FI)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Greek (el-GR)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Korean (ko-KR)<br>Norwegian Bokmål (nb-NO)<br>Polish (pl-PL)<br>Portuguese Brazil (pt-BR)<br>Russian (ru-RU)<br>Spanish (es-CO, es-ES, es-MX, es-PE)<br>Swedish (sv-SE)<br>Thai (th-TH)<br>Turkish (tr-TR)|
|[Payables Agent](payables-agent.md)|AU (Australia)<br>CA (Canada)<br>DE (Germany)<br>DK (Denmark)<br>ES (Spain)<br>FR (France)<br>GB (United Kingdom)<br>IT (Italy)<br>NZ (New Zealand)<br>US (United States)|English (en-AU, en-GB, en-US, en-NZ)|
|[Sales line suggestions](sales-suggest-sales-lines-with-copilot.md)|[All](https://aka.ms/bccountries)|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|
|[Sales Order Agent](sales-order-agent.md)|[All](https://aka.ms/bccountries)|Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-NZ, en-US)<br>Finnish (fi-FI)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Icelandic (is-IS)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Norwegian Bokmål (nb-NO)<br>Portuguese Brazil (pt-BR)<br>Russian (ru-RU)<br>Spanish (es-ES, es-MX)<br>Swedish (sv-SE)|
|[Suggest item substitutions](suggest-item-substitutions-copilot.md)|[All](https://aka.ms/bccountries)|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|
|[Suggest number series](suggest-number-series-copilot.md)|[All](https://aka.ms/bccountries)|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|
|[Summarize records](summarize-with-copilot.md)|[All](https://aka.ms/bccountries)|Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Spanish (es-CO, es-ES, es-MS, es-PE)|

> [!NOTE]
> Features validated in specific languages might still function in other languages, but the quality might vary based on user interaction or system settings. This variation might impact accuracy and the user experience. Learn more in [Supported versus unlocked languages](#supported-versus-unlocked-languages).

## Understanding Copilot availability: Geography, languages, and localization

Understanding how Copilot features become available across regions and languages can be challenging. This section explains how geographic infrastructure, language support, and environment localization affect access to these AI-powered capabilities and serves as a reference for Copilot feature availability.

### Why Microsoft doesn't release features everywhere simultaneously

Microsoft takes a measured, phased approach to releasing Copilot features across geographies and languages. Several critical factors drive this strategy:

**Regulatory and compliance requirements**: Different countries/regions have varying data residency, privacy, and AI governance regulations. Microsoft must ensure full compliance with local laws before launching Copilot features in a new geography, including regulations around data processing, AI transparency, and customer consent. For example, features must meet GDPR requirements in Europe, which might differ from regulations in other regions.

**Azure infrastructure dependencies**: Copilot features rely on specific Azure AI services and infrastructure. You must deploy these services and make them operational in Azure data centers within a given geography before you can make features available to customers in that region.

**Quality and performance validation**: Each new geography requires extensive testing to ensure that Copilot features perform reliably under local network conditions, latency constraints, and regional usage patterns. Microsoft validates performance benchmarks before expanding availability.

**Language model quality**: For features that support multiple languages, Microsoft must train and validate AI models for each language to ensure high-quality outputs. This testing process takes time and resources, which is why features often launch in English first and expand to more languages over subsequent releases.

This phased approach ensures that when a feature becomes available in your geography and language, it delivers a reliable, compliant, and high-quality experience.

### Key dimensions of Copilot availability

To understand Copilot feature availability and support, you need to consider four independent but interconnected dimensions:

1. **Azure OpenAI Service geography** - Where AI processing occurs
2. **Business Central environment country/region version** - Defines localization and business rules
3. **Business Central data residency (Azure region)** - Where your business data is stored
4. **Supported languages** - Languages for user interaction

The following sections explain each dimension in detail.

#### 1. Azure OpenAI Service geography

**What it is**: The physical Azure data center region where the AI model processes your prompts and generates responses.

**Why it matters**:
- Determines where AI processing occurs for compliance and data sovereignty
- Affects latency and performance of AI responses

**Key point**: It's about **where the AI thinks**, not where your business data lives.

**Example**: When you use analysis assist in Business Central, your prompt is sent to an Azure OpenAI endpoint in a specific geography (such as Europe, United States, or Asia Pacific) for processing.

#### 2. Business Central environment country/region

**What it is**: The country/region setting you choose when creating a Business Central environment, which determines the localization version of Business Central.

**Why it matters**:

- Controls which regulatory features, tax calculations, and reporting formats are available
- Determines which localization-specific functionality you have access to
- Can't be changed after environment creation
- Determines the Azure region where Business Central data is stored

**Key point**: It's about **localization and regulatory compliance**, not physical data location.

**Example**: A Denmark (DK) environment includes Danish VAT rules, tax reporting, and regulatory requirements, regardless of where the environment is physically hosted.

#### 3. Business Central data residency region

**What it is**: The Azure region where your Business Central environment database is physically hosted and stored.

**Why it matters**:

- Determines physical location of your business data
- Automatically determined by your environment country/region setting
- Affects data residency compliance and regulations
- Can result in cross-geography data movement if Azure OpenAI Service operates in a different geography. Learn more in [Cross-geography data movement for Copilot](ai-copilot-data-movement.md)

**Key point**: It's about **where your business data lives**.

**Example**: A Danish (DK) environment is hosted in Azure's Europe North region, keeping your customer data, transactions, and business records within European data centers.

#### 4. Supported languages

**What it is**: The languages in which you can interact with Copilot features and in which Business Central displays its user interface.

**Why it matters**:

- Determines which languages Microsoft has tested and validated for each Copilot feature
- Controls the language of prompts, AI responses, and feature outputs
- Is independent of both localization and data location

**Key distinction**: Microsoft distinguishes between **officially supported languages** (tested and validated) and **unlocked languages** (might work but not guaranteed). See [Supported versus unlocked languages](#supported-versus-unlocked-languages) for details.

**Example**: You can have a Danish-localized environment, hosted in Europe, with users interacting with Copilot in English, German, or any other supported language.

##### Supported versus unlocked languages

Understanding the difference between supported and unlocked languages is critical for setting appropriate expectations:

**Supported languages** (listed in the [feature table](#feature-availability-by-countryregion-and-language):

- Microsoft officially tests and validates these languages
- Meet established quality metrics for accuracy and appropriateness
- Full support available if problems occur
- Deliver consistent, high-quality results

**Unlocked (untested) languages**:

- Features might technically work in languages not listed in the table
- Microsoft didn't rigorously test these languages
- Quality, accuracy, and appropriateness of AI-generated content aren't guaranteed
- No official support for language-specific problems
- Results vary based on the AI model's general language capabilities

**Why features work in unlocked languages**: The underlying AI models (like Azure OpenAI Service) often have broad multilingual capabilities. When you use a Copilot feature in an untested language, the AI might still generate responses, but Microsoft didn't validate that these responses meet quality standards.

**The risks of using unlocked languages**:

- Inaccurate or inappropriate translations
- Culturally insensitive content
- Mixing of languages in outputs
- Lower accuracy in understanding prompts
- Reduced quality of generated suggestions
- Inconsistent results between sessions

**Our recommendation**:

- **Production environments**: Use Copilot features only in officially supported languages for business-critical processes
- **Test environments**: You can experiment with unlocked languages, but understand that results aren't guaranteed and support is limited
- **Quality assurance**: If you must use an unlocked language, implement extra review processes to validate AI outputs

This approach ensures reliable business operations while allowing flexibility for exploration and testing.

### How these four dimensions work together

These dimensions are **independent** but work together to determine availability:

```
┌─────────────────────────────────────────────────────────────────┐
│ User in London, England                                         │
│                                                                 │
│ [1] Uses Business Central in language: English GB               │
│         ↓                                                       │
│ [2] Environment country/region is: United Kingdom (GB)          │
│     (Danish VAT, tax rules, regulatory features)                │
│         ↓                                                       │
│ [3] Environment data stored in Azure region: United Kingdom West│
│     (Database, transactions, customer data)                     │
│         ↓                                                       │
│ [4] Copilot prompt sent to AZURE OPENAI in: United Kingdom      │
│     (AI processing, model inference)                            │
│         ↓                                                       │
│ [5] Response returned in: DANISH (supported language)           │
└─────────────────────────────────────────────────────────────────┘

   ✓ All four dimensions align - Full functionality available
```

**Cross-geography scenario**:

```
┌─────────────────────────────────────────────────────────────────┐
│ User in Copenhagen, Denmark                                     │
│                                                                 │
│ [1] Uses Business Central in language: DANISH                   │
│         ↓                                                       │
│ [2] Environment country/region is: DENMARK (DK)                 │
│         ↓                                                       │
│ [3] Environment data stored in Azure region: EUROPE NORTH       │
│         ↓                                                       │
│         ↓  ! DATA CROSSES GEOGRAPHY BOUNDARY                    │
│         ↓                                                       │
│ [4] Copilot prompt sent to AZURE OPENAI in: SWEDEN              │
│     (Feature not yet available in Europe geography)             │
│         ↓                                                       │
│         ↓  ! RESPONSE CROSSES GEOGRAPHY BOUNDARY                │
│         ↓                                                       │
│ [5] Response returned in: DANISH (supported language)           │
└─────────────────────────────────────────────────────────────────┘

   !  Cross-geography data movement occurs
   → Check your organization's data residency policies
```

### Summary of the four dimensions

| Dimension | What it determines | Set by | Can it be changed? | Example |
|-----------|-------------------|--------|-------------|---------|
| 1. Azure OpenAI Services geography | Where AI processing occurs | Microsoft Azure OpenAI deployment | No (Microsoft controls) | Europe, United States, Asia Pacific |
| 2. Business Central environment country/region| Localization and regulatory features | You (at environment creation) | No | Denmark (DK), United States (US) |
| 3. Azure region for Business Central data residency | Where business data is stored | Automatically based on country/region | No | Germany West Cental West, North America |
| 4. Supported languages | User interaction language | You (user/admin settings) | Yes | Danish, English, German, French |