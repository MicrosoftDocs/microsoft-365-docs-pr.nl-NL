---
title: Inhoudszoekresultaten exporteren
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: Exporteert de zoekresultaten van een inhoudszoekactie in het Microsoft 365 compliancecentrum naar een lokale computer. E-mailresultaten worden geëxporteerd als PST-bestanden. Inhoud van SharePoint en OneDrive voor Bedrijven sites worden geëxporteerd als inheems Office documenten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3bb46966ddd8d4b2ae61091b126daea1413039ac
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/24/2021
ms.locfileid: "52162723"
---
# <a name="export-content-search-results"></a>Inhoudszoekresultaten exporteren

Nadat een inhoudszoekactie is uitgevoerd, kunt u de zoekresultaten exporteren naar een lokale computer. Wanneer u e-mailresultaten exporteert, worden deze als PST-bestanden naar uw computer gedownload. Wanneer u inhoud exporteert van SharePoint en OneDrive voor Bedrijven sites, worden kopieën van Office documenten geëxporteerd. Er zijn andere documenten en rapporten opgenomen in de geëxporteerde zoekresultaten.
  
Als u de resultaten van een inhoudszoekactie exporteert, worden de resultaten voorbereid en vervolgens gedownload naar een lokale computer.
  
## <a name="before-you-export-content-search-results"></a>Voordat u inhoudszoekresultaten exporteert

- Als u zoekresultaten wilt exporteren, moet u de rol Exportbeheer krijgen toegewezen in het beveiligings- & Compliancecentrum. Deze rol wordt toegewezen aan de ingebouwde rollengroep eDiscovery Manager. De functie is niet standaard toegewezen aan de rollengroep Organisatiebeheer. Zie [eDiscovery-machtigingen](assign-ediscovery-permissions.md)toewijzen voor meer informatie.

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
  
