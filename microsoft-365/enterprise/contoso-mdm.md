---
title: Beheer van mobiele apparaten voor Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Meer informatie over hoe Contoso Microsoft Intune gebruikt in Microsoft 365 Enterprise voor het beheren van haar apparaten en de apps die erop worden uitgevoerd.
ms.openlocfilehash: 7232c89cc105525cc57facd5a1b9de06426adbca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811285"
---
# <a name="mobile-device-management-for-contoso"></a>Beheer van mobiele apparaten voor Contoso

Microsoft 365 Enterprise omvat Intune en een verzameling Azure-services om mobiele apparaten, toepassingsbeheer en beveiliging te ondersteunen.

Contoso heeft veel mobiele medewerkers, waarvan sommigen een werkplek hebben in Contoso-locaties en anderen niet. Contoso had behoefte aan een manier om de productiviteit van medewerkers in te schakelen, maar de apparaten, de gegevens op die apparaten en het gedrag van toepassingen veilig te houden.

## <a name="plan"></a>Plannen

Al vroeg in de analyse van beheer van mobiele apparaten voor Microsoft 365 Enterprise identificeerde Contoso de volgende Intune-use cases:

- Exchange Online-e-mail en -gegevens beschermen, zodat ze veilig kunnen worden gebruikt door mobiele apparaten
- Een BYOD-programma (Bring Your Own Device) implementeren voor Contoso-werknemers
- Telefoons en gedeelde tabletten met beperkt gebruik in eigendom van Contoso uitgeven aan Contoso-werknemers.

Contoso gebruikt Intune niet om:

- Werknemers veilige toegang te bieden tot Office 365 vanuit een onbeheerde openbare kiosk
- On-premises e-mail en gegevens te beschermen, zodat ze veilig kunnen worden gebruikt door mobiele apparaten, omdat er geen on-premises Microsoft Exchange-servers meer zijn.

## <a name="deploy"></a>Implementeren

Dit is de manier waarop Contoso de infrastructuur voor het beheer van mobiele apparaten heeft ingesteld:

- Intune als MDM-instantie (Mobile Device Management) ingesteld en Intune op Azure om de inhoud en apparaten te beheren
- Azure AD-groepen gemaakt voor apparaten voor registratie en Intune-instellingen en beleid voor voorwaardelijke toegang voor apparaten

  Zie [Beleid voor voorwaardelijke toegang van Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) voor meer informatie.

- Het Apple-apparaatplatform ingeschakeld om medewerkers met iPads, iMacs, iPhones te ondersteunen en voor op iPhone-gebaseerde telefoons van Contoso
- Specifiek Contoso-voorwaardenbeleid gemaakt, dat wordt weergegeven tijdens de installatie van het bedrijfsportaal van Contoso op mobiele apparaten
- Een verzameling MAM-beleid (Mobile Application Management) gemaakt om verificatie te eisen voor toegang tot Office 365-services voor apparaten die niet zijn geregistreerd
- Intune-beleid gemaakt dat het volgende afdwingt:
  - Goedgekeurde apps
  - Apparaatversleuteling om ongeoorloofde toegang te voorkomen
  - Een pincode of wachtwoord van zes cijfers
  - Een timeout-periode als niet actief
  - Antivirus- en malwarebescherming en handtekeningupdates met Windows Defender op Windows 10-apparaten
  - Automatische updates op Windows 10-apparaten inclusief de nieuwste beveiligingsupdates
  - Certificaten pushen naar beheerde apparaten
  - Een duidelijke scheiding tussen bedrijfs- en persoonlijke gegevens.  Gebruikers of beheerders kunnen selectief bedrijfsgegevens van het apparaat wissen en persoonlijke gegevens als foto’s, persoonlijke e-mailaccounts en persoonlijke bestanden ongemoeid laten.

Na de implementatie registreerde Contoso pc’s en smartphones en tablets van het bedrijf door ze toe te voegen aan de juiste Intune-apparaatgroepen en implementeerde een BYOD-programma voor werknemers, zodat die hun persoonlijke apparaten konden registreren. Registreerde apparaten ontvingen Intune-beleid en dat resulteerde in beheerde en beveiligde apparaten en toepassingen. Apparaten die niet zijn geregistreerd hebben MAM-beleid (Mobile Application Management) dat de toegestane toepassingen specificeert.

Hieronder ziet u de implementatie-architectuur voor het beheer van mobiele apparaten van Contoso.

![De implementatie-infrastructuur voor het beheer van mobiele apparaten van Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Volgende stap

[Meer informatie](contoso-info-protect.md) over hoe Contoso de mogelijkheden voor gegevensbescherming van Microsoft 365 Enterprise gebruikt om belangrijke digitale activa binnen de organisatie te classificeren, te identificeren en te beschermen.

## <a name="see-also"></a>Zie ook

[Beheer van mobiele apparaten voor Microsoft 365 Enterprise](mobility-infrastructure.md)

[Implementatiehandleiding](deploy-microsoft-365-enterprise.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

