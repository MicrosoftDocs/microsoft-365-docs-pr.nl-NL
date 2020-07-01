---
title: Nieuwe Microsoft Edge
description: ''
keywords: browser, Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: d11fd8f29e3232472f9457ba1fc288a5084429e9
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936135"
---
# <a name="new-microsoft-edge-app"></a>Nieuwe Microsoft Edge-app

De nieuwe [Microsoft Edge-browser](https://www.microsoft.com/edge) biedt prestaties van wereldklasse met meer privacy, meer productiviteit en meer waarde terwijl u bladert. Microsoft Managed Desktop biedt een openbare preview van de implementatie van de nieuwe Edge-browser in uw omgeving.

## <a name="initial-deployment"></a>Eerste implementatie

Als u uw Microsoft Managed Desktop-apparaten wilt migreren naar de nieuwe Microsoft Edge-browser, dient u een IT-ondersteuningsticket in via de Microsoft Managed Desktop Portal. We implementeren het Edge Stable-kanaal naar de testgroep wanneer u het ticket indient en implementeren het vervolgens elke 24 uur in elke volgende implementatiegroep. Als u de implementatie wilt onderbreken, dient u een ander ticket in waarin operations wordt gevraagd deze vast te houden.

## <a name="updates-to-microsoft-edge"></a>Updates voor Microsoft Edge

Microsoft Managed Desktop implementeert het [stabiele kanaal](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) van Microsoft Edge, dat ongeveer elke zes weken automatisch wordt bijgewerkt. Updates op het Stable-kanaal worden [geleidelijk](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) uitgerold door de Microsoft Edge-productgroep om de beste ervaring voor klanten te garanderen. Het Microsoft Edge Beta-kanaal is momenteel niet beschikbaar.

Wijzig het [microsoft Edge-updatebeleid](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)niet om ervoor te zorgen dat Microsoft Edge-updates correct worden bijgewerkt.

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Instellingen beheerd door Microsoft Managed Desktop

Microsoft Managed Desktop heeft een standaardset beleidsregels gemaakt voor Microsoft Edge om de browser te beveiligen. De standaard browserinstellingen zijn als volgt:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge-extensies

Met de beveiligingsbasislijn voor Microsoft Edge op Microsoft Managed Desktop-apparaten worden twee beleidsregels ingesteld om alle Chrome-extensies uit te schakelen en eindgebruikers te beveiligen. Zie Instellingen die u beheert als u extensies in uw omgeving wilt inschakelen en implementeren. 

#### <a name="extension-installation-blocklist"></a>Blokkerlijst van extensie-installatie
**Standaardwaarde:** Alle

Microsoft Managed Desktop stelt dit beleid in om te voorkomen dat Chrome-extensies worden geïnstalleerd op beheerde eindpunten. Er zijn bekende risico's verbonden aan het Chromium-uitbreidingsmodel, waaronder bescherming tegen gegevensverlies, privacy en andere risico's die apparaten in gevaar kunnen brengen. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Native messaging-hosts op gebruikersniveau toestaan (geïnstalleerd zonder beheerdersmachtigingen)

**Standaardwaarde:** Handicap

Door dit beleid uit te schakelen, gebruikt Microsoft Edge alleen native messaging-hosts die op systeemniveau zijn geïnstalleerd. Native messaging hosts zijn een onderdeel van Chrome-extensies waarmee de browser kan communiceren met andere delen van het eindpunt van de gebruiker, waardoor een verscheidenheid aan beveiligingsproblemen ontstaat.  

### <a name="secure-sockets-layer-ssl"></a>Secure Sockets Layer (SSL)

#### <a name="minimum-ssl-version"></a>Minimale SSL-versie

**Standaardwaarde:** Minimaal TLS 1.2 ondersteund

Als u de minder veilige TLS 1.1 wilt gebruiken, u dit aanvragen.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Hiermee kunnen gebruikers verder gaan vanaf de SSL-waarschuwingspagina

**Standaardwaarde:** Handicap

We raden u af deze instelling in te schakelen, omdat gebruikers hiermee sites met SSL-fouten kunnen bezoeken.

### <a name="microsoft-defender-smart-screen"></a>Microsoft Defender-slim scherm

#### <a name="configure-microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen configureren

**Standaardwaarde:** Ingeschakeld

Standaard ingeschakeld om eindgebruikers te beschermen.

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a>Microsoft Defender SmartScreen vraagt naar sites

**Standaardwaarde:** Ingeschakeld

We raden u af deze instelling uit te schakelen, omdat gebruikers hierdoor waarschuwingen kunnen negeren en mogelijk mogelijk schadelijke sites kunnen blijven gebruiken.

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a>Voorkomen dat microsoft Defender SmartScreen-waarschuwingen over downloads worden omzeild

**Standaardwaarde:** Ingeschakeld

We raden u af deze instelling uit te schakelen, omdat gebruikers hierdoor waarschuwingen kunnen negeren en niet-geverifieerde downloads kunnen voltooien.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Standaardinstelling voor Adobe Flash

**Standaardwaarde:** Handicap

We raden het gebruik van Flash af vanwege de bijbehorende beveiligingsrisico's. Als u nog steeds processen hebt die afhankelijk zijn van Flash, stelt u het beleid **[Voorforurls voor Plug-in](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** ingesteld om Flash in te schakelen voor sites die dit nodig hebben. Als een toegestane lijst met sites niet kan worden onderhouden om Flash te gebruiken, dient u een wijzigingsverzoek in om de waarde te wijzigen in **Klik om af te spelen,** waarmee gebruikers kunnen kiezen wanneer het nodig is om Flash uit te voeren.

### <a name="password-manager"></a>Wachtwoordmanager

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Wachtwoorden opslaan inschakelen voor de wachtwoordmanager

**Standaardwaarde:** Handicap

We raden eindgebruikers af om wachtwoorden op hun apparaat op te slaan.

### <a name="other-settings"></a>Andere instellingen

#### <a name="enable-site-isolation-for-every-site"></a>Site-isolatie inschakelen voor elke site

**Standaardwaarde:** Ingeschakeld

Wanneer dit beleid is ingeschakeld, kunnen gebruikers zich niet afmelden voor het standaardgedrag waarin elke site in zijn eigen proces wordt uitgevoerd.

#### <a name="supported-authentication-schemes"></a>Ondersteunde verificatieschema's

**Standaardwaarde:** NTLM, Onderhandelen

Microsoft Managed Desktop biedt geen ondersteuning voor basis- of digestverificatieschema's.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>De gegevens en instellingen van een andere browser automatisch importeren bij de eerste run

**Standaardwaarde:** Alle ondersteunde gegevenstypen en -instellingen automatisch importeren vanuit de standaardbrowser 

Met dit beleid toegepast, slaat de first run experience de sectie importeren over, waardoor de interactie van de gebruiker wordt geminimaliseerd. De browsergegevens van oudere versies van Microsoft Edge worden altijd geruisloos gemigreerd bij de eerste uitvoering, ongeacht deze instelling. 


## <a name="settings-you-manage"></a>Instellingen die u beheert

U alle Microsft Edge-instellingen implementeren die niet eerder zijn beschreven met het profiel Beheerderssjablonen in Microsoft Intune. Zie Microsoft [Edge-beleidsinstellingen configureren met Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)voor meer informatie. Als u een beleid wilt evalueren dat momenteel niet is opgenomen in de beheersjablonen van Microsoft Edge in Intune, u aangepaste instellingen gebruiken voor Windows 10-apparaten in Intune.

### <a name="enabling-specific-chrome-extensions"></a>Specifieke Chrome-extensies inschakelen

De beheersjabloon biedt een instelling voor het implementeren van bepaalde Chrome-extensies met Microsoft Intune. U het vinden in **Computer configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.

### <a name="install-extensions-silently"></a>Extensies in stilte installeren

U de beheersjabloon ook gebruiken om Microsoft Edge in te stellen extensies te installeren zonder de gebruiker te waarschuwen. U het vinden in **Computer Configuration > Microsoft Edge > Extensions > Control welke extensies in stilte zijn geïnstalleerd.**

### <a name="other-common-enterprise-policies"></a>Ander gemeenschappelijk ondernemingsbeleid

Microsoft Edge biedt een groot aantal aanvullende beleidsregels. Dit zijn enkele van de meest voorkomende:
 
- [Sites configureren in de enterprise-sitelijst en de IE-modus](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Start-up, startpagina en nieuwe tabpagina-instellingen configureren](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Surfgame-instelling configureren](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Proxyserverinstellingen configureren](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

