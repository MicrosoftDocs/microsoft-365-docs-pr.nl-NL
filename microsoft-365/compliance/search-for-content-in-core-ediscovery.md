---
title: Zoeken naar inhoud in een hoofd-eDiscovery-zaak
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Zoek naar inhoud die relevant kan zijn voor een core eDiscovery-zaak.
ms.openlocfilehash: 8d2e2a20135312a8f111a071abbe77b03b8e8363
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311773"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>Zoeken naar inhoud in een hoofd-eDiscovery-zaak

Nadat een core eDiscovery-zaak is gemaakt en personen die geïnteresseerd zijn in de zaak in de wacht worden geplaatst, kunt u een of meer zoekopdrachten maken en uitvoeren naar inhoud die relevant is voor de zaak. Zoekopdrachten die zijn gekoppeld aan een core eDiscovery-zaak, worden niet weergegeven op de pagina Inhoud zoeken in het Microsoft 365 compliancecentrum.  Deze zoekopdrachten worden weergegeven op de pagina **Zoekopdrachten** van het hoofd-eDiscover-geval waar de zoekopdrachten aan zijn gekoppeld. Dit betekent ook dat zoekopdrachten die aan een zaak zijn gekoppeld, alleen toegankelijk zijn voor caseleden.

Een core eDiscovery-zoekopdracht maken:
  
1. Ga naar en meld u aan met de referenties voor gebruikersaccount die zijn toegewezen aan de juiste eDiscovery-machtigingen en die lid <https://compliance.microsoft.com> zijn van de zaak.

2. Klik in het linkernavigatiedeelvenster van Microsoft 365 compliancecentrum op Alles weergeven **en** klik vervolgens op **eDiscovery > Core.**

3. Selecteer op **de pagina Core eDiscovery** de case die u wilt maken en klik vervolgens op **Hoofd zaak openen.**

4. Klik op **de startpagina** voor de zaak op **het tabblad** Zoekopdrachten en klik vervolgens op **Nieuwe zoekopdracht.**

   ![Klik op Nieuw zoeken om een zoekopdracht in Core eDiscovery te maken](../media/CoreeDiscoverySearch1.png)

   > [!NOTE]
   > Met de optie Zoeken op **id-lijst** kunt u zoeken naar specifieke e-mailberichten en andere postvakitems met een lijst met Exchange id's. Als u een zoekopdracht naar een id-lijst wilt maken, dient u een CSV-bestand (door komma's gescheiden waarde) in dat de specifieke postvakitems identificeert die moeten worden gezocht. Zie Een [CSV-bestand voorbereiden voor een id-lijst zoeken](csv-file-for-an-id-list-content-search.md)voor instructies.

5. Typ in **de wizard** Nieuw zoeken een naam voor de zoekopdracht en een optionele beschrijving waarmee u de zoekopdracht kunt identificeren. De naam van de zoekopdracht moet uniek zijn in uw organisatie.

6. Kies op **de** pagina Locaties de inhoudslocaties die u wilt zoeken. U kunt zoeken in postvakken, sites en openbare mappen.

    ![De inhoudslocaties kiezen die u in de wacht wilt zetten](../media/ContentSearchLocations.png)
  
   1. **Exchange postvakken:** Stel de schakelknop in op **Aan** en klik vervolgens op **Gebruikers,** groepen of teams kiezen om op te geven welke postvakken in de wacht moeten worden gezet. Gebruik het zoekvak om gebruikerspostvakken en distributiegroepen te zoeken (om de postvakken van groepsleden in de wacht te zetten) om deze in de wacht te zetten. U kunt ook zoeken in het postvak dat is gekoppeld aan een Microsoft-team (voor kanaalberichten), Office 365 Groep en Yammer Groep. Zie Inhoud die is opgeslagen in postvakken voor [eDiscovery](what-is-stored-in-exo-mailbox.md)voor meer informatie over de toepassingsgegevens die zijn opgeslagen in postvakken.

   2. **SharePoint sites:** Stel de schakelknop in op **Aan** en klik vervolgens op Sites **kiezen** om op te geven SharePoint sites en OneDrive accounts in de wacht te zetten. Typ de URL voor elke site die u in de wacht wilt zetten. U kunt ook de URL voor de SharePoint toevoegen voor een Microsoft-team, Office 365 groep of Yammer Groep.
  
   3. **Exchange openbare mappen:** Stel de schakelknop in op **Aan** om alle openbare mappen in uw Exchange Online in de wacht te zetten. U kunt geen specifieke openbare mappen kiezen om in de wacht te zetten. Schakel de wisselknop uit als u openbare mappen niet in de wacht wilt zetten.
  
   4. Houd dit selectievakje ingeschakeld om te zoeken naar Teams inhoud voor on-premises gebruikers. Als u bijvoorbeeld alle Exchange-postvakken in de organisatie doorzoekt en dit selectievakje is geselecteerd, wordt de cloudopslag die wordt gebruikt voor het opslaan van Teams-chatgegevens voor on-premises gebruikers, opgenomen in het bereik van de zoekopdracht. Zie Zoeken naar Teams [chatgegevens voor on-premises gebruikers](search-cloud-based-mailboxes-for-on-premises-users.md)voor meer informatie.

7. Typ op **de pagina Uw zoekvoorwaarden definiëren** een trefwoordquery en voeg zo nodig voorwaarden toe aan de zoekquery.

   ![De zoekquery configureren](../media/ContentSearchQuery.png)

   1. Geef trefwoorden, berichteigenschappen op, zoals verzonden en ontvangen datums, of documenteigenschappen zoals bestandsnamen of de datum waarop een document voor het laatst is gewijzigd. U kunt complexere query's gebruiken met een Booleaanse operator, zoals **EN,** **OF,** **NIET** en **NEAR.** Als u het vak met trefwoorden leeg laat, wordt alle inhoud op de opgegeven inhoudslocaties opgenomen in de zoekresultaten. Zie [Keyword-query's en zoekvoorwaarden voor eDiscovery](keyword-queries-and-search-conditions.md)voor meer informatie.

   2. U kunt ook op het selectievakje **Trefwoordlijst tonen** klikken en in elke rij een trefwoord typen. Als u dit doet, worden de trefwoorden in elke rij verbonden door een logische operator **(c:s)** die in functionaliteit lijkt op de **operator OF** in de zoekquery die is gemaakt.

      Waarom de lijst met trefwoorden gebruiken? U kunt statistieken krijgen die laten zien hoeveel items overeenkomen met elk trefwoord. Op deze manier kunt u snel bepalen welke trefwoorden het meest (en het minst) effectief zijn. U kunt ook een trefwoordzin (tussen haakjes) in een rij gebruiken. Zie Trefwoordstatistieken voor zoekopdrachten voor meer informatie over de lijst met trefwoorden en [zoekstatistieken.](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)

      > [!NOTE]
      > Als u problemen wilt beperken die worden veroorzaakt door grote lijsten met trefwoorden, bent u beperkt tot maximaal 20 rijen in de lijst met trefwoorden.

   3. U kunt zoekvoorwaarden toevoegen om een zoekopdracht te verfijnen en een meer verfijnde set resultaten te retourneren. Elke voorwaarde voegt een component toe aan de zoekquery die wordt gemaakt en uitgevoerd wanneer u de zoekopdracht start. Een voorwaarde is logisch verbonden met de trefwoordquery (opgegeven in het trefwoordvak) door een logische operator **(c:c)** die in functionaliteit vergelijkbaar is met de **operator AND.** Dit betekent dat items moeten voldoen aan zowel de trefwoordquery als een of meer voorwaarden om in de resultaten te worden opgenomen. Dit is de manier waarop voorwaarden helpen om uw resultaten te beperken. Zie Zoekvoorwaarden voor een lijst en beschrijving van voorwaarden die u kunt gebruiken in [een zoekquery.](keyword-queries-and-search-conditions.md#search-conditions)

8. Controleer de zoekinstellingen (en bewerk indien nodig) en verzend de zoekopdracht om deze te starten.

Nadat de zoekopdracht is voltooid, kunt u een voorbeeld van de zoekresultaten bekijken. Klik indien nodig op **Vernieuwen** op **de pagina Zoekopdrachten** om de zoekopdracht weer te geven die u hebt gemaakt.

## <a name="more-information-about-searching-content-locations"></a>Meer informatie over het zoeken naar inhoudslocaties

- Wanneer u op **Gebruikers, groepen** of teams kiezen klikt om postvakken op te geven die u wilt zoeken, is de postvakvertaler die wordt weergegeven leeg. Dit is een ontwerp om de prestaties te verbeteren. Als u geadresseerden aan deze lijst wilt toevoegen, klikt u op **Gebruikers,** groepen of teams kiezen, typt u een naam (minimaal drie tekens) in het zoekvak, selecteert u het selectievakje naast de naam en klikt u op **Kiezen**.

- U kunt inactieve postvakken, Microsoft Teams, Yammer Groepen, Office 365 Groepen en distributiegroepen toevoegen aan de lijst met postvakken die u wilt zoeken. Dynamische distributiegroepen worden niet ondersteund. Als u Microsoft Teams, Yammer groepen of groepen Office 365, wordt het groeps- of teampostvak doorzocht. de postvakken van de groepsleden worden niet doorzocht.

- Als u sites wilt toevoegen aan de zoekopdracht, schakelt u de schakelknop in en klikt u vervolgens **op Sites kiezen.** Typ de URL voor elke site die u wilt zoeken. U kunt ook de URL toevoegen voor de SharePoint voor een Microsoft-team, een Yammer groep of een Office 365 Groep.
