---
title: Overzicht van Microsoft Viva Topics
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: cjtan; lauris
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Overzicht van Viva Topics.
ms.openlocfilehash: 89f35062009372c2a44dddcb4e4d2934e494282f
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908318"
---
# <a name="microsoft-viva-topics-overview"></a>Overzicht van Microsoft Viva Topics 

Viva Topics gebruikt Microsoft AI-technologie, Microsoft 365, Microsoft Graph, Zoeken en andere onderdelen en services om uw gebruikers kennis te brengen in de Microsoft 365-apps die ze dagelijks gebruiken, te beginnen met SharePoint moderne pagina's, Microsoft Zoeken en Zoeken in Word, PowerPoint, Outlook en Excel.

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

<br/>

Viva Topics helpt bij het oplossen van een belangrijk zakelijk probleem in veel bedrijven, door de informatie te verstrekken aan gebruikers wanneer ze deze nodig hebben. Zo moeten nieuwe werknemers snel veel nieuwe informatie opnemen en komen ze bij het doorlezen van bedrijfsgegevens termen tegen waar ze niets van weten. Om meer te weten moet de gebruiker even stoppen waar hij of zij mee bezig is, en gaat kostbare tijd verloren met het zoeken naar informatie, zoals over wat de term is, wie in de organisatie een expert is op een bepaald gebied, en mogelijk aan de term gerelateerde sites en documenten.

In Viva Topics wordt AI gebruikt om automatisch te zoeken naar *onderwerpen* in je organisatie. Het stelt informatie samen over hen, zoals een korte beschrijving, personen die aan het onderwerp en sites en bestanden werken, en pagina's die aan het onderwerp zijn gerelateerd. Een kennismanager of medewerker kan ervoor kiezen om de onderwerpgegevens zo nodig bij te werken. De onderwerpen zijn beschikbaar voor je gebruikers. Dit betekent dat de tekst wordt gemarkeerd voor elk exemplaar van het onderwerp dat op een moderne SharePoint-site in nieuws en op pagina's wordt weergegeven. Gebruikers kunnen ervoor kiezen om het onderwerp te selecteren om hierover meer te weten te komen via de onderwerpdetails. Topics vind je ook in SharePoint Search.

## <a name="how-topics-are-displayed-to-users"></a>Hoe onderwerpen worden weergegeven aan gebruikers

Onderwerpen worden weergegeven voor gebruikers via:

