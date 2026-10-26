---
title: Norwegian VAT Reporting in Business Central
description: Use Norwegian-specific features in Business Central to calculate and report VAT returns electronically to the Norwegian tax authorities.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Norwegian VAT reporting, Norwegian Electronic VAT, Electronic VAT submission, ID-porten, troubleshoot connection, tradesettlement report, submit electronic VAT, electronic VAT returns, integration point setup, VAT reporting setup, Norwegian version
ms.search.form: 737, 738, 743, 10601, 10604, 10692 ,10696
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
ms.custom: sfi-image-nochange
---

# Norwegian VAT reporting

> [!IMPORTANT]
> ID-porten in Norway has changed. Microsoft updated the Norwegian Electronic VAT submission solution to the new ID-porten system from the 23.5 release.

[!INCLUDE[prod_short](../../includes/prod_short.md)] provides features that allow you to calculate and report VAT returns to the Norwegian tax authorities.  

This article shows the typical steps that you should follow when reporting Norwegian VAT.  

This article assumes that VAT reporting is set up. Learn more in [Set Up Calculations and Posting Methods for Value-Added Tax](../../finance-setup-vat.md) and [Report VAT to Tax Authorities](../../finance-how-report-vat.md).

## Set up Business Central to generate and submit electronic VAT returns

To submit VAT returns to Norwegian tax authorities, an administrator must create a connection to ID-Porten at Digitaliseringsdirektoratet.  

> [!TIP]
> We recommend that you always use [!INCLUDE [prod_short](../../includes/prod_short.md)] in a browser to set up the connection to ID-Porten.

### Register your company with ID-Porten

