---
title: Predict Late Payments for Sales Documents | Microsoft Docs
description: Use our predictive model to predict whether an invoice will be paid on time.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customer, payment, invoice, sales, invoice, quote
ms.date: 04/01/2020
ms.author: bholtorf

---
# The Late Payment Prediction Extension  
Effectively managing receivables is important to the overall financial health of a business. The Late Payment Prediction extension can help you reduce outstanding receivables and fine-tune your collections strategy by predicting whether sales invoices will be paid on time. For example, if a payment is predicted to be late, you might decide to adjust the terms of payment or the payment method for the customer.

## Getting Started

When you open a posted sales document, a notification will display at the top of the page. To use the Late Payment Prediction Extension you can opt in by choosing **Enable** in the notification. Alternatively, you can set up the extension manually. For example, if you regret dismissing the notification.  

To enable the extension manually, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Late Payment Prediction Setup**, and then choose the related link.  
2. Fill in the fields as necessary.

> [!Note]
> If you decide to enable the extension manually, be aware that [!INCLUDE[d365fin](includes/d365fin_md.md)] will not allow you to do so if the quality of the model is low. The quality of the model indicates how accurate the model's predictions are likely to be. Several factors can impact the quality of a model. For example, there might not have been enough data, or the data did not contain enough variation. You can view the quality of the model you are currently using on the **Late Payment Prediction Setup** page. You can also specify a minimum threshold for the model quality.   

## Viewing All Payment Predictions
If you enable the extension a **Payments Predicted to be Late** tile is available in the **Business Manager** Role Center. The tile displays the number of payments that are predicted to be late, and let's you open the **Customer Ledger Entries** page where you can dig deeper into the posted invoices. There are three columns to pay attention to:  

* **Late Payment** - Indicates whether the payment for the invoice is predicted to be late.
* **Prediction Confidence** - Indicates how reliable you should consider the prediction to be. **High** means that the prediction is at least 90% sure, **Medium** is between 80 and 90%, and **Low** is below 80%.
* **Prediction Confidence %** - Shows the actual percentage behind the confidence rating. By default, this column is not displayed, but you can add it if you want. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

> [!Tip]
> The Customer Ledger Entries page also shows a FactBox on the right. While you are reviewing predictions, the information in the **Customer Details** section can be helpful. When you choose the invoice in the list, the section shows information about the customer. It also lets you take immediate action. For example, if a customer frequently misplaces their wallet, you can open the Customer card from the FactBox and block the customer for future sales.  

## Viewing a Payment Prediction for a Specific Sales Document
You can also predict late payments up-front. On the **Sales Quotes**, **Sales Orders**, and **Sales Invoices** pages, you can use the **Predict Payment** action to generate a prediction for the sales document you're viewing.

<!--## Scheduling Payment Predictions
On the **Late Payment Prediction Setup** page you can schedule updates to payment predictions for a time that is convenient for you. -->

## Design details
Microsoft deploys and operates number of predictive web services in all regions where [!INCLUDE[d365fin](includes/d365fin_md.md)] is available. Access to these web services is included in your [!INCLUDE[d365fin](includes/d365fin_md.md)] subscription. For more information, see the Microsoft Dynamics 365 Business Central Licensing Guide. The guide is available for download on the [Business Central](https://dynamics.microsoft.com/en-us/business-central/overview/) website.

The web-services work in three modes:
- Train model. The web service trains the model based on the provided dataset.
- Evaluate model. The web service checks whether the model returns reliable data for the provided dataset.
- Predict. Web-service applies the model to the provided dataset to make a prediction.

These web-services are stateless, meaning they use data only to calculate predictions on demand. They do not store data. 

> [!NOTE]  
>   You can use your own predictive web service instead of ours. For more information, see [Create and use your own predictive web service late payment prediction](#AnchorText). 

### Data required to train and evaluate the model 
For each **Customer ledger entry** that has a related **Posted Sales Invoice**:
- Amount (LCY) including Tax
- Payment terms in days is calculated as **Due Date** minus **Posting Date**.
- Whether there is an applied credit memo. 

Additionally, the record is enriched with aggregated data from other invoices that are related to the same customer. This includes the following:

- Total number and amount of paid invoices
- Total number and amount of invoices that were paid late
- Total number and amount of outstanding invoices
- Total number and amount of outstanding invoices that are already late
- Average days late
- Ratio: Number Paid Late/Paid invoices
- Ratio: Amount Paid Late/Paid invoices
- Ratio: Number Outstanding Late/Outstanding invoices
- Ratio: Amount Outstanding Late/Outstanding invoices
> [!Note]
> The information about the customer is not included in the dataset.

### Standard model and My model
The Late Payment Prediction extension contains a predictive model that is trained using data that is representative of a range of small to medium-sized businesses. When you start posting invoices and receiving payments, [!INCLUDE[d365fin](includes/d365fin_md.md)] will evaluate whether the standard model fits your business flow. 

If it appears that your processes do not match the standard model, you still can use the extension but you will need to get more data. Just continue to use [!INCLUDE[d365fin](includes/d365fin_md.md)].
> [!Note]
> We use a bit of your compute time each week when we evaluate and re-train the model. 

[!INCLUDE[d365fin](includes/d365fin_md.md)] runs training and evaluation automalically when there are enough paid and late invoices are available, however you can run it manually whenever you want.

#### To train and use your model
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Late Payment Prediction Setup**, and then choose the related link.  
2. In the **Selected Model** field, choose **My Model**.
3. Choose the **Create My Model** action, to train model on your data.  

## <a name="AnchorText"> </a>Create and use your own predictive web service for late payment prediction
You can also create your own predictive web service based on a public model named **Prediction Experiment for Dynamics 365 Business Central**. This predictive model is available online in the Azure AI Gallery. To use the model, follow these steps:  

1. Open a browser and go to the [Azure AI Gallery](https://go.microsoft.com/fwlink/?linkid=2086310).  
2. Search for **Prediction Experiment for Dynamics 365 Business Central**, and then open the model in Azure Machine Learning Studio.  
3. Use your Microsoft account to sign up for a workspace, and then copy the model.  
4. Run the model, and publish it as a web service.  
5. Make a note of the API URL and API key. You will use these credentials for a cash flow setup.  
6. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Late Payment Prediction Setup**, and then choose the related link.  
7. Choose the **Use My Azure Subscription** check box.
8. On the **My Model Credentials** FastTab, enter the API URL and API key for your model.  .  

## See Also  
[Azure Machine Learning Studio Documentation](https://go.microsoft.com/fwlink/?linkid=861765)  
[Customizing Business Central Using Extensions](ui-extensions.md)  
[Welcome to [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  
