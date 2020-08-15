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
description: 'Samenvatting: u kunt de IT-posters voor de architectuur, de implementatie en platform opties voor SharePoint, Exchange, Skype voor bedrijven en Lync met behulp van een beschrijving doen.'
ms.openlocfilehash: 67f1018c70dfc86306b0d1e7ceb6061a166b3db8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689353"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Architectuurmodellen voor SharePoint, Exchange, Skype voor Bedrijven en Lync

Deze IT-medewerkers beschrijven de architectuur modellen en implementatie-opties voor SharePoint, Exchange, Skype voor bedrijven en Lync, en bieden ontwerpinformatie voor de implementatie van SharePoint in Microsoft Azure.
  
Met Microsoft 365 kunt u de services voor samenwerking en communicatie aanwijzen waarmee uw gebruikers bekend zijn als een service op de Cloud. Met een paar uitzonderingen blijft de gebruikerservaring hetzelfde, ongeacht of u een on-premises implementatie beheert of met Microsoft 365. Deze geïntegreerde gebruikerservaring maakt het minder eenvoudig om te bepalen waar u elke werklast moet plaatsen en vragen te doen, zoals:
  
- Hoe bepaal ik welke platform optie u moet kiezen voor de afzonderlijke werkbelastingen?
    
- Is het verstandig om een service on-premises te houden?
    
- Wat is een scenario waarbij een hybride implementatie geschikt is?
    
- Hoe past Microsoft Azure in de afbeelding?
    
- Wat zijn de ondersteunde configuraties voor Office Server-belastingen in azure?
    
> [!TIP]
> De meeste postvakken op deze pagina zijn beschikbaar in meerdere talen, waaronder Chinees, Engels, Frans, Duits, Italiaans, Japans, Koreaans, Portugees, Russisch en Spaans. Als u een poster in een van deze talen wilt downloaden, klikt u op de koppeling **meer talen** voor de poster.
  
Laat ons weten wat u ervan vindt! Stuur ons e-mail op [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com). 
  
Deze pagina wordt gekoppeld aan de volgende posters:
  
