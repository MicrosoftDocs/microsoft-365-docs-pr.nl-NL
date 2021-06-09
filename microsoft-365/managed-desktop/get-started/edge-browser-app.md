---
title: Nieuwe Microsoft Edge-apps
description: Hier wordt uitgelegd hoe de nieuwe Edge-browser wordt geïmplementeerd en bijgewerkt
keywords: browser, Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2bf1fab504ae77a1e66235f49333c3b123e38904
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822248"
---
# <a name="new-microsoft-edge-app"></a>Nieuwe Microsoft Edge app

De nieuwe [Microsoft Edge biedt](https://www.microsoft.com/edge) prestaties van wereldklasse met meer privacy, meer productiviteit en meer waarde terwijl u bladert. Microsoft Managed Desktop biedt een openbare preview van de implementatie van de nieuwe Edge-browser in uw omgeving.

## <a name="initial-deployment"></a>Eerste implementatie

Als u uw Microsoft Managed Desktop wilt migreren naar de nieuwe Microsoft Edge browser, kunt u een IT-ondersteuningsticket indienen via de Microsoft Managed Desktop Portal. We implementeren het Edge Stable-kanaal naar de testgroep wanneer u het ticket intoetst en implementeren het vervolgens elke 24 uur in elke volgende implementatiegroep. Als u de implementatie wilt onderbreken, moet u een ander ticket indienen waarin Operations wordt gevraagd de implementatie te onderbreken.

Het [bètakanaal](/deployedge/microsoft-edge-channels#beta-channel) is ook beschikbaar op aanvraag voor representatieve validatie binnen uw organisatie. Microsoft Managed Desktop de toepassing implementeren zoals vereist voor de test- en eerste groepen, zodat al deze gebruikers het bètakanaal hebben naast het stabiele kanaal. Voor alle andere gebruikers die toegang nodig hebben tot het bètakanaal, voegt u deze toe aan de groep Moderne werkplek **- Edge Beta-gebruikers** en laten ze het installeren vanaf de Bedrijfsportal

## <a name="updates-to-microsoft-edge"></a>Updates voor Microsoft Edge

Microsoft Managed Desktop implementeert het [Stabiele kanaal](/deployedge/microsoft-edge-channels#stable-channel) van Microsoft Edge, dat ongeveer om de zes weken automatisch wordt bijgewerkt. Updates voor het Stable-kanaal worden geleidelijk door de Microsoft Edge productgroep uitgerold om de beste ervaring voor klanten te garanderen. [](/deployedge/microsoft-edge-update-progressive-rollout) 

Het [bètakanaal](/deployedge/microsoft-edge-channels#beta-channel) wordt geïmplementeerd op apparaten in zowel de groepen Test als First voor representatieve validatie binnen de organisatie. Dit kanaal wordt volledig ondersteund en wordt ongeveer om de zes weken automatisch bijgewerkt met nieuwe functies.

Als u ervoor wilt zorgen Microsoft Edge updates correct worden bijgewerkt, wijzigt u het beleid voor Microsoft Edge [bijwerken niet.](/deployedge/microsoft-edge-update-policies)



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Instellingen beheerd door Microsoft Managed Desktop

Microsoft Managed Desktop heeft een standaardset beleid gemaakt voor Microsoft Edge browser te beveiligen. De standaardbrowserinstellingen zijn als volgt:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge extensies

De beveiligingslijn voor Microsoft Edge op Microsoft Managed Desktop apparaten stelt twee beleidsregels in om alle Chrome-extensies uit te schakelen en gebruikers te beveiligen. Als u extensies in uw omgeving wilt in- en implementeren, Instellingen u beheert. 

#### <a name="extension-installation-blocklist"></a>Uitbreidingsinstallatieblokkering
**Standaardwaarde:** Alles

Microsoft Managed Desktop wordt dit beleid ingesteld om te voorkomen dat Chrome-extensies worden geïnstalleerd op beheerde eindpunten. Er zijn bekende risico's verbonden aan Chromium uitbreidingsmodel, waaronder bescherming tegen gegevensverlies, privacy en andere risico's die apparaten kunnen compromitteerden. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Native messaging-hosts op gebruikersniveau toestaan (geïnstalleerd zonder beheerdersmachtigingen)

**Standaardwaarde:** Uitgeschakeld

Door dit beleid uit te Microsoft Edge gebruikt u alleen native messaging-hosts die zijn geïnstalleerd op systeemniveau. Native messaging-hosts maken deel uit van Chrome-extensies, waardoor de browser kan communiceren met andere delen van het eindpunt van de gebruiker, waardoor er diverse beveiligingsproblemen worden aan de dag komen.  

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

#### <a name="minimum-tls-version"></a>Minimale TLS-versie

**Standaardwaarde:** Minimaal TLS 1.2 ondersteund

Als u de minder veilige TLS 1.1 wilt gebruiken, kunt u een aanvraag indienen om dit te doen.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Hiermee kunnen gebruikers verdergaan vanaf de SSL-waarschuwingspagina

**Standaardwaarde:** Uitgeschakeld

U wordt niet aangeraden deze instelling in te stellen, omdat gebruikers hiermee sites kunnen bezoeken met TSL-fouten.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>SmartScreen Windows Defender configureren

**Standaardwaarde:** Ingeschakeld

Standaard ingeschakeld om gebruikers te beschermen.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender SmartScreen-prompts voor sites

**Standaardwaarde:** Ingeschakeld

Het is niet raadzaam deze instelling uit te zetten, omdat gebruikers hierdoor waarschuwingen kunnen negeren en mogelijk schadelijke sites kunnen blijven gebruiken.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Voorkomen dat waarschuwingen Windows Defender SmartScreen worden overgeslagen

**Standaardwaarde:** Ingeschakeld

We raden u af deze instelling uit te zetten, omdat gebruikers dan waarschuwingen kunnen negeren en niet-geverifieerde downloads kunnen voltooien.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Standaardinstelling voor Adobe Flash

**Standaardwaarde:** Uitgeschakeld

U wordt niet aangeraden Flash te gebruiken vanwege de bijbehorende beveiligingsrisico's. Als u nog steeds processen hebt die afhankelijk zijn van Flash, stelt u het beleid **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** in om Flash in te stellen voor sites die dit nodig hebben. Als u een toegestane lijst met sites niet kunt behouden om Flash te gebruiken, kunt u een wijzigingsaanvraag indienen om de waarde te wijzigen in Klik om af te **spelen,** zodat gebruikers kunnen kiezen wanneer flash moet worden uitgevoerd.

### <a name="password-manager"></a>Wachtwoordbeheer

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Wachtwoorden opslaan inschakelen voor wachtwoordbeheer

**Standaardwaarde:** Uitgeschakeld

De wachtwoordmanager is standaard uitgeschakeld. Als u deze functie hebt ingeschakeld, kunt u een ondersteuningsaanvraag indienen en kunnen onze servicetechnici de instelling in uw omgeving inschakelen. 

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer-modus in Microsoft Edge
Met de IE-Microsoft Edge kunt u eenvoudig alle sites die uw organisatie nodig heeft in één browser gebruiken. De engine maakt gebruik van de geïntegreerde Chromium-engine voor sites die compatibel zijn met de Chromium-rendering engine en gebruikt de Trident MSHTML-engine van Internet Explorer 11 (IE11) voor sites die niet afhankelijk zijn van IE-functionaliteit of die niet afhankelijk zijn van IE-functionaliteit. [Meer informatie](/DeployEdge/edge-ie-mode) 

Microsoft Managed Desktop internet explorer-modus standaard inschakelen voor uw apparaten 

#### <a name="internet-explorer-mode-integration"></a>Integratie van de Internet Explorer-modus
**Standaardwaarde:** Internet Explorer-modus

Apparaten zijn standaard ingesteld op de Internet Explorer-modus, maar u kunt instellen dat ze sites openen in een zelfstandig Internet Explorer 11-venster. Als u dit gedrag wilt wijzigen, moet u een ondersteuningsaanvraag indienen.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Sites toevoegen aan de sitelijst ondernemingsmodus
Als u sites wilt openen in de Internet Explorer-modus, moet u ze opnemen in de [lijst Ondernemingssite.](/DeployEdge/edge-ie-mode-sitelist) Het onderhouden en implementeren van de lijst ondernemingssite is uw verantwoordelijkheid. Zie Configure using the Configure Enterprise Mode Site List policy (Configureren [ondernemingsmodus sitelijstbeleid configureren) voor meer informatie.](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Andere instellingen

#### <a name="enable-site-isolation-for-every-site"></a>Siteisolatie voor elke site inschakelen

**Standaardwaarde:** Ingeschakeld

Wanneer dit beleid is ingeschakeld, kunnen gebruikers zich niet afkeerd van het standaardgedrag waarin elke site in een eigen proces wordt uitgevoerd.

#### <a name="supported-authentication-schemes"></a>Ondersteunde verificatieschema's

**Standaardwaarde:** NTLM, Onderhandelen

Microsoft Managed Desktop biedt geen ondersteuning voor basis- of digestverificatieschema's.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Gegevens en instellingen van een andere browser automatisch importeren bij de eerste run

**Standaardwaarde:** Alle ondersteunde gegevenstypen en instellingen automatisch importeren vanuit de standaardbrowser 

Wanneer dit beleid is toegepast, wordt de sectie Eerste keer uitvoeren overgeslagen in de importsectie, waardoor de interactie van de gebruiker wordt geminimporteert. De browsergegevens van oudere versies van Microsoft Edge worden altijd gemigreerd bij de eerste uitvoering, ongeacht deze instelling. 


## <a name="settings-you-manage"></a>Instellingen beheren

U kunt alle instellingen Microsoft Edge die niet eerder zijn beschreven, implementeren met behulp van het profiel Beheersjablonen in Microsoft Intune. Zie De beleidsinstellingen [Microsoft Edge configureren met Microsoft Intune.](/deployedge/configure-edge-with-intune) Als u een beleid wilt evalueren dat momenteel niet is opgenomen in de Microsoft Edge-beheersjablonen in Intune, kunt u aangepaste instellingen gebruiken voor Windows 10 apparaten in Intune.

### <a name="enabling-specific-chrome-extensions"></a>Specifieke Chrome-extensies inschakelen

De beheerssjabloon biedt een instelling voor het implementeren van bepaalde Chrome-extensies met Microsoft Intune. U vindt deze in **Computerconfiguratie > Microsoft Edge > extensies > Toestaan dat specifieke extensies worden geïnstalleerd.**

### <a name="install-extensions-silently"></a>Extensies in stilte installeren

U kunt ook de beheerssjabloon gebruiken om extensies Microsoft Edge te installeren zonder de gebruiker te waarschuwen. U vindt deze in **Computerconfiguratie > Microsoft Edge > Extensies > Besturingselement** welke extensies in stilte worden geïnstalleerd.

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge updatebeleid
Als u ervoor wilt zorgen Microsoft Edge updates correct worden bijgewerkt, wijzigt u het beleid voor Microsoft Edge [bijwerken niet.](/deployedge/microsoft-edge-update-policies)

### <a name="other-common-enterprise-policies"></a>Andere algemene ondernemingsbeleidsregels

Microsoft Edge biedt een groot aantal andere beleidsregels. Dit zijn enkele van de meest voorkomende:
 
- [Sites configureren op de lijst met ondernemingssites en de IE-modus](/deployedge/edge-ie-mode-sitelist)
- [Instellingen voor start-up, startpagina en nieuwe tabbladpagina configureren](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Surf game-instelling configureren](/deployedge/microsoft-edge-policies#allowsurfgame)
- [Instellingen voor proxyserver configureren](/deployedge/microsoft-edge-policies#proxy-server)
