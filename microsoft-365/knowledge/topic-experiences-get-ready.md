---
title: Uw omgeving voorbereiden op Microsoft Viva-onderwerpen
description: Bereid uw omgeving voor, zodat u zo veel mogelijk inhoud voor uw gebruikers kunt aanbieden met Microsoft Viva-onderwerpen.
ms.author: samanro
author: samanro
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 5a13af3e78848471b436d44ab051eca945176c74
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107694"
---
# <a name="get-your-environment-ready-for-microsoft-viva-topics"></a>Uw omgeving voorbereiden op Microsoft Viva-onderwerpen

Als u het meeste uit Viva-onderwerpen wilt halen, wilt u zo veel mogelijk inhoud toevoegen aan onderwerpdetectie, zodat u een uitgebreide reeks onderwerpen voor uw gebruikers kunt gebruiken. Maar welke inhoud moet worden gebruikt voor onderwerpdetectie? Hoe maximaliseert u de geïndexeerde inhoud en hebt u de controle? Hoe meer inhoud binnen het bereik valt, hoe beter de inzichten die kunstmatige intelligentie kan ontdekken. In dit artikel wordt stap voor stap beschreven hoe u ervoor kunt zorgen dat u de juiste inhoud op neemt en dat u de juiste personen en resources hebt om uw gebruikers een goede ervaring te bieden.

Als u een planning wilt maken voor Viva-onderwerpen, moet u:

