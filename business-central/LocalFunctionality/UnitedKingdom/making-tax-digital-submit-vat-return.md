---
title: 'Making Tax Digital - Submitting VAT Returns | Microsoft Docs'
description: Business Central includes features to manage your VAT and comply with Making Tax Digital. This page contains information about these features and how to use them.
author: sorenfriisalexandersen
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: making tax digital, vat, vat return, submit vat, making tax digital software, hmrc, tax
ms.date: 12/01/2018
ms.author: soalex

---
# Making Tax Digital (UK)
<!--this is an extension, right? The next heading has "VAT," do we need that here too? Added "(UK)" but we can remove that if you prefer-->
Her Majesty's Revenue and Customs (HMRC) is implementing the first step of Making Tax Digital, which imposes new requirements on VAT registered businesses above the VAT threshold <!-- Is it "with revenues above the VAT threshold. And what is the threshold?-->. Requirements will be implemented in phases. In the first phase, with a deadline in April, 2019, the following requirements will take effect:

* Keeping records digitally - Businesses must now keep all their records digitally. For users of ERP systems this will not have any impact since they already keep their records digitally in these systems.  
* Submit VAT return electronically using [software recognized by HMRC](https://www.gov.uk/guidance/software-for-sending-income-tax-updates).  

[!INCLUDE[d365fin](../../includes/d365fin_md.md)] already supports submitting the VAT Return to HMRC using the GovTalk service. From April, 2019 HMRC is switching to newer technology and communication mechanisms which required changes in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].

## Making Tax Digital VAT Capabilities in Dynamics 365 Business Central
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] has functionality to create VAT reports, called a VAT Return. The Making Tax Digital VAT features extend this foundational VAT capability to allow for communication with HMRC.  

The Making Tax Digital VAT extension lets you:

* Retreive VAT obligations from HMRC <!--not sure what you mean by "obligations" here. Is it the same as "liabilities?" The term "requirements" is also used--> 
* Get reminded about VAT obligations that are approaching or already past due   
* Submit VAT returns to HMRC  
* View the VAT return  
* View VAT payments with HMRC  
* View VAT liabilities with HMRC  

## Set up Making Tax Digital VAT
<!--for?-->
The Making Tax Digital feature uses a service connection to communicate with HMRC. To make it easy to establish communications, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] provides the **HMRC VAT Setup** service connection, which contains most of the information needed to communicate with HMRC. To finish the connection, you must give the **Dynamics 365 Business Central MTD VAT** application the authority to interact with HMRC on your behalf. Microsoft manages the **Dynamics 365 Business Central MTD VAT** application on the HMRC web site, and the application is a requirement for the connection. You give permission by requesting an authorization code from HMRC, and then copying the code to the service connection. The following steps describe how to set up the service connection.   

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Connections**, and then choose the related link.  
2. On the **Service Connections** page, choose **HMRC VAT Setup**. 

    > [!Tip]
    > If you just want to try these features, choose **HMRC VAT Sandbox Setup** instead.  

3. To open a GOV.UK website and request an authorizaton code, choose **Process**, then **Request Authorization Code**, and then choose **Continue**. 
<!-- Don't think we need this step. I moved most of the description to the lead-in paragraph anyway. Need to confirm step 3 now though.   4. First, HMRC informs you that you must grant the **Dynamics 365 Business Central MTD VAT** application the authority to interact with HMRC on your behalf. Microsoft manages the **Dynamics 365 Business Central MTD VAT** application on the HMRC web site, and this is needed to setup the integration.-->
5. Sign in with your HMRC credentials. To allow the **Dynamics 365 Business Central MTD VAT** application to interact with HMRC on your behalf, choose **Grant authority**.
6. A confirmation page displays "Authorization granted" and an authorization code. To copy the authorization code, choose **Copy**.
7. Return to the service connection <!--page?--> you are setting up, and paste the authorization code in the **Enter Authorization Code** field. Then choose **Enter**.

    > [!Note] 
    > [!INCLUDE[d365fin](../../includes/d365fin_md.md)] will use the authorization code to test whether the service connection can communicate with HMRC. If the connection is successful, a confirmation page prompts you to verify your VAT registration number. To open the **Company Information** page and verify the number is correct, and the one you have used to register with HMRC, choose **Yes**.

