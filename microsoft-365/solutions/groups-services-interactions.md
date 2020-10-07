---
title: Interacties tussen groepen Services
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Interacties tussen groepen Services
ms.openlocfilehash: 235a897314a784ba3bb1ac50fe8bdfe9986a70d3
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377627"
---
# <a name="groups-services-interactions"></a>Interacties tussen groepen Services

Microsoft 365 groepen biedt een gemeenschappelijke Fabric voor een aantal services en werkbelasting in het Microsoft 365-platform om een verbinding te kunnen voeren voor eindgebruikers. In de kern is een Microsoft 365-groep beschikbaar voor de volgende bewerkingen:

- Een manier om het lidmaatschap (Azure AD) te beheren
- Een plaats waar berichten en gesprekken plaatsvinden (Exchange-postvak, Microsoft teams, Yammer)
- Een locatie voor het opslaan van bestanden (SharePoint)
- Een agenda voor planning (Exchange)
- Een notitieblok voor het vastleggen van notities (OneNote)

Wanneer u groepen maakt, worden er ook een aantal andere resources ingericht, maar deze zijn pas zichtbaar wanneer ze voor het eerst worden geopend voor de eerste keer van de service:

- Een bord voor het beheren van groeps taken (planner)
- Een werkruimte voor rapportage (Power BI)
- Een gebied voor gedeelde Video's (Microsoft stream)
- Een gebied voor gedeelde formulieren (formulieren)

In Microsoft 365 kunnen andere services communiceren met Microsoft 365-groepen om extra functies en mogelijkheden voor groepsleden te bieden.
Voorbeelden hiervan zijn:

- Power-apps voor apps
- Automatisch aan de werkstroom voor werkstromen
- Project op het web en routekaart voor het waterval van Project Management
- Teams voor kanaal gesprekken
- Yammer voor community's van belang

## <a name="user-interactions-with-groups"></a>Gebruikersinteracties met groepen

Microsoft 365-groepen kunnen worden gemaakt en beheerd vanuit diverse interfaces, zowel beheerders als eindgebruikers. 

### <a name="administrative-experiences"></a>Beheer ervaring

Beheerders kunnen Microsoft 365-groepen maken en beheren vanuit diverse beheer centra, opdrachtregel interfaces die ondersteuning bieden voor het uitvoeren van scripts en aangepaste apps die met de Graph-API werken. De enige uitzondering hierop is Yammer-groepen die moeten worden gemaakt binnen de Yammer-website.

**Gerelateerde instellingen**

In de verschillende beheerinterfaces die de groepsinstellingen kunnen beheren, bestaan diverse overlappingen waarvan u op de hoogte moet zijn.

**Microsoft 365-beheercentrum**

In het Microsoft 365-Beheercentrum is gasttoegang voor groepen standaard ingeschakeld, en is de mogelijkheid om eigenaren toe te voegen om gasten toe te voegen. Er zijn geen besturingselementen voor organisatieniveau beschikbaar voor groepen uit dit Beheercentrum.

**Azure AD-Beheercentrum**

Het Azure AD-Beheercentrum bevat besturingselementen om te bepalen of gebruikersgroepen kunnen maken of eigenaren kunnen toewijzen in azure-portals, evenals de beleidsinstellingen voor de vervaldatum en de naamgeving.

Het Beheercentrum biedt ook een aantal opties voor de uitnodigingen van een gast, die verder gaan dan het aantal van het Microsoft 365-Beheercentrum, bijvoorbeeld de mogelijkheid om te beperken of niet-eigenaren ook gasten kunnen uitnodigen

**SharePoint**

SharePoint-sites worden gemaakt met de beveiligingsgroepen eigenaar, lid en bezoekers, en de eerste twee stemmen overeen met hun Microsoft 365-groep tegenhangers. Hoewel lidmaatschap van SharePoint Online-sites meestal wordt beheerd door de bijbehorende Microsoft 365-groep, is het geen bidirectioneelere relatie. Wijzigingen aan het lidmaatschap van het Microsoft 365-groepsniveau worden weergegeven in SharePoint, maar als lidmaatschap in de SharePoint-groep is gewijzigd, wordt dit niet weergegeven in de groep Microsoft 365.

### <a name="user-experiences"></a>Gebruikerservaring

Eindgebruikers kunnen groepen maken op basis van diverse services binnen Microsoft 365 en in anderen die ze alleen met een groep kunnen delen.

