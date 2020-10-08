---
title: Ondersteuning voor de Microsoft 365-client-app — moderne verificatie
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: In dit artikel vindt u informatie over welke platforms, clients en PowerShell-modules moderne verificatie voor Microsoft 365 ondersteunen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eee0e9009f7e6a74f25ebf0315b2772ac3e98814
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384822"
---
# <a name="microsoft-365-client-app-support---modern-authentication"></a>Ondersteuning voor Microsoft 365 client app-moderne verificatie

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Moderne verificatie Active Directory Authentication Library (ADAL)-aanmelding voor Office-clienttoepassingen op verschillende platforms. Hiermee kunt u aanmeld functies, zoals meervoudige verificatie (MFA), smartcard en verificatie op basis van certificaten.

Meer informatie over [multi-factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication) en [verificatie op basis van certificaten](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started).

## <a name="supported-platforms"></a>Ondersteunde platformen

 - Bureaublad van Windows 10
 - Moderne Windows 10-apps
 - Browser<sup>1</sup>
 - Android<sup>2</sup>
 - Apparaten
 - macOS

Zie [systeemvereisten voor Microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)voor meer informatie over platform ondersteuning in microsoft 365.

## <a name="supported-clients"></a>Ondersteunde clients

De meest recente versies van de volgende clients ondersteunen moderne verificatie:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Pictogram toegang](../media/o365-access-64x64.png) <br> [Toegang](https://products.office.com/access) | ![Azure-pictogram](../media/o365-azure-64x64.png) <br> [Azure- <br> Portal ](https://azure.microsoft.com/features/azure-portal/) | ![Pictogram voor bedrijfsportal](../media/o365-microsoft-64x64.png) <br> [Bedrijfs <br> Portal ](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Pictogram Delve](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Dynamics 365-pictogram](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) 
| ![Pictogram Edge](../media/o365-edge-64x64.png) <br> [Allernieuwste](https://www.microsoft.com/windows/microsoft-edge) | ![Excel-pictogram](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![Formulier pictogram](../media/o365-forms-64x64.png) <br> [Forms](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) | ![Kaizala-pictogram](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Office.com-pictogram](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) 
| ![Pictogram Office 365-beheerder](../media/o365-o365admin-64x64.png) <br> [Microsoft 365- <br> beheerder](https://products.office.com/business/manage-office-365-admin-app) | ![Lens pictogram](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![OneDrive voor bedrijven-pictogram](../media/o365-OneDrive-64x64.png) <br> [OneDrive](https://products.office.com/onedrive-for-business/online-cloud-storage) |  ![OneNote-pictogram](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Outlook-pictogram](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) 
| ![Pictogram planner](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![PowerApps-pictogram](../media/o365-powerapps-64x64.png) <br> [PowerApps ](https://powerapps.microsoft.com) | ![Pictogram Power automatisch automatiseren](../media/o365-flow-64x64.png) <br> [Automatisch aan de macht <br>](https://flow.microsoft.com) | ![PowerBI-pictogram](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com)| ![PowerPoint-pictogram](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Project-pictogram](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Publisher-pictogram](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![SharePoint-pictogram](../media/o365-sharepoint-64x64.png) <br> [Point](https://products.office.com/sharepoint) | ![Skype voor bedrijven-pictogram](../media/o365-skypeforbusiness-64x64.png) <br> [Skype voor <br> bedrijven<sup>1</sup>](https://www.skype.com/business/) | ![StaffHub-pictogram](../media/o365-staffhub-64x64.png) <br> [StaffHub](https://products.office.com/microsoft-staffhub/staff-scheduling-software)
| ![Pictogram Sticky Notes](../media/o365-stickynotes-64x64.png) <br> [Sticky Notes](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | ![Pictogram stream](../media/o365-stream-64x64.png) <br> [Stream](https://stream.microsoft.com) | ![Sway-pictogram](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![Pictogram teams](../media/o365-teams-64x64.png) <br> [Teams](https://products.office.com/microsoft-teams/group-chat-software) | ![Pictogram taak](../media/o365-todo-64x64.png) <br> [Taak](https://todo.microsoft.com) 
| ![Visio-pictogram](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Whiteboard pictogram](../media/o365-whiteboard-64x64.png) <br> [Whiteboard<sup>1</sup>,<sup>2</sup>](https://whiteboard.microsoft.com/) | ![Word-pictogram](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Pictogram Yammer](../media/o365-yammer-64x64.png) <br> [Yammer](https://products.office.com/yammer/yammer-overview) | ![Pictogram Yammer](../media/o365-yammer-64x64.png) <br> [Yammer- <br> kennisgeving](https://products.office.com/yammer/yammer-overview) |  |

## <a name="supported-powershell-modules"></a>Ondersteunde PowerShell-modules

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure-pictogram](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Pictogram Exchange](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![SharePoint-pictogram](../media/o365-sharepoint-64x64.png) <br> [SharePoint Online- <br> PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> ondersteuning voor whiteboard en Skype voor bedrijven op de web-app die binnenkort beschikbaar is. <br>
> <sup>2</sup> ondersteuning voor whiteboard op Android is binnenkort beschikbaar.

## <a name="see-also"></a>Zie ook

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
