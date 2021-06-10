---
title: Controleactiviteit voor beheerders weergeven
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Gebruik het hulpprogramma Advanced eDiscovery bewaarderbeheer om eenvoudig toegang te krijgen tot de activiteit en te zoeken naar bewaarders in uw zaak.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9e96d0b5dd3bf42dbba56a6e1be91014485ce98
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2020
ms.locfileid: "52161481"
---
# <a name="view-custodian-audit-activity"></a>Controleactiviteit voor beheerders weergeven

Wilt u weten of een gebruiker een bepaald document heeft bekeken of een item uit zijn of haar postvak heeft verwijderd? Advanced eDiscovery is nu geïntegreerd met het bestaande zoekprogramma voor auditlogboek in & Compliancecentrum. Met deze ingesloten ervaring kunt u het hulpprogramma Advanced eDiscovery bewaarderbeheer gebruiken om uw onderzoek te vergemakkelijken door eenvoudig toegang te krijgen tot de activiteit en te zoeken naar beheerders in uw zaak.

## <a name="get-permissions"></a>Machtigingen krijgen

Als u auditlogboeken wilt doorzoeken, moet aan u de rol Auditlogboeken alleen-weergeven of Auditlogboeken in Exchange Online zijn toegewezen. Deze rollen worden standaard toegewezen aan de rollengroepen Compliancebeheer en Organisatiebeheer op de pagina Machtigingen in het Exchange-beheercentrum. Als u een gebruiker de mogelijkheid wilt geven om het Advanced eDiscovery-auditlogboek te doorzoeken met het minimumniveau van bevoegdheden, kunt u een aangepaste rollengroep maken in Exchange Online, de rol View-Only Auditlogboeken of Auditlogboeken toevoegen en vervolgens de gebruiker toevoegen als lid van de nieuwe rollengroep. Zie voor meer informatie Rollengroepen beheren in Exchange Online.

> [!IMPORTANT]
> Als u een gebruiker de rol View-Only auditlogboeken of auditlogboeken toewijst op de pagina Machtigingen in het beveiligings- & compliancecentrum, kunnen ze niet in het auditlogboek zoeken. U moet deze machtigingen toewijzen in Exchange Online. Dat komt omdat de onderliggende cmdlet voor het doorzoeken van het auditlogboek een Exchange Online-cmdlet is.

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a>Stap 1: het auditlogboek doorzoeken op activiteiten die door een bewaarder worden uitgevoerd

1. Ga naar **eDiscovery > Advanced eDiscovery** en open de zaak.
  
2. Klik op **het tabblad** Bronnen.
  
3. Selecteer op **de pagina Bewaarders** een bewaarder in de lijst en klik vervolgens op **Bewaaractiviteiten weergeven** op de flyoutpagina.

    De zoekpagina Bewaaractiviteiten wordt weergegeven. Houd er rekening mee dat de bewaarder die u in de vorige stap hebt geselecteerd, wordt weergegeven in het vervolgkeuzevak **Bewaarder.** U kunt verschillende beheerders selecteren in de vervolgkeuzebus, maar u kunt alleen zoeken naar activiteiten voor één bewaarder tegelijk.

    ![Zoekpagina voor beheerdersactiviteiten](../media/AeDCustodianActivities1.png)
   
4. Configureer de volgende zoekcriteria: 
      
   1. **Activiteiten:** klik op de vervolgkeuzelijst om de activiteiten weer te geven die u kunt zoeken. Nadat u de zoekopdracht hebt uitgevoerd, worden alleen de auditrecords voor de geselecteerde activiteiten weergegeven. Als **u Resultaten weergeven voor alle activiteiten selecteert,** worden resultaten weergegeven voor alle activiteiten die worden uitgevoerd door de bewaarder die voldoen aan de andere zoekcriteria.

      ![Lijst met activiteiten](../media/CustodianActivityAudit.PNG)
      
   1. **Begindatum en einddatum:** selecteer een datum en tijdbereik om de gebeurtenissen weer te geven die binnen die periode hebben plaatsgevonden. De laatste zeven dagen zijn standaard geselecteerd. De datum en tijd worden weergegeven in de UTC-indeling (Coordinated Universal Time). Het maximumdatumbereik dat u kunt opgeven, is één jaar.
      
   1. **Bewaarders:** klik in dit vak en selecteer vervolgens een specifieke bewaarder om zoekresultaten weer te geven. Auditrecords voor de geselecteerde activiteit die wordt uitgevoerd door de gebruikers die u in dit vak selecteert, worden weergegeven in de lijst met resultaten.
      
5. Klik op ![Knop Zoeken](../media/SearchButton.PNG)  om de zoekopdracht uit te voeren met behulp van uw zoekcriteria. De zoekresultaten worden geladen en na enkele ogenblikken worden ze weergegeven onder Resultaten op de zoekpagina Bewaaractiviteiten. 

## <a name="step-2-view-the-audit-log-search-results"></a>Stap 2: De zoekresultaten van het auditlogboek weergeven

De resultaten van een zoekopdracht in een auditlogboek worden weergegeven onder Resultaten op de pagina Bewaarcontrolelogboek. Maximaal 5.000 (nieuwste) gebeurtenissen worden weergegeven in stappen van 150 gebeurtenissen. Om meer gebeurtenissen weer te geven, kunt u de schuifbalk in het deelvenster Resultaten gebruiken of u kunt op Shift + End drukken om de volgende 150 gebeurtenissen weer te geven.