Met de volgende services kan het maken van groepen door eindgebruikers:
                         
Outlook planner project voor de webshare Point stream Microsoft teams Yammer

**Beperking van het maken van groepen**

Een veelgebruikte aanpak voor het beheren van sprawl van teams is beperkt welke gebruikers ze kunnen maken. Dit kan alleen worden gedaan door het maken van groepen te beperken. Dit heeft gevolgen voor de mogelijkheid om groepen te maken van andere services, indien dit voor eindgebruikers mogelijk noodzakelijk is. Microsoft 365-groepen biedt geen ondersteuning voor de mogelijkheid om het maken van groepen van bepaalde apps of services te beperken, terwijl u de groepen van derden toestaat.

De ervaring voor het maken van groepen is afhankelijk van apps en services:


|App of service|Optreedt|
|:-------------|:---------|
|Outlook|De optie **nieuwe groep** wordt verwijderd uit het menu Nieuw op de pagina personen|
|Planner|**Nieuw plan** geeft aan dat het maken van groepen is uitgeschakeld en dat u aanbiedingen wilt toevoegen aan een bestaande groep|
|Project voor het web en routekaart|Menu **groep maken** geeft uitleg dat het maken van groepen is beperkt en dat een bestaande groep wordt voorgesteld.|
|SharePoint|U kunt nog steeds een team site maken die niet is gekoppeld aan een groep.|
|Stream|De optie **groep** wordt niet weergegeven in het **menu maken**.|
|Teams|Gebruiker kan geen team maken met een nieuwe groep, maar u kunt nog wel een team maken dat gebruikmaakt van een bestaande groep.<br><br>U **maakt een team** knop door **team maken van een groep**te vervangen.|
|Yammer|**De optie een groep maken** wordt verwijderd uit hoofdgroepen/community's-navigatie.|

## <a name="services-interactions-with-groups"></a>Service interacties met groepen

Zie de groepen in Microsoft 365-poster voor informatie over de verschillende soorten groepen, hoe deze worden gemaakt en beheerd en wat de aanbevelingen zijn.

