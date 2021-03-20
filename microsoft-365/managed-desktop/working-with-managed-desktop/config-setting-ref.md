---
title: Verwijzing naar configureerbare instellingen voor Microsoft Managed Desktop
description: Categorieën instellen voor configureerbare instellingen in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1245268b6128aa022a972fd0282009573558ec47
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917702"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Verwijzing naar configureerbare instellingen - Microsoft Managed Desktop

In dit onderwerp worden de instellingencategorieën vermeld die klanten kunnen configureren met Microsoft Managed Desktop. Elke instellingscategorie bevat informatie over vereisten, best practices en hoe u de instellingscategorie kunt aanpassen. 

## <a name="desktop-background-picture"></a>Bureaubladachtergrondafbeelding
U kunt de bureaubladachtergrondafbeelding aanpassen voor Microsoft Managed Desktop-apparaten in uw organisatie. U kunt dit gebruiken om een merk of marketingmateriaal van een bedrijf toe te passen. 

### <a name="requirements"></a>Vereisten

Aan deze vereisten moet worden voldaan voor een achtergrondafbeelding op het bureaublad:
- Afbeeldingsbestandsindeling - .jpg, jpeg of .png
- Bestandslocatie: host op een vertrouwde beveiligde http-locatie (https). 
- Niet toegestaan: http- en unc-locaties (file share) worden niet ondersteund. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Bureaubladachtergrondafbeelding aanpassen en implementeren

