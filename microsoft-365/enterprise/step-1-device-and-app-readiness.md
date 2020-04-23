---
title: 'Stap 1: apparaat- en app-gereedheid'
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Leer hoe u de apparaat- en app-gereedheid in de omgeving kunt beoordelen.
ms.openlocfilehash: fc048b046e46b4b2e792aa9bffb695eed742a74c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636854"
---
# <a name="step-1-device-and-app-readiness"></a>Stap 1: apparaat- en app-gereedheid

![](../media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><strong>Stap 1: apparaat- en app-gereedheid</strong></p>
<p>Start het implementatieproject van uw desktop met een inventaris van uw apparaten en apps, geef prioriteit aan wat u nodig hebt en test apps en apparaten met prioriteit. Vervolgens kunt u herstellen wat nodig is voor de implementatie.</p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>De apparaat- en app-gereedheid is de eerste stap in ons aanbevolen implementatieproces door de holistische aspecten van de toepassings- en hardwarecompatibiliteit te behandelen. Ga naar het [Implementatiecentrum voor desktops](https://aka.ms/HowToShift) om het volledige desktop-implementatieproces te zien.
>

In het verleden was toepassings- en hardwarecompatibiliteit een belangrijke horde voor het upgraden van de desktops van gebruikers. Het goede nieuws bij het plannen van uw overstap naar Windows 10 en Microsoft 365-apps voor ondernemingen is dat zo ongeveer elke toepassing die in de afgelopen 10 jaar is geschreven, kan worden uitgevoerd op Windows 10. De eventuele COM-invoegtoepassingen en VBA-macro's van uw organisatie die werden gebruikt in versies van Office die teruggaan tot Office 2010 blijven werken met de nieuwste versies van Office, zonder aanpassingen.

Dit gezegd hebbende, afhankelijk van de grootte en leeftijd van uw organisatie, is het controleren van de compatibiliteit van toepassingen en hardware waarschijnlijk nog steeds een belangrijke stap in het aanbevolen implementatieproces van acht fasen.

In dit artikel wordt u begeleid bij de eerste fase: apparaat- en app-gereedheid. U gebruikt hiervoor de Microsoft Readiness Assessment tools, waaronder de Desktop Analytics, een intelligente cloud-oplossing die beschikbaar is in uw Windows-licentie.

## <a name="windows-10-compatibility-scan"></a>Compatibiliteitsscan voor Windows 10

Voordat u Windows 10 implementeert, wordt u aangeraden de gereedheid van de bestaande apparaten met Windows 7 of 8/8.1 te controleren. De Installatiemedia voor Windows 10 ondersteunen een opdrachtregelschakeloptie voor het uitvoeren van het setup.exe, waarbij alleen op compatibiliteit wordt gecontroleerd en de upgrade zelf niet wordt uitgevoerd. ScanOnly kan worden uitgevoerd als een batchbestand met een script of worden geïntegreerd in een taakreeks van Microsoft Endpoint Configuration Manager, met inbegrip van de mogelijkheid om ScanOnly rechtstreeks vanuit het netwerk uit te voeren, zodat de Windows 10-installatiemedia niet naar het lokale apparaat worden gestreamd. Wanneer ScanOnly is voltooid, worden de resultaten via retourcodes geretourneerd in logboekbestanden die worden gegenereerd door Setup.EXE.   

Een voorbeeld van een ScanOnly-opdrachtregel waarmee de compatibiliteitsscan op de achtergrond wordt uitgevoerd, ziet er ongeveer als volgt uit:

    Setup.EXE /Auto Upgrade /Quiet /NoReboot /Compat ScanOnly

Voor meer informatie over ScanOnly en andere opdrachtschakelopties voor Windows Setup, raadpleegt u de [Opdrachtregelopties voor Windows Setup](https://aka.ms/setupswitches).

## <a name="recommended-tool-desktop-analytics"></a>Aanbevolen tool: Desktop Analytics

Desktop Analytics biedt veel voordelen ten opzichte van traditionele bureaubladbeheersystemen en is onze aanbevolen tool. De tool werkt zonder agent en begeleidt u door de benodigde stappen waarbij gebruik wordt gemaakt van informatie over toepassings- en stuurprogramma-compatibiliteit die is verzameld via het upgraden van honderden miljoenen consumentencomputers. Met deze informatie krijgt u een gedetailleerde analyse, met de gevonden compatibiliteitsproblemen die mogelijk uw upgrade verhinderen en ondersteund met koppelingen naar voorgestelde oplossingen die bij Microsoft bekend zijn.

Als u Desktop Analytics wilt instellen, moet u eerst een Azure-abonnement instellen waarin een werkruimte voor Azure Log Analytics is opgenomen. Wanneer u beschikt over Desktop Analytics kunt u vervolgens elk Windows 7 SP1-apparaat of nieuwer apparaat registreren via Groepsbeleidsinstellingen. Zo eenvoudig is het. Er zijn geen agenten om te implementeren en de visuele werkstroom van Desktop Analytics helpt u bij de implementatie van pilot- tot productimplementatie. Als u wilt, kunt u gegevens uit Desktop Analytics exporteren naar hulpprogramma's voor software-implementatie, zoals Microsoft Endpoint Configuration Manager (Current Branch), om doel-pc's rechtstreeks aan te pakken en om verzamelingen te maken wanneer ze klaar zijn voor implementatie.

Als u op dit moment Desktop Analytics niet hebt ingesteld voor uw omgeving of als u zich wilt registreren voor een proefversie, gaat u naar de pagina Desktop Analytics](https://www.aka.ms/desktopanalytics) en gaat u aan de slag.

## <a name="device-and-app-readiness-process"></a>Het apparaat- en app-gereedheidsproces

Apparaat- en app-gereedheid bestaat uit vier stappen: 1. Inventaris: 2 Prioriteiten stellen 3. Testen, 4. Herstellen. Laten we deze stap voor stap doornemen.

### <a name="1-inventory"></a>1\. Inventaris

Desktop Analytics gebruikt een proces zonder agent om de computers en toepassingen in uw pc-infrastructuur te inventariseren. Daarnaast biedt de tool rapporten over veelbezochte internetsites, apps en intranetlocaties om u te helpen de compatibiliteit ervan later te testen.

![](../media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

![](../media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a>2\. Prioriteiten stellen

Na de afgeronde inventarisatie gebruikt u Desktop Analytics om de meestgebruikte apps en hardware van uw organisatie te identificeren en hieraan prioriteit te geven. U moet ook kijken naar het beschikbaar maken van zo veel mogelijk computers voor de implementatie.

![](../media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

De tool biedt ook richtlijnen om te evalueren welke updates nodig zijn voor het oplossen van problemen tijdens de volgende stap: testen.

### <a name="3-testing"></a>3\. Testen

U zult merken dat de meeste geïnventariseerde toepassingen, stuurprogramma's en invoegtoepassingen gewoon blijven werken. Voor items waarvoor Desktop Analytics problemen verwacht, krijgt u de beschikking over de bekende informatie, waaronder waar u versie-updates kunt vinden om compatibiliteitsproblemen op te lossen. In plaats van tijd en geld te spenderen aan het oplossen van ingewikkelde problemen bij niet-kritieke, weinig ingezette toepassingen en oudere apparaten, kunt u in plaats daarvan ervoor kiezen om met gebruikers samen te werken om deze items buiten gebruik te stellen en te vervangen.

U kunt Desktop Analytics ook gebruiken om de compatibiliteitsproblemen met de browser te evalueren: stel vast welke door gebruikers gebruikte websites en webapps nog steeds ActiveX-besturingselementen, browserhelperobjecten, VBScript of andere verouderde technologie gebruiken die niet worden ondersteund door de browser Microsoft Edge. Uw gebruikers moeten nog steeds Internet Explorer 11 gebruiken voor deze sites en u kunt deze toevoegen aan de [sitelijst voor Ondernemingsmodus](https://docs.microsoft.com/microsoft-edge/deploy/emie-to-improve-compatibility) met behulp van Sitelijstbeheer van ondernemingsmodus.

Om u te helpen bij het overstappen naar Microsoft 365-apps voor ondernemingen, kunt u gebruikmaken van de [Readiness Toolkit voor Office](https://docs.microsoft.com/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) voor het testen van de compatibiliteit van uw invoegtoepassingen en VBA-macro's (Microsoft Visual Basic for Applications).

![](../media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a>4\. Herstellen

De laatste fase van de apparaat- en app-gereedheid is 'herstellen'. Hier wilt u de vereiste software- of stuurprogrammapakketten verzamelen. U gaat deze namelijk gebruiken om oudere versies te vervangen of bij te werken als onderdeel van het implementatieproces.

![](../media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

Naarmate u door de lijst gaat en problemen oplost, ziet u dat er meer en meer pc's 'gereed voor implementatie' worden. Dit betekent dat zowel de stuurprogramma's als de apps op de pc's compatibel zijn met de versie van Windows 10 die u gaat gebruiken voor implementatie.

### <a name="configuration-manager-software-inventory-for-application-prioritization"></a>Software-inventarisatie in Configuration Manager voor het prioriteit geven aan toepassingen

Software-inventarisatie in Configuration Manager is een alternatief voor het gebruik van analyse-oplossingen in de cloud voor apparaat- en app-gereedheid. U kunt het aantal installaties gebruiken en u richten op specifieke computers om prioriteit te geven aan compatibiliteitstests en -validatie en toepassingspakketten in te stellen die compatibel zijn met Windows 10 via pakketinstellingen. Hoewel u met deze optie geen bekende compatibiliteitsgegevens kunt vergelijken met de analytische services van Microsoft, kan dit een effectieve oplossing zijn voor het instellen van een kleinere set apps met prioriteit voor handmatig testen. 

Raadpleeg voor meer informatie [Inleiding tot software-inventarisatie in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/inventory/introduction-to-software-inventory) en voor het instellen van platformvereisten in toepassingspakketten [Pakketten en programma's in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).


## <a name="app-assure"></a>App Assure

Een andere tool voor het oplossen van compatibiliteit met Windows 10 en de app van Microsoft 365-apps voor ondernemingen is het programma [App Assure](https://aka.ms/appassure) dat beschikbaar is via het FastTrack Center. Bij geldige toepassingsproblemen biedt een technicus van Microsoft ondersteuning zonder extra kosten voor u bij het herstellen van de compatibiliteit van toepassingen via App Assure.

## <a name="continued-use-of-diagnostic-data-tools"></a>Voortgezet gebruik van Hulpprogramma's voor diagnostische gegevens

Desktop Analytics is niet alleen een tool waarmee u kunt overstappen naar Windows 10 en Microsoft 365-apps voor ondernemingen. Wanneer u eenmaal desktops op Windows 10 en Office 365 hebt draaien, kunt u deze gebruiken om uw implementatie te onderhouden en de halfjaarlijkse functie-updates te beheren, zodat u actueel kunt blijven.

## <a name="next-step"></a>Volgende stap 

## <a name="step-2-directory-and-network-readiness"></a>[Stap 2: gereedheid van directory en netwerk](https://aka.ms/mdd2)
