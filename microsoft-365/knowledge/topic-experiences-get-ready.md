---
title: Uw omgeving voorbereiden op Microsoft Viva Topics
description: Maak uw omgeving gereed, zodat u zo veel mogelijk inhoud voor uw gebruikers kunt Microsoft Viva Topics.
ms.author: samanro
author: samanro
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 8e1da50c120d333812014f6720f1168d4afb9741
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984878"
---
# <a name="get-your-environment-ready-for-microsoft-viva-topics"></a>Uw omgeving voorbereiden op Microsoft Viva Topics

Als u zoveel mogelijk gebruik wilt maken van Viva-onderwerpen, wilt u zo veel mogelijk inhoud hebben voor het ontdekken van onderwerpen, zodat u een uitgebreide set onderwerpen voor uw gebruikers kunt hebben. Maar welke inhoud moet worden gebruikt voor onderwerpdetectie? Hoe maximaliseert u de geïndexeerde inhoud terwijl u de controle hebt? Hoe meer inhoud binnen het bereik valt, hoe beter de inzichten die de kunstmatige intelligentie kan ontdekken. In dit artikel vindt u de planningsstappen om ervoor te zorgen dat u de juiste inhoud op neemt en dat u de juiste personen en resources hebt om een goede ervaring voor uw gebruikers te maken.

Als u viva-onderwerpen wilt plannen, moet u het volgende doen:

