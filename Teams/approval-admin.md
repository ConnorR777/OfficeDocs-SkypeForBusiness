---
title: Approvals application availability in Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
  - Microsoft Teams
search.appverid: MET150
description: Learn about the Approvals application availability in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection: 
  - M365-collaboration
appliesto: 
  - Microsoft Teams
---

# Teams Approvals app availability

The Approvals app is available as a personal app for all Microsoft Teams users.
The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.

 ![shows the approvals app](media/approvals-selection.png)

Users can pin the Approvals app to save it to the menu bar.

 ![shows the approvals app with the pin option](media/approvalApp-pin.png)

The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment. Approvals created from the Approvals app will be stored in the default CDS environment.

This article describes the Approvals app requirements and roles.

## Required permissions and licenses

To use the Approvals app, you need permission for the following items:

- Permissions to create a Microsoft CDS database.

- An account on [flow.microsoft.com](https://flow.microsoft.com/)

- Administrator Role in the target environment.

- License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.

## Storage

The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS. It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes. Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).

Learn more about the [Approval workflow](/power-automate/modern-approvals).

Approvals that are created from a template are still stored in CDS such as their title, details, template ID, and more. Responses that are submited on the approval request are stored in Forms. Learn more about [Data storage for Microsoft Forms](https://support.microsoft.com/en-us/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe.).

> [!Note]
> If you delete the Form template on the Microsoft Forms site it will also delete it for your Approval template and users will not be able to start the request. Users will get an error "CDB TableNotFound" when trying to open a Approval template that has been deleted on Microsoft Forms.  

## Approvals Teams app permissions

The Approvals Teams app lets you access the following features:

- Receive messages and data that you provide to it.

- Send you messages and notifications.

- Render personal apps and dialogs without a Teams-provided header.

- Access your profile information such as your name, email address, company name, and preferred language.

- Receive messages and data that team members provide to it in a channel.

- Send messages and notifications in a channel.

- Access your team's information:
  - team name
  - channel list
  - roster (team member's names and email addresses).

- Use the team's information to contact them.

Approval Template Permissions:

- All team owners have the ability to create an approval template for their specific teams that they are an owner of. 

- For Admins creating templates for tenant wide templates a new Teams team is created where you can manage the roster who has access to create templates within this scope. Please do not delete this as permission to create and view these templates will be lost.

## Disable the Approvals app

The Approvals app is available by default. You can disable the app in the Teams admin center.

  1. Sign in to the Teams admin center.

  2. Expand **Teams apps** and select **Manage apps**.

  3. Search for the Approvals app.

![shows the Admin center navigation with Teams Apps > Manage Apps highlighted](media/manage-approval-apps.png)

  4. Select Approvals.

  5. Select the toggle to disable the app for your organization.

![shows the details for the Approvals app](media/approvals-details.png)

## Retention policy

Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time. Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).

## Auditing

The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center. You can view the audit log.

1. Go to the Microsoft 365 Compliance Site.

2. Select the **Audit** section.

3. Search for activities under **Microsoft Teams approvals activities**.

You can search for the following activities:

- Create new approval request

- View approval request details

- Approved approval request

- Rejected approval request

- Canceled approval request

- Shared approval request

- File attached to approval request

- Reassigned approval request

- Added e-signature to approval request

For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response. Create, update, and delete operations are auditable events for Approval records. Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).

Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.

2. Select **Search & investigation**.

3. Search the Audit log and select the **Dynamics 365 activities** tab.

Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).

## Security

From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received. Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.

> [!Note]
> A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created. They won't have the ability to take action on the request if they weren't given that role when the approval was created.

## Approvals eSign integration

E-signature approvals created from the Approvals App are stored in the selected providers cloud environment. For further information regarding storage around the e-signature agreement please view their documentation around storage.

To use the Approvals app e-Signature feature, you need the following items:

- License for the specific e-Signature provider. In order to obtain a license for your organization you will need to go to the providers site.

For the Approvals e-Signature functionality, Third party signature partners will appear in the Teams Approvals app by default. You can disable specific e-Signature providers through the app settings within the Teams admin center.
	
  1. Within the Approvals app under the Manage apps section in the Teams admin center select Settings

  2. Select the toggle for the specific eSignature provider to disable it. Should a Teams admin disable a provider, end users will not see the provider when creating an approval.

E-signature Approvals created from the Approvals App are stored in the selected providers cloud. To export any data regarding eSign you will need to go to the providers site in order to do this. Please refer to their documentation around export and retention of these agreements.