![Migreren, verbinden, moderniseren, beveiligen en identificeren van de stappen voor onboarding naar kennisbeheer](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Inhoud migreren naar SharePoint](#1-migrate-content-to-microsoft-365)
    - Onderwerpindexering bevat alleen inhoud op SharePoint-sites.
      - Migreert waar mogelijk waardevolle inhoud van externe bronnen naar SharePoint Online.
      - Geef inhoudsbronnen prioriteit met veel mogelijkheden voor bezwijgende kennis.
      - Belicht de voordelen van kennisbeheer om gebruikers aan te moedigen inhoud van OneDrive naar SharePoint-sites te verplaatsen.

2. [Gegevens verbinden met Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - In de toekomst kan externe inhoud in de Knowledge Graph worden gebruikt en beschikbaar komen.
    - Voor inhoud die niet kan worden verplaatst, kunt u Graph Connectors gebruiken om zoekopdrachten te verbeteren en u voor te bereiden op toekomstige opname.

3. [SharePoint-pagina's moderniseren](#3-modernize-sharepoint-pages)
    - Onderwerpkaarten kunnen alleen op moderne pagina's worden weergegeven.
    - Identificeer klassieke pagina's met hoge profielen die kandidaten zijn voor modernisatie.

4. [Inhoud op de juiste manier beveiligen](#4-secure-content-appropriately)
    - Onderwerpbronnen worden beveiligd op basis van de machtigingen van een gebruiker.
    - Inhoud identificeren die mogelijk onjuist algemene of beperkende machtigingen heeft:
      - Site-eigenaren aanmoedigen om de rapporten voor delen te gebruiken om machtigingen te bekijken
      - Beheerders breed gedeelde inhoud laten controleren met de zoekfunctie
      - Stimuleer eigenaren van inhoud om inhoud te delen die niet gevoelig is en die mogelijk breder voordeel heeft voor de organisatie.
    - Controleer uw Microsoft Graph-configuratie voor gebruikers en inhoud:
      - Bij het indexeren van onderwerpen wordt de configuratie niet gebruikt, met uitzondering van inhoud van Zoeken of Delve (bijvoorbeeld NOINDEX). Controleer of deze configuraties nog steeds relevant zijn.

5. [Kennisbeheerders en onderwerpen identificeren](#5-identify-knowledge-managers-and-topics)
    - Gebruik bestaande taxonomieën om handmatig onderwerpen te maken of hulp bij het bevestigen van AI-voorgestelde onderwerpen.
    - Identificeer deskundigen op het gebied van verwachte of seeded onderwerpen.
    - Identificeer sites die een grote hoeveelheid waardevolle gegevens bevatten die kunnen worden gebruikt voor het gebruik van pilot onderwerpmining.
    - Betrek Knowledge Managers en community's van de praktijk.

## <a name="1-migrate-content-to-microsoft-365"></a>1. Inhoud migreren naar Microsoft 365

Er zijn verschillende hulpprogramma's en services die u kunt helpen bij de migratie. U krijgt een overzicht en informatie over hoe u migreert op De inhoud migreren naar [Microsoft 365.](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) Hulpprogramma's voor migratie zijn:

- [Migratiebeheer](https://docs.microsoft.com/sharepointmigration/mm-get-started)
- [SharePoint-migratieprogramma (SPMT)](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Hulpprogramma's en services voor partnermigratie](https://www.microsoft.com/solution-providers)

Maak het meeste uit de migratie:

- Migreren naar een moderne site , waaronder Microsoft Teams. Hoewel het indexeren kan plaatsvinden op een SharePoint-site (klassiek of modern), worden onderwerpen alleen weergegeven voor gebruikers via highlights en kaarten op moderne pagina's.
- Gebruikersnamen onderhouden: met de meeste migratiehulpprogramma's kunt u gebruikersidentiteiten aan de migratie aanpassen, zodat eigenschappen als Gemaakt door of Gewijzigd door na de migratie behouden blijven. Dit is belangrijk voor onderwerpen omdat de auteur van bestanden wordt gebruikt om de experts te identificeren die aan een onderwerppagina of -kaart zijn toegevoegd. 
- Maak namen van serviceaccounts beschrijvend: in sommige gevallen is het niet mogelijk gebruikersnamen te onderhouden. Bijvoorbeeld als u inhoud migreert die is gemaakt door iemand die geen werknemer van de organisatie meer is. In dit geval wordt met de meeste migratiehulpprogramma's een bestand verplaatst alsof het is gemaakt door een beheerdersaccount of een serviceaccount. Als dit regelmatig gebeurt, kan dat serviceaccount als expert worden vermeld op onderwerpen. Hier wordt de naamgeving van dat account heel belangrijk. Als u het beschrijvend maakt, is de aanwezigheid van deze niet-menselijke accounts begrijpelijk door de onderwerpen die door gebruikers worden gebruikt.

## <a name="2-connect-information-to-microsoft-graph"></a>2. Informatie verbinden met Microsoft Graph

Als u bepaalde inhoud niet kunt migreren, maakt u verbinding met Microsoft Graph:

- Overweeg om [Graph Content Connectors te implementeren.](https://docs.microsoft.com/microsoftsearch/connectors-overview) Via connectors kan externe inhoud worden geïndexeerd in Microsoft Graph, waar gebruikers deze vervolgens kunnen vinden via Microsoft Search.
- Toekomstige ontwikkelingen brengen externe gegevens naar Viva-onderwerpen.

## <a name="3-modernize-sharepoint-pages"></a>3. SharePoint-pagina's moderniseren

Aangezien onderwerpkaarten en highlights alleen op moderne pagina's kunnen worden weergegeven, kunt u pagina's die u wilt opnemen in Viva-onderwerpen bijwerken van klassiek naar modern. Zie [Uw klassieke SharePoint-sites moderniseren.](https://docs.microsoft.com/sharepoint/dev/transform/modernize-classic-sites) U kunt de [SharePoint-scanner voor modernisatie gebruiken](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) om uw klassieke sites voor te bereiden op modernisatie.

Als u veel klassieke sites hebt, moet u hoge profielpagina's prioriteit geven om te converteren naar modern.

## <a name="4-secure-content-appropriately"></a>4. Inhoud op de juiste manier beveiligen

Wanneer gebruikers werken met een onderwerpkaart of een onderwerppagina, zien ze mogelijk verschillende bronnen. Dit komt omdat ze toegang hebben tot verschillende bestanden die aan het onderwerp zijn gekoppeld. Als uw onderliggende machtigingen te strikt zijn, nemen de serendipitous aspecten van informatiedetectie via onderwerpen mogelijk af. Aan de andere kant, als ze te ruim zijn, kan een onderwerp inhoud aan de gebruiker laten zien die u niet voor de hand hebt.
Goed machtigingenbeheer is hier essentieel. En goed machtigingenbeheer is gebaseerd op een continue samenwerking tussen beheerders en eigenaren van inhoud. Hoewel dit een lopende activiteit kan zijn, zijn er enkele praktische stappen die u kunt ondernemen bij het voorbereiden van onderwerpen:

- Moedig site-eigenaren aan om het delen en machtigingen te controleren.

  SharePoint-site-eigenaren kunnen een rapport voor delen voor hun site bekijken met alle details van alle machtigingen en koppelingen voor delen die op de site zijn geconfigureerd. Zie [Rapporten delen.](https://docs.microsoft.com/sharepoint/sharing-reports) Hier worden interne en externe gebruikers (gast) vermeld.

  Site-eigenaren kunnen ook zien wie machtigingen heeft  voor de site door naar de pagina's Sitemachtigingen en Geavanceerde **machtigingeninstellingen te** gaan.

  1. Kies Instellingen voor   >  **sitemachtigingen** op uw site. Controleer wie wordt weergegeven onder Site-eigenaren, Siteleden en Sitebezoekers. Controleer of er gastgebruikers zijn.
  2. Kies Geavanceerde **machtigingeninstellingen** op de pagina **Machtigingen.** U kunt controleren op unieke machtigingen en bekijken wie beperkte toegang heeft tot items op de site.

- Controleer Microsoft 365 Groepen en Teams om er zeker van te zijn dat ze goed zijn ingesteld als openbare of privégroepen of teams. Nieuwe Teams en Microsoft 365-groepen zijn standaard ingesteld op privé, maar wanneer deze voor het eerst werden uitgebracht, waren deze standaard openbaar. Als u eerder deze technologieën hebt gebruikt, is het misschien een goed begin om dit na te kijken. Bovendien ontwikkelt de functie van een team zich tijdens de levenscyclus vaak verder en moet de instelling mogelijk worden bijgewerkt om het huidige gebruik van het team aan te geven.
- Controleer het gebruik van 'iedereen', 'iedereen behalve externe gebruikers' of uitgebreide beveiligingsgroepen. Inhoud wordt mogelijk onjuist gedeeld met deze waarden. Als u het gebruik van deze groepen wilt bekijken, kunt u het volgende doen:
  - Een account zonder groepslidmaatschap maken
  - Gebruik zoeken met dit account om inhoud te vinden die algemeen wordt gedeeld.
  - Als er ongepaste inhoud zichtbaar is voor dit account via een zoekopdracht, kunt u samen met de site-eigenaren de machtigingsconfiguratie corrigeren.

Naast machtigingen kunt u ook bepalen wat er in de onderwerpen te vinden is. U hebt altijd de controle over wat er wordt geïndexeerd.

Beheerders kunnen indexering configureren in het Microsoft 365-beheercentrum. Wanneer u [Knowledge Management in stelt,](set-up-topic-experiences.md)kunt u het volgende doen:

- Toestaan dat alle SharePoint-sites worden gevonden of sites opgeven die als onderwerpbronnen moeten worden gebruikt of uitgesloten.
- Wanneer u vertrouwelijke termen hebt, kunt u onderwerpen ook op naam uitsluiten. Als u bijvoorbeeld de naam van een gevoelig project hebt en u geen markering of kaart wilt weergegeven, ongeacht de machtigingen van de gebruiker, kunt u de projectnaam uitsluiten.

Op inhoudsniveau kunt u ook bepalen wat er kan worden ontdekt. Elke configuratie die u hebt uitgevoerd om inhoud uit te sluiten van zoekopdrachten, wordt ook gebruikt door content discovery. Dus als u bijvoorbeeld hebt uitgesloten dat een bepaalde documentbibliotheek wordt weergegeven in zoekresultaten, wordt deze documentbibliotheek niet gebruikt voor onderwerpdetectie.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. Kennisbeheerders en onderwerpen identificeren

Het beheren van onderwerpen omvat drie belangrijke rollen, waaronder twee nieuwe AAD-rollen (Azure Active Directory) : Knowledge Administrator en Knowledge Manager:

- De Knowledge Administrator (KA) is een technische rol, meestal in IT. Met deze rol kunnen de Viva-onderwerpen worden ingesteld in het M365-beheercentrum, evenals de configuratie van onderwerpdetectie en zichtbaarheid.
- De Knowledge Manager (KM) werkt met de onderwerpen zelf en is verantwoordelijk voor de kwaliteit en volledigheid.
- Onderwerpbijdragers (TCs) zijn niet gebaseerd op een AAD-rol, maar machtigingen in het beheercentrum. Dit zijn deskundigen die onderwerpen kunnen bespreken en informatiebronnen en personen kunnen toevoegen.

Afhankelijk van uw organisatie kunnen er maar weinig of veel personen in deze rollen werken. Voor sommige organisaties zijn dit mogelijk dezelfde personen.

| Kennisbeheerder | Knowledge Manager | Onderwerpbijdrager |
|:-------|:-------|:-------|:-------|
| AAD-rol | AAD-rol | MÉO |
| Heeft toegang tot het beheercentrum | Heeft toegang tot het beheercentrum | Geen toegang tot het beheercentrum |
| Stelt Viva-onderwerpen in | Eigenaar zijn van beheer en kwaliteit van onderwerpen | Draagt bij aan onderwerpen op basis van hun expertise. |
| Zorgt ervoor dat standaarden voor beveiliging en naleving worden afgedwongen en dat de licentieovereenkomst wordt begrepen.| Voert taken voor onderwerpbeheer uit, zoals onderwerpen maken, bewerken, verwijderen en weigeren. Ondersteunt inzenders van onderwerpen met hun taken. | Curseert de informatie en inhoud op onderwerppagina's, waaronder welke personen en resources aan dat onderwerp zijn vastgemaakt. |

Highlights en kaarten worden aan gebruikers weergegeven in de context van hun werk, bijvoorbeeld wanneer ze door moderne pagina's bladeren in SharePoint. U controleert de eindgebruikerservaring voor onderwerpen.

- Wie kan Onderwerpen zien? De zichtbaarheid van het onderwerp is geconfigureerd in het Microsoft 365-beheercentrum. Kies welke groepen u wilt toestaan om onderwerpen te bekijken:
  - Iedereen in mijn organisatie. 'Iedereen' bevat geen gasten, het zijn alle interne gebruikers in uw adreslijst
  - Alleen geselecteerde personen of beveiligingsgroepen (deze optie is goed wanneer u nog Viva-onderwerpen uitrolt, zodat u kunt testen met een subset van gebruikers). Als u wilt dat gasten Onderwerpen kunnen bekijken, moet u de optie 'geselecteerde personen of beveiligingsgroepen' gebruiken en hen een licentie verlenen.
  - Niemand.

    Alle gebruikers, ook gastgebruikers, moeten een licentie hebben toegepast om het onderwerp te kunnen bekijken. En vergeet niet dat machtigingen altijd bepalen wat zichtbaar is.

- Welke onderwerpen zijn zichtbaar? U kunt het volgende doen:
  - Alle kandidaat-onderwerpen tonen.
  - Alleen bevestigd onderwerpen tonen.

Nu we de managers, experts en gebruikers hebben, kunnen we het over de onderwerpen zelf hebben.

- Het is een goede gewoonte om onderwerpen in uw onderwerplijst te plaatsen. De kwaliteit en hoeveelheid onderwerpen is gebaseerd op uw inhoud. Deze wordt alleen als een onderwerp gemaakt als deze is opgenomen in de inhoud die binnen het bereik valt. Als er voldoende informatie en bewijs beschikbaar is voor het onderwerp, wordt deze gemaakt door de AI. Het plaatsen van onderwerpen is de plaats waar Knowledge Manager en deskundigen op onderwerp u kunnen helpen. Het combineren van menselijke kennis met de AI is de beste route voor kwaliteitsonderwerpen. Als er onderwerpen zijn die u verwacht, kunt u deze dus handmatig maken in het onderwerpcentrum. Als u dat doet, geeft de AI een sterk signaal van de relevantie van dat onderwerp en identificeert het resources en personen die aan dat onderwerp moeten worden geassocieerd.
- Gebruik bestaande taxonomieën voor de planning van uw onderwerp, hetzij vanuit SharePoint of ergens anders. Bestaande taxonomieën bevatten vaak bedrijfsvoorwaarden, producten, onderwerpgebieden, en meer. Bronnen voor onderwerpen kunnen ook afkomstig zijn van lijsten met projecten, bestaande zoek bladwijzers, en meer.
