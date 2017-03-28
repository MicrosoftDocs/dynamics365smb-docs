## Microsoft Open Source Code of Conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

# dynamics365smb-docs-pr
Welcome to the repository for user assistance content for Dynamics 365 for Financials! Financials is aimed at small and midsized businesses, and the repo is private while we work on pre-release content.
If you have any questions, please contact us through the navua alias.

======================================
Getting started with Open Publishing

Quick Start
-----------

Start contributing to Open Publishing docs using the following steps:

1. Clone the repo:
   ```
   git clone https://github.com/Microsoft/dynamics365smb-docs-pr.git
   ```

2. Edit the Markdown files using your favorite Markdown editor.
3. Commit and push your changes:
   ```
   git add -u
   git commit -m "update doc"
   git push
   ```

4. Wait for a moment and your changes will be automatically published to staging.
> If you don't have the permission to push to this repo, fork it to your own account and use pull request to submit your changes back.

Validation and Preview
----------------------

You can build and preview your content in local to discover and fix problems early, before pushing your changes to the GitHub repo:

1. To validate your changes, just run `.\.openpublishing.build.ps1` under the root of the repo.
2. To preview your changes:
   * Run `.\.openpublishing.build.ps1 -parameters:targets=serve` under the root of the repo.
   * Open `http://localhost:8080` in your browser.


Best Practices
----------------------

### Properties and tags
All topics must start with a YAML header with the following set of attributes.

For Financials:

```
---
title: "How to: Change the Role Center"
author: MyGitHubAccount
ms.author: MyDomainAccount
ms.custom: na
ms.date: MM/DD/YYYY
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-service: "project-madeira"
---
```

The author attribute is used for the GitHub association, while the ms.author attribute is used in OPS and SkyEye. Remember to specify your own accounts...

The ms.date tag must be updated according to this schedule:  
- Topic created
    - Set ms.date to the date when the topic will be published the first time (typically the 12th of the subsequent month)  
- Topic updated with bug fix or user feedback
    - Set ms.date to the current date
- Topic revised due to feature development
    - Set ms.date to the date when the topic will be published the next time (typically the 12th of the subsequent month)

Some articles will have a different value for the ms.topic tag. For more information, see https://opsdocs.azurewebsites.net/en-us/opsdocs/partnerdocs/metadata?branch=master.

### Headings
Use ```#``` for headings.

Examples:
```#``` Heading 1, looks like:
# Heading 1

```##``` Heading 2, looks like:
## Heading 2

```###``` Heading 3, looks like:
### Heading 3


### Bulleted lists
Use - to create bullets, for example:

The following options are available:
```
- first option
- second option
- third option
```

### Ordered lists
Use numbers for ordered lists. No space between the lines, we'll let the template take care of that.

```
1. In the **Search** box, enter **Payment Journal**, and then choose the related link.
2. In the **Payment Journal** window, on the first journal line, enter the relevant information about the payment entry.
3. To apply a single vendor ledger entry:
4. In the **Applies-to Doc. No.** field, choose the field to open the **Apply Vendor Entries** window.
```

### Bold and italics syntax
Use ```**bold**``` and ```*italics*```

### Tables
- For tables in the body, use the markdown syntax.

```
| To   | See                       |
|------|---------------------------|
|<text>|<link>|
| | |
| | |
```

- For nested tables in ordered and unordered lists use HTML-syntax. Markdown does not support tables very well. If you use the markdown syntax the list will be broken, the table will align left and list will be renumbered.

### Comment syntax
Useful for sections that are not ready and will not pass the build check.
```
<!-- Comments -->
```
Examples
```
<!-- [Managing Payables](payables-manage-payables.md)-->
<!-- This is a paragraph that spans more lines and I can just put the comment tag
at the beginning and end of it -->
```
### Links
Ordinary link to a different topic in the same folder

These links have the format ```[link text](filename.md)```.

Example:
```[Managing Payables](payables-manage-payables.md)```


### Link to a topic in a subfolder of the source topic

These links have the format ```[link text](subfolder/filename.md)```.

For example, you want to link to payables-manage-payables.md from ui-work-general-journals.md, where the folder structure is as follows:

- articles
    - ui-work-general-journals.md
- ManagePayables
    - conManagePayables.md

Here is the link:
```[Manage Payables](ManagePayables/payables-manage-payables.md)```

### Link to a topic in a different folder than source topic

These links have the format ```[link text](../folder/filename.md)```.

For example, you want to link to payables-manage-payables.md from receivables-manage-receivables.md, where the folder structure is as follows:

