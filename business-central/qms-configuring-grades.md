---
title: Configure quality inspection results
description: Learn how to configure and manage quality inspection results, including result setup, priority rules, and business process integration.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 03/05/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Configure quality inspection results

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

This article explains how to configure and use quality inspection results in quality management.

Quality inspection results represent the possible outcomes of quality inspections. Examples of typical results are Incomplete, Fail, and Pass. However, you can configure as many results as you want, and in what circumstances.  If you're unsure what to configure, use the three defaults. To learn more about the defaults, go to [Result concepts](#result-concepts). 

## Result concepts

The following are the default results for quality inspections:

| Result Code | Description | Evaluation Sequence | Allow Finish      | 
| ---------- | ----------- | -------- | ------------------ |
| INPROGRESS | In Progress | 0        | Do Not Allow Finish | 
| FAIL       | Fail        | 1        | Allow Finish |
| PASS       | Pass        | 2        | Allow Finish | 

- **In Progress** - The inspection is incomplete or in progress.
- **Fail** - The inspection failed to meet quality criteria.  
- **Pass** -The inspection met quality criteria.

However, you can also create custom results:

- Create multiple passing results. For example, Excellent, Good, and Acceptable.
- Create multiple failing results. For example, Minor Defect, Major Defect, and Critical Failure.


## Configure quality inspection results

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Results**, and then choose the related link.
1. Choose **New** to create a new result.
1. In the **Code** field, enter a short name that indicates the state of the result. For example, Pass or Fail.
1. In the **Description** field, enter a short description of the result.
1. In the **Evaluation Sequence** field, enter a number that corresponds to the result. Results with a lower number in the **Evaluation Sequence** field are evaluated first.
6. In the **Result Visibility** field, specify whether to promote the result, which emphasizes it on various pages and reports. Promoted results are displayed inline and are editable when you configure tests. They also display prominently when you run inspection, and are featured in reports. For example, **Certificate of Analysis** report shows promoted results. You typically promote pass conditions.
1. In the **Result Category** field, specify whether the result represents something good, or bad. For inconclusive results, leave the field blank.
1. In the **Finish Allowed** field, specify whether to allow inspections to be completed if they contain the result.
1. For items with lot, serial, or package tracking, you can specify how quality inspection results affect specific document transactions. For example, you can block purchase documents while inspections are in progress and block sales documents for failed inspections. Learn more at [Lot blocking and unblocking](qms-lot-blocking-unblocking.md)
1. In the **Override Style** field, specify how to emphasize the result.


## Configure result conditions

After you configure the quality inspection results, you must define how each test evaluates those results. At the test level, you specify the conditions that determine which result is assigned when the test is executed. 

In addition, you can override these evaluation rules in the quality template. This is useful when the same test is used in multiple scenarios but should be evaluated differently depending on the template context. Overriding conditions at the template level allows you to tailor the evaluation logic without modifying the underlying test definition.

>[Important]
> You can only configure result conditions in tests and templates for results where the **Result Visibility** is set to *Prioritise*.

## Related information

[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Lot Blocking and Unblocking](qms-lot-blocking-unblocking.md)  
[Configuring Workflows](qms-quality-workflows.md)  
[Quality Management Setup and Configuration](qms-setup.md)  
[Quality Management Overview](qms-overview.md)
