---
title: 'Tutorial: Configure BlueJeans for automatic user provisioning with Azure Active Directory | Microsoft Docs'
description: Learn how to configure Azure Active Directory to automatically provision and de-provision user accounts to BlueJeans.
services: active-directory
author: zhchia
writer: zhchia
manager: CelesteDG
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 03/27/2019
ms.author: jeedes
---

# Tutorial: Configure BlueJeans for automatic user provisioning

The objective of this tutorial is to demonstrate the steps to be performed in BlueJeans and Azure Active Directory (Azure AD) to configure Azure AD to automatically provision and de-provision users and/or groups to BlueJeans.

> [!NOTE]
> This tutorial describes a connector built on top of the Azure AD User Provisioning Service. For important details on what this service does, how it works, and frequently asked questions, see [Automate user provisioning and deprovisioning to SaaS applications with Azure Active Directory](../app-provisioning/user-provisioning.md).

## Prerequisites

The scenario outlined in this tutorial assumes that you already have the following:

* An Azure AD tenant
* A BlueJeans tenant with the [My Company](https://www.BlueJeans.com/pricing) plan or better enabled
* A user account in BlueJeans with Admin permissions

> [!NOTE]
> The Azure AD provisioning integration relies on the [BlueJeans API](https://BlueJeans.github.io/developer), which is available to BlueJeans teams on the Standard plan or better.

## Adding BlueJeans from the gallery

Before configuring BlueJeans for automatic user provisioning with Azure AD, you need to add BlueJeans from the Azure AD application gallery to your list of managed SaaS applications.

**To add BlueJeans from the Azure AD application gallery, perform the following steps:**

1. In the **[Azure portal](https://portal.azure.com)**, in the left navigation panel, select **Azure Active Directory**.

	![The Azure Active Directory button](common/select-azuread.png)

2. Go to **Enterprise applications**, and then select **All applications**.

	![The Enterprise applications blade](common/enterprise-applications.png)

3. To add a new application, select the **New application** button at the top of the pane.

	![The New application button](common/add-new-app.png)

4. In the search box, enter **BlueJeans**, select **BlueJeans** in the results panel, and then select the **Add** button to add the application.

	![BlueJeans in the results list](common/search-new-app.png)

## Assigning users to BlueJeans

Azure Active Directory uses a concept called "assignments" to determine which users should receive access to selected apps. In the context of automatic user provisioning, only the users and/or groups that have been "assigned" to an application in Azure AD are synchronized.

Before configuring and enabling automatic user provisioning, you should decide which users and/or groups in Azure AD need access to BlueJeans. Once decided, you can assign these users and/or groups to BlueJeans by following the instructions here:

* [Assign a user or group to an enterprise app](../manage-apps/assign-user-or-group-access-portal.md)

### Important tips for assigning users to BlueJeans

* It is recommended that a single Azure AD user is assigned to BlueJeans to test the automatic user provisioning configuration. Additional users and/or groups may be assigned later.

* When assigning a user to BlueJeans, you must select any valid application-specific role (if available) in the assignment dialog. Users with the **Default Access** role are excluded from provisioning.

## Configuring automatic user provisioning to BlueJeans

This section guides you through the steps to configure the Azure AD provisioning service to create, update, and disable users and/or groups in BlueJeans based on user and/or group assignments in Azure AD.

> [!TIP]
> You may also choose to enable SAML-based single sign-on for BlueJeans, following the instructions provided in the [BlueJeans single sign-on tutorial](bluejeans-tutorial.md). Single sign-on can be configured independently of automatic user provisioning, though these two features compliment each other.

### To configure automatic user provisioning for BlueJeans in Azure AD:

1. Sign in to the [Azure portal](https://portal.azure.com) and select **Enterprise Applications**, select **All applications**, then select **BlueJeans**.

	![Enterprise applications blade](common/enterprise-applications.png)

2. In the applications list, select **BlueJeans**.

	![The BlueJeans link in the Applications list](common/all-applications.png)

3. Select the **Provisioning** tab.

	![Provisioning tab](common/provisioning.png)

4. Set the **Provisioning Mode** to **Automatic**.

	![Provisioning tab automatic](common/provisioning-automatic.png)

5. Under the **Admin Credentials** section, input your BlueJeans Tenant URL and Secret Token. Click **Test Connection** to ensure Azure AD can connect to BlueJeans. If the connection fails, ensure your BlueJeans account has Admin permissions and try again.

 	![Token](common/provisioning-testconnection-tenanturltoken.png)


6. In the **Notification Email** field, enter the email address of a person or group who should receive the provisioning error notifications and check the checkbox - **Send an email notification when a failure occurs**.

	![Notification Email](common/provisioning-notification-email.png)

7. Click **Save**.

8. Under the **Mappings** section, select **Synchronize Azure Active Directory Users to BlueJeans**.

9. Review the user attributes that are synchronized from Azure AD to BlueJeans in the **Attribute Mapping** section. The attributes selected as **Matching** properties are used to match the user accounts in BlueJeans for update operations. Select the **Save** button to commit any changes.

|Attribute|Type|Supported for filtering|
|---|---|---|
|userName|String|&check;|
|active|Boolean|
|title|String|
|emails[type eq "work"].value|String|
|name.givenName|String|
|name.familyName|String|
|phoneNumbers[type eq "work"].value|String|
|urn:ietf:params:scim:schemas:extension:enterprise:2.0:User:manager|String|

10. To configure scoping filters, refer to the following instructions provided in the [Scoping filter tutorial](../app-provisioning/define-conditional-rules-for-provisioning-user-accounts.md).

11. To enable the Azure AD provisioning service for BlueJeans, change the **Provisioning Status** to **On** in the **Settings** section.

	![Provisioning Status Toggled On](common/provisioning-toggle-on.png)

12. Define the users and/or groups that you would like to provision to BlueJeans by choosing the desired values in **Scope** in the **Settings** section.

	![Provisioning Scope](common/provisioning-scope.png)

13. When you are ready to provision, click **Save**.

	![Saving Provisioning Configuration](common/provisioning-configuration-save.png)

This operation starts the initial synchronization of all users and/or groups defined in **Scope** in the **Settings** section. The initial sync takes longer to perform than subsequent syncs, which occur approximately every 40 minutes as long as the Azure AD provisioning service is running. You can use the **Synchronization Details** section to monitor progress and follow links to provisioning activity report, which describes all actions performed by the Azure AD provisioning service on BlueJeans.

For more information on how to read the Azure AD provisioning logs, see [Reporting on automatic user account provisioning](../app-provisioning/check-status-user-account-provisioning.md).

## Connector Limitations

* Bluejeans does not allow userNames that exceed 30 characters.

## Additional resources

* [Managing user account provisioning for Enterprise Apps](../app-provisioning/configure-automatic-user-provisioning-portal.md)
* [What is application access and single sign-on with Azure Active Directory?](../manage-apps/what-is-single-sign-on.md)

## Next steps

* [Learn how to review logs and get reports on provisioning activity](../app-provisioning/check-status-user-account-provisioning.md)

<!--Image references-->

[1]: ./media/bluejeans-provisioning-tutorial/tutorial_general_01.png
[2]: ./media/bluejeans-tutorial/tutorial_general_02.png
[3]: ./media/bluejeans-tutorial/tutorial_general_03.png
