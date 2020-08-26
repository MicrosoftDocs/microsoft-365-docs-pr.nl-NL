---
title: Nieuwe Microsoft Edge-apps
description: ''
keywords: browser, Microsoft beheerde desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 089d9dc79da568a43c1d5701d7bc52d9bed0f4f5
ms.sourcegitcommit: c76c025fe75cd9c06eccbf9c7fc887b09da36659
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/26/2020
ms.locfileid: "46903869"
---
# <a name="new-microsoft-edge-app"></a>Nieuwe Microsoft Edge-app

De nieuwe [browser Microsoft Edge](https://www.microsoft.com/edge) biedt wereldwijde prestaties met meer privacy, meer productiviteit en meer tijdens het browsen. Microsoft Managed Desktop biedt een openbare preview van de implementatie van de nieuwe Edge-browser in uw omgeving.

## <a name="initial-deployment"></a>Eerste implementatie

Als u uw Microsoft Managed Desktop-apparaten wilt migreren naar de nieuwe Microsoft Edge-browser, kunt u een IT-ondersteunings ticket via de beheerde bureaublad portal van Microsoft opslaan. We implementeren de Edge stabiel kanaal naar de test groep wanneer u het ticket bijwerkt en het vervolgens in elke volgende implementatiegroep elke 24 uur implementeren. Als u de implementatie wilt onderbreken, moet u een ander ticket vragen om te worden bewaard.

Het [bèta kanaal](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is ook beschikbaar wanneer u daarom aanvraag onderneemt voor een representatieve validering binnen uw organisatie. Microsoft Managed Desktop implementeert de toepassing als vereist voor de test en de eerste groepen, zodat al deze gebruikers het bèta-kanaal hebben, naast het stabiele kanaal. Voor alle extra gebruikers die toegang hebben tot het bèta kanaal, voegt u ze toe aan de groep van de **moderne gebruikers van de werkplek** en kunnen ze deze installeren via de bedrijfs portal.

## <a name="updates-to-microsoft-edge"></a>Updates voor Microsoft Edge

Microsoft Managed Desktop implementeert het [stabiele kanaal](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) van Microsoft Edge die elke zes weken automatisch wordt bijgewerkt. Updates op het stabiele kanaal worden [progressief](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) uitgeworpen door de productgroep Microsoft Edge om ervoor te zorgen dat ze de beste ervaring voor klanten zijn. 

Het [bèta kanaal](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) wordt geïmplementeerd op apparaten in zowel de test als de eerste groepen voor de representatieve validatie binnen de organisatie. Dit kanaal wordt volledig ondersteund en wordt telkens zes weken automatisch bijgewerkt met nieuwe functies.

U kunt ervoor zorgen dat Microsoft Edge correct wordt bijgewerkt door de [Update beleidsregels](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)voor Microsoft Edge niet te wijzigen.

### <a name="microsoft-edge-beta-channel"></a>Microsoft Edge bèta-kanaal


## <a name="settings-managed-by-microsoft-managed-desktop"></a>Instellingen die worden beheerd door Microsoft Managed Desktop

Microsoft Managed Desktop heeft een standaardreeks beleidsregels voor Microsoft Edge gemaakt om de browser te beveiligen. De instellingen voor standaardbrowser zijn als volgt:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge-extensies

Met de beveiligings basis voor Microsoft Edge on Microsoft Managed Desktop devices stelt u twee beleidsregels in om alle Chrome-extensies en veilige eindgebruikers uit te schakelen. Als u extensies wilt inschakelen en implementeren in uw omgeving, raadpleegt u instellingen die u beheert. 

#### <a name="extension-installation-blocklist"></a>Extensies installeren blokkeringslijst geplaatst
**Standaardwaarde:** Al

Microsoft Managed Desktop stelt dit beleid in om te voorkomen dat chroom extensies worden geïnstalleerd op beheerde eindpunten. Er zijn bekende Risico's die zijn gekoppeld aan het Chroom-uitbreidings model, waaronder beveiliging tegen bescherming van gegevensverlies, privacy en andere Risico's waarmee apparaten kunnen worden aangetast. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Native berichten hosten op gebruikersniveau toestaan (geïnstalleerd zonder beheerdersmachtigingen)

**Standaardwaarde:** Uitgeschakeld

Door dit beleid uit te schakelen, wordt Microsoft Edge alleen gebruikt voor de native Messaging-hosts die op systeemniveau zijn geïnstalleerd. Hosts voor systeemeigen berichten maken deel uit van chroom extensies waarmee de browser kan communiceren met andere onderdelen van het eindpunt van gebruikers, en maakt diverse beveiligingskwesties.  

### <a name="secure-sockets-layer-ssl"></a>Secure Sockets Layer (SSL)

#### <a name="minimum-ssl-version"></a>Minimale SSL-versie

**Standaardwaarde:** Minimale TLS-1,2 ondersteund

Als u het minder veilige TLS 1,1 wilt gebruiken, kunt u dit aanvragen.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Gebruikers kunnen doorgaan op de pagina SSL-waarschuwing

**Standaardwaarde:** Uitgeschakeld

We raden u aan deze instelling niet in te schakelen omdat gebruikers sites kunnen bezoeken met een SSL-fout.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Windows Defender SmartScreen configureren

**Standaardwaarde:** Enabled

Standaard ingeschakeld om eindgebruikers te helpen beschermen.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender SmartScreen vraagt voor sites

**Standaardwaarde:** Enabled

U wordt aangeraden deze instelling uit te schakelen omdat gebruikers waarschuwingen negeren en doorgaan naar potentieel schadelijke sites.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Negeering van Windows Defender SmartScreen-waarschuwingen over downloads voorkomen

**Standaardwaarde:** Enabled

U wordt aangeraden deze instelling uit te schakelen omdat gebruikers waarschuwingen negeren en niet-geverifieerde downloads voltooien.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Standaardinstelling voor Adobe Flash

**Standaardwaarde:** Uitgeschakeld

We raden u niet aan gebruik te maken van Flash vanwege bijbehorende beveiligingsrisico's. Als u nog steeds processen hebt die van Flash variëren, stelt u het **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** -beleid in om Flash voor sites in te schakelen. Als u een toegestane lijst met sites niet kunt bewaren voor gebruik van Flash, moet u een wijzigingsaanvraag indienen om de waarde te wijzigen om **te worden afgespeeld**, zodat gebruikers kunnen kiezen wanneer deze nodig zijn om Flash uit te voeren.

### <a name="password-manager"></a>Wachtwoordbeheer

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Het opslaan van wachtwoorden naar wachtwoordbeheer inschakelen

**Standaardwaarde:** Uitgeschakeld

U wordt aangeraden eindgebruikers niet in staat te stellen om wachtwoorden op hun apparaat op te slaan.

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer-modus in Microsoft Edge
Met de IE-modus op Microsoft Edge kunt u eenvoudig gebruikmaken van alle sites die uw organisatie nodig heeft in één browser. Met de geïntegreerde toepassing van chroom voor sites die compatibel zijn met de chroom beeldrendering-engine, wordt de Trident MSHTML-engine van Internet Explorer 11 (IE11) gebruikt voor sites die geen of geen afhankelijkheden hebben van de IE-functionaliteit. [Meer informatie] (https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

Microsoft Managed Desktop schakelt standaard de Internet Explorer-modus voor uw apparaten in 

#### <a name="internet-explorer-mode-integration"></a>Integratie van de Internet Explorer-modus
**Standaardwaarde:** De modus Internet Explorer

Apparaten zijn standaard ingesteld op de modus Internet Explorer, maar u kunt ze instellen voor het openen van sites in een zelfstandig, Internet Explorer 11-venster. Als u dit wilt wijzigen, moet u een ondersteuningsaanvraag indienen.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Sites toevoegen aan de site lijst van de ondernemingsmodus
Voor sites die u wilt openen in de Internet Explorer-modus, moet u deze opnemen in de [lijst met bedrijfssites](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist). Het onderhoud en de implementatie van de ondernemings site lijst is uw eigen verantwoordelijkheid. Voor meer informatie raadpleegt u [configureren met behulp van het site lijstbeleid Enterprise mode configureren](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Andere instellingen

#### <a name="enable-site-isolation-for-every-site"></a>Site-isolatie inschakelen voor elke site

**Standaardwaarde:** Enabled

Wanneer dit beleid is ingeschakeld, kunnen gebruikers niet deelnemen aan het standaardgedrag waarbij de afzonderlijke sites in een eigen proces worden uitgevoerd.

#### <a name="supported-authentication-schemes"></a>Ondersteunde verificatieschema's

**Standaardwaarde:** NTLM, Negotiate

Microsoft Managed Desktop biedt geen ondersteuning voor basisverificatie en verificatieschema's.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>De gegevens en instellingen van een andere browser automatisch importeren bij de eerste uitvoering

**Standaardwaarde:** Automatisch alle ondersteunde gegevenstypen en instellingen in de standaardbrowser importeren 

Met deze beleidsinstelling wordt de eerste uitvoering van de ervaring overgeslagen en wordt de functie voor het importeren van de gebruikersinteractie overgeslagen. De browser gegevens uit oudere versies van Microsoft Edge worden altijd Silent gemigreerd naar de eerste sessie, ongeacht deze instelling. 


## <a name="settings-you-manage"></a>Instellingen die u beheert

U kunt alle instellingen voor Microsoft Edge die niet eerder zijn beschreven, implementeren met behulp van het Profielbeheer sjablonen in Microsoft intune. Zie [Microsoft Edge-beleidsinstellingen met Microsoft intune configureren](https://docs.microsoft.com/deployedge/configure-edge-with-intune)voor meer informatie. Als u een beleid wilt beoordelen dat nog niet is opgenomen in de beheersjablonen van Microsoft Edge in intune, kunt u aangepaste instellingen voor Windows 10-apparaten gebruiken in intune.

### <a name="enabling-specific-chrome-extensions"></a>Specifieke Chrome-extensies inschakelen

De sjabloon beheerder biedt een instelling voor het implementeren van bepaalde Chrome-uitbreidingen met Microsoft intune. U vindt het bestand in **computer configuratie > Microsoft Edge > extensies > de mogelijkheid om bepaalde extensies te installeren**.

### <a name="install-extensions-silently"></a>Extensies op de achtergrond installeren

U kunt ook de beheersjabloon gebruiken om Microsoft Edge te installeren om uitbreidingen te installeren zonder dat u een melding krijgt van de gebruiker. U vindt het bestand in **computer configuratie > Microsoft Edge > extensies > bepalen welke extensies op de achtergrond worden geïnstalleerd**.

### <a name="microsoft-edge-update-policies"></a>Updatebeleid voor Microsoft Edge
U kunt ervoor zorgen dat Microsoft Edge correct wordt bijgewerkt door de [Update beleidsregels](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)voor Microsoft Edge niet te wijzigen.

### <a name="other-common-enterprise-policies"></a>Overig algemeen ondernemingsbeleid

Microsoft Edge biedt een groot aantal extra beleidsregels. Dit zijn enkele van de meest voorkomende versies:
 
- [Sites configureren in de lijst met ondernemings sites en de IE-modus](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Instellingen voor opstarten, startpagina en nieuw tabblad configureren](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Instellingen voor een surf spel configureren](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Instellingen voor proxyserver configureren](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