**Een aangepaste bureaubladachtergrondafbeelding toevoegen**
1. Meld u aan [bij Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu Apparaten 
2. Zoek naar de sectie Beheerd bureaublad van Microsoft en selecteer **Instellingen.**
3. Selecteer **in de** werkruimte Instellingen de optie **Bureaubladachtergrondafbeelding**. 
4. Voer de locatie in van de afbeelding die u wilt gebruiken. 
5. Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en te implementeren in de groep Test. 

## <a name="browser-start-pages"></a>Startpagina's van browser
Startpagina's van de browser worden geopend op afzonderlijke tabbladen wanneer uw gebruikers Microsoft Edge starten. Als u het uw gebruikers gemakkelijk wilt maken om een reeks sites te openen die ze vaak gebruiken, voegt u een startpagina van de browser toe voor elke site. 

### <a name="requirements"></a>Vereisten

U moet de volledig gekwalificeerde domeinnaam (FQDN) voor intranet- of internetsites voor startpagina's van uw browser verstrekken. Als interne sites zijn geconfigureerd, laat u gebruikers weten dat toegang tot deze sites alleen is toegestaan wanneer ze zijn verbonden met het interne netwerk wanneer ze op kantoor zijn of wanneer ze zijn verbonden met een VPN-verbinding. 

### <a name="customize-and-deploy-browser-start-pages"></a>Startpagina's voor browsers aanpassen en implementeren

**Een startpagina van een browser toevoegen**
1. Meld u aan [bij Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu Apparaten 
2. Zoek naar de sectie Beheerd bureaublad van Microsoft en selecteer **Instellingen.**
3. Selecteer  startpagina's van browser in de werkruimte **Instellingen.** 
4. Selecteer **Startpagina toevoegen.**
5. Voer **op de startpagina van** de browser toevoegen de URL in voor de site die u wilt gebruiken en selecteer **startpagina toevoegen.** 
6. Herhaal stap 1-5 voor extra startpagina's van de browser. 
7. Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en te implementeren in de groep Test.

## <a name="enterprise-mode-site-list-location"></a>Sitelijstlocatie ondernemingsmodus

Als u specifieke websites en apps hebt die compatibiliteitsproblemen hebben met Microsoft Edge, kunt u de sitelijst ondernemingsmodus gebruiken, zodat de websites automatisch worden geopend met Internet Explorer 11. Als u weet dat uw intranetsites niet correct werken met Microsoft Edge, kunt u ook instellen dat alle intranetsites automatisch worden geopend met Internet Explorer 11. Als u de ondernemingsmodus gebruikt, kunt u Microsoft Edge blijven gebruiken als standaardbrowser, terwijl u er ook voor zorgt dat uw apps blijven werken op Internet Explorer 11. Zie Sitelijsten in de ondernemingsmodus en ondernemingsmodus voor meer informatie over sitelijsten in de [ondernemingsmodus.](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode) 

U kunt een locatie https:// of de locatie voor een interne share waar u de sitelijst voor de ondernemingsmodus hebt gehost. 

### <a name="requirements"></a>Vereisten

Aan deze vereisten moet worden voldaan voor het sitelijstbestand in de ondernemingsmodus:
- Bestandsindeling : XML-bestand dat voldoet [aan bestandsvereisten](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Bestandslocatie - Hostbestand op een interne https-locatie. 
- Niet toegestaan- Hosting op een interne bestands delen, zoals */sharename,* is niet toegestaan

### <a name="best-practices"></a>Aanbevolen procedures

Deze best practices worden aangeboden om klanten te helpen bij het nemen van beslissingen om hun IT-infrastructuur te moderniseren:
- **Kies een beperkt aantal sites:** Microsoft Managed Desktop gebruikt Microsoft Edge als voorkeursbrowser om de algehele beveiliging voor uw organisatie en bruikbaarheid voor uw gebruikers te verbeteren. De meeste sites in deze lijst zijn voor oudere web-apps die een oudere versie van een browser nodig hebben die niet zo veel beveiligingsfuncties bevat. 
- **Overweeg een alternatief:** overweeg een andere site of web-app waarvoor u geen oudere browser nodig hebt. Of overweeg de site bij te werken, zodat deze nieuwere browsers kan gebruiken. Nieuwere browsers gebruiken de nieuwste technologie en helpen de beveiliging te verbeteren.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Locatie van lijst met de ondernemingssitemodus aanpassen en implementeren

**Een lijstlocatie voor de ondernemingssitemodus toevoegen**

1. Meld u aan [bij Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu Apparaten 
2. Zoek naar de sectie Beheerd bureaublad van Microsoft en selecteer **Instellingen.**
3. Selecteer **in de** werkruimte Instellingen de locatie van de **sitelijst van de ondernemingsmodus.** 
4. Voer de https-locatie voor uw sitelijst in. 
5. Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en te implementeren in de groep Test.

## <a name="trusted-sites"></a>Vertrouwde sites

Met vertrouwde sites kunt u beveiligingszones aanpassen, of waar een site kan worden gebruikt, voor verschillende sites. Beveiligingszones zijn: 
- Zone 1 – Local Intranet zone
- Zone 2 : zone vertrouwde sites
- Zone 3 – Internetzone
- Zone 4 : zone met beperkte sites

### <a name="requirements"></a>Vereisten

Geef de volledig gekwalificeerde domeinnaam (FQDN) op voor intranet- of internetsites voor elke vertrouwde site. 

### <a name="customize-and-deploy-trusted-sites"></a>Vertrouwde sites aanpassen en implementeren

**Een vertrouwde site toevoegen**

1. Meld u aan [bij Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu Apparaten 
2. Zoek naar de sectie Beheerd bureaublad van Microsoft en selecteer **Instellingen.**
3. Selecteer **vertrouwde** sites in **de** werkruimte Instellingen en selecteer vervolgens Vertrouwde **site toevoegen.** 
4. Voer **bij Vertrouwde site toevoegen** de URL in, kies een beveiligingszone en selecteer vervolgens Vertrouwde site **toevoegen.** 
5. Herhaal stap 1-4 voor elke vertrouwde site die u wilt toevoegen. 
6. Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en te implementeren in de groep Test.

**Een vertrouwde site verwijderen**

1. Meld u aan [bij Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu Apparaten 
2. Zoek naar de sectie Beheerd bureaublad van Microsoft en selecteer **Instellingen.**
3. Selecteer **vertrouwde** sites in de werkruimte **Instellingen.** 
4. Selecteer de site die u wilt verwijderen en selecteer **vervolgens Verwijderen.** 
5. Herhaal stap 1-4 voor elke vertrouwde site die u wilt verwijderen. 
6. Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en te implementeren in de groep Test.

## <a name="proxy"></a>Proxy
U kunt netwerkproxy-instellingen voor uw organisatie beheren. Voeg uw proxyserver en poortnummer toe en voeg vervolgens de uitzonderingen op de proxysite toe. Microsoft Managed Desktop bevat een set standaardproxy-uitzonderingen die nodig zijn om de service te kunnen gebruiken. De standaarduitsluitingslijst kan alleen worden gewijzigd door de Microsoft Managed Desktop-service.  Zie Netwerkconfiguratie voor Microsoft Managed Desktop voor [meer informatie.](../get-ready/network.md) 

De uitzonderingen op de proxysite die u toevoegt in de Microsoft Managed Desktop-portal, worden toegevoegd aan de standaardproxy-uitzonderingen die zijn opgenomen in de Microsoft Managed Desktop-service. 

> [!NOTE]
> Het bijwerken van de standaardlijst met uitzondering van proxy's heeft altijd prioriteit boven klantimplementaties. Dit betekent dat de gefaseerde implementatie wordt onderbroken als er een implementatie is voor de standaardlijst met proxy-uitzonderingen.  

### <a name="requirements"></a>Vereisten

Aan deze vereisten moet worden voldaan voor uitzonderingen op proxyservers en proxysite's:
- Moet een geldig serveradres en poortnummer zijn
- URL's moeten een geldige http-site zijn 

### <a name="customize-and-deploy-proxies"></a>Proxies aanpassen en implementeren

**Een uitzondering voor een afzonderlijke proxysite toevoegen**

1. Meld u aan [bij Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu Apparaten 
2. Zoek naar de sectie Beheerd bureaublad van Microsoft en selecteer **Instellingen.**
3. Selecteer **proxy** in de werkruimte **Instellingen.** 
4. Voer het **adres-** en **poortnummer voor** uw proxyserver in en selecteer **vervolgens Uitzondering voor proxy toevoegen.** 
5. Voer de URL van een geldige http-site in en selecteer **vervolgens Proxy-uitzondering toevoegen.** 
6. Herhaal stap 1-5 voor elke vertrouwde site die u wilt toevoegen. 
7. Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en te implementeren in de groep Test.

## <a name="additional-resources"></a>Aanvullende bronnen
- [Overzicht van configureerbare instellingen](config-setting-overview.md) 
- [Configureerbare instellingen implementeren](config-setting-deploy.md)