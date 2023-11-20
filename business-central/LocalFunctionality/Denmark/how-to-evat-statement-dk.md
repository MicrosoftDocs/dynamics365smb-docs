---
title: Submit VAT returns electronically 
description: This article describes how to setup and submit VAT electronically in Denmark. 
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: vat, return, statement, electronic, denmark, submission
ms.search.form:  
ms.date: 11/17/2023
ms.author: altotovi

---

# Submit VAT returns electronically

Dynamics 365 Business Central supports reporting of VAT return by using the Danish Tax Agency's VAT API in Danish localization.  

To generate a VAT return and send it directly to the Danish Tax Agency's VAT API, the following setup must be complete:   

- Configure the **Registration No.** (CVR number) and VAT Registration No. fields of the legal entity on the **Company Information** page. 
- Associate a VAT posting group setup with **Sales** and **Purchase VAT Reporting Codes** on the **VAT Posting Setup SAF-T** page. 
- Obtain and store in the **Azure Key Vault** certificates to work with the _Danish Tax Agency's VAT API_.  

## VAT return submission setup  
Complete the following tasks to set up VAT return submission.

### Set up certificates 

Before you can begin the setup, an administrator must configure certificates. 

1. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Certificates**, and then select the related link.  
2. Select **New** to create a _Client Certificate_. This is a company certificate (VOCES3) issued by MitID Erhverv (OCES3), and must include a private key for signing. 
3. Select **New** to create a _Server Certificate_. This is a certificate provided by NemVirksomhed to verify response XMLs.  

### Set up VAT statements  

Follow these steps to configure a VAT statement. 

1. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statements**, and then select the related link.   
2. On the **VAT Statements** page, create a new **VAT Statement** using the **VAT Statement Name** page or use a default statement.   
3. On the **VAT Statement** page, set up VAT setup lines to point VAT setups to the correct export boxes using the **Box No.** field. Each box number equals is tied to the ModtagMomsangivelseForeloebig XML field.  
4. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Return E-Submission Setup**, and then select the related link. 
5. Set up endpoints for the **_VirksomhedKalenderHent_**, **_ModtagMomsangivelseForeloebig_**, and **_MomsangivelseKvitteringHent_** services. You can select **Set Default Endpoints** to have the system run automatically, or you can make updates if the default values are no longer usable. 
6. Set up **Client** and **Server Certificates Codes** to the ones created and uploaded in the previous step on the **Certifications** page.  

## Use and aubmit a VAT return  

Complete these steps to submit a **VAT Return**.  

1. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Return Periods**, and then select the related link.  
2. Select **Get VAT Return Periods** action. Dynamics 365 Business Central will contact the **_VirksomhedKalenderHent_** endpoint and get **VAT Return Periods** for your company.  
3. Select an existing **VAT Return Period** and then select **Create VAT Return**. Business Central will create a new **VAT Return** record.   
4. Select **Suggest Lines** to get suggested and created lines/records for this **VAT Return**.    
5. When you check and confirm validity of suggested lines, select **Release** action to protect any changes in VAT return before you submit the return.  
6. When you are ready to submit this VAT return, select **Submit** to generate the xml body for the request and submit the request to the **_ModtagMomsangivelseForeloebig_** service. 

If the process is done correctly, the message **Request has been submitted** appears and the **VAT Return** status changes to **Submitted**. 

You can double check the request message for the VAT return later, by selecting **Download**.   

## After a VAT return is submitted   

Because you won't always know the final status as confirmed by authorities, Business Central regularly checks the **_MomsangivelseKvitteringHent_** service through the configured endpoint for any response regarding submitted VAT returns. When a response is available, it's received, and the status of the company’s **VAT Return** is changed to**Accepted** or **Rejected**. 

You can download a **Response** message using the **Download** action and save the receipt link for the **VAT Return** if the status was **Accepted**.   


## See also

[Financial Management](../../finance.md)  
[VAT Management Overview](../../finance-manage-vat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
