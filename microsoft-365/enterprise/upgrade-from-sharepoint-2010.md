---
title: Een upgrade uitvoeren van SharePoint 2010
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: Informatie en resources zoeken voor een upgrade van SharePoint 2010 en SharePoint Server 2010. Ondersteuning voor beide uiteinden van 13 april 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fba095a15164f8a09ce1e0a1cbd5ee9cd298aa74
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519761"
---
# <a name="upgrading-from-sharepoint-2010"></a>Een upgrade uitvoeren van SharePoint 2010

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft SharePoint 2010 en SharePoint Server 2010 wordt beëindigd met de ondersteuning op **13 April 2021**. Dit artikel bevat informatiebronnen die u helpen bij het migreren van uw bestaande SharePoint Server 2010-gegevens naar SharePoint Online in Microsoft 365 of om uw on-premises SharePoint Server 2010-omgeving bij te werken.

## <a name="what-is-end-of-support"></a>Wat is het *einde van de ondersteuning*?

De meeste Microsoft-producten hebben een ondersteunings levensduur, waaronder nieuwe functies, foutoplossingen, beveiligingsoplossingen, enzovoort. Na de einddatum van de ondersteuning werkt het product niet meer, maar Microsoft biedt niet langer:

- Technische ondersteuning voor problemen die kunnen optreden.

- Oplossingen voor problemen die gevolgen kunnen hebben voor de stabiliteit en bruikbaarheid van de server.

- Beveiligingscorrecties voor beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsproblemen.

- Tijdzone-updates.

Dit betekent dat er geen updates, patches of oplossingen voor het product zijn, waaronder beveiligingspatches en fixes. Microsoft Support heeft de ondersteuning voor de ondersteuning van alle recente versies volledig verschoven.

Als het einde van de ondersteuning van SharePoint Server 2010 aanpakt, verwijdert u de gegevens die u niet meer nodig hebt voordat u het product upgradet en uw belangrijke gegevens migreert.

