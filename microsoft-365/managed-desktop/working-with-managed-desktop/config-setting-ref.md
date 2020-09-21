---
title: Overzicht van configureerbare instellingen voor Microsoft Managed Desktop
description: Categorieën instellen voor configureerbare instellingen in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2c7c7d75fad58cab0cd6d19a16a97667ea3641a1
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104486"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Overzicht van configureerbare instellingen-Microsoft Managed Desktop

Dit onderwerp bevat een overzicht van de instellingen categorieën die klanten kunnen configureren met Microsoft Managed Desktop. Elke instellings categorie bevat informatie over vereisten, aanbevolen procedures en de manier waarop u de categorie instelling kunt aanpassen. 

## <a name="desktop-background-picture"></a>Afbeelding van bureaubladachtergrond
U kunt de bureaubladachtergrond afbeelding aanpassen voor Microsoft Managed Desktop-apparaten in uw organisatie. U kunt deze gebruiken om de merk-of marketingmateriaal van een bedrijf toe te passen. 

### <a name="requirements"></a>Vereisten

Voor een bureaubladachtergrond moet aan de volgende vereisten wordt voldaan:
- Afbeeldings bestandsindeling:. jpg,. JPEG of. png
- Locatie van de bestanden: host op een vertrouwde, beveiligde HTTP-locatie (https). 
- Niet toegestaan-http-en bestandsshare (UNC)-locaties worden niet ondersteund. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Afbeelding van bureaubladachtergrond aanpassen en implementeren

