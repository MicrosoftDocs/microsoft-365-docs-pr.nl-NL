---
title: Migratie naar Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Doorloop het proces van het migreren van versies van Microsoft Office, Office-servers en Windows naar Microsoft 365 Enterprise binnen uw organisatie.
ms.openlocfilehash: 6830b4627eea799e18d32d3f9150617df339d7d4
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011793"
---
# <a name="migration-to-microsoft-365-enterprise"></a>Migratie naar Microsoft 365 Enterprise

De meeste ondernemingen hebben een heterogene omgeving met meerdere versies van besturingssystemen, clientsoftware en serversoftware. Microsoft 365 Enterprise bevat de veiligste versies van deze belangrijke componenten van uw IT-infrastructuur met productiviteitsfuncties die zijn ontworpen om te profiteren van cloudtechnologieën.

Om de bedrijfswaarde van de geïntegreerde productsuite van Microsoft 365 Enterprise te maximaliseren, begint u met het plannen en implementeren van een strategie voor het migreren van releases van:

- De Office-client die op uw computer is geïnstalleerd naar Microsoft 365-apps voor ondernemingen
- Office-servers die op uw servers zijn geïnstalleerd naar identieke services in Office 365
- Windows 7 en Windows 8,1 op uw apparaten naar Windows 10 Enterprise

>[!Note]
>Windows 7 heeft het einde van de ondersteuning bereikt op **14 januari 2020**. Voor meer informatie klikt u [hier](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).
>

Door al deze migraties in de loop van de tijd te voltooien, komt uw organisatie dichter bij de [moderne werkplek](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/): een veilige en geïntegreerde omgeving die teamwerk en creativiteit in uw organisatie ontsluit, mogelijk gemaakt door Microsoft 365 Enterprise. 

Voor meer informatie over het migreren van gebruikers en gegevens voor specifieke Office 365-workloads:

- Gebruikerspostvakken van Exchange Server naar Exchange Online, zie de [Exchange Online-workload](exchangeonline-workload.md).
- SharePoint-gegevens van SharePoint Server naar SharePoint Online, zie de [SharePoint Online-workload](sharepoint-online-onedrive-workload.md).
- Skype voor Bedrijven Online naar Microsoft teams, zie de [Microsoft Teams-workload](teams-workload.md).

## <a name="migration-for-microsoft-office-client-products"></a>Migratie voor Microsoft Office-clientproducten

In veel grote en kleine organisaties wordt mogelijk een combinatie gebruikt van oudere versies van de Office-clientproducten, zoals Word, Excel en PowerPoint. Deze oudere versies:

- Kunnen worden [bijgewerkt](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) met de nieuwste beveiligingsupdates en ondersteuningsoplossingen, maar het proces is soms handmatig en kan mogelijk niet worden geschaald binnen uw organisatie.
- Zijn niet optimaal geschikt om de cloudtechnologieën van Microsoft te gebruiken en u te helpen bij het digitaal transformeren van uw bedrijf.
- Bevatten geen nieuwe functies.
 
Microsoft 365 Enterprise omvat Microsoft 365-apps voor ondernemingen, een versie van de Office-clientproducten die beschikbaar is met een Microsoft 365 Enterprise-licentie en die wordt geïnstalleerd en bijgewerkt vanuit de Microsoft-Cloud. Microsoft 365-apps voor ondernemingen bevat beveiligingsupdates en de nieuwste functies. Zie [Over Microsoft 365-apps voor ondernemingen](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps) voor meer informatie.

### <a name="office-2007"></a>Office 2007

Versies van Office in de Office 2007-release worden inmiddels niet meer ondersteund. Zie [Roadmap einde van ondersteuning voor Office 2007](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap) voor meer informatie.

In plaats van uw computers met Office 2007 te upgraden naar Office 2010, Office 2013 of Office 2016, kunt u het volgende overwegen:

1. Een Microsoft 365-licentie voor uw gebruikers verkrijgen en toewijzen.
2. Office 2007 van hun computers verwijderen.
3. Microsoft 365-apps voor ondernemingen installeren, afzonderlijk of in combinatie met een IT-implementatie. Zie [Fase 4: Microsoft 365-apps voor ondernemingen](office365proplus-infrastructure.md) voor meer informatie.

Microsoft 365-apps voor ondernemingen installeert updates automatisch en kan gebruikmaken van cloudgebaseerde services voor verbeterde beveiliging en productiviteit.

### <a name="office-2010"></a>Office 2010

Voor versies van Office in de Office 2010-release eindigt de ondersteuning op **13 oktober 2020**. Zie [Roadmap einde van ondersteuning voor Office 2010](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) voor meer informatie.

In plaats van uw computers met Office 2010 te upgraden met Office 2013 of Office 2016, die beide handmatig moeten worden bijgewerkt, kunt u het volgende overwegen: 

1. Een Microsoft 365-licentie voor uw gebruikers verkrijgen en toewijzen.
2. Office 2010 van hun computers verwijderen.
3. Microsoft 365-apps voor ondernemingen installeren, afzonderlijk of in combinatie met een IT-implementatie. Zie [Fase 4: Microsoft 365-apps voor ondernemingen](office365proplus-infrastructure.md) voor meer informatie.

