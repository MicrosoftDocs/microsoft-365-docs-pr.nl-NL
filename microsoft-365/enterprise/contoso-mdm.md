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
description: Meer inzicht in hoe Contoso Microsoft Intune in Microsoft 365 voor bedrijven gebruikt om de apparaten en de apps die erop worden uitgevoerd, te beheren.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753991"
---
# <a name="mobile-device-management-for-contoso"></a>Beheer van mobiele apparaten voor Contoso

Microsoft 365 voor bedrijven bevat Intune en een set Azure-services die ondersteuning bieden voor mobiel apparaat- en toepassingsbeheer en -beveiliging.

Contoso heeft veel mobiele werknemers. Sommige hebben kantoren op Contoso-locaties en sommige hebben geen kantoren. Contoso had behoefte aan een manier om de productiviteit van medewerkers in te schakelen, maar de apparaten, de gegevens op die apparaten en het gedrag van toepassingen veilig te houden.

## <a name="plan"></a>Plannen

Contoso heeft de volgende Intune-gebruiksgevallen voor mobiel apparaatbeheer voor Microsoft 365 voor bedrijven geïdentificeerd:

- Bescherm Exchange Online e-mail en gegevens zodat deze veilig toegankelijk zijn op mobiele apparaten.
- Implementeert een BYOD-programma (Bring-your-own-device) voor Medewerkers van Contoso.
- Problemen met telefoons die eigendom zijn van de organisatie en gedeelde tablets voor beperkt gebruik aan contoso-werknemers.

Contoso gebruikt Intune niet voor:

- Sta werknemers toe veilig toegang te krijgen tot Microsoft 365 vanuit een niet-bemande openbare kiosk.
- Bescherm on-premises e-mail en gegevens, zodat deze veilig kunnen worden gebruikt op mobiele apparaten, omdat er geen on-premises Microsoft-Exchange zijn.

## <a name="deploy"></a>Implementeren

Dit is de manier waarop Contoso de infrastructuur voor het beheer van mobiele apparaten heeft ingesteld:

- Stel Intune in als de MDM-autoriteit (Mobile Device Management) en gebruik Intune op Azure om inhoud te beheren en de apparaten te beheren
- Gemaakt Azure Active Directory (Azure AD) groepen voor apparaten voor inschrijvings- en Intune-instellingen en op apparaten gebaseerd beleid voor voorwaardelijke toegang

  Zie Beleidsregels voor Voorwaardelijke toegang [van Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)voor meer informatie.

- Het Apple-apparaatplatform ingeschakeld om werknemers te ondersteunen met iPads, iMacs en iPhones en iPhones van het bedrijf
- Specifiek Contoso-voorwaardenbeleid gemaakt, dat wordt weergegeven tijdens de installatie van het bedrijfsportaal van Contoso op mobiele apparaten
- Voor apparaten die niet zijn geregistreerd, heeft u een reeks MAM-beleidsregels (Mobile Application Management) geïmplementeerd om verificatie te vereisen voor toegang tot Microsoft 365 services
- Intune-beleid gemaakt dat het volgende afdwingt:
  - Toegestane apps.
  - Apparaatversleuteling om onbevoegde toegang te voorkomen.
  - Een pincode of wachtwoord met zes cijfers.
  - Een time-outperiode voor inactiviteit.
  - Antivirus- en malwarebeveiliging en handtekeningupdates met Windows Defender op Windows 10 apparaten.
  - Automatische updates op Windows 10 apparaten met de meest recente beveiligingsupdates.
  - Certificaten naar beheerde apparaten pushen.
  - Een duidelijke scheiding tussen bedrijfs- en persoonlijke gegevens.  Gebruikers of beheerders kunnen selectief bedrijfsgegevens van het apparaat wissen en persoonlijke gegevens als foto’s, persoonlijke e-mailaccounts en persoonlijke bestanden ongemoeid laten.

Contoso heeft geïmplementeerde pc's en smartphones en tablets van het bedrijf geregistreerd door ze toe te voegen aan de juiste Intune-apparaatgroepen. Ze hebben ook een BYOD-programma ingesteld voor werknemers om hun persoonlijke apparaten in te schrijven. Geregistreerde apparaten ontvangen Intune-beleid, wat resulteert in beheerde en beveiligde apparaten en hun toepassingen. Apparaten die niet zijn geregistreerd, hebben MAM-beleid (Mobile Application Management) dat toegestane toepassingen opgeeft.

Hier is de implementatiearchitectuur voor mobiele apparaatbeheer van Contoso.

![Implementatie-infrastructuur voor mobiel apparaatbeheer van Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Volgende stap

Lees hoe Contoso gebruikmaakt van de [informatiebeveiligingsmogelijkheden](contoso-info-protect.md) van Microsoft 365 voor ondernemingen om essentiële digitale activa in de hele organisatie te classificeren, te identificeren en te beveiligen.

## <a name="see-also"></a>Zie ook

[Apparaatbeheer voor Microsoft 365](device-management-roadmap-microsoft-365.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

