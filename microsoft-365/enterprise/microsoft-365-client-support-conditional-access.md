---
title: 'Ondersteuning voor Microsoft 365-client-apps: Voorwaardelijke toegang'
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
description: In dit artikel wordt beschreven welke platforms, clients en PowerShell-modules voorwaardelijke toegang voor Microsoft 365 ondersteunen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 969dd9d712fe124458273144b3e7974e03ade9e0
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097244"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Ondersteuning voor Microsoft 365-client-apps: Voorwaardelijke toegang

In de moderne werkplek hebben gebruikers vanaf elke locatie toegang tot de bronnen van uw organisatie via verschillende apparaten en apps. Als u zich alleen maar richt op wie toegang heeft tot een resource, volstaat het niet meer. Uw organisatie moet ook ondersteunen hoe en waar een bron wordt gebruikt in uw toegangsbeheerinfrastructuur.

Met Azure Active Directory-apparaat, locatie en voorwaardelijke toegang op basis van meervoudige verificatie kunt u aan deze nieuwe vereiste voldoen. Voorwaardelijke toegang is een functie van Azure Active Directory waarmee u besturingselementen kunt afdwingen voor de toegang tot apps in uw omgeving, allemaal op basis van specifieke voorwaarden en die worden beheerd vanaf een centrale locatie.

Meer informatie over voorwaardelijke [toegang voor Azure Active Directory.](/azure/active-directory/conditional-access/)

## <a name="supported-clients--platforms"></a>Ondersteunde clients & platforms

De nieuwste versies van de volgende clients en platforms ondersteunen voorwaardelijke toegang. Zie de systeemvereisten voor Microsoft 365 voor meer informatie over platformondersteuning in [Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)

<br>
<br>

| Klanten | Android | iOS | Mac| Windows 10 <br> Moderne apps| Windows 10 <br> Bureaublad |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory-beheerder | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Toegang | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Azure-beheerder | N.v.t. | N.v.t. | N.v.t. | N.v.t. | N.v.t. |
| Bedrijfsportal | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Cortana | Gepland | Gepland | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Delve | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Edge | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Excel | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Exchange Online-beheerder | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Forms | N.v.t. | N.v.t. | N.v.t. | N.v.t. | N.v.t. |
| Office 365-beheerder | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |  |
| Kaizala | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Office Lens| ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Office Mobile | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Office-portal | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| OneDrive | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| OneNote | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Outlook | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Planner | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Power Apps | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | Gepland | N.v.t. |
| Power Automate | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Power BI | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| PowerPoint | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Project | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Publisher | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Skype voor Bedrijven | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. ||
| SharePoint | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| SharePoint Online-beheerder | N.v.t. | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Plaknotities | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Stream | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | N.v.t. |
| Sway | N.v.t. | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Teams | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| To Do | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Visio | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
| Whiteboard | Gepland | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) | N.v.t. |
| Word | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) |
| Werkplekanalyse | N.v.t. | N.v.t. | N.v.t. | N.v.t. | N.v.t. |
| Yammer | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | ![Ondersteund](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>Ondersteunde PowerShell-modules

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
