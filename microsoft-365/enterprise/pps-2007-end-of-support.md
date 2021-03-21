---
title: Roadmap voor einde van ondersteuning voor PerformancePoint Server 2007
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- PSV120
- PDD140
- MET150
ms.assetid: 89d9feee-2285-419c-8c14-0f7f583536e0
f1.keywords:
- NOCSH
description: PerformancePoint Server 2007, ProClarity en SharePoint Server 2007 hebben het einde van de ondersteuning bereikt. Lees dit artikel om uw BI-oplossingsupgrade te plannen.
ms.openlocfilehash: aa6adae24d78b6be72f17fd56c272b1293e6fcdc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927334"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>Roadmap voor einde van ondersteuning voor PerformancePoint Server 2007

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Office 2007-servers en -toepassingen hebben hun einde van de ondersteuning bereikt, inclusief servers en toepassingen die u mogelijk gebruikt als onderdeel van uw BI-oplossingen (Business Intelligence). In de volgende tabel worden BI-toepassingen vermeld die van invloed zijn:
  
|**Microsoft BI-toepassingen**|**Datumondersteuning beëindigd**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 Service Pack 3  <br/> ProClarity Desktop Professional 6.3  <br/> ProClarity SharePoint Viewer 6.3  <br/> |11 juli 2017  <br/> |
|SharePoint Server 2007 Service Pack 3  <br/> |10 oktober 2017  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |9 januari 2018  <br/> |
   
