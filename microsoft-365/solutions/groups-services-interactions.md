---
title: Services-interacties groepeert
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
description: Services-interacties groepeert
ms.openlocfilehash: 331c30c86481b1729251c685de2d663fb14f390b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921022"
---
# <a name="groups-services-interactions"></a>Services-interacties groepeert

Microsoft 365 Groups biedt een veelgebruikte structuur voor een aantal services en werkbelastingen binnen het Microsoft 365-platform om eindgebruikers een verbonden ervaring te bieden. In de kern bestaat er een Microsoft 365-groep voor het volgende:

- Een manier om het lidmaatschap te beheren (Azure AD)
- Een plek waar berichten en gesprekken kunnen plaatsvinden (Exchange-postvak, Microsoft Teams, Yammer)
- Een plek waar bestanden moeten worden opgeslagen (SharePoint)
- Een agenda voor planning (Exchange)
- Een notitieblok voor het vastleggen van notities (OneNote)

Op het moment van het maken van groepen worden ook een aantal andere resources ingericht, maar ze zijn pas zichtbaar wanneer ze voor het eerst worden gebruikt vanuit de service:

- Een bord voor het beheren van groepstaken (Planner)
- Een werkruimte voor rapportage (Power BI)
- Een gebied voor gedeelde video's (Microsoft Stream)
- Een gebied voor gedeelde formulieren (Formulieren)

In Microsoft 365 kunnen andere services werken met Microsoft 365-groepen om extra functionaliteit en mogelijkheden te bieden aan groepsleden.
Voorbeelden hiervan zijn:

- Power Apps voor apps
- Power Automate voor werkstromen
- Project op het web en Roadmap voor projectmanagement op basis van waterval
- Teams voor gesprekken op basis van kanalen
- Yammer voor gemeenschappen van belang

## <a name="user-interactions-with-groups"></a>Gebruikersinteracties met groepen

Microsoft 365 Groepen kunnen worden gemaakt en beheerd op verschillende interfaces, zowel door beheerders als eindgebruikers. 

### <a name="administrative-experiences"></a>Beheerervaringen

Beheerders kunnen Microsoft 365-groepen maken en beheren vanuit verschillende workload-beheercentra, opdrachtregelinterfaces die scripting ondersteunen, evenals aangepaste apps die werken met de Graph-API. De enige uitzondering hierop zijn Yammer-groepen, die moeten worden gemaakt vanuit de webinterface van Yammer.

**Gerelateerde instellingen**

In de verschillende beheerinterfaces die groepsinstellingen kunnen beheren, bestaan verschillende overlappingen waarvan u op de hoogte moet zijn.

**Microsoft 365-beheercentrum**

In het Microsoft 365-beheercentrum is gasttoegang tot Groepen standaard ingeschakeld, evenals de mogelijkheid om eigenaren toe te staan gasten toe te voegen. Er zijn geen andere besturingselementen op organisatieniveau beschikbaar voor Groepen in dit beheercentrum.

**Azure AD-beheercentrum**

Het Azure AD-beheercentrum biedt besturingselementen voor het maken van groepen of het toewijzen van eigenaren in Azure-portals, evenals beleidsinstellingen voor verloop en naamgeving.

Het beheercentrum biedt ook een aantal controlemaatregelen voor gastuitnodiging die verder gaan dan die van het Microsoft 365-beheercentrum, zoals de mogelijkheid om te beperken of niet-eigenaren ook gasten kunnen uitnodigen

**SharePoint**

SharePoint-sites worden gemaakt met beveiligingsgroepen eigenaar, lid en bezoeker, met de eerste twee die overeenkomen met de tegenhangers van de Microsoft 365-groep. Hoewel lidmaatschap voor SharePoint Online-sites over het algemeen wordt beheerd door de bijbehorende Microsoft 365-groep, is het geen bidirectionele relatie. Wijzigingen in het lidmaatschap op groepsniveau van Microsoft 365 worden doorgevoerd in SharePoint, maar als het lidmaatschap in de SharePoint-groep wordt gewijzigd, wordt dit niet doorgevoerd in de Microsoft 365-groep.