[![Miniatuurafbeelding van de infographic voor groepen](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

De volgende tabel bevat een overzicht van Microsoft 365 groepen interacties met verschillende services:

|Product|Functies|Gaat de service<br>bestaan zonder een groep?|Kan de service<br>een groep maken?|Verwijdert de<br>exemplaar verwijderen van de groep?|
|:---|:---|:---|:---|:---|
|Azure AD|Lidmaatschap, besturingselementen voor groepen, gasten|Ja|Ja|Ja|
|Exchange|Agenda, Postvak|Ja|Ja|Ja|
|Forms|Trans|Ja|Nee|Nee|
|OneNote|Terechtkom|Ja|Nee|Nee|
|Planner|Takenbord|Nee|Ja|Ja|
|Power apps-app|App|Ja|Nee|Nee|
|Automatisch aan de macht|Workflowregels|Ja|Nee|Nee|
|Power BI (klassiek)|Workspace|Nee|Ja|Ja|
|Power BI (nieuw)|Workspace|Ja|Nee|Ja|
|Project voor het web|Project plan|Ja|Ja|Nee|
|Roadmap|Roadmap|Ja|Ja|Nee|
|SharePoint|Site|Ja|Ja|Ja|
|Stream|Kanaal, video|Ja|Ja|Ja|
|Teams|Ondersteuning|Nee|Ja|Ja|
|Yammer|Groep|Ja|Ja|Ja|

Hoewel de bovenstaande tabel een algemeen overzicht biedt van groeps interacties met Microsoft 365-Services, zijn er een aantal nuances en intricacies die u moet begrijpen. In de volgende secties vindt u meer gedetailleerde informatie over de specifieke werkbelastingen en hun interacties met groepen.

## <a name="azure-ad"></a>Azure AD

Azure AD biedt de onderliggende functies voor Identiteitsbeheer in Microsoft 365.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Groepslidmaatschap
- Naam beleid
- Vervalbeleid
- Gast
- Beperking van het maken van groepen

**Kan Azure AD een groep maken?**

Ja, Microsoft 365-groepen kunnen worden gemaakt op basis van Azure AD via de webportal van beheer, via PowerShell of graph API.

**Bestaat Azure AD zonder een groep?**

Ja, Azure AD voert een geweldig aantal services uit die geen relatie hebben met Microsoft 365-groepen. Elke groep Microsoft 365 wordt weergegeven als een object in azure AD.

**Kunnen er meerdere exemplaren van Azure AD per groep zijn?**

Nee, er is maar één exemplaar van Azure AD.

**Kan Azure AD worden gekoppeld aan meerdere groepen?**

Ja, omdat Azure AD het onderliggende platform is dat de service voor groeps lidmaatschap biedt.

**Kan de koppeling van Azure AD met een groep worden gewijzigd?**

Nee, Azure AD is het onderliggende platform waar groepen bestaan.

**Verwijdert het exemplaar van de groep?**

Als u de groep in azure AD verwijdert, worden de bijbehorende services en inhoud van de groep verwijderd.

## <a name="teams"></a>Teams

Teams is een werkruimte met chat centrum voor een betere samenwerking door een enkelvoudige interface te bieden voor de interactie met diverse Microsoft-services en services van derden.

Wanneer een team wordt gemaakt, worden standaard de e-mail en de agenda die zijn gekoppeld aan de Microsoft 365-groep, verborgen in de algemene adreslijst in Exchange, en in Outlook. Dit kan handmatig worden overschreven door een beheerder als de gebruiker Outlook en teams wil gebruiken in dezelfde Microsoft 365-groep.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Communicatie
- & tabbladen kanalen
- Rekken

**Kunnen teams een groep maken?**

Ja, als u een nieuw team wilt maken, maakt u een nieuwe groep Microsoft 365. U kunt ook een team maken voor een bestaande groep die momenteel geen abonnement heeft.

**Bestaan teams zonder een groep?**

Nee, het is niet mogelijk dat een team bestaat zonder een groep.

**Kunnen er meerdere teams per groep zijn?**

Nee, de relatie tussen een team en een groep is 1:1.

**Kan een team worden gekoppeld aan meerdere groepen?**

Nee, het team zelf kan maar aan één groep worden gekoppeld.

**Kan de koppeling van een team met een groep worden gewijzigd?**

Nee, het team kan maar ooit worden gekoppeld aan de groep waaraan het oorspronkelijk is gekoppeld.

**Verwijdert het team de groep?**

Ja, als u het team verwijdert in Microsoft teams, wordt de groep, de gekoppelde services en de inhoud verwijderd.

## <a name="exchange"></a>Exchange

Exchange Online levert functies voor berichten, agenda's, contactpersonen en bijbehorende functionaliteit. In de context van een groep is slechts één resource gekoppeld, in plaats van een volledig service-exemplaar.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Postvak en agenda
- Mogelijkheid om alle groepsleden te e-mailen
- Opslag van teams-kanaal gesprekken voor eDiscovery-doeleinden, planner-opmerkingen

**Kan Exchange een groep maken?**

Ja, u kunt een groep maken vanuit het Exchange Online-Beheercentrum en vanuit Outlook. U kunt distributielijsten van Exchange ook converteren naar Microsoft 365 groepen.

**Maakt Exchange geen groep?**

Ja, Exchange Online biedt een aantal services, inclusief gedeelde postvakken en agenda's, zonder groeps koppeling.

**Kunnen er meerdere exemplaren van Exchange-postvakken of-agenda's per groep zijn?**

Nee, er kunnen maar één postvak van Exchange Online zijn en agenda voor een groep.

**Kunnen Exchange-postvakken en-agenda's worden gekoppeld aan meerdere groepen?**

Nee, het postvak en de agenda hebben een 1:1-relatie met de groep. Het is mogelijk dat u het postvak met andere gebruikers of groepen deelt, maar dit is niet van invloed op een vorm van Service Association.

**Kunnen de koppeling van het Exchange-postvak of de agenda van een groep worden gewijzigd?**

Nee, het postvak en de agenda kunnen niet worden gewijzigd in een andere groep. U kunt echter de inhoud van het ene Postvak verplaatsen naar het andere in Outlook of met behulp van een programma van derden.

**Verwijdert het postvak van de groep?**

Ja, als u het postvak in Exchange verwijdert, wordt de groep verwijderd en worden ook services en inhoud die aan de groep zijn gekoppeld.

## <a name="forms"></a>Forms

Forms biedt enquêtes en toetsen voor het web.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Eigendom van formulieren

**Kan formulieren groepen maken?**

Nee, formulieren kunnen geen groep maken.

**Bestaan er formulieren zonder een groep?**

Ja, enquêtes en toetsen kunnen rechtstreeks worden gemaakt in het account van een eindgebruiker.

**Kunnen er meerdere formulieren per groep worden?**

Ja, er kunnen meerdere formulieren zijn die aan een groep zijn gekoppeld.

**Kunnen formulieren aan meerdere groepen worden gekoppeld?**

Nee, een formulier kan slechts aan één groep worden gekoppeld.

**Kan de koppeling van een formulier met een groep worden gewijzigd?**

Nee, nadat een formulier is gekoppeld aan een groep (rechtstreeks binnen of eigenaar van een persoon die is overgebracht van een individu), kan het formulier niet worden verplaatst naar een andere groep.

**Verwijdert het formulier de groep?**

Nee, het is niet mogelijk om een groep uit de formulier interface te verwijderen, maar alleen afzonderlijke formulieren.

## <a name="onenote"></a>OneNote

OneNote is een toepassing voor digitale notitieblokken. Het OneNote-notitieblok dat is gemaakt met een groep, is een bestand in de bijbehorende SharePoint-site, in plaats van een service met een groep.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Gedeeld notitieblok (opgeslagen in de door de groep gekoppelde SharePoint-bibliotheek)

**Kan OneNote een groep maken?**

Nee, u kunt geen groep maken met de OneNote-toepassing.

**Bestaan er OneNote-notitieblokken zonder een groep?**

Ja, notitieblokken kunnen rechtstreeks worden gemaakt in OneDrive of op andere gedeelde locaties.

**Kunnen er meerdere OneNote-notitieblokken per groep zijn?**

Ja, er is standaard een notitieblok gemaakt en anderen kunnen toevoegen, maar een koppeling naar OneNote uit met de groep gekoppelde services wordt altijd naar het standaardnotitieblok verzonden.

**Kan een OneNote-notitieblok worden gekoppeld aan meerdere groepen?**

Nee, het notitieblok wordt opgeslagen in de door de groep gekoppelde SharePoint-site bibliotheek en gekoppeld aan diverse interfaces. Dit kan wel op dezelfde manier worden gedeeld met andere groepen, op dezelfde manier als met personen.

**Kan de koppeling van het notitieblok met een groep worden gewijzigd?**

Nee, het notitieblok zelf is gekoppeld aan de groep en kan rechtstreeks worden geopend vanuit andere services die met een groep verbonden zijn, maar de inhoud kan worden verplaatst van het ene notitieblok naar het andere binnen de OneNote-toepassing.

**Verwijdert de groep als u het notitieblok verwijdert.**

Nee, maar als het OneNote-notitieblok wordt verwijderd, zijn er mogelijk verbroken koppelingen in enkele van de door de groep gekoppelde services.

## <a name="planner"></a>Planner

Planner is een lichtgewicht service voor groepsbeheer.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Bord voor het beheren van groeps taken

**Kan planner een groep maken?**

Ja, het maken van een plan maakt een nieuwe groep.

**Bestaat er een planner-bord zonder een groep?**

Nee, een plan moet zijn gekoppeld aan een groep.

**Kunnen er meerdere abonnementen per groep zijn?**

Ja, er kunnen meerdere abonnementen per groep zijn.

**Kan een plan worden gekoppeld aan meerdere groepen?**

Nee, op basis van het groepslidmaatschap moet het groepslidmaatschap de toegang bepalen.

**Kan de koppeling van een plan met een groep worden gewijzigd?**

Nee, als u een plan kopieert, wordt een nieuwe groep gemaakt.

> [!NOTE]
> Een groep die door een andere toepassing is gemaakt, wordt niet automatisch weergegeven in planner voor een gebruiker. Om het bord in eerste instantie te openen, moeten ze dit openen vanuit een andere op de groep gebaseerde interface, zoals Outlook.

**Wordt de groep verwijderd wanneer u het abonnement verwijdert?**

Ja, als u een plan verwijdert, worden de services en inhoud van de groep en groep verwijderd.

## <a name="power-apps"></a>Power Apps

Power-apps bieden een canvas voor het ontwikkelen van apps zonder code.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Apps kunnen worden gedeeld met een groep die moet worden uitgevoerd en gewijzigd

**Kunnen Power-apps groepen maken?**

Nee, Power-apps kunnen geen Microsoft 365-groep maken.

**Bestaan er Power-apps zonder een groep?**

Ja, apps kunnen worden gemaakt binnen Power-apps en opgeslagen in het account Creators totdat ze worden gedeeld of gepubliceerd.

**Kunnen er meerdere apps per groep zijn?**

Ja, er kunnen meerdere apps met een groep worden gedeeld.

**Kunnen apps worden gekoppeld aan meerdere groepen?**

Ja, een app kan worden gedeeld met meerdere groepen.

**Kan de koppeling van een app met een groep worden gewijzigd?**

Ja, aangezien de koppeling tussen Power-apps en een Microsoft 365-groep alleen delen is, is de app nog steeds bij de maker.

> [!IMPORTANT]
> [Voor groepen moet beveiliging zijn ingeschakeld voordat apps kunnen worden gedeeld](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).

**Verwijdert de app in de groep?**

Nee, de apps zijn niet verbonden met de groep die u met hen deelt.

## <a name="power-automate"></a>Automatisch aan de macht

Automatisch automatiseren (voorheen bekend als Microsoft flow) levert werkstromen en automatiserings Services.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- U kunt werkstromen delen met een groep om deze uit te voeren en te wijzigen.

**Kan de groep een groep maken?**

Nee, automatisch automatiseren kan geen Microsoft 365-groep maken in de context van het bestand dat is gekoppeld aan een groep.

Het is ook mogelijk om een stroom te creëren waarmee verschillende bewerkingen worden uitgevoerd, zoals het maken van een Azure AD-beveiligingsgroep of het bijwerken van lidmaatschap van een groep van Microsoft 365.

**Bestaan er stromen zonder een groep?**

Ja, stromen kunnen worden gemaakt binnen het automatiseren van de toepassing en bevinden zich in het account Creators totdat ze worden gedeeld of gepubliceerd.

**Kunnen er meerdere stromen per groep zijn?**

Ja, er kunnen meerdere stromen met een groep worden gedeeld.

**Kan een stroom worden gekoppeld aan meerdere groepen?**

Ja, een stroom kan worden gedeeld met meerdere groepen.

**Kan een stroom koppeling met een groep worden gewijzigd?**

Ja, aangezien de koppeling tussen het automatiseren van de werkstroom en een Microsoft 365-groep alleen delen is, is de stroom nog niet inbegrepen bij de auteur.

**Verwijdert de groep verwijderen als u een stroom verwijdert.**

Nee, zoals Power-apps, zijn de stromen niet verbonden met de groep die u met hen deelt.

## <a name="power-bi-classic"></a>Power BI (klassiek)

Power BI biedt interactieve dashboards en rapporten van gegevensgestuurde gegevens.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Gegevensrapportage

**Kan Power BI een groep maken?**

Ja, als u een klassieke werkruimte maakt, wordt een Microsoft 365-groep gemaakt.

**Bestaat er een klassieke werkruimte van Power BI zonder een groep?**

Nee, [in Power bi een klassieke werkruimte moet zijn gekoppeld aan een groep](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).

**Kunnen er meerdere Power BI-werkruimten per groep zijn?**

Nee, de relatie tussen een klassieke werkruimte en een groep is 1:1.

**Kan een werkruimte aan meerdere groepen worden gekoppeld?**

Technisch Nee, terwijl de klassieke werkruimte met de groep wordt gemaakt, kan de inhoud buiten de groep worden gedeeld met gebruikers en beveiligingsgroepen.

**Kan de koppeling van de werkruimte met een groep worden gewijzigd?**

Nee, de klassieke werkruimte zelf is niet gekoppeld aan de groep, maar de inhoud kan worden verplaatst van de ene naar de andere werkruimte in de Power BI-interface of door de inhoud lokaal te exporteren.

**Verwijdert de groep uit de werkruimte?**

Ja, als u de werkruimte in Power BI verwijdert, wordt de groep en de gekoppelde services en inhoud verwijderd.

## <a name="power-bi-new"></a>Power BI (nieuw)

Power BI biedt interactieve dashboards en rapporten van gegevensgestuurde gegevens.

Tijdens het maken van een nieuwe werkruimte in Power BI is geen Microsoft 365-groep gemaakt, wat betekent dat een groep op andere manieren een nieuwe (niet Classic) werkruimte in Power BI maakt.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Gegevensrapportage

**Kan Power BI een groep maken?**

Nee, het is niet mogelijk om een Microsoft 365-groep te maken op basis van de nieuwe Power BI-interface.

**Bestaat de nieuwe Power BI-werkruimte zonder een groep?**

Ja, het is mogelijk dat u rapporten en werkruimten die zijn gemaakt in Power BI, hebt gemaakt die niet zijn gekoppeld aan Microsoft 365-groepen.

**Kunnen er meerdere werkruimten per groep zijn?**

Ja, u [kunt meerdere werkruimten die zijn gemaakt met Power bi, delen met een enkele groep](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).

**Kan een werkruimte aan meerdere groepen worden gekoppeld?**

Nee, een werkruimte die u hebt gemaakt met Power BI, kan slechts aan één groep worden gekoppeld.

**Kan de koppeling van een werkruimte met een groep worden gewijzigd?**

Ja en Nee. Een werkruimte die u hebt gemaakt met Power BI, kan slechts aan één groep tegelijk worden gekoppeld, maar de koppeling kan op elk moment worden gewijzigd. Een werkruimte die is gemaakt in Power BI door een groep, wordt permanent aan die groep gekoppeld.

**Verwijdert de groep uit de werkruimte?**

Ja, als u de werkruimte in Power BI verwijdert, worden de services en inhoud die aan de groep zijn gekoppeld, verwijderd.

## <a name="project-for-the-web"></a>Project voor het web

Project voor het web biedt de mogelijkheid om project plannen, Gantt-diagrammen en routekaarten te maken.
Belangrijkste functies van groepen.

- Project plannen

**Kan project een groep maken voor het web?**

Ja, het is mogelijk om rechtstreeks vanuit project voor het web een nieuwe Microsoft 365-groep te maken.

**Bestaan er projecten zonder een groep?**

Ja, projecten kunnen bestaan zonder dat ze zijn gekoppeld aan een Microsoft 365-groep, maar de toewijzing van taken vereist groeps koppeling.

**Kunnen er meerdere projecten per groep zijn?**

Ja, het is mogelijk om meerdere projecten in één groep te verbinden.

**Kan project worden gekoppeld aan meerdere groepen?**

Nee, een project kan slechts aan één groep worden gekoppeld.

**Kan de koppeling van een project met een groep worden gewijzigd?**

Nee, als de koppeling met een groep is gemaakt, kan deze niet worden gewijzigd.

**Verwijdert het project de groep?**

Nee, als u het project verwijdert in project voor het web, wordt de groep niet verwijderd.

## <a name="roadmap"></a>Roadmap

Routekaart biedt de mogelijkheid project plannen te maken met project voor Internet en project online.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Project plannen

**Kan een routekaart een groep maken?**

Ja, het is mogelijk om rechtstreeks vanuit een routekaart een nieuwe Microsoft 365-groep te maken.

**Bestaat zonder een groep?**

Ja, route plannen kunnen bestaan zonder dat ze zijn gekoppeld aan een groep van Microsoft 365, maar het delen van de routekaart vereist groeps koppeling.

**Kunnen er meerdere route plannen per groep zijn?**

Ja, het is mogelijk om meerdere route plannen te verbinden met een enkele groep.

**Kan een routekaart worden gekoppeld aan meerdere groepen?**

Nee, een routekaart kan maar aan één groep worden gekoppeld.

**Kan ik de koppeling van een routekaart met een groep wijzigen?**

Nee, als de koppeling met een groep is gemaakt, kan deze niet worden gewijzigd.

**Verwijdert de groep als u het wegwijzer verwijdert.**

Nee, als u het routekaart verwijdert, wordt de groep niet verwijderd.

## <a name="sharepoint"></a>SharePoint

SharePoint is een systeem voor inhoudsbeheer op basis van andere zaken, opslagservices voor een aantal Microsoft 365-Services.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Document bibliotheek
- Bibliotheek voor het opslaan van OneNote-notitieblokken
- Opslag van teams-wiki-bestanden

**Kan een groep worden gemaakt in SharePoint?**

Ja, als u een team site maakt in SharePoint, wordt standaard een Microsoft 365-groep gemaakt. Het is ook mogelijk om een groep te maken en desgewenst een team voor een bestaande site te maken.

**Bestaan er SharePoint-sites zonder een groep?**

Ja, SharePoint biedt een aantal niet-door de groep gekoppelde services en sites zoals communicatie-en hub-sites. 

**Kunnen er meerdere sites per groep worden?**

Nee, u kunt maar één site per groep hebben. Persoonlijke kanalen in teams gebruiken andere sites die niet zijn verbonden met de groep.

**Kunnen sites aan meerdere groepen worden gekoppeld?**

Technisch Nee, maar wanneer een site met een groep wordt gemaakt, kan de inhoud met andere groepen worden gedeeld.

**Kan de koppeling van een site met een groep worden gewijzigd?**

Nee, de site zelf is niet gekoppeld aan de groep, maar de inhoud kan worden verplaatst van de ene site naar de andere in de SharePoint-interface, door inhoud lokaal te exporteren of door middel van een programma van derden.

**Verwijdert de groep uit de site?**

Ja, als u de site in SharePoint verwijdert, worden de services en de gekoppelde services en de bijbehorende groepen verwijderd.

## <a name="stream"></a>Stream

Microsoft stream is een video-hosting en deel platform.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Video-opslag
- Opname van teams-vergadering
- Video kanalen

**Kan stream maken van een groep?**

Ja, het is mogelijk om rechtstreeks vanuit de stroom een nieuwe Microsoft 365-groep te maken.

**Bestaat de stream zonder een groep?**

Ja, videokanalen en Video's kunnen bestaan in stream zonder dat ze aan een groep zijn gekoppeld.

**Kunnen er meerdere Video's en kanalen per groep worden toegevoegd?**

Ja, er kunnen meerdere Video's en kanalen in elke groep worden toegevoegd.

**Kan een video of kanaal worden gekoppeld aan meerdere groepen?**

Ja, terwijl een video of kanaal wordt gemaakt met een groep, kunt u het bestanddelen met andere groepen.

**Kan de koppeling met een groep worden gewijzigd?**

Ja en Nee; Video's in de stroom zijn eigendom van de oorspronkelijke Uploader of vergaderings recorder, en kunnen dus aan een willekeurige groep worden gekoppeld, maar u kunt alleen videokanalen koppelen aan de groep waarin ze oorspronkelijk zijn gemaakt.

**Verwijdert de groep als u Video's of kanalen verwijdert?**

Nee, Video's of kanalen verwijderen niet de groep. Als u echter de groep zelf verwijdert, worden de services en inhoud van de groep verwijderd, met uitzondering van de feitelijke Video's.

## <a name="yammer"></a>Yammer

Yammer is een sociaal platform dat is ontworpen voor de bevordering van de betrokkenheid van community's binnen en tussen organisaties.

Door een community te maken (voorheen bekend als ' groep ') in Yammer wordt een postvak gemaakt, maar dit wordt niet in de huidige weergave gebruikt.

Een Microsoft 365-groep die is gekoppeld aan Yammer, kan niet worden gebruikt met een team in Microsoft teams.

**Belangrijkste functies die beschikbaar zijn voor groepen**

- Gespreks gebied

**Kan Yammer een groep Microsoft 365 maken?**

Ja, als u een nieuwe groep maakt in Yammer, maakt u een nieuwe groep Microsoft 365, als de platforms verbonden zijn en de gebruiker de mogelijkheid heeft om een groep te maken.

Een Yammer-groep met gekoppelde Microsoft 365-groep kan niet worden gemaakt in een andere interface of service dan Yammer zelf.

**Bestaat er een Yammer-groep zonder een Microsoft 365-groep?**

Ja, het is mogelijk om een Yammer-groep te maken zonder een Microsoft 365-groep.

Als het Yammer-platform niet is verbonden met Microsoft 365-groepen of gebruikers geen toegang hebben tot de groep Microsoft 365, worden Yammer-groepen gemaakt zonder een Microsoft 365-groeps koppeling.

**Kunnen er meerdere Yammer-groepen per Microsoft 365-groep worden?**

Nee, de relatie tussen een Yammer-groep en een Microsoft 365-groep is 1:1.

**Kan een Yammer-groep worden gekoppeld aan meerdere Microsoft 365-groepen?**

Nee, de Yammer-groep kan alleen worden gekoppeld aan één Microsoft 365-groep. Het is mogelijk dat berichten worden gedeeld met of verplaatst naar andere Yammer-groepen.

**Kan de koppeling van een Yammer-groep met een Microsoft 365-groep worden gewijzigd?**

Nee, de Yammer-groep kan maar ooit worden gekoppeld aan de Microsoft 365-groep waaraan deze oorspronkelijk is gekoppeld.

**Verwijdert de Yammer-groep de groep Microsoft 365.**

Ja, als u de groep in Yammer verwijdert, worden verwante Microsoft-groepen en door groepen gekoppelde services en inhoud verwijderd.

