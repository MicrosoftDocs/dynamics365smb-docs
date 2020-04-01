---
title: 'Making Tax Digital - Submitting VAT Returns | Microsoft Docs'
description: Business Central includes features to manage your VAT and comply with Making Tax Digital. This article describes how to set up and use these features.
author: sorenfriisalexandersen
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: making tax digital, vat, vat return, submit vat, making tax digital software, hmrc, tax
ms.date: 04/01/2020
ms.author: soalex

---
# Making Tax Digital in the United Kingdom
Her Majesty's Revenue and Customs (HMRC) is implementing the first step of Making Tax Digital, which imposes new requirements on VAT registered businesses above the VAT threshold. Requirements will be implemented in phases. In the first phase, with a deadline in April, 2019, the following requirements will take effect:

* Keeping records digitally - Businesses must now keep all their records digitally. For users of ERP systems this will not have any impact since they already keep their records digitally in these systems.  
* Submit VAT return electronically using [software recognized by HMRC](https://www.gov.uk/guidance/software-for-sending-income-tax-updates).  

[!INCLUDE[d365fin](../../includes/d365fin_md.md)] already supports submitting VAT returns to HMRC using the GovTalk service. From April, 2019 HMRC is switching to newer technology and communication mechanisms that required changes in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].

## Making Tax Digital for VAT Capabilities in Dynamics 365 Business Central
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)] you can use the VAT Return report for creating VAT reports. The Making Tax Digital VAT features extend this capability to communicate with HMRC. For example, the Making Tax Digital VAT extension lets you:

* Retrieve VAT obligations from HMRC
* Get reminded about VAT obligations that are approaching or already past due
* Submit VAT returns to HMRC  
* View the VAT return  
* View VAT payments with HMRC  
* View VAT liabilities with HMRC  

## Set up Making Tax Digital for VAT
The Making Tax Digital feature uses a service connection to communicate with HMRC. To make it easy to establish communications, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] provides the **HMRC VAT Setup** service connection, which contains most of the information needed to communicate with HMRC. To finish the connection, you must give the **Dynamics 365 Business Central MTD VAT** application the authority to interact with HMRC on your behalf. Microsoft manages the **Dynamics 365 Business Central MTD VAT** application on the HMRC web site, and the application is a requirement for the connection. You give permission by requesting an authorization code from HMRC, and then copying the code to the service connection. The following steps describe how to set up the service connection.   
  
> [!Note]
> If you are using an on-premises version, there are some additional steps to set up the features for Making Tax Digital. In the cloud version, these happen automatically. For more information, see the section titled [Additional Setup Requirements for On-Premises Versions](#additional-setup-requirements-for-on-premises-versions) below.

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Connections**, and then choose the related link.  
2. On the **Service Connections** page, choose **HMRC VAT Setup**.

    > [!Note]
    > If you use an on-premises version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)] you will also need to provide a client ID and client secret. If you are not sure what these are, contact your partner. They can get the information for you on [PartnerSource](https://mbs.microsoft.com/partnersource/global/deployment/downloads/tax-regulatory-updates/365dynamicsbctaxdigitsupinfo). 

3. To open a GOV.UK website and request an authorizaton code, choose **Process**, then **Request Authorization Code**, and then choose **Continue**. 
4. Sign in with your HMRC credentials. To allow the **Dynamics 365 Business Central MTD VAT** application to interact with HMRC on your behalf, choose **Grant authority**.
5. A confirmation page displays "Authorization granted" and an authorization code. To copy the authorization code, choose **Copy**.
6. Return to the service connection you are setting up, and paste the authorization code in the **Enter Authorization Code** field. Then choose **Enter**. Note, that the authorization code is valid for 10 minutes and must be entered into [!INCLUDE[d365fin](../../includes/d365fin_md.md)] before expiry in order to set up the connection correctly.

    > [!Note] 
    > [!INCLUDE[d365fin](../../includes/d365fin_md.md)] will use the authorization code to test whether the service connection can communicate with HMRC. If the connection is successful, a confirmation page prompts you to verify your VAT registration number. To open the **Company Information** page and verify the number is correct, and the one you have used to register with HMRC, choose **Yes**.

### Additional Setup Requirements for On-Premises Versions
1. You must add a VAT report configuration on the **VAT Reports Configuration** page.  
  
    a. Create a new configuration, and choose the VAT Return type.  
    b. Give the configuration a descriptive name, such as **HMRC MTD**.  
    c. In the **Suggest Lines Codeunit ID** field, choose codeunit **745**.  
    d. In the **Content Coneunit ID** field, choose codeunit **10531**.  
    e. In the **Submission Codeunit ID** field, choose codeunit **10532**.  
    f. In the **Validate Codeunit ID** field, choose codeunit **10533**.  
    g. Fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]

2. You must edit the VAT report setup on the **VAT Report Setup** page.  
  
    a. Expand the **Return Period** FastTab.  
    b. In the **Report Version** field, choose the VAT report configuration that you created in the previous step.  
    c. In the **Manual Receive Codeunit ID** field, choose codeunit **10534**.  
    d. In the **Receive Submitted Return Codeunit ID** field, choose codeunit **10536**.  
    e. Optional: If you want to automatically update the information about VAT obligations, specify how often to do so in the **Update Period Job Frequency** field, and then specify codeunit **10535** in the **Auto Receive Codeunit ID** field.  
    f. Fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]

