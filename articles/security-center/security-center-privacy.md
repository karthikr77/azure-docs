---
title: Manage user data in Azure Security Center | Microsoft Docs
description: " Learn how to manage user data in Azure Security Center. "
services: security-center
documentationcenter: na
author: rkarlin
manager: MBaldwin
editor: ''

ms.assetid: 411d7bae-c9d4-4e83-be63-9f2f2312b075
ms.service: security-center
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/23/2018
ms.author: rkarlin

---

# Manage user data in Azure Security Center
This article provides information about how you can manage the user data in Azure Security Center. Managing user data includes the ability to access, delete, or export data.

[!INCLUDE [gdpr-intro-sentence.md](../../includes/gdpr-intro-sentence.md)]

A Security Center user assigned the role of Reader, Owner, Contributor, or Account Administrator can access customer data within the tool. See [Built-in roles for Azure role-based access control](../role-based-access-control/built-in-roles.md) to learn more about the Reader, Owner, and Contributor roles. See [Azure subscription administrators](../billing/billing-add-change-azure-subscription-administrator.md) to learn more about the Account Administrator role.

## Searching for and identifying personal data
A Security Center user can view their personal data through the Azure portal. Security Center only stores security contact details such as email addresses and phone numbers. See [Provide security contact details in Azure Security Center](security-center-provide-security-contact-details.md) for more information.

In the Azure portal, a user can view allowed IP configurations using Security Center's just in time VM access feature. See [Manage virtual machine access using just in time](security-center-just-in-time.md) for more information.

In the Azure portal, a user can view security alerts provided by Security Center including IP addresses and attacker details. See [Managing and responding to security alerts in Azure Security Center](security-center-managing-and-responding-alerts.md) for more information.

## Classifying personal data
You do not need to classify personal data found in Security Center's security contact feature. The data saved is an email address (or multiple email addresses) and a phone number. [Contact data](security-center-provide-security-contact-details.md) is validated by Security Center.

You do not need to classify the IP addresses and port numbers saved by Security Center's [just in time](security-center-just-in-time.md) feature.

Only a user assigned the role of Administrator can classify personal data by [viewing alerts](security-center-managing-and-responding-alerts.md) in Security Center.

## Securing and controlling access to personal data
A Security Center user assigned the role of Reader, Owner, Contributor, or Account Administrator can access [security contact data](security-center-provide-security-contact-details.md).

A Security Center user assigned the role of Reader, Owner, Contributor, or Account Administrator can access their [just in time](security-center-just-in-time.md) policies.

A Security Center user assigned the role of Reader, Owner, Contributor, or Account Administrator can view their [alerts](security-center-managing-and-responding-alerts.md).

## Updating personal data
A Security Center user assigned the role of Owner, Contributor, or Account Administrator can update [security contact data](security-center-provide-security-contact-details.md) via the Azure portal.

A Security Center user assigned the role of Owner, Contributor, or Account Administrator can update their [just in time policies](security-center-just-in-time.md).

An Account Administrator cannot edit alert incidents. An [alert incident](security-center-managing-and-responding-alerts.md) is considered security data and is read only.

## Deleting personal data
A Security Center user assigned the role of Owner, Contributor, or Account Administrator can delete [security contact data](security-center-provide-security-contact-details.md) via the Azure portal.

A Security Center user assigned the role of Owner, Contributor, or Account Administrator can delete the [just in time policies](security-center-just-in-time.md) via the Azure portal.

A Security Center user cannot delete alert incidents. Due to security needs, an [alert incident](security-center-managing-and-responding-alerts.md) is considered read only data.

## Exporting personal data
A Security Center user assigned the role of Reader, Owner, Contributor, or Account Administrator can export [security contact data](security-center-provide-security-contact-details.md) by:

- Performing a copy from the Azure portal
- Executing the Azure REST API call, GET HTTP:
```HTTP
GET https://<endpoint>/subscriptions/{subscriptionId}/providers/Microsoft.Security/securityContacts?api-version={api-version}
```

A Security Center user assigned the role of Account Administrator can export the [just in time policies](security-center-just-in-time.md) containing the IP addresses by:

- Performing a copy from the Azure portal
- Executing the Azure REST API call, GET HTTP:
```HTTP
GET https://<endpoint>/subscriptions/{subscriptionId}/resourceGroups/{resourceGroup}/providers/Microsoft.Security/locations/{location}/jitNetworkAccessPolicies/default?api-version={api-version}
```

An Account Administrator can export the alert details by:

- Performing a copy from the Azure portal
- Executing the Azure REST API call, GET HTTP:
```HTTP
GET https://<endpoint>/subscriptions/{subscriptionId}/providers/microsoft.Security/alerts?api-version={api-version}
```

See [Get Security Alerts (GET Collection)](https://msdn.microsoft.com/library/mt704050.aspx) for more information.

## Restricting the use of personal data for profiling or marketing without consent
A Security Center user can choose to opt out by deleting their [security contact data](security-center-provide-security-contact-details.md).

[Just in time data](security-center-just-in-time.md) is considered non-identifiable data and is retained for a period of 30 days.

[Alert data](security-center-managing-and-responding-alerts.md) is considered security data and is retained for a period of two years.

## Auditing and reporting
Audit logs of security contact, just in time, and alert updates are maintained in [Azure Activity Logs](../monitoring-and-diagnostics/monitoring-overview-activity-logs.md).

## Next steps
For more information about managing user data, see [Manage user data found in an Azure Security Center investigation](security-center-investigation-user-data.md).
