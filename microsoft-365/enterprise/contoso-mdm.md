---
title: Beheer van mobiele apparaten voor Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Meer informatie over hoe contoso Microsoft intune gebruikt in Microsoft 365 for Enterprise voor het beheren van de apparaten en de apps die daarop worden uitgevoerd.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753991"
---
# <a name="mobile-device-management-for-contoso"></a>Beheer van mobiele apparaten voor Contoso

Microsoft 365 voor Enterprise omvat intune en een set Azure-Services die ondersteuning bieden voor mobiel apparaat en toepassingen beheren en beveiliging.

Contoso kent veel mobiele medewerkers. Sommige hebben kantoren op contoso locaties en sommige hebben geen kantoren. Contoso had behoefte aan een manier om de productiviteit van medewerkers in te schakelen, maar de apparaten, de gegevens op die apparaten en het gedrag van toepassingen veilig te houden.

## <a name="plan"></a>Plannen

Contoso heeft de volgende intune-gebruik gevallen vastgesteld voor het beheer van mobiele apparaten voor Microsoft 365 for Enterprise:

- E-mail en gegevens van Exchange Online beveiligen, zodat deze veilig kan worden geopend door mobiele apparaten.
- Implementeer een versie van het BYOD-programma (online) voor Contoso medewerkers.
- Problemen met de organisatie en beperkte telefoons en beperkte deelnemers gebruiken voor werknemers van contoso.

Contoso maakt geen gebruik van intune voor:

- Medewerkers in staat stellen om Microsoft 365 veilig te openen vanuit een openbare kiosk.
- Beveilig on-premises e-mailadres en gegevens, zodat het veilig kan worden geopend door mobiele apparaten, omdat er geen on-premises Microsoft Exchange-servers zijn.

## <a name="deploy"></a>Implementeren

Dit is de manier waarop Contoso de infrastructuur voor het beheer van mobiele apparaten heeft ingesteld:

- Stel intune in als de MDM-Authority (Mobile Device Management) en gebruik intune op Azure om inhoud te beheren en de apparaten te beheren
- Azure Active Directory-groepen (Azure AD) maken voor apparaten voor de registratie en intune-instellingen en het beleid voor voorwaardelijke toegang op basis van een apparaat

  Zie [voorwaardelijke toegangsbeleid van Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)voor meer informatie.

- Het Apple-platform is ingeschakeld voor ondersteuning van werknemers met iPads, iMacs en iPhones en van corporate zijnde iPhones
- Specifiek Contoso-voorwaardenbeleid gemaakt, dat wordt weergegeven tijdens de installatie van het bedrijfsportaal van Contoso op mobiele apparaten
- Voor apparaten die niet zijn ingeschreven, is een set Mobile Application Management-beleid (MAM) geïmplementeerd waarvoor verificatie is vereist voor toegang tot services van Microsoft 365.
- Intune-beleid gemaakt dat het volgende afdwingt:
  - Toegestane apps.
  - Apparaatversleuteling om toegang door onbevoegden te helpen voorkomen.
  - Een pincode of wachtwoord van zes cijfers.
  - Een inactiviteit-time-outperiode.
  - Beveiliging tegen virussen en malware, en handtekening updates met Windows Defender op Windows 10-apparaten.
  - Automatische updates op Windows 10-apparaten die de nieuwste beveiligingsupdates bevatten.
  - Certificaten naar beheerde apparaten pushen.
  - Een duidelijke scheiding tussen bedrijfs- en persoonlijke gegevens.  Gebruikers of beheerders kunnen selectief bedrijfsgegevens van het apparaat wissen en persoonlijke gegevens als foto’s, persoonlijke e-mailaccounts en persoonlijke bestanden ongemoeid laten.

Door contoso geregistreerde geïmplementeerde Pc's en eigen smartphones en tablets door ze toe te voegen aan de desbetreffende groepen van intune-apparaten. Ze hebben ook een BYOD-programma gemaakt voor werknemers die hun persoonlijke apparatuur kunnen registreren. Geregistreerde apparaten ontvangen intune-beleidsregels, wat resulteert in beheerde en beveiligde apparaten en hun toepassingen. Apparaten die niet zijn ingeschreven, hebben een Mobile Application Management-beleid (MAM) die toegestane toepassingen opgeven.

Dit is de implementatie architectuur voor mobiel Apparaatbeheer van contoso.

![Implementatie-infrastructuur van Contoso Mobile Device Management](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Volgende stap

Meer informatie over hoe Contoso de [mogelijkheden voor informatiebescherming](contoso-info-protect.md) van microsoft 365 for Enterprise gebruikt voor het classificeren, identificeren en beschermen van cruciale digitale activa binnen de organisatie.

## <a name="see-also"></a>Zie ook

[Apparaatbeheer voor Microsoft 365](device-management-roadmap-microsoft-365.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