- articles
    - ManageReceivables
        - receivables-manage-receivables.md
    - ui-work-general-journals.md
    - ManagePayables
        - payables-manage-payables.md

Here is the link:
```[Manage Payables](../ManagePayables/payables-manage-payables.md)```

### Link to a place in the same article
From within an article, you can create a link to a specific heading in the same article. You can create the link like other links except with the following format:

```[link text](#target-heading)```

target-heading is the text of the heading that you want to link to, except it is all lowercase and spaces between words are replaced with hyphens. For example, here is the link:
```[How Autoscaling Works](#how-autoscaling-works)```

To the heading:
```## How Autoscaling Works```

### Link to a place in a different article
From an article, you can create a link to a specific heading in another article. You can create the link like other links except with the following format:

```[link text](targetarticlename#target-heading)```

targetarticlename is the file name of the article, including the .md file type.
target-heading is the text of the heading that you want to link to, except it is all lowercase and spaces between words are replaced with hyphens.

For example, to link to the heading "How Autoscaling Works" in the article Autoscaling.md", add the following code:
```[link text](Autoscaling.md#how-autoscaling-works)```

### Link to MSDN
Omit the brackets with the NAV version info. Markdown mistakes that bracket for its own link indication.
Example:  
MSDN URL: ```https://msdn.microsoft.com/en-us/library/hh173988(v=nav.80).aspx```  
Entered in markdown: ```https://msdn.microsoft.com/en-us/library/hh173988.aspx```

### Line breaks (soft return)
In the editor, add two blank spaces at the end of the sentence and hit return. This is used in the See Also list. (See Also must be heading 2.)

### Continue steps after a non-step para
Enter four spaces in front of the non-step para. Otherwise, the non-step para will restart the step sequence.

### TOC
The TOC structure of the TOC file is as follows:

```
#[Overview](overview.md)
 ##[Topic 1](topic-1.md)
 ##[Topic 2](topic-2.md)
 ##[Topic 3](topic-3.md)
 ##[Topic 4](topic-4.md)
```

### Standard Phrases
All fields in Dynamics NAV have tooltips. Therefore, do not document fields in Help. To refer readers to the tooltips, use this standard phrase where relevant:    
"Choose a field to read a short description of the field or link to more information."

### File naming

#### Rules
- No spaces or punctuation characters. Use hyphens to separate the words in the file name.
- Use all lowercase letters
- No more than 80 characters - this is a publishing system limit
- Use action verbs that are specific such as develop, buy, build, troubleshoot. No -ing words.
- No small words - don't include a, and, the, in, or, etc.
- Country-specific article file names are prefixed with the country code. Example: "ca-" for Canada.
- All files must be in markdown and use the .md file extension.

#### Examples

|Topic title |Naming  |
|------------|--------|
|How to: Select a Company|ui-how-select-company.md|
|Enter Criteria in Filters|ui-enter-criteria-filters.md|
|Troubleshooting: Record Locked by Another User|ui-troubleshoot-record-locked-another-user.md|
|Changing Role Center|ui-change-role-center.md|
|||
|Set Up Currencies|finance-setup-currencies.md|
|How to: Set Up Purchasers|purchases-how-setup-purchasers.md|
|Understanding Session Timeouts|admin-understand-session-timeouts.md|
|Manage Data Encryption|admin-manage-data-encryption.md|
|||
|How to: Work With GIFI Codes in Canada|ca-finance-work-GiFI-codes.md|

Naming consists of the following elements: ```<country prefix>-<category prefix>-<topic title>.<extension>```

### Country-specific content
To simplify content localization and translation, country-specific articles live in the same folder ```/articles``` as the articles for the generic product. We distinguish country-specific article file names by a country prefix.

To give readers the impression that the content library is truly country-specific, while maintaining the simple file structure, we integrate country-specific articles in a subtle way by following these guidelines:

- Prefix article file names with the country code. Example: ```ca-``` for Canada.
- End article titles with ```in <country>```. Example: "How to: Work With GIFI Codes in Canada".
- Link to country-specific content from generic content whenever relevant. The more you link to and from country-specific content, the more integrated it will feel. As for all other links, the link name must be the same as the title of the target article.
- In navigation tables; the To/See tables in top-level topics, create rows for country-specific references at the bottom of the table. Prefix the text in the **To** column with ```<country>:``` Example: "Canada: How to: Work With GIFI Codes in Canada".
- Do not create TOC entries for country-specific content. TOC entries will make the content library appear less country-specific.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
