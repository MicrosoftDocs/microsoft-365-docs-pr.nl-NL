---
title: 'Ondersteuning voor Microsoft 365-client app: voorwaardelijke toegang'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: In dit artikel vindt u informatie over welke platforms, clients en PowerShell-modules voorwaardelijke toegang voor Microsoft 365 ondersteunen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc187a26cd3aa644888312327b07fc9a116950cc
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806680"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Ondersteuning voor Microsoft 365-client app: voorwaardelijke toegang

In de moderne werknemer hebben gebruikers toegang tot de bronnen van uw organisatie met behulp van diverse apparaten en apps, waar u ook bent. Daarom is het dus niet voldoende om aan te geven wie toegang heeft tot een resource. Uw organisatie moet ook ondersteunen hoe en waar een resource in de infrastructuur van toegangsbeheer wordt geopend.

Met Azure Active Directory-apparaat, locatie en meervoudige verificatie op basis van een voorwaardelijke toegang kunt u aan deze nieuwe vereiste voldoen. Voorwaardelijke toegang is een mogelijkheid van Azure Active Directory waarmee u besturingselementen voor de toegang tot apps in uw omgeving kunt afdwingen, op basis van specifieke voorwaarden en die u vanaf een centrale locatie kunt beheren.

Zie [voorwaardelijke toegang tot Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/)voor meer informatie.

## <a name="supported-clients--platforms"></a>Ondersteunde clients & platforms

De meest recente versies van de volgende clients en platforms ondersteunen voorwaardelijke toegang. Zie [systeemvereisten voor Microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)voor meer informatie over platform ondersteuning in microsoft 365.

<br>
<br>

| Emulatieclients | Android | Apparaten | Mac| Windows 10 <br> Moderne apps| Windows 10 <br> Desk |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory-beheerder | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Access | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Azure-beheerder | N.v.t. | N.v.t. | N.v.t. | N.v.t. | N.v.t. |
| Bedrijfsportal | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Cortana | Overwogen | Overwogen | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Delve | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Allernieuwste | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Excel | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Beheerder van Exchange Online | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Forms | N.v.t. | N.v.t. | N.v.t. | N.v.t. | N.v.t. |
| Office 365-beheerder | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |  |
| Kaizala | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Office Lens| ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Office Mobile | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Office-Portal | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| OneDrive | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| OneNote | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Outlook | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Planner | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Power Apps | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | Overwogen | N.v.t. |
| Automatisch aan de macht | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Power BI | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| PowerPoint | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Project | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Publisher | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Skype voor Bedrijven | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. ||
| SharePoint | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| SharePoint Online-beheerder | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Sticky Notes | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Stream | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Sway | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Teams | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Taak | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Visio | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Whiteboard | Overwogen | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Word | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Bedrijfsanalyse | N.v.t. | N.v.t. | N.v.t. | N.v.t. | N.v.t. |
| Yammer | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>Ondersteunde PowerShell-modules

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online-PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