## VAT Obligations
HMRC maintains a list of VAT obligations <!--should we say what an obligation is? It isn't clear to me what the difference between an obligation and a liability.--> for companies and exposes this information through their APIs. This makes it possible for [!INCLUDE[d365fin](../../includes/d365fin_md.md)] to read these and store them <!--store the vat obligations, right?-->. These VAT obligations hold information about the period to which an obligation is related and the due date for submitting the VAT return. These VAT obligations are stored in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] as [**VAT Return Periods**](https://businesscentral.dynamics.com?page=737). [!INCLUDE[d365fin](../../includes/d365fin_md.md)] uses VAT return periods to:

* Remind you about VAT returns that are due or overdue.
* Automatically enter start and end dates when you create VAT returns.

To retrieve the VAT return periods: <!--why do we need to retrieve the VAT return periods?-->

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter [**VAT Return Periods**](https://businesscentral.dynamics.com?page=737), and then choose the related link.  
2. On the **VAT Return Periods** page, choose **Process**, and then choose **Get VAT Return Periods**.
3. Enter the **Start Date** and **End Date** to specify the period for which to get the VAT return periods, and then choose **OK**.  
    
The VAT obligations are now retrieved from HMRC and stored in the [**VAT Return Periods**](https://businesscentral.dynamics.com?page=737) table <!--This should be a page, right? SaaS folks don't know what a table is.-->. A confirmation page shows how many obligations were retrieved.

## VAT Returns
You can create VAT returns on the [VAT Return Period](https://businesscentral.dynamics.com?page=737) page.

To create a VAT return:

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Return Periods**, and then choose the related link.  
2. On the **VAT Return Periods** page, choose **Process**, and then choose **Create VAT Return**.
3. If you want to open the VAT return, on the confirmation page <!--is it a page, or just a dialog?-->, choose **Yes**.
4. On the **VAT Return** page, to calculate and prepare the amounts for the VAT return, choose **Process**, and then choose **Suggest Lines**. 
5. Fill in the fields as necessary, and choose **OK**. VAT amounts display in the **Report Lines** section on the **VAT Return** page.  
6. To release the VAT return and prepare it for submission, choose **Process**, and then choose **Release**. After you release a VAT return you cannot edit it. If you need to change something, you must reopen the return. Releasing the VAT return does not submit it.
6. To submit the VAT return to HMRC, choose **Process**, and then choose **Submit**.  

## VAT Payments and Liabilities
If you want to check the status of your VAT, you can retrieve information about your VAT liabilities and payments to HMRC. VAT liabilities are amounts that you owed to HMRC, and show if there are outstanding amounts to be paid. VAT payments are the actual payments your company has made to HMRC.

To retrieve VAT liabilities:

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter [**VAT Liabilities**](https://businesscentral.dynamics.com?page=10530), and then choose the related link.  
2. On the [**VAT Liabilities**](https://businesscentral.dynamics.com?page=10530) page, choose **Process**, and then select **Get Liabilities**.
3. Enter the **Start Date** and **End Date** of the period to retrieve VAT liabilities for, and then choose **OK**.

The VAT liabilities are now retrieved from HMRC and stored in the [**VAT Liabilities**](https://businesscentral.dynamics.com?page=10530) table. <!--same comment as earlier--> A confirmation page shows how many liabilities were retrieved.

To retrieve VAT payments:

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter [**VAT Payments**](https://businesscentral.dynamics.com?page=10531), and then choose the related link.  
2. On the [**VAT Payments**](https://businesscentral.dynamics.com?page=10531) page, choose **Process**, and then choose **Get Payments**.
3. Enter the **Start Date** and **End Date** of the period to retrieve VAT payments for, and then choose **OK**.

The VAT payments are now retrieved from HMRC and stored in the [**VAT Payments**](https://businesscentral.dynamics.com?page=10531) table. A confirmation page shows how many VAT payments were retrieved.


## See Also
[United Kingdom Local Functionality](united-kingdom-local-functionality.md)  
[The GetAddress.io UK Postcodes Extension](../../ui-extensions-getaddressio.md)  
[Customizing [!INCLUDE[d365fin](../../includes/d365fin_md.md)] Using Extensions](../../ui-extensions.md)  
[Working with [!INCLUDE[d365fin](../../includes/d365fin_md.md)]](../../ui-work-product.md)  
