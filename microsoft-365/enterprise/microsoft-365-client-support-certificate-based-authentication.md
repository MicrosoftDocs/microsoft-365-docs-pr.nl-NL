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
description: In dit artikel vindt u meer informatie over ondersteuning voor de Microsoft 365-client-app voor verificatie op basis van certificaten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 57ced47c268f4d0515acb26aa8f705fa6e9ae0f9
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999382"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Ondersteuning voor Microsoft 365-client-apps: verificatie op basis van certificaat

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Moderne verificatie is een overkoepelende term voor een combinatie van authenticatie-en autorisatie methoden. Dit zijn onder andere:

- **Verificatiemethoden** : meervoudige verificatie; Verificatie op basis van client certificaat.
- **Autorisatie methoden** : de implementatie van Microsoft Open Authorization (OAuth).

Moderne verificatie wordt ingeschakeld via het gebruik van een authenticatie bibliotheek, zoals Active Directory Authentication Library (ADAL) of Microsoft Authentication Library (MSAL). Moderne verificatie is wat clients gebruiken om toegang tot bronnen van Microsoft 365 te verifiëren en te machtigen. Moderne verificatie maakt gebruik van OAuth en biedt een veilig mechanisme voor het verkrijgen van toegang tot Microsoft 365-Services, zonder dat ze toegang hebben tot gebruikersreferenties. Wanneer de gebruiker zich aanmeldt, verifieert de gebruiker rechtstreeks met Azure Active Directory en ontvangt een token paar voor Access/vernieuwen. Met het toegangstoken wordt de clienttoegang verleend tot de juiste bronnen in de Microsoft 365-Tenant. Een vernieuwingstoken wordt gebruikt om een nieuw toegangstoken of vernieuwingstoken paar te verkrijgen wanneer het huidige toegangstoken verloopt.

Moderne verificatie ondersteunt verschillende verificatiemethoden, zoals verificatie op basis van certificaten. Clients op Windows-, Android-of iOS-apparaten kunnen verificatie op basis van certificaten (CBA) gebruiken voor verificatie met Azure Active Directory via een clientcertificaat op het apparaat. In plaats van een typische gebruikersnaam/wachtwoord wordt het certificaat gebruikt om een token paar van Azure Active Directory te verkrijgen.

Meer informatie over [verificatie op basis van certificaten](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Ondersteunde clients & platforms

De meest recente versies van de volgende clients en platforms ondersteunen verificatie op basis van certificaten wanneer u zich aanmeldt bij Azure Active Directory-accounts binnen de client (bijvoorbeeld wanneer u een account toevoegt aan de app). Zie [systeemvereisten voor Microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)voor meer informatie over platform ondersteuning in microsoft 365.
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
| Edge<sup>1</sup> | ![Ondersteund](../media/check-mark.png) | ![Ondersteund](../media/check-mark.png) | N.v.t. | N.v.t. | ![Ondersteund](../media/check-mark.png) |
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

>[!NOTE]
><sup>1</sup> Edge voor IOS en Android ondersteunt verificatie op basis van certificaten tijdens het account toevoegen van stromen. Edge voor iOS en Android biedt geen ondersteuning voor verificatie op basis van certificaten wanneer u authenticatie uitvoert voor websites die meestal intranetsites zijn. <br><br>  In dit scenario gaat een gebruiker navigeren naar een website (meestal op het intranet) waar de gebruiker moet authenticatie via een certificaat voor de website. Dit geldt niet voor moderne verificatie en maakt geen gebruik van een Microsoft-verificatie bibliotheek. Dit wordt veroorzaakt door een beperking met iOS: iOS voorkomt dat apps van derden toegang krijgen tot de systeemsleutel hanger, waar de certificaten worden opgeslagen (alleen Apple-apps en de Webwerkset van [Safari](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) hebben toegang tot de systeemsleutel hanger <br><br> De Edge is niet toegankelijk voor webkit, maar het is niet mogelijk om de sleutelhanger van het systeem te openen en de gebruiker met de optie certificaat te presenteren. Dit is helaas een ontwerp vanwege de architectuur van Apple.

## <a name="supported-powershell-modules"></a>Ondersteunde PowerShell-modules

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online-PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

