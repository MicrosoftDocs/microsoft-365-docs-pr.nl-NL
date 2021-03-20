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
description: Ontvang IT-posters met een beschrijving van de architectuurmodellen, implementatie- en platformopties voor SharePoint, Exchange, Skype voor Bedrijven en Lync.
ms.openlocfilehash: 6c8aea1f6389c5007adb1800639488972483d5fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905510"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Architectuurmodellen voor SharePoint, Exchange, Skype voor Bedrijven en Lync

In de IT-posters in dit artikel worden de architectuurmodellen en implementatieopties voor SharePoint, Exchange, Skype voor Bedrijven en Lync beschreven. Ze bevatten ook ontwerpgegevens voor de implementatie van SharePoint in Microsoft Azure.
  
Met Microsoft 365 kunt u vertrouwde samenwerkings- en communicatieservices leveren via de cloud. Op enkele uitzonderingen na blijft de gebruikerservaring hetzelfde, ongeacht of u een on-premises implementatie onderhoudt of Microsoft 365 gebruikt. 

Deze geïntegreerde gebruikerservaring compliceert de beslissing waar u elke werkbelasting moet plaatsen. Er worden ook vragen gesteld:
  
- Hoe kiest u een platform voor afzonderlijke werkbelastingen?
    
- Is het zinvol om een service on-premises te houden?
    
- In welk scenario is een hybride implementatie geschikt?
    
- Hoe past Azure in de afbeelding?
    
- Welke configuraties van Office-serverwerkbelastingen worden door Azure ondersteund?
    
> [!TIP]
> De meeste posters in dit artikel zijn beschikbaar in meerdere talen. Beschikbare talen zijn Chinees, Engels, Frans, Duits, Italiaans, Japans, Koreaans, Portugees, Russisch en Spaans. Als u een poster in een van deze talen wilt downloaden, selecteert u onder de miniatuurafbeelding van de poster de optie **Meer talen.**
  
Laat ons weten wat u denkt! Stuur ons e-mail [cloudadopt@microsoft.com.](mailto:cloudadopt@microsoft.com) 
  
Gebruik de volgende koppelingen om de posters te downloaden die u nodig hebt:
  
