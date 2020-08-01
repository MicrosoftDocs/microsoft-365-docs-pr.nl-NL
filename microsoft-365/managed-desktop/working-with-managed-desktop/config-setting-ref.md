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
ms.openlocfilehash: c3f8aec244b1b0685b8293fda0b048d662c7cef2
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529359"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Referentie voor configureerbare instellingen - Microsoft Managed Desktop

In dit onderwerp worden de instellingencategorieën weergegeven die klanten kunnen configureren met Microsoft Managed Desktop. Elke instellingscategorie bevat informatie over vereisten, aanbevolen procedures en hoe u de instellingscategorie aanpassen. 

## <a name="desktop-background-picture"></a>Bureaubladachtergrondafbeelding
U de bureaubladachtergrondafbeelding aanpassen voor Microsoft Managed Desktop-apparaten in uw organisatie. U dit gebruiken om een bedrijfsmerk of marketingmateriaal toe te passen. 

### <a name="requirements"></a>Vereisten

Aan deze vereisten moet worden voldaan voor een achtergrondafbeelding op het bureaublad:
- Afbeeldingsbestandsindeling - .jpg, jpeg of .png
- Bestandslocatie - Host op een vertrouwde beveiligde http (https) locatie. 
- Niet toegestaan - Http- en bestandsshare-locaties (unc) worden niet ondersteund. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Bureaubladachtergrondafbeelding aanpassen en implementeren

**Een aangepaste bureaubladachtergrondafbeelding toevoegen**
1. Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)
2. Selecteer **Configureerbaar**onder **Instellingen**.
3. Selecteer **in Configureerbare** werkruimte **de optie Bureaubladachtergrondafbeelding**. 
4. Voer de locatie in van de afbeelding die u wilt gebruiken. 
5. Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen. 

## <a name="browser-start-pages"></a>Startpagina's van de browser
Startpagina's in de browser worden geopend in afzonderlijke tabbladen wanneer uw gebruikers Microsoft Edge starten. Als u het uw gebruikers gemakkelijk wilt maken om een set sites te openen die ze vaak gebruiken, voegt u voor elke site een startpagina van de browser toe. 

### <a name="requirements"></a>Vereisten

U moet de volledig gekwalificeerde domeinnaam (FQDN) opgeven voor intranet- of internetsites voor startpagina's van uw browser. Als interne sites zijn geconfigureerd, laat gebruikers weten dat toegang tot deze sites alleen is toegestaan wanneer ze zijn verbonden met het interne netwerk wanneer ze op kantoor zijn of wanneer ze zijn verbonden met een VPN-verbinding. 

### <a name="customize-and-deploy-browser-start-pages"></a>Startpagina's voor browser aanpassen en implementeren

**Een startpagina voor een browser toevoegen**
1. Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)
2. Selecteer **Configureerbaar**onder **Instellingen**.
3. Selecteer **startpagina's voor browser in** **Configureerbare** werkruimte. 
4. Selecteer **Startpagina toevoegen**.
5. Voer **op De startpagina van**de browser toevoegen de URL in voor de site die u wilt gebruiken en selecteer **Startpagina toevoegen**. 
6. Herhaal stap 1-5 voor extra startpagina's voor de browser. 
7. Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.

## <a name="enterprise-mode-site-list-location"></a>Locatie van de sitelijst in de ondernemingsmodus

Als u specifieke websites en apps hebt waarvan u weet dat ze compatibiliteitsproblemen hebben met Microsoft Edge, u de sitelijst voor de Ondernemingsmodus gebruiken, zodat de websites automatisch worden geopend met Internet Explorer 11. Als u ook weet dat uw intranetsites niet correct gaan werken met Microsoft Edge, u alle intranetsites automatisch openen met Internet Explorer 11. Als u de Enterprise-modus gebruikt, u Microsoft Edge blijven gebruiken als uw standaardbrowser, terwijl u er ook voor zorgen dat uw apps blijven werken op Internet Explorer 11. Zie [Sitelijsten ondernemingsmodus en site in ondernemingsmodus](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)voor meer informatie over sitelijsten in de ondernemingsmodus . 

U een https:// locatie opgeven of de locatie voor een intern aandeel waar u uw sitelijst in ondernemingsmodus hebt gehost. 

### <a name="requirements"></a>Vereisten

