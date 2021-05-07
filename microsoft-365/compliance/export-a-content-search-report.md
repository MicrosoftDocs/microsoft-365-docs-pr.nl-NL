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
ms.openlocfilehash: fec6e441458ad7429067a1314a7aec3824aff11a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "52162589"
---
# <a name="export-a-content-search-report"></a>Een inhoudszoekrapport exporteren

In plaats van de volledige set zoekresultaten te exporteren uit een inhoudszoekactie in het Beveiligings- & Compliancecentrum (en vanuit een inhoudszoekactie die is gekoppeld aan een eDiscovery-zaak), kunt u dezelfde rapporten exporteren die worden gegenereerd wanneer u zoekresultaten exporteert.
  
Wanneer u een rapport exporteert, wordt het gedownload naar een map met dezelfde naam als het zoeken naar inhoud, maar die is toegevoegd aan *_ReportsOnly.* Als het zoeken naar inhoud bijvoorbeeld de naam *ContosoCase0815* heeft, wordt het rapport gedownload naar een map *met de naam ContosoCase0815_ReportsOnly.* Zie Wat is opgenomen in het rapport voor een lijst met documenten die in het rapport [zijn opgenomen.](#whats-included-in-the-report)

## <a name="assign-roles-and-check-system-requirements"></a>Rollen toewijzen en systeemvereisten controleren

- Als u een inhoudszoekrapport wilt exporteren, moet u de rol compliancezoekbeheer toegewezen krijgen in het beveiligings- & Compliancecentrum. Deze rol wordt standaard toegewezen aan de ingebouwde rollengroepen eDiscovery Manager en Organisatiebeheer. Zie [eDiscovery-machtigingen](assign-ediscovery-permissions.md)toewijzen voor meer informatie.

- Wanneer u een rapport exporteert, worden de gegevens tijdelijk opgeslagen in een uniek Azure Storage in de Microsoft-cloud voordat deze worden gedownload naar uw lokale computer. Zorg ervoor dat uw organisatie verbinding kan maken met het eindpunt in Azure, dat **\* .blob.core.windows.net** is (het jokerteken vertegenwoordigt een unieke id voor uw export). De zoekresultaten worden twee weken na het maken Azure Storage verwijderd uit het Azure Storage gebied.

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

- Als de geschatte totale grootte van de resultaten die worden geretourneerd door een inhoudszoekactie groter is dan 2 TB, mislukt het exporteren van het rapport. Als u het rapport wilt exporteren, probeert u het bereik te beperken en de zoekopdracht opnieuw uit te voeren, zodat de geschatte grootte van de resultaten kleiner is dan 2 TB.

- Het exporteren van inhoudszoekrapporten telt mee voor het maximum aantal exporten dat tegelijkertijd wordt uitgevoerd en het maximum aantal exporten dat één gebruiker kan uitvoeren. Zie Inhoudszoekresultaten exporteren voor meer informatie over [exportlimieten.](export-search-results.md#export-limits)

## <a name="generate-and-download-a-content-search-report"></a>Een inhoudszoekrapport genereren en downloaden

De stappen voor het genereren en downloaden van een inhoudszoekrapport zijn vergelijkbaar met het daadwerkelijk exporteren van zoekresultaten.
  
## <a name="step-1-generate-the-report-for-export"></a>Stap 1: Het rapport genereren voor export

De eerste stap is het voorbereiden van het rapport voor het downloaden naar uw computer exporteren. Wanneer u het rapport gebruikt, worden de rapportdocumenten geüpload naar een Azure Storage in de Microsoft-cloud.
  
1. Ga naar [https://protection.office.com](https://protection.office.com).
    
2. Meld u aan met uw werk- of schoolaccount.
    
3. Klik in het linkerdeelvenster van & Compliancecentrum op **Zoeken in** \> **inhoud.**
    
4. Selecteer op **de pagina Inhoud** zoeken een zoekopdracht. 
    
5. Klik in het detailvenster onder **Rapport exporteren naar een computer** op Rapport **genereren.**
    
    > [!NOTE]
    > Als de resultaten voor een zoekopdracht ouder zijn dan 7 dagen, wordt u gevraagd de zoekresultaten bij te werken. Als dit gebeurt, annuleert u de export, klikt u **in** het detailvenster op Zoekresultaten bijwerken voor de geselecteerde zoekopdracht en start u het rapport opnieuw nadat de resultaten zijn bijgewerkt. 
  
6. Kies op **de pagina Een rapport** exporteren onder Deze items uit de **zoekopdracht** opnemen een van de volgende opties:
    
    - Alleen geïndexeerde items exporteren
    
    - Geïndexeerde en niet-geïndexeerde items exporteren
    
    - Alleen niet-geïndexeerde items exporteren
    
    Zie Gedeeltelijk geïndexeerde items in Inhoud zoeken voor meer informatie over niet-geïndexeerde [items.](partially-indexed-items-in-content-search.md)
    
7. Kies om zoekstatistieken op te nemen voor alle versies van SharePoint documenten. Deze optie wordt alleen weergegeven als de inhoudsbronnen van de zoekopdracht sites SharePoint of OneDrive voor Bedrijven bevatten.
    
8. Klik **op Rapport genereren.**
    
    Het rapport met zoekresultaten is voorbereid voor het downloaden, wat betekent dat de rapportdocumenten worden geüpload naar het Azure Storage in de Microsoft-cloud. Wanneer het rapport klaar is om te worden gedownload, wordt de **koppeling** Rapport downloaden weergegeven onder Rapport exporteren naar **een computer** in het detailvenster. 
    
> [!NOTE]
> U kunt ook een rapport exporteren voor een inhoudszoekactie die is gekoppeld aan een eDiscovery-zaak. Hiervoor gaat u naar **eDiscovery** \> **eDiscovery,** selecteert u een zaak en klikt u op **Pictogram** ![ Bewerken ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) bewerken. Selecteer op **de pagina** Zoekopdrachten een zoekopdracht en klik vervolgens op **Pictogram** Zoekresultaten exporteren Exporteren ![ Een rapport ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **exporteren.** 
  
## <a name="step-2-download-the-report"></a>Stap 2: Het rapport downloaden

De volgende stap is het downloaden van het rapport van het Azure Storage naar uw lokale computer.
  
1. Klik in het detailvenster voor de zoekopdracht waar u het rapport voor hebt gegenereerd, onder **Rapport exporteren** naar een computer op Rapport **downloaden.**
    
    De **pagina Rapport** downloaden wordt weergegeven en bevat de volgende informatie over het rapport dat naar uw computer is gedownload. 
    
    - Het aantal items dat wordt gedownload.
    
    - De geschatte totale grootte van de items die worden gedownload.
    
    - Geïndexeerd of niet-geïndexeerd wordt geëxporteerd. Niet-geïndexeerde items zijn items met een herkende notatie, die zijn versleuteld of die om andere redenen niet zijn geïndexeerd.
    
    - Of versies van SharePoint documenten worden gedownload.
    
    - De status van het rapportexportproces. U kunt het rapport gaan downloaden, zelfs als de voorbereiding van het rapport niet is voltooid.
    
2. Klik **onder Exportcode** op **Kopiëren naar klembord.** U gebruikt deze sleutel in stap 5 om het rapport te downloaden.
    
    > [!IMPORTANT]
    > Omdat iedereen het hulpprogramma eDiscovery Export kan installeren en starten en vervolgens deze sleutel kan gebruiken om het zoekrapport te downloaden, moet u voorzorgsmaatregelen nemen om deze sleutel te beveiligen, net zoals u wachtwoorden of andere beveiligingsgerelateerde informatie zou beveiligen. 
  
3. Klik **op Rapport downloaden.**
    
4. Als u wordt gevraagd het **eDiscovery-exportprogramma te installeren,** klikt u op **Installeren.**
    
5. Plak in **het eDiscovery-exporthulpmiddel** de exportcode die u in stap 2 in het juiste vak hebt gekopieerd.
    
6. Klik **op Bladeren** om de locatie op te geven waar u het rapport wilt downloaden. 
    
7. Klik **op Start** om de zoekresultaten naar uw computer te downloaden. 
    
    Het **eDiscovery-exporthulpmiddel** geeft statusgegevens weer over het exportproces, inclusief een schatting van het aantal (en de grootte) van de resterende items die moeten worden gedownload. Wanneer het exportproces is voltooid, hebt u toegang tot de bestanden op de locatie waar ze zijn gedownload. 
    
> [!NOTE]
> U kunt het rapport downloaden voor een inhoudszoekactie die is gekoppeld aan een eDiscovery-zaak. Hiervoor gaat u naar **eDiscovery** \> **eDiscovery,** selecteert u een zaak en klikt u op **Pictogram** ![ Bewerken ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) bewerken. Selecteer op **de** pagina Export een rapport exporteren en klik vervolgens op **Rapport downloaden** in het detailvenster. 
  
## <a name="whats-included-in-the-report"></a>Wat is opgenomen in het rapport

Wanneer u een rapport over de resultaten van een inhoudszoekactie genereert en exporteert, worden de volgende documenten gedownload:
  
- **Exportoverzicht:** Een Excel document met een overzicht van de export. Dit omvat informatie, zoals het aantal inhoudsbronnen dat is doorzocht, het aantal zoekresultaten van elke inhoudslocatie, het geschatte aantal items, het werkelijke aantal items dat zou worden geëxporteerd en de geschatte en werkelijke grootte van items die zouden worden geëxporteerd. 
    
    > [!NOTE]
    > Als u niet-geïndexeerde items opgeeft bij het exporteren van het rapport, wordt het aantal niet-geïndexeerde items opgenomen in het totale aantal geschatte zoekresultaten en in het totale aantal gedownloade zoekresultaten (als u de zoekresultaten wilt exporteren) die worden weergegeven in het rapport Overzicht exporteren. Met andere woorden, het totale aantal items dat wordt gedownload, is gelijk aan het totale aantal geschatte resultaten en het totale aantal niet-geïndexeerde items. 
  
- **Manifest:** Een manifestbestand (in XML-indeling) dat informatie bevat over elk item dat in de zoekresultaten wordt opgenomen. 
    
- **Resultaten:** Een Excel document met een rij met informatie over elk geïndexeerd item dat met de zoekresultaten zou worden geëxporteerd. Voor e-mail bevat het resultatenlogboek informatie over elk bericht, waaronder: 
    
  - De locatie van het bericht in het bronpostvak (inclusief of het bericht zich in het primaire of archiefpostvak bevindt).
    
  - De datum waarop het bericht is verzonden of ontvangen.
    
  - De onderwerpregel van het bericht.
    
  - De afzender en geadresseerden van het bericht.
    
    Voor documenten van SharePoint en OneDrive voor Bedrijven sites bevat het logboek Resultaten informatie over elk document, waaronder:
    
  - De URL voor het document.
    
  - De URL voor de siteverzameling waar het document zich bevindt.
    
  - De datum waarop het document voor het laatst is gewijzigd.
    
  - De naam van het document (dat zich in de kolom Onderwerp in het resultatenlogboek bevindt).
    
    > [!NOTE]
    > Het aantal rijen  in het rapport Resultaten moet gelijk zijn aan het totale aantal zoekresultaten minus het totale aantal items dat wordt weergegeven in het rapport **Niet-geïndexeerde** items. 
  
- **Niet-geïndexeerde items:** Een Excel document met informatie over niet-geïndexeerde items in de zoekresultaten. Als u geen niet-geïndexeerde items opgeeft wanneer u het rapport met zoekresultaten genereert, wordt dit rapport nog steeds gedownload, maar is het leeg.
