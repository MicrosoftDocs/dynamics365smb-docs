---
title: Set Up Colored Indicators on Cues for a Company or User
description: As an administrator, you can set up Cues that appear on the users' Role Centers to include an indicator that changes color based on the data values in the Cues.
author: jswymer


ms.topic: how-to
ms.devlang: al
ms.search.form: 9701, 9702
ms.date: 11/10/2026
ms.author: jswymer

ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---
# Set up colored indicators on cues for a company or user

As an administrator, you can set up Cues that appear on the users' Role Centers to include an indicator that changes color based on the data values in the Cues.  

The indicator appears as a colored bar along the top border of the Cue tile. It provides a visual signal of the status of the Cue's activity, which can indicate favorable or unfavorable conditions to prompt the user to take action. For example, if a Cue displays ongoing sales invoices, you can set up the indicator to appear green (favorable) when total number of ongoing sales invoices is below 10, and appears red (unfavorable) when the total is greater than 20.  

From the **Cue Setup** page, you set up indicators for all the Cues that are available in the company database. You can set up the indicators to apply to all users in the company or an individual user only. The indicator settings on the **Cue Setup** page act as the default indicator settings. If the **Cue Setup End User** page is made available to users, then they can personalize the indicators settings that you define on the **Cue Setup** page.  

To set up the indicator, you specify up to two threshold values that define three ranges of data values (low, middle, and high) to which you can apply a different color (or style).  

## Set up colored indicators on cues
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Cue Setup**, and then choose the related link.  

     The **Cue Setup** page appears. The page lists the indicators that are currently setup up on Cues. Indicators that apply to all users in the company have a blank **User Name** field. Indicators that apply to a specific user include the user's name in the **User Name** field.  

    > [!NOTE]  
    >  If you set up a company-wide indicator and a user modifies the indicator later on, then a separate entry for the indicator appears in list for that user.  

1. Choose **Edit List** action.
1. To set up an indicator for a Cue that is not listed on the page, choose the **New** action, and then fill in the fields as described in the following. If you want to modify an existing indicator, go to the next step.

    |  Field  |  Description  |    
    |---------|---------------|  
    |**User Name**|If you want to set up the indicator for all users, leave this field blank.<br /><br /> If you want to set up the indicator for a specific user, then set this field to the user name.|  
    |**Table ID**|Specifies the ID of the table object that contains the Cue. Use the lookup to select the table. The **Table Name** field is filled in based on your selection.|
    |**Cue ID**|Specifies the ID of the Cue that you want to set up an indicator on. Use the lookup to select the Cue. The Cue ID corresponds to the field number assigned to the Cue in the table. The **Cue Name** field is filled in based on your selection.|

1. To set up the indicator for a Cue, set the fields as described in the following table. **Threshold 2** must be greater than **Threshold 1**.

    |  Field  |  Description  |    
    |---------|---------------|  
    |**Low Range Style**|Specifies the color of the indicator when the Cue's value is below the value of the **Threshold 1** field.|
    |**Threshold 1**|Specifies the value at or above which the indicator changes to the color specified by the **Middle Range Style** field.|
    |**Middle Range Style**|Specifies the color of the indicator when the Cue's value is greater than or equal to **Threshold 1** but less than or equal to **Threshold 2**.|
    |**Threshold 2**|Specifies the value above which the indicator changes to the color specified by the **High Range Style** field.|
    |**High Range Style**|Specifies the color to use when the Cue's value is above the value of the **Threshold 2** field.|

     The following table lists the colors that correspond to the options of the **Low Range Style**, **Middle Range Style**, and **High Range Style** fields.

    |  Option  |  Color  |  
    |----------|---------|  
    |**None**|No color (same color as the Cue tile)|  
    |**Favorable**|Green|  
    |**Unfavorable**|Red|  
    |**Ambiguous**|Yellow|  
    |**Subordinate**|Gray|  

## Related information

[Customize pages for profiles](ui-personalization-manage.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
