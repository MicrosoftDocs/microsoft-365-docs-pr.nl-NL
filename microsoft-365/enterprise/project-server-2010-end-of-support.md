---
title: Routekaart voor eindondersteuning van Project Server 2010
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
description: De ondersteuning voor Project Server 2010 eindigt op 13 april 2021. Gebruik dit artikel als handleiding voor een upgrade naar Project Online of een nieuwere versie van Project Server on-premises.
ms.openlocfilehash: 807c09bff0cb6331b872474acc22f8d2c622a6c6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927370"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 einde van ondersteuningsroutekaart

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Project Server 2010 eindigt op **13 april 2021** op het einde van de ondersteuning. Deze datum is verlengd vanaf de vorige einddatum van ondersteuning van 13 oktober 2020. Als u momenteel Project Server 2010 gebruikt, moet u er rekening mee houden dat deze gerelateerde producten de volgende datums voor het einde van de ondersteuning hebben:

|Product |Eind van de ondersteuningsdatum|
|---|---|
|Project 2010 Standard|13 oktober 2020|
|Project 2010 Professional|13 oktober 2020|

Zie Upgraden van [Office 2010-servers en clientproducten](plan-upgrade-previous-versions-office.md)voor meer informatie over het bereiken van het einde van de ondersteuning.

## <a name="what-does-end-of-support-mean"></a>Wat betekent *het einde van de ondersteuning?*

Bijna alle Microsoft-producten hebben een ondersteuningslevenscyclus, waarin ze nieuwe functies, bugfixes en beveiligingsupdates krijgen. Deze levenscyclus duurt meestal tien jaar vanaf de eerste release van het product. Het einde van deze levenscyclus wordt het einde van de ondersteuning van het product genoemd. Nadat Project Server 2010 op 13 april 2021 het einde van de ondersteuning heeft bereikt, biedt Microsoft het volgende niet meer:

- Technische ondersteuning voor problemen die kunnen optreden.

- Bug fixes for issues that are discovered and that may impact the stability and usability of the server.

- Beveiligingsfixes voor beveiligingsproblemen die worden ontdekt en die de server kwetsbaar kunnen maken voor beveiligingslekken.

- Tijdzone-updates.

De installatie van Project Server 2010 blijft na deze datum worden uitgevoerd. Vanwege de eerder genoemde wijzigingen wordt u echter ten zeerste aangeraden zo snel mogelijk te migreren van Project Server 2010.

## <a name="what-are-my-options"></a>Wat zijn mijn opties?

Uw migratieopties zijn:

- Migreren naar Project Online

- Migreren naar een nieuwere on-premises versie van Project Server (bij voorkeur Project Server 2019)

Hier volgen de twee paden die u kunt volgen om het einde van de ondersteuning voor Project Server 2010 te voorkomen.