- [Belangrijke onderwerpen](topic-experiences-overview.md#topic-highlights) op SharePoint pagina's
- Antwoorden over onderwerpen in [zoekresultaten](topic-experiences-overview.md#search-results)
- Zoeken in [office-toepassingen](topic-experiences-overview.md#office-application-search)
- [Startpagina onderwerpcentrum](topic-experiences-overview.md#topic-center)

### <a name="topic-highlights"></a>Belangrijke kenmerken van Topics

Wanneer een onderwerp wordt genoemd in nieuws en SharePoint-pagina's, dan wordt dit gemarkeerd. Je kunt het onderwerpoverzicht openen vanuit de markering. Open de onderwerpdetails in de titel van de samenvatting om de volledige onderwerppagina te bekijken. Het genoemde onderwerp kan automatisch worden geïdentificeerd of kan zijn toegevoegd aan de pagina met een directe verwijzing naar het onderwerp door de paginaauteur. 

   ![Schermafbeelding met de highlights van het onderwerp.](../media/knowledge-management/saturn.png) 

### <a name="search-results"></a>Zoekresultaten

U kunt een onderwerpantwoord [zien](search.md#topic-answer) in zoekresultaten wanneer u zoekt vanaf de startpagina van SharePoint, op Office.com zoekt of op een SharePoint-site zoekt nadat u het zoekbereik hebt gewijzigd om de volledige organisatie op te nemen. Het antwoord op het onderwerp wordt weergegeven op het onderwerp van de lijst met resultaten en geeft u een korte reeks informatie over dat onderwerp. 

   ![Schermafbeelding van de zoekresultaten van een SharePoint site zoeken.](../media/knowledge-management/site-search-results.png) 

### <a name="office-application-search"></a>Office zoeken in toepassingen

Wanneer u Zoeken gebruikt in Office-apps, zoals Word, PowerPoint, Outlook of Excel, via het zoekvak of door Zoeken **te** selecteren in het contextmenu, worden onderwerp antwoorden weergegeven in de zoekresultaten.

   ![Schermafbeelding van zoeken in Word via het vak Zoeken.](../media/knowledge-management/word-search-2.png)

   ![Schermafbeelding van zoeken in Word via het contextmenu Zoeken.](../media/knowledge-management/word-search-1.png)

### <a name="topic-center"></a>Onderwerpcentrum

Gebruikers kunnen onderwerpen in hun organisatie zien waarmee ze verbinding hebben op de startpagina [van het onderwerpcentrum.](topic-center-overview.md#home-page)

## <a name="knowledge-indexing"></a>Kennisindexering

Viva Topics gebruikt Microsoft AI-technologie om *onderwerpen* te identificeren in je Microsoft 365-omgeving.

Een onderwerp is een woordgroep of term die belangrijk is in de organisatie. Het heeft een specifieke betekenis voor de organisatie met hieraan gerelateerde bronnen zodat mensen kunnen begrijpen wat het is en hier meer informatie over kunnen vinden. Er is een groot aantal verschillende soorten onderwerpen dat belangrijk is voor je organisatie. In eerste instantie richt de Microsoft AI-technologie zich op de volgende typen:

- Project
- Gebeurtenis
- Organisatie
- Locatie
- Product
- Creatief werk
- Onderzoeksgebied

Wanneer een onderwerp wordt geïdentificeerd en AI bepaalt dat het voldoende informatie heeft om een voorgesteld onderwerp te kunnen zijn, dan geeft een *onderwerppagina* de informatie weer die is verzameld door onderwerpindexering, zoals:

- Alternatieve namen en acroniemen.
- Een korte beschrijving van het onderwerp.
- Personen die mogelijk wat van het onderwerp afweten.
- Bestanden, pagina's en sites die aan het onderwerp zijn gerelateerd.

Je kennisbeheerders kunnen ervoor kiezen om alle SharePoint-sites in je tenant te verkennen voor onderwerpen, of om alleen bepaalde sites te selecteren.

Zie Onderwerpdetectie en [curatie voor meer informatie.](./topic-experiences-discovery-curation.md)

## <a name="roles"></a>Rollen

Als je Viva Topics gebruikt in je Microsoft 365-omgeving, dan hebben je gebruikers de volgende rollen:

- Onderwerpgebruikers: gebruikers die de belangrijkste onderwerpen op moderne SharePoint-sites kunnen zien en hier ten minste *leestoegang* toe hebben, en in Microsoft Search. Ze kunnen de belangrijkste onderwerpen selecteren om de onderwerpdetails weer te geven op de onderwerppagina's. Gebruikers van onderwerpen kunnen feedback geven over hoe nuttig een onderwerp voor hen is.

- Inzenders: gebruikers die recht hebben op het bewerken of maken van nieuwe onderwerpen. Kennisbeheerders wijzen inzendermachtigingen toe aan gebruikers via Viva Topics-instellingen in het Microsoft 365-beheercentrum. Je kunt er ook voor kiezen om alle personen die onderwerpen bekijken toestemming te geven om onderwerpen te bewerken en te maken, zodat iedereen kan bijdragen aan onderwerpen die ze zien.

- Kennisbeheerders: gebruikers die onderwerpen door de levenscyclus van onderwerpen leiden. Kennisbeheerders gebruiken  de pagina Onderwerpen beheren in het onderwerpcentrum om ai-voorgestelde onderwerpen te bevestigen, onderwerpen te verwijderen die niet meer relevant zijn, bestaande onderwerpen te bewerken of nieuwe onderwerpen te maken en zijn de enige gebruikers die er toegang toe hebben. Kennisbeheerders wijzen kennisbeheerders toe aan gebruikers via Viva Topics-beheerinstellingen in het Microsoft 365-beheercentrum. 

- Kennisbeheerders: beheerders stellen Viva-onderwerpen in en beheren deze via de beheerbesturingselementen in het Microsoft 365 beheercentrum. Op dit moment kan een globale beheerder of SharePoint-beheerder van Microsoft 365 fungeren als een kennisbeheerder.

Zie De rollen [van Viva-onderwerpen voor meer informatie.](topic-experiences-roles.md)

## <a name="topic-management"></a>Onderwerpbeheer

Onderwerpbeheer wordt uitgevoerd op **de pagina Onderwerpen beheren** in het onderwerpcentrum van uw *organisatie.* Het onderwerpcentrum wordt gemaakt tijdens de installatie en fungeert als uw kenniscentrum voor uw organisatie. 

Hoewel alle gelicentieerde gebruikers onderwerpen kunnen zien met wie  ze verbonden zijn in het onderwerpcentrum, kunnen alleen gebruikers met machtigingen voor onderwerpen beheren (kennisbeheerders) de pagina Onderwerpen **beheren** bekijken en gebruiken.

Kennisbeheerders kunnen:

- Onderwerpen bevestigen of verwijderen die zijn ontdekt in uw tenant.
- Indien nodig nieuwe onderwerpen maken (als er bijvoorbeeld onvoldoende informatie beschikbaar is om deze via AI te vinden).
- Bestaande onderwerppagina's bewerken.

Zie Onderwerpen beheren [in het onderwerpcentrum voor meer informatie.](manage-topics.md)  

## <a name="admin-controls"></a>Beheerdersinstellingen

Met beheerbesturingselementen in Microsoft 365 beheercentrum kunt u Viva-onderwerpen beheren. Hiermee kan een globale beheerder of SharePoint-beheerder van Microsoft 365 het volgende doen:

- Bepalen welke gebruikers in uw organisatie onderwerpen mogen zien op moderne SharePoint-pagina's of in zoekresultaten van SharePoint.
- Bepalen welke SharePoint-sites worden verkend om onderwerpen te identificeren.
- Uitsluiten dat bepaalde onderwerpen niet worden gevonden.
- Bepalen welke gebruikers onderwerpen in het onderwerpcentrum kunnen beheren.
- Bepalen welke gebruikers onderwerpen kunnen maken en bewerken.
- Bepalen welke gebruikers onderwerpen kunnen bekijken.

Zie Gebruikersmachtigingen [toewijzen,](./plan-topic-experiences.md#user-permissions)onderwerpzichtbaarheid [](./topic-experiences-knowledge-rules.md)beheren en onderwerpdetectie beheren voor meer [informatie over beheerbesturingselementen.](./topic-experiences-discovery.md)

## <a name="topic-curation--feedback"></a>Bewaren van onderwerpen en feedback

AI zal voortdurend blijven werken om jouw suggesties voor onderwerpen te verbeteren naarmate uw omgeving verandert. 

Gebruikers met machtigingen voor bewerken of het maken van onderwerpen kunnen onderwerppagina's rechtstreeks bewerken als ze correcties willen maken of aanvullende informatie willen toevoegen. Ze kunnen ook nieuwe onderwerpen toevoegen die AI niet heeft kunnen identificeren. Als er voldoende informatie over deze handmatig toegevoegde onderwerpen is en AI dit type onderwerp kan identificeren, kunnen aanvullende suggesties van AI deze handmatig toegevoegde onderwerpen verbeteren.

Gebruikers die je toegang geeft tot onderwerpen tijdens hun dagelijkse werkzaamheden, kunnen worden gevraagd of het onderwerp nuttig voor hen is. Het systeem bekijkt deze reacties en gebruikt het om de markering van onderwerpen te verbeteren, en helpt om te bepalen wat er wordt weergegeven over onderwerpsamenvattingen en in informatie over onderwerpen.

Daarnaast kunnen gebruikers met de juiste machtigingen items labelen, zoals een Yammer-gesprek dat relevant is voor een onderwerp, en ze toevoegen aan een specifiek onderwerp. 

Zie Onderwerpdetectie en [curatie voor meer informatie.](./topic-experiences-discovery-curation.md)

## <a name="see-also"></a>Zie ook

[Microsoft Search gebruiken om onderwerpen te zoeken in Viva-onderwerpen](./search.md)