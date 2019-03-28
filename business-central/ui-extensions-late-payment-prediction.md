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
ms.date: 04/01/2019
ms.author: bholtorf

---
# The Late Payment Prediction Extension  
Effectively managing receivables is important to the overall financial health of a business. The Late Payment Prediction extension can help you reduce outstanding receivables and fine-tune your collections strategy by predicting whether sales invoices will be paid on time. For example, if a payment is predicted to be late, you might decide to adjust the terms of payment or the payment method for the customer.

## What are Predictions Based On?  
The Late Payment Prediction extension uses a predictive model that we developed in Azure Machine Learning Studio and trained using data that is representative of a range of small to medium sized businesses. Though we have already trained and evaluated it, our predictive model will continue to learn from your data. The more you use the model and the more data you feed it, the more accurate predictions will become. By default, the extension evaluates the model and updates the predictions on a weekly basis. However, you can update the predictions whenever you want by choosing the **Update Prediction** action on the **Customer Ledger Entries** page.  

> [!Note]
> We use a bit of your compute time each week when we evaluate the model and update your predictions. In addition to manually updating your predictions, other actions that consume compute time are when you train the model (which you might do if you've recently added data) and when you evaluate the model (which looks at the quality of the model).

## Getting Started
The extension is free in [!INCLUDE[d365fin](includes/d365fin_md.md)], and we provide a subscription to Azure Machine Learning. The subscription offers 30 minutes of compute time per month. If you need more than that you can create your own predictive model and use it instead. For more information, see the section titled _Building Your Own Predictive Model_ later in this topic.  

When you open a posted sales document, a notification will display at the top of the page. To use the Late Payment Prediction Extension you can opt in by choosing **Enable** in the notification. Alternatively, you can set up the extension manually. For example, if you regret dismissing the notification.  

To enable the extension manually, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Connections**, and then choose the related link.  
2. Choose the **Late Payment Prediction Setup** option, and then fill in the fields as necessary.

## Viewing All Payment Predictions
If you enable the extension a **Payments Predicted to be Late** tile is available in the **Business Manager** Role Center. The tile displays the number of payments that are predicted to be late, and let's you open the **Customer Ledger Entries** page where you can dig deeper into the posted invoices. There are three columns to pay attention to:  

* **Late Payment** - Indicates whether the payment for the invoice is predicted to be late.
* **Prediction Confidence** - Indicates how reliable you should consider the prediction to be. **High** means that the prediction is at least 90% sure, **Medium** is between 80 and 90%, and **Low** is below 80%.
* **Prediction Confidence %** - Shows the actual percentage behind the confidence rating. By default, this column is not displayed, but you can add it if you want. For more information, see [Personalizing Your Workspace](ui-personalization-user.md).

> [!Tip]
> The Customer Ledger Entries page also shows a FactBox on the right. While you are reviewing predictions, the information in the **Customer Details** section can be helpful. When you choose the invoice in the list, the section shows information about the customer. It also let's you take immediate action. For example, if a customer frequently misplaces their wallet, you can open the Customer card from the FactBox and block the customer for future sales.  

## Viewing a Payment Prediction for a Specific Sales Document
You can also predict late payments up-front. On the **Sales Quotes**, **Sales Orders**, and **Sales Invoices** pages, you can use the **Predict Payment** action to generate a prediction for the sales document you're viewing.

<!--## Scheduling Payment Predictions
On the **Late Payment Prediction Setup** page you can schedule updates to payment predictions for a time that is convenient for you. -->

## Building Your Own Predictive Model
Interested in building your own predictive model? You can use Azure Machine Learning Studio to build your own predictive model and use it in [!INCLUDE[d365fin](includes/d365fin_md.md)]. To use your own model, you must subscribe to Azure Machine Learning. For more information, see [Azure Machine Learning Studio Documentation](https://go.microsoft.com/fwlink/?linkid=861765).  

We do, however, offer an easier way for you to create and use your own predictive model. You can share data from your invoices with our [Prediction Experiment for Dynamics 365 Business Central](https://go.microsoft.com/fwlink/?linkid=2086310) in Azure Machine Learning, and let our experiment create and train a predictive model based on your data. To share your data, on the **Late Payment Prediction Setup** page, choose the **Create My Model** action. Afterward, predictions will be based on your model and your data, not ours.  

> [!Note]
>   The quality of the model is important. When our predictive experiment uses your data to train a model it determines a quality value for the model as a percentage. The model quality indicates how accurate the model's predictions are likely to be. Several factors can impact the quality of a model. For example, these factors might be that there was not enough data, or the data did not contain enough variation. You can view the quality of the model you are currently using on the **Late Payment Prediction Setup** page. You can also specify a minimum threshold for the model quality. Models with a quality value below the threshold will not produce predictions.  

### To use your model instead of ours  
If you create your own model in Azure Machine Learning Studio, without using the tools in [!INCLUDE[d365fin](includes/d365fin_md.md)], you must provide your credentials so that [!INCLUDE[d365fin](includes/d365fin_md.md)] can access the model. There are a couple of steps to do that:

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Late Payment Prediction Setup**, and then choose the related link.  
2. Choose the **Use My Azure Subscription** check box.  
3. In the **Selected Model** field, choose **My Model**.  
4. On the **My Model Credentials** FastTab, enter the API URL and API key for your model.  

## See Also  
[Azure Machine Learning Studio Documentation](https://go.microsoft.com/fwlink/?linkid=861765)  
[Customizing Business Central Using Extensions](ui-extensions.md)  
[Welcome to [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  
