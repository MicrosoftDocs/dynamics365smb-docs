---
title: Electronic submission of VAT Return Denmark 
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

# Electronic submission of VAT Return 

Dynamics 365 Business Central supports reporting of VAT return via the Danish Tax Agency's VAT API in Danish localization.  

To generate VAT return and sent it directly to the Danish Tax Agency's VAT API, the following setup must be completed:   

- Configure **Registration No.** (CVR number) and VAT Registration No. fields of legal entity on the **Company Information** page. 
- Associate VAT Posting Group Setup with **Sales** and **Purchase VAT Reporting Codes** in the **VAT Posting Setup SAF-T** page. 
- Obtain and store in the **Azure Key Vault** certificates to interoperation with _Danish Tax Agency's VAT API_.  

## VAT Return Submission Setup  

### Certificates Setup  

Before starting, administrator needs to configure certificates. To do this, follow next steps:  

1. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Certificates**, and then select the related link.  
2. Click **New** to create _Client Certificate_. This is company certificate (VOCES3) issued by MitID Erhverv (OCES3), and it must include private key for signing. 
3. Click **New** to create _Server Certificate_. This is certificate provided by NemVirksomhed to verify response XMLs.  

### VAT Statement Setup  

Follow next steps to configure **VAT Statement**:  

1. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statements**, and then select the related link.   
2. In the **VAT Statements** page, create a new **VAT Statement** using the **VAT Statement Name** page or use default one.   
3. In the **VAT Statement** page, set up **VAT Setup Lines** to point VAT setups to correct export boxes using the **Box No.** field. Each **Box No.** equals to respective ModtagMomsangivelseForeloebig XML field).  
4. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Return E-Submission Setup**, and then select the related link. 
5. Set up endpoints for **_VirksomhedKalenderHent_**, **_ModtagMomsangivelseForeloebig_** and **_MomsangivelseKvitteringHent_** services. Running the action **Set Default Endpoints** Business Central will do it automatically, or you can change if defaults are not good anymore. 
6. Set up **Client** and **Server Certificates Codes** to the ones created and uploaded in the previous step in the **Certifications** page.  

## Using and Submission of VAT Return  

To submit **VAT Return**, follow next steps:  

1. Select the ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Return Periods**, and then select the related link.  
2. Run the **Get VAT Return Periods** action, so Business Central will contact **_VirksomhedKalenderHent_** endpoint and get **VAT Return Periods** for your company.  
3. Select an existing **VAT Return Period** and run the **Create VAT Return** action so Business Central will create a new **VAT Return** record and on its open page.   
4. Run the **Suggest Lines** action to get suggested and created lines/records for this **VAT Return**.    
5. When you check and confirm validity of suggested lines, click the **Release** action to protect any changes in VAT return before submitting it.  
6. When you are ready to submit this VAT return, run the **Submit** action. This action will generate xml body for the request and submit the request to **_ModtagMomsangivelseForeloebig_** service. 

If complete process is done correctly, the message **Request has been submitted** will appear, and the **VAT Return** status will be changed to **Submitted**. 

You can double check the request message for the VAT return later, using the **Download** action.   

### After VAT Return Submission   

As the company does not know the final status confirmed by authorities, Business Central will regularly check **_MomsangivelseKvitteringHent_** service through configured endpoint for response regarding submitted **VAT Returns**. Whenever a response is available, it will be received, and the status of the company’s **VAT Return** will be changed to either **Accepted** or **Rejected**. 

Users will be able to download **Response** message using the **Download** action, as well as save the receipt link for the **VAT Return** if the status was **Accepted**.   


## See also

[Financial Management](../../finance.md)  
[VAT Management Overview](../../finance-manage-vat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
