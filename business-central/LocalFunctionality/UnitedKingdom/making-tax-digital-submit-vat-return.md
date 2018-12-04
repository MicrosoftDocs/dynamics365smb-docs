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
# Making Tax Digital

Her Majesty's Revenue and Customs (HMRC) is implementing the first step of Making Tax Digital which imposes new requirements on VAT registered businesses above the VAT threshold. Requirements will be implemented in phases. In the first phase, with a deadline in April 2019, the following requirements will have effect:

* Keeping records digitally - Businesses must now keep all their records digitally. For users of ERP systems this will not have any impact since they already keep their records digitally in these systems.

* Submit VAT return electronically using [software recognized by HMRC](https://www.gov.uk/guidance/software-for-sending-income-tax-updates)

[!INCLUDE[d365fin](../../includes/d365fin_md.md)] already supports submitting the VAT Return to HMRC using the GovTalk service. From April 2019 HMRC is switching to newer technology and communication mechanisms which required changes in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].

## Making Tax Digital VAT in Dynamics 365 Business Central

[!INCLUDE[d365fin](../../includes/d365fin_md.md)] has functionality to create VAT reports, called a VAT Return. The Making Tax Digital VAT features extend this foundational VAT capability to allow for communication with HMRC.
The Making Tax Digital VAT features enables you to:

* Retreive VAT Obligations from HMRC

* Get reminded about upcoming or due VAT obligations

* Submit VAT Returns to HMRC

* View the VAT Return

* View VAT payments with HMRC

* View VAT liabilities with HMRC

## Set up Making Tax Digital VAT

The Making Tax Digital feature revolvees around the communication with HMRC which happens through a Service Connection.

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Connections**, and then choose the related link.  

2. In the **Service Connections** window, choose **HMRC VAT Setup**. (if you want to just test these features, instead choose  **HMRC VAT Sandbox Setup**)

3. The Service Connection is pre-filled with information needed to communicate with HMRC but to complete this setup you need to request an authorization code. Choose **Process** and select **Request Authorization Code**. This will open a browser and open a GOV.UK web page at HMRC on which to make the authorization code request.

4. First, HMRC informs you that the **Dynamics 365 Business Central MTD VAT** application on HMRC needs to be granted authority to interact with HMRC on your behalf. The **Dynamics 365 Business Central MTD VAT** application is an application that Microsoft manages on the HMRC web site and this is needed to setup the integration. Choose **Continue**.

5. On the next page you will be asked to sign in with your HMRC credentials. These credentials must be requested directly with the HMRC. After signing in the HMRC will present you with a page where you must grant the **Dynamics 365 Business Central MTD VAT** application authority to interact with HMRC on your behalf. Choose **Grant authority**.

6. A confirmation page now displays "Authorisation granted" and you must copy the authorisation code shown on the page. Choose **Copy**.

7. Return to the Service Connection you are setting up and paste the authorization code into the **Enter Authorisation Code** field shown in the **Request Authorisation Code** FastTab and press **Enter**.

8. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] will now use the authoriasation code and attempt to communicate with HMRC to test the setup of the Service Connection and display a confirmation if the authorisation was successful. In this confirmation you will be asked to check the setup of your VAT Registration Number in the Company Information. Choose **Yes** if you want to open Company Information and check if the number is correct and the one youe have used to register with HMRC.

You are now ready to use the features that communicates with HMRC.

## VAT Obligations (VAT Return Periods)