### <a name="user-experiences"></a>Gebruikerservaringen

Eindgebruikers kunnen groepen maken van verschillende services in Microsoft 365, en in andere kunnen ze alleen delen met een groep.

Met de volgende services kunt u groepen maken door eindgebruikers:
                         
Outlook Planner Project voor het web SharePoint Stream Microsoft Teams Yammer

**Beperking van het maken van groepen**

Een veelgebruikte methode om de wildgroei van teams te beperken, is het beperken van de gebruikers die ze kunnen maken. Dit kan alleen door het maken van groepen te beperken. Dit is van invloed op de mogelijkheid om groepen te maken van andere services waar dit mogelijk nodig is voor eindgebruikers. Microsoft 365 Groepen biedt geen ondersteuning voor de mogelijkheid om het maken van groepen van bepaalde apps of services te beperken, terwijl deze door anderen worden toe te staan.

De ervaring met beperkingen voor het maken van groepen verschilt per apps en services:


|App of service|Ervaring|
|:-------------|:---------|
|Outlook|**De optie** Nieuwe groep wordt verwijderd uit het menu Nieuw op de pagina Personen|
|Planner|**Nieuw plan** legt uit dat het maken van groepen is uitgeschakeld en biedt om het plan toe te voegen aan een bestaande groep|
|Project voor het web en Routekaart|**In het groepsmenu** wordt uitgelegd dat het maken van groepen is beperkt en wordt gesuggereerd dat u een bestaande groep gebruikt.|
|SharePoint|U kunt nog steeds een teamsite maken die niet is verbonden met een groep.|
|Stream|**Groepsoptie** wordt niet weergegeven onder het **menu Maken.**|
|Teams|Gebruiker kan geen team maken met een nieuwe groep, maar kan wel een team maken dat een bestaande groep gebruikt.<br><br>**Een teamknop** maken wordt vervangen door **Team maken vanuit een groep.**|
|Yammer|**Een groepsoptie** maken wordt verwijderd uit de hoofdnavigatie van Groepen/Community's.|

## <a name="services-interactions-with-groups"></a>Services-interacties met groepen

Zie de poster Groepen in Microsoft 365 voor informatie over verschillende typen groepen, hoe deze worden gemaakt en beheerd, en een paar aanbevelingen voor het beheer.