## VAT Obligations
HMRC maintains a list of VAT obligations for companies, which are the periods for which they must report VAT and the due date for the report. HMRC exposes this information through their APIs, which enables [!INCLUDE[d365fin](../../includes/d365fin_md.md)] to retrieve the obligations. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] stores VAT obligations as **VAT Return Periods**, and uses them to:

* Remind you about VAT returns that are due or overdue.
* Automatically enter start and end dates when you create VAT returns.

### To retrieve the VAT return periods from HMRC:
1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Return Periods**, and then choose the related link.  
2. On the **VAT Return Periods** page, choose **Process**, and then choose **Get VAT Return Periods**.
3. Enter the **Start Date** and **End Date** to specify the period for which to get the VAT return periods, and then choose **OK**.  
    
The VAT obligations are now retrieved from HMRC and you can view them on the **VAT Return Periods** page. A confirmation page shows how many obligations were retrieved.

  > [!NOTE]  
  >  Do not create VAT return periods manually when submitting VAT Returns to HMRC. VAT return periods must be retrieved from HMRC using the steps above. Creating them manually will result in inability to submit VAT Returns.  


## VAT Returns
Use this report to submit VAT for sales and purchase documents, such as purchase and sales orders,invoices, and credit memos.

### To create and submit a VAT return:
1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Return Periods**, and then choose the related link.  
2. On the **VAT Return Periods** page, choose **Process**, and then choose **Create VAT Return**.
3. If you want to open the VAT return, on the confirmation page, choose **Yes**.
4. On the **VAT Return** page, to calculate and prepare the amounts for the VAT return, choose **Process**, and then choose **Suggest Lines**. 
5. Fill in the fields as necessary, and choose **OK**. VAT amounts display in the **Report Lines** section on the **VAT Return** page.  
6. To release the VAT return and prepare it for submission, choose **Process**, and then choose **Release**. After you release a VAT return you cannot edit it. If you need to change something, you must reopen the return. Releasing the VAT return does not submit it.
6. To submit the VAT return to HMRC, choose **Process**, and then choose **Submit**.  

A successful submission of the VAT Return will result in a Status = Accepted on the VAT Return. This status is based on the submission result at the HMRC. If the status after submission is not set to Approved a previously submitted VAT Return can be retrieved from the HMRC.

### To receive previously submitted VAT Returns from HMRC
1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Return Periods**, and then choose the related link.  
2. On the **VAT Return Periods** page, choose <!-- Go the VAT Return Period Card for the selected VAT Return Period>
3. On the **VAT Return Period Card** page, choose <!-- Receive submitted VAT Returns? >

## VAT Liabilities and Payments
If you want to check the status of your VAT, you can retrieve information from HMRC about your VAT liabilities and payments. VAT liabilities are the amounts that you owed to HMRC, and show if there are outstanding amounts to be paid. VAT payments are the actual payments your company has made to HMRC.

To retrieve VAT liabilities:

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Liabilities**, and then choose the related link.  
2. On the **VAT Liabilities** page, choose **Process**, and then select **Get Liabilities**.
3. Enter the **Start Date** and **End Date** of the period to retrieve VAT liabilities for, and then choose **OK**.

The VAT liabilities are now retrieved from HMRC and you can view them on the **VAT Liabilities** page. A confirmation page shows how many liabilities were retrieved.

To retrieve VAT payments from HMRC:

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Payments**, and then choose the related link.  
2. On the **VAT Payments** page, choose **Process**, and then choose **Get Payments**.
3. Enter the **Start Date** and **End Date** of the period to retrieve VAT payments for, and then choose **OK**.

The VAT payments are now retrieved from HMRC and you can view them on the **VAT Payments** page. A confirmation page shows how many VAT payments were retrieved.

## Not in scope of this feature
This integration to HMRC and support of Making Tax Digital for VAT does not include support for:
- Group VAT scenarios. While it is possible that your [!INCLUDE[d365fin](../../includes/d365fin_md.md)] submits VAT on behalf of a group of companies that share a VAT Registration Number (Group VAT) there is no built in mechanism for retreiving VAT entries from other companies in the group. There are currently no plans to support Group VAT and we refer to Microsoft partners to add this functioanlity.
- Agent services. Agents can submit VAT Returns on behalf of their customers and HMRC has solutions for that. This is currently not supported by [!INCLUDE[d365fin](../../includes/d365fin_md.md)].

## Connection errors with HMRC
If you experience "The operation has timed out" errors on an on-premises installation of [!INCLUDE[d365fin](../../includes/d365fin_md.md)] please check your firewall settings that may be blocking the communication to and from HMRC.

## Testing the integration to HMRC in a Sandbox

Due to a limitation at HMRC, it is not possible to send test submissions of VAT Returns and test the integration in non-production scenarios. You can only send real VAT returns. Certain online documentation at HMRC refers to the term *Sandbox*. This refers to and environment for software developers such as Microsoft and others for testing their features during development. this environment is not intended for customer testing and is unrelated to [!INCLUDE[prodshort](../../includes/prodshort.md)] sandboxes.

## See Also
[United Kingdom Local Functionality](united-kingdom-local-functionality.md)  
[The GetAddress.io UK Postcodes Extension](../../ui-extensions-getaddressio.md)  
[Customizing [!INCLUDE[d365fin](../../includes/d365fin_md.md)] Using Extensions](../../ui-extensions.md)  
[Working with [!INCLUDE[d365fin](../../includes/d365fin_md.md)]](../../ui-work-product.md)  