- **Architectuurmodellen:** gebruik deze bronnen om uw ideale platform en configuratie voor SharePoint 2016 en Skype voor Bedrijven 2015 te bepalen.
    
  - [Architectuurmodellen van Microsoft SharePoint 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePoint Server 2016-databases](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Architectuurmodellen van Microsoft Skype voor Bedrijven 2015](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Platform:** Gebruik deze bronnen om uw ideale platform en configuratie voor SharePoint 2013, Exchange 2013 en Lync 2013 te bepalen.
    
  - [SharePoint 2013-platformopties](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Opties voor Exchange 2013-platform](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Opties voor lync 2013-platform](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint Server 2013 in Azure:** Gebruik deze IT-posters voor het ontwerpen en configureren van SharePoint Server 2013-werkbelastingen in Azure-infrastructuurservices.
    
  - [Internetsites in Azure met SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Ontwerpvoorbeeld: Internetsites in Azure voor SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [SharePoint-rampherstel naar Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Posters voor architectuurmodellen

De IT-posters voor SharePoint 2016 en Skype voor Bedrijven 2015 bieden een manier om implementatiemethoden te vergelijken in een eenvoudig te afdrukken indeling. In de posters worden alle configuratie- of platformopties weergegeven. Ze bevatten de volgende informatie voor elke optie:
  
- **Overzicht:** Een korte samenvatting van het platform, inclusief een conceptueel diagram.
    
- **Het beste voor**: Veelvoorkomende scenario's die bij uitstek geschikt zijn voor het platform.
    
- **Licentievereisten:** De licenties die u nodig hebt voor implementatie.
    
- **Architectuurtaken:** de beslissingen die u als architect moet nemen.
    
- **IT-professionele taken of verantwoordelijkheden:** de dagelijkse verantwoordelijkheden die uw IT-personeel moet plannen.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Architectuurmodellen van Microsoft SharePoint Server 2016

|Item|Beschrijving|
|---|---|
|[![Miniatuur voor de poster Architectuurmodellen van SharePoint Server 2016.](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf) \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=52650)|Deze IT-poster beschrijft de on-premises configuraties van SharePoint Online, Azure en SharePoint die zakelijke besluitvormers en oplossingen moeten kennen. <br/><br/> - **SharePoint Online (SaaS)**: Gebruik SharePoint via een SaaS-abonnementsmodel (Software as a Service). <br/> - **Hybride SharePoint:** Verplaats uw SharePoint-sites en -apps in uw eigen tempo naar de cloud. <br/> - **SharePoint in Azure (IaaS)**: Breid uw on-premises omgeving uit naar Azure en implementeer SharePoint 2016-servers daar. (Dit model wordt aanbevolen voor omgevingen met hoge beschikbaarheid of noodherstel en dev/testomgevingen.) <br/> - **SharePoint on-premises**: Uw SharePoint-omgeving plannen, implementeren, onderhouden en aanpassen in een datacenter dat u onderhoudt.|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>SharePoint Server 2016-databases

|Item|Beschrijving|
|---|---|
|[![Miniatuur voor de poster SharePoint Server 2016-databases.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf) \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=55041)|Deze IT-poster is een beknopt overzicht van SharePoint Server 2016-databases. U ziet details voor elke database: <br/><br/> - Grootte <br/> - Richtlijnen voor schaalvergroting <br/> - I/O-patronen <br/> - Vereisten <br/><br/>  Op de eerste pagina ziet u de SharePoint-systeemdatabases en de servicetoepassingen met meerdere databases. Op de tweede pagina ziet u alle servicetoepassingen met afzonderlijke databases. <br/><br/>  Zie Databasetypen en [beschrijvingen in SharePoint Server 2016](/SharePoint/technical-reference/database-types-and-descriptions)voor meer informatie.|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Architectuurmodellen van Microsoft Skype voor Bedrijven 2015

|Item|Beschrijving|
|---|---|
|[![Miniatuur voor de poster Architectuurmodellen van Skype voor Bedrijven.](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf) \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=55022)|Deze poster beschrijft Skype voor Bedrijven Online, on-premises, hybride en cloud private branch exchange (PBX). Ook wordt de integratie beschreven met Exchange- en SharePoint-configuraties die door zakelijke besluitvormers en oplossingen moeten worden beschreven. <br/><br/> De poster is bedoeld voor IT-professionals om mensen bewust te maken van de fundamentele architectuurmodellen waarmee Skype voor Bedrijven Online en Skype voor Bedrijven on-premises kunnen worden gebruikt. <br/><br/>Begin met de configuratie die het beste past bij de behoeften en plannen van uw organisatie. Overweeg en gebruik zo nodig andere configuraties. U kunt bijvoorbeeld overwegen om te integreren met Exchange en SharePoint of een oplossing die gebruik maakt van het Microsoft Cloud PBX-aanbod.|
   
## <a name="platform-options-posters"></a>Posters met platformopties

Met de IT-posters voor SharePoint 2013, Exchange 2013 en Lync 2013 kunt u de implementatiemethoden in één oogopslag vergelijken. Elke poster bevat alle configuraties of platformopties. De optie bevat de volgende informatie voor elke optie:
  
- **Overzicht:** Een korte samenvatting van het platform, inclusief een conceptueel diagram.
    
- **Het beste voor**: Veelvoorkomende scenario's die bij uitstek geschikt zijn voor het platform.
    
- **Licentievereisten:** De licenties die u nodig hebt voor implementatie.
    
- **Architectuurtaken:** de beslissingen die u als architect moet nemen.
    
- **IT-professionele taken of verantwoordelijkheden:** de dagelijkse verantwoordelijkheden die uw IT-personeel moet plannen.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>Platformopties voor SharePoint 2013

|Item|Beschrijving|
|---|---|
|[![Miniatuurafbeelding van de poster Platformopties voor SharePoint 2013.](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=40332)|Voor zakelijke besluitvormers en architecten toont deze poster de platformopties voor SharePoint 2013, SharePoint in Microsoft 365, on-premises hybride met Microsoft 365-, Azure- en on-premises implementaties. Het bevat een overzicht van elke architectuur, aanbevelingen, licentievereisten en lijsten met taken van architect en IT-professional voor elk platform. In de poster worden verschillende SharePoint-oplossingen in Azure belicht.|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Platformopties voor Exchange 2013

|Item|Beschrijving|
|---|---|
|[![Miniatuurafbeelding van de poster Opties voor Exchange-platform.](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=42676)|Voor zakelijke besluitvormers en architecten worden in deze poster de platformopties voor Exchange 2013 beschreven. Klanten kunnen kiezen uit Exchange Online met Microsoft 365, hybride Exchange, Exchange Server on-premises en gehoste Exchange. In de poster wordt elke architectonische optie be detaild, inclusief de ideale scenario's voor elk, de licentievereisten en it-verantwoordelijkheden.|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Platformopties voor Lync 2013

|Item|Beschrijving|
|---|---|
|[![Miniatuurafbeelding van de poster Platformopties voor Lync 2013.](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=41677)|Voor zakelijke besluitvormers en architecten worden in deze poster de platformopties voor Lync 2013 beschreven. Klanten kunnen kiezen uit Lync Online met Microsoft 365, hybride Lync, Lync Server on-premises en gehost Lync. De IT-poster geeft elke architectuuroptie weer, inclusief de ideale scenario's voor elk, de licentievereisten en it-verantwoordelijkheden.|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>SharePoint in Azure-oplossingenposters

Op de IT-posters voor SharePoint in Azure worden Azure-oplossingen voor SharePoint Server 2013 gebruikt.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Internetsites in Microsoft Azure met SharePoint Server 2013

|Item|Beschrijving|
|---|---|
|[![Afbeelding van de internetsites in Azure met sharepoint server 2013-poster.](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=41992)|Deze poster bevat een overzicht van belangrijke ontwerpactiviteiten en aanbevolen architectuur voor internetsites in Azure.  <br/><br/> Zie de volgende artikelen voor meer informatie:  <br/><br/> - [Internetsites in Azure met SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Azure-architecturen voor SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Internetsites in Azure voor SharePoint 2013

|Item|Beschrijving|
|---|---|
|[![Afbeelding van de internetsites in Microsoft Azure voor SharePoint Server 2013 poster.](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=41991)|Gebruik dit ontwerpvoorbeeld als uitgangspunt voor uw eigen architectuur van een internetsite in Azure met SharePoint Server 2013. <br/><br/> Zie de volgende artikelen voor meer informatie:  <br/><br/> - [Internetsites in Azure met SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Azure-architecturen voor SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>SharePoint Disaster Recovery naar Microsoft Azure

|Item|Beschrijving|
|---|---|
|[![Afbeelding van de poster voor het herstelproces van SharePoint-ramp naar Azure.](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=41993)|Deze IT-poster toont architectuurprincipes voor een omgeving voor noodherstel in Azure. <br/><br/> Zie de volgende artikelen voor meer informatie:  <br/><br/> - [Herstel na een ramp met SharePoint Server 2013 in Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Azure-architecturen voor SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>Zie ook

- [Microsoft 365-oplossings- en -architectuurcentrum](../solutions/index.yml)
  
- [Modellen voor Microsoft-cloudarchitectuur](../solutions/cloud-architecture-models.md)
  
- [Microsoft 365 test lab guides](m365-enterprise-test-lab-guides.md)
  
- [Hybride oplossingen](hybrid-solutions.md)