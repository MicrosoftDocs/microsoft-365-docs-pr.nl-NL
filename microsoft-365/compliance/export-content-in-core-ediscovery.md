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
description: Hier wordt beschreven hoe u inhoud exporteert en downloadt vanuit een hoofd-eDiscovery-zaak in Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310840"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>Inhoud exporteren uit een hoofd-eDiscovery-zaak

Nadat een zoekopdracht is uitgevoerd die is gekoppeld aan een Core eDiscovery-zaak, kunt u de zoekresultaten exporteren. Wanneer u zoekresultaten exporteert, worden postvakitems gedownload in PST-bestanden of als afzonderlijke berichten. Wanneer u inhoud exporteert van SharePoint en OneDrive voor Bedrijven sites, worden kopieën van Office documenten en andere documenten geëxporteerd. Een Results.csv bestand met informatie over elk item dat wordt geëxporteerd en een manifestbestand (in XML-indeling) dat informatie bevat over elk zoekresultaat, wordt ook geëxporteerd.
  
## <a name="export-search-results"></a>Zoekresultaten exporteren

1. Ga naar en meld u aan met de referenties voor gebruikersaccount die zijn toegewezen aan de juiste [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery-machtigingen.

2. Klik in het linkernavigatiedeelvenster van Microsoft 365 compliancecentrum op Alles weergeven **en** klik vervolgens op **eDiscovery > Core.**

3. Klik op **de pagina Core eDiscovery** op de naam van de zaak waarin u de wacht wilt houden.

4. Klik op **de startpagina** voor de zaak op **het tabblad** Zoekopdrachten.

5. Klik in **het** menu Acties onder aan de flyoutpagina op **Resultaten exporteren.**

   ![Optie Resultaten exporteren in het menu Acties](../media/ActionMenuExportResults.png)

   De werkstroom voor het exporteren van de resultaten van een zoekopdracht die is gekoppeld aan een Hoofd eDiscovery-zaak, is hetzelfde als het exporteren van de zoekresultaten voor een zoekopdracht op de pagina **Inhoud zoeken.** Zie Zoekresultaten voor inhoud exporteren voor [stapsgewijse instructies.](export-search-results.md)

   > [!NOTE]
   > Wanneer u zoekresultaten exporteert, kunt u de-duplicatie inschakelen, zodat slechts één kopie van een e-mailbericht wordt geëxporteerd, ook al zijn er mogelijk meerdere exemplaren van hetzelfde bericht gevonden in de postvakken die zijn doorzocht. Zie [De-duplicatie in eDiscovery-zoekresultaten](de-duplication-in-ediscovery-search-results.md)voor meer informatie over de-duplicatie en hoe dubbele items worden geïdentificeerd.

   Nadat u de export hebt gestart, worden de zoekresultaten voorbereid voor het downloaden, wat betekent dat ze worden overgebracht naar een door Microsoft verstrekte Azure Storage locatie in de Microsoft-cloud.
  
6. Klik op **het tabblad** Export in de zaak om de lijst met exporttaken weer te geven.
  
   ![Taken exporteren op het tabblad Exporteren in hoofd-eDiscovery-zaak](../media/CoreeDiscoveryExport.png)

   Mogelijk moet u op Vernieuwen klikken **om** de lijst met exporttaken bij te werken, zodat de exporttaken worden weergegeven die u hebt gemaakt. Exporttaken hebben dezelfde naam als de bijbehorende zoekopdracht **met _Export** toegevoegd aan de zoeknaam.

7. Klik op de exportklus die u hebt gemaakt om statusgegevens weer te geven op de flyoutpagina. Deze informatie bevat het percentage items dat is overgebracht naar de Azure Storage locatie.

8. Nadat alle items zijn overgedragen, klikt u op **Resultaten downloaden** om de zoekresultaten naar uw lokale computer te downloaden. Zie Stap 2 in Zoekresultaten exporteren voor meer informatie over het downloaden [van zoekresultaten.](export-search-results.md#step-2-download-the-search-results)

### <a name="more-information-about-exporting-searches-from-a-case"></a>Meer informatie over het exporteren van zoekopdrachten vanuit een zaak

- Zie Een inhoudszoekrapport exporteren voor meer informatie over de exportbestanden die zijn opgenomen wanneer u zoekresultaten [exporteert.](export-a-content-search-report.md#whats-included-in-the-report)

- Als u de export opnieuw start, hebben wijzigingen in de query's van de zoekopdrachten die deel uit maken van de exportklus, geen invloed op de zoekresultaten die worden opgehaald. Wanneer u een export opnieuw start, wordt dezelfde gecombineerde zoekquery-taak uitgevoerd die werd uitgevoerd toen de exportklus werd gemaakt, opnieuw uitgevoerd.

- Als u een export opnieuw start, worden de vorige resultaten overschreven door de zoekresultaten die naar de Azure Storage locatie worden gekopieerd. De vorige resultaten die zijn gekopieerd, zijn niet beschikbaar om te worden gedownload.