[![Miniatuurafbeelding van de infographic voor groepen](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

In de volgende tabel vindt u een overzicht van interacties tussen Microsoft 365 Groepen en verschillende services:

|Product|Functies|Doet de service<br>bestaan zonder een groep?|Kan de service<br>een groep maken?|Wordt het verwijderen van de<br>exemplaar verwijdert u de groep?|
|:---|:---|:---|:---|:---|
|Azure AD|Lidmaatschap, groepsbesturingselementen, Gasten|Ja|Ja|Ja|
|Exchange|Agenda, postvak|Ja|Ja|Ja|
|Forms|Formulier|Ja|Nee|Nee|
|OneNote|Notitieblok|Ja|Nee|Nee|
|Planner|Taakbord|Nee|Ja|Ja|
|Power Apps-app|App|Ja|Nee|Nee|
|Power Automate|Werkstroom|Ja|Nee|Nee|
|Power BI (klassiek)|Workspace|Nee|Ja|Ja|
|Power BI (nieuw)|Workspace|Ja|Nee|Ja|
|Project voor het web|Projectplan|Ja|Ja|Nee|
|Roadmap|Roadmap|Ja|Ja|Nee|
|SharePoint|Site|Ja|Ja|Ja|
|Stream|Kanaal, video|Ja|Ja|Ja|
|Teams|Team|Nee|Ja|Ja|
|Yammer|Groep|Ja|Ja|Ja|

Hoewel de bovenstaande tabel een overzicht op hoog niveau biedt van groepsinteracties met Microsoft 365-services, zijn er een aantal nuances en fijne kneepjes die u moet begrijpen. In de volgende secties wordt uitgebreider gereviewd naar de specifieke werkbelastingen en de interacties met groepen.

## <a name="azure-ad"></a>Azure AD

Azure AD biedt de onderliggende mogelijkheden voor identiteitsbeheer in Microsoft 365.

**Belangrijke functies die aan Groepen worden geleverd**

- Groepslidmaatschap
- Naamgevingsbeleid
- Vervalbeleid
- Gasten
- Beperking van het maken van groepen

**Kan Azure AD een groep maken?**

Ja, Microsoft 365 Groepen kunnen worden gemaakt vanuit Azure AD via de beheerwebportal, via PowerShell of Graph API.

**Bestaat Azure AD zonder een groep?**

Ja, Azure AD voert een groot aantal services uit die geen relatie hebben met Microsoft 365 Groepen. Elke Microsoft 365-groep wordt weergegeven als een object in Azure AD.

**Kunnen er meerdere exemplaren van Azure AD per groep zijn?**

Nee, er is slechts één exemplaar van Azure AD.

**Kan Azure AD worden gekoppeld aan meerdere groepen?**

Ja, omdat Azure AD het onderliggende platform is dat de groepslidmaatschapsservice biedt.

**Kan de associatie van Azure AD met een groep veranderen?**

Nee, Azure AD is het onderliggende platform waar groepen bestaan.

**Wordt de groep verwijderd als u het exemplaar verwijdert?**

Als u de groep verwijdert in Azure AD, worden relevante aan de groep gekoppelde services en inhoud verwijderd.

## <a name="teams"></a>Teams

Teams is een chatwerkruimte die is gericht op het verbeteren van de samenwerking door een unieke interface te bieden voor interactie met diverse microsoft- en externe services.

Wanneer een team wordt gemaakt, zijn het postvak en de agenda die zijn gekoppeld aan de Microsoft 365-groep standaard verborgen in zowel de algemene adreslijst in Exchange als Outlook. Dit kan handmatig worden overgenomen door een beheerder als de gebruiker zowel Outlook als Teams in dezelfde Microsoft 365-groep wil gebruiken.

**Belangrijke functies die aan Groepen worden geleverd**

- Gesprekken
- Kanalen & tabbladen
- Vergaderingen

**Kan Teams een groep maken?**

Ja, als u een nieuw team maakt, maakt u een nieuwe Microsoft 365-groep. Het is ook mogelijk om een team te maken voor een bestaande groep die momenteel geen team heeft.

**Bestaan teams zonder groep?**

Nee, het is niet mogelijk dat een team bestaat zonder een groep.

**Kunnen er meerdere teams per groep zijn?**

Nee, de relatie tussen een team en een groep is 1:1.

**Kan een team aan meerdere groepen worden gekoppeld?**

Nee, het team zelf kan alleen aan één groep worden gekoppeld.

**Kan de samenwerking van een team met een groep veranderen?**

Nee, het team kan alleen worden gekoppeld aan de groep waaraan het oorspronkelijk is gekoppeld.

**Wordt de groep verwijderd als u het team verwijdert?**

Ja, als u het team in Microsoft Teams verwijdert, worden de groep, de aan de groep gekoppelde services en de inhoud verwijderd.

## <a name="exchange"></a>Exchange

Exchange Online biedt berichten, agenda' s, contactpersonen en bijbehorende functionaliteit. In de context van een groep is slechts één resource gekoppeld, in tegenstelling tot een heel service-exemplaar.

**Belangrijke functies die aan Groepen worden geleverd**

- Postvak en agenda
- Mogelijkheid om alle groepsleden een e-mail te sturen
- Opslag van Teams-kanaalgesprekken voor eDiscovery-doeleinden, opmerkingen van Planner

**Kan Exchange een groep maken?**

Ja, het is mogelijk om een groep te maken vanuit het Exchange Online-beheercentrum en vanuit Outlook. U kunt ook Exchange-distributielijsten converteren naar Microsoft 365-groepen.

**Bestaat Exchange zonder groep?**

Ja, Exchange Online biedt een aantal services, waaronder gedeelde postvakken en agenda's, zonder enige groepsorganisatie.

**Kunnen er meerdere exemplaren van Exchange-postvakken of agenda's per groep zijn?**

Nee, er kan slechts één Exchange Online-postvak en een agenda voor een groep zijn.

**Kunnen Exchange-postvakken en agenda's aan meerdere groepen worden gekoppeld?**

Nee, het postvak en de agenda hebben een 1:1-relatie met de groep. Het is mogelijk om het postvak te delen met andere gebruikers of groepen, maar hiermee wordt geen enkele vorm van service-associatie tot stand brengen.

**Kan de associatie van het Exchange-postvak of de agenda met een groep worden gewijzigd?**

Nee, het postvak en de agenda kunnen niet worden gewijzigd in een andere groep. De inhoud kan echter van het ene postvak naar het andere worden verplaatst in Outlook of met behulp van een hulpprogramma van derden.

**Wordt de groep verwijderd als u het postvak verwijdert?**

Ja, als u het postvak in Exchange verwijdert, worden de groep en de aan de groep gekoppelde services en inhoud verwijderd.

## <a name="forms"></a>Forms

Forms bevat webenquêtes en toetsvragen.

**Belangrijke functies voor groepen**

- Eigendom van formulieren

**Kan Formulieren een groep maken?**

Nee, formulieren kunnen geen groep maken.

**Bestaan formulieren zonder groep?**

Ja, enquêtes en toetsvragen kunnen rechtstreeks in het account van een eindgebruiker worden gemaakt.

**Kunnen er meerdere formulieren per groep zijn?**

Ja, er kunnen meerdere formulieren zijn gekoppeld aan een groep.

**Kunnen formulieren aan meerdere groepen worden gekoppeld?**

Nee, een formulier kan alleen aan één groep worden gekoppeld.

**Kan de associatie van een formulier met een groep veranderen?**

Nee, wanneer een formulier is gekoppeld aan een groep (rechtstreeks gemaakt binnen of eigendom overgedragen van een persoon), kan het niet worden verplaatst naar een andere groep.

**Wordt de groep verwijderd als u het formulier verwijdert?**

Nee, het is niet mogelijk om een groep te verwijderen uit de interface Formulieren, alleen afzonderlijke formulieren.

## <a name="onenote"></a>OneNote

OneNote is een digitale notitiebloktoepassing. Het OneNote-notitieblok dat met een groep is gemaakt, is een bestand op de bijbehorende SharePoint-site in plaats van een service met een groep.

**Belangrijke functies voor groepen**

- Gedeeld notitieblok (opgeslagen in de Aan de groep gekoppelde SharePoint-bibliotheek)

**Kan OneNote een groep maken?**

Nee, de OneNote-toepassing kan geen groep maken.

**Bestaan OneNote-notitieblokken zonder groep?**

Ja, notitieblokken kunnen rechtstreeks worden gemaakt in OneDrive of op andere gedeelde locaties.

**Kunnen er meerdere OneNote-notitieblokken per groep zijn?**

Ja, een notitieblok wordt standaard gemaakt en anderen kunnen worden toegevoegd, maar elke koppeling naar OneNote vanuit aan de groep gekoppelde services gaat altijd naar het standaardnotitieblok.

**Kan een OneNote-notitieblok aan meerdere groepen worden gekoppeld?**

Nee, het notitieblok wordt opgeslagen in de aan de groep gekoppelde SharePoint-sitebibliotheek en gekoppeld vanuit verschillende interfaces. Het kan echter op dezelfde manier worden gedeeld met andere groepen als met personen.

**Kan de band tussen het notitieblok en een groep worden gewijzigd?**

Nee, het notitieblok zelf is gekoppeld aan de groep en kan rechtstreeks worden gebruikt vanuit andere services die met de groep zijn verbonden, maar de inhoud kan worden verplaatst van het ene notitieblok naar het andere in de OneNote-toepassing.

**Wordt de groep verwijderd als u het notitieblok verwijdert?**

Nee, maar als het OneNote-notitieblok wordt verwijderd, zijn er mogelijk verbroken koppelingen in sommige aan de groep gekoppelde services.

## <a name="planner"></a>Planner

Planner is een lichtgewicht groepstaakbeheerservice.

**Belangrijke functies voor groepen**

- Bord voor het beheren van groepstaken

**Kan Planner een groep maken?**

Ja, als u een plan maakt, wordt er een nieuwe groep gemaakt.

**Bestaat een Planner-bord zonder groep?**

Nee, een plan moet aan een groep zijn gekoppeld.

**Kunnen er meerdere abonnementen per groep zijn?**

Ja, er kunnen meerdere abonnementen per groep zijn.

**Kan een abonnement aan meerdere groepen worden gekoppeld?**

Nee, een plan is alleen afhankelijk van het groepslidmaatschap om de toegang te bepalen.

**Kan de samenwerking tussen een plan en een groep worden gewijzigd?**

Nee, maar als u een plan kopieert, wordt er een nieuwe groep gemaakt.

> [!NOTE]
> Een groep die door een andere toepassing is gemaakt, wordt niet automatisch in Planner voor een gebruiker gebruikt. Als ze het bord in eerste instantie willen openen, moeten ze het openen vanuit een andere op groep gebaseerde interface, zoals Outlook.

**Wordt de groep verwijderd als u het plan verwijdert?**

Ja, als u het plan verwijdert, worden de aan de groep gekoppelde services en inhoud verwijderd.

## <a name="power-apps"></a>Power Apps

Power Apps biedt een canvas voor app-ontwikkeling zonder code.

**Belangrijke functies die aan Groepen worden geleverd**

- Apps kunnen worden gedeeld met een groep die moet worden uitgevoerd en gewijzigd

**Kan Power Apps een groep maken?**

Nee, Power Apps kan geen Microsoft 365-groep maken.

**Bestaan Power Apps zonder groep?**

Ja, apps kunnen worden gemaakt in Power Apps en zich binnen het makersaccount bevinden totdat ze worden gedeeld of gepubliceerd.

**Kunnen er meerdere apps per groep zijn?**

Ja, er kunnen meerdere apps met een groep worden gedeeld.

**Kunnen apps aan meerdere groepen worden gekoppeld?**

Ja, een app kan worden gedeeld met meerdere groepen.

**Kan de associatie van een app met een groep veranderen?**

Ja, omdat de relatie tussen Power Apps en een Microsoft 365-groep alleen wordt gedeeld: de app bevindt zich nog steeds bij de maker.

> [!IMPORTANT]
> [Groepen moeten beveiligings ingeschakeld zijn voordat apps met hen kunnen worden gedeeld.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)

**Wordt de groep verwijderd als u de app verwijdert?**

Nee, de apps zijn niet verbonden met de groep, anders dan dat ze met hen worden gedeeld.

## <a name="power-automate"></a>Power Automate

Power Automate (voorheen Bekend als Microsoft Flow) biedt werkstromen en automatiseringsservices.

**Belangrijke functies voor groepen**

- Werkstromen kunnen worden gedeeld met een groep die moet worden uitgevoerd en gewijzigd.

**Kan Power Automate een groep maken?**

Nee, Power Automate kan geen Microsoft 365-groep maken in de context van het gekoppeld zijn aan een groep.

Het is echter mogelijk om een stroom te maken die verschillende bewerkingen uitvoert, zoals het maken van een Azure AD-beveiligingsgroep of het bijwerken van het lidmaatschap van een Microsoft 365-groep.

**Bestaan er stromen zonder groep?**

Ja, stromen kunnen worden gemaakt in Power Automate en zich binnen het makersaccount bevinden totdat ze worden gedeeld of gepubliceerd.

**Kunnen er meerdere stromen per groep zijn?**

Ja, er kunnen meerdere stromen worden gedeeld met een groep.

**Kan een stroom aan meerdere groepen worden gekoppeld?**

Ja, een stroom kan worden gedeeld met meerdere groepen.

**Kan de band tussen een stroom en een groep worden gewijzigd?**

Ja, omdat de relatie tussen Power Automate en een Microsoft 365-groep alleen wordt gedeeld: de stroom bevindt zich nog steeds bij de maker.

**Wordt de groep verwijderd door een stroom te verwijderen?**

Nee, net als Power Apps zijn de stromen niet verbonden met de groep, anders dan dat ze met hen worden gedeeld.

## <a name="power-bi-classic"></a>Power BI (klassiek)

Power BI biedt interactieve dashboards en rapporten op gegevens gebaseerde.

**Belangrijke functies voor groepen**

- Gegevensrapportage

**Kan Power BI een groep maken?**

Ja, als u een klassieke werkruimte maakt, maakt u een Microsoft 365-groep.

**Bestaat een klassieke Power BI-werkruimte zonder een groep?**

Nee, [een klassieke werkruimte in Power BI moet zijn gekoppeld aan een groep.](/power-bi/collaborate-share/service-collaborate-power-bi-workspace)

**Kunnen er meerdere Power BI-werkruimten per groep zijn?**

Nee, de relatie tussen een klassieke werkruimte en een groep is 1:1.

**Kan een werkruimte aan meerdere groepen worden gekoppeld?**

Technisch nee, terwijl de klassieke werkruimte met de groep wordt gemaakt, kan de inhoud buiten de groep worden gedeeld met gebruikers en beveiligingsgroepen.

**Kan de samenwerking tussen de werkruimte en een groep worden gewijzigd?**

Nee, de klassieke werkruimte zelf is gekoppeld aan de groep, maar de inhoud kan van de ene werkruimte naar de andere worden verplaatst binnen de Power BI-interface of door inhoud lokaal te exporteren.

**Wordt de groep verwijderd als u de werkruimte verwijdert?**

Ja, als u de werkruimte in Power BI verwijdert, worden aan de groep gekoppelde services en inhoud verwijderd.

## <a name="power-bi-new"></a>Power BI (nieuw)

Power BI biedt interactieve dashboards en rapporten op gegevens gebaseerde.

Als u een nieuwe werkruimte maakt in Power BI, wordt er geen Microsoft 365-groep gemaakt, maar maakt u op een andere manier een nieuwe (niet klassieke) werkruimte in Power BI.

**Belangrijke functies voor groepen**

- Gegevensrapportage

**Kan Power BI een groep maken?**

Nee, het is niet mogelijk om een Microsoft 365-groep te maken vanuit de nieuwe Power BI-interface.

**Bestaat de nieuwe Power BI-werkruimte zonder een groep?**

Ja, het is mogelijk om rapporten en werkruimten te maken in Power BI die niet zijn gekoppeld aan Microsoft 365-groepen.

**Kunnen er meerdere werkruimten per groep zijn?**

Ja, meerdere werkruimten die door Power BI zijn [gemaakt, kunnen met één groep worden gedeeld.](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)

**Kan een werkruimte aan meerdere groepen worden gekoppeld?**

Nee, een werkruimte die is gemaakt door Power BI, kan slechts aan één groep worden gekoppeld.

**Kan de samenwerking tussen een werkruimte en een groep worden gewijzigd?**

Ja en nee. Een werkruimte die door Power BI is gemaakt, kan slechts aan één groep tegelijk worden gekoppeld, maar kan de vereniging op elk moment wijzigen. Een werkruimte die door een groep in Power BI is gemaakt, is permanent aan die groep gekoppeld.

**Wordt de groep verwijderd als u de werkruimte verwijdert?**

Ja, als u de werkruimte in Power BI verwijdert, worden de aan de groep gekoppelde services en inhoud verwijderd.

## <a name="project-for-the-web"></a>Project voor het web

Project voor het web biedt de mogelijkheid om projectplannen, Gantt-diagrammen en routekaarten te maken.
Belangrijke functies die aan groepen worden geleverd.

- Projectplannen

**Kan Project voor het web een groep maken?**

Ja, het is mogelijk om rechtstreeks vanuit Project voor het web een nieuwe Microsoft 365-groep te maken.

**Bestaan projecten zonder groep?**

Ja, projecten kunnen bestaan zonder dat ze zijn gekoppeld aan een Microsoft 365-groep, maar voor taaktoewijzing is groepsorganisatie vereist.

**Kunnen er meerdere projecten per groep zijn?**

Ja, het is mogelijk om meerdere projecten in één groep te verbinden.

**Kan project aan meerdere groepen worden gekoppeld?**

Nee, een project kan alleen aan één groep worden gekoppeld.

**Kan de samenwerking tussen een project en een groep worden gewijzigd?**

Nee, wanneer de associatie met een groep tot stand is gebracht, kan deze niet meer worden gewijzigd.

**Wordt de groep verwijderd als u het project verwijdert?**

Nee, als u het project verwijdert in project voor het web, wordt de groep niet verwijderd.

## <a name="roadmap"></a>Roadmap

Roadmap biedt de mogelijkheid om project roadmaps te maken met Project voor het web en Project Online.

**Belangrijke functies die aan Groepen worden geleverd**

- Routekaarten voor projecten

**Kan Roadmap een groep maken?**

Ja, het is mogelijk om rechtstreeks vanuit roadmap een nieuwe Microsoft 365-groep te maken.

**Bestaat Roadmap zonder groep?**

Ja, routekaarten kunnen bestaan zonder dat ze zijn gekoppeld aan een Microsoft 365-groep, maar voor het delen van de routekaart is groepsorganisatie vereist.

**Kunnen er meerdere routekaarten per groep zijn?**

Ja, het is mogelijk om meerdere routekaarten aan één groep te koppelen.

**Kan een routekaart aan meerdere groepen worden gekoppeld?**

Nee, een routekaart kan alleen aan één groep worden gekoppeld.

**Kan de samenwerking tussen een routekaart en een groep veranderen?**

Nee, wanneer de associatie met een groep tot stand is gebracht, kan deze niet meer worden gewijzigd.

**Wordt de groep verwijderd als u de routekaart verwijdert?**

Nee, als u de routekaart verwijdert, wordt de groep niet verwijderd.

## <a name="sharepoint"></a>SharePoint

SharePoint is een webplatform voor inhoudsbeheer dat onder andere opslagservices levert voor een aantal Microsoft 365-services.

**Belangrijke functies die aan Groepen worden geleverd**

- Documentbibliotheek
- Bibliotheek voor opslag van OneNote-notitieblok
- Opslag van Teams-wikibestanden

**Kan SharePoint een groep maken?**

Ja, als u een teamsite maakt in SharePoint, wordt standaard een Microsoft 365-groep gemaakt. Het is ook mogelijk om een groep en eventueel een team voor een bestaande site te maken.

**Bestaan SharePoint-sites zonder een groep?**

Ja, SharePoint biedt een aantal services en sites die niet aan de groep zijn gekoppeld, zoals communicatie- en hubsites. 

**Kunnen er meerdere sites per groep zijn?**

Nee, er kan slechts één site per groep zijn. Privékanalen in Teams gebruiken extra sites die niet zijn verbonden met de groep.

**Kunnen sites aan meerdere groepen worden gekoppeld?**

Technisch niet, maar terwijl een site met een groep wordt gemaakt, kan de inhoud worden gedeeld met andere groepen.

**Kan de associatie van een site met een groep veranderen?**

Nee, de site zelf is gekoppeld aan de groep, maar de inhoud kan van de ene site naar de andere worden verplaatst binnen de SharePoint-interface, door inhoud lokaal te exporteren of door een hulpprogramma van derden te gebruiken.

**Wordt de groep verwijderd als u de site verwijdert?**

Ja, als u de site in SharePoint verwijdert, worden aan de groep gekoppelde services en inhoud verwijderd.

## <a name="stream"></a>Stream

Microsoft Stream is een platform voor het hosten en delen van video's.

**Belangrijke functies die aan Groepen worden geleverd**

- Videoopslag
- Opname van Teams-vergadering
- Videokanalen

**Kan Stream een groep maken?**

Ja, het is mogelijk om rechtstreeks vanuit Stream een nieuwe Microsoft 365-groep te maken.

**Bestaat Stream zonder groep?**

Ja, videokanalen en video's kunnen aanwezig zijn in Stream zonder aan een groep te zijn gekoppeld.

**Kunnen er meerdere video's en kanalen per groep zijn?**

Ja, er kunnen meerdere video's en kanalen in elke groep zijn.

**Kan een video of kanaal aan meerdere groepen worden gekoppeld?**

Ja, terwijl een video of kanaal wordt gemaakt met een groep, kan deze worden gedeeld met andere groepen.

**Kan de associatie met een groep worden gewijzigd?**

Ja en nee; video's in Stream zijn eigendom van de oorspronkelijke uploader of vergaderingsrecorder en kunnen dus aan elke groep worden gekoppeld, maar videokanalen kunnen alleen worden gekoppeld aan de groep waarin ze oorspronkelijk zijn gemaakt.

**Wordt de groep verwijderd door video's of kanalen te verwijderen?**

Nee, als u video's of kanalen verwijdert, wordt de groep niet verwijderd. Als u de groep echter zelf verwijdert in Stream, worden aan de groep gekoppelde services en inhoud verwijderd, met uitzondering van de werkelijke video's.

## <a name="yammer"></a>Yammer

Yammer is een sociaal platform voor ondernemingen dat is ontworpen om betrokkenheid van de community binnen en tussen organisaties te bevorderen.

Als u een community (voorheen 'groep' genoemd) maakt in Yammer, wordt een postvak gemaakt, maar op dit moment wordt dit niet gebruikt.

Een Microsoft 365-groep die is gekoppeld aan Yammer, kan niet worden gebruikt met een team in Microsoft Teams.

**Belangrijke functies die aan Groepen worden geleverd**

- Gespreksgebied

**Kan Yammer een Microsoft 365-groep maken?**

Ja, als de platforms zijn verbonden en de gebruiker de mogelijkheid heeft om een groep te maken, wordt er een nieuwe Microsoft 365-groep in Yammer aan het maken.

Een Yammer-groep met de bijbehorende Microsoft 365-groep kan niet worden gemaakt in een andere interface of service dan Yammer zelf.

**Bestaat een Yammer-groep zonder een Microsoft 365-groep?**

Ja, het is mogelijk om een Yammer-groep te maken zonder een Microsoft 365-groep.

Als het Yammer-platform niet is verbonden met Microsoft 365-groepen of als gebruikers niet de mogelijkheid hebben om een Microsoft 365-groep te maken, worden Yammer-groepen gemaakt zonder een Microsoft 365-groepsorganisatie.

**Kunnen er meerdere Yammer-groepen per Microsoft 365-groep zijn?**

Nee, de relatie tussen een Yammer-groep en een Microsoft 365-groep is 1:1.

**Kan een Yammer-groep worden gekoppeld aan meerdere Microsoft 365-groepen?**

Nee, de Yammer-groep kan alleen worden gekoppeld aan één Microsoft 365-groep. Het is mogelijk dat berichten worden gedeeld met of verplaatst naar andere Yammer-groepen.

**Kan de samenwerking van een Yammer-groep met een Microsoft 365-groep worden gewijzigd?**

Nee, de Yammer-groep kan alleen worden gekoppeld aan de Microsoft 365-groep waaraan de groep oorspronkelijk is gekoppeld.

**Wordt de Microsoft 365-groep verwijderd als u de Yammer-groep verwijdert?**

Ja, als u de groep in Yammer verwijdert, worden gerelateerde Microsoft-groep en aan de groep gekoppelde services en inhoud verwijderd.

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)