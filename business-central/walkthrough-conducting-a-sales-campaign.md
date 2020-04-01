---
    title: Walkthrough - Conducting a Sales Campaign | Microsoft Docs
    description: A campaign is any kind of activity that involves several contacts. An important part of setting up a campaign involves selecting the target audience for your campaign. For this purpose, in Business Central, you create a segment, or a group of contacts using filters.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Walkthrough: Conducting a Sales Campaign
A campaign is any kind of activity that involves several contacts. An important part of setting up a campaign involves selecting the target audience for your campaign. For this purpose, in [!INCLUDE[d365fin](includes/d365fin_md.md)], you create a segment, or a group of contacts using filters.  

 You use these features in Sales & Marketing to carefully plan your marketing activities and to manage your interactions with contacts and customers. You can create campaigns and set up segments of your contacts for mailings and other types of interactions with your contacts and prospective customers.  

 The Campaign and Segment features with their automated processes enable you to plan, organize, and keep track of your marketing activities. This will increase the chances of winning new customers and retaining existing customers.  

## About This Walkthrough  
 This walkthrough demonstrates the process for following up on a trade show and targeting potential customers (contacts) in a follow-up campaign.  

 The walkthrough introduces the campaign and segment management feature in the Sales & Marketing department. This walkthrough illustrates the following tasks:  

-   Setting up a campaign.  
-   Selecting the target audience.  
-   Mining data.  
-   Sending letters to contacts.  
-   Registering campaign responses.  

## Roles  
 This walkthrough demonstrates tasks that are performed by the following user roles:  

-   Marketing Manager or Sales Manager  
-   Marketing Staffer  

