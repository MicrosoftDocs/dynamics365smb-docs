---
title: "Walkthrough: Conduct a Sales Campaign"
description: Follow a sales campaign in Business Central, from selecting contacts and saving segment criteria to sending correspondence and recording campaign responses.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.date: 10/22/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Walkthrough: Conduct a sales campaign

A campaign is any kind of activity that involves several contacts. An important part of setting up a campaign involves selecting the target audience for your campaign. For this purpose, in [!INCLUDE[prod_short](includes/prod_short.md)], you create a segment, or a group of contacts using filters.  

 You use these features in Sales & Marketing to carefully plan your marketing activities and to manage your interactions with contacts and customers. You can create campaigns and set up segments of your contacts for mailings and other types of interactions with your contacts and prospective customers.  

 The Campaign and Segment features with their automated processes enable you to plan, organize, and keep track of your marketing activities. This increases the chances of winning new customers and retaining existing customers.  

## About this walkthrough

 This walkthrough demonstrates the process for following up on a trade show and targeting potential customers (contacts) in a follow-up campaign.  

 The walkthrough introduces the campaign and segment management feature in the Sales & Marketing department. This walkthrough illustrates the following tasks:  

- Preparing the data.
- Setting up a campaign.  
- Selecting the target audience.  
- Mining data.  
- Sending letters to contacts.  
- Registering campaign responses.  

## Roles in the walkthrough

 This walkthrough demonstrates tasks that are performed by the following user roles:  

- Marketing Manager or Sales Manager  
- Marketing Staffer  

## Prepare the demonstration company

Use a demonstration company in [!INCLUDE[prod_short](includes/prod_short.md)]. Before you start, make sure that you have:

- Number series for campaigns and segments on the **Marketing Setup** page.
- A campaign status code such as **1-PLAN**.
- Contact persons assigned to the **PURCHASE** job responsibility, including some who belong to companies with the **CUST** business relation.
- An interaction template such as **BUS** for business letters. For the attachment-based example, use a template that doesn't have a **Word Template Code**.
- An email account set up for sending messages, and valid email addresses on the contacts you want to email.

The codes in this walkthrough are examples. Create them if they're missing, or use equivalent codes from your company.

## Campaign scenario

 The marketing manager in the Sales department of CRONUS is responsible for planning campaigns and for executing them. The marketing manager also makes decisions about which trade shows to participate in and evaluates campaign progress.  

 The marketing staffer in the Marketing department handles producing, distributing, and placing marketing material.  

 The company has launched a new product called the Rome Guest Chair. The product was recently promoted at a trade show, Office Futurus. Many customers expressed great interest in the product, and as part of a promotional effort, customers who bought Rome Guest Chair during a campaign period were offered a special campaign price.  

 One of the marketing staffer’s tasks after the trade show is to enter all the potential customers as contacts.  

 The marketing manager sets up a campaign, creates a segment that contains all the new contacts and then mines the contact data to select the target audience for the campaign.  

 The staffer helps send out thank you letters to all the contacts who left their cards with the staff at the stand, and finally, the manager records all the responses they receive from the prospective customers.  

## Set up a campaign

 As soon as the staffer has entered the business cards received at the trade show, the marketing manager sets up a campaign card to manage the activities involved in the campaign.  

### Create the campaign card

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Campaigns**, and then choose the related link.  
2. Choose the **New** action to create a new campaign. On the campaign card, select <kbd>Enter</kbd> to have a campaign number automatically inserted.  
3. In the **Description** field, enter a description for the campaign, for example, **Office Futurus trade show**.  
4. Choose the **Status Code** field, and select the status code "1-PLAN". 
5. Fill in the **Starting Date** and **Ending Date** fields of the campaign as appropriate.  

## Select the target audience

 The marketing manager creates a segment to select the contacts that they want to interact with.  
 
 When you create a segment, you can use various criteria to select the contacts that must be targets for the segment. For example, you can select contact persons who work at a customer site or a prospective customer site who are responsible for purchases at their company. You use filters to add contacts according to the criteria that best fit your purposes. For example, you can choose to filter by the job responsibility of the contact person or the business relation or industry of the contact company. For this walkthrough, we'll choose the **Job Responsibility** filter to select contacts.

### Create a segment with the relevant contacts

1. Choose the **Navigate** action, and then choose **Segments**.  
2. Choose the **New** action to create a new segment. On the segment card, select **Enter** to have a segment number automatically inserted.  
3. On the **General** FastTab, in the **Description** field, enter, for example, *Visitors at the Office Futurus trade show*.
4. Choose the **Add Contacts** action to open the **Add Contacts** filter.  
5. Scroll down to the **Contact Job Responsibility** FastTab, select the **Purchase** filter as the **Job Responsibility Code** and choose the **OK** button.  

The **Segment** page now contains a list of contacts based on the filter you entered. On the **General** FastTab, in the **No. of Lines** field, you can see at a glance the number of contacts that meet these criteria.  

> [!NOTE]  
> You can save your segmentation criteria to be reused at a later stage.

### Save your segmentation criteria

1. On the **Segment** page, choose **Actions**.
2. Choose **Functions**, then **Segment**, and then choose the **Save Criteria** action.  
3. On the **Save Segment Criteria** page, enter a code for the segment. In the **Description** field, enter a description of the segment criteria.
4. Choose the **OK** button.  

## Refine the target audience

 The marketing manager takes a closer look at the segmented list of contacts and realizes that the list is much too large. The manager decides to reduce the list based on actual, prospective customers to focus on the correct target group. This process of refining and reducing the data is also referred to as data mining.  