Microsoft 365-apps voor ondernemingen installeert updates voor zowel beveiliging als nieuwe functies automatisch en kan gebruikmaken van cloudgebaseerde services in Microsoft 365, voor verbeterde beveiliging en productiviteit.

### <a name="office-2013-and-office-2016"></a>Office 2013 en Office 2016

De roadmap voor het einde van de ondersteuning voor Office 2013- en Office 2016-versies van Office is nog niet vastgesteld. Net als Office 2010 moet u echter nog steeds [beveiligingsupdates installeren](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5). De kans is aanwezig dat deze niet goed kunnen worden geschaald, afhankelijk van de grootte van uw organisatie.

In plaats van uw computers steeds bij te werken met de nieuwste beveiligingsupdates voor Office 2013 of Office 2016, of uw computers bij te werken van Office 2013 naar Office 2016, kunt u het volgende overwegen:

1. Een Microsoft 365-licentie voor uw gebruikers verkrijgen en toewijzen.
2. Office 2013 of Office 2016 van hun computers verwijderen.
3. Microsoft 365-apps voor ondernemingen installeren, afzonderlijk of in combinatie met een IT-implementatie. Zie [Fase 4: Microsoft 365-apps voor ondernemingen](office365proplus-infrastructure.md) voor meer informatie.

Microsoft 365-apps voor ondernemingen installeert updates voor zowel beveiliging als nieuwe functies automatisch en kan gebruikmaken van cloudgebaseerde services in Microsoft 365, voor verbeterde beveiliging en productiviteit.

## <a name="migration-for-microsoft-office-server-products"></a>Migratie voor Microsoft Office-serverproducten

In veel grote en kleine organisaties wordt mogelijk een combinatie gebruikt van oudere versies van de Office-serverproducten, zoals Exchange Server en SharePoint Server. Deze oudere versies:

- Moeten worden bijgewerkt met de nieuwste beveiligingsupdates en ondersteuningsoplossingen. In sommige gevallen worden deze updates maandelijks uitgebracht.
- Zijn niet optimaal geschikt om de cloudtechnologieën van Microsoft te gebruiken en u te helpen bij het digitaal transformeren van uw bedrijf.
- Voegen geen nieuwe productiviteitstoepassingen toe, zoals Microsoft Teams.
- Voegen niet de nieuwste beveiligingsfuncties toe, zoals Exchange Advanced Threat Protection.

Microsoft 365 Enterprise omvat Office 365, dat cloudgebaseerde versies van Office Server-services bevat die een aantal van dezelfde tools gebruiken als lokale versies van Office Server-software, zoals webbrowsers en de Outlook-client. Deze services worden voortdurend bijgewerkt op het punt van beveiliging zonder dat de IT-afdeling hierbij betrokken hoeft te zijn. U bespaart zo tijd die u kunt gebruiken om on-premises servers te onderhouden en bij te werken. Deze services bieden ook nieuw functieverbeteringen die niet aanwezig zijn in Office Server-software. 

### <a name="office-server-2007"></a>Office Server 2007

Serverproducten in de Office 2007-release worden inmiddels niet meer ondersteund. Zie de volgende artikelen voor meer informatie:

