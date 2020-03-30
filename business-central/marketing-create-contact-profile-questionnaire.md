---
title: 'Use profiles to classify contacts'
description: 'Set up profile questionnaires to help classify your business contacts'
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: contacts, profiles
ms.author: edupont
ms.date: 04/01/2020
---

# Use Profile Questionnaires to Classify Business Contacts
You can set up profile questionnaires that you want to use when entering information about your contacts' profiles. Within each questionnaire, you can set up the different questions you intend to ask your contacts.  

You can also run the questionnaire to answer some of the questions based on contact, customer, or vendor data automatically.  

## To add a profile questionnaire
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Questionnaire Setup**, and then choose the related link.  
2.  Choose the **New** Action.  
3.  Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## To add questions to a profile questionnaire
1.  Choose the relevant profile questionnaire, and then choose the **Edit Questionnaire Setup** action.  
2.  On the first empty line, in the **Type** field, choose **Question** and type your question in the **Description** field. Fill in the other fields on this line.  
3.  On the next empty line, in the **Type** field, choose **Answer** and type your answer in the **Description** field.  
4.  In the **Priority** field, select the priority. In the **From Value** and **To Value** fields, define a point range. Contacts that receive points within the defined range will get the answer.  

Repeat these steps to enter all the questions and answers within the profile questionnaire.

After you have created a questionnaire, you must create contact ratings to classify your contacts. You can also set up questions that are rated automatically based on information in the contact card.  

> [!NOTE]
> If you enter a question that is automatically answered, choose <STRONG>Line</STRONG>, and then choose <STRONG>Question Details</STRONG>, to enter the criteria to automatically answer the question.

## The Automatic Classification of Contacts
You can automatically classify your contacts according to customer, vendor, and contact information, by setting up automatically answered profile questions on the **Profile Questionnaire Setup** page.  

> [!NOTE]
> Only contacts that are recorded as customers can be assigned a classification based on customer data and only contacts that are recorded as vendors can be assigned a classification based on vendor data. The automatic classification is not updated automatically. Consequently, you may want to update the profile questionnaires, after you have updated the customer, vendor or contact data they are based on.  

After you have set up automatically answered profile questions, if you assign the profile questionnaire containing these questions to a contact, [!INCLUDE[d365fin](includes/d365fin_md.md)] will automatically assign the right answers for the contact.  

## Example
You can classify your contacts according to how much they bought from you:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Answer</strong></th>
<th><strong>Applies to</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A</p></td>
<td><p>contacts who bought for 500,000 LCY or more</p></td>
</tr>
<tr class="even">
<td><p>B</p></td>
<td><p>contacts who bought for 100,000 up to 499,999 LCY</p></td>
</tr>
<tr class="odd">
<td><p>C</p></td>
<td><p>contacts who bought for 99,999 LCY or less</p></td>
</tr>
</tbody>
</table>

To do this, fill on the **Profile Questionnaire Setup** page as follows:


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Type</strong></th>
<th><strong>Description</strong></th>
<th><strong>Automatic Classification</strong></th>
<th><strong>From Value</strong></th>
<th><strong>To Value</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Question</p></td>
<td><p>ABC Classification</p></td>
<td><p>Click to insert a check mark</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Answer</p></td>
<td><p>A</p></td>
<td><p> </p></td>
<td><p>500,000</p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Answer</p></td>
<td><p>B</p></td>
<td><p> </p></td>
<td><p>100,000</p></td>
<td><p>499,999</p></td>
</tr>
<tr class="even">
<td><p>Answer</p></td>
<td><p>C</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>99,999</p></td>
</tr>
</tbody>
</table>

Then fill on the **Profile Question Details** page as follows:
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Field</strong></th>
<th><strong>Value</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Customer Classification Field</strong></td>
<td><emphasis>Sales (LCY)</emphasis></td>
</tr>
<tr>
<td><strong>Classification Method</strong></td>
<td><emphasis>Defined Value</emphasis></td>
</tr>
</tbody>
</table>

When you assign the profile questionnaire containing this question to a contact, application automatically enters the relevant answer for this contact on the profile lines of the contact card.

## See Also
[Creating Contacts](marketing-create-contact-companies.md)  