Zie Resources voor een upgrade van [Office 2007-servers en -clients voor meer informatie.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-does-end-of-support-mean"></a>Wat betekent *het einde van de ondersteuning?*

Net als de meeste Microsoft-producten hebben PerformancePoint Server 2007 SP3, ProClarity-software en SharePoint Server 2007 SP3 een levenscyclus voor ondersteuning, waarin Microsoft nieuwe functies, bugfixes en beveiligingsupdates biedt. De levenscyclus van een product duurt meestal tien jaar vanaf de eerste release van het product. Het einde van die levenscyclus wordt het einde van de ondersteuning van het product genoemd. Aangezien ProClarity, PerformancePoint Server en SharePoint Server 2007 hun einde van de ondersteuning hebben bereikt, biedt Microsoft niet meer:
  
- Technische ondersteuning voor problemen die kunnen optreden.
    
- Bug fixes for issues that are discovered and that may impact the stability and usability of servers.
    
- Beveiligingsfixes voor beveiligingsproblemen die worden ontdekt en die servers of toepassingen kwetsbaar kunnen maken voor beveiligingslekken.
    
- Tijdzone-updates.
    
Uw installatie van ProClarity, SharePoint Server 2007 SP3 en PerformancePoint Server 2007 SP3 blijft worden uitgevoerd, ook al is de ondersteuning beëindigd. We raden u echter ten zeerste aan zo snel mogelijk van deze toepassingen te migreren.
  
## <a name="what-are-my-options"></a>Wat zijn mijn opties?

Er zijn veel wijzigingen in Microsoft BI-toepassingen sinds 2007 en u hebt verschillende opties om rekening mee te houden, zoals samengevat in de volgende tabel.
  
|**Als u deze ...**|**Bekijk deze opties ...**|**En houd dit in gedachten ...**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 Monitoring &amp; Analytics-mogelijkheden, waaronder:<br/>- PerformancePoint Monitoring Server <br/>- PerformancePoint Dashboard Designer<br/>- Dashboard Viewer voor SharePoint Services (gebruikt voor het weergeven van PerformancePoint-dashboards, scorecards en rapporten)<br/> |**Excel met Excel in een browser** (in de cloud of on-premises). Zie BI-mogelijkheden in Excel en [Microsoft 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)voor een overzicht.<br/><br/> **Power BI** (in de cloud of on-premises). Zie Wat [is Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) voor een overzicht. <br/><br/> **SQL Server Reporting Services** (on-premises). Zie SQL [Server Reporting Services (SSRS):](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)Mobiele en pagina's maken, implementeren en beheren voor een overzicht. <br/><br/> **PerformancePoint Services** (on-premises). Zie Nieuw voor [PerformancePoint Services (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))voor een overzicht. <br/> |Excel is beschikbaar als een onlineoplossing (cloud) of on-premises oplossing. Aan veel rapportage- en dashboardbehoeften kan worden voldaan met Excel.  <br/><br/> Power BI is beschikbaar als een online- of on-premises oplossing. Power BI is niet opgenomen in Microsoft 365. Maar u kunt Power BI gratis gaan gebruiken. Later kunt u, afhankelijk van uw gegevensgebruik en zakelijke behoeften, een upgrade uitvoeren naar Power BI Pro met Microsoft 365 E5.<br/> <br/> Reporting Services en PerformancePoint Services zijn beide on-premises oplossingen. <br/><br/> PerformancePoint Services is beschikbaar in SharePoint Server 2010, SharePoint Server 2013 en SharePoint Server 2016. <br/> <br/> Sommige functies en rapporttypen die beschikbaar waren in PerformancePoint Server 2007, zijn niet beschikbaar in Excel, Power BI, Reporting Services of PerformancePoint Services. Bekijk de beschikbare functies om de beste oplossing voor uw zakelijke behoeften te bepalen. <br/> |
| ProClarity-software, waaronder:<br/>- ProClarity Desktop Professional<br/> - ProClarity Analytics Server<br/>- ProClarity SharePoint Viewer<br/> |**Werk samen met een Microsoft-partner** om een oplossing te vinden die het beste aan uw behoeften voldoet. Ga naar [het Microsoft Partner center.](https://go.microsoft.com/fwlink/?linkid=841249) <br/><br/> U kunt ook Excel met Excel gebruiken in een browser, Power BI, SQL Server Reporting Services of PerformancePoint Services.  <br/> |Verschillende, maar niet alle functies van ProClarity-software zijn beschikbaar in andere Microsoft-aanbiedingen, waaronder Excel, Power BI, Reporting Services en PerformancePoint Services.  <br/> |
|SharePoint Server 2007 KPI's (ook wel MOSS KPI's genoemd)  <br/> |**Excel met Excel Services.** Zie Business [Intelligence in Excel en Excel Services (SharePoint Server 2013) voor een overzicht.](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |MOSS KPI's die zijn gemaakt met SharePoint Server 2007, kunnen worden gebruikt in SharePoint Server 2010, SharePoint Server 2013 en SharePoint Server 2016. U kunt echter geen nieuwe MOSS-KPI's maken.  <br/> |
|Excel 2007  <br/> |**Excel** (in de cloud of on-premises). Zie BI-mogelijkheden in Excel en [Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)voor een overzicht. <br/><br/> **Power BI** (in de cloud of on-premises). Zie Wat [is Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) voor een overzicht. <br/> |Zowel Excel als Power BI bieden uw organisatie cloud- en on-premises oplossingen, met ondersteuning voor een groot aantal gegevensbronnen.  <br/> |
   
### <a name="help-selecting-a-solution"></a>Help bij het selecteren van een oplossing

Nu er zoveel BI-opties beschikbaar zijn, lijkt het misschien overweldigend om te bepalen welke optie het beste is. Er is een onlinehandleiding beschikbaar om u te helpen. Zie [Microsoft Business Intelligence -hulpprogramma's (BI) kiezen voor analyse en rapportage.](/sql/reporting-services/choosing-microsoft-business-intelligence-bi-tools-for-analysis-and-reporting)
  
### <a name="what-if-i-dont-upgrade-now"></a>Wat gebeurt er als ik nu geen upgrade doe?

U kunt ervoor kiezen om niet direct een upgrade uit te voeren. Uw bestaande servers en toepassingen blijven worden uitgevoerd. U ontvangt echter geen verdere updates, inclusief beveiligingsupdates, omdat de ondersteuning is beëindigd. En als er iets misgaat met uw servertoepassingen, kunt u geen hulp krijgen van de technische ondersteuning van Microsoft.
  
## <a name="how-do-i-plan-my-upgrade"></a>Hoe plan ik mijn upgrade?

Nadat u de upgradeopties hebt verkend, is de volgende stap het voorbereiden van een upgradeplan. De volgende secties bevatten informatie en aanvullende informatiebronnen om u te helpen. U hebt vier hoofdopties, waaronder twee die zowel in de cloud als on-premises werken, en twee on-premises:
  
|**Optie**|**In de cloud of on-premises?**|
|:-----|:-----|
|[Excel met SharePoint Server (on-premises)](#excel-with-sharepoint-server-on-premises) <br/> |Beide  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |Beide  <br/> |
|[Reporting Services](#use-reporting-services-on-premises) <br/> |Alleen on-premises  <br/> |
|[PerformancePoint Services](#use-performancepoint-services-on-premises) <br/> |Alleen on-premises  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Excel gebruiken (in de cloud of on-premises)

Met Excel, ook wel Bekend als *Excel Services* in SharePoint Server, kunt u werkmappen weergeven en gebruiken in een browservenster, zelfs als Excel niet op de computer is geïnstalleerd. U kunt Excel gebruiken om rapporten, scorecards en dashboards te maken. Deel vervolgens uw werkmappen met anderen, die Excel in een browser kunnen gebruiken, ongeacht of ze SharePoint Online gebruiken als onderdeel van Microsoft 365 of SharePoint Server on-premises. U kunt gegevens gebruiken die on-premises of in de cloud zijn opgeslagen, zodat u een groot aantal gegevensbronnen kunt gebruiken.
  
In de volgende tabel worden de belangrijkste voordelen van het gebruik van Excel met Microsoft 365 vergeleken met het gebruik van Excel met SharePoint Server. Meer informatie volgt.
  
|**Excel met Microsoft 365 (in de cloud)**|**Excel met SharePoint Server (on-premises)**|
|:-----|:-----|
|**U krijgt de nieuwste, beste versie van Excel.** Met Microsoft 365 krijgt u de nieuwste versie van Excel, met krachtige nieuwe grafiektypen, de mogelijkheid om snel en eenvoudig grafieken en tabellen te maken en ondersteuning voor meer gegevensbronnen. <br/> <br/> **Setup is veel eenvoudiger.** Excel is opgenomen in Microsoft 365 voor Bedrijven, dus er is geen zware werkkosten van uw kant. Meld u aan en meld u aan, en u werkt sneller en efficiënter dan wanneer u uw on-premises servers upgradet. <br/> <br/> **Mensen hebben overal toegang tot hun werkmappen.** Personen kunnen werkmappen veilig bekijken, waar ze ook zijn, met hun computer, smartphone en tablet. <br/> <br/> **Er is nog meer!** Zie [BI-mogelijkheden in Excel en Office 365.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/> |**U beheert uw algemene instellingen.** Als SharePoint-beheerder kunt u globale instellingen opgeven, zoals beveiliging, taakverdeling, sessiebeheer, werkmap caching en externe gegevensverbindingen. <br/> <br/> **U kunt Excel Services gebruiken met PerformancePoint Services.** U kunt Excel Services en PerformancePoint Services configureren als onderdeel van uw SharePoint Server-installatie en Excel Services-rapporten opnemen in uw PerformancePoint-dashboards. <br/> <br/> **Er is nog meer!** Zie [Business Intelligence in Excel en Excel Services (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx). <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Excel met Microsoft 365 (in de cloud)

Als u naar Microsoft 365 gaat, hebt u de meest recente services en toepassingen, waaronder Excel 2016. PerformancePoint Services is niet beschikbaar in Microsoft 365, dus u vervangt uw PerformancePoint-dashboardinhoud door Excel-werkmappen of andere rapporten. Het goede nieuws is dat Excel 2016 veel nieuwe grafiektypen heeft en dat het eenvoudiger dan ooit is om indrukwekkende dashboards te maken in Excel. En er worden regelmatig nieuwe functies toegevoegd. Zie Nieuw [in Excel 2016 voor Windows voor meer informatie.](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx)
  
Als u 50 seats of meer van Microsoft 365 koopt, kan het Microsoft FastTrack-team u ook helpen bij het instellen. Ga naar FastTrack voor [meer informatie.](https://www.microsoft.com/fasttrack/microsoft-365)
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel met SharePoint Server (on-premises)

Als u een upgrade naar een nieuwere versie van SharePoint hebt uitgevoerd, kunt u Excel als volgt gebruiken met Excel Services of in een browser:
  
- Excel Services in SharePoint Server 2010
    
- Excel Services in SharePoint Server 2013
    
- Excel, dat deel uitmaakt van Office Online Server, is afzonderlijk geïnstalleerd van SharePoint Server 2016
    
U kunt PerformancePoint Services ook configureren in uw nieuwe versie van SharePoint Server en deze samen met Excel gebruiken.
  
Zie Routekaart voor einde ondersteuning van [SharePoint Server 2007](sharepoint-2007-end-of-support.md)voor meer informatie over de upgradeopties voor SharePoint.
  
Zie Overzicht van Excel [Services (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee424405(v=office.14))voor meer informatie over Excel Services.
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Power BI gebruiken (in de cloud of on-premises)

Power BI is een suite met hulpprogramma's voor bedrijfsanalyse om gegevens te analyseren en inzichten te delen. Met Power BI kunt u on-premises of onlinegegevensbronnen gebruiken om interactieve rapporten en dashboards te maken. Personen kunnen uw rapporten en dashboards bekijken en gebruiken op hun computers of mobiele apparaten.
  
Power BI maakt geen deel uit van Microsoft 365 of SharePoint Server. Het is een apart aanbod met Power BI Desktop, Power BI-gateways en de Power BI-service. Power BI is ook geïntegreerd met SharePoint Online. U kunt gratis aan de slag met Power BI. Op basis van uw gegevensgebruik en zakelijke behoeften kunt u later een upgrade uitvoeren naar Power BI Pro met Microsoft 365 E5. Zie Wat [is Power BI? voor meer informatie.](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Reporting Services (on-premises) gebruiken

SQL Server Reporting Services biedt een krachtige rapportageoplossing. U kunt Reporting Services configureren in de ingebouwde modus of de in SharePoint geïntegreerde modus. U kunt verschillende hulpmiddelen gebruiken om rapporten te maken, zoals Rapportontwerper, Opbouwfunctie voor rapporten en Power View. Met de nieuwste release van SQL Server kunt u ook SQL Server Mobile Report Publisher gebruiken om rapporten te leveren die worden geschaald naar elke schermgrootte. Hierdoor kunnen gebruikers rapporten op hun mobiele apparaten gebruiken. Zie [SQL Server Reporting Services (SSRS):](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)Mobiele en pagina's maken, implementeren en beheren voor meer informatie.
  
### <a name="use-performancepoint-services-on-premises"></a>PerformancePoint Services (on-premises) gebruiken

PerformancePoint Server 2007 is afzonderlijk van SharePoint Server 2007 verkocht. Vanaf SharePoint Server 2010 is PerformancePoint Services een servicetoepassing in SharePoint Server. U hoeft dus geen afzonderlijke serverlicenties of hardware te kopen om PerformancePoint Services te gebruiken.
  
Als u wilt overschakelen van PerformancePoint Server 2007 naar PerformancePoint Services, gaat u naar een meer recente versie van SharePoint Server en configureert u PerformancePoint Services. De versie van SharePoint Server die u verplaatst, bepaalt of u uw bestaande dashboardinhoud van PerformancePoint Server 2007 kunt importeren naar PerformancePoint Services.
  
- Als u een upgrade naar SharePoint Server 2010 hebt uitgevoerd, kunt u uw PerformancePoint-dashboardinhoud importeren van PerformancePoint Server 2007 naar PerformancePoint Services in SharePoint Server 2010. Zie Wizard [Importeren: PerformancePoint Server 2007-inhoud naar SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/ee681485(v=office.14))voor meer informatie.
    
- Als u naar SharePoint Server 2013 of SharePoint Server 2016 gaat, moet u waarschijnlijk nieuwe dashboardinhoud (gegevensbronnen, rapporten, scorecards en dashboardpagina's) maken.
    
Zie de volgende bronnen om aan de slag te gaan met uw PerformancePoint Services-upgradeplan:
  
- [SharePoint Server 2007 einde van ondersteuning Roadmap](sharepoint-2007-end-of-support.md)
    
- Als u weet naar welke versie van SharePoint u gaat, bekijkt u het bijbehorende artikel voor PerformancePoint Services:
    
  - [Plannen voor PerformancePoint Services (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee681486(v=office.14))
    
  - [Overzicht van PerformancePoint Services in SharePoint Server 2013](/sharepoint/administration/performancepoint-services-overview)
    
  - [Overzicht van PerformancePoint Services in SharePoint Server 2016](/sharepoint/administration/performancepoint-services-overview)
    
Wanneer u een upgrade naar PerformancePoint Services hebt uitgevoerd, krijgt u verschillende nieuwe functies en verbeteringen. PerformancePoint Services biedt verbeterde scorecards. nieuwe visualisaties, zoals het rapport Ontledingsstructuur en KPI-details; meer grafiektypen; betere time intelligence-filtermogelijkheden; en verbeterde naleving van toegankelijkheid. Zie Nieuw voor [PerformancePoint Services (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))voor meer informatie.
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>Waar kan ik hulp krijgen bij mijn upgrade?

Of u nu on-premises upgradet of naar Microsoft 365 gaat, we raden u aan met een Microsoft-partner te werken. Een gekwalificeerde partner kan u helpen bij het identificeren van de oplossing die het beste voldoet aan uw zakelijke behoeften en hulp bij uw implementatie. Ga naar [het Microsoft Partnercentrum](https://go.microsoft.com/fwlink/?linkid=841249)en gebruik de zoekfilters om een oplossingsprovider te vinden.
  
## <a name="related-topics"></a>Verwante onderwerpen

[Resources om u te helpen bij het upgraden van Office 2007-servers en -clients](upgrade-from-office-2007-servers-and-products.md)