To register your company with ID-Porten, follow the steps provided by [Samarbeidsportalen](https://samarbeid.digdir.no/id-porten/ta-i-bruk-id-porten/94). After you register, note the following information. You'll need it later when you use the assisted setup guide to authorize [!INCLUDE[prod_short](../../includes/prod_short.md)] to access ID-Porten.

* Valid redirection URIs
* Client ID
* Client secret

> [!IMPORTANT]
> It's important to safely store the client ID and client secret of the integration point.

### Set up the integration point

After you register your company in ID-Porten, the next step is to create an integration point in your company's account in ID-Porten. Learn more in [integration point](https://docs.digdir.no/).

> [!NOTE]
> The following portal instructions describe the integration settings. ID-porten portal navigation, captions, and available electronic IDs can change independently of [!INCLUDE[prod_short](../../includes/prod_short.md)]. If the portal differs, follow the current guidance from Digitaliseringsdirektoratet and Skatteetaten.

1. Sign in to [Skatteetaten](https://skatteetaten.github.io/mva-meldingen/english/idportenauthentication/).
1. On the navigation pane, choose **Integrasjoner**, and under **Produksjon**, choose **Ver 2**.
1. Choose **New Integration** to add a new integration point at [ID-porten self-service](https://sjolvbetjening.samarbeid.digdir.no/).
1. Fill in the fields as described in the following table.

    | Norwegian parameter name | Parameter description | Parameter value |
    |---|---|---|
    | Difi-tjeneste | Select the service to be assigned correct scopes. | Select **API-klient**. |
    | Scopes | The APIs and resources that the integration can access. | <p>Select the following scopes:</p><ul><li>**openid**</li><li>**skatteetaten:mvameldinginnsending**</li><li>**skatteetaten:mvameldingvalidering**</li></ul> |
    | Kundens org.nr. | The organization number of the service owner. | You don't have to specify a value in this field. The required value is automatically set when the setup of the integration point is saved. |
    | Integrasjonens identifikator | The unique identifier of the service. | You don't have to specify a value in this field. The required value is automatically set when the setup of the integration point is saved. |
    | Navn på integrasjonen | The name of the integration as it appears in the sign-in window. | Specify **Microsoft Dynamics 365 Business Central (New)**. |
    | Beskrivelse | A brief description of the service, such as "Meeting portal for NN municipality". | Specify **Integration with Microsoft Dynamics 365 Business Central**. |
    | Tillatte grant types | A grant represents the user's consent to retrieve an access token. By selecting specific grants, you consent to the corresponding methods of retrieving an access token. | <p>Select the following grant types:</p><ul><li>**authorization_code**</li><li>**refresh_token**</li></ul> |
    | Klientautentiseringsmetode | The method of authentication of your client. | Specify **client_secret_post**. |
    | Applikasjonstype | The application or client type is the type of runtime environment that the client is running under. OAuth2 chapter 2.1 lists the available options. The choice of client type is a security assessment that the customer performs. | Select **web**. |
    | Gyldig(e) redirect uri-er | This parameter applies only to personal sign-in integrations. It specifies the URIs that the client is allowed to go to after sign-in. | The URI is a combination of your base URI and OAuthLanding.htm. This value differs depending on whether you use Business Central online or on-premises. For online, use the following URI, `https://businesscentral.dynamics.com/OAuthLanding.htm`. Here's an example of a URI for on-premises: `https://<hostname>/OAuthLanding.htm`. |
    | Gyldig(e) post logout redirect uri-er | This parameter applies only to personal sign-in integrations. It specifies the URIs that the client is allowed to go to after sign out. | Specify `https://skatteetaten.no`. |
    | Frontchannel logout uri | The URI that the provider sends a request to upon sign out that another client triggers in the same session. If you don't set this parameter, you risk that users remain signed in to your service when they sign out of ID-porten. | The value should be blank. |
    | Frontchannel logout krever sesjons-id | This parameter applies only to personal sign-in integrations. It's a flag that determines whether the issuer and session ID parameters are passed together with **frontchannel_logout_uri**. | Leave this checkbox cleared. |
    | Tilbake-uri | This parameter applies only to personal sign-in integrations. It specifies the URI that a user is sent back to when they cancel sign-in. | Specify `https://skatteetaten.no`. |
    | PKCE | This parameter specifies the code challenge method. | Specify **S256**. |
    | Authorization levetid (sekunder) | The lifetime of the registered authorization. In an OpenID Connect context, this authorization gives access to the "userinfo" endpoint. The value must be specified in seconds. | Specify **31536000**, which is one year. |
    | Access token levetid (sekunder) | The lifetime of the issued **access_token** in seconds. | Specify **7200**, which is two hours. |
    | Refresh token levetid (sekunder) | The lifetime of the issued **refresh_token** in seconds. | Specify **0**, which is zero. |
    | Refresh token type | <ul><li>**One-time** – You get a new **refresh_token** at each refresh of **access_token**.</li><li>**Reusable** – A refresh of **access_token** doesn't change **refresh_token**.</li></ul> | Specify **Engangs**. |

:::image type="content" source="../../media/nor-vat-return-integration-point-new.png" alt-text="Integration point settings for Norwegian VAT":::

### Set up electronic VAT reporting

To make it easier to set up VAT reporting, [!INCLUDE[prod_short](../../includes/prod_short.md)] provides the **Set up an electronic VAT submission** assisted setup guide.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Assisted Setup**, and then choose the related link.
1. Choose **Set up an electronic VAT submission** to start the assisted setup guide. Choose **Next** and accept the consent prompt to enable electronic VAT submission.
1. Choose **Open Electronic VAT Setup**. Enter **Client ID**, **Client Secret**, and **Redirect URL** from your company's registration for ID-Porten.
1. Choose **Open OAuth 2.0 setup**. On **OAuth 2.0 Setup**, choose **Request Authorization Code**, and complete sign-in with a user who is allowed to submit VAT returns.
1. After authorization succeeds, accept the prompt to open **Company Information** and verify your company's VAT registration number.
1. Return to the guide, confirm that the status is **Authorized**, and choose **Next**.
1. If VAT codes are missing, choose **Show Codes** to review them, and then **Add Codes**.
1. Choose **Update** to mark the VAT codes that must report a rate and assign their **VAT Rate For Reporting**. Review the codes and rates on **VAT Reporting Codes**, and then choose **Next**.
1. Choose **Open VAT Posting Setup** to review the combinations and assign **Sales VAT Reporting Code** and **Purchase VAT Reporting Code**. If posting accounts or other settings need changes, use **VAT Posting Setup** to make them. Close the page when finished.
1. To create a VAT statement, select **VAT Statement Template Name**, enter a new **VAT Statement Name**, and choose **Create VAT statement**. The statement uses the VAT business and product posting group combinations and reporting codes in the posting setup. If you already have the required statement, skip this action.
1. Choose **Next**, and then **Finish**.

For MinID sign-in, have the identification number, password, and PIN available, and follow the portal prompts. The electronic IDs offered and their sign-in sequence depend on the external portal.

[!INCLUDE[prod_short](../../includes/prod_short.md)] provides 32 VAT codes, but some codes don't require VAT reporting. Codes can also vary by industry or type of business. On **VAT Reporting Codes**, use **Edit List** to review and maintain the codes and rates relevant to your business. Learn more about posting setup in [Set Up Calculations and Posting Methods for Value-Added Tax](../../finance-setup-vat.md).

> [!NOTE]
> **Update** assigns the rates that were valid in December, 2021. It isn't a live rate update from the tax authorities. You're responsible for ensuring that those rates are still valid.

Authorization is specific to the current user and company. Each user who submits returns or retrieves responses needs an enabled **OAuth 2.0 Setup** for electronic VAT submission. Completing the guide without authorization doesn't authorize that user.

> [!NOTE]
> The extension automatically creates the **ELEC VAT** configuration for **VAT Return**, including line suggestion, content generation, validation, submission, and response handling. You can view it on **VAT Reports Configuration**. When the guide initializes an existing **VAT Report Setup**, it also selects **Report VAT Base** and **Report VAT Note**.

The extension supplies these production connection defaults on **Electronic VAT Setup**:

| Field | Default value |
|---|---|
| **Authentication URL** | `https://idporten.no` |
| **Login URL** | `https://login.idporten.no` |
| **Validate VAT Return URL** | `https://idporten.api.skatteetaten.no/api/mva/grensesnittstoette/mva-melding/valider` |
| **Exchange ID-Porten Token URL** | `https://platform.altinn.no/authentication/api/v1/exchange/id-porten` |
| **Submission Environment URL** | `https://skd.apps.altinn.no/` |
| **Submission App URL** | `skd/mva-melding-innsending-v1/` |

The OAuth setup uses the scopes `openid`, `skatteetaten:mvameldingvalidering`, and `skatteetaten:mvameldinginnsending`. It uses `/authorize` for authorization and `/token` for access and refresh tokens, with the `code` response type, PKCE **S256**, and **Use Nonce** enabled. Authorization uses **Login URL**; token requests use **Authentication URL**.

#### Electronic VAT setup for existing users  

> [!IMPORTANT]
> If you're an existing user, you need to manually change some information on the **Electronic VAT Setup** page.  

To update the electronic VAT setup for the use of the new ID-porten system, follow these steps:

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Electronic VAT Setup**, and then choose the related link.
1. On the **Electronic VAT Setup** page, select the **General** FastTab, and then update the following values:

   1. In the **Authentication URL** field, specify `https://idporten.no`.
   1. In the **Login URL** field, specify `https://login.idporten.no`.

1. Close the page.

> [!NOTE]
> You can't open the sign-in page from a bookmark or a link.

### VAT report setup

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Report Setup**, and then choose the related link.
1. On the **General** FastTab, to let users modify VAT reports that were submitted to the tax authorities, select the **Allow Modification** field. If the field isn't selected, users must create a corrective or supplementary VAT report instead.
1. On the **General** FastTab, select the **Report VAT Base** field if the VAT base must be calculated and shown to the user in the VAT reports.
1. On the **General** FastTab, select the **Report VAT Note** field to make **Note** available on the **VAT Return** lines.
1. On the **Numbering** FastTab, specify the default number series to use for all standard VAT reports.
1. On the **Return Period** and **VAT Group Management** FastTabs, specify the relevant information.  
1. Choose the **OK** button.  

## Create and submit a VAT return

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Returns**, and then choose the related link.
1. Choose the **New** action.
1. In the **Version** field, choose **ELEC VAT**.
1. Optionally, in the **KID** field, specify a payment identification number.
1. Choose **Suggest Lines** to open the **VAT Report Request Page** page, where you specify criteria for generating lines for the report.
1. After you specify the criteria, choose **OK**.  
1. On the **VAT Return** page, choose **Release** to run local validation.
1. To submit the VAT return, choose **Submit**. [!INCLUDE [prod_short](../../includes/prod_short.md)] validates each report line through Skatteetaten's service before submitting the return through Altinn. After successful submission, the status changes to **Submitted**.
1. To view whether the tax authorities accepted your submission, choose **Receive Response**.

> [!NOTE]
> The response from the tax authority isn't immediately available. If it isn't ready, the status doesn't change. When feedback is available, **Receive Response** changes the status to **Accepted** or **Rejected**. For a rejection, download the response message and check the attached documents.

Release checks include a company VAT registration number and, for codes that report a VAT rate and have a nonzero base, a comparison of the VAT amount with the base multiplied by the reporting rate. A difference greater than 1 causes an error. **Disable Checks On Release** on **Electronic VAT Setup** skips these extension-specific local checks, not the service validation during submission.

If **Report VAT Note** is selected on **VAT Report Setup**, you can enter free text in **Note** on the VAT return lines. The text is included in the submission unless the VAT reporting code has a **VAT Note Code**. In that case, the predefined note is exported instead.

**KID** is optional when preparing the return. A value you enter is included in the submission. Retrieving feedback can also update **KID** from the returned payment information.

## Troubleshoot your connection to ID-Porten

If you don't receive a response after you submit your return, such as within 24 hours, contact ID-Porten and ask them to verify that they received your return. To help them identify your return, you can send the value from **Message ID** on the **General** FastTab of **VAT Return**. This value identifies the Altinn submission instance. You can also use page inspection to get the value. Learn more in [Inspecting Pages in Business Central](../../across-inspect-page.md).

You can also send a copy of the XML files for your submission and the response you received. To get the files, on the **VAT Return** page, choose the **Download Submission Message** and **Download Response Message** actions.  

## <a name="vat-periods"></a>Close VAT periods

To align with legal requirements, VAT periods are to be closed after settling. Normally, a fiscal year consists of six VAT periods, numbered 1 to 6. When the VAT is settled, the period is closed for further posting.  

> [!TIP]
> Not all organizations use the standard six VAT periods. Which periods the current organization uses is defined in the **VAT Period** page.

You can view information about settled periods in the **Settled VAT Period** page. The closed periods are created by the report **Calc. and Post VAT Settlement** when you post VAT. If you want to post in the closed VAT period, you can open the period again by clearing the **Closed** field.  

## Tradesettlement report

Before January 2022, you used the **Tradesettlement** report to report VAT. This report is no longer described in this article, but you can read about it in the [Dynamics NAV 2016 documentation archive](/previous-versions/dynamicsnav-2016/dn283106(v=nav.90)).  

## Related information

- [Norwegian VAT Codes](norwegian-vat-codes.md)  
- [Proportional VAT](proportional-vat.md)  
- [Norway Local Functionality](norway-local-functionality.md)  
- [Work with VAT on Sales and Purchases](../../finance-work-with-vat.md)  
- [Set Up Calculations and Posting Methods for Value-Added Tax](../../finance-setup-vat.md)  
- [The VAT Group Management Extension](../../ui-extensions-vat-group.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