**Een aangepaste bureaubladachtergrond afbeelding toevoegen**
1. Meld u aan bij [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu **apparaten** .
2. Ga naar de sectie Microsoft Managed Desktop en selecteer **instellingen**.
3. Selecteer in de werkruimte **instellingen** de optie **afbeelding van bureaubladachtergrond**. 
4. Voer de locatie in van de afbeelding die u wilt gebruiken. 
5. Selecteer **fase-implementatie** om de wijzigingen op te slaan en te implementeren in de groep testen. 

## <a name="browser-start-pages"></a>Startpagina's in browser
Browser startpagina's worden in afzonderlijke tabbladen geopend wanneer uw gebruikers Microsoft Edge starten. Als u wilt voorkomen dat uw gebruikers een set sites openen die ze vaak gebruiken, voegt u een startpagina voor een browser toe voor elke site. 

### <a name="requirements"></a>Vereisten

U moet de FQDN (Fully Qualified Domain Name)-naam (FULLy Qualified Domain Name) voor intranetsites of Internet sites voor de startpagina's van uw browser. Als interne sites zijn geconfigureerd, kunnen gebruikers de toegang tot deze sites alleen laten weten wanneer ze verbinding hebben met het interne netwerk wanneer ze zich op kantoor bevinden of wanneer ze verbinding maken met een VPN-verbinding. 

### <a name="customize-and-deploy-browser-start-pages"></a>Startpagina's voor browser aanpassen en implementeren

**Een startpagina voor een browser toevoegen**
1. Meld u aan bij [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu **apparaten** .
2. Ga naar de sectie Microsoft Managed Desktop en selecteer **instellingen**.
3. Selecteer in de werkruimte **instellingen** de optie **browser startpagina's**. 
4. Selecteer **Startpagina toevoegen**.
5. Voer op de **Startpagina van de browser toevoegen**de URL in voor de site die u wilt gebruiken en selecteer vervolgens **Startpagina toevoegen**. 
6. Herhaal stappen 1-5 voor andere startpagina's van de browser. 
7. Selecteer **fase-implementatie** om de wijzigingen op te slaan en te implementeren in de groep testen.

## <a name="enterprise-mode-site-list-location"></a>Locatie van de site lijst voor de ondernemingsmodus

Als u specifieke websites en apps hebt met compatibiliteitsproblemen met Microsoft Edge, kunt u de site lijst voor de ondernemingsmodus gebruiken, zodat de websites automatisch met Internet Explorer 11 worden geopend. Als u weet dat uw intranetsites niet goed werken met Microsoft Edge, kunt u instellen dat alle intranetsites automatisch met Internet Explorer 11 worden geopend. Met behulp van de ondernemingsmodus kunt u Microsoft Edge als standaardbrowser blijven gebruiken, terwijl u er ook voor zorgt dat uw apps werken met Internet Explorer 11. Zie [Enterprise mode en site lijsten voor ondernemings](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)modus voor meer informatie over site lijsten voor ondernemings modi. 

U kunt een https://-locatie opgeven of de locatie voor een interne share waarop u de site lijst van de ondernemingsmodus hebt gehost. 

### <a name="requirements"></a>Vereisten

U moet voldoen aan de volgende vereisten voor het site-lijstbestand:
- Bestandsindeling-XML-bestand die voldoet aan de [Bestands vereisten](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Bestandslocatie-hostbestand op een interne https-locatie. 
- Niet toegestaan-hosting voor een interne bestandsshare, zoals *//sharename*, is niet toegestaan.

### <a name="best-practices"></a>Aanbevolen procedures

Deze aanbevolen procedures worden gebruikt om klanten te helpen bij het aanbrengen van een beslissing hun IT-infrastructuur te moderniseren:
- **Kies een beperkt aantal sites** : Microsoft Managed Desktop gebruikt Microsoft Edge als de beste browser om het algehele beveiligingsniveau voor uw organisatie en bruikbaarheid voor uw gebruikers te verbeteren. De meeste sites in deze lijst zijn bedoeld voor oudere web-apps die een oudere versie van een browser nodig hebben die geen veel beveiligingsfuncties biedt. 
- **Kijk eens** naar een andere site of een web-app waarvoor geen oudere browser is vereist. U kunt ook overwegen om de site bij te werken, zodat u nieuwe browsers kunt gebruiken. Nieuwere browsers maken gebruik van de nieuwste technologieën en helpen de beveiliging te verbeteren.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>De locatie van de lijst met ondernemings site modi aanpassen en implementeren

**De locatie van een lijst met zakelijke site modi toevoegen**

1. Meld u aan bij [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu **apparaten** .
2. Ga naar de sectie Microsoft Managed Desktop en selecteer **instellingen**.
3. Selecteer in de werkruimte **instellingen** de locatie van de **site lijst voor de ondernemingsmodus**. 
4. Voer de https-locatie voor uw site lijst in. 
5. Selecteer **fase-implementatie** om de wijzigingen op te slaan en te implementeren in de groep testen.

## <a name="trusted-sites"></a>Vertrouwde sites

Met vertrouwde websites kunt u beveiligingszones en de locatie waar u een site kunt gebruiken, aanpassen voor verschillende sites. Beveiligingszones zijn onder meer: 
- Zone 1: lokale intranet zone
- Zone 2 – zone met vertrouwde websites
- Zone 3: Internet zone
- Zone 4 – zone met beperkte sites

### <a name="requirements"></a>Vereisten

Geef de FQDN-naam (Fully Qualified Domain Name) voor de intranet-of Internet site op voor elke vertrouwde site. 

### <a name="customize-and-deploy-trusted-sites"></a>Vertrouwde sites aanpassen en implementeren

**Een vertrouwde site toevoegen**

1. Meld u aan bij [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu **apparaten** .
2. Ga naar de sectie Microsoft Managed Desktop en selecteer **instellingen**.
3. Selecteer in de werkruimte **instellingen** de optie **vertrouwde websites**en selecteer vervolgens **vertrouwde site toevoegen**. 
4. Voer de URL in bij **vertrouwde site toevoegen**, kies een beveiligingszone en selecteer vervolgens **vertrouwde site toevoegen**. 
5. Herhaal stap 1-4 voor elke vertrouwde site die u wilt toevoegen. 
6. Selecteer **fase-implementatie** om de wijzigingen op te slaan en te implementeren in de groep testen.

**Een vertrouwde site verwijderen**

1. Meld u aan bij [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu **apparaten** .
2. Ga naar de sectie Microsoft Managed Desktop en selecteer **instellingen**.
3. Selecteer in de werkruimte **instellingen** de optie **vertrouwde websites**. 
4. Selecteer de site die u wilt verwijderen en selecteer vervolgens **verwijderen**. 
5. Herhaal stap 1-4 voor elke vertrouwde site die u wilt verwijderen. 
6. Selecteer **fase-implementatie** om de wijzigingen op te slaan en te implementeren in de groep testen.

## <a name="proxy"></a>/Proxy-invoegtoepassing
U kunt de instellingen voor de netwerkproxy voor uw organisatie beheren. Voeg uw proxyserver en poortnummer toe en voeg vervolgens uw proxy site-uitzonderingen toe. Microsoft Managed Desktop bevat een set standaard-proxy-uitzonderingen die nodig zijn om de service uit te voeren. De standaardlijst voor uitsluitingen mag alleen worden gewijzigd door de Microsoft beheerde bureaublad service.  Zie [Netwerkconfiguratie voor Microsoft beheerde bureaublad](../get-ready/network.md)voor meer informatie. 

De uitzonderingen voor de proxy site die u toevoegt in de Microsoft beheerde bureaublad Portal, worden toegevoegd aan de standaard-proxy-uitzonderingen van de beheerde bureaublad service van Microsoft. 

> [!NOTE]
> Het bijwerken van de standaardlijst met proxy-uitzonderingen wordt altijd met prioriteit gewijzigd voor klant implementaties. Dit houdt in dat uw gefaseerde implementatie wordt onderbroken als er een implementatie voor de standaardlijst met proxy-uitzonderingen is.  

### <a name="requirements"></a>Vereisten

Voor proxyserver-en proxy site-uitzonderingen moet de volgende vereisten zijn voldaan:
- Moet een geldig serveradres en een geldig poortnummer zijn
- Url's moet een geldige http-site zijn 

### <a name="customize-and-deploy-proxies"></a>Proxy's aanpassen en implementeren

**Een individuele uitzondering op de proxy site toevoegen**

1. Meld u aan bij [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu **apparaten** .
2. Ga naar de sectie Microsoft Managed Desktop en selecteer **instellingen**.
3. Selecteer in de werkruimte **instellingen** de optie **proxy**. 
4. Voer het **adres** en het **poortnummer** van de proxyserver in en selecteer vervolgens **proxy uitzondering toevoegen**. 
5. Voer de URL van een geldige http-site in en selecteer vervolgens **proxy uitzondering toevoegen**. 
6. Herhaal stap 1-5 voor elke vertrouwde site die u wilt toevoegen. 
7. Selecteer **fase-implementatie** om de wijzigingen op te slaan en te implementeren in de groep testen.

## <a name="additional-resources"></a>Aanvullende bronnen
- [Overzicht van configureerbare instellingen](config-setting-overview.md) 
- [Configureerbare instellingen implementeren](config-setting-deploy.md)