### Remove existing customers from the segment

1. On the **Segment** page, choose **Actions**.
1. Choose **Functions** > **Contacts** > **Reduce Contacts**. The **Remove Contacts - Reduce** page opens.
1. On the **Contact Business Relation** FastTab, select the **CUST** filter as the **Business Relation Code**, and choose the **OK** button.

 The **Segment** page now contains a reduced list of contacts, and in the **No. of Lines** field, you can see the number of contacts that now meet these new criteria.  

 > [!NOTE]  
 > If you have to reverse this removal of a group of contacts, you can do this using the **Go Back** function. In other words, you can undo your last segmentation.  

### Bring back the removed contacts

1. On the **Segment** page, choose the **Segment** action.
2. Choose the **Go Back** action.

The contacts that you removed are added back to the list of contacts.

## Link a segment to a campaign

The marketing manager decides that the reduced list is the final list of contacts that they want to be part of the campaign. They therefore link this segment to the campaign FUTURUS trade show.  

### Assign the campaign to the segment

1. On the **Segment** page, on the **Campaign** FastTab, choose the **Campaign No.** field to select the campaign that you want the segment to be attached to, for example, **CP0001**.
2. Select **Yes**.  
3. Since this segment is the target of the campaign, select the **Campaign Target** check box and choose **Yes**.  

## Send letters and email messages to contacts

 The marketing staffer helps the marketing manager send out correspondence to the prospective customers, in which they thank them for visiting the trade show.

### Prepare letters and log the segment

> [!NOTE]  
> In this procedure you have to attach a Word document. You can add attachments in any language.

> [!NOTE]  
> If needed, select **Edit** to open the page in edit mode.
>
> The **Hard Copy** correspondence type doesn't print letters from the web client. In this procedure, download and print the letters separately, then log the segment without sending attachments.

1. Open the **Segment** card for the **Visitors at the FUTURUS trade show**.  
2. On the **Interaction** FastTab, in the **Interaction Template Code** field, select the Business Letter template code **BUS** and select **Yes**.
3. Choose the **Language Code (Default)** field to open the **Segment Interaction Languages** page. Select a **Language Code** and then choose the **OK** button.
4. Leave **Correspondence Type (Default)** blank.
5. In the **Attachment** field, select the **Ellipsis** box. This opens the Import Attachment dialog.
    1. Select the **Choose** button to choose your file.
    1. Find the file and select the **Open** button to attach it.
6. In the **Subject (Default)** field, enter the following example text: **Thank you for visiting the trade show**. Select the <kbd>Tab</kbd> key to leave the field, and select the **Yes** button.
1. For each contact line, choose **Line** > **Attachment** > **Open** to prepare the letter. Download and print the letter from the program that opens it.
1. After you send the letters, choose **Log**. On the **Log Segment** page, clear **Send Attachments** and select **Create Follow-up Segment**.
1. Choose **OK**, and then acknowledge the message that the segment has been logged.

The segment is no longer in the list of open segments. To view the logged segment, [!INCLUDE[open-search](includes/open-search.md)], enter **Logged Segments**, and then choose the related link. A new follow-up segment contains the same contacts for further communication.

After the segment is logged, each letter that is sent is recorded as an interaction, which you can view in the log.  

[!INCLUDE[open-search](includes/open-search.md)], enter **Interaction Log Entries**, and then choose the related link. There's an entry for each sent letter.  

### Send an email message to the segment contacts

1. Open the follow-up segment. On the **Interaction** FastTab, in the **Interaction Template Code** field, select the Business Letter template, code **BUS**.
2. In the **Subject (Default)** field, enter the following example text: **Thank you for visiting the trade show**.  
3. In the **Correspondence Type (Default)** field, choose **Email**, and confirm that the change applies to the segment lines.
4. Specify language settings, and attach a Word document, as in the previous procedure.  
5. Choose the **Log** action. The **Log Segment** page opens.  
6. Select the **Send Attachments** check box to have the attachments sent by email.  
7. Select the **Create Follow-up Segment** check box.  
8. Choose the **OK** button.  

 The letters are automatically sent by email, and the segment is logged. Because the segment has been logged, it's no longer in the list of segments but is saved in the list of logged segments. To see that list, [!INCLUDE[open-search](includes/open-search.md)], enter **Logged Segments**, and then choose the related link.  

## Register campaign responses

 During the next couple of weeks, the prospective customers respond to the letter. The marketing manager wants to keep track of the responses and records these interactions.  

 For this purpose, set up a segment for the contacts who have responded to the letter.  

### Record the contacts who respond

1. On the **Segment** page, on the **Interaction** FastTab, choose the **Interaction Template Code** field.  

 There's no interaction template for recording responses to campaigns. Therefore, create a new template.  

2. On the **Interaction Templates** dropdown, choose the **New** action.  
3. In the **Code** field, enter **RESP**, and in the **Description** field, enter **Campaign Responses**.  
4. Choose the **OK** button.
5. Choose **Yes** to confirm that you want to apply this interaction template code to all segment lines.
6. On the **Campaign** FastTab, select the **Campaign Response** field. Choose **Yes** to confirm the message *You have modified Campaign Response*.  
7. On the **Segment** page, choose the **Log** action.  
8. On the **Log Segment** page, clear the **Send Attachments** check box. Then choose the **OK** button to confirm the message that the segment has been logged.  
  
## Related information  
[Relationship Management](marketing-relationship-management.md)  
 [Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)  
 [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
