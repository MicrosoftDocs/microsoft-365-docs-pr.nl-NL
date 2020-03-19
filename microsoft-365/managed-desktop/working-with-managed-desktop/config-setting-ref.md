---
title: Configureerbare instellingen referentie voor Microsoft Managed Desktop
description: Categorieën instellen voor configureerbare instellingen in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9a405f96ee7a113197fbc9c237779db3e3e5e5ca
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806291"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Verwijzing naar configureerbare instellingen - Microsoft Managed Desktop

In dit onderwerp worden de instellingencategorieën weergegeven die klanten kunnen configureren met Microsoft Managed Desktop. Elke instellingscategorie bevat informatie over vereisten, aanbevolen procedures en hoe u de instellingscategorie aanpassen. 

## <a name="desktop-background-picture"></a>Bureaubladachtergrondafbeelding
U de bureaubladachtergrondafbeelding aanpassen voor Microsoft Managed Desktop-apparaten in uw organisatie. U dit gebruiken om een bedrijfsmerk of marketingmateriaal toe te passen. 

### <a name="requirements"></a>Vereisten

Aan deze vereisten moet worden voldaan voor een bureaubladachtergrondafbeelding:
- Afbeeldingsbestandsindeling - .jpg, jpeg of .png
- Bestandslocatie - Host op een vertrouwde beveiligde http (https)-locatie. 
- Niet toegestaan - Http- en bestandsshare (unc)-locaties worden niet ondersteund. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Bureaubladachtergrondafbeelding aanpassen en implementeren