- [Roadmap voor einde van ondersteuning voor Exchange 2007](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [Roadmap voor het einde van de levensduur van SharePoint Server 2007](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [Roadmap voor einde van ondersteuning voor Project Server 2007](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [Roadmap voor einde van ondersteuning voor Office Communications Server](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [Roadmap voor einde van ondersteuning voor PerformancePoint Server 2007](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

In plaats van uw serverproducten in de Office 2007-release bij te werken met serverproducten in de Office 2010-, Office 2013- of Office 2016-releases, kunt u het volgende overwegen:

1. De gegevens op uw Office 2007-servers migreren naar Office 365. U kunt een Microsoft-partner inhuren om u hierbij te helpen.
2. De nieuwe functionaliteit en werkprocessen implementeren voor uw gebruikers.
3. Als de on-premises servers met Office 2007-serverproducten niet meer nodig zijn, kunt u deze buiten bedrijf stellen.

### <a name="office-server-2010"></a>Office Server 2010

De ondersteuning voor [Exchange Server 2010](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support) wordt beëindigd op **13 oktober 2020**.

De ondersteuning voor [SharePoint Server 2010](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010) wordt beëindigd op **13 april 2021**.

In plaats van deze serverproducten in de Office 2010-release bij te werken met serverproducten in de Office 2013- of Office 2016-release, kunt u het volgende overwegen:

1. De gegevens op uw Office 2010-servers migreren naar Microsoft 365. Zie voor meer informatie [FastTrack voor Microsoft 365](https://fasttrack.microsoft.com/microsoft365) of schakel de hulp van een Microsoft-partner in.
2. De nieuwe functionaliteit en werkprocessen implementeren voor uw gebruikers.
3. Als de on-premises servers met Office 2010-serverproducten niet meer nodig zijn, kunt u deze buiten bedrijf stellen.

### <a name="office-server-2013"></a>Office Server 2013

Voor serverproducten in de Office 2013-release is de einddatum voor de ondersteuning nog niet vastgesteld. In plaats van uw serverproducten in de Office 2013-release bij te werken met serverproducten in de Office 2016-release, kunt u het volgende overwegen:

1. De gegevens op uw Office 2013-servers migreren naar Office 365. Zie voor meer informatie [FastTrack voor Microsoft 365](https://fasttrack.microsoft.com/microsoft365) of schakel de hulp van een Microsoft-partner in.
2. De nieuwe functionaliteit en werkprocessen implementeren voor uw gebruikers.
3. Als de on-premises servers met Office 2013-serverproducten niet meer nodig zijn, kunt u deze buiten bedrijf stellen.

### <a name="office-server-2016"></a>Office Server 2016

Voor serverproducten in de Office 2016-release is de einddatum voor de ondersteuning nog niet vastgesteld. Als u voordeel wilt hebben van de cloudservice en verbeteringen bij de digitale transformatie van uw bedrijf, kunt u het volgende overwegen:

1. De gegevens op uw Office 2016-servers migreren naar Office 365. Zie voor meer informatie [FastTrack voor Microsoft 365](https://fasttrack.microsoft.com/microsoft365) of schakel de hulp van een Microsoft-partner in.
2. De nieuwe functionaliteit en werkprocessen implementeren voor uw gebruikers.
3. Als de on-premises servers met Office 2016-serverproducten niet meer nodig zijn, kunt u deze buiten bedrijf stellen.

## <a name="migration-for-microsoft-windows-7-and-81"></a>Migratie voor Microsoft Windows 7 en 8.1

Windows 7 heeft het einde van de ondersteuning bereikt op **14 januari 2020**. Als u uw apparaten met Windows 7 of Windows 8.1 wilt migreren, kunt u een [in-place upgrade](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade)uitvoeren. 

Zie [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios) (Implementatiescenario's voor Windows 10) voor aanvullende methoden. U kunt ook zelf [de implementatie van Windows 10 plannen](https://aka.ms/planforwin10deployment).

## <a name="summary-of-options-for-office-2010-clients-and-servers-and-windows-7"></a>Overzicht van opties voor Office 2010-clients en -servers en Windows 7

Voor een visueel overzicht van de opties voor het upgraden, migreren en overstappen naar de cloud voor deze producten, raadpleegt u de [poster met de einddatums voor ondersteuning](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf).

[![Afbeelding van de poster Eindgebruikersondersteuning voor Office 2010-clients en -servers en Windows 7](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)

Deze poster van één pagina is een snelle manier om een beeld te krijgen van de verschillende trajecten die u kunt volgen om te voorkomen dat er geen ondersteuning meer wordt geboden voor client- en serverproducten van Office 2010 en voor Windows 7. De geadviseerde trajecten en hun bestemmingen qua ondersteuning in Microsoft 365 Enterprise zijn gemarkeerd.

U kunt [deze poster downloaden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) en afdrukken in de indeling Letter, Legal of Tabloid (11 x 17).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hoe Microsoft omgaat met Microsoft 365 Enterprise

Raadpleeg de volgende Engelstalige informatiebronnen om te lezen hoe IT-specialisten van Microsoft het bedrijf hebben gemigreerd naar Microsoft 365 Enterprise: 

- [Microsoft 365-apps voor ondernemingen implementeren en bijwerken](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Microsoft migrates 150,000 mailboxes to Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)(Hoe Microsoft 150.000 postvakken heeft gemigreerd naar Exchange Online)
- [SharePoint to the cloud: Learn how Microsoft ran its own migration](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration) (SharePoint naar de cloud: lees hoe Microsoft zelf de eigen migratie heeft uitgevoerd)
- [Deploying Windows 10 at Microsoft as an in-place upgrade](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade) (Windows 10 implementeren bij Microsoft als een in-place upgrade)
- [Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video) (Implementatie van Windows 10: tips en trucs van Microsoft IT)

## <a name="transition-your-entire-organization"></a>Uw hele organisatie overzetten

Voor een beter beeld over het migreren naar producten en services in Microsoft 365 Enterprise voor uw gehele organisatie, zie de [overgangsposter](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf).

[![Afbeelding van de poster Overgang naar Microsoft 365](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)

Deze poster van twee pagina's is een snelle manier om de bestaande infrastructuur te inventariseren en de informatiebronnen te vinden die u kunnen helpen bij het overstappen naar het bijbehorende product of de bijbehorende service in Microsoft 365 Enterprise. De poster bevat Windows- en Office-producten en andere infrastructuur- en beveiligingselementen, zoals apparaat- en identiteitsbeheer, informatiebeveiliging en beveiliging tegen bedreigingen.

U kunt [deze poster downloaden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf) en afdrukken in de indeling Letter, Legal of Tabloid (11 x 17).

## <a name="result"></a>Resultaat

Uw organisatie heeft oudere versies van Microsoft Office, Office-servers en Windows gemigreerd naar Microsoft 365 Enterprise.
