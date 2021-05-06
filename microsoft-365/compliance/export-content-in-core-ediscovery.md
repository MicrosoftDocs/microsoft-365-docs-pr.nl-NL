---
title: Inhoud exporteren en downloaden uit een Hoofd-eDiscovery-zaak
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
description: In dit artikel wordt beschreven hoe u inhoud exporteert en downloadt vanuit een hoofd-eDiscovery-zaak.
ms.openlocfilehash: 30fc30943bd570cf4d79ce88b5bef5836b3dfe14
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161662"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>Inhoud exporteren uit een hoofd-eDiscovery-zaak

Nadat een zoekopdracht is uitgevoerd, kunt u de zoekresultaten exporteren. Wanneer u zoekresultaten exporteert, worden postvakitems gedownload in PST-bestanden of als afzonderlijke berichten. Wanneer u inhoud exporteert van SharePoint en OneDrive voor Bedrijven sites, worden kopieën van Office documenten en andere documenten geëxporteerd. Een Results.csv bestand met informatie over elk item dat wordt geëxporteerd en een manifestbestand (in XML-indeling) dat informatie bevat over elk zoekresultaat, wordt ook geëxporteerd.
  
U kunt de resultaten exporteren van één zoekopdracht [die](#export-the-results-of-a-single-search) is gekoppeld aan een zaak of u kunt de resultaten exporteren van meerdere zoekopdrachten die aan [een zaak zijn gekoppeld.](#export-the-results-of-multiple-searches)
  
## <a name="export-the-results-of-a-single-search"></a>De resultaten van één zoekopdracht exporteren

1. Ga naar en meld u aan met de referenties voor gebruikersaccount die zijn toegewezen aan de juiste [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery-machtigingen.

2. Klik in het linkernavigatiedeelvenster van Microsoft 365 compliancecentrum op Alles weergeven **en** klik vervolgens op **eDiscovery > Core.**

3. Selecteer op **de pagina Core eDiscovery** de zaak waaruit u zoekresultaten wilt exporteren en klik vervolgens op **Zaak openen.**

4. Klik op **de startpagina** voor de zaak op **het tabblad** Zoekopdrachten.

5. Klik in de lijst met zoekopdrachten naar de zaak op de zoekopdracht waaruit u zoekresultaten wilt exporteren en klik vervolgens op Resultaten exporteren **in** de flyout.

    De **pagina Resultaten exporteren** wordt weergegeven. 

    ![Pagina Resultaten exporteren](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    De werkstroom voor het exporteren van de resultaten van een zoekopdracht die is gekoppeld aan een Hoofd eDiscovery-zaak, is hetzelfde als het exporteren van de zoekresultaten voor een zoekopdracht op de pagina **Inhoud zoeken.** Zie Zoekresultaten voor inhoud exporteren voor [stapsgewijse instructies.](export-search-results.md)

    > [!NOTE]
    > Wanneer u zoekresultaten exporteert, kunt u de-duplicatie inschakelen, zodat slechts één kopie van een e-mailbericht wordt geëxporteerd, ook al zijn er mogelijk meerdere exemplaren van hetzelfde bericht gevonden in de postvakken die zijn doorzocht. Zie [De-duplicatie in eDiscovery-zoekresultaten](de-duplication-in-ediscovery-search-results.md)voor meer informatie over de-duplicatie en hoe dubbele items worden geïdentificeerd.

    Nadat u de export hebt gestart, worden de zoekresultaten voorbereid voor het downloaden, wat betekent dat ze worden geüpload naar een microsoft-Azure Storage locatie in de Microsoft-cloud.
  
6. Klik op **het tabblad** Exporteren om de lijst met exporttaken voor de zaak weer te geven.
  
    Mogelijk moet u op Vernieuwen klikken **om** de lijst met exporttaken bij te werken, zodat de exporttaken worden weergegeven die u hebt gemaakt. Exporttaken hebben dezelfde naam als de bijbehorende zoekopdracht **met _Export** toegevoegd aan de zoeknaam.

7. Klik op de exportklus die u hebt gemaakt om statusgegevens weer te geven op de flyoutpagina. Deze informatie bevat het percentage items dat is overgebracht naar de Azure Storage locatie.

8. Nadat alle items zijn overgedragen, klikt u op **Resultaten downloaden** om de zoekresultaten naar uw lokale computer te downloaden. Zie Stap 2 in Zoekresultaten exporteren voor meer informatie over het downloaden [van zoekresultaten.](export-search-results.md#step-2-download-the-search-results)

## <a name="export-the-results-of-multiple-searches"></a>De resultaten van meerdere zoekopdrachten exporteren

Als alternatief voor het exporteren van de resultaten van één zoekopdracht die aan een zaak is gekoppeld, kunt u de resultaten van meerdere zoekopdrachten exporteren vanuit hetzelfde geval in één exportklus. Het exporteren van de resultaten van meerdere zoekopdrachten gaat sneller en eenvoudiger dan het exporteren van de resultaten één zoekopdracht tegelijk.
  
> [!NOTE]
> U kunt de resultaten van meerdere zoekopdrachten niet exporteren als een van deze zoekopdrachten is geconfigureerd voor zoeklocaties in de wacht.

1. Ga naar en meld u aan met de referenties voor gebruikersaccount die zijn toegewezen aan de juiste [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery-machtigingen.

2. Klik in het linkernavigatiedeelvenster van Microsoft 365 compliancecentrum op Alles weergeven **en** klik vervolgens op **eDiscovery > Core.**

3. Selecteer op **de pagina Core eDiscovery** de zaak waaruit u zoekresultaten wilt exporteren en klik vervolgens op **Zaak openen.**

4. Klik op **de startpagina** voor de zaak op **het tabblad** Zoekopdrachten.
    
5. Schakel in de lijst met zoekopdrachten naar de zaak het selectievakje in naast twee of meer zoekopdrachten waaruit u zoekresultaten wilt exporteren. 

   De **flyoutpagina Bulkacties** wordt weergegeven. 

    ![Klik op de pagina Bulkacties op Resultaten exporteren](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. Klik **op Resultaten exporteren.**

   De **pagina Resultaten exporteren** wordt weergegeven. 

    ![Pagina Resultaten exporteren](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    Op dit moment is de werkstroom voor het exporteren van de resultaten van meerdere zoekopdrachten die zijn gekoppeld aan een Core eDiscovery-zaak hetzelfde als het exporteren van de zoekresultaten voor één zoekopdracht. Zie stap 5 in de vorige sectie.

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>Meer informatie over het exporteren van de resultaten van meerdere zoekopdrachten

- Wanneer u de resultaten van meerdere zoekopdrachten exporteert, worden de zoekquery's uit alle zoekopdrachten gecombineerd met **BEHULP** VAN OF-operatoren en wordt de gecombineerde zoekopdracht gestart. De geschatte resultaten van de gecombineerde zoekopdracht worden weergegeven op de flyoutpagina van de geselecteerde exportklus. De zoekresultaten worden vervolgens gekopieerd naar de Azure Storage locatie in de Microsoft-cloud. De status van de kopieerklus wordt ook weergegeven op de flyoutpagina. Zoals eerder vermeld, kunt u de zoekresultaten downloaden naar een lokale computer nadat alle zoekresultaten zijn gekopieerd.

- Het maximum aantal trefwoorden uit query's voor alle zoekopdrachten die u wilt exporteren, is 500. Dit is dezelfde limiet voor één zoekopdracht. De exportfunctie combineert namelijk alle zoekquery's met behulp van de **operator OF.** Als u deze limiet overschrijdt, wordt een fout geretourneerd. In dit geval moet u de resultaten exporteren uit minder zoekopdrachten of de zoekquery's vereenvoudigen van de oorspronkelijke zoekopdrachten die u wilt exporteren.

- De zoekresultaten die worden geëxporteerd, worden ingedeeld op de inhoudslocatie waarin het item is gevonden. Dit betekent dat op een inhoudslocatie in de exportresultaten items kunnen worden geretourneerd door verschillende zoekopdrachten. Als u bijvoorbeeld kiest voor het exporteren van e-mailberichten in één PST-bestand voor elk postvak, kan het PST-bestand resultaten hebben van meerdere zoekopdrachten.

- Als hetzelfde e-mailitem of hetzelfde document van dezelfde inhoudslocatie wordt geretourneerd door meer dan één van de zoekopdrachten die u exporteert, wordt slechts één kopie van het item geëxporteerd.

- U kunt een export niet bewerken voor meerdere zoekopdrachten nadat u deze hebt aan het maken. U kunt bijvoorbeeld geen zoekopdrachten toevoegen of verwijderen uit de exportfunctie. U moet een exportfunctie maken om te wijzigen welke zoekresultaten worden geëxporteerd. Nadat een exportklus is gemaakt, kunt u de resultaten alleen downloaden naar een computer, de export opnieuw starten of de exportklus verwijderen.

- Als u de export opnieuw start, hebben wijzigingen in de query's van de zoekopdrachten die deel uit maken van de exportklus, geen invloed op de zoekresultaten die worden opgehaald. Wanneer u een export opnieuw start, wordt dezelfde gecombineerde zoekquery-taak uitgevoerd die werd uitgevoerd toen de exportklus werd gemaakt, opnieuw uitgevoerd.

- Als u een export opnieuw start, worden de vorige resultaten overschreven door de zoekresultaten die naar de Azure Storage locatie worden gekopieerd. De vorige resultaten die zijn gekopieerd, zijn niet beschikbaar om te worden gedownload.