## Prerequisites  
 Before you can perform the tasks in the walkthrough, you must install the [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## Story  
 The marketing manager in the Sales department of CRONUS is responsible for planning campaigns and for executing them. He also makes decisions about which trade shows to participate in and he evaluates campaign progress.  

 The marketing staffer in the Marketing department handles producing, distributing, and placing marketing material.  

 The company has just launched a new product called the Millennium Server. The product was recently promoted at a trade show, Computer Futurus. Many customers expressed great interest in the product, and as part of a promotional effort, customers who bought Millennium Server during a campaign period were offered a special campaign price.  

 One of the marketing staffer’s tasks after the trade show is to enter all the potential customers as contacts.  

 The marketing manager sets up a campaign, creates a segment that contains all the new contacts and then mines the contact data to select the target audience for the campaign.  

 The staffer helps send out thank you letters to all the contacts who left their cards with the staff at the stand, and finally, the manager records all the responses they receive from the prospective customers.  

## Setting Up a Campaign  
 As soon as the staffer has entered the business cards received at the trade show, the marketing manager sets up a campaign card to manage the activities involved in the campaign.  

### To set up a campaign  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Campaigns**, and then choose the related link.  
2.  Choose the **New** action to create a new campaign. On the campaign card, press Enter to have a campaign number automatically inserted.  
3.  In the **Description** field, enter a description for the campaign, for example, **FUTURUS trade show**.  
4.  Choose the **Status Code** field, and select a status code from the list that opens on the **Campaign Status** page.  
5.  Fill in the **Starting Date** and **Ending Date** fields of the campaign as appropriate.  

## Selecting the Target Audience  
 The marketing manager creates a segment to select the contacts that he wants to interact with.  

### To create a segment with the relevant contacts  

1.  Choose the **Segments** action.  
2.  Choose the **New** action to create a new segment. On the segment card, press Enter to have a segment number automatically inserted.  
3.  On the **General** FastTab, in the **Description** field, enter, for example, **Visitors at the FUTURUS trade show**.  

     After entering general information about the segment, select the contacts to be included in the segment.  

     You can use a variety of criteria to select contacts, for example, you can select contact persons who work at a customer site or a prospective customer site who are responsible for purchases at their company.  

     You use filters to add contacts according to the criteria that best fit your purposes. For example, you can choose to filter by the job responsibility of the contact person or the business relation or industry of the contact company. For this walkthrough, choose the **Job Responsibility** filter to select contacts.  

4.  On the **Segment** page, choose the **Add Contacts** action to open the **Add Contacts** filter.  
5.  On the **Job Responsibility** FastTab, select the **Purchase** filter as the **Job Responsibility Code** and choose the **OK** button.  

     The **Segment** page now contains a list of contacts based on the filter you entered. On the **General** FastTab, in the **No. of Lines** field, you can see at a glance the number of contacts that meet these criteria.  

    > [!NOTE]  
    >  You can save your segmentation criteria to be reused at a later stage.

    1.  On the **Segment** page, choose the **Segment** action, and then choose the **Save Criteria** action.  
    2.  On the **Save Segment Criteria** page, enter a code for the segment. In the **Description** field, enter a description of the segment criteria.
    3.  Choose the **OK** button.  

## Mining the Data  
 The marketing manager takes a closer look at the segmented list of contacts and realizes that the list is much too big. He decides to reduce the list based on actual, prospective customers to make sure he focuses on the correct target group. This process of refining and reducing the data is also referred to as data mining.  

### To remove contacts from the segment  

1.  On the **Segment** page, choose the **Contacts** action, and then choose the **Reduce Contacts** action to open the **Remove Contacts – Reduce** page.  
2.  On the **Business Relation** FastTab, select the **PROS** filter as the **Business Relation Code**, and choose the **OK** button.  

     The **Segment** page now contains a reduced list of contacts, and in the **No. of Lines** field, you can see the number of contacts that now meet these new criteria.  

    > [!NOTE]  
    >  If you have to reverse this removal of a group of contacts, you can do this using the **Go Back** function. In other words, you can undo your last segmentation.  
    >   
    >  On the **Segment** page, choose the **Segment** action, and then choose the **Go Back** action.  
    >   
    >  The contacts that you just removed are added back to the list of contacts.  

## Linking a Segment to a Campaign  
 The marketing manager decides that the reduced list is the final list of contacts that he wants to be part of the campaign. He therefore links this segment to the campaign FUTURUS trade show.  

### To link a segment to the campaign  

1.  On the **Segment** page, on the **Campaign** FastTab, choose the **Campaign No.** field to select the campaign that you want the segment to be attached to, for example, **CP0001**.  
2.  Since this segment is the target of the campaign, select the **Campaign Target** check box.  

## Sending Letters and Email Messages to Contacts  
 The marketing staffer helps the marketing manager send out correspondence to the prospective customers, in which he thanks them for visiting the trade show.  

### To use a segment to send a letter to a contact  

1.  Open the **Segment** card for the **Visitors at the FUTURUS trade show**.  
2.  On the **Interaction** FastTab, in the **Interaction Template Code** field, select the Business Letter template, code **BUS**.  
3.  In the **Subject (Default)** field, enter the following example text: **Thank you for visiting the trade show**.  

    > [!NOTE]  
    >  This template consists of more than one attachment document, each of them written in a different language. Example languages include English and Danish.  

4.  Choose the **Language Code (Default)** field to open the **Segment Interaction Languages** page. Select a language code and then choose the **OK** button.  
5.  You can display the document in the selected language. Choose the **Attachment** action, and then choose the **Open** action.  

     To respond to the message that requests permission to start Word, choose the **Allow for this client session** option.  

     This opens the attached Word document so that you can inspect it. You can also take this opportunity to edit and modify the letter. Close Word when you are finished.  

6.  Enter the subject of the letter in the **Subject** field, in the language selected for the template.  
7.  Choose the **Log** action.
8.  Choose the **Send Attachments** check box to have the attachments printed.  

    1. Select the **Create Follow-up Segment** check box.  
    2. Choose the **OK** button to start the **Log Segment** batch job.  

9. The attachments are sent. When the process is done, choose the **OK** button for the message that states that the segment has been logged.  

     The letters are automatically printed and the segment is logged. Because the segment has been logged, it is no longer in the list of segments but is moved to the list of logged segments. To see that list, Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Logged Segments**, and then choose the related link.  

10. After the segment is logged, each letter that is sent is recorded as an interaction, which you can view in the log.  

     Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Interaction Log Entries**, and then choose the related link. There is an entry for each sent letter.  

### To send an email message to a contact  

1.  On the **Interaction** FastTab, in the **Interaction Template Code** field, select the Business Letter template, code **BUS**.  
2.  In the **Subject (Default)** field, enter the following example text: **Thank you for visiting the trade show**.  
3.  In the **Correspondence Type** field, choose **E-Mail**.  
4.  Specify language settings, as in the previous procedure.  
5.  Choose the **Log** action. The **Log Segment** page opens.  
6.  Select the **Send Attachments** check box to have the attachments sent by email.  
7.  Select the **Create Follow-up Segment** check box.  
8.  Choose the **OK** button.  

     The letters are automatically sent by email, and the segment is logged. Because the segment has been logged, it is no longer in the list of segments but is saved in the list of logged segments. To see that list, Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Logged Segments**, and then choose the related link.  

## Registering Campaign Responses  
 During the next couple of weeks, the prospective customers respond to the letter. The marketing manager wants to keep track of the responses and record these interactions.  

 For this purpose, set up a segment for the contacts who have responded to the letter.  

### To register campaign responses  

1.  On the **Segment** page, expand the **Interaction** FastTab.  
2.  Choose the **Interaction Template Code** field.  

     There is no interaction template for recording responses to campaigns. Therefore, create a new template.  

3.  On the **Interaction Templates** page, choose the **New** action.  
4.  In the **Code** field, enter **RESP**, and in the **Description** field, enter **Campaign Responses**.  
5.  Choose the **OK** button.  
6.  Select this interaction template in the **Interaction Template Code** field and confirm the message that asks if you want to update the segment lines with the same Interaction Template Code.  

     Now specify that these contacts have responded to the campaign:  
7.  On the **Campaign** FastTab, in the **Campaign No.** field, select your campaign.  
8.  Leave the **Campaign No.** field and confirm the message that asks if you want to update the segment lines with the same Interaction Template Code.  
9. Select the **Campaign Response** field and confirm the subsequent message.  

     Log the segment to make sure that the interactions are recorded.  
10. On the **Segment** page, choose the **Log** action.  
11. On the **Log Segment** page, clear the **Send Attachments** check box, and then choose the **OK** button and confirm the message that appears.  

     After the segment is logged, an entry for the campaign is automatically created to record this action on the **Campaign Entries** page.  

## See Also  
[Relationship Management](marketing-relationship-management.md)  
 [Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)  
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
