---
title: Veelgestelde vragen over basismobiliteit en beveiliging
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Veelgestelde vragen over basismobiliteit en beveiliging.
ms.openlocfilehash: 14e12678ec210325f63914594fb6debcf7abb880
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023891"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Veelgestelde vragen over basismobiliteit en beveiliging

Dit artikel bevat veelgestelde vragen over Basismobiliteit en beveiliging, een functie waarmee u mobiele apparaten kunt beheren en beveiligen in Microsoft 365. Als u geen antwoord op uw vraag kunt vinden, laat het ons dan weten door een opmerking op de pagina achter te laten, zodat we uw vraag kunnen toevoegen aan dit artikel.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Hoe kan ik basismobiliteit en beveiliging krijgen? Ik zie het niet in het Microsoft 365 beheercentrum

1.  Activeer Basismobiliteit en beveiliging door naar de pagina [Office 365 Beveiligings- & compliance te](https://protection.office.com/) gaan.

2.  Ga naar Preventie van gegevensverlies > Apparaatbeheer.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Hoe kan ik aan de slag met apparaatbeheer in Basismobiliteit en Beveiliging?

Er zijn vier stappen om aan de slag te gaan met Basismobiliteit en Beveiliging: 

1. Activeer Basismobiliteit en beveiliging door naar de [Office 365 beveiligingsbeleid & compliance](https://protection.office.com/).

2. Ga naar Preventie van gegevensverlies > apparaatbeheer > Apparaatbeleid.
    
3. Maak apparaatbeheerbeleid en pas deze toe op groepen gebruikers die zijn ingesteld in beveiligingsgroepen. U wordt aangeraden het beleid te implementeren in een kleine testgroep. Zie Apparaatbeveiligingsbeleid maken [in Basismobiliteit en Beveiliging voor meer informatie.](create-device-security-policies.md)

4. Gebruikers die een beleid hebben toegepast op hen, worden gevraagd hun apparaten in te schrijven wanneer ze toegang proberen te krijgen tot Microsoft 365 gegevens. Zie Uw mobiele apparaat registreren met [basismobiliteit en beveiliging voor meer informatie.](enroll-your-mobile-device.md)

Zie Basismobiliteit en beveiliging instellen voor [meer informatie.](set-up.md)

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Ik probeer basismobiliteit en beveiliging in te stellen, maar het lijkt vast te zitten. De Microsoft 365 Service health wordt al een tijdje weergegeven met 'inrichting'. Wat kan ik doen?

Het kan enige tijd duren om de service voor u klaar te maken. Wanneer de inrichting is voltooid, ziet u de pagina Basismobiliteit en beveiliging. Als u 24 uur hebt gewacht en de status nog steeds wordt ingericht, neem dan contact op met ondersteuning en we helpen u erachter te komen wat het probleem is.

## <a name="what-can-i-do-if-device-enrollment-fails"></a>Wat kan ik doen als de registratie van apparaten mislukt?

Als u problemen hebt met het verkrijgen van een apparaat dat is geregistreerd, controleert u eerst het volgende:

- Zorg ervoor dat het apparaat nog niet is geregistreerd bij een andere provider voor mobiel apparaatbeheer, zoals Intune.

- Zorg ervoor dat het apparaat is ingesteld op de juiste datum en tijd.

- Schakel over naar een ander WIFI- of mobiel netwerk op het apparaat.

- Voor Android- of iOS-apparaten verwijdert en installeert u de Intune-bedrijfsportal app op het apparaat.
    
Zie Problemen met basismobiliteit en beveiliging oplossen als inschrijving nog steeds [niet werkt.](troubleshoot.md)

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Wat is het verschil tussen Intune en Basismobiliteit en Beveiliging?

Basismobiliteit en beveiliging wordt gehost door de Intune-service. Het is een subset van Intune-services die worden geleverd als een extra voordeel voor Microsoft 365 en is een ingebouwde cloudoplossing voor het beheren van apparaten in uw organisatie. Zie Kiezen tussen Basismobiliteitsbeveiliging en [Intune](choose-between-basic-mobility-and-security-and-intune.md)voor een vergelijking van de twee services naast elkaar om te bepalen of het gebruik van Intune of Basismobiliteit en beveiliging voor Microsoft 365 het beste bij u past.

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Hoe werken beleidsregels voor basismobiliteit en beveiliging? Hoe stel ik ze in? Uitschakelen?

Nadat u de eerste installatie voor Basismobiliteit en Beveiliging hebt voltooid, maakt u beleidsregels en kunt u deze toepassen op groepen gebruikers in het Beveiligings- & Compliancecentrum. Voor beleidsregels moeten gebruikers van het beleid hun apparaten registreren in Basismobiliteit en Beveiliging voordat het apparaat kan worden gebruikt om toegang te krijgen tot Microsoft 365 gegevens. Het beleid dat u in stelt, bepaalt de instellingen voor mobiele apparaten, bijvoorbeeld hoe vaak wachtwoorden opnieuw moeten worden ingesteld of of gegevensversleuteling vereist is. Zie Apparaatbeveiligingsbeleid maken [in Basismobiliteit](create-device-security-policies.md)en beveiliging en Microsoft 365   [compliancecentrum voor meer informatie.](../../compliance/microsoft-365-compliance-center.md)

Zie Apparaatbeveiligingsbeleid maken [in Basismobiliteit en Beveiliging](create-device-security-policies.md)voor stapsgewijse instructies voor het maken en implementeren van apparaatbeleid.

Als u wilt uitsluiten dat een bepaalde groep gebruikers wordt beïnvloed door beleid, kunt u een groep toevoegen aan de uitsluitingsgroep.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Kan ik overschakelen van Exchange ActiveSync apparaatbeheer naar Basismobiliteit en beveiliging voor Microsoft 365?

Als u al gebruik maakt van Exchange ActiveSync voor het beheren van mobiele apparaten, kunt u basismobiliteit en beveiliging gebruiken door de stappen voor het instellen van basismobiliteit en beveiliging uit te voeren. Zie Gebruikers- en apparaattoegang [beveiligen](../../compliance/protect-access-to-data-and-services.md) en [Basismobiliteit](set-up.md)en beveiliging instellen voor meer informatie.

Wanneer u het beleid dat u in Basismobiliteit en Beveiliging maakt, op groepen gebruikers gebruikt Exchange ActiveSync, worden met dit beleid beleidsregels voor postvakbeleid voor mobiele apparaten en regels voor apparaattoegang overgenomen die u eerder hebt gemaakt in het Exchange-beheercentrum voor deze gebruikers.

Nadat een apparaat is geregistreerd voor Basismobiliteit en beveiliging, wordt elke Exchange ActiveSync beleid voor postvak of apparaattoegangsregel voor mobiele apparaten die op het apparaat is toegepast, genegeerd.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Ik heb Basismobiliteit en Beveiliging ingesteld, maar nu wil ik deze verwijderen. Wat zijn de stappen?

Het is helaas niet mogelijk om basismobiliteit en beveiliging te 'onteigenen' nadat u deze hebt ingesteld. U kunt deze echter voor groepen gebruikers verwijderen door gebruikersbeveiligingsgroepen te verwijderen uit het apparaatbeleid dat u hebt gemaakt. U kunt het ook voor iedereen uitschakelen door het apparaatbeleid te verwijderen, zodat ze niet op hun plaats zijn en niet worden afgedwongen. Zie Basismobiliteit en beveiliging uitschakelen voor [meer informatie.](turn-off.md)