**Een aangepaste bureaubladachtergrondafbeelding toevoegen**
1. Aanmelden bij [de portal Beheerde Desktopbeheerder](https://aka.ms/mwaasportal) van Microsoft
2. Selecteer onder **Instellingen**de optie **Configureerbaar**.
3. Selecteer in **Configureerbare** werkruimte de optie **Bureaubladachtergrondafbeelding**. 
4. Voer de locatie in van de afbeelding die u wilt gebruiken. 
5. Selecteer **Faseimplementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen. 

## <a name="browser-start-pages"></a>Startpagina's voor browser
Browserstartpagina's worden geopend in afzonderlijke tabbladen wanneer uw gebruikers Microsoft Edge starten. Als u het uw gebruikers gemakkelijk wilt maken om een reeks sites te openen die ze vaak gebruiken, voegt u voor elke site een startpagina van de browser toe. 

### <a name="requirements"></a>Vereisten

U moet de volledig gekwalificeerde domeinnaam (FQDN) opgeven voor intranet- of internetsites voor uw browserstartpagina's. Als interne sites zijn geconfigureerd, laat gebruikers dan weten dat toegang tot deze sites alleen is toegestaan wanneer deze is verbonden met het interne netwerk wanneer ze op kantoor zijn, of wanneer ze zijn verbonden met een VPN-verbinding. 

### <a name="customize-and-deploy-browser-start-pages"></a>Startpagina's voor het browseraanpassen en implementeren

**Een startpagina van de browser toevoegen**
1. Aanmelden bij [de portal Beheerde Desktopbeheerder](https://aka.ms/mwaasportal) van Microsoft
2. Selecteer onder **Instellingen**de optie **Configureerbaar**.
3. Selecteer in **Configureerbare** werkruimte de optie **Beginpagina's van browser**. 
4. Selecteer **Beginpagina toevoegen**.
5. Voer op **de startpagina van**de browser toevoegen de URL in voor de site die u wilt gebruiken en selecteer vervolgens **Beginpagina toevoegen**. 
6. Herhaal stap 1-5 voor extra startpagina's van de browser. 
7. Selecteer **Faseimplementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.

## <a name="enterprise-mode-site-list-location"></a>Locatie van de sitelijst in bedrijfsmodus

Als u specifieke websites en apps hebt waarvan u weet dat deze compatibiliteitsproblemen hebben met Microsoft Edge, u de sitelijst met ondernemingsmodus gebruiken, zodat de websites automatisch worden geopend met Internet Explorer 11. Als u weet dat uw intranetsites niet correct werken met Microsoft Edge, u alle intranetsites instellen om automatisch te openen met Internet Explorer 11. Het gebruik van de Bedrijfsmodus betekent dat u Microsoft Edge als standaardbrowser blijven gebruiken, terwijl u er ook voor zorgt dat uw apps blijven werken op Internet Explorer 11. Zie [Ondernemingsmodus- en Enterprise Mode-sitelijsten](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)voor meer informatie over de sitelijsten van bedrijfsmodus.For more information on enterprise mode site lists,see Enterprise Mode and Enterprise Mode Site Lists . 

U een https:// locatie opgeven of de locatie voor een intern aandeel waar u de sitelijst met bedrijfsmodus hebt gehost. 

### <a name="requirements"></a>Vereisten

Aan deze vereisten moet worden voldaan voor het lijstbestand voor bedrijfsmodussite:
- Bestandsindeling - XML-bestand dat voldoet aan [bestandsvereisten](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Bestandslocatie - Hostbestand op een interne https-locatie. 
- Niet toegestaan - Hosting op een intern bestandsaandeel, zoals */sharename,* is niet toegestaan

### <a name="best-practices"></a>Aanbevolen procedures

Deze best practices worden aangeboden om klanten te helpen beslissingen te nemen om hun IT-infrastructuur te moderniseren:
- **Kies een beperkt aantal sites** : Microsoft Managed Desktop gebruikt Microsoft Edge als de voorkeursbrowser om de algehele beveiliging voor uw organisatie en bruikbaarheid voor uw gebruikers te verbeteren. De meeste sites in deze lijst zijn voor oudere web-apps die een oudere versie van een browser die niet zo veel beveiligingsfuncties zal bevatten nodig. 
- **Overweeg een alternatieve** - Overweeg een andere site of web-app waarvoor geen oudere browser nodig is. Of overweeg de site bij te werken, zodat deze nieuwere browsers kan gebruiken. Nieuwere browsers maken gebruik van de nieuwste technologie en helpen de beveiliging te verbeteren.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Lijstlocatie bedrijfssitemodus aanpassen en implementeren

**Een lijstlocatie voor de bedrijfssitemodus toevoegen**

1.  Aanmelden bij [de portal Beheerde Desktopbeheerder](https://aka.ms/mwaasportal) van Microsoft
2.  Selecteer onder **Instellingen**de optie **Configureerbaar**.
3.  Selecteer in **Configureerbare** werkruimte de locatie van de sitelijst in **de ondernemingsmodus**. 
4.  Voer de https-locatie voor uw sitelijst in. 
5.  Selecteer **Faseimplementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.

## <a name="trusted-sites"></a>Vertrouwde sites

Met vertrouwde sites u beveiligingszones aanpassen of waar een site kan worden gebruikt voor verschillende sites. Veiligheidszones zijn onder andere: 
- Zone 1 – Lokale intranetzone
- Zone 2 – Zone 2 – Vertrouwde siteszone
- Zone 3 – Internetzone
- Zone 4 – Zone 4 – Zone beperkte sites

### <a name="requirements"></a>Vereisten

Geef de volledig gekwalificeerde domeinnaam (FQDN) op voor intranet- of internetsites voor elke vertrouwde site. 

### <a name="customize-and-deploy-trusted-sites"></a>Vertrouwde sites aanpassen en implementeren

**Een vertrouwde site toevoegen**

1. Aanmelden bij [de portal Beheerde Desktopbeheerder](https://aka.ms/mwaasportal) van Microsoft
2. Selecteer onder **Instellingen**de optie **Configureerbaar**.
3. Selecteer in **configureerbare** werkruimte **Vertrouwde sites**en selecteer vervolgens Vertrouwde **site toevoegen**. 
4. Voer op **Vertrouwde site toevoegen**de URL in, kies een beveiligingszone en selecteer vervolgens Vertrouwde site **toevoegen**. 
5. Herhaal stap 1-4 voor elke vertrouwde site die u wilt toevoegen. 
6. Selecteer **Faseimplementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.

**Een vertrouwde site verwijderen**

1. Aanmelden bij [de portal Beheerde Desktopbeheerder](https://aka.ms/mwaasportal) van Microsoft
2. Selecteer onder **Instellingen**de optie **Configureerbaar**.
3. Selecteer in **Configureerbare** werkruimte **Vertrouwde sites**. 
4. Selecteer de site die u wilt verwijderen en selecteer **Verwijderen.** 
5. Herhaal stap 1-4 voor elke vertrouwde site die u wilt verwijderen. 
6. Selecteer **Faseimplementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.

## <a name="proxy"></a>Proxy
U de instellingen voor netwerkproxy's voor uw organisatie beheren. Voeg uw proxyserver en poortnummer toe en voeg vervolgens uitzonderingen op de proxysite toe. Microsoft Managed Desktop bevat een set standaardproxyuitzonderingen die vereist zijn om de service te laten werken. De standaarduitsluitingslijst mag alleen worden gewijzigd door de Microsoft Managed Desktop-service.  Zie [Netwerkconfiguratie voor Microsoft Managed Desktop voor](../get-ready/network.md)meer informatie. 

De uitzonderingen op proxysite's die u toevoegt in de Microsoft Managed Desktop-portal worden toegevoegd aan de standaardproxyuitzonderingen die zijn opgenomen in de Microsoft Managed Desktop-service. 

> [!NOTE]
> Het bijwerken van de standaardlijst proxy-uitzondering wordt altijd geprioriteerd boven implementaties van klanten. Dit betekent dat uw gefaseerde implementatie wordt onderbroken als er een implementatie is voor de standaardlijst proxy-uitzondering.  

### <a name="requirements"></a>Vereisten

Aan deze vereisten moet worden voldaan voor uitzonderingen op proxyserver- en proxysite:These requirements must be to on the proxy server and proxy site exceptions:
- Moet een geldig serveradres en poortnummer zijn
- URL's moeten een geldige http-site zijn 

### <a name="customize-and-deploy-proxies"></a>Proxy's aanpassen en implementeren

**Een afzonderlijke proxysiteuitzondering toevoegen**

1. Aanmelden bij [de portal Beheerde Desktopbeheerder](https://aka.ms/mwaasportal) van Microsoft
2. Selecteer onder **Instellingen**de optie **Configureerbaar**.
3. Selecteer **Proxy**in **configureerbare** werkruimte. 
4. Voer het **adres-** en **poortnummer** voor uw proxyserver in en selecteer **Proxy-uitzondering toevoegen**. 
5. Voer de URL van een geldige http-site in en selecteer **Proxy-uitzondering toevoegen**. 
6. Herhaal stap 1-5 voor elke vertrouwde site die u wilt toevoegen. 
7. Selecteer **Faseimplementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.

## <a name="additional-resources"></a>Aanvullende bronnen
- [Overzicht van configureerbare instellingen](config-setting-overview.md) 
- [Configureerbare instellingen implementeren](config-setting-deploy.md)
