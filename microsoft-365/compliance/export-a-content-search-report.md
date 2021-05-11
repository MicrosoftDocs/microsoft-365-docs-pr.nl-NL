---
title: Een inhoudszoekrapport exporteren
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: In plaats van de werkelijke resultaten van een inhoudszoekactie te exporteren in & Compliancecentrum voor beveiliging in Office 365, kunt u een rapport met zoekresultaten exporteren. Het rapport bevat een overzicht van de zoekresultaten en een document met gedetailleerde informatie over elk item dat zou worden geëxporteerd.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311569"
---
# <a name="export-a-content-search-report"></a>Een inhoudszoekrapport exporteren

In plaats van de volledige reeks zoekresultaten te exporteren uit een inhoudszoekactie in het Microsoft 365 compliancecentrum (of uit een zoekopdracht die is gekoppeld aan een Core eDiscovery-zaak), kunt u dezelfde rapporten exporteren die worden gegenereerd wanneer u de werkelijke zoekresultaten exporteert.
  
Wanneer u een rapport exporteert, worden de rapportbestanden gedownload naar een map op uw lokale computer die dezelfde naam heeft als het zoeken naar inhoud, maar die wordt toegevoegd met *_ReportsOnly.* Als het zoeken naar inhoud bijvoorbeeld de naam *ContosoCase0815* heeft, wordt het rapport gedownload naar een map *met de naam ContosoCase0815_ReportsOnly.* Zie Wat is opgenomen in het rapport voor een lijst met documenten die in het rapport [zijn opgenomen.](#whats-included-in-the-report)

## <a name="before-you-export-a-search-report"></a>Voordat u een zoekrapport exporteert

- Als u een zoekrapport wilt exporteren, moet u de rol compliancezoekbeheer toegewezen krijgen in & Compliancecentrum. Deze rol wordt standaard toegewezen aan de ingebouwde rollengroepen eDiscovery Manager en Organisatiebeheer. Zie [eDiscovery-machtigingen](assign-ediscovery-permissions.md)toewijzen voor meer informatie.

- Wanneer u een rapport exporteert, worden de gegevens tijdelijk opgeslagen op Azure Storage locatie in de Microsoft-cloud voordat deze worden gedownload naar uw lokale computer. Zorg ervoor dat uw organisatie verbinding kan maken met het eindpunt in Azure, dat **\* .blob.core.windows.net** is (het jokerteken vertegenwoordigt een unieke id voor uw export). De zoekresultaten worden twee weken na het maken Azure Storage van de locatie verwijderd.

- De computer die u gebruikt om de zoekresultaten te exporteren, moet voldoen aan de volgende systeemvereisten:

  - Nieuwste versie van Windows (32-bits of 64-bits)

  - Microsoft .NET Framework 4.7

- U moet een van de volgende ondersteunde browsers gebruiken om het eDiscovery Export Tool 1 uit te<sup>voeren:</sup>

  - Microsoft Edge <sup>2</sup>

    OF

  - Microsoft Internet Explorer 10 en nieuwere versies

  > [!NOTE]
  > <sup>1</sup> Microsoft produceert geen extensies of invoegtoepassingen van derden voor ClickOnce toepassingen. Het exporteren van zoekresultaten met een niet-ondersteunde browser met extensies of invoegtoepassingen van derden wordt niet ondersteund.<br/>
  > <sup>2</sup> Als gevolg van recente wijzigingen in Microsoft Edge is ClickOnce standaard niet meer ingeschakeld. Zie Het [eDiscovery-exporthulpmiddel](configure-edge-to-export-search-results.md)gebruiken in Microsoft Edge voor instructies over het inschakelen van ClickOnce ondersteuning in Edge.

- Als de geschatte totale grootte van de resultaten die door zoeken worden geretourneerd groter is dan 2 TB, mislukt het exporteren van de rapporten. Als u de rapporten wilt exporteren, probeert u het bereik te beperken en de zoekopdracht opnieuw uit te voeren, zodat de geschatte grootte van de resultaten kleiner is dan 2 TB.

- Als de resultaten van een zoekopdracht ouder zijn dan 7 dagen en u een exportrapportfunctie indient, wordt er een foutbericht weergegeven waarin u wordt gevraagd de zoekopdracht opnieuw uit te voeren om de zoekresultaten bij te werken. Als dit gebeurt, annuleert u de export, heruitvoert u de zoekopdracht en start u de export opnieuw.

- Het exporteren van zoekrapporten telt mee voor het maximum aantal exporten dat tegelijkertijd wordt uitgevoerd en het maximum aantal exporten dat één gebruiker kan uitvoeren. Zie Zoekresultaten voor inhoud exporteren voor meer informatie over [exportlimieten.](export-search-results.md#export-limits)
  
## <a name="step-1-generate-the-report-for-export"></a>Stap 1: Het rapport genereren voor export

De eerste stap is het voorbereiden van het rapport voor het downloaden naar uw computer exporteren. Wanneer u het rapport exporteert, worden de rapportdocumenten geüpload naar een Azure Storage in de Microsoft-cloud.
  
1. Selecteer in Microsoft 365 compliancecentrum de inhoudszoekactie waaruit u het rapport wilt exporteren.
  
2. Klik in **het** menu Acties onder aan de flyoutpagina van de zoekactie op **Rapport exporteren.**

   ![Rapportoptie exporteren in het menu Acties](../media/ActionMenuExportReport.png)

   De **flyoutpagina** Rapport exporteren wordt weergegeven. De exportrapportopties die beschikbaar zijn om informatie over de zoekopdracht te exporteren, zijn afhankelijk van of zoekresultaten zich in postvakken of sites bevinden of een combinatie van beide.
  
3. Kies **onder Uitvoeropties** een van de volgende opties:
  
   ![Uitvoeropties exporteren](../media/ExportOutputOptions.png)

    - Alle items, met uitzondering van items met een niet-herkende notatie, worden versleuteld of zijn om andere redenen **niet geïndexeerd.** Deze optie exporteert alleen informatie over geïndexeerde items.
  
    - Alle items, inclusief items met een niet-herkende notatie, worden versleuteld of zijn om andere redenen **niet geïndexeerd.** Met deze optie exporteert u informatie over geïndexeerde en niet-geïndexeerde items.
  
    - **Alleen items met een niet-herkende notatie,** worden versleuteld of om andere redenen niet geïndexeerd. Met deze optie wordt alleen informatie over niet-geïndexeerde items geexporteerd.

4. Configureer **de optie Deplicatie inschakelen voor Exchange inhoud.**
  
   - Als u deze optie selecteert, wordt het aantal dubbele berichten (vóór de duplicatie en na de duplicatie) opgenomen in het overzichtsrapport exporteren. Er wordt ook slechts één kopie van een bericht opgenomen in het manifest.xml bestand. Het rapport Exportresultaten bevat echter een rij voor elke kopie van een duplicaatbericht, zodat u de postvakken kunt identificeren die een kopie van het dubbele bericht bevatten. Zie Wat is opgenomen in het rapport voor meer informatie over [de geëxporteerde rapporten.](#whats-included-in-the-report)

   - Als u deze optie niet selecteert, bevatten de exportrapporten informatie over alle berichten die door de zoekopdracht worden geretourneerd, inclusief duplicaten.

     Zie [De-duplicatie in eDiscovery-zoekresultaten](de-duplication-in-ediscovery-search-results.md)voor meer informatie over de-duplicatie en hoe dubbele items worden geïdentificeerd.

5. Klik **op Rapport genereren.**

   De zoekrapporten zijn voorbereid voor het downloaden, wat betekent dat de rapportdocumenten worden geüpload naar een Azure Storage locatie in de Microsoft-cloud. Dit kan enkele minuten duren.

Zie de volgende sectie voor instructies voor het downloaden van de geëxporteerde zoekrapporten.
  
## <a name="step-2-download-the-report"></a>Stap 2: Het rapport downloaden

De volgende stap is het downloaden van het rapport van het Azure Storage naar uw lokale computer.

1. Selecteer op **de pagina Inhoud** zoeken in het Microsoft 365 compliancecentrum het tabblad **Exporten**
  
   Mogelijk moet u op Vernieuwen klikken **om** de lijst met exporttaken bij te werken, zodat de exporttaken worden weergegeven die u hebt gemaakt. Rapporttaken exporteren hebben dezelfde naam als de bijbehorende zoekopdracht **_ReportsOnly** toegevoegd aan de zoeknaam.
  
2. Selecteer de exportklus die u hebt gemaakt in stap 1.

3. Klik op **de flyoutpagina** Rapport exporteren onder **Exportcode** op **Kopiëren naar klembord.** U gebruikt deze sleutel in stap 6 om de zoekresultaten te downloaden.
  
   > [!IMPORTANT]
   > Omdat iedereen het hulpprogramma eDiscovery Export kan installeren en starten en vervolgens deze sleutel kan gebruiken om het zoekrapport te downloaden, moet u voorzorgsmaatregelen nemen om deze sleutel te beveiligen, net zoals u wachtwoorden of andere beveiligingsgerelateerde informatie zou beveiligen.

4. Klik boven aan de flyoutpagina op **Resultaten downloaden.**

5. Als u wordt gevraagd het **eDiscovery-exportprogramma te installeren,** klikt u op **Installeren.**

6. Ga als volgt te werk in het **eDiscovery-exporthulpmiddel:**

   ![eDiscovery Export Tool](../media/eDiscoveryExportTool.png)

   1. Plak de exportcode die u hebt gekopieerd in stap 3 in het juiste vak.
  
   2. Klik **op Bladeren** om de locatie op te geven waar u de zoekrapportbestanden wilt downloaden.

7. Klik **op Start** om de zoekresultaten naar uw computer te downloaden.
  
    Het **eDiscovery-exporthulpmiddel** geeft statusgegevens weer over het exportproces, inclusief een schatting van het aantal (en de grootte) van de resterende items die moeten worden gedownload. Wanneer het exportproces is voltooid, hebt u toegang tot de bestanden op de locatie waar ze zijn gedownload.
  
## <a name="whats-included-in-the-report"></a>Wat is opgenomen in het rapport

Wanneer u een rapport genereert en exporteert over de resultaten van een zoekopdracht naar inhoud, worden de volgende documenten gedownload:
  
- **Exportoverzicht:** Een Excel document met een overzicht van de export. Dit omvat informatie, zoals het aantal inhoudsbronnen dat is doorzocht, het aantal zoekresultaten van elke inhoudslocatie, het geschatte aantal items, het werkelijke aantal items dat zou worden geëxporteerd en de geschatte en werkelijke grootte van items die zouden worden geëxporteerd.

   Als u niet-geïndexeerde items opgeeft bij het exporteren van het rapport, wordt het aantal niet-geïndexeerde items opgenomen in het totale aantal geschatte zoekresultaten en in het totale aantal gedownloade zoekresultaten (als u de zoekresultaten wilt exporteren) die worden weergegeven in het overzichtsrapport exporteren. Met andere woorden, het totale aantal items dat wordt gedownload, is gelijk aan het totale aantal geschatte resultaten en het totale aantal niet-geïndexeerde items.
  
- **Manifest:** Een manifestbestand (in XML-indeling) dat informatie bevat over elk item dat in de zoekresultaten wordt opgenomen. Als u de optie de-duplicatie hebt ingeschakeld, worden dubbele berichten niet opgenomen in het manifestbestand.

- **Resultaten:** Een Excel document met een rij met informatie over elk geïndexeerd item dat met de zoekresultaten zou worden geëxporteerd. Voor e-mail bevat het resultatenlogboek informatie over elk bericht, waaronder: 

  - De locatie van het bericht in het bronpostvak (inclusief of het bericht zich in het primaire of archiefpostvak bevindt).

  - De datum waarop het bericht is verzonden of ontvangen.

  - De onderwerpregel van het bericht.

  - De afzender en geadresseerden van het bericht.

  Voor documenten van SharePoint en OneDrive voor Bedrijven sites bevat het resultatenlogboek informatie over elk document, waaronder:

  - De URL voor het document.

  - De URL voor de siteverzameling waar het document zich bevindt.

  - De datum waarop het document voor het laatst is gewijzigd.

  - De naam van het document (dat zich in de kolom Onderwerp in het resultatenlogboek bevindt).

  > [!NOTE]
  > Het aantal rijen  in het rapport Resultaten moet gelijk zijn aan het totale aantal zoekresultaten minus het totale aantal items dat wordt weergegeven in het rapport **Niet-geïndexeerde** items.
  
- **Trace.log:** een tracelogboek dat gedetailleerde logboekgegevens over het exportproces bevat en u kunt helpen bij het opsporen van problemen tijdens het exporteren. Als u een ticket opent met Microsoft Support over een probleem met betrekking tot het exporteren van zoekrapporten, wordt u mogelijk gevraagd dit tracelogboek op te geven.

- **Niet-geïndexeerde items:** Een Excel document met informatie over niet-geïndexeerde items in de zoekresultaten. Als u geen niet-geïndexeerde items opgeeft wanneer u het rapport met zoekresultaten genereert, wordt dit rapport nog steeds gedownload, maar is het leeg.
