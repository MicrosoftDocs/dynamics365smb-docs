---
title: Customize Visual Signals About a Cue's Activity | Microsoft Docs
description: Set up a colored indicator on a Cue tile to provide a personalized visual signal of the Cue’s activity.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: personalize, customize
ms.date: 03/29/2017
ms.author: solsen

---
# Set Up a Colored Indicator on Cues
You can set up Cues that appear on the **Home** page to include an indicator that changes color based on the data values in the Cues.

The indicator appears as a colored bar along the top border of the Cue tile. It provides a visual signal of the status of the Cue's activity, which can indicate favorable or unfavorable conditions to prompt the user to take action. For example, if a Cue displays ongoing sales invoices, you can set up the indicator to appear green (favorable) when total number of ongoing sales invoices is below 10, and appears red (unfavorable) when the total is greater than 20.

From the **Cue Setup** window, you set up indicators for all the Cues that are available in the company database.

To set up the indicator, you specify up to two threshold values that define three ranges of data values (low, middle, and high) to which you can apply a different color (or style).

## To set up colored indicators on Cues
1. Under **Activities** on your **Home** page, choose **Set Up Cues**.  
   The **Cue Setup** window appears. The window lists the indicators that are currently setup up on Cues.
2. To modify an indicator, edit the fields and modify, for example, the values for the different thresholds.  

The following table lists the colors that correspond to the options of the **Low Range Style**, **Middle Range Style**, and **High Range Style** fields.

| Option | Color |
| --- | --- |
| **None** |No color (same color as the Cue tile)|
| **Favorable** |Green |
| **Unfavorable** |Red |
| **Ambiguous** |Yellow |
| **Subordinate** |Gray |

## See Also
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
