---
title: "Copilot and Agent Feature Availability by Geography and Language"
description: "Learn how geographic availability, language support, and environment localization determine access to Copilot and agent features in Business Central."
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: "concept-article"
ms.collection: "get-started #Required; If this isn't a getting started article, don't remove the attribute, but leave the value blank. The values for this attribute will be updated over time."
ms.date: 02/05/2026
ms.custom: bap-template #Required; don't change.
---

# Copilot geographic and language availability

Understanding how Copilot features become available across regions and languages can be challenging. This article explains how geographic infrastructure, language support, and environment localization affect access to these AI-powered capabilities and serves as a reference for Copilot feature availability.

## Copilot feature support matrix by country/region and language

The following table lists each Copilot feature in Business Central, along with the countries/regions and languages each feature supports. For a conceptual overview of how geography, languages, and localization affect availability, see **Understanding Copilot availability: Geography, languages, and localization** later in this article.

<!--
|Feature|Supported Languages|Azure geography|Learn more|
|---|---|---|---|
|Analysis assist|Chinese Simplified (zh-CN)<br>Czech (cs-CZ)<br>Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)<br>Finnish (fi-FI)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Greek (el-GR)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Korean (ko-KR)<br>Norwegian Bokmål (nb-NO)<br>Polish (pl-PL)<br>Portuguese Brazil (pt-BR)<br>Russian (ru-RU)<br>Spanish (es-CO, es-ES, es-MX, es-PE)<br>Swedish (sv-SE)<br>Thai (th-TH)<br>Turkish (tr-TR)|Asia Pacific, Australia, Brazil, Canada, China, Europe, France, Germany, India, Italy, Japan, New Zealand, Norway, Poland, Qatar, Singapore, South Africa, South Korea, Spain, Sweden, Switzerland, United Arab Emirates, United Kingdom, United States|[Analyze data in lists with Copilot](analysis-assist.md)|
|Autofill fields|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|Not specified|[Autofill with Copilot](autofill-fields-with-copilot.md)|
|Bank account reconciliation assist|Chinese Simplified (zh-CN)<br>Czech (cs-CZ)<br>Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)<br>Finnish (fi-FI)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Greek (el-GR)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Korean (ko-KR)<br>Norwegian Bokmål (nb-NO)<br>Polish (pl-PL)<br>Portuguese Brazil (pt-BR)<br>Russian (ru-RU)<br>Spanish (es-CO, es-ES, es-MX, es-PE)<br>Swedish (sv-SE)<br>Thai (th-TH)<br>Turkish (tr-TR)|Asia Pacific, Australia, Brazil, Canada, Europe, France, Germany, India, Japan, Norway, Singapore, South Africa, South Korea, Sweden, Switzerland, United Arab Emirates, United Kingdom, United States|[Reconcile bank accounts with Copilot](bank-reconciliation-with-copilot.md)|
|Map e-documents to purchase order lines|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|Asia Pacific, Australia, Brazil, Canada, Europe, France, Germany, India, Japan, Norway, Singapore, South Africa, South Korea, Sweden, Switzerland, United Arab Emirates, United Kingdom, United States|[Map e-documents to purchase order lines with Copilot](map-edocuments-with-copilot.md)|
|Marketing text suggestions|Chinese Simplified (zh-CN)<br>Czech (cs-CZ)<br>Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)<br>Finnish (fi-FI)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Greek (el-GR)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Korean (ko-KR)<br>Norwegian Bokmål (nb-NO)<br>Polish (pl-PL)<br>Portuguese Brazil (pt-BR)<br>Russian (ru-RU)<br>Spanish (es-CO, es-ES, es-MX, es-PE)<br>Swedish (sv-SE)<br>Thai (th-TH)<br>Turkish (tr-TR)|Asia Pacific, Australia, Brazil, Canada, Europe, France, Germany, India, Japan, Norway, Singapore, South Africa, South Korea, Sweden, Switzerland, United Arab Emirates, United Kingdom, United States|[Create marketing text with Copilot](item-marketing-text.md)|
|Payables Agent|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|Australia, Canada, Europe, United Kingdom, United States|[Payables Agent](payables-agent.md)|
|Sales line suggestions|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|Asia Pacific, Australia, Brazil, Canada, Europe, France, Germany, India, Japan, Norway, Singapore, South Africa, South Korea, Sweden, Switzerland, United Arab Emirates, United Kingdom, United States|[Suggest lines on sales orders with Copilot](sales-suggest-sales-lines-with-copilot.md)|
|Sales Order Agent|Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-NZ, en-US)<br>Finnish (fi-FI)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Icelandic (is-IS)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Norwegian Bokmål (nb-NO)<br>Portuguese Brazil (pt-BR)<br>Russian (ru-RU)<br>Spanish (es-ES, es-MX)<br>Swedish (sv-SE)|Asia Pacific, Australia, Brazil, Canada, China, Europe, France, Germany, India, Italy, Japan, New Zealand, Norway, Poland, Qatar, Singapore, South Africa, South Korea, Spain, Sweden, Switzerland, United Arab Emirates, United Kingdom, United States|[Sales Order Agent](sales-order-agent.md)|
|Suggest item substitutions|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|Not specified|[Find item substitutions with Copilot](suggest-item-substitutions-copilot.md)|
|Suggest number series|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|Asia Pacific, Australia, Brazil, Canada, Europe, France, Germany, India, Japan, Norway, Singapore, South Africa, South Korea, Sweden, Switzerland, United Arab Emirates, United Kingdom, United States|[Suggest number series with Copilot](suggest-number-series-copilot.md)|
|Summarize records|Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Spanish (es-CO, es-ES, es-MS, es-PE)|Asia Pacific, Australia, Brazil, Canada, Europe, France, Germany, India, Japan, Norway, Singapore, South Africa, South Korea, Sweden, Switzerland, United Arab Emirates, United Kingdom, United States|[Summarize with Copilot](summarize-with-copilot.md)|