HMRC maintains a list of VAT Obligations for companies and exposes this information through their APIs. This makes it possible for [!INCLUDE[d365fin](../../includes/d365fin_md.md)] to read these and store them. These VAT Obligations hold information about the period to which an obligation is related and the due date at which the VAT Return must be submitted. These VAT Obligations are stored in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] as [**VAT Return Periods**](https://businesscentral.dynamics.com?page=737). Because VAT Return Periods holds this information [!INCLUDE[d365fin](../../includes/d365fin_md.md)] is able to:

* Remind you aboutof due or overdue VAT Returns.

* Automatically use the periods when creating VAT Returns, so you do not have to manually enter Start- and End dates.

To retrieve the VAT Return Periods:

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter [**VAT Return Periods**](https://businesscentral.dynamics.com?page=737), and then choose the related link.  

2. In the **VAT Return Periods** window, choose **Process** and select **Get VAT Return Periods**.

3. Enter the **Start Date** and **End Date** to specify for which period to get the VAT Return Periods and choose **OK**.

4. The VAT Return Periods are now retrieved from HMRC and stored in the [**VAT Return Periods**](https://businesscentral.dynamics.com?page=737) table and a confirmation will display how many periods were retrieved.

## VAT Returns

VAT Returns in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] can be created directly from the [VAT Return Period](https://businesscentral.dynamics.com?page=737).

To create a VAT Return:

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Return Periods**, and then choose the related link.  

2. In the **VAT Return Periods** window, choose **Process** and select **Create VAT Return**.

3. A confirmation will display that a VAT Return has been created. If you want to open the VAT Return, choose **Yes**.

4. In the **VAT Return** window you must calculate and prepare the VAT amounts to be included in the VAT Return. To calculate and prepare the amounts for the VAT Return choose **Process** and select **Suggest Lines**. This will display a window with settings related to find VAT entries to use for the VAT Return. Set the fields to the desired settings and choose **OK**.

5. VAT amounts will now display in the **Report Lines** section in the **VAT Return** window. The VAT Return must now be released which will prepare it for submission. Choose **Process** and select **Release**. This will not submit the VAT Return but just make in ineditable. If you want to enable editing again you must reopen the VAt Return. 

6. When you are ready to submit the VAT Return choose **Process** and select **Submit**. This will send the VAT Return to HMRC.  

## VAT Payments and Liabilities

HMRC also makes it possible for [!INCLUDE[d365fin](../../includes/d365fin_md.md)] to retrieve information about VAT liabilities your company has with HMRC and the VAT payments made from your company to HMRC. This gives you a near real time status on your VAT. VAT Liabilities represent amounts that was owed to HMRC. The VAT Liabilities also shows if there are outstanding amounts to be paid. VAT Payments show the actual payments the HMRC has received from your company.

To retrieve VAT Liabilities:

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter [**VAT Liabilities**](https://businesscentral.dynamics.com?page=10530), and then choose the related link.  

2. In the [**VAT Liabilities**](https://businesscentral.dynamics.com?page=10530) window, choose **Process** and select **Get Liabilities**.

3. Enter the **Start Date** and **End Date** that specifies the period for which you want to retrieve VAT liabilities and choose **OK**.

4. The VAT liabilities are now retrieved from HMRC and stored in the [**VAT Liabilities**](https://businesscentral.dynamics.com?page=10530) table and a confirmation will display how many periods were retrieved.

To retrieve VAT Payments:

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter [**VAT Payments**](https://businesscentral.dynamics.com?page=10531), and then choose the related link.  

2. In the [**VAT Payments**](https://businesscentral.dynamics.com?page=10531) window, choose **Process** and select **Get Payments**.

3. Enter the **Start Date** and **End Date** that specifies the period for which you want to retrieve VAT payments and choose **OK**.

4. The VAT payments are now retrieved from HMRC and stored in the [**VAT Payments**](https://businesscentral.dynamics.com?page=10531) table and a confirmation will display how many periods were retrieved.


## See Also
[United Kingdom Local Functionality](united-kingdom-local-functionality.md)  
[The GetAddress.io UK Postcodes Extension](../../ui-extensions-getaddressio.md)  
[Customizing [!INCLUDE[d365fin](../../includes/d365fin_md.md)] Using Extensions](../../ui-extensions.md)  
[Working with [!INCLUDE[d365fin](../../includes/d365fin_md.md)]](../../ui-work-product.md)  
