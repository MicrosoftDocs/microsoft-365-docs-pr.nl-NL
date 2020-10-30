---
title: 'Ondersteuning voor Microsoft 365-client-apps: verificatie op basis van certificaat'
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
description: In dit artikel vindt u meer informatie over ondersteuning voor de Microsoft 365-client app voor verificatie op basis van certificaten...
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 49ed1e329e83b73441c89de9a142bfb9dcac5395
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806692"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Ondersteuning voor Microsoft 365-client-apps: verificatie op basis van certificaat

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Verificatie op basis van certificaten: u kunt zich verifiëren bij Azure Active Directory met een clientcertificaat op Windows-, Android-of iOS-apparaten. Met deze functie kunt u een combinatie van gebruikersnaam en wachtwoord invoeren in bepaalde e-mail-en Microsoft Office-toepassingen op uw mobiele apparaat.

Meer informatie over [verificatie op basis van certificaten](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Ondersteunde clients & platforms

De nieuwste versies van de volgende clients en platforms ondersteunen verificatie op basis van certificaten. Zie [systeemvereisten voor Microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)voor meer informatie over platform ondersteuning in microsoft 365.
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
| OneDrive | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | Overwogen | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| OneNote | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Outlook | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Planner | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Power Apps | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Automatisch aan de macht | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Power BI | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| PowerPoint | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Project | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Publisher | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Skype voor Bedrijven | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Skype voor bedrijven-beheerder | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| SharePoint | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| SharePoint Online-beheerder | Overwogen | Overwogen | N.v.t. | N.v.t. | N.v.t. |
| Sticky Notes | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Stream | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Sway | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Teams | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | Overwogen |
| Taak | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Visio | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Whiteboard | Overwogen | Overwogen | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Word | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Bedrijfsanalyse | N.v.t. | N.v.t. | N.v.t. | N.v.t. | N.v.t. |
| Yammer | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | Overwogen | N.v.t. | Overwogen |

## <a name="supported-powershell-modules"></a>Ondersteunde PowerShell-modules

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online-PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