![Migreren, verbinden, moderniseren, beveiligen en identificeren van stappen voor onboarding naar Viva-onderwerpen.](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Inhoud migreren naar SharePoint](#1-migrate-content-to-microsoft-365)
    - Onderwerpindexering bevat alleen inhoud op SharePoint sites.
      - Migreert waar mogelijk waardevolle inhoud naar SharePoint Online vanuit externe bronnen.
      - Geef prioriteit aan inhoudsbronnen met een hoog potentieel voor stilzwijgende kennis.
      - Markeer de voordelen van Viva-onderwerpen om gebruikers aan te moedigen inhoud te verplaatsen van OneDrive naar SharePoint sites.

2. [Verbinding maken informatie naar Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - In de toekomst kan externe inhoud in de kennisgrafiek worden gebracht en beschikbaar komen.
    - Voor inhoud die niet kan worden verplaatst, kunt u Graph connectors gebruiken om het zoeken te verbeteren en u voor te bereiden op toekomstige opname.

3. [Pagina's SharePoint moderniseren](#3-modernize-sharepoint-pages)
    - Onderwerpkaarten kunnen alleen op moderne pagina's worden weergegeven.
    - Identificeer klassieke pagina's met een hoog profiel die kandidaten voor de modernisatie zijn.

4. [Inhoud op de juiste manier beveiligen](#4-secure-content-appropriately)
    - Onderwerpbronnen zijn beveiliging bijgesneden op basis van de machtigingen van een gebruiker.
    - Identificeer inhoud met onjuist brede of beperkende machtigingen:
      - Site-eigenaren aanmoedigen om de rapporten delen te gebruiken om machtigingen te controleren
      - Beheerders laten breed gedeelde inhoud controleren met behulp van Zoeken
      - Moedig eigenaren van inhoud aan om inhoud te delen die niet gevoelig is en die mogelijk een breder voordeel voor de organisatie heeft.
    - Controleer uw Microsoft-Graph gebruikers en inhoud:
      - Onderwerpindexering honors configuration excluding content from Search or Delve (example, NOINDEX). Controleer of deze configuraties nog steeds relevant zijn.

5. [Kennismanagers en -onderwerpen identificeren](#5-identify-knowledge-managers-and-topics)
    - Gebruik bestaande taxonomie om handmatig onderwerpen te maken of help bij het bevestigen van AI-voorgestelde onderwerpen.
    - Identificeer deskundigen op het gebied van onderwerp (kleine en middelgrote ondernemingen) voor verwachte of gezaaide onderwerpen.
    - Identificeer sites die een grote hoeveelheid waardevolle gegevens bevatten die kunnen worden gebruikt om onderwerpmining te piloten.
    - Engage Knowledge Managers en community's van de praktijk.

## <a name="1-migrate-content-to-microsoft-365"></a>1. Inhoud migreren naar Microsoft 365

Er zijn verschillende hulpprogramma's en services die u kunt helpen bij uw migratie: u kunt een overzicht en informatie krijgen over hoe u migreert bij Uw inhoud migreren naar [Microsoft 365.](/sharepointmigration/migrate-to-sharepoint-online) Migratiehulpprogramma's zijn:

- [Migratiebeheer](/sharepointmigration/mm-get-started)
- [SharePoint Migratiehulpmiddel (SPMT)](/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Hulpprogramma's en services voor partnermigratie](https://www.microsoft.com/solution-providers)

Maak het meeste uit uw migratie:

- Migreren naar een moderne site, inclusief Microsoft Teams. Hoewel indexeren kan plaatsvinden op SharePoint site (klassiek of modern), worden onderwerpen aan gebruikers weergegeven via highlights en kaarten alleen op moderne pagina's.
- Gebruikersnamen behouden: met de meeste migratiehulpprogramma's kunt u gebruikersidentiteiten in de migratie in kaart brengen, zodat eigenschappen zoals Gemaakt door of Gewijzigd door na de migratie worden behouden. Dit is belangrijk voor onderwerpen, omdat het auteurschap van bestanden wordt gebruikt om de experts te identificeren die zijn toegevoegd aan een onderwerppagina of -kaart. 
- Namen van serviceaccounts beschrijven: in sommige gevallen is het niet mogelijk gebruikersnamen te onderhouden. Als u bijvoorbeeld inhoud migreert die is gemaakt door iemand die geen werknemer meer van de organisatie is. In dit geval worden met de meeste migratiehulpmiddelen een bestand verplaatst alsof het is gemaakt door een beheerdersaccount of een serviceaccount. Als dit vaak gebeurt, kan dat serviceaccount vervolgens als expert worden weergegeven tegen onderwerpen. Hier wordt de naamgeving van dat account echt belangrijk. Als u het beschrijvend maakt, is de aanwezigheid van deze niet-menselijke accounts begrijpelijk voor gebruikers die onderwerpen consumeren.

## <a name="2-connect-information-to-microsoft-graph"></a>2. Verbinding maken naar Microsoft-Graph

Als u bepaalde inhoud niet kunt migreren, verbindt u deze met de Microsoft-Graph:

- Overweeg om Graph [connectors voor inhoud te implementeren.](/microsoftsearch/connectors-overview) Met behulp van verbindingslijnen kan externe inhoud worden geïndexeerd in de Microsoft-Graph, waar gebruikers deze vervolgens kunnen ontdekken via Microsoft Search.
- Toekomstige ontwikkelingen brengen externe gegevens naar Viva-onderwerpen.

## <a name="3-modernize-sharepoint-pages"></a>3. De pagina'SharePoint moderniseren

Omdat onderwerpkaarten en highlights alleen op moderne pagina's kunnen worden weergegeven, kunt u pagina's die u wilt opnemen in Viva-onderwerpen bijwerken van klassiek naar modern. Zie [Uw klassieke sites SharePoint moderniseren.](/sharepoint/dev/transform/modernize-classic-sites) U kunt de scanner voor [SharePoint moderne versie gebruiken](/sharepoint/dev/transform/modernize-scanner) om uw klassieke sites voor te bereiden op de modernisatie.

Als u veel klassieke sites hebt, geeft u prioriteit aan pagina's met een hoog profiel om te converteren naar modern.

## <a name="4-secure-content-appropriately"></a>4. Inhoud op de juiste manier beveiligen

Wanneer gebruikers werken met een onderwerpkaart of een onderwerppagina, zien ze mogelijk verschillende bronnen. Dit komt omdat ze toegang hebben tot verschillende bestanden die aan het onderwerp zijn gekoppeld. Als uw onderliggende machtigingen te strikt zijn, kunnen de serendipitous aspecten van informatiedetectie via onderwerpen worden verminderd. Als ze echter te breed zijn, kan een onderwerp inhoud aan een gebruiker toevoegen die u niet wilt zien.
Goed machtigingsbeheer is hierbij essentieel. En goed machtigingsbeheer is gebaseerd op een doorlopend partnerschap tussen beheerders en inhoudseigenaren. Hoewel dit een lopende activiteit kan zijn, zijn er enkele praktische stappen die u kunt nemen bij het voorbereiden van onderwerpen:

- Moedig site-eigenaren aan om delen en machtigingen te controleren.

  SharePoint site-eigenaren kunnen een rapport voor delen voor hun site bekijken met volledige details van alle machtigingen en koppelingen voor delen die zijn geconfigureerd op de site, zie [Rapporten delen.](/sharepoint/sharing-reports) Hier worden interne en externe (gast)gebruikers vermeld.

  Site-eigenaren kunnen ook zien wie machtigingen heeft voor de site door naar de **pagina's Sitemachtigingen** en Geavanceerde **machtigingen Instellingen** gaan.

  1. Kies op uw site de **Instellingen**  >  **Sitemachtigingen.** Controleer wie wordt weergegeven onder Site-eigenaren, Siteleden en Sitebezoekers. Controleer op gastgebruikers.
  2. Kies op **de pagina** Machtigingen de optie **Geavanceerde machtigingen Instellingen.** U kunt controleren op unieke machtigingen en zien wie beperkte toegang heeft tot items op de site.

- Controleer Microsoft 365 groepen en Teams om ervoor te zorgen dat ze op de juiste manier zijn ingesteld als openbare of persoonlijke groepen of teams. Nieuwe Teams en Microsoft 365 groepen zijn standaard ingesteld op privé, maar wanneer ze voor het eerst werden uitgebracht, waren ze standaard openbaar. Als u eerder deze technologieën hebt gebruikt, kunt u dit controleren. Bovendien ontwikkelt de functie van een team zich vaak gedurende de levenscyclus en moet de instelling mogelijk worden bijgewerkt om het huidige gebruik van het team weer te geven.
- Controleer het gebruik van 'iedereen', 'iedereen behalve externe gebruikers' of brede beveiligingsgroepen. Inhoud kan onjuist worden gedeeld met deze waarden. Als u het gebruik van deze groepen wilt bekijken, kunt u het volgende doen:
  - Een account maken zonder groepslidmaatschap
  - Gebruik zoeken met dit account om inhoud te ontdekken die breed wordt gedeeld.
  - Als ongepaste inhoud zichtbaar is voor dit account door middel van zoeken, kunt u samen met de site-eigenaren de machtigingsconfiguratie corrigeren.

Naast machtigingen kunt u ook het bereik bepalen van wat er kan worden ontdekt via onderwerpen. U hebt altijd de controle over wat wordt geïndexeerd.

Beheerders kunnen indexering configureren in het Microsoft 365-beheer Center. Wanneer u [Viva-onderwerpen in stelt,](set-up-topic-experiences.md)kunt u het volgende doen:

- Sta detectie toe op alle SharePoint sites of geef sites op die u wilt opnemen of uitsluiten als onderwerpbronnen.
- Waar u gevoelige termen hebt, kunt u ook onderwerpen uitsluiten op naam. Als u bijvoorbeeld de naam van een gevoelig project hebt, waarbij u niet wilt dat een markering of kaart wordt weergegeven, ongeacht de machtigingen van de gebruiker, kunt u die projectnaam uitsluiten.

Op inhoudsniveau kunt u ook bepalen wat er kan worden ontdekt. Elke configuratie die u hebt uitgevoerd om inhoud uit te sluiten van zoeken, wordt ook gebruikt door inhoudsdetectie. Als u bijvoorbeeld hebt uitgesloten dat een bepaalde documentbibliotheek wordt weergegeven in zoekresultaten, wordt deze documentbibliotheek niet gebruikt voor onderwerpdetectie.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. Kennismanagers en onderwerpen identificeren

Het beheren van onderwerpen omvat drie belangrijke rollen, waaronder twee nieuwe Azure Active Directory (AAD)-rollen: Knowledge Administrator en Knowledge Manager:

- De Kennisbeheerder (KA) is een technische rol, meestal in DE IT. Met deze rol kunt u de Viva-onderwerpen instellen in het M365-beheercentrum, evenals de configuratie van onderwerpdetectie en zichtbaarheid.
- De Knowledge Manager (KM) werkt zelf met de onderwerpen en houdt toezicht op de kwaliteit en volledigheid.
- Onderwerpcontribuanten (TCs) zijn niet gebaseerd op een AAD-rol, maar op machtigingen in het beheercentrum. Ze zijn vakexperts die de inhoud over onderwerpen kunnen beheren en resources en personen kunnen toevoegen.

Afhankelijk van uw organisatie zijn er mogelijk weinig of veel personen die in deze rollen werken. Voor sommige organisaties kunnen dit dezelfde personen zijn.

| Kennisbeheerder | Knowledge manager | Onderwerpbetaler |
|:-------|:-------|:-------|:-------|
| AAD-rol | AAD-rol | MKB |
| Heeft toegang tot het beheercentrum | Heeft toegang tot het beheercentrum | Geen toegang tot het beheercentrum |
| Viva-onderwerpen in stellen | Eigenaar van beheer en kwaliteit van onderwerpen | Draagt bij aan onderwerpen op basis van hun expertise. |
| Zorgt ervoor dat beveiligings- en compliancestandaarden worden afgedwongen en begrijpt de licentieovereenkomst.| Voert onderwerpbeheertaken uit, zoals het maken, bewerken, verwijderen en weigeren van onderwerpen. Ondersteunt inzenders van onderwerpen bij hun taken. | Curseert de informatie en inhoud op onderwerppagina's, inclusief welke personen en resources aan dat onderwerp zijn vastgemaakt. |

Highlights en kaarten worden weergegeven voor gebruikers in de context van hun werk, bijvoorbeeld wanneer ze moderne pagina's in SharePoint. U kunt de ervaring van de eindgebruiker bepalen voor onderwerpen.

- Wie kunt u Onderwerpen zien? De zichtbaarheid van het onderwerp is geconfigureerd in het Microsoft 365-beheer Center. Kies welke groepen u wilt toestaan om onderwerpen te bekijken:
  - Iedereen in mijn organisatie. 'Iedereen' bevat geen gasten, het zijn allemaal interne gebruikers in uw adreslijst
  - Alleen geselecteerde personen of beveiligingsgroepen (deze optie is goed terwijl u nog Steeds Viva-onderwerpen uitrolt, zodat u kunt testen met een subset gebruikers). Als u wilt dat gasten Onderwerpen bekijken, moet u de optie 'geselecteerde personen of beveiligingsgroepen' gebruiken en hen een licentie verlenen.
  - Niemand.

    Alle gebruikers, zelfs gastgebruikers, moeten een licentie hebben toegepast om de onderwerpervaring te kunnen bekijken. En vergeet niet dat machtigingen altijd bepalen wat er kan worden gezien.

- Welke onderwerpen zijn zichtbaar? U kunt kiezen uit:
  - Alle kandidaat-onderwerpen laten zien.
  - Alleen bevestigd onderwerpen tonen.

Nu we de managers, experts en gebruikers hebben, kunnen we de onderwerpen zelf bespreken.

- Het is een goede gewoonte om onderwerpen in uw onderwerplijst te plaatsen. De kwaliteit en hoeveelheid onderwerpen is gebaseerd op uw inhoud. Deze wordt alleen als onderwerp gemaakt als deze is opgenomen in de inhoud die binnen het bereik valt. Als er voldoende informatie en bewijs voor het onderwerp is, wordt deze gemaakt door de AI. Seeding topics is where the Knowledge Manager and subject-matter experts can help. Het combineren van menselijke kennis met de AI is de beste route voor kwaliteitsonderwerpen. Dus als er onderwerpen zijn die u verwacht, kunt u deze handmatig maken in het onderwerpcentrum. Als u dit doet, geeft de AI een sterk signaal van de relevantie van dat onderwerp en worden resources en personen aan dat onderwerp verbonden.
- Gebruik bestaande taxonomie om uw onderwerp te plannen, van SharePoint of ergens anders. Bestaande taxonomieën bevatten vaak organisatievoorwaarden, producten, onderwerpgebieden, en meer. Bronnen voor onderwerpen kunnen ook afkomstig zijn van lijsten met projecten, bestaande zoekwijzers, en meer.