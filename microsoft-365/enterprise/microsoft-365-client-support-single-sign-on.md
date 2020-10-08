---
title: Ondersteuning voor Microsoft 365-client apps – eenmalige aanmelding
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
description: In dit artikel vindt u informatie over welke platforms, clients en PowerShell-modules eenmalige aanmelding voor Microsoft 365 ondersteunen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d0a45c30ffe736cf67e811bce6eb029d6fb50674
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384808"
---
# <a name="microsoft-365-client-app-support--single-sign-on"></a>Ondersteuning voor Microsoft 365-client apps – eenmalige aanmelding

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met eenmalige aanmelding (SSO) kunt u beveiliging en gemak toevoegen wanneer gebruikers zich aanmelden bij toepassingen in azure Active Directory (Azure AD). Met eenmalige aanmelding meldt gebruikers zich eenmaal aan met één account voor toegang tot on-premises Active Directory Domain Services (AD DS)-domein, software als een service (SaaS) en webtoepassingen.

Meer informatie over [eenmalige aanmelding](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="supported-platforms"></a>Ondersteunde platformen

 - Windows 10 bureaublad<sup>2</sup>
 - Moderne Windows 10-apps
 - Webbrowsers
 - Android<sup>3</sup>
 - iOS<sup>1</sup>
 - macOS<sup>4</sup>

Zie [systeemvereisten voor Microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)voor meer informatie over platform ondersteuning in microsoft 365.

## <a name="supported-clients"></a>Ondersteunde clients

De meest recente versies van de volgende clients ondersteunen eenmalige aanmelding:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Pictogram toegang](../media/o365-access-64x64.png) <br> [Toegang](https://products.office.com/access) | ![Pictogram voor bedrijfsportal](../media/o365-microsoft-64x64.png) <br> [Bedrijfs <br> Portal<sup>3, 4</sup>](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Pictogram Delve](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Pictogram Edge](../media/o365-edge-64x64.png) <br> [Edge<sup>1</sup>](https://www.microsoft.com/windows/microsoft-edge) | ![Excel-pictogram](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) 
| ![Kaizala-pictogram](../media/o365-kaizala-64x64.png) <br> [Kaizala<sup>1</sup>](https://products.office.com/en/business/microsoft-kaizala) | ![Office.com-pictogram](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![Lens pictogram](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![OneDrive voor bedrijven-pictogram](../media/o365-OneDrive-64x64.png) <br> [OneDrive](https://products.office.com/onedrive-for-business/online-cloud-storage) | ![OneNote-pictogram](../media/o365-OneNote-64x64.png) <br> [OneNote<sup>2</sup>](https://products.office.com/onenote) 
| ![Outlook-pictogram](../media/o365-outlook-64x64.png) <br> [Outlook<sup>4</sup>](https://products.office.com/outlook) | ![Pictogram planner](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![Pictogram Power automatisch automatiseren](../media/o365-flow-64x64.png) <br> [Automatisch aan de macht <br>](https://flow.microsoft.com) | ![PowerBI-pictogram](../media/o365-powerbi-64x64.png) <br> [Power BI<sup>2</sup>](https://powerbi.microsoft.com)| ![PowerPoint-pictogram](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Project-pictogram](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Publisher-pictogram](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![SharePoint-pictogram](../media/o365-sharepoint-64x64.png) <br> [Point](https://products.office.com/sharepoint) | ![Pictogram Sticky Notes](../media/o365-stickynotes-64x64.png) <br> [Sticky Notes](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw)  | ![Sway-pictogram](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) 
| ![Pictogram teams](../media/o365-teams-64x64.png) <br> [Teams<sup>2, 4</sup>](https://products.office.com/microsoft-teams/group-chat-software) | ![Pictogram taak](../media/o365-todo-64x64.png) <br> [Taak](https://todo.microsoft.com) | ![Visio-pictogram](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Whiteboard pictogram](../media/o365-whiteboard-64x64.png) <br> [Whiteboard<sup>3</sup>](https://whiteboard.microsoft.com/) | ![Word-pictogram](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) 
| ![Pictogram Yammer](../media/o365-yammer-64x64.png) <br> [Yammer<sup>2</sup>](https://products.office.com/yammer/yammer-overview) |

## <a name="supported-powershell-modules"></a>Ondersteunde PowerShell-modules

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure-pictogram](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Pictogram Exchange](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![SharePoint-pictogram](../media/o365-sharepoint-64x64.png) <br> [SharePoint Online- <br> PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> ondersteuning voor Edge en Kaizala op Ios is binnenkort beschikbaar. <br>
> <sup>2</sup> ondersteuning voor OneNote, PowerBI, teams en Yammer op Windows 10-bureaublad is binnenkort beschikbaar. <br>
> <sup>3</sup> ondersteuning voor whiteboard op Android is binnenkort beschikbaar. <br>
> <sup>4</sup> ondersteuning voor Outlook, teams en bedrijfs portal op macOS is binnenkort beschikbaar. <br>

## <a name="see-also"></a>Zie ook

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