De resultaten bevatten de volgende informatie over elke gebeurtenis die door de zoekopdracht wordt geretourneerd.
- **Datum:** De datum en tijd (in UTC-indeling) wanneer de gebeurtenis heeft plaatsgevonden.

- **IP-adres**: het IP-adres van het apparaat dat is gebruikt toen de activiteit in het logboek werd vastgelegd. Het IP-adres wordt weergegeven in een IPv4- of IPv6-adresindeling.

- **Gebruiker**: de gebruiker (of serviceaccount) die de actie heeft uitgevoerd die de gebeurtenis heeft veroorzaakt.

- **Activiteit**: de activiteit die door de gebruiker is uitgevoerd. Deze waarde komt overeen met de activiteiten die u hebt geselecteerd in de vervolgkeuzelijst Activiteiten. Voor een gebeurtenis uit het auditlogboek voor Exchange-beheerders is de waarde in deze kolom een Exchange-cmdlet.

- **Item**: het object dat is gemaakt of gewijzigd als gevolg van de bijbehorende activiteit. Bijvoorbeeld het bestand dat is bekeken of gewijzigd of het gebruikersaccount dat is bijgewerkt. Niet alle activiteiten hebben een waarde in deze kolom.

- **Detail:** Meer informatie over een activiteit. Nogmaals, niet alle activiteiten hebben een waarde.

## <a name="step-3-filter-the-search-results"></a>Stap 3: de zoekresultaten filteren

Behalve sorteren kunt u de resultaten van een zoekopdracht in het auditlogboek ook filteren. Dit kan u helpen om snel de resultaten te filteren voor een specifieke gebruiker of activiteit. 

U filtert de resultaten als volgt:

 1. Een auditlogboek zoeken maken en uitvoeren.
  
2. Klik op **Resultaten filteren** wanneer de resultaten worden weergegeven.
 
3. Onder elke kolomkop wordt een vak met trefwoorden weergegeven.
  
4. Klik op een van de vakken onder een kolomkop en typ een woord of zinsdeel, afhankelijk van de kolom die u filtert. De resultaten worden dynamisch aangepast en de gebeurtenissen die met het filter overeenkomen, worden weergegeven.
  
5. Als u een filter wilt verwijderen, klikt u op **de X** in het filtervak of klikt u op **Filteren verbergen.**

## <a name="export-the-search-results-to-a-file"></a>De zoekresultaten exporteren naar een bestand

U kunt de resultaten van een zoekopdracht in een auditlogboek exporteren naar een door komma's gescheiden waardebestand (CSV) op uw lokale computer. U kunt dit bestand openen in Microsoft Excel en functies gebruiken zoals zoeken, sorteren, filteren en splitsen van één kolom (die cellen met meerdere waarden bevat) in meerdere kolommen.

1. Voer een zoekopdracht in een auditlogboek uit en pas de zoekcriteria aan tot u de gewenste resultaten hebt.
  
2. Klik op Resultaten exporteren en selecteer een van de volgende opties:

    - **Geladen resultaten opslaan:** Kies deze optie om alleen de items te exporteren die worden weergegeven onder **Resultaten** op de zoekpagina van het logboek **van de bewaardercontrole.** Het CSV-bestand dat wordt gedownload bevat dezelfde kolommen (en gegevens) die worden weergegeven op de pagina (Datum, Gebruiker, Activiteit, Item en Details). Er wordt een extra kolom (met de naam **Meer)** opgenomen in het CSV-bestand met meer informatie uit de vermelding van het auditlogboek. Omdat u dezelfde resultaten exporteert die zijn geladen (en kunnen worden weergegeven) op de pagina Zoeken in auditlogboek, worden er maximaal 5000 vermeldingen geëxporteerd.
        
    - **Alle resultaten downloaden:** Kies deze optie om alle items uit het auditlogboek te exporteren die voldoen aan de zoekcriteria. Kies voor een grote set zoekresultaten deze optie om alle items uit het auditlogboek te downloaden, naast de 5.000 resultaten die kunnen worden weergegeven op de zoekpagina **Van** controlelogboek voor beheerders. Met deze optie worden de onbewerkte gegevens uit het auditlogboek gedownload naar een CSV-bestand en worden aanvullende gegevens uit de vermelding van het auditlogboek in een kolom met de naam AuditData toegevoegd. Het downloaden van het bestand kan langer duren als u deze exportoptie kiest, omdat het bestand veel groter kan zijn dan het bestand dat wordt gedownload als u de andere optie kiest.
    
      > [!IMPORTANT]
      > U kunt maximaal 50.000 vermeldingen (als gevolg van één zoekopdracht) in een CSV-bestand downloaden. Als er 50.000 resultaten in het CSV-bestand zijn gedownload, kunt u aannemen dat er meer dan 50.000 gebeurtenissen zijn die aan de zoekcriteria voldoen. Als u meer wilt exporteren, kunt u een datumbereik kiezen om het aantal vermeldingen in het auditlogboek te verminderen. Mogelijk moet u meerdere zoekopdrachten uitvoeren met kleinere datumbereiken als u meer dan 50.000 vermeldingen wilt exporteren.
        

3. Nadat u een exportoptie hebt geselecteerd, wordt onder aan het venster een bericht weergegeven waarin u wordt gevraagd het CSV-bestand te openen, op te slaan in de map Downloads of het op te slaan in een specifieke map

Zie Het auditlogboek doorzoeken in het Beveiligings- & Compliancecentrum voor meer informatie over het weergeven, filteren [of exporteren van de zoekresultaten van het auditlogboek.](search-the-audit-log-in-security-and-compliance.md)
