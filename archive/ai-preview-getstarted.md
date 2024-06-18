---
title: Get started with a Business Central preview version for Copilot
description: Explains how to get a Business Central environment with the new AI capability for generating text suggestions for item/product descriptions.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 03/16/2023
ms.custom: bap-template
---

# Get started with a Business Central preview version for Copilot

<!--[!INCLUDE[ai-preview](includes/ai-preview.md)]-->

You can try AI-powered item marketing text with Copilot whether you're an existing Business Central customer or a potential customer, that is, someone who's just interested in exploring Business Central and trying out the new capability. To get started, you'll need access to a Business Central online version that supports the new capability. Complete the section below that applies to you.

## Your organization already uses Business Central

As an existing customer or partner, you'll need an admin with access to the Business Central admin center to set up an environment that runs the preview version that includes Copilot. Once the environment is up and running, users can try out the new feature.

If you're an environment admin, complete the following steps:

1. Sign in to the Business Central admin center.
2. Select **Environments** > **New**.
3. In the **Create Environment** pane, specify a name for the new environment in the **Environment Name** field.
4. Set **Environment Type** to **Sandbox** or **Production**.
5. Set **Country** to any country/region on the list, but be aware that in the preview, the AI-generated marketing text from Copilot is only in English.
6. In the **Version** box, choose a version 22 or later from the list.

   <!--
   > [!IMPORTANT]
   > You must use **22.0.54157.54311 (Preview - Copilot edition)** to experience Copilot.
   -->
7. Select **Create**.  

For more information about how to create environments, go to [Create an environment](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments#create-a-new-environment).


> [!IMPORTANT]
> If you have preview sandboxes that run on **22.0.54157.54311 (Preview - Copilot edition)**, be aware that these environments are only available until 01 May 2023. After this date, you'll need to provision a new environment or upgrade any of your other environments to version 22.0 or later to continue trying the preview of AI-powered item marketing text.

## Your organization doesn't use Business Central

If you're not a Business Central customer, sign up for a free trial to try out the new AI capabilities. Signing up for the trial is simple. You'll be guided through a few steps where you'll have to provide some information, like your email address, telephone number, and name. To get the trial, complete the following steps:

1. Go to [this trial site](https://go.microsoft.com/fwlink/?linkid=2227167) to get started with the sign-up process.
2. Follow the instructions on the screen.

   You're asked to provide information like your email address, name, and telephone number. The exact experience may vary, depending on the information you provide. <!--But here are a couple important points to be aware of as you run through the sign-up process:--> For your email address, use your work or school email address. We'll establish your trial on your organization's account. You can't use email addresses provided by consumer email services or telecommunication providers, such as outlook.com, hotmail.com, gmail.com, and others.
   
   <!-- When you get to the option for **Country or region** be sure to set this **United States**.

      > [!IMPORTANT]
      > You must set **Country or region** to **United States**; otherwise the AI-powered item marketing text with Copilot won't be available in Business Central.  -->
3. When you get to the **Confirmation Details** step, you're ready to start the trial.

   - To go directly to Business Central, select **Skip & go to Dynamics 365 Business Central** > **Get started**.
   - You also have the option to invite others in your organization to the free trial as well. Just enter, the email addresses of each person, then select **Send invitations**. Select **Get started** to go to Business Central.  

   You'll be redirected to your trial at [https://businesscentral.dynamics.com/](https://businesscentral.dynamics.com/). It can take several minutes to get the trial ready the first time you sign in.

<!--
1. On the **Let's get you started** step, enter your work or school email address, then select **Next**.

   Use your work or school email address. We'll establish your trial on your organization's account. You can't use email addresses provided by consumer email services or telecommunication providers, such as outlook.com, hotmail.com, gmail.com, and others.
3. When asked what kind of email you have, select **I got it from my organization** > **Next**.
4. On the **Create your account** step, you provide information that will help use set up a trial version of Business Central that you can sign in to.

   1. Provide a telephone number that we can use to send you a verification code. Enter a country code and number that isn't VoIP or toll free.
   2. Choose how you want us to send the verification code:
      - Select **Text me** to get the verification code in a text message.
      - Select **Call me** to get the code in a voice message.
   3. Select **Send verification code**. 
   4. When you get the code, type it in the **Enter your verification code** box, then select **Verify**.

      Once you're verified, we'll send you an email with another verification code that you'll use in the next step to complete creating your account.
   5. Fill in your first and last name.
   6. Set **Country or region** to **United States**.

      > [!IMPORTANT]
      > You must set **Country or region** to **United States**; otherwise the AI-powered item marketing text with Copilot won't be available in Business Central.  

   7. Enter a valid phone umber in the **Business telephone number** box.
   8. In the **Create password** and **Confirm password** boxes, enter a password that you want to use to sign in to Business Central. The password must at least eight characters and include at least one number, an uppercase letter, and a lower case letter.
   9. In the **Verification code** box, enter the verification code we sent you in an email, then select **Next**.
   10. When you get a prompt that your account is successfully created, select **Sign in**.
-->

4. Once you're signed in, you'll see the Business Central home page, called the role center, which looks similar to the following figure:

   [![Shows the Business Central role center and the checklist for Copilot](media/copilot-checklist.png)](media/copilot-checklist.png#lightbox)

5. To get a guided introduction to creating AI-powered item marketing text with Copilot, under **Your Checklist** near the top of the page, select **Create with Copilot** > **Start tour**. Then follow the on-screen instructions.

   > [!TIP]
   > If you don't see **Your Checklist**, select the **Show demo tours** button first.

## Next steps

The AI capabilities provided by Copilot must be enabled before you or anyone else can use Copilot. To enable the AI capabilities, an administrator must consent to the terms and conditions of the [preview](https://go.microsoft.com/fwlink/?linkid=2189520) and [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839) on behalf of the organization.

> [!NOTE]
> If you're using a trial, you're the administrator. If you've invited other people in your organization to the trial during sign-up, they won't be able to use Copilot until you agree to the terms and conditions.

There are two ways to consent as an admin:

- The easiest way is to use Copilot. The first time you use Copilot as an admin, you're prompted to review the terms and conditions, then agree or disagree. To learn how to use Copilot, go to [Add marketing text to items](item-marketing-text.md).  

- The other way is to use the **Privacy Notices Status** page in Business Central and agree to the **Azure OpenAI** integration for all users. To learn more, go to [Consent to terms and conditions](enable-ai.md#consent-to-or-reject-preview-and-privacy-terms-and-conditions-for-all-users).

## See also

[Overview of AI-powered item marketing text with Copilot](ai-overview.md)  
[Configure AI-powered item marketing text with Copilot as an admin](enable-ai.md)  
[Create marketing text to items using Copilot](item-marketing-text.md)  
[FAQ for marketing text suggestions](faqs-marketing-text.md)  