- We raden u aan zoekresultaten te downloaden naar een lokale computer. Als u echter wilt voorkomen dat de firewall of proxy-infrastructuur van uw bedrijf problemen veroorzaakt bij het downloaden van zoekresultaten, kunt u overwegen zoekresultaten te downloaden naar een virtueel bureaublad buiten uw netwerk. Dit kan time-outs verminderen die voorkomen in Azure-gegevensverbindingen bij het exporteren van een groot aantal bestanden. Zie voor meer informatie over virtuele bureaubladen [Windows Virtual Desktop.](https://azure.microsoft.com/services/virtual-desktop) 

- Als u de prestaties bij het downloaden van zoekresultaten wilt verbeteren, kunt u zoekopdrachten die een grote reeks resultaten retourneren, verdelen in kleinere zoekopdrachten. U kunt bijvoorbeeld datumbereiken in zoekquery's gebruiken om een kleinere reeks resultaten te retourneren die sneller kunnen worden gedownload.
  
- Wanneer u zoekresultaten exporteert, worden de gegevens tijdelijk opgeslagen op een door Microsoft verstrekte Azure Storage in de Microsoft-cloud voordat deze worden gedownload naar uw lokale computer. Zorg ervoor dat uw organisatie verbinding kan maken met het eindpunt in Azure, dat **\* .blob.core.windows.net** is (het jokerteken vertegenwoordigt een unieke id voor uw export). De zoekresultaten worden twee weken na het maken Azure Storage van de locatie verwijderd. 
  
- Als uw organisatie een proxyserver gebruikt om te communiceren met internet, moet u de proxyserverinstellingen definiëren op de computer die u gebruikt om de zoekresultaten te exporteren (zodat het exportprogramma kan worden geverifieerd door uw proxyserver). Open hiervoor het *machine.config* bestand op de locatie die overeenkomt met uw versie van Windows. 
  
  - **32-bits:**`%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
  
  - **64-bits:**`%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
  
    Voeg de volgende regels toe aan  *machine.config*  bestand tussen de  `<configuration>`  `</configuration>` tags. Zorg ervoor dat u de juiste waarden voor uw organisatie  `ProxyServer`  `Port` vervangt, `proxy01.contoso.com:80` bijvoorbeeld. 
  
    ```xml
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="https://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

## <a name="step-1-prepare-search-results-for-export"></a>Stap 1: Zoekresultaten voorbereiden voor export

De eerste stap is het voorbereiden van de zoekresultaten voor het exporteren. Wanneer u de resultaten voorbereidt, worden deze geüpload naar een door Microsoft verstrekte Azure Storage in de Microsoft-cloud. Inhoud van postvakken en sites wordt geüpload met een maximumsnelheid van 2 GB per uur.
  
1. Ga naar [https://protection.office.com](https://protection.office.com).
  
2. Meld u aan met uw werk- of schoolaccount.
  
3. Klik in het linkerdeelvenster van & Compliancecentrum op **Zoeken in** \> **inhoud.**
  
4. Selecteer op **de pagina Inhoud** zoeken een zoekopdracht. 
  
5. Klik in het detailvenster onder **Resultaten exporteren naar een computer** op Exporteren **starten.**
  
    > [!NOTE]
    > Als de resultaten voor een zoekopdracht ouder zijn dan 7 dagen, wordt u gevraagd de zoekresultaten bij te werken. Als dit gebeurt, annuleert u de export, klikt u **in** het detailvenster op Zoekresultaten bijwerken voor de geselecteerde zoekopdracht en start u de export opnieuw nadat de resultaten zijn bijgewerkt. 
  
6. Kies op **de pagina De** zoekresultaten exporteren onder **Uitvoeropties** een van de volgende opties:
  
    - Alle items, met uitzondering van items met een niet-herkende notatie, worden versleuteld of zijn om andere redenen niet geïndexeerd
  
    - Alle items, inclusief items met een niet-herkende notatie, worden versleuteld of zijn om andere redenen niet geïndexeerd
  
    - Alleen items met een niet-herkende notatie, worden versleuteld of om andere redenen niet geïndexeerd
  
    Zie de [sectie Meer informatie](#more-information) voor een beschrijving over hoe gedeeltelijk geïndexeerde items worden geëxporteerd. Zie Gedeeltelijk geïndexeerde items in Inhoud zoeken voor meer informatie over gedeeltelijk geïndexeerde [items.](partially-indexed-items-in-content-search.md)
  
7. Kies **onder Exchange inhoud exporteren als** een van de volgende opties:
  
    - **Eén PST-bestand voor elk postvak:** Hiermee exporteert u één PST-bestand voor elk gebruikerspostvak dat zoekresultaten bevat. Alle resultaten uit het archiefpostvak van de gebruiker worden opgenomen in hetzelfde PST-bestand. Met deze optie wordt de structuur van de postvakmap uit het bronpostvak gereproduceerd.
  
    - **Eén PST-bestand met alle berichten:** Hiermee exporteert u één PST-bestand *(Exchange.pst)* dat de zoekresultaten bevat van alle bronpostvakken die in de zoekopdracht zijn opgenomen. Met deze optie wordt de structuur van de postvakmap voor elk bericht gereproduceerd.
  
    - **Eén PST-bestand met alle berichten in één map:** Hiermee exporteert u zoekresultaten naar één PST-bestand waarin alle berichten zich in één map op het hoogste niveau bevinden. Met deze optie kunnen revisoren items in chronologische volgorde bekijken (items worden gesorteerd op verzonden datum) zonder dat ze in de oorspronkelijke mapstructuur voor elk item moeten navigeren.
  
    - **Afzonderlijke berichten:** Hiermee exporteert u zoekresultaten als afzonderlijke e-mailberichten met de MSG-indeling. Als u deze optie selecteert, worden de zoekresultaten per e-mail geëxporteerd naar een map in het bestandssysteem. Het mappad voor afzonderlijke berichten is hetzelfde als het pad dat wordt gebruikt als u de resultaten exporteert naar PST-bestanden.
  
      > [!IMPORTANT]
      > Als u RMS-beveiligde berichten wilt ontsleutelen wanneer ze worden geëxporteerd, moet u zoekresultaten per e-mail exporteren als afzonderlijke berichten. Versleutelde berichten blijven versleuteld als u de zoekresultaten exporteert als een PST-bestand. Zie E-mailberichten en versleutelde bestandsbijlagen in dit artikel ontsleutelen met [RMS-beveiligde e-mailberichten](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments) en versleutelde bestandsbijlagen voor meer informatie.
  
8. Klik op **het selectievakje Duplicatie** inschakelen om dubbele berichten uit te sluiten. Deze optie wordt alleen weergegeven als de inhoudsbronnen van de zoekopdracht Exchange postvakken of openbare mappen bevatten. 
  
    Als u deze optie selecteert, wordt slechts één kopie van een bericht geëxporteerd, zelfs als er meerdere exemplaren van hetzelfde bericht worden gevonden in de postvakken die zijn doorzocht. Het rapport exportresultaten (Results.csv) bevat een rij voor elke kopie van een duplicaatbericht, zodat u de postvakken (of openbare mappen) kunt identificeren die een kopie van het dubbele bericht bevatten. Zie [De-duplicatie in eDiscovery-zoekresultaten](de-duplication-in-ediscovery-search-results.md)voor meer informatie over de-duplicatie en hoe dubbele items worden geïdentificeerd.
  
9. Klik op **het selectievakje Versies opnemen voor SharePoint documenten om** alle versies van documenten SharePoint exporteren. Deze optie wordt alleen weergegeven als de inhoudsbronnen van de zoekopdracht sites SharePoint of OneDrive voor Bedrijven bevatten. 
  
10. Klik op **het selectievakje Bestanden exporteren in een gecomprimeerde map (geritst)** om zoekresultaten te exporteren naar gecomprimeerde mappen. Deze optie is alleen beschikbaar wanneer u ervoor kiest om Exchange als afzonderlijke berichten te exporteren en wanneer de zoekresultaten documenten SharePoint of OneDrive bevatten. Deze optie wordt voornamelijk gebruikt om te werken rond de limiet van 260 tekens in Windows bestandspadnamen wanneer items worden geëxporteerd. Zie de 'Bestandsnaam van geëxporteerde items' in [de sectie Meer](#more-information) informatie. 
  
11. Klik **op Exporteren starten.** De zoekresultaten zijn voorbereid voor het downloaden, wat betekent dat ze worden geüpload naar een Azure Storage locatie in de Microsoft-cloud. Dit kan enkele minuten duren.

Zie de volgende sectie voor instructies voor het downloaden van de geëxporteerde zoekresultaten.
  
## <a name="step-2-download-the-search-results"></a>Stap 2: De zoekresultaten downloaden

De volgende stap is het downloaden van de zoekresultaten van de Azure Storage locatie naar uw lokale computer.
  
1. Klik op **de pagina Inhoud** zoeken op het tabblad **Exporteren.** 
  
   Mogelijk moet u op Vernieuwen klikken **om** de lijst met exporttaken bij te werken, zodat de exporttaken worden weergegeven die u hebt gemaakt. Exporttaken hebben dezelfde naam als de bijbehorende zoekopdracht **met _Export** toegevoegd aan de zoeknaam.
  
2. Selecteer de exportklus die u hebt gemaakt in stap 1.

3. Klik op de flyoutpagina onder **Exportcode** op **Kopiëren naar klembord.** U gebruikt deze sleutel in stap 6 om de zoekresultaten te downloaden.
  
4. Klik **op Resultaten downloaden.**

5. Als u wordt gevraagd het **eDiscovery-exportprogramma te installeren,** klikt u op **Installeren.**

6. Ga als volgt te werk in het **eDiscovery-exporthulpmiddel:**

   ![eDiscovery Export Tool](../media/eDiscoveryExportTool.png)

   1. Plak de exportcode die u hebt gekopieerd in stap 3 in het juiste vak.
  
   2. Klik **op Bladeren** om de locatie op te geven waar u de zoekresultaten wilt downloaden.
  
      > [!IMPORTANT]
      >  Vanwege de hoge netwerkactiviteit tijdens het downloaden, moet u zoekresultaten alleen downloaden naar een locatie op een intern station op uw lokale computer. Volg de volgende richtlijnen voor de beste downloadervaring: <br/>
      >- Download geen zoekresultaten naar een UNC-pad, een netwerkstation, een extern USB-station of een gesynchroniseerd OneDrive voor Bedrijven account.<br/>
      >- Schakel het scannen van virussen uit voor de map waar u het zoekresultaat naar downloadt.<br/>
      >- Download zoekresultaten naar verschillende mappen voor gelijktijdige downloadtaken.

6. Klik **op Start** om de zoekresultaten naar uw computer te downloaden.
  
    Het **eDiscovery-exporthulpmiddel** geeft statusgegevens weer over het exportproces, inclusief een schatting van het aantal (en de grootte) van de resterende items die moeten worden gedownload. Wanneer het exportproces is voltooid, hebt u toegang tot de bestanden op de locatie waar ze zijn gedownload.

## <a name="more-information"></a>Meer informatie

Hier vindt u meer informatie over het exporteren van zoekresultaten.
  
[Exportlimieten](#export-limits)
  
[Rapporten exporteren](#export-reports)
  
[Gedeeltelijk geïndexeerde items exporteren](#exporting-partially-indexed-items)

[Afzonderlijke berichten of PST-bestanden exporteren](#exporting-individual-messages-or-pst-files)

[Met RMS beveiligde e-mailberichten en versleutelde bestandsbijlagen ontsleutelen](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments)

[Bestandsnaam van geëxporteerde items](#filenames-of-exported-items)  
  
[Diversen](#miscellaneous)
  
### <a name="export-limits"></a>Exportlimieten

Zie de sectie 'Exportlimieten' in Limieten voor inhoud zoeken voor informatie over limieten bij het exporteren van [inhoudsresultaten.](limits-for-content-search.md#export-limits)

### <a name="export-reports"></a>Rapporten exporteren
  
- Wanneer u zoekresultaten exporteert, worden naast de zoekresultaten ook de volgende rapporten opgenomen.
  
  - **Exportoverzicht** Een Excel document met een overzicht van de export. Dit omvat informatie, zoals het aantal inhoudsbronnen dat is doorzocht, de geschatte en gedownloade grootte van de zoekresultaten en het geschatte en gedownloade aantal items dat is geëxporteerd.
  
  - **Manifest** Een manifestbestand (in XML-indeling) dat informatie bevat over elk item dat in de zoekresultaten wordt opgenomen.
  
  - **Resultaten** Een Excel document met informatie over elk item dat als zoekresultaat wordt gedownload. Voor e-mail bevat het resultatenlogboek informatie over elk bericht, waaronder:
  
    - De locatie van het bericht in het bronpostvak (inclusief of het bericht zich in het primaire of archiefpostvak bevindt).
  
    - De datum waarop het bericht is verzonden of ontvangen.

    - De onderwerpregel van het bericht.

    - De afzender en geadresseerden van het bericht.

    - Of het bericht een duplicaatbericht is als u de optie de-duplicatie hebt ingeschakeld bij het exporteren van de zoekresultaten. Dubbele berichten hebben een waarde in de kolom **Dupliceren** naar item die het bericht als een duplicaat identificeert. De waarde in de **kolom Dupliceren** naar item bevat de itemidentiteit van het bericht dat is geëxporteerd. Zie [De-duplicatie in de zoekresultaten van eDiscovery voor meer informatie.](de-duplication-in-ediscovery-search-results.md)

      Voor documenten van SharePoint en OneDrive voor Bedrijven sites bevat het resultatenlogboek informatie over elk document, waaronder:

      - De URL voor het document.

      - De URL voor de siteverzameling waar het document zich bevindt.

      - De datum waarop het document voor het laatst is gewijzigd.

      - De naam van het document (dat zich in de kolom Onderwerp in het resultatenlogboek bevindt).

  - **Niet-geïndexeerde items** Een Excel document met informatie over gedeeltelijk geïndexeerde items die in de zoekresultaten zouden worden opgenomen. Als u geen gedeeltelijk geïndexeerde items op neemt wanneer u het rapport met zoekresultaten genereert, wordt dit rapport nog steeds gedownload, maar is het leeg.

  - **Fouten en waarschuwingen** Bevat fouten en waarschuwingen voor bestanden die tijdens het exporteren zijn aangetroffen. Zie de kolom Foutgegevens voor informatie die specifiek is voor elke afzonderlijke fout of waarschuwing.

  - **Overgeslagen items** Wanneer u zoekresultaten exporteert van SharePoint en OneDrive voor Bedrijven sites, bevat de export meestal een rapport overgeslagen items (SkippedItems.csv). De items die in dit rapport worden aangehaald, zijn meestal items die niet worden gedownload, zoals een map of een documentset. Het niet exporteren van dit type items is een ontwerp. Voor andere items die zijn overgeslagen, wordt in het veld Fouttype en Foutgegevens in het rapport Overgeslagen items de reden weergegeven waarom het item is overgeslagen en niet is gedownload met de andere zoekresultaten.

  - **Logboek traceren** Bevat gedetailleerde logboekregistratiegegevens over het exportproces en kan helpen bij het ontdekken van problemen tijdens het exporteren.
  
    > [!NOTE]
    > U kunt deze documenten gewoon exporteren zonder de werkelijke zoekresultaten te exporteren. Zie [Een inhoudszoekrapport exporteren.](export-a-content-search-report.md) 
  
### <a name="exporting-partially-indexed-items"></a>Gedeeltelijk geïndexeerde items exporteren
  
- Als u postvakitems exporteert vanuit een inhoudszoekactie die alle postvakitems in de zoekresultaten retourneert (omdat er geen trefwoorden zijn opgenomen in de zoekquery), worden gedeeltelijk geïndexeerde items niet gekopieerd naar het PST-bestand met de niet-geïndexeerde items. Dit komt omdat alle items, inclusief gedeeltelijk geïndexeerde items, automatisch worden opgenomen in de normale zoekresultaten. Dit betekent dat gedeeltelijk geïndexeerde items worden opgenomen in een PST-bestand (of als afzonderlijke berichten) met de andere, geïndexeerde items.

    Als u zowel de geïndexeerde als gedeeltelijk geïndexeerde items exporteert of als u alleen de geïndexeerde items exporteert uit een inhoudszoekactie die alle items retourneert, wordt hetzelfde aantal items gedownload. Dit gebeurt ook al bevatten de geschatte zoekresultaten voor het zoeken naar inhoud (weergegeven in de zoekstatistieken in het beveiligings- & compliancecentrum) nog steeds een afzonderlijke schatting voor het aantal gedeeltelijk geïndexeerde items. Stel dat de schatting voor een zoekopdracht met alle items (geen trefwoorden in de zoekquery) laat zien dat er 1000 items zijn gevonden en dat er ook 200 gedeeltelijk geïndexeerde items zijn gevonden. In dit geval bevatten de 1.000 items de gedeeltelijk geïndexeerde items, omdat de zoekopdracht alle items retourneert. Met andere woorden, er zijn in totaal 1.000 items die door de zoekopdracht worden geretourneerd en niet 1.200 items (zoals u zou verwachten). Als u de resultaten van deze zoekopdracht exporteert en geïndexeerde en gedeeltelijk geïndexeerde items exporteert (of alleen gedeeltelijk geïndexeerde items exporteert), worden 1000 items gedownload. Nogmaals, dat komt omdat gedeeltelijk geïndexeerde items worden opgenomen in de normale (geïndexeerde) resultaten wanneer u een lege zoekquery gebruikt om alle items te retourneren. Als u in hetzelfde voorbeeld ervoor kiest om slechts gedeeltelijk geïndexeerde items te exporteren, worden alleen de 200 niet-geïndexeerde items gedownload.

    Houd er ook rekening mee dat in het vorige voorbeeld (wanneer u geïndexeerde en gedeeltelijk geïndexeerde items exporteert of alleen geïndexeerde items exporteert), het rapport Overzicht exporteren in de geëxporteerde zoekresultaten 1000 geschatte items en 1.000 gedownloade items bevat om dezelfde redenen als eerder beschreven.  

- Als de zoekopdracht waaruit u resultaten exporteert, een zoekopdracht was naar specifieke inhoudslocaties of alle inhoudslocaties in uw organisatie, worden alleen de gedeeltelijke items van inhoudslocaties die items bevatten die voldoen aan de zoekcriteria, geëxporteerd. Met andere woorden: als er geen zoekresultaten worden gevonden in een postvak of site, worden gedeeltelijk geïndexeerde items in dat postvak of die site niet geëxporteerd. De reden hiervoor is dat het exporteren van gedeeltelijk geïndexeerde items vanuit een groot aantal locaties in de organisatie de kans op exportfouten kan vergroten en de tijd kan vergroten om de zoekresultaten te exporteren en te downloaden.

    Als u gedeeltelijk geïndexeerde items wilt exporteren van alle inhoudslocaties voor een zoekopdracht, configureert u de zoekopdracht om alle items te retourneren (door trefwoorden uit de zoekquery te verwijderen) en exporteert u vervolgens alleen gedeeltelijk geïndexeerde items wanneer u de zoekresultaten exporteert.

    ![De derde exportoptie gebruiken om alleen niet-geïndexeerde items te exporteren](../media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- Wanneer u zoekresultaten exporteert van SharePoint- of OneDrive voor Bedrijven-sites, is de mogelijkheid om niet-geïndexeerde items te exporteren ook afhankelijk van de exportoptie die u selecteert en of een site die is gezocht een geïndexeerd item bevat dat voldoet aan de zoekcriteria. Als u bijvoorbeeld op specifieke SharePoint- of OneDrive voor Bedrijven-sites zoekt en er geen zoekresultaten worden gevonden, worden er geen niet-geïndexeerde items van deze sites geëxporteerd als u de tweede exportoptie kiest om zowel geïndexeerde als niet-geïndexeerde items te exporteren. Als een geïndexeerd item van een site wel voldoet aan de zoekcriteria, worden alle niet-geïndexeerde items van die site geëxporteerd bij het exporteren van zowel geïndexeerde als niet-geïndexeerde items. In de volgende afbeelding worden de exportopties beschreven op basis van of een site een geïndexeerd item bevat dat overeenkomt met de zoekcriteria.

    ![De exportoptie kiezen op basis van of een site een geïndexeerd item bevat dat voldoet aan de zoekcriteria](../media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    a. Alleen geïndexeerde items die voldoen aan de zoekcriteria, worden geëxporteerd. Er worden geen gedeeltelijk geïndexeerde items geëxporteerd.

    b. Als geen geïndexeerde items van een site overeenkomen met de zoekcriteria, worden gedeeltelijk geïndexeerde items van dezelfde site niet geëxporteerd. Als geïndexeerde items van een site worden geretourneerd in de zoekresultaten, worden de gedeeltelijk geïndexeerde items van die site geëxporteerd. Met andere woorden: alleen de gedeeltelijk geïndexeerde items van sites die items bevatten die voldoen aan de zoekcriteria, worden geëxporteerd.

    c. Alle gedeeltelijk geïndexeerde items van alle sites in de zoekopdracht worden geëxporteerd, ongeacht of een site items bevat die voldoen aan de zoekcriteria.

    Als u ervoor kiest om gedeeltelijk geïndexeerde items te exporteren, worden gedeeltelijk geïndexeerde postvakitems geëxporteerd in een afzonderlijk PST-bestand, ongeacht de optie die u kiest onder **Exchange exporteren** als .

- Als gedeeltelijk geïndexeerde items worden geretourneerd in de zoekresultaten (omdat andere eigenschappen van gedeeltelijk geïndexeerde items overeenkomen met de zoekcriteria), worden deze gedeeltelijk geïndexeerd met de normale zoekresultaten geëxporteerd. Als u ervoor kiest om zowel geïndexeerde items als gedeeltelijk geïndexeerde items te exporteren (door alle **items te selecteren,** inclusief items met een niet-herkende notatie, zijn versleuteld of niet zijn geïndexeerd om andere redenen exportoptie), worden de gedeeltelijk geïndexeerde items die met de normale resultaten worden geëxporteerd, weergegeven in het rapport Results.csv. Ze worden niet weergegeven in het niet-geïndexeerde items.csv rapport.
  
### <a name="exporting-individual-messages-or-pst-files"></a>Afzonderlijke berichten of PST-bestanden exporteren
  
- Als de naam van het bestandspad van een bericht de maximumtekenlimiet voor Windows overschrijdt, wordt de naam van het bestandspad afgekapt. Maar de oorspronkelijke naam van het bestandspad wordt weergegeven in het Manifest en ResultsLog.
  
- Zoals eerder uitgelegd, worden e-mailzoekresultaten geëxporteerd naar een map in het bestandssysteem. Het mappad voor afzonderlijke berichten zou het mappad in het postvak van de gebruiker repliceren. Voor een zoekopdracht met de naam 'ContosoCase101' bevinden berichten in het Postvak IN van een gebruiker zich bijvoorbeeld in het  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox` mappad.

- Als u ervoor kiest om e-mailberichten te exporteren in één  PST-bestand  met alle berichten in één map, worden een map Verwijderde items en een map Zoekmappen opgenomen in het bovenste niveau van de PST-map. Deze mappen zijn leeg.

- Zoals eerder is vermeld, moet u zoekresultaten per e-mail exporteren als afzonderlijke berichten om met RMS beveiligde berichten te ontsleutelen wanneer ze worden geëxporteerd. Versleutelde berichten blijven versleuteld als u zoekresultaten per e-mail exporteert als een PST-bestand.
  
### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments"></a>Met RMS beveiligde e-mailberichten en versleutelde bestandsbijlagen ontsleutelen

Alle met rechten beveiligde (RMS-beveiligde) e-mailberichten die zijn opgenomen in de resultaten van een inhoudszoekactie, worden ontsleuteld wanneer u deze exporteert. Bovendien wordt elk bestand dat is [](encryption.md) versleuteld met een Microsoft-versleutelingstechnologie en is gekoppeld aan een e-mailbericht dat is opgenomen in de zoekresultaten, ook ontsleuteld wanneer het wordt geëxporteerd. Deze ontsleutelingsfunctie is standaard ingeschakeld voor leden van de rollengroep eDiscovery Manager. Dit komt omdat de beheerrol RMS Decrypt standaard aan deze rollengroep is toegewezen. Houd rekening met de volgende zaken bij het exporteren van versleutelde e-mailberichten en bijlagen:
  
- Als u rms-beveiligde berichten wilt ontsleutelen wanneer u deze exporteert, moet u de zoekresultaten exporteren als afzonderlijke berichten. Als u zoekresultaten exporteert naar een PST-bestand, blijven rms-beveiligde berichten versleuteld.

- Berichten die zijn ontsleuteld, worden geïdentificeerd in het **rapport ResultsLog.** Dit rapport bevat een kolom met de naam **Status decoderen** en een waarde van **Gedecodeerd** in deze kolom identificeert de berichten die zijn ontsleuteld.

- Naast het ontsleutelen van bestandsbijlagen bij het exporteren van zoekresultaten, kunt u ook een voorbeeld van het ontsleutelde bestand bekijken wanneer u een voorbeeld van zoekresultaten bekijkt. U kunt het met rechten beveiligde e-mailbericht alleen weergeven nadat u het hebt geëxporteerd.

- Op dit moment bevat de ontsleutelingsfunctie bij het exporteren van zoekresultaten geen versleutelde inhoud van SharePoint en OneDrive voor Bedrijven sites. Er is echter binnenkort ondersteuning voor documenten die zijn versleuteld met Microsoft-versleutelingstechnologieën en die zijn opgeslagen in SharePoint Online en OneDrive voor Bedrijven.

- Als u wilt voorkomen dat iemand RMS-beveiligende berichten en versleutelde bestandsbijlagen ontsleutelt, moet u een aangepaste rollengroep maken (door de ingebouwde eDiscovery Manager-rollengroep te kopiëren) en vervolgens de beheerrol RMS Decrypt verwijderen uit de aangepaste rollengroep. Voeg vervolgens de persoon toe die u berichten niet wilt ontsleutelen als lid van de aangepaste rollengroep.
  
### <a name="filenames-of-exported-items"></a>Bestandsnaam van geëxporteerde items
  
- Er is een limiet van 260 tekens (opgelegd door het besturingssysteem) voor de volledige padnaam voor e-mailberichten en sitedocumenten die naar uw lokale computer worden geëxporteerd. De volledige padnaam voor geëxporteerde items bevat de oorspronkelijke locatie van het item en de maplocatie op de lokale computer waar de zoekresultaten naar worden gedownload. Als u bijvoorbeeld opgeeft om de zoekresultaten te downloaden in het  `C:\Users\Admin\Desktop\SearchResults` hulpprogramma eDiscovery-export, is de volledige padnaam voor een gedownload e-mailitem  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg` .

- Als de limiet van 260 tekens wordt overschreden, wordt de volledige padnaam voor een item afgekapt, op basis van het volgende:

  - Als de naam van het volledige pad langer is dan 260 tekens, wordt de bestandsnaam ingekort om onder de limiet te komen. Houd er rekening mee dat de afgekapte bestandsnaam (met uitzondering van de bestandsextensie) niet minder dan acht tekens bevat.

  - Als de naam van het volledige pad na het inkorten van de bestandsnaam nog te lang is, wordt het item verplaatst van de huidige locatie naar de bovenliggende map. Als de padnaam nog te lang is, wordt het proces herhaald: verkort de bestandsnaam en ga zo nodig opnieuw naar de bovenliggende map. Dit proces wordt herhaald totdat de volledige padnaam onder de limiet van 260 tekens valt.

  - Als er al een afgekapte volledige padnaam bestaat, wordt er een versienummer toegevoegd aan het einde van de bestandsnaam. `statusmessage(2).msg`bijvoorbeeld.

    Als u dit probleem wilt beperken, kunt u zoekresultaten downloaden naar een locatie met een naam voor een kort pad. Als u bijvoorbeeld zoekresultaten downloadt naar een map met de naam, worden er minder tekens toegevoegd aan de padnamen van geëxporteerde items dan dat u ze downloadt naar een map met  `C:\Results` de naam  `C:\Users\Admin\Desktop\Results` .

- Wanneer u sitedocumenten exporteert, is het ook mogelijk dat de oorspronkelijke bestandsnaam van een document wordt gewijzigd. Dit gebeurt specifiek voor documenten die zijn verwijderd van een SharePoint of OneDrive voor Bedrijven site die in de wacht is geplaatst. Nadat een document dat zich op een site in bewaring heeft geplaatst, is verwijderd, wordt het verwijderde document automatisch verplaatst naar de bewaringsbibliotheek voor de site (die is gemaakt toen de site in bewaring werd geplaatst). Wanneer het verwijderde document wordt verplaatst naar de bewaringsbibliotheek, wordt een willekeurig gegenereerde en unieke id toegevoegd aan de oorspronkelijke bestandsnaam van het document. Als de bestandsnaam voor een document bijvoorbeeld is en dat document later wordt verwijderd en naar de bewaringsbibliotheek wordt verplaatst, wordt de bestandsnaam van het document dat naar de bewaringsbibliotheek wordt verplaatst, gewijzigd in zoiets  `FY2017Budget.xlsx`  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` als . Als een document in de bibliotheek Bewaring behouden overeenkomt met de query van een inhoudszoekactie en u de resultaten van die zoekopdracht exporteert, heeft het geëxporteerde bestand de gewijzigde bestandsnaam. in dit voorbeeld is de bestandsnaam van het geëxporteerde document  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` .

    Wanneer een document op een site die in bewaring staat, is gewijzigd (en versie voor de documentbibliotheek op de site is ingeschakeld), wordt automatisch een kopie van het bestand gemaakt in de bibliotheek Bewaring. In dit geval wordt ook een willekeurig gegenereerde en unieke id toegevoegd aan de bestandsnaam van het document dat is gekopieerd naar de bewaringsbibliotheek.

    De reden waarom bestandsnaam van documenten die worden verplaatst of gekopieerd naar de bewaringsbibliotheek, is om conflicterende bestandsnaamen te voorkomen. Zie Overzicht van in-place bewaring in SharePoint [Server 2016 voor](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)meer informatie over het plaatsen van een bewaring op sites en de bewaringsbibliotheek.

### <a name="miscellaneous"></a>Diversen
  
- Wanneer u zoekresultaten downloadt met het eDiscovery-exporthulpmiddel, is het mogelijk dat u de volgende foutmelding ontvangt: Dit is een tijdelijke fout, die meestal optreedt op de Azure Storage `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` locatie. Als u dit probleem wilt oplossen, [downloadt](#step-2-download-the-search-results)u de zoekresultaten opnieuw, waarmee het eDiscovery-exporthulpmiddel opnieuw wordt gestart.

- Alle zoekresultaten en de exportrapporten worden opgenomen in een map met dezelfde naam als het zoeken naar inhoud. De e-mailberichten die zijn geëxporteerd, bevinden zich in een map **met de Exchange.** Documenten bevinden zich in een map met **de SharePoint.**

- De metagegevens van het bestandssysteem voor documenten op SharePoint en OneDrive voor Bedrijven sites worden bewaard wanneer documenten naar uw lokale computer worden geëxporteerd. Dit betekent dat documenteigenschappen, zoals gemaakte en laatst gewijzigde datums, niet worden gewijzigd wanneer documenten worden geëxporteerd.

- Als uw zoekresultaten een lijstitem uit SharePoint bevatten dat overeenkomt met de zoekquery, worden alle rijen in de lijst geëxporteerd, naast het item dat overeenkomt met de zoekquery en eventuele bijlagen in de lijst. De reden voor dit gedrag is om een context te bieden voor lijstitems die worden geretourneerd in de zoekresultaten. De extra lijstitems en bijlagen kunnen ertoe leiden dat het aantal geëxporteerde items anders is dan de oorspronkelijke schatting van zoekresultaten.
