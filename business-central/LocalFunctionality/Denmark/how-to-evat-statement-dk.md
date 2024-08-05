---
title: Submit VAT returns electronically
description: This article describes how to set up and submit value-added tax (VAT) returns electronically in Denmark.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: vat, return, statement, electronic, denmark, submission, skat
ms.search.form: 
ms.date: 04/24/2024
ms.author: altotovi

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Submit VAT returns electronically

In the Danish localization, Microsoft Dynamics 365 [!INCLUDE [prod_short](../../includes/prod_short.md)] supports using the Danish Tax Agency's VAT API to report value-added tax (VAT) returns.  

> [!IMPORTANT]
> This feature allows to report **_draft VAT Return version_** to skat.dk website from [!INCLUDE [prod_short](../../includes/prod_short.md)]. You will still need to manually login into your account on the tax authorities site, review the draft and submit it finally. Reporting such draft needs to be set up first in the tax authorities account. (See “Onboarding legal entities” on skat.dk)

> [!NOTE]
> Before you begin, make sure that the **VAT Return E-Submission** app has been installed and enabled. 

To generate a VAT return and send it directly to the Danish Tax Agency's VAT API, complete the following setup:

- On the **Company Information** page, configure the **Registration No.** and **VAT Registration No.** fields for the legal entity. In the **Registration No.** field, enter the legal entity's Central Business Register (CVR) number.
- On the **VAT Posting Setup SAF-T** page, associate a VAT posting group setup with **Sales VAT Reporting Code** and **Purchase VAT Reporting Code**.
- Obtain certificates to work with the Danish Tax Agency's VAT API, and store them in the Azure key vault.

## Set up VAT return submission

Complete the following procedures to set up VAT return submission.

### Set up certificates

> [!NOTE]
> If you use [!INCLUDE [prod_short](../../includes/prod_short.md)] online, you do not need to configure your certificates, as you will use preinstalled Microsoft security certificate for VAT submission. 

If you use on-premises [!INCLUDE [prod_short](../../includes/prod_short.md)] version, before you begin the setup, an administrator must configure the certificates using the following procedure: 

1. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Certificates**, and then select the related link.
2. Select **New** to create a _client certificate_. This certificate is a company certificate (VOCES3) that's issued by MitID Erhverv (OCES3). It must include a private key for signing.
3. Select **New** to create a _server certificate_. This certificate is a certificate that NemVirksomhed provides to verify response XML.

> [!NOTE]
> If you are using the online option, you need to use the Microsoft Denmark A/S **CVR number** to authorize your Business Central in your company's _skat.dk_ profile. This allows Business Central to submit VAT drafts, as Microsoft already provides a default certificate for connecting with _skat.dk_.

### Set up electronic VAT declaration 

Follow these steps to configure the electronic VAT declaration:

1. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Electronic VAT Declaration Setup**, and then select the related link.  
2. On the **Electronic VAT Declaration Setup** page, enter your legal SE/CVR number in the **ERP SE Number** field as a number used to report the VAT return to Skat service. Once you enter your CVR number, you'll have to give a consent that your data would be shared with the third party system (skat.dk) in this process. If you agree, you need to select the **I accept** button.  

### Set up VAT report  

Follow these steps to configure a VAT reporting:

1. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Reports Configuration**, and then select the related link.  
2. Make sure that the setup for VAT Return with version **DK ELE.VAT** exists, and gets selected in the **VAT Report Version** field on the **VAT Reports Configuration** page. This setup will activate the following fields: **Suggest Lines Codeunit ID**, **Content Codeunit ID**, **Submission Codeunit ID**, and **Validate Codeunit ID** and populate the values.
3. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Report Setup**, and then select the related link. 
4. On the **VAT Report Setup** page, select the **Return Period** FastTab, and verify that the **Report Version** field contains the **DK ELE.VAT** setup report version that you previously configured.
5. The **Manual Receive Codeunit ID** field where you can specify the codeunit ID associated with a manual receipt of the VAT return periods. If codeunit `13610` is selected, the **Manual Receive Codeunit Caption** field will be automatically populated with the
**Elec. VAT Decl. Get Periods** value.

### Set up VAT statements

Follow these steps to configure a VAT statement:

1. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statements**, and then select the related link.
2. On the **VAT Statements** page, create a new VAT statement by using the **VAT Statement Name** page, or use a default statement.
3. On the **VAT Statement** page, use the **Box No.** field to set up VAT setup lines so that they point VAT setups to the correct export boxes. Each box number is linked to the `ModtagMomsangivelseForeloebig` XML field.
4. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Return E-Submission Setup**, and then select the related link.
5. Set up endpoints for the **VirksomhedKalenderHent**, **ModtagMomsangivelseForeloebig**, and **MomsangivelseKvitteringHent** services. You can select **Set Default Endpoints** to have the system run automatically. Alternatively, you can make updates if the default values are no longer usable.
6. Set **Client Certificate Code** and **Server Certificate Code** to the certificates that you previously created and uploaded on the **Certifications** page.

## Use and submit a VAT return

Follow these steps to submit a VAT return:

1. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Return Periods**, and then select the related link. 
2. Select **Get VAT Return Periods**. Dynamics 365 [!INCLUDE [prod_short](../../includes/prod_short.md)] contacts the **VirksomhedKalenderHent** endpoint and gets VAT return periods for your company.  
3. Select an existing VAT return period, and then select **Create VAT Return**. [!INCLUDE [prod_short](../../includes/prod_short.md)] creates a new **VAT Return** record.  
4. Select **Suggest Lines** to get suggested and created lines/records for the VAT return.   
5. When you check and confirm the validity of the suggested lines, select **Release** to protect any changes in the VAT return before you submit the return. 
6. When you're ready to submit the VAT return, select **Submit** to generate the XML body for the request and submit the request to the **ModtagMomsangivelseForeloebig** service. 

If the process is done correctly, you receive a "Request has been submitted" message, and the VAT return's status is changed to **Submitted**.

You can double-check the request message for the VAT return later by choosing the **Download** action.  

## After a VAT return is submitted

You won't always know the final status that's confirmed by the authorities. Therefore, [!INCLUDE [prod_short](../../includes/prod_short.md)] regularly checks the **MomsangivelseKvitteringHent** service through the configured endpoint, to look for any response about submitted VAT returns. If a response is available, it's received, and the status of the company's VAT return is changed to **Accepted** or **Rejected**.

You can download a **Response** message by selecting **Download**. If the status is **Accepted**, you can save the receipt link for the VAT return.

## See also

[Financial Management](../../finance.md)    
[VAT Management Overview](../../finance-manage-vat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
