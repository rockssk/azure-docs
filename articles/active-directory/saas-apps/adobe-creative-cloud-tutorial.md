---
title: 'Tutorial: Azure Active Directory single sign-on (SSO) integration with Adobe Creative Cloud | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and Adobe Creative Cloud.
services: active-directory
documentationCenter: na
author: jeevansd
manager: mtillman
ms.reviewer: barbkess

ms.assetid: c199073f-02ce-45c2-b515-8285d4bbbca2
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: tutorial
ms.date: 10/21/2019
ms.author: jeedes

ms.collection: M365-identity-device-management
---

# Tutorial: Azure Active Directory single sign-on (SSO) integration with Adobe Creative Cloud

In this tutorial, you'll learn how to integrate Adobe Creative Cloud with Azure Active Directory (Azure AD). When you integrate Adobe Creative Cloud with Azure AD, you can:

* Control in Azure AD who has access to Adobe Creative Cloud.
* Enable your users to be automatically signed-in to Adobe Creative Cloud with their Azure AD accounts.
* Manage your accounts in one central location - the Azure portal.

To learn more about SaaS app integration with Azure AD, see [What is application access and single sign-on with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis).

## Prerequisites

To get started, you need the following items:

* An Azure AD subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* Adobe Creative Cloud single sign-on (SSO) enabled subscription.

## Scenario description

In this tutorial, you configure and test Azure AD SSO in a test environment.

* Adobe Creative Cloud supports **SP** initiated SSO





## Adding Adobe Creative Cloud from the gallery

To configure the integration of Adobe Creative Cloud into Azure AD, you need to add Adobe Creative Cloud from the gallery to your list of managed SaaS apps.

