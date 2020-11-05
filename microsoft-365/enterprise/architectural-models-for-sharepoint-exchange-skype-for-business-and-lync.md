---
title: Architectuurmodellen voor SharePoint, Exchange, Skype voor Bedrijven en Lync
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
ms.assetid: 5b49fa68-f8f2-4705-af96-5f5475e8539a
search.appverid:
- MET150
description: U kunt IT-posterjes met de architecturale modellen, implementatie en platform opties voor SharePoint, Exchange, Skype voor bedrijven en Lync.
ms.openlocfilehash: 6d5cda89fb67f5c41dcf161abe7258c4600ee8ce
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919818"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Architectuurmodellen voor SharePoint, Exchange, Skype voor Bedrijven en Lync

In dit artikel worden de architecturale modellen en implementatieopties beschreven voor SharePoint, Exchange, Skype voor bedrijven en Lync. Ze bieden ook ontwerpinformatie over het implementeren van SharePoint in Microsoft Azure.
  
Met behulp van Microsoft 365 kunt u bekende samenwerking en communicatiediensten aanbieden via de Cloud. Met een paar uitzonderingen blijft de gebruikerservaring hetzelfde, ongeacht of u een on-premises implementatie beheert of met Microsoft 365. 

Deze geïntegreerde gebruikerservaring is van toepassing op de manier waarop u elke belasting moet plaatsen. U kunt ook vragen stellen:
  
- Hoe kies ik een platform voor afzonderlijke werkbelastingen?
    
- Is het verstandig om een service on-premises te houden?
    
- In welk scenario is een hybride implementatie van toepassing?
    
- Hoe past Azure in de foto?
    
- Welke configuraties van Office Server-workloads worden door Azure ondersteund?
    
> [!TIP]
> De meeste posters in dit artikel zijn beschikbaar in meerdere talen. Beschikbare talen zijn Chinees, Engels, Frans, Duits, Italiaans, Japans, Koreaans, Portugees, Russisch en Spaans. Als u een poster wilt downloaden in een van deze talen, selecteert u **meer talen** onder de miniatuurafbeelding van de poster.
  
Laat ons weten wat u ervan vindt! Stuur ons e-mail op [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com). 
  
Gebruik de volgende koppelingen om de posters te kopen die u nodig hebt:
  