![Upgradepaden voor Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Waarom zou ik liever migreren naar Project Server 2019?|Waarom zou ik liever migreren naar Project Online?|
|---|---|
|Met bedrijfsregels kan ik mijn bedrijf niet in de cloud bedienen.  <br/><br/>  Ik heb controle nodig over updates voor mijn omgeving.|Ik heb mobiele of externe gebruikers.<br/><br/>  Kosten voor het migreren van on-premises servers zijn een belangrijk probleem (hardware, software, tijd en moeite om te implementeren, etc.). <br/><br/>  Na de migratie zijn de kosten voor het onderhouden van mijn omgeving een probleem (bijvoorbeeld automatische updates, gegarandeerde uptime, etc.).|

> [!NOTE]
> Zie Bronnen voor een upgrade van [Office 2010-servers en -clients voor meer informatie over uw migratieopties.](upgrade-from-office-2010-servers-and-products.md) Project Server biedt geen ondersteuning voor hybride configuratie omdat Project Server en Project Online niet dezelfde resourcegroep kunnen delen.

### <a name="what-are-my-options-for-project-client"></a>Wat zijn mijn opties voor projectclient?

Als u Project Professional 2010 of Project Standard 2010 gebruikt, zijn uw opties:

- Naar een nieuwere versie van Project Professional of Project Standard gaan
- Naar een onlineoplossing gaan, zoals Project Online of Project voor het web

#### <a name="move-to-a-newer-version-of-project-client"></a>Naar een nieuwere versie van projectclient gaan

Als u migreert van Project Standard 2010, kunt u naar een nieuwere versie van Project Standard (Project Standard 2016 of Project Standard 2019) gaan. U wordt aangeraden naar de nieuwste versie te gaan om te profiteren van de nieuwste functies. Als u migreert naar een minder recente versie (Project Standard 2016), betekent dit ook dat u sneller opnieuw moet migreren.

Als u migreert van Project Professional 2010, kunt u ook naar een nieuwere versie gaan (Project Professional 2019 of Project Professional 2016). Ga nogmaals naar de nieuwste versie, indien mogelijk. Als u Project Professional gebruikt om verbinding te maken met Project Server, moet u migreren naar een versie van Project Professional die verbinding maakt met de versie van Project Server die u gebruikt.

Gebruikers van Project Professional 2010 kunnen ook migreren naar de Project Online Desktop-client, een abonnementsversie van Project Professional 2019. Deze is opgenomen in abonnementen op ProjectPlan 3 en ProjectPlan 5.

#### <a name="move-to-an-online-solution"></a>Naar een onlineoplossing gaan

U kunt ook migreren van Project Professional 2010 of Project Standard 2010 naar een onlineoplossing op basis van een Project-abonnement. Zowel Project Plan 3 als Plan 5 bevatten Project Online en de nieuwste cloudaanbieding [Project voor het web.](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1) Beide bieden nieuwe functies en voordelen die het verkennen waard zijn.

Zie De servicebeschrijving van Microsoft Project voor meer informatie over functies en [licenties.](/office365/servicedescriptions/project-online-service-description/project-online-service-description)

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Belangrijke aandachtspunten voor het migreren van Project Server 2010

Houd rekening met het volgende wanneer u van plan bent te migreren van Project Server 2010:

- **Hulp krijgen van een Microsoft-oplossingsprovider:** een upgrade van Project Server 2010 kan een uitdaging zijn. Het vereist veel voorbereiding en planning. Het kan vooral lastig zijn als u niet de persoon bent die oorspronkelijk Project Server 2010 heeft ingesteld. Microsoft-oplossingsproviders zijn beschikbaar voor hulp, ongeacht of u van plan bent te migreren naar Project Server 2019 of naar Project Online. Zoek naar een oplossingsprovider in het [Microsoft-centrum voor oplossingsproviders.](https://go.microsoft.com/fwlink/p/?linkid=841249)

- **Uw aanpassingen plannen:** aanpassingen in uw Project Server 2010-omgeving werken mogelijk niet wanneer u migreert naar Project Server 2019 of Project Online. Er zijn aanzienlijke verschillen in Project Server-architectuur tussen versies. Ook verschillen de vereiste besturingssystemen, databaseservers en webbrowsers die met de versies werken. Hebt u een plan voor het testen of opnieuw opbouwen van uw aanpassingen in de nieuwe omgeving. Maak van deze gelegenheid gebruik om te bepalen of er nog specifieke aanpassingen nodig zijn. Zie Een plan maken voor huidige aanpassingen tijdens de upgrade naar [SharePoint 2013](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)voor meer informatie.

- **Tijd en geduld:** upgradeplanning, uitvoering en testen kost veel tijd en moeite, met name voor een upgrade naar Project Server 2019. Als u migreert van Project Server 2010 naar Project Server 2019, moet u eerst migreren naar Project Server 2013, uw gegevens controleren, vervolgens migreren naar Project Server 2016 en vervolgens naar Project Server 2019. Misschien wilt u contact op nemen met een Microsoft-oplossingsprovider voor een tijdsbestek en de geschatte kosten voor hulp.

## <a name="migrate-to-project-online"></a>Migreren naar Project Online

Als u ervoor kiest om te migreren van Project Server 2010 naar Project Online, kunt u de volgende stappen volgen om uw projectplangegevens handmatig te migreren:

1. Sla uw projectplannen op van Project Server 2010 naar .mpp-indeling.

2. Met Project Professional 2016, Project Professional 2019 of de Project Online-bureaubladclient opent u elk MPP-bestand en vervolgens op en publiceert u het in Project Online.

U kunt uw PWA-configuratie handmatig maken in Project Online (bijvoorbeeld de benodigde aangepaste velden of bedrijfsagenda's opnieuw maken). Microsoft-oplossingsproviders kunnen ook helpen met dit proces.

Belangrijke bronnen:

|Resource|Beschrijving|
|---|---|
|[Aan de slag met Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Project Online instellen en gebruiken|
|[Servicebeschrijving van Project Online](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|Informatie over de verschillende Beschikbare Project Online-abonnementen|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migreren naar een nieuwere on-premises versie van Project Server

We zijn ervan overtuigd dat u de beste waarde en gebruikerservaring krijgt door te migreren naar Project Online. Maar we begrijpen ook dat sommige organisaties projectgegevens on-premises moeten houden. Als u ervoor kiest om uw projectgegevens on-premises te houden, kunt u uw Project Server 2010-omgeving migreren naar Project Server 2013, Project Server 2016 of Project Server 2019.

Als u niet kunt migreren naar Project Online, raden we u aan te migreren naar Project Server 2019. Project Server 2019 bevat de meeste belangrijke functies in eerdere versies van Project Server. En het komt het meest overeen met de ervaring die beschikbaar is met Project Online, hoewel sommige functies alleen beschikbaar zijn in Project Online.

Nadat u elke migratie hebt voltooid, moet u ervoor zorgen dat uw gegevens zijn gemigreerd.

> [!NOTE]
> Als u beperkt bent tot een on-premises oplossing en alleen wilt migreren naar Project Server 2013, moet u er rekening mee houden dat deze versie nog maar een paar jaar ondersteuning heeft. Het einde van de ondersteuningsdatum voor Project Server 2013 met Service Pack 2 oktober 13, 2023. Zie [Microsoft Product Lifecycle Policy (Microsoft Product Lifecycle Policy)](/lifecycle/)voor meer informatie over einddatums van ondersteuning.

### <a name="how-do-i-migrate-to-project-server-2019"></a>Hoe kan ik migreren naar Project Server 2019?

De architecturale verschillen tussen Project Server 2010 en Project Server 2019 voorkomen een direct migratiepad. U moet dus uw Project Server 2010-gegevens migreren naar elke opeenvolgende versie van Project Server totdat u Bij Project Server 2019 bent. Stappen voor het upgraden van Project Server 2010 naar Project Server 2019:

1. Migreren naar Project Server 2013.

2. Migreren van Project Serve 2013 naar Project Server 2016.

3. Migreren van Project Server 2016 naar Project Server 2019.

Nadat u elke migratie hebt voltooid, moet u ervoor zorgen dat uw gegevens zijn gemigreerd.

### <a name="step-1-migrate-to-project-server-2013"></a>Stap 1: Migreren naar Project Server 2013

Zie Upgraden naar Project Server 2013 voor uitgebreide informatie over het upgraden van Project Server 2010 naar Project Server [2013.](/project/upgrade-to-project-server-2016)

Belangrijke bronnen:

- [Overzicht van het upgradeproces voor Project Server 2013](/project/upgrade-to-project-server-2016)

  Krijg een overzicht op hoog niveau van hoe u een upgrade kunt uitvoeren van Project Server 2010 naar Project Server 2013.
- [Een upgrade naar Project Server 2013 plannen](/project/plan-for-upgrade-to-project-server-2016)

  Bekijk planningsoverwegingen bij het upgraden van Project Server 2010 naar Project Server 2013, inclusief systeemvereisten.

- [Nieuwe functies in de upgrade van Project Server 2013](/project/what-s-new-in-project-server-2013-upgrade) hebben betrekking op belangrijke wijzigingen voor deze versie, waaronder:

   - Er is geen in-place upgrade naar Project Server 2013. De methode database-attach is de enige ondersteunde manier om een upgrade uit te voeren van Project Server 2010 naar Project Server 2013.

   - Het upgradeproces converteert niet alleen uw Project Server 2010-gegevens naar de projectserver 2013-indeling, maar voegt ook de vier Project Server 2010-databases samen in één Project Web App-database.

   - Zowel SharePoint Server 2013 als Project Server 2013 zijn gewijzigd in verificatie op basis van claims uit de vorige versie. Als u klassieke verificatie gebruikt, moet u dit overwegen bij het upgraden. Zie Migreren van de klassieke modus naar verificatie op basis van [claims in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)voor meer informatie.

Belangrijke bronnen:

- [Overzicht van het upgradeproces naar Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)

- [Uw databases en Project Web App-siteverzamelingen upgraden (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Microsoft Project Server-upgradeprocesdiagram](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [De grote databaseconsolidatie, De migratie van Project Server 2010 naar 2013 in 8 eenvoudige stappen](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Stap 2: Migreren naar Project Server 2016

Nadat u naar Project Server 2013 bent overgeslagen en hebt gecontroleerd of uw gegevens zijn gemigreerd, is de volgende stap het migreren naar Project Server 2016.

Zie Upgraden naar [Project Server 2016 voor meer informatie.](/Project/upgrade-to-project-server-2016)

Belangrijke bronnen:

- [Overzicht van het upgradeproces voor Project Server 2016](/Project/overview-of-the-project-server-2016-upgrade-process)

  Begrijp wat u moet doen om een upgrade uit te voeren van Project Server 2013 naar Project Server 2016.

- [Een upgrade plannen naar Project Server 2016](/Project/plan-for-upgrade-to-project-server-2016)

  Bekijk de planningsoverwegingen die u moet maken bij het upgraden van Project Server 2013 naar Project Server 2016.

[Wat u moet weten over de upgrade van Project Server 2016,](/project/plan-for-upgrade-to-project-server-2016#thingknow) heeft betrekking op belangrijke wijzigingen voor het upgraden naar deze versie, waaronder:

- Wanneer u uw Project Server 2016-omgeving maakt, moet u er rekening mee houden dat de installatiebestanden van Project Server 2016 zijn opgenomen in SharePoint Server 2016. Zie [Project Server 2016 implementeren](/project/deploy-project-server-2016)voor meer informatie.

- Resourceplannen worden afgeschaft in Project Server 2016. Uw Project Server 2013-resourceplannen worden gemigreerd naar Resourceafspraak in Project Server 2016 en in Project Online. Zie [Overzicht: Resourceafspraak voor](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) meer informatie.

### <a name="step-3-migrate-to-project-server-2019"></a>Stap 3: Migreren naar Project Server 2019

Nadat u naar Project Server 2016 hebt gemigreerd en hebt gecontroleerd of uw gegevens zijn gemigreerd, is de volgende stap het migreren van uw gegevens naar Project Server 2019.

Zie Upgraden naar Project Server 2019 voor meer informatie over wat u moet doen om een upgrade uit te voeren van Project Server 2016 naar Project Server [2019.](/Project/upgrade-to-project-server-2016)

Belangrijke bronnen:

- [Overzicht van het upgradeproces voor Project Server 2019](/project/overview-of-the-project-server-2019-upgrade-process)

  Krijg op hoog niveau inzicht in wat u moet doen om een upgrade uit te voeren van Project Server 2013 naar Project Server 2016.

- [Een upgrade plannen naar Project Server 2019](/project/plan-for-upgrade-to-project-server-2019)

  Bekijk planningsoverwegingen voor het upgraden van Project Server 2016 naar Project Server 2019.

- [Dingen die u moet weten over de upgrade van Project Server 2019](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>Meer informatie over belangrijke wijzigingen voor het upgraden naar deze versie, waaronder:

   - Tijdens het upgradeproces worden uw gegevens gemigreerd van uw Project Server 2016-database naar de SharePoint Server 2019-inhoudsdatabase.  In Project Server 2019 wordt geen eigen Project Server-database meer gemaakt in de SharePoint Server-farm.

   - Na de upgrade moet u rekening houden met verschillende wijzigingen in Project Web App.  Zie Nieuw in [Project Server 2019 voor meer informatie.](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)

**Andere bronnen:**

- [Project Online Service Beschrijvingen:](/office365/servicedescriptions/project-online-service-description/project-online-service-description)Bekijk de functies voor portfoliobeheer die zijn opgenomen in Project Server 2016 en Project Online Premium.

- [Migratiehandleiding voor Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Overzicht van opties voor Office 2010-client en -servers en Windows 7

Zie het einde van de ondersteuningsposter voor een visueel overzicht van de upgrade,migreren en verplaatsen naar [](../downloads/Office2010Windows7EndOfSupport.pdf)de cloudopties voor Office 2010-clients en -servers en Windows 7.

[![Einde van ondersteuning voor Office 2010-clients en -servers en Windows 7-poster](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Deze poster illustreert de verschillende paden die u kunt volgen om het einde van de ondersteuning voor Office 2010-client- en serverproducten en Windows 7 te voorkomen, met voorkeurspaden en optieondersteuning in Microsoft 365 Enterprise gemarkeerd.

U kunt deze [poster ook](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) downloaden en afdrukken in de notatie letter, legal of tabloid (11 x 17).

## <a name="related-topics"></a>Verwante onderwerpen

[Upgraden van SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Upgrade van Office 2010-servers en -clients](upgrade-from-office-2010-servers-and-products.md)