-->
|Feature|Countries/regions|Languages|
|---|---|---|
|[Analysis assist](analysis-assist.md)|[All](https://aka.ms/bccountries)|Chinese Simplified (zh-CN)<br>Czech (cs-CZ)<br>Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)<br>Finnish (fi-FI)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Greek (el-GR)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Korean (ko-KR)<br>Norwegian Bokmål (nb-NO)<br>Polish (pl-PL)<br>Portuguese Brazil (pt-BR)<br>Russian (ru-RU)<br>Spanish (es-CO, es-ES, es-MX, es-PE)<br>Swedish (sv-SE)<br>Thai (th-TH)<br>Turkish (tr-TR)|
|[Autofill fields](autofill-fields-with-copilot.md)|[All](https://aka.ms/bccountries)|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|
|[Bank account reconciliation assist](bank-reconciliation-with-copilot.md)|[All](https://aka.ms/bccountries)|Chinese Simplified (zh-CN)<br>Czech (cs-CZ)<br>Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)<br>Finnish (fi-FI)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Greek (el-GR)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Korean (ko-KR)<br>Norwegian Bokmål (nb-NO)<br>Polish (pl-PL)<br>Portuguese Brazil (pt-BR)<br>Russian (ru-RU)<br>Spanish (es-CO, es-ES, es-MX, es-PE)<br>Swedish (sv-SE)<br>Thai (th-TH)<br>Turkish (tr-TR)|
|[Map e-documents to purchase order lines](map-edocuments-with-copilot.md)|[All](https://aka.ms/bccountries)|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|
|[Marketing text suggestions](item-marketing-text.md)|[All](https://aka.ms/bccountries)|Chinese Simplified (zh-CN)<br>Czech (cs-CZ)<br>Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)<br>Finnish (fi-FI)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Greek (el-GR)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Korean (ko-KR)<br>Norwegian Bokmål (nb-NO)<br>Polish (pl-PL)<br>Portuguese Brazil (pt-BR)<br>Russian (ru-RU)<br>Spanish (es-CO, es-ES, es-MX, es-PE)<br>Swedish (sv-SE)<br>Thai (th-TH)<br>Turkish (tr-TR)|
|[Payables Agent](payables-agent.md)|AU (Australia)<br>CA (Canada)<br>DE (Germany)<br>DK (Denmark)<br>ES (Spain)<br>FR (France)<br>GB (United Kingdom)<br>IT (Italy)<br>NZ (New Zealand)<br>US (United States)|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|
|[Sales line suggestions](sales-suggest-sales-lines-with-copilot.md)|[All](https://aka.ms/bccountries)|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|
|[Sales Order Agent](sales-order-agent.md)|[All](https://aka.ms/bccountries)|Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-NZ, en-US)<br>Finnish (fi-FI)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Icelandic (is-IS)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Norwegian Bokmål (nb-NO)<br>Portuguese Brazil (pt-BR)<br>Russian (ru-RU)<br>Spanish (es-ES, es-MX)<br>Swedish (sv-SE)|
|[Suggest item substitutions](suggest-item-substitutions-copilot.md)|[All](https://aka.ms/bccountries)|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|
|[Suggest number series](suggest-number-series-copilot.md)|[All](https://aka.ms/bccountries)|English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)|
|[Summarize records](summarize-with-copilot.md)|[All](https://aka.ms/bccountries)|Danish (da-DK)<br>Dutch (nl-BE, nl-NL)<br>English (en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA)<br>French (fr-BE, fr-CA, fr-CH, fr-FR)<br>German (de-AT, de-CH, de-DE)<br>Italian (it-CH, it-IT)<br>Japanese (ja-JP)<br>Spanish (es-CO, es-ES, es-MS, es-PE)|

> [!NOTE]
> Features validated in specific languages might still function in other languages, but the quality might vary based on user interaction or system settings. This variation might impact accuracy and the user experience. For more information about geographic and language availability, see [Copilot international availability](https://aka.ms/bapcopilot-intl-report-external).

## Understanding Copilot availability: Geography, languages, and localization

One of the most common sources of confusion when reviewing Copilot feature availability is understanding the relationship between four distinct but interconnected concepts. These dimensions work independently of each other, creating a matrix of availability that can seem complex at first glance. This article clarifies these concepts to help you better understand when and how Copilot features become available to your organization.

### Why Microsoft doesn't release features everywhere simultaneously

Microsoft takes a measured, phased approach to releasing Copilot features across geographies and languages. Several critical factors drive this strategy:

**Regulatory and compliance requirements**: Different countries/regions have varying data residency, privacy, and AI governance regulations. Microsoft must ensure full compliance with local laws before launching Copilot features in a new geography, including regulations around data processing, AI transparency, and customer consent. For example, features must meet GDPR requirements in Europe, which might differ from regulations in other regions.

**Azure infrastructure dependencies**: Copilot features rely on specific Azure AI services and infrastructure. You must deploy these services and make them operational in Azure data centers within a given geography before you can make features available to customers in that region.

**Quality and performance validation**: Each new geography requires extensive testing to ensure that Copilot features perform reliably under local network conditions, latency constraints, and regional usage patterns. Microsoft validates performance benchmarks before expanding availability.

**Language model quality**: For features that support multiple languages, Microsoft must train and validate AI models for each language to ensure high-quality outputs. This testing process takes time and resources, which is why features often launch in English first and expand to more languages over subsequent releases.

This phased approach ensures that when a feature becomes available in your geography and language, it delivers a reliable, compliant, and high-quality experience.

### The four dimensions of Copilot availability

To understand Copilot feature availability, you must consider four independent dimensions:

#### 1. Azure OpenAI Service geography (AI processing location)

**What it is**: The physical Azure data center region where the AI model processes your prompts and generates responses.

**Why it matters**:
- Determines where AI processing occurs for compliance and data sovereignty
- Affects latency and performance of AI responses
- Constrains which features are available based on Azure OpenAI Service deployment

**Key point**: This is about **where the AI thinks**, not where your business data lives.

**Example**: When you use analysis assist in Business Central, your prompt is sent to an Azure OpenAI endpoint in a specific geography (such as Europe, United States, or Asia Pacific) for processing.

#### 2. Business Central environment country/region (localization)

**What it is**: The country/region setting you choose when creating a Business Central environment, which determines the localization version of Business Central.

**Why it matters**:
- Controls which regulatory features, tax calculations, and reporting formats are available
- Determines which localization-specific functionality you have access to
- Cannot be changed after environment creation

**Key point**: This is about **what business rules and features** your environment has, not where data is stored.

**Example**: A Denmark (DK) environment includes Danish VAT rules, tax reporting, and regulatory requirements, regardless of where the environment is physically hosted.

#### 3. Business Central data residency (database location)

**What it is**: The Azure geography where your Business Central environment database is physically hosted and stored.

**Why it matters**:
- Determines physical location of your business data
- Automatically determined by your environment country/region setting
- Affects data residency compliance and regulations
- **Creates potential cross-geography data movement** if Azure OpenAI Service operates in a different geography

**Key point**: This is about **where your business data lives**.

**Important consideration - Cross-geography data movement**:
When your Business Central environment and Azure OpenAI Service are in different geographies, prompts and AI-processed data move across geographic boundaries. For example:
- Your BC environment might be hosted in Europe (for data residency)
- But Azure OpenAI Service processes requests in United States geography
- This means your prompts travel from Europe to United States for AI processing

Microsoft ensures this cross-geography movement complies with applicable regulations, but you should understand these data flows for your organization's compliance requirements.

**Example**: A Danish (DK) environment is hosted in Azure's Europe geography, keeping your customer data, transactions, and business records within European data centers.

#### 4. Supported languages (interaction and interface)

**What it is**: The languages in which you can interact with Copilot features and in which Business Central displays its user interface.

**Why it matters**:
- Determines which languages Microsoft has tested and validated for each Copilot feature
- Controls the language of prompts, AI responses, and feature outputs
- Independent of both localization and data location

**Key point**: This is about **what languages users can speak to the system**.

**Important distinction**: 
- **Business Central UI languages**: Languages available for menus, buttons, and interface elements
- **Copilot supported languages**: Languages tested and validated for specific AI features
- **Azure OpenAI capabilities**: Broad multilingual capabilities that might work but aren't officially supported

**Example**: You can have a Danish-localized environment, hosted in Europe, with users interacting with Copilot in English, German, or any other supported language.

##### Supported versus unlocked languages

Understanding the difference between supported and unlocked languages is critical for setting appropriate expectations:

**Supported languages** (listed in the feature table):
- Microsoft officially tests and validates these languages
- Meet established quality metrics for accuracy and appropriateness
- Full support available if problems occur
- Documentation reflects these languages
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
- **Quality assurance**: If you must use an unlocked language, implement additional review processes to validate AI outputs

This approach ensures reliable business operations while allowing flexibility for exploration and testing.

### How these four dimensions work together

These dimensions are **independent** but work together to determine availability:

```
┌─────────────────────────────────────────────────────────────────┐
│ User in Copenhagen, Denmark                                      │
│                                                                   │
│ [1] Uses Business Central in: DANISH UI LANGUAGE                │
│         ↓                                                         │
│ [2] Environment configured as: DENMARK (DK) LOCALIZATION        │
│     (Danish VAT, tax rules, regulatory features)                 │
│         ↓                                                         │
│ [3] Environment data stored in: AZURE EUROPE GEOGRAPHY          │
│     (Database, transactions, customer data)                       │
│         ↓                                                         │
│ [4] Copilot prompt sent to: AZURE OPENAI IN EUROPE              │
│     (AI processing, model inference)                              │
│         ↓                                                         │
│ [5] Response returned in: DANISH (supported language)            │
└─────────────────────────────────────────────────────────────────┘

   ✓ All four dimensions align - Full functionality available
```

**Cross-geography scenario**:

```
┌─────────────────────────────────────────────────────────────────┐
│ User in Copenhagen, Denmark                                      │
│                                                                   │
│ [1] Uses Business Central in: DANISH UI LANGUAGE                │
│         ↓                                                         │
│ [2] Environment configured as: DENMARK (DK) LOCALIZATION        │
│         ↓                                                         │
│ [3] Environment data stored in: AZURE EUROPE GEOGRAPHY          │
│         ↓                                                         │
│         ↓  ⚠️ DATA CROSSES GEOGRAPHY BOUNDARY                    │
│         ↓                                                         │
│ [4] Copilot prompt sent to: AZURE OPENAI IN UNITED STATES       │
│     (Feature not yet available in Europe geography)              │
│         ↓                                                         │
│         ↓  ⚠️ RESPONSE CROSSES GEOGRAPHY BOUNDARY                │
│         ↓                                                         │
│ [5] Response returned in: DANISH (supported language)            │
└─────────────────────────────────────────────────────────────────┘

   ⚠️  Cross-geography data movement occurs
   → Check your organization's data residency policies
```

### Common scenarios that cause confusion

#### Scenario 1: "Why can't I use a feature when my country is supported?"

**Example**: You're in Germany, Business Central supports Germany, but you can't access a specific Copilot feature.

**Explanation**: Check all four dimensions:
1. **Azure OpenAI geography**: Is the feature deployed in Azure's Europe region?
2. **BC localization**: Does Germany (DE) localization support this feature?
3. **Data residency**: Where is your environment hosted?
4. **Language**: Are you using a supported language (German or English)?

All four must align for the feature to work.

#### Scenario 2: "My data is in Europe, so why does Copilot process in the United States?"

**Example**: You have a French environment (hosted in Europe), but a feature shows "United States" in the Azure geography column.

**Explanation**: 
- Your **Business Central data** (#3) stays in Europe
- Your **Copilot prompts** (#1) are processed in United States Azure OpenAI
- This creates **cross-geography data movement** for AI processing
- Microsoft ensures this complies with regulations, but you should verify it meets your policies

#### Scenario 3: "The feature table shows 'All' countries, but I still can't access it"

**Example**: A feature shows "[All](https://aka.ms/bccountries)" in the Countries/regions column, but it's not available.

**Explanation**: "All" means all countries/regions where Business Central is available (#2), but you still need:
- Azure OpenAI deployment in your region (#1) 
- Your environment hosted in a supported geography (#3)
- Interaction in a supported language (#4)
- Proper licensing and admin configuration

### Summary: The four dimensions compared

| Dimension | What It Determines | Set By | Can Change? | Example |
|-----------|-------------------|--------|-------------|---------|
| **1. Azure OpenAI Geography** | Where AI processing occurs | Microsoft Azure OpenAI deployment | No (Microsoft controls) | Europe, United States, Asia Pacific |
| **2. BC Environment Country/Region** | Localization and regulatory features | You (at environment creation) | No | Denmark (DK), United States (US) |
| **3. BC Data Residency** | Where business data is stored | Automatically by #2 | No | Azure Europe, Azure North America |
| **4. Supported Languages** | User interaction language | You (user/admin settings) | Yes | Danish, English, German, French |

### Data movement and compliance considerations

Understanding data movement is critical for compliance:

**Within same geography**:
- BC environment in Europe (#3) → Azure OpenAI in Europe (#1)
- No cross-geography data movement
- Simplified compliance

**Across geographies**:
- BC environment in Europe (#3) → Azure OpenAI in United States (#1)
- Prompts and responses cross geography boundaries
- Microsoft ensures regulatory compliance
- **Your organization should verify this meets internal policies**

**What crosses geographies**:
- User prompts to Copilot
- AI-generated responses
- Feature-specific data processed by AI

**What stays in BC geography**:
- Customer records
- Financial transactions  
- Master data
- Historical business data

### How to determine if a feature is available to you

Follow this checklist across all four dimensions:

**1. Azure OpenAI Geography**:
- Check the feature table for supported geographies
- Confirm Microsoft deployed Azure OpenAI in a geography accessible to your tenant
- Understand if cross-geography data movement occurs

**2. Business Central Environment Country/Region**:
- Verify your environment's country/region setting
- Confirm the feature supports your localization
- Check the [Countries/regions](https://aka.ms/bccountries) list

**3. Business Central Data Residency**:
- Confirm where your environment is hosted (your admin can verify)
- Understand data residency requirements for your organization
- Ensure this meets regulatory obligations

**4. Supported Languages**:
- Check if your preferred language is listed in the feature table
- Verify your user language settings
- Confirm the feature supports your language

**Plus**: 
- Licensing: Does your organization have required licenses?
- Admin settings: Are Copilot features enabled?
- Country/region approval: See [Copilot international availability](https://aka.ms/bapcopilot-intl-report-external)

### Looking ahead

Microsoft continually expands Copilot availability across all four dimensions:

- **Azure OpenAI geographies**: New regions being added regularly
- **Country/region localizations**: More countries/regions gaining Copilot access
- **Data residency options**: Enhanced control over where processing occurs
- **Language support**: Expanding from English to more languages

The table in this article represents availability as of February 2026. Check the [Copilot international availability report](https://aka.ms/bapcopilot-intl-report-external) for the latest updates across all dimensions.

### Key takeaways

- **Four independent dimensions** determine Copilot availability, not three
- **Azure OpenAI geography** (#1) and **BC data residency** (#3) are different - one is about AI processing, the other about data storage
- **Cross-geography data movement** can occur when these dimensions don't align
- **Environment country/region** (#2) determines localization, which then determines data residency (#3)
- **Language support** (#4) is independent of all geographic considerations
- All four dimensions must align for full functionality
- Understanding data movement is critical for compliance