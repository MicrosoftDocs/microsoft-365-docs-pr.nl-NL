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
   > Met de optie **Zoeken op lijst-id** kunt u zoeken naar specifieke e-mailberichten en andere postvakitems met behulp van een lijst met Exchange-id's. Als u een zoekopdracht voor een lijst met id's wilt maken, dient u een bestand met door komma's gescheiden waarden (CSV) in dat de specifieke postvakitems identificeert waar u naar wilt zoeken. Zie [Een CSV-bestand voorbereiden voor het zoeken naar een lijst met id's](csv-file-for-an-id-list-content-search.md) voor instructies.

5. Typ in **de wizard** Nieuw zoeken een naam voor de zoekopdracht en een optionele beschrijving waarmee u de zoekopdracht kunt identificeren. De naam van de zoekopdracht moet uniek zijn in uw organisatie.

6. Kies op de pagina **Locaties** de inhoud die u wilt doorzoeken. U kunt zoeken in postvakken, sites en openbare mappen.

    ![Kies de inhoudslocaties die u vast wilt zetten](../media/ContentSearchLocations.png)
  
   1. **Exchange-postvakken**: Stel de wisselknop in op **Aan** en klik vervolgens op **Kies gebruikers, groepen of teams** om de postvakken op te geven die u vast wilt zetten. Gebruik het zoekvak om gebruikerspostvakken en distributiegroepen te zoeken (om de postvakken van groepsleden vast te zetten) die u vast wilt zetten. U kunt ook zoeken in het postvak dat is gekoppeld aan een Microsoft Team (voor kanaalberichten), Office 365-groep en Yammer-groep. Zie voor meer informatie over de toepassingsgegevens die zijn opgeslagen in postvakken [Inhoud die is opgeslagen in postvakken voor eDiscovery](what-is-stored-in-exo-mailbox.md).

   2. **SharePoint-sites**: Stel de wisselknop in op **Aan** en klik vervolgens op **Sites kiezen** om SharePoint-sites en OneDrive-accounts op te geven die u vast wilt zetten. Typ de URL voor elke site die u vast wilt zetten. U kunt ook de URL toevoegen voor de SharePoint-site voor een Microsoft Team, Office 365-groep of Yammer-groep.
  
   3. **Openbare Mappen in Exchange**: Stel de wisselknop in op **Aan** om alle openbare mappen in uw Exchange Online-organisatie vast te zetten. U kunt geen specifieke openbare mappen kiezen die u vast wilt zetten. Zet de wisselknop uit als u geen openbare mappen vast wilt zetten.
  
   4. Laat dit selectievakje ingeschakeld als u wilt zoeken naar inhoud van Teams voor on-premises gebruikers. Als u bijvoorbeeld alle Exchange-postvakken in de organisatie doorzoekt en ook dit selectievakje inschakelt, wordt cloud-opslag voor het opslaan van chatgegevens van Teams voor on-premises gebruikers opgenomen in het bereik van de zoekopdracht. Zie [Zoeken naar chatgegevens van Teams voor on-premises gebruikers](search-cloud-based-mailboxes-for-on-premises-users.md) voor meer informatie.

7. Typ op de pagina **Uw zoekvoorwaarden definiëren** een trefwoordquery en voeg zo nodig voorwaarden aan de zoekquery toe.

   ![De zoekquery configureren](../media/ContentSearchQuery.png)

   1. Specificeer trefwoorden, berichteigenschappen (zoals verzend- en ontvangstdatums) of documenteigenschappen (zoals bestandsnamen of de datum waarop een document voor het laatst is gewijzigd). U kunt complexere query's gebruiken die gebruikmaken van een booleaanse operator, zoals **AND**, **OR**, **NOT** en **NEAR**. Als u het vak met trefwoorden leeg laat, wordt alle inhoud op de opgegeven inhoudslocaties opgenomen in de zoekresultaten. Zie [Trefwoordquery's en zoekvoorwaarden voor eDiscovery](keyword-queries-and-search-conditions.md) voor meer informatie.

   2. U kunt ook het selectievakje **Lijst met zoekwoorden weergeven** selecteren en in elke rij een trefwoord typen. Als u dit doet, worden de trefwoorden in elke rij gekoppeld aan een logische operator (**c:s**) die qua functie vergelijkbaar is met de operator **OR** in de zoekquery die wordt gemaakt.

      Waarom wordt de lijst met trefwoorden gebruikt? U kunt statistieken krijgen die laten zien hoeveel items overeenkomen met elk trefwoord. Zo kunt u snel bepalen welke trefwoorden het meest (en minst) effectief zijn. U kunt ook een trefwoordzin (tussen haakjes) gebruiken in een rij. Zie [Trefwoordstatistieken weergeven voor zoekopdrachten](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches) voor meer informatie over de trefwoordlijst en zoekstatistieken.

      > [!NOTE]
      > Eventuele problemen die worden veroorzaakt door grote trefwoordlijsten, worden verminderd door het aantal rijen in de lijst met trefwoorden tot twintig te beperken.

   3. U kunt zoekvoorwaarden toevoegen om een zoekopdracht te verfijnen en een kleiner aantal resultaten te retourneren. Elke voorwaarde verbindt een clausule aan de zoekquery die wordt gemaakt. Deze wordt uitgevoerd wanneer u de zoekopdracht start. Een voorwaarde is logisch gekoppeld aan de trefwoordquery (aangegeven in het trefwoordvak) door middel van een logische operator (**c:c**). Deze is vergelijkbaar met de operator **AND**. Dit betekent dat items moeten voldoen aan zowel de trefwoordquery als een of meer voorwaarden die in de resultaten moeten worden opgenomen. Op die manier kunt u door middel van voorwaarden de resultaten beperken. Zie voor een lijst en beschrijving van voorwaarden die u in een zoekquery kunt gebruiken [Zoekvoorwaarden](keyword-queries-and-search-conditions.md#search-conditions).

8. Controleer de zoekinstellingen (en bewerk deze indien nodig) en verzend de zoekopdracht vervolgens om deze te starten.

Nadat de zoekopdracht is voltooid, kunt u een voorbeeld van de zoekresultaten bekijken. Klik indien nodig op **Vernieuwen** op **de pagina Zoekopdrachten** om de zoekopdracht weer te geven die u hebt gemaakt.

## <a name="more-information-about-searching-content-locations"></a>Meer informatie over het zoeken naar inhoudslocaties

- Wanneer u op **Gebruikers, groepen** of teams kiezen klikt om postvakken op te geven die u wilt zoeken, is de postvakvertaler die wordt weergegeven leeg. Dit is een ontwerp om de prestaties te verbeteren. Als u geadresseerden aan deze lijst wilt toevoegen, klikt u op **Gebruikers,** groepen of teams kiezen, typt u een naam (minimaal drie tekens) in het zoekvak, selecteert u het selectievakje naast de naam en klikt u op **Kiezen**.

- U kunt inactieve postvakken, Microsoft Teams, Yammer Groepen, Office 365 Groepen en distributiegroepen toevoegen aan de lijst met postvakken die u wilt zoeken. Dynamische distributiegroepen worden niet ondersteund. Als u Microsoft Teams, Yammer groepen of groepen Office 365, wordt het groeps- of teampostvak doorzocht. de postvakken van de groepsleden worden niet doorzocht.

- Als u sites wilt toevoegen aan de zoekopdracht, schakelt u de schakelknop in en klikt u vervolgens **op Sites kiezen.** Typ de URL voor elke site die u wilt zoeken. U kunt ook de URL toevoegen voor de SharePoint voor een Microsoft-team, een Yammer groep of een Office 365 Groep.