- **Bouwtekeningen voor architecturale modellen** U kunt deze bronnen gebruiken voor het bepalen van het ideale platform en de configuratie voor SharePoint 2016 en Skype voor bedrijven 2015.
    
  - [Microsoft SharePoint 2016 architecturale modellen](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [Databases van SharePoint Server 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Microsoft Skype voor bedrijven 2015 architectuur modellen](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Posters van platform opties** U kunt deze bronnen gebruiken voor het bepalen van het ideale platform en de configuratie voor SharePoint 2013, Exchange 2013 en Lync 2013.
    
  - [Platform opties voor SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Opties voor Exchange 2013 platform](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Opties voor Lync 2013 platform](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint Server 2013 in azure Solutions-posters** U kunt deze bewerkings poster gebruiken voor het bepalen van het ontwerp en de configuratie voor SharePoint Server 2013-belastingen in azure-infrastructuurservices.
    
  - [Internet sites in Microsoft Azure met behulp van SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Ontwerp voorbeeld: Internet sites in Microsoft Azure voor SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [Herstel van SharePoint naar Microsoft Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Bouwtekeningen voor architecturale modellen

Met deze nieuwe IT-poster voor SharePoint 2016 en Skype voor bedrijven 2015 kunt u de diverse implementatiemethoden met een eenvoudige Afdrukindeling vergelijken. Elke poster bevat een overzicht van alle beschikbare configuraties of platform opties en bevat de volgende informatie voor elke optie:
  
- **Overzicht** Een beknopt overzicht van het platform, waaronder een conceptueel diagram.
    
- **Geschikt voor** Veelgebruikte scenario's die ideaal zijn voor het specifieke platform.
    
- **Licentievereisten** De licenties die u nodig hebt voor de implementatie.
    
- **Architectuur taken** Welke beslissingen u moet nemen als architect.
    
- **Taken of verantwoordelijkheden voor IT-professionals** De dagelijkse verantwoordelijkheden waarop uw IT-personeel de behoeften moet plannen.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-2016-architectural-models"></a>Microsoft SharePoint 2016 architecturale modellen

|**Item**|**Beschrijving**|
|:-----|:-----|
|[![Miniatuur van de poster van de SharePoint 2016 Architectura model](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf) \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=52650) <br/> | Dit is een beschrijving van de on-premises configuraties van SharePoint Online, Microsoft Azure en SharePoint en Business Decision decisioners en Solution Architects. <br/><br/> - **SharePoint Online (SaaS)** : gebruik SharePoint via een software als een service (SaaS)-abonnements model. <br/> - **Hybride versie van SharePoint** : u kunt uw SharePoint-sites en-apps op uw eigen tempo verplaatsen naar de Cloud. <br/> - **SharePoint in azure (IaaS)** : u kunt uw on-premises omgeving verlengen in Microsoft Azure en sharepoint 2016-servers implementeren. (Dit wordt aanbevolen voor hoge beschikbaarheid/herstel omgevingen, en testomgevingen.) <br/> - **On-premises SharePoint** : u kunt uw SharePoint-omgeving plannen, implementeren, onderhouden en aanpassen in een datacenter dat u onderhoudt. <br/> |
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>Databases van SharePoint Server 2016

|**Item**|**Beschrijving**|
|:-----|:-----|
|[![Miniatuur voor de poster van de SharePoint Server 2016-database](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)          ](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf) \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=55041) <br/> | Dit is een snelle Naslaggids voor SharePoint Server 2016-databases. Elke database heeft de volgende informatie: <br/><br/> -Formaat <br/> Richtlijnen voor de schaling <br/> -I/O-patronen <br/> -Vereisten <br/><br/>  De eerste pagina heeft de SharePoint-systeemdatabases en de servicetoepassingen met meerdere databases. Op de tweede pagina ziet u alle servicetoepassingen die één database hebben. <br/><br/>  Zie voor meer informatie over de SharePoint Server 2016-databases [typen en beschrijvingen in SharePoint server 2016](https://docs.microsoft.com/SharePoint/technical-reference/database-types-and-descriptions) <br/> |
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Microsoft Skype voor bedrijven 2015 architectuur modellen

|**Item**|**Beschrijving**|
|:-----|:-----|
|[![Miniatuur van de poster voor de Skype voor bedrijven-bouwer modellen](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)          ](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf) \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=55022) <br/> |In deze poster worden de Skype voor bedrijven online, on-premises, hybride, Cloud PBX en integratie met Exchange-en SharePoint-configuraties met Exchange-en SharePoint-configuraties beschreven waarvan de makers van de professionele beslissing en oplossingen architecten moeten weten. <br/><br/> De doelgroep is bedoeld voor de IT-professionals waarmee de producten van de architectuur van de kern architectuur kunnen worden gebruikt om te zien welke Skype voor bedrijven online en Skype voor bedrijven on-premises on-premises zijn. <br/><br/>Begin met welke configuratie het beste past bij de behoeften van uw organisatie en voor toekomstige plannen. Overweeg om anderen te gebruiken. U kunt bijvoorbeeld de integratie met Exchange en SharePoint of een oplossing gebruiken die van de Cloud PBX van Microsoft gebruikmaakt.  <br/> |
   
## <a name="platform-options-posters"></a>Posters van platform opties

Met dit soort posters voor SharePoint 2013, Exchange 2013 en Lync 2013 kunt u de diverse implementatiemethoden in één oogopslag met een grote poster indeling vergelijken. Elke poster bevat een overzicht van alle beschikbare configuraties of platform opties en bevat de volgende informatie voor elke optie:
  
- **Overzicht** Een beknopt overzicht van het platform, waaronder een conceptueel diagram.
    
- **Geschikt voor** Veelgebruikte scenario's die ideaal zijn voor het specifieke platform.
    
- **Licentievereisten** De licenties die u nodig hebt voor de implementatie.
    
- **Architectuur taken** Welke beslissingen u moet nemen als architect.
    
- **Taken of verantwoordelijkheden voor IT-professionals** De dagelijkse verantwoordelijkheden waarop uw IT-personeel de behoeften moet plannen.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>Platform opties voor SharePoint 2013

****

|**Item**|**Beschrijving**|
|:-----|:-----|
|[![Miniatuurafbeelding van de platform opties van SharePoint 2013](../media/SP-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=40332) <br/> |Voor beslissers (BDMs) en architecten bevat dit model de platform opties voor SharePoint 2013, SharePoint in Microsoft 365, on-premises Hybrid met Microsoft 365, Azure en on-premises implementaties. Het bevat een overzicht van alle architecturen, aanbevelingen, licentievereisten en lijsten van de project architect en IT-Pro voor elk platform. Meerdere SharePoint-oplossingen op Azure zijn gemarkeerd. <br/> |
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Opties voor Exchange 2013 platform

****

|**Item**|**Beschrijving**|
|:-----|:-----|
|[![Miniatuurafbeelding van opties voor platform van Exchange](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=42676) <br/> |Voor BDMs en architecten bevat dit model een beschrijving van de beschikbare platform opties voor Exchange 2013. Klanten kunnen kiezen uit Exchange Online met Microsoft 365, hybride Exchange, Exchange Server on-premises en gehoste Exchange. De poster bevat details van elke architecturale optie, waaronder de meest ideale scenario's voor elk, de licentievereisten en de verantwoordelijkheden van IT-professionals. <br/> |
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Opties voor Lync 2013 platform

****

|**Item**|**Beschrijving**|
|:-----|:-----|
|[![Miniatuurafbeelding van opties voor Lync-platform](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=41677) <br/> |Voor BDMs en architecten bevat dit model een beschrijving van de beschikbare platform opties voor Lync 2013. Klanten kunnen kiezen uit Lync online met Microsoft 365, hybride Lync, Lync server on-premises en gehoste Lync. De IT-poster bevat details van elke architecturale optie, waaronder de meest ideale scenario's voor elk, de licentievereisten en de verantwoordelijkheden van IT-professionals.  <br/> |
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>SharePoint voor posters van Azure Solutions

Dit soort posters toont Azure-oplossingen die gebruikmaken van SharePoint Server 2013 in grote poster indeling.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Internet sites in Microsoft Azure met behulp van SharePoint Server 2013

****

|**Item**|**Beschrijving**|
|:-----|:-----|
|[![Afbeelding van Internet sites in azure met behulp van SharePoint](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=41992) <br/> |In deze poster worden belangrijke ontwerp activiteiten en aanbevolen architectuur keuzes voor sites op internet in azure beschreven.  <br/><br/> Zie de volgende artikelen voor meer informatie:  <br/><br/> - [Internet sites in Microsoft Azure met behulp van SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Microsoft Azure architecturen voor SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) <br/> |
   
<a name="DesignSampleInternetSites"> </a>
### <a name="design-sample-internet-sites-in-microsoft-azure-for-sharepoint-2013"></a>Ontwerp voorbeeld: Internet sites in Microsoft Azure voor SharePoint 2013

****

|**Item**|**Beschrijving**|
|:-----|:-----|
|[![Afbeelding van het ontwerp voorbeeld: Internet sites in Microsoft Azure voor SharePoint 2013](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=41991) <br/> |Gebruik dit ontwerp voorbeeld als uitgangspunt voor uw eigen architectuur Internet gerichte site in azure met behulp van SharePoint Server 2013. <br/><br/> Zie de volgende artikelen voor meer informatie:  <br/><br/> - [Internet sites in Microsoft Azure met behulp van SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Microsoft Azure architecturen voor SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) <br/> |
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Herstel van SharePoint naar Microsoft Azure

****

|**Item**|**Beschrijving**|
|:-----|:-----|
|[![SharePoint-noodherstel proces op Azure](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554) \| [Meer talen](https://www.microsoft.com/download/details.aspx?id=41993) <br/> |Deze poster toont architectuur beginselen voor een omgeving voor noodherstel in Azure. <br/><br/> Zie de volgende artikelen voor meer informatie:  <br/><br/> - [Herstel na herstel van SharePoint Server 2013 in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Microsoft Azure architecturen voor SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) <br/> |
   
## <a name="see-also"></a>Zie ook

[Microsoft 365-oplossingen- en -architectuurcentrum](../solutions/solution-architecture-center.md)
  
[Afbeeldingen van Microsoft Cloud for Enterprise Architect](../solutions/cloud-architecture-models.md)
  
[Test Lab-handleidingen voor Microsoft 365](m365-enterprise-test-lab-guides.md)
  
[Hybride oplossingen](hybrid-solutions.md)