Aan deze vereisten moet worden voldaan voor het lijstbestand van de site in de ondernemingsmodus:
- Bestandsindeling - XML-bestand dat voldoet aan [bestandsvereisten](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Bestandslocatie - Hostbestand op een interne https-locatie. 
- Niet toegestaan - Hosten op een intern bestandsaandeel, zoals *//sharename*, is niet toegestaan

### <a name="best-practices"></a>Aanbevolen procedures

Deze best practices worden aangeboden om klanten te helpen beslissingen te nemen om hun IT-infrastructuur te moderniseren:
- **Kies een beperkt aantal sites** : Microsoft Managed Desktop gebruikt Microsoft Edge als de favoriete browser om de algehele beveiliging voor uw organisatie en bruikbaarheid voor uw gebruikers te verbeteren. De meeste sites in deze lijst zijn voor oudere web-apps die een oudere versie van een browser nodig hebben die niet zoveel beveiligingsfuncties bevat. 
- **Overweeg een alternatief** : overweeg een andere site of web-app waarvoor geen oudere browser nodig is. Of overweeg de site bij te werken zodat deze nieuwere browsers kan gebruiken. Nieuwere browsers maken gebruik van de nieuwste technologie en helpen de beveiliging te verbeteren.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Locatie van de lijst met de ondernemingssitemodus aanpassen en implementeren

**Locatie van een lijst met bedrijfssitemodus toevoegen**

1.  Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)
2.  Selecteer **Configureerbaar**onder **Instellingen**.
3.  Selecteer **in Configureerbare** werkruimte de locatie van de sitelijst in **de ondernemingsmodus**. 
4.  Voer de https-locatie voor uw sitelijst in. 
5.  Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.

## <a name="trusted-sites"></a>Vertrouwde sites

Vertrouwde sites stellen u in staat om beveiligingszones aan te passen, of waar een site kan worden gebruikt, voor verschillende sites. Veiligheidszones zijn onder andere: 
- Zone 1 – Lokale intranetzone
- Zone 2 – Zone Trusted sites
- Zone 3 – Internetzone
- Zone 4 – Zone Restricted Sites

### <a name="requirements"></a>Vereisten

Geef de volledig gekwalificeerde domeinnaam (FQDN) voor intranet of internetsites voor elke vertrouwde site. 

### <a name="customize-and-deploy-trusted-sites"></a>Vertrouwde sites aanpassen en implementeren

**Een vertrouwde site toevoegen**

1. Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)
2. Selecteer **Configureerbaar**onder **Instellingen**.
3. Selecteer **vertrouwde sites**in **Configureerbare** werkruimte en selecteer **Vervolgens Vertrouwde site toevoegen**. 
4. Voer **op Vertrouwde site toevoegen**de URL in, kies een beveiligingszone en selecteer **Vervolgens Vertrouwde site toevoegen**. 
5. Herhaal stap 1-4 voor elke vertrouwde site die u wilt toevoegen. 
6. Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.

**Een vertrouwde site verwijderen**

1. Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)
2. Selecteer **Configureerbaar**onder **Instellingen**.
3. Selecteer **vertrouwde sites**in **de werkruimte Configureerbaar.** 
4. Selecteer de site die u wilt verwijderen en selecteer **Verwijderen**. 
5. Herhaal stap 1-4 voor elke vertrouwde site die u wilt verwijderen. 
6. Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.

## <a name="proxy"></a>Proxy
U netwerkproxy-instellingen voor uw organisatie beheren. Voeg uw proxyserver en poortnummer toe en voeg vervolgens uitzonderingen op uw proxysite toe. Microsoft Managed Desktop bevat een set standaardproxy-uitzonderingen die nodig zijn om de service te laten werken. De standaarduitsluitingslijst kan alleen worden gewijzigd door de Microsoft Managed Desktop-service.  Zie [Netwerkconfiguratie voor Microsoft Managed Desktop voor](../get-ready/network.md)meer informatie. 

De uitzonderingen op proxysite die u toevoegt in de Microsoft Managed Desktop-portal, worden toegevoegd aan de standaardproxy-uitzonderingen die zijn opgenomen in de Microsoft Managed Desktop-service. 

> [!NOTE]
> Het bijwerken van de standaardlijst voor proxy-uitzondering wordt altijd geprioriteerd boven implementaties van klanten. Dit betekent dat uw gefaseerde implementatie wordt onderbroken als er een implementatie is voor de standaardlijst voor proxy-uitzondering.  

### <a name="requirements"></a>Vereisten

Aan deze vereisten moet worden voldaan voor uitzonderingen op proxyserver en proxysite:
- Moet een geldig serveradres en poortnummer zijn
- URL's moeten een geldige http-site zijn 

### <a name="customize-and-deploy-proxies"></a>Proxy's aanpassen en implementeren

**Een afzonderlijke proxysiteuitzondering toevoegen**

1. Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)
2. Selecteer **Configureerbaar**onder **Instellingen**.
3. Selecteer Proxy in **de werkruimte Configureerbaar.** **Proxy** 
4. Voer het **adres-** en **poortnummer** voor uw proxyserver in en selecteer **Proxy exception toevoegen**. 
5. Voer de URL van een geldige http-site in en selecteer **Proxy exception toevoegen**. 
6. Herhaal stap 1-5 voor elke vertrouwde site die u wilt toevoegen. 
7. Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.

## <a name="additional-resources"></a>Overige informatiebronnen
- [Overzicht van configureerbare instellingen](config-setting-overview.md) 
- [Configureerbare instellingen implementeren](config-setting-deploy.md)