1. Sign in to the [Azure portal](https://portal.azure.com) using either a work or school account, or a personal Microsoft account.
1. On the left navigation pane, select the **Azure Active Directory** service.
1. Navigate to **Enterprise Applications** and then select **All Applications**.
1. To add new application, select **New application**.
1. In the **Add from the gallery** section, type **Adobe Creative Cloud** in the search box.
1. Select **Adobe Creative Cloud** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.


## Configure and test Azure AD single sign-on for Adobe Creative Cloud

Configure and test Azure AD SSO with Adobe Creative Cloud using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between an Azure AD user and the related user in Adobe Creative Cloud.

To configure and test Azure AD SSO with Adobe Creative Cloud, complete the following building blocks:

1. **[Configure Azure AD SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with B.Simon.
    1. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable B.Simon to use Azure AD single sign-on.
1. **[Configure Adobe Creative Cloud SSO](#configure-adobe-creative-cloud-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Adobe Creative Cloud test user](#create-adobe-creative-cloud-test-user)** - to have a counterpart of B.Simon in Adobe Creative Cloud that is linked to the Azure AD representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Azure AD SSO

Follow these steps to enable Azure AD SSO in the Azure portal.

1. In the [Azure portal](https://portal.azure.com/), on the **Adobe Creative Cloud** application integration page, find the **Manage** section and select **single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, click the edit/pen icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, enter the values for the following fields:

	a. In the **Sign on URL** text box, type a URL:
    `https://adobe.com`

    b. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `https://www.okta.com/saml2/service-provider/<token>`

	> [!NOTE]
	> The Identifier value is not real. Update this value with the actual Identifier. Contact [Adobe Creative Cloud Client support team](https://www.adobe.com/au/creativecloud/business/teams/plans.html) to get this value. You can also refer to the patterns shown in the **Basic SAML Configuration** section in the Azure portal.

1. Adobe Creative Cloud application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/edit-attribute.png)

1. In addition to above, Adobe Creative Cloud application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirement.

	| Name | Source Attribute|
	|----- | --------- |
	| FirstName | user.givenname |
	| LastName | user.surname |
	| Email | user.mail |

	> [!NOTE]
	> Users need to have a valid Office 365 ExO license for email claim value to be populated in the SAML response.

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Certificate (Base64)** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

1. On the **Set up Adobe Creative Cloud** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

### Create an Azure AD test user

In this section, you'll create a test user in the Azure portal called B.Simon.

1. From the left pane in the Azure portal, select **Azure Active Directory**, select **Users**, and then select **All users**.
1. Select **New user** at the top of the screen.
1. In the **User** properties, follow these steps:
   1. In the **Name** field, enter `B.Simon`.  
   1. In the **User name** field, enter the username@companydomain.extension. For example, `B.Simon@contoso.com`.
   1. Select the **Show password** check box, and then write down the value that's displayed in the **Password** box.
   1. Click **Create**.

### Assign the Azure AD test user

In this section, you'll enable B.Simon to use Azure single sign-on by granting access to Adobe Creative Cloud.

1. In the Azure portal, select **Enterprise Applications**, and then select **All applications**.
1. In the applications list, select **Adobe Creative Cloud**.
1. In the app's overview page, find the **Manage** section and select **Users and groups**.

   ![The "Users and groups" link](common/users-groups-blade.png)

1. Select **Add user**, then select **Users and groups** in the **Add Assignment** dialog.

	![The Add User link](common/add-assign-user.png)

1. In the **Users and groups** dialog, select **B.Simon** from the Users list, then click the **Select** button at the bottom of the screen.
1. If you're expecting any role value in the SAML assertion, in the **Select Role** dialog, select the appropriate role for the user from the list and then click the **Select** button at the bottom of the screen.
1. In the **Add Assignment** dialog, click the **Assign** button.

## Configure Adobe Creative Cloud SSO

1. In a different web browser window, sign-in to [Adobe Admin Console](https://adminconsole.adobe.com) as an administrator.

2. Go to **Settings** on the top navigation bar and then choose **Identity**. The list of domains opens. Click **Configure** link against your domain. Then perform the following steps on **Single Sign On Configuration Required** section. For more information, see [Setup a domain](https://helpx.adobe.com/enterprise/using/set-up-domain.html)

	![Settings](https://helpx.adobe.com/content/dam/help/en/enterprise/using/configure-microsoft-azure-with-adobe-sso/_jcr_content/main-pars/procedure_719391630/proc_par/step_3/step_par/image/edit-sso-configuration.png "Settings")

	a. Click **Browse** to upload the downloaded certificate from Azure AD to **IDP Certificate**.

	b. In the **IDP issuer** textbox, paste the value of **Azure AD Identifier** which you copied from Azure portal.

	c. In the **IDP Login URL** textbox, paste the value of **Login URL** which you copied from Azure portal.

	d. Select **HTTP - Redirect** as **IDP Binding**.

	e. Select **Email Address** as **User Login Setting**.

	f. Click **Save** button.

3. The dashboard will now present the XML **"Download Metadata"** file. It contains Adobe’s EntityDescriptor URL and AssertionConsumerService URL. Please open the file and configure them in the Azure AD application.

	![Configure Single Sign-On On App Side](./media/adobe-creative-cloud-tutorial/tutorial_adobe-creative-cloud_003.png)

	a. Use the EntityDescriptor value Adobe provided you for **Identifier** on the **Configure App Settings** dialog.

	b. Use the AssertionConsumerService value Adobe provided you for **Reply URL** on the **Configure App Settings** dialog.

### Create Adobe Creative Cloud test user

In order to enable Azure AD users to sign into Adobe Creative Cloud, they must be provisioned into Adobe Creative Cloud. In the case of Adobe Creative Cloud, provisioning is a manual task.

### To provision a user accounts, perform the following steps:

1. Sign in to [Adobe Admin Console](https://adminconsole.adobe.com) site as an administrator.

2. Add the user within Adobe’s console as Federated ID and assign them to a Product Profile. For detailed information on adding users, see [Add users in Adobe Admin Console](https://helpx.adobe.com/enterprise/using/users.html#Addusers) 

3. At this point, type your email address/upn into the Adobe sign in form, press tab, and you should be federated back to Azure AD:
   * Web access: www\.adobe.com > sign-in
   * Within the desktop app utility > sign-in
   * Within the application > help > sign-in

## Test SSO 

In this section, you test your Azure AD single sign-on configuration using the Access Panel.

When you click the Adobe Creative Cloud tile in the Access Panel, you should be automatically signed in to the Adobe Creative Cloud for which you set up SSO. For more information about the Access Panel, see [Introduction to the Access Panel](https://docs.microsoft.com/azure/active-directory/active-directory-saas-access-panel-introduction).

## Additional resources

- [ List of Tutorials on How to Integrate SaaS Apps with Azure Active Directory ](https://docs.microsoft.com/azure/active-directory/active-directory-saas-tutorial-list)

- [What is application access and single sign-on with Azure Active Directory? ](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)

- [What is conditional access in Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)

- [Try Adobe Creative Cloud with Azure AD](https://aad.portal.azure.com/)

- [Set up a domain (adobe.com)](https://helpx.adobe.com/enterprise/using/set-up-domain.html)
  
- [Configure Azure for use with Adobe SSO (adobe.com)](https://helpx.adobe.com/enterprise/kb/configure-microsoft-azure-with-adobe-sso.html)

