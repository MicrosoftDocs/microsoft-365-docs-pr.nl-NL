---
title: 'Ondersteuning voor Microsoft 365 client-apps: enkelvoudige Sign-On'
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
ms.openlocfilehash: b70f0c1ec4a6e94651b987830c8b29993732a3c2
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806659"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a>Ondersteuning voor Microsoft 365 client-apps: enkelvoudige Sign-On

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met eenmalige aanmelding (SSO) kunt u beveiliging en gemak toevoegen wanneer uw gebruikers zich aanmelden bij toepassingen in azure Active Directory. Met eenmalige aanmelding meldt gebruikers zich eenmaal aan met één account voor toegang tot on-premises Active Directory Domain Services (AD DS)-domein, software als een service (SaaS) en webtoepassingen.

Meer informatie over [eenmalige aanmelding](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="supported-clients--platforms"></a>Ondersteunde clients & platforms

De meest recente versies van de volgende clients en platforms ondersteunen eenmalige aanmelding. Zie [systeemvereisten voor Microsoft 365](https://products.office.com/office-system-requirements)voor meer informatie over platform ondersteuning in microsoft 365.
<br>
<br>

| Emulatieclients | Android | Apparaten | Mac| Windows 10 <br> Moderne apps| Windows 10 <br> Desk |
|:---|:---:|:---:|:---:|:---:|:---:|
| Access | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Bedrijfsportal | N.v.t. | ![Ondersteund](../media/check-mark.png) | Overwogen | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Cortana | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Delve | Overwogen | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Allernieuwste | ![Ondersteund](../media/check-mark.png) | Overwogen | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Excel | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Kaizala | ![Ondersteund](../media/check-mark.png) | Overwogen | N.v.t. | N.v.t. | N.v.t. |
| Office Lens| ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Office Mobile | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Office-Portal | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| OneDrive | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | Overwogen | ![Ondersteund](../media/check-mark.png) | Overwogen |
| OneNote | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | Overwogen |
| Outlook | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | Overwogen | ![Ondersteund](../media/check-mark.png) |
| Planner | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Power Apps | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | Overwogen | N.v.t. |
| Automatisch aan de macht | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Power BI | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) | Overwogen |
| PowerPoint | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Project | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Publisher | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Skype voor Bedrijven | Overwogen | Overwogen | N.v.t. | N.v.t. | N.v.t. |
| SharePoint | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Sticky Notes | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Stream | Overwogen | Overwogen | N.v.t. | N.v.t. | N.v.t. |
| Sway | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Teams | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | Overwogen | N.v.t. | Overwogen |
| Taak | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Visio | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Whiteboard | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Word | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Yammer | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | Overwogen |

## <a name="supported-powershell-modules"></a>Ondersteunde PowerShell-modules

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online-PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