> [!NOTE]
> Een software levensduur duurt doorgaans tien jaar vanaf de eerste release. [Microsoft Solution Providers](https://go.microsoft.com/fwlink/?linkid=841249) kunnen u helpen bij een upgrade naar de volgende versie van de software of naar microsoft 365-migratie (of beide) migreren. Zorg ervoor dat u zich bewust bent van end-of-ondersteunings datums voor kritieke, onderliggende technologieën, met name voor de versie van Microsoft SQL Server die u met SharePoint gebruikt. Voor meer informatie raadpleegt u het [beleid voor vaste levens regels](https://support.microsoft.com/help/14085).

## <a name="plan-ahead"></a>Voorspringen

Controleer de datums die de ondersteuning voor de [product levenscyclus site](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)ondersteunen. Plan de upgrades of migraties met deze datums in gedachten. Houd er rekening mee dat uw product *niet meer werkt* op de vermeldings datum. Aangezien de installatie na deze datum niet meer wordt hersteld, moet u een soepele overgang naar de volgende versie van het productplannen.

Met deze matrix kunt u een cursus uitzetten onder migratie opties:

|Einde van ondersteunings product|Uitstekend |Doen|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (on-premises)|SharePoint Online|
||SharePoint Server 2013 Hybrid met SharePoint Online|SharePoint Server 2016 (on-premises)|
|||Hybride zoeken voor de SharePoint-Cloud|

Als u een optie op het lage einde van de schaal kiest (goed), moet u eerst plannen voor een andere upgrade, binnenkort na de migratie van SharePoint Server 2010.

Dit zijn de drie paden die u kunt nemen om te voorkomen dat de ondersteuning van SharePoint Server 2010 wordt beëindigd.

![Upgradepaden van SharePoint Server 2010](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> Het einde van de ondersteuning voor SharePoint Server 2010 en SharePoint Foundation 2010 is op dit moment gepland voor 13 april 2021. Zorg er wel voor dat u de [product levenscyclus site](https://support.microsoft.com/lifecycle) controleert op de meest recente datums.

## <a name="whats-next"></a>En nu?

SharePoint Server 2013 en SharePoint Foundation 2013 kunnen on-premises worden geïnstalleerd op uw eigen servers. U kunt ook SharePoint Online gebruiken, een online service die onderdeel is van Microsoft 365. U kunt kiezen voor:

- Migreren naar SharePoint Online.

- Voer on-premises een upgrade van SharePoint Server of SharePoint Foundation uit.

- Voer beide bovenstaande handelingen uit.

- Implementeer een [hybride SharePoint-](https://docs.microsoft.com/sharepoint/hybrid/hybrid) oplossing.

Let op de verborgen kosten voor het onderhoud van een serverfarm, waaronder het onderhoud of migreren van aanpassingen en het bijwerken van hardware. Als u de rekening hebt gehouden met deze factoren, is het eenvoudiger om on-premises on-premises te upgraden. Als u de farm uitvoert op oudere SharePoint-servers zonder een zware aanpassing, kunt u gebruikmaken van een geplande migratie naar SharePoint Online. Als u een on-premises SharePoint Server-omgeving gebruikt, kunt u overwegen om bepaalde gegevens te verplaatsen in SharePoint Online om de overhead van hardware management te beperken.

> [!NOTE]
> SharePoint-beheerders kunnen een abonnement op Microsoft 365 maken, nieuwe SharePoint Online-sites installeren en vervolgens op de site van SharePoint Server 2010 wissen, zodat ze alleen essentiële documenten met de nieuwe sites worden gemaakt. Vervolgens kunnen de resterende gegevens van de SharePoint Server 2010-site worden verwaterd in on-premises archieven.

|SharePoint Online|SharePoint Server on-premises|
|---|---|
|Hoge kosten voor tijd (planning/uitvoering/verificatie)|Hoge kosten voor tijd (planning/uitvoering/verificatie)|
|Lagere kosten voor financiële middelen (geen hardware aankopen)|Hogere kosten in fondsen (hardware aankopen)|
|Eenmalige kosten in migratie|Eenmalige kosten die worden herhaald per toekomstige migratie|
|Lage totale eigendomskosten/onderhoud|Grote totale eigendomskosten/onderhoud|

Een eenmalige overstap naar Microsoft 365 kost een hogere kosten wanneer u gegevens organiseert en opgeeft wat u wilt doen met de Cloud en wat u achter moet laten. Wanneer uw gegevens zijn gemigreerd, worden toekomstige upgrades automatisch gewijzigd, omdat u niet langer de hardware-en software-updates hoeft te beheren. En de hoeveelheid tijd van uw farm wordt ondersteund door een [Microsoft Service Level Agreement (Sla)](https://go.microsoft.com/fwlink/?linkid=843153).

### <a name="migrate-to-sharepoint-online"></a>Migreren naar SharePoint Online

Zorg ervoor dat SharePoint Online alle benodigde functies biedt. Zie de beschrijving van de [SharePoint-Service](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

U kunt geen rechtstreekse migratie van SharePoint Server 2010 (of SharePoint Foundation 2010) naar SharePoint Online. Zo veel migratie werken handmatig. Maar in deze stap kunt u gegevens en sites die u niet meer nodig hebt voor de verhuizing, weghalen via de verkoopkans. U kunt andere gegevens in de opslag archivering. 

Houd er rekening mee dat de ondersteuning van SharePoint Server 2010 en SharePoint Foundation 2010 helemaal niet wordt beëindigd. Beheerders kunnen beheerders een punt hebben wanneer SharePoint nog steeds wordt uitgevoerd als hun klanten vergeten bepaalde gegevens te verplaatsen.

Als u een upgrade uitvoert naar SharePoint Server 2013 of SharePoint Server 2016 en ervoor kiest om gegevens op te slaan in SharePoint Online, kunt u de [SharePoint MIGRATION API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) gebruiken om gegevens te migreren naar OneDrive voor bedrijven.

|SharePoint Online-voordeel|Nadeel voor SharePoint Online|
|---|---|
|Microsoft levert SPO-hardware en al het beheer van de hardware.|De beschikbare functies kunnen verschillen van SharePoint Server on-premises en SPO.|
|U bent de globale beheerder van uw abonnement en u kunt beheerders aan SPO-sites toewijzen.|Sommige acties die voor een farmbeheerder in SharePoint Server on-premises beschikbaar zijn, bestaan niet (of zijn niet nodig) in de SharePoint-beheerdersrol in Microsoft 365. Maar SharePoint-beheer, beheer van de siteverzameling en site eigendom zijn lokale voor uw organisatie.|
|Patches, oplossingen en updates in onderliggende hardware en software worden door Microsoft toegepast, waaronder SQL-servers waarop SharePoint Online wordt uitgevoerd.|Aangezien u geen toegang hebt tot het onderliggende bestandssysteem in de service, is aanpassing beperkt.|
|Microsoft publiceert [Service Level Agreements](https://go.microsoft.com/fwlink/?linkid=843153) en zet snel de serviceniveau van een abonnement.|Back-up-en herstelopties en andere opties voor herstellen worden automatisch door de service in SharePoint Online. Back-ups worden overschreven indien niet gebruikt.|
|Het testen van de beveiliging en het afstemmen van de serverprestaties worden in de service doorlopend uitgevoerd door Microsoft.|Wijzigingen in de gebruikersinterface en andere SharePoint-functies worden geïnstalleerd door de service en moeten mogelijk worden in-of uitgeschakeld.|
|Microsoft 365 voldoet aan een groot aantal industriestandaarden: [Microsoft compliance-aanbiedingen](https://go.microsoft.com/fwlink/?linkid=843165).|[FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) hulp voor migratie is beperkt.  <br/> Veel van de upgrade is de handleiding of via de SPO-migratie-API die wordt beschreven in de [SharePoint Online-en OneDrive Migration content-wegwijzer](https://go.microsoft.com/fwlink/?linkid=843184).|
|Microsoft-ondersteuningstechnici en Datacenter medewerkers hebben geen beperkte beheerderstoegang tot uw abonnement.|Er kunnen extra kosten zijn als de hardware-infrastructuur moet worden bijgewerkt voor de ondersteuning van de nieuwere versie van SharePoint, of als een secundaire Farm is vereist voor de upgrade.|
|Solution Providers kunnen helpen met de eenmalige taak van het migreren van uw gegevens naar SharePoint Online.|Niet alle wijzigingen in SharePoint Online zijn binnen uw besturingselement. Na de migratie kunnen ontwerp verschillen in menu's, Bibliotheken en andere functies tijdelijk van invloed zijn op de bruikbaarheid.|
|Online producten worden automatisch bijgewerkt in de service. Functies die kunnen worden weergegeven, maar er zijn geen echt ondersteunings levensduur.|Er is een einde-ondersteunings levensduur voor SharePoint Server of SharePoint Foundation en onderliggende SQL servers.|

Als u hebt besloten een nieuwe Microsoft 365-site te maken en deze zo nodig handmatig te migreren, controleert u de [Opties van Microsoft 365](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>SharePoint Server on-premises upgraden

Vanaf SharePoint Server 2019 moeten de upgrades  *serieel* zijn. Er is geen manier om een upgrade van SharePoint Server 2010 naar SharePoint Server 2016 of SharePoint 2019 rechtstreeks uit te voeren. Serieel upgrade traject:

- SharePoint Server 2010 \> SharePoint server 2013 \> SharePoint Server 2016

Het duurt langer voordat u het volledige pad van SharePoint 2010 naar SharePoint Server 2016 volgt. Voor de upgrades gelden de kosten voor hardware (SQL servers moet ook worden bijgewerkt), software en beheer. Het kan ook zijn dat aanpassingen moeten worden bijgewerkt of zelfs moeten worden afgebroken. Als u een upgrade van uw SharePoint server-farm uitvoert, moet u ervoor zorgen dat u belangrijke aanpassingen documenteert.

> [!NOTE]
> Het is mogelijk om uw end-to-support SharePoint 2010-Farm te behouden, een SharePoint Server 2016-Farm te installeren op nieuwe hardware (zodat de afzonderlijke Farms gelijktijdig worden uitgevoerd) en vervolgens een handmatige migratie van inhoud plannen en uitvoeren (bijvoorbeeld om de inhoud te downloaden en opnieuw te uploaden). Deze handmatig verplaatsingen zijn mogelijk niet beschikbaar voor deze handmatige verplaatsingen, zoals documenten die afkomstig zijn van 2010 en die een recent gewijzigde account hebben met de alias van het account dat het handmatig vernieuwt. Daarnaast moet een deel van het werk, zoals het opnieuw maken van sites, subsites, machtigingen en lijst structuren, op een later tijdstip plaatsvinden. Zorg ervoor dat u de omgeving opschoont voordat u een upgrade uitvoert. U kunt ook rekening houden met de gegevens die u in de opslagruimte kunt zetten of niet langer nodig hebt. Dit kan de gevolgen van de migratie verminderen. Zorg ervoor dat uw bestaande farm functioneel is voordat u een upgrade uitvoert, en (zeker) voordat u met de Commissie verdergaat.

Vergeet niet de *ondersteunde en niet-ondersteunde upgradepaden* te controleren:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Als u *aanpassingen* hebt, is het essentieel dat u voor elke stap in het migratie traject de volgende stappen plant:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|On-premises voordeel|Nadeel van on-premises|
|---|---|
|Volledig beheer van alle aspecten van uw SharePoint-farm (en de bijbehorende SQL), van de serverhardware.|Alle onderbrekingen en fixes vormen de verantwoordelijkheid van uw bedrijf. U kunt ook Microsoft ondersteuning bieden voor ondersteuning als uw product niet meer aan de kant van de ondersteuning valt.|
|Volledige functieset van SharePoint Server on-premises met de mogelijkheid om via hybride verbinding te maken tussen uw on-premises Farm en een SharePoint Online-abonnement.|Upgrades, patches, beveiligingsoplossingen, hardware-upgrades en het onderhoud van SharePoint Server en de SQL-farm worden on-premises beheerd.|
|Volledige toegang voor betere aanpassingsopties dan met SharePoint Online.|[Microsoft compliance-aanbiedingen](https://go.microsoft.com/fwlink/?linkid=843165) moeten handmatig on-premises worden geconfigureerd.|
|Het testen van de beveiliging en het afstemmen van de serverprestaties worden uitgevoerd onder uw besturingselement.|In Microsoft 365 kunnen functies voor SharePoint Online beschikbaar worden gemaakt die niet compatibel zijn met SharePoint Server on-premises.|
|Solution Providers kunnen helpen bij het migreren van gegevens naar de volgende versie van SharePoint Server (en daarbuiten).|Op uw SharePoint Server-sites worden niet automatisch [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) certificaten gebruikt zoals deze worden weergegeven in SharePoint Online.|
|Volledig beheer van de naamgevingsconventies, back-up en herstel en andere herstelopties in SharePoint Server on-premises.|SharePoint Server on-premises is gevoelig voor productlevenscyclus.|

### <a name="upgrade-resources"></a>Bronnen voor upgraden

Begin met het vergelijken van hardware-en softwarevereisten. Als uw huidige omgeving niet aan de basisvereisten voldoet, moet u mogelijk eerst de hardware upgraden naar de farm of SQL servers. 

U kunt ervoor kiezen om een aantal van uw sites te verplaatsen naar de hardware van SharePoint Online groen. Wanneer u de beoordeling hebt uitgevoerd, kunt u de ondersteunde upgradepaden en-methoden volgen.

- *Hardware-en softwarevereisten voor:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Software grenzen en-limieten voor:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *Overzicht van het upgradeproces voor:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Een hybride oplossing maken met SharePoint Online en SharePoint Server on-premises

Een hybride installatie biedt de beste online on-premises en online voor sommige migratie behoeften. U kunt SharePoint Server 2013, 2016 of 2019 Farms met SharePoint Online verbinden met SharePoint Online voor het maken van een hybride versie van SharePoint: [meer informatie over hybride SharePoint-oplossingen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).

Als een hybride SharePoint-server farm uw migratie doelstelling is, moet u bepalen welke sites en gebruikers online overstappen en welke on-premises moeten blijven staan. Rangschikking van de inhoud van de SharePoint-server farm als hoog, normaal of laag risico voor uw bedrijf kan helpen met deze beslissing. U moet mogelijk alleen gebruikersaccounts voor aanmelding en de SharePoint Server-zoekindex delen met SharePoint Online. Dit kan echter niet helder zijn voordat u bespreekt met de manier waarop uw sites worden gebruikt. Als uw bedrijf later besluit om al uw inhoud te migreren naar SharePoint Online, kunt u alle resterende accounts en gegevens online verplaatsen en uw on-premises Farm ontmantelen. Beheer/beheer van de SharePoint-farm wordt vanaf dat moment uitgevoerd via Microsoft 365-consoles.

Zorg ervoor dat u vertrouwd bent met de bestaande soorten Hybrids en hoe u de verbinding configureert tussen uw on-premises SharePoint-farm en uw Microsoft 365-abonnement.

|Optie|Beschrijving|
|---|---|
|[Microsoft compliance-aanbiedingen](https://go.microsoft.com/fwlink/?linkid=843165).|[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) hulp voor migratie is beperkt.<br/><br/> Veel van de upgrade is de handleiding of via de SPO-migratie-API die wordt beschreven in de [SharePoint Online-en OneDrive Migration content-wegwijzer](https://go.microsoft.com/fwlink/?linkid=843184).|
|Microsoft-ondersteuningstechnici en Datacenter medewerkers hebben geen beperkte beheerderstoegang tot uw abonnement.|Er kunnen extra kosten in rekening worden gehouden als de hardware-infrastructuur moet worden bijgewerkt voor de ondersteuning van de nieuwere versie van SharePoint, of als een secundaire Farm is vereist.|
|Partners kunnen helpen met de eenmalige taak van het migreren van uw gegevens naar SharePoint Online.||
|Online producten worden automatisch bijgewerkt in de service. Functies die kunnen worden weergegeven, maar het einde van de ondersteuning is niet waar.||

Als u hebt besloten een nieuwe Microsoft 365-site te maken en deze zo nodig handmatig te migreren, controleert u de [Opties van Microsoft 365](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>SharePoint Server on-premises upgraden

U kunt geen versies van SharePoint-upgrades overslaan. Dit betekent dat als upgrades serieel gaat:

- SharePoint 2007 \> SharePoint server 2010 \> SharePoint Server 2013 \> sharepoint server 2016

U kunt als volgt het volledige pad van SharePoint 2007 naar SharePoint Server 2016 betekenen een belangrijke investering van tijd en de hardware (SQL servers moet ook worden geüpgraded), software en administratiekosten. Aanpassingen moeten worden bijgewerkt of gestaakt, op basis van de ernst van de functie.

> [!NOTE]
> Het is mogelijk om de einde-van de SharePoint-versie van SharePoint 2007 te behouden, een SharePoint Server 2016-Farm te installeren op nieuwe hardware (zodat de afzonderlijke Farms gelijktijdig worden weergegeven) en vervolgens een handmatige migratie van inhoud plannen en uitvoeren (bijvoorbeeld om de inhoud te downloaden en opnieuw te uploaden). Maar er zijn enkele nadelen voor deze handmatige verplaatsingen, zoals het verplaatsen van documenten die het laatst gewijzigde account vervangen door de alias van het account dat het handmatig verschuift. En veel werk moet eerder plaatsvinden, zoals het opnieuw maken van sites, subsites, machtigingen en lijst structuren. Houd in een willekeurige zaak rekening met welke gegevens u kunt overstappen of niet langer hoeft te zijn de gevolgen van de migratie te verminderen.

Zorg ervoor dat u de omgeving opschoont voordat u de upgrade uitvoert. Voordat u een upgrade uitvoert, moet u ervoor zorgen dat uw bestaande farm functioneel is voordat u de upgrade uitvoert.

Vergeet niet de *ondersteunde en niet-ondersteunde upgradepaden* te controleren:

- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Als u *aanpassingen* hebt, is het belangrijk om de upgrade voor elke stap in het migratie traject te plannen:

- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|On-premises Pro|On-premises con|
|---|---|
|Volledig beheer van alle aspecten van uw SharePoint-farm, vanaf de serverhardware.|Alle onderbrekingen en fixes vormen de verantwoordelijkheid van uw bedrijf. (Maar neem contact op met de ondersteuning van Microsoft als uw product niet meer aan de kant van de ondersteuning valt.)|
|Volledige functieset van SharePoint Server on-premises met de mogelijkheid om via hybride verbinding te maken tussen uw on-premises Farm en een SharePoint Online-abonnement.|Upgrades, patches, beveiligingsoplossingen en alles onderhoud van SharePoint Server worden on-premises beheerd.|
|Volledige toegang voor betere aanpassingen.|[Microsoft compliance-aanbiedingen](https://go.microsoft.com/fwlink/?linkid=843165) moeten handmatig on-premises worden geconfigureerd.|
|Het testen van de beveiliging en het afstemmen van de serverprestaties worden via uw besturingselement op uw bedrijf uitgevoerd.|In Microsoft 365 kunnen functies voor SharePoint Online beschikbaar worden gemaakt die niet compatibel zijn met SharePoint Server on-premises.|
|Partners kunnen helpen met het migreren van gegevens naar de volgende versie van SharePoint Server (en daarbuiten).|Op uw SharePoint Server-sites worden niet automatisch [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) certificaten gebruikt zoals deze worden weergegeven in SharePoint Online.|
|Volledig beheer van de naamgevingsconventies, back-up en herstel en andere herstelopties in SharePoint Server on-premises.|SharePoint Server on-premises is gevoelig voor productlevenscyclus.|

### <a name="upgrade-resources"></a>Bronnen voor upgraden

U moet eerst weten dat u aan de hardware-en softwarevereisten voldoet en vervolgens de ondersteunde upgrademethoden kunt volgen.

- *Hardware-en softwarevereisten voor*:

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Software grenzen en-limieten voor*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *Overzicht van het upgradeproces voor*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Een hybride SharePoint-oplossing maken tussen SharePoint Online en on-premises

Als het antwoord op uw migratie behoefte zich bevindt op een ander besturingselement dan de on-premises plaats en de lagere eigendomskosten van SharePoint Online, kunt u SharePoint Server 2013 of 2016 Farms met SharePoint Online verbinden via hybride. [Meer informatie over hybride SharePoint-oplossingen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Als u besluit dat een hybride SharePoint-server farm uw bedrijf zal voorstellen, kunt u vertrouwd raken met de bestaande soorten hybriden en de verbinding configureren tussen uw on-premises SharePoint-farm en uw Microsoft 365-abonnement.

U kunt een Microsoft 365-ontwikkel-en testomgeving maken die u kunt instellen met [testlab-handleidingen](m365-enterprise-test-lab-guides.md). Nadat u een proefabonnement hebt aangeschaft of Microsoft 365 hebt aangeschaft, kunt u de siteverzamelingen, webs en documentbibliotheken maken in SharePoint Online, waar u gegevens kunt migreren. U kunt handmatig migreren, met behulp van de migratie-API, of, als u mijn site-inhoud wilt migreren naar OneDrive voor bedrijven, via de hybride wizard.

> [!NOTE]
> Als u de hybride optie wilt gebruiken, moet u eerst on-premises 2010 een upgrade uitvoeren naar SharePoint Server 2013 of 2016. SharePoint Foundation 2010 en SharePoint Foundation 2013 biedt geen ondersteuning voor hybride verbindingen met SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Overzicht van opties voor Office 2010-client en-servers en Windows 7

Voor een visueel overzicht van de opties voor de upgrade, migratie en verplaatsen van een upgrade, migratie en migratie van Office 2010-clients en-servers en Windows 7, raadpleegt u het [einde van de ondersteunings poster](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Einde van de ondersteuning voor Office 2010-clients en-servers en Windows 7-poster](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Deze poster toont de verschillende paden die u kunt nemen om Office 2010-client-en Server producten en Windows 7 einde van de ondersteuning te voorkomen, waarbij de gewenste paden en optie worden ondersteund in Microsoft 365 Enterprise gemarkeerd.

U kunt deze poster ook [downloaden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) en afdrukken met de indeling letter, juridisch of tabloid (11 x 17).

## <a name="related-articles"></a>Verwante artikelen

[Bronnen om u te helpen bij het upgraden van Office 2007 of 2010-servers en-clients](upgrade-from-office-2010-servers-and-products.md)

[Overzicht van het upgradeproces van SharePoint 2010 naar SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)

[Aanbevolen procedures voor het uitvoeren van een upgrade van SharePoint 2010 naar SharePoint 2013](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)

[Problemen met het upgraden van een database in SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)

[Zoek naar Microsoft Solution Providers om u te helpen bij de upgrade](https://go.microsoft.com/fwlink/?linkid=841249)

[Bijgewerkt product onderhoudsbeleid voor SharePoint 2013](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)

[Bijgewerkt product onderhoudsbeleid voor SharePoint Server 2016](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
