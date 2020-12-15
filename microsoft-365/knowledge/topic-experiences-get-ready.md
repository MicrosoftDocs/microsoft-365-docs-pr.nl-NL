---
title: Uw omgeving voorbereiden op de onderwerpen (preview)
description: Uw omgeving voorbereiden zodat u zo veel mogelijk inhoud kunt aanbieden voor uw gebruikers met topics (preview).
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX
ms.openlocfilehash: 19112b222be328eb75b7eea807bea94e524fd56d
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683410"
---
# <a name="get-your-environment-ready-for-topic-experiences-preview"></a>Uw omgeving voorbereiden op de onderwerpen (preview)

> [!Note]
> De inhoud in dit artikel is bedoeld voor project cortex private preview. [Meer informatie over Project Cortex](https://aka.ms/projectcortex).

Om optimaal gebruik te kunnen maken van de functies van het onderwerp, kunt u zoveel mogelijk inhoud opnemen voor het detecteren van een onderwerp, zodat u over een uitgebreide reeks onderwerpen beschikt voor uw gebruikers. Maar welke inhoud moet worden gebruikt voor het detecteren van een onderwerp? Hoe maximaliseert u de inhoud die wordt geïndexeerd, terwijl u de besturing blijft overnemen? De meer inhoud is binnen het bereik, de betere inzichten van de kunstmatige intelligentie. In dit artikel wordt u stapsgewijs begeleid bij het plannen van stappen om ervoor te zorgen dat u de juiste inhoud opneemt, en dat u beschikt over de juiste personen en resources om de gebruikers een goede ervaring te bieden.

Voor het plannen van topics (preview), moet u het volgende doen:

![Migreer, maak verbinding, maak een modern, veiliger en Identificeer de stappen voor het onboarding to Knowledge Management](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Inhoud migreren naar SharePoint](#1-migrate-content-to-microsoft-365)
    - Onderwerp bevat alleen inhoud op SharePoint-sites.
      - Migreer waar mogelijk waardevolle inhoud van externe bronnen naar SharePoint Online.
      - Prioriteit geven aan inhoudsbronnen met een hoge potentiële informatie voor stilzwijgende kennis.
      - Benadruk de voordelen van kennisbeheer ter aanmoediging van gebruikers om inhoud van OneDrive naar SharePoint-sites te verplaatsen.

2. [Informatie verbinden met Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - In de toekomst kan externe inhoud worden binnengebracht in de kennis grafiek en beschikbaar worden.
    - Voor inhoud die niet kan worden verplaatst, kunt u gebruikmaken van Graph-connectors voor een betere zoekfunctie en voorbereiding voor toekomstige opname.

3. [SharePoint-pagina's moderniseren](#3-modernize-sharepoint-pages)
    - U kunt geen onderwerpgebieden toepassen op moderne pagina's.
    - Identificeer geavanceerde pagina's met geavanceerde profielen die een moderne kandidaat zijn.

4. [Beveilig de inhoud op de juiste manier](#4-secure-content-appropriately)
    - Onderwerpen over onderwerpen zijn beveiligingsbeperkingen op basis van de machtigingen van een gebruiker.
    - Identificeer willekeurige inhoud met een onjuiste algemene of beperkte machtigingen:
      - Site-eigenaren stimuleren om machtigingen te controleren met behulp van de rapporten voordelen
      - Beheerders algemeen gedeelde inhoud laten controleren met behulp van zoeken
      - Stimuleer inhouds eigenaren voor het delen van inhoud die niet vertrouwelijk is en die een bredere voordeel kunnen uitmaken van de organisatie.
    - De configuratie van Microsoft Graph voor gebruikers en inhoud controleren:
      - In het onderwerp van de zoekfunctie wordt de configuratie geaccepteerd, met uitzondering van inhoud van zoekopdrachten of Delve Kijk of deze configuraties nog relevant zijn.

5. [Kennis beheerders en onderwerpen identificeren](#5-identify-knowledge-managers-and-topics)
    - Bestaande taxonomieën gebruiken om handmatig onderwerpen te maken.
    - De experts van onderhevige zaken (Kmo's) identificeren voor verwachte of geseede onderwerpen.
    - Identificeer sites met een grote hoofdtekst van waardevolle gegevens die kunnen worden gebruikt voor het testen van onderwerpen.
    - Kennis managers en community's van oefenen deel te nemen.

## <a name="1-migrate-content-to-microsoft-365"></a>1. inhoud migreren naar Microsoft 365

U kunt verschillende hulpprogramma's en Services raadplegen voor de migratie: u krijgt een overzicht van de informatie over het migreren van [inhoud naar Microsoft 365](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online). Migratiehulpprogramma's zijn:

- [Migratiebeheer](https://docs.microsoft.com/sharepointmigration/mm-get-started)
- [SharePoint-migratieprogramma (SPMT)](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Hulpmiddelen en services voor het migreren van partners](https://www.microsoft.com/solution-providers)

Optimaal van uw migratie maken:

- Migreren naar een moderne site, waaronder Microsoft teams. Hoewel indexeren kan plaatsvinden op een SharePoint-site (klassiek of modern), kunnen de onderwerpen van de gebruikers alleen met hooglichten en kaarten worden weergegeven op moderne pagina's.
- Gebruikersnamen onderhouden-met de meeste migratie hulpmiddelen kunt u gebruikersidentiteiten toewijzen aan de migratie, zodat de eigenschappen zoals gemaakt door of gewijzigd door worden bijgehouden na de migratie. Dit is belangrijk voor onderwerpen omdat de auteur van bestanden wordt gebruikt om de experts aan te geven die worden toegevoegd aan een onderwerpenpagina of kaart. 
- Een beschrijving van de namen van serviceaccounts geven: er worden ook enkele gevallen waarbij gebruikersnamen niet mogelijk zijn. Als u bijvoorbeeld inhoud migreert die door iemand is gemaakt en die niet meer een werknemer van de organisatie is. In dit geval wordt met de meeste migratieprogramma's een bestand verplaatst alsof het is gemaakt door een beheerdersaccount of een serviceaccount. Als dit regelmatig gebeurt, dan kan dit serviceaccount worden vermeld tegen onderwerpen als een expert. Dit is waar de naamgeving van dat account echt belangrijk wordt. Als u het concept maakt, is het mogelijk dat de aanwezigheid van deze niet-menselijke accounts bekend is voor uw gebruikers.

## <a name="2-connect-information-to-microsoft-graph"></a>2. gegevens aan Microsoft Graph koppelen

Ga als volgt te werk als u inhoud niet kunt migreren en vervolgens verbinden met Microsoft Graph:

- Overweeg om [Graph-inhouds verbindingslijnen](https://docs.microsoft.com/microsoftsearch/connectors-overview)te implementeren. Met connectors kan externe inhoud worden geïndexeerd in Microsoft Graph, zodat gebruikers deze kunnen ontdekken via Microsoft Search.
- Toekomstige ontwikkelingen zorgen voor externe gegevens in onderwerp-ervaringen.

## <a name="3-modernize-sharepoint-pages"></a>3. modern SharePoint-pagina's

Aangezien de onderwerpgebieden en de belangrijkste punten alleen kunnen worden weergegeven op moderne pagina's, moet u alle pagina's bijwerken die u wilt opnemen in het onderwerp ervaringen van klassiek naar modern. Zie [uw klassieke SharePoint-sites moderniseren](https://docs.microsoft.com/sharepoint/dev/transform/modernize-classic-sites). Met de [SharePoint-moderniserings scanner](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) kunt u uw klassieke sites voorbereiden voor modernisering.

Als u veel klassieke sites hebt, kunt u een prioriteit instellen voor de High-profielpagina's die u wilt converteren naar modern.

## <a name="4-secure-content-appropriately"></a>4. de inhoud passend beveiligen

Wanneer gebruikers met een onderwerpvenster of een onderwerp werken, kunnen ze verschillende bronnen zien. Dit komt doordat ze toegang hebben tot andere bestanden die zijn gekoppeld aan het onderwerp. Als uw onderliggende machtigingen te smal zijn, kunnen de serendipitous-aspecten van informatie detectie via onderwerpen niet worden verminderd. Als ze ook te groot zijn, kunnen de inhoud van een onderwerp worden geoppereerd met een gebruiker die u niet wilt zien.
Dit is essentieel voor het beheer van goede machtigingen. En een goed machtigings beheer is gebaseerd op een voortdurende samenwerking tussen beheerders en eigenaren van inhoud. Hoewel dit een voortdurende activiteit kan zijn, kunt u de volgende praktische stappen uitvoeren wanneer u een onderwerp gaat voorbereiden:

- Site-eigenaren stimuleren om delen en machtigingen te bekijken.

  SharePoint-site-eigenaren kunnen een rapport delen voor hun site met alle details van alle machtigingen en SharePoint-sites die zijn geconfigureerd op de [site weergeven.](https://docs.microsoft.com/sharepoint/sharing-reports) Dit bevat interne en externe (gast) gebruikers.

  Site-eigenaren kunnen ook zien wie er machtigingen voor de site heeft door naar de pagina **site machtigingen** en **Geavanceerde machtigingsinstellingen** te gaan.

  1. Kies op uw site **instellingen**  >  **site machtigingen**. Ga na of de lijst onder site-eigenaren, siteleden en bezoekers van de site wordt weergegeven. Kijk of er gastgebruikers zijn.
  2. Kies op de pagina **machtigingen** de optie **Geavanceerde instellingen voor machtigingen**. U kunt controleren op unieke machtigingen en zien wie er beperkte toegang heeft tot alle items in de site.

- Controleer Microsoft 365 groepen en teams, zodat u zeker weet dat ze op de juiste wijze zijn ingesteld als openbare of persoonlijke groepen of teams. Nieuwe teams en Microsoft 365-groepen zijn standaard ingesteld op privé, maar wanneer de eerste uitgave standaard openbaar was. Als u eerder een van deze technologieën kon overstappen, wilt u wellicht kijken. Daarnaast is de functie van een team vaak binnen de levenscyclus van het team, en moet de instelling mogelijk worden bijgewerkt om het huidige gebruik van het team weer te geven.
- Het gebruik van ' iedereen ', ' iedereen behalve externe gebruikers ' of grote beveiligingsgroepen, bekijken. Inhoud kan onjuist worden gedeeld met deze waarden. U kunt als volgt een overzicht van het gebruik van deze groepen bekijken:
  - Een account maken zonder groepslidmaatschappen
  - Gebruik zoeken met dit account om inhoud te ontdekken die algemeen wordt gedeeld.
  - Als ongeschikte inhoud voor dit account via een zoekopdracht zichtbaar is, kunt u met de site-eigenaren werken om de machtigings configuratie te corrigeren.

Naast de machtigingen kunt u ook het bereik bepalen van wat er kan worden gevonden. U bepaalt altijd wat er is geïndexeerd.

Beheerders kunnen indexeren configureren in het Microsoft 365-Beheercentrum. Wanneer u [kennisbeheer](set-up-topic-experiences.md)instelt, kunt u het volgende doen:

- Detectie toestaan op alle SharePoint-sites of sites opgeven die u wilt opnemen in of uitsluiten van de onderwerp-bronnen.
- Met gevoelige voorwaarden kunt u ook onderwerpen onder naam uitsluiten. Als u bijvoorbeeld de naam van een vertrouwelijk project hebt, waar u niet wilt dat een markering of kaart wordt weergegeven, ongeacht de machtigingen van de gebruiker, kunt u die projectnaam uitsluiten.

U kunt op inhouds niveau ook aangeven wat er wordt gedetecteerd. Alle configuraties die u hebt uitgevoerd om inhoud uit de zoekopdracht uit te sluiten, worden ook gebruikt door inhoud detectie. Als u bijvoorbeeld een specifieke documentbibliotheek uitsluiten van de zoekresultaten, wordt deze documentbibliotheek niet gebruikt voor het detecteren van het onderwerp.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. kennis beheerders en onderwerpen identificeren

Voor het beheren van onderwerpen zijn er drie belangrijke rollen, waaronder twee nieuwe functies van Azure Active Directory (AAD): kennis beheerder en Knowledge Manager:

- De kennis beheerder (KA) is een technische rol. Met deze functie kunnen de onderwerpen in het M365-Beheercentrum worden ingesteld, evenals de configuratie van detectie en zichtbaarheid van het onderwerp.
- De Knowledge Manager (KM) werkt samen met de onderwerpen zelf en ziet hun kwaliteit en volledigheid.
- Medewerkers van het onderwerp (televisiecamerasystemen) zijn niet gebaseerd op de rol van een AAD, maar machtigingen in het Beheercentrum. Hij of zij onderhevig is aan de inhoud van onderwerpen, zodat resources en personen kunnen worden toegevoegd.

Afhankelijk van uw organisatie hebt u mogelijk een aantal of veel personen die in deze rollen handelen. Voor sommige organisaties kunnen dit dezelfde personen zijn.

| Kennis beheerder | Knowledge Manager | Bijdrage van onderwerp |
|:-------|:-------|:-------|:-------|
| AAD-rol | AAD-rol | FINANCIERING |
| Toegang heeft tot het Beheercentrum | Toegang heeft tot het Beheercentrum | Geen toegang tot het Beheercentrum |
| Stelt onderwerp ervaringen in | Bezit van beheer en kwaliteit van onderwerpen | Draagt bij aan onderwerpen op basis van hun expertise. |
| Zorgt ervoor dat de normen voor beveiliging en naleving worden afgedwongen en de licentieovereenkomst begrijpt.| Hiermee kunt u beheertaken voor het onderwerp uitvoeren, zoals het maken, bewerken, verwijderen en negeren van onderwerpen. Ondersteuning van medewerkers van een onderwerp met hun taken. | De informatie en inhoud op topic pagina's, waaronder de personen en resources, zijn vastgemaakt aan dat onderwerp. |

Voor gebruikers in de context van hun werk worden de belangrijkste en de kaarten getoond, bijvoorbeeld door de moderne pagina's in SharePoint. U bestuurt de eindgebruikers ervaring voor onderwerpen.

- Wie kan de onderwerpen zien? De zichtbaarheid van het onderwerp is geconfigureerd in het Microsoft 365-Beheercentrum. Kies de groepen die u wilt toestaan om onderwerpen weer te geven:
  - Iedereen binnen mijn organisatie. ' Iedereen ' bevat geen gasten, het is alle interne gebruikers in de adreslijst.
  - Alleen geselecteerde personen of beveiligingsgroepen (deze optie is handig wanneer u nog steeds topic-ervaringen uitrollen, zodat u kunt testen met een subset van gebruikers). Als u wilt dat gasten onderwerpen kunnen zien, moet u de optie geselecteerde personen of beveiligingsgroepen gebruiken en een licentie verlenen.
  - Niemand.

    Alle gebruikers, zelfs gastgebruikers, moeten een licentie hebben toegepast om het onderwerp te kunnen bekijken. Houd er rekening mee dat machtigingen altijd aangeven wat er zichtbaar kan zijn.

- Welke onderwerpen zijn zichtbaar? U kunt kiezen voor:
  - Alle kandidaat-onderwerpen weergeven.
  - Alleen bevestigde onderwerpen weergeven.

Nu we de managers, experts en gebruikers hebben, kunnen we de onderwerpen zelf bespreken.

- Het is een goede gewoonte om onderwerpen te seeden in de lijst met onderwerpen. De kwaliteit en de hoeveelheid van onderwerpen is gebaseerd op uw inhoud, maar wordt alleen als onderwerp gemaakt als deze wordt opgenomen in de inhoud van het bereik. Als er voldoende informatie en bewijs voor het onderwerp worden weergegeven, wordt deze door de AI gemaakt. Met behulp van de experts voor de kennis Manager en het onderwerp kunnen we u helpen. Met de AI is de beste route voor kwaliteits onderwerpen de beste routering van mensen met de AI-ervaring. Daarom kunt u deze handmatig maken in het onderwerp centrum. Dit levert de AI een sterke signalering van de relevantie van dit onderwerp en identificeert bronnen en personen die aan dat onderwerp moeten worden gekoppeld.
- U kunt bestaande taxonomieën gebruiken voor het plannen van uw onderwerp via SharePoint of elders. Bestaande taxonomieën bevatten vaak organisatie voorwaarden, producten, onderwerpgebieden, enzovoort. Bronnen voor onderwerpen kunnen ook worden weergegeven in een lijst met projecten, bestaande Zoek bladwijzers, enzovoort.