- **Architecturale modellen** : gebruik deze informatiebronnen om uw ideale platform en configuratie te bepalen voor sharepoint 2016 en Skype voor bedrijven 2015.
    
  - [Microsoft SharePoint 2016 architecturale modellen](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [Databases van SharePoint Server 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Microsoft Skype voor bedrijven 2015 architectuur modellen](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Platform** : gebruik deze informatiebronnen om uw ideale platform en configuratie voor sharepoint 2013, Exchange 2013 en Lync 2013 te bepalen.
    
  - [Platform opties voor SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Opties voor Exchange 2013 platform](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Opties voor Lync 2013 platform](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint server 2013 in azure** : gebruik deze bewerkings posteren om SharePoint Server 2013-belastingen te ontwerpen en te configureren in azure-infrastructuurservices.
    
  - [Internet sites in azure met behulp van SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Ontwerp voorbeeld: Internet sites in azure voor SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [SharePoint-noodherstel op Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Bouwtekeningen voor architecturale modellen

Met de IT-poster voor SharePoint 2016 en Skype voor bedrijven 2015 kunt u implementatiemethoden met een eenvoudige Afdrukindeling vergelijken. De lijst met poster alle opties voor het instellen van de configuraties of platform. Ze bieden de volgende informatie voor elke optie:
  
- **Overzicht** : een kort overzicht van het platform, waaronder een conceptueel diagram.
    
- **Geschikt voor** : veelvoorkomende scenario's die ideaal zijn voor het platform.
    
- **Licentievereisten** : de licenties die u nodig hebt voor de implementatie.
    
- **Architectuur taken** : welke beslissingen u moet nemen als architect.
    
- **Taken of verantwoordelijkheden voor IT-professionals** : de dagelijkse verantwoordelijkheden waarop uw IT-medewerkers moet plannen.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Microsoft SharePoint Server 2016 architecturale modellen

|Item|Beschrijving|
|---|---|
|[![Miniatuur voor de poster van de SharePoint Server 2016 architecturale modellen.](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf) \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=52650)|Op deze IT-poster worden de on-premises configuraties van SharePoint Online, Azure en SharePoint beschreven die u moet weten. <br/><br/> - **SharePoint Online (SaaS)** : gebruik SharePoint via een software als een service (SaaS)-abonnements model. <br/> - **Hybride SharePoint-** sites en-apps verplaatsen naar de Cloud, op uw eigen tempo. <br/> - **SharePoint in azure (IaaS)** : Breid uw on-premises omgeving uit naar Azure en implementeer daar sharepoint 2016-servers. (Dit model wordt aanbevolen voor omgevingen met een hoge beschikbaarheid of een omgeving voor noodherstel, en omgevingen voor ontwikkelaars/testen.) <br/> - **On-premises SharePoint** : u kunt uw SharePoint-omgeving plannen, implementeren, onderhouden en aanpassen in een datacenter dat u onderhoudt.|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>Databases van SharePoint Server 2016

|Item|Beschrijving|
|---|---|
|[![Miniatuur voor de poster van de SharePoint Server 2016-database.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf) \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=55041)|Deze poster is een beknopt overzicht van de SharePoint Server 2016-databases. U ziet de Details voor elke database: <br/><br/> -Formaat <br/> Richtlijnen voor de schaling <br/> -I/O-patronen <br/> -Vereisten <br/><br/>  Op de eerste pagina ziet u de SharePoint-systeemdatabases en de servicetoepassingen met meerdere databases. Op de tweede pagina ziet u alle servicetoepassingen die één database hebben. <br/><br/>  Zie [soorten databases en beschrijvingen in SharePoint Server 2016](https://docs.microsoft.com/SharePoint/technical-reference/database-types-and-descriptions)voor meer informatie.|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Microsoft Skype voor bedrijven 2015 architectuur modellen

|Item|Beschrijving|
|---|---|
|[![Miniatuur voor de poster voor de Skype voor bedrijven-architecturale modellen.](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf) \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=55022)|Deze poster bevat een beschrijving van Skype voor bedrijven online, on-premises, hybride en Cloud Private Branch Exchange (PBX). Dit beschrijft ook de integratie met Exchange-en SharePoint-configuraties waarbij ontwerpers van besluitvorming en de IT-oplossingen van een professionele beslissing informatie willen kennen. <br/><br/> De poster is bedoeld voor IT-professionals, zodat de fundamentele architectuur modellen via Skype voor bedrijven online en Skype voor bedrijven on-premises kunnen worden gebruikt. <br/><br/>Begin met de configuratie die het beste past bij de behoeften en plannen van uw organisatie. Let op de gewenste configuratie en gebruik andere configuraties. U kunt bijvoorbeeld de integratie van Exchange en SharePoint of een oplossing gebruiken die gebruikmaakt van Microsoft Cloud PBX.|
   
## <a name="platform-options-posters"></a>Posters van platform opties

De IT-poster voor SharePoint 2013, Exchange 2013 en Lync 2013 biedt een manier om de implementatiemethoden in één oogopslag te vergelijken. Elke poster bevat alle configuraties of platform opties. Het biedt de volgende informatie voor elke optie:
  
- **Overzicht** : een kort overzicht van het platform, waaronder een conceptueel diagram.
    
- **Geschikt voor** : veelvoorkomende scenario's die ideaal zijn voor het platform.
    
- **Licentievereisten** : de licenties die u nodig hebt voor de implementatie.
    
- **Architectuur taken** : welke beslissingen u moet nemen als architect.
    
- **Taken of verantwoordelijkheden voor IT-professionals** : de dagelijkse verantwoordelijkheden waarop uw IT-medewerkers moet plannen.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>Platform opties voor SharePoint 2013

|Item|Beschrijving|
|---|---|
|[![Miniatuurafbeelding van de poster opties van het SharePoint 2013-platform.](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=40332)|Voor besluitvorming en architecten voor bedrijven, ziet u in deze poster de platform opties voor SharePoint 2013, SharePoint in Microsoft 365, on-premises Hybrid met Microsoft 365, Azure en on-premises implementaties. Het bevat een overzicht van alle architecturen, aanbevelingen, licentievereisten en lijsten van de project architect en IT-Pro voor elk platform. De poster markeert diverse SharePoint-oplossingen op Azure.|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Opties voor Exchange 2013 platform

|Item|Beschrijving|
|---|---|
|[![Miniatuurafbeelding van de poster opties van Exchange platform.](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=42676)|Voor besluitvorming en architecten voor bedrijven worden in deze poster de platform opties voor Exchange 2013 beschreven. Klanten kunnen kiezen uit Exchange Online met Microsoft 365, hybride Exchange, Exchange Server on-premises en gehoste Exchange. De poster bevat elke architecturale optie, waaronder de ideale scenario's, de licentievereisten en de verantwoordelijkheden van IT-professionals.|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Opties voor Lync 2013 platform

|Item|Beschrijving|
|---|---|
|[![Miniatuurafbeelding van de poster opties voor Lync 2013-platform.](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=41677)|Voor besluitvorming en architecten voor bedrijven worden in deze poster de platform opties voor Lync 2013 beschreven. Klanten kunnen kiezen uit Lync online met Microsoft 365, hybride Lync, Lync server on-premises en Lync hosten. Op de IT-poster vindt u elke architecturale optie, waaronder de ideale scenario's, de licentievereisten en de verantwoordelijkheden van IT-professionals.|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>SharePoint voor posters van Azure Solutions

De IT-poster voor SharePoint in azure tonen Azure-oplossingen die gebruikmaken van SharePoint Server 2013.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Internet sites in Microsoft Azure met behulp van SharePoint Server 2013

|Item|Beschrijving|
|---|---|
|[![Afbeelding van de Internet sites in azure die gebruikmaken van SharePoint Server 2013-poster.](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=41992)|In deze poster worden belangrijke ontwerp activiteiten en aanbevolen architectuur voor sites op internet in azure beschreven.  <br/><br/> Zie de volgende artikelen voor meer informatie:  <br/><br/> - [Internet sites in azure met behulp van SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Azure architecturen voor SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Internet sites in azure voor SharePoint 2013

|Item|Beschrijving|
|---|---|
|[![Afbeelding van Internet sites in Microsoft Azure voor SharePoint Server 2013-poster.](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=41991)|Gebruik dit ontwerp voorbeeld als uitgangspunt voor uw eigen architectuur van een internetgerichte site in azure met behulp van SharePoint Server 2013. <br/><br/> Zie de volgende artikelen voor meer informatie:  <br/><br/> - [Internet sites in azure met behulp van SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Azure architecturen voor SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Herstel van SharePoint naar Microsoft Azure

|Item|Beschrijving|
|---|---|
|[![Afbeelding van de poster voor het herstelproces van SharePoint voor noodgevallen in Azure.](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=41993)|Deze poster toont architectuur beginselen voor een omgeving voor noodherstel in Azure. <br/><br/> Zie de volgende artikelen voor meer informatie:  <br/><br/> - [SharePoint Server 2013 noodherstel in azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Azure architecturen voor SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>Zie ook

- [Microsoft 365-oplossings- en architectuurcentrum](../solutions/solution-architecture-center.md)
  
- [Modellen voor Microsoft-cloudarchitectuur](../solutions/cloud-architecture-models.md)
  
- [Test Lab-handleidingen voor Microsoft 365](m365-enterprise-test-lab-guides.md)
  
- [Hybride oplossingen](hybrid-solutions.md)

