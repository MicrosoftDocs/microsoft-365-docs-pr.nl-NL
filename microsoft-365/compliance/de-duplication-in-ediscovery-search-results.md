---
title: De-duplicatie in de zoekresultaten van eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
ms.custom:
- seo-marvel-apr2020
description: Lees hoe u dubbele eDiscovery-zoekresultaten verwijdert, zodat slechts één kopie van een e-mailbericht wordt geëxporteerd.
ms.openlocfilehash: 859c1c41a9f6a530cdefce5220039fbc6ba1a14e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162108"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>De-duplicatie in de zoekresultaten van eDiscovery

In dit artikel wordt beschreven hoe het de-dupliceren van eDiscovery-zoekresultaten werkt en worden de beperkingen van het algoritme voor de duplicatie beschreven.
  
Wanneer u eDiscovery-hulpprogramma's gebruikt om de resultaten van een eDiscovery-zoekopdracht te exporteren, hebt u de optie om de geëxporteerde resultaten te de-dupliceren. Wat betekent dit? Wanneer u de-duplicatie inschakelen (standaard is de-duplicatie niet ingeschakeld), wordt slechts één kopie van een e-mailbericht geëxporteerd, ook al zijn er mogelijk meerdere exemplaren van hetzelfde bericht gevonden in de postvakken die zijn doorzocht. De-duplicatie helpt u tijd te besparen door het aantal items te verminderen dat u moet controleren en analyseren nadat de zoekresultaten zijn geëxporteerd. Maar het is belangrijk om te begrijpen hoe de-duplicatie werkt en er rekening mee te houden dat er beperkingen zijn aan het algoritme, zodat een uniek item tijdens het exportproces als een duplicaat kan worden gemarkeerd.
  
## <a name="how-duplicate-messages-are-identified"></a>Hoe dubbele berichten worden geïdentificeerd

eDiscovery-hulpprogramma's gebruiken een combinatie van de volgende e-maileigenschappen om te bepalen of een bericht een duplicaat is:
  
- **InternetMessageId:** met deze eigenschap wordt de internetberichtaanduiding van een e-mailbericht opgegeven, een globaal unieke id die verwijst naar een specifieke versie van een specifiek bericht. Deze id wordt gegenereerd door het e-mailclientprogramma van de afzender of het host-e-mailsysteem dat het bericht verzendt. Als een persoon een bericht naar meer dan één geadresseerde verzendt, is de internetbericht-id hetzelfde voor elk exemplaar van het bericht. Volgende revisies van het oorspronkelijke bericht ontvangen een andere berichtaanduiding. 

- **ConversationTopic** - Met deze eigenschap wordt het onderwerp opgegeven van de gespreksthread van een bericht. De waarde van de **eigenschap ConversationTopic** is de tekenreeks die het algemene onderwerp van het gesprek beschrijft. Een bewaring bestaat uit een eerste bericht en alle berichten die worden verzonden als antwoord op het eerste bericht. Berichten in hetzelfde gesprek hebben dezelfde waarde voor de **eigenschap ConversationTopic.** De waarde van deze eigenschap is meestal de onderwerpregel van het eerste bericht dat het gesprek heeft voortgebracht. 

- **BodyTagInfo** - Dit is een interne Exchange store-eigenschap. De waarde van deze eigenschap wordt berekend door verschillende kenmerken in de body van het bericht te controleren. Deze eigenschap wordt gebruikt om verschillen in de tekst van berichten te identificeren. 

Tijdens het eDiscovery-exportproces worden deze drie eigenschappen vergeleken voor elk bericht dat voldoet aan de zoekcriteria. Als deze eigenschappen identiek zijn voor twee (of meer) berichten, worden deze berichten als duplicaten bepaald en is het resultaat dat slechts één kopie van het bericht wordt geëxporteerd als de duplicatie is ingeschakeld. Het bericht dat wordt geëxporteerd, wordt het 'bronitem' genoemd. Informatie over dubbele berichten wordt opgenomen in de **Results.csv** en **Manifest.xml** rapporten die zijn opgenomen in de geëxporteerde zoekresultaten. In het **Results.csv** wordt een duplicaatbericht geïdentificeerd met een waarde in de kolom **Dupliceren naar** item. De waarde in deze kolom komt overeen met de waarde in de **kolom Itemidentiteit** voor het bericht dat is geëxporteerd. 
  
In de volgende afbeeldingen wordt weergegeven  hoe dubbele berichten worden weergegeven in deResults.csven **Manifest.xml** die met de zoekresultaten worden geëxporteerd. Deze rapporten bevatten niet de e-maileigenschappen die eerder zijn beschreven, die worden gebruikt in het algoritme voor de duplicatie. In plaats daarvan bevatten de rapporten de **eigenschap Itemidentiteit** die is toegewezen aan items door de Exchange store. 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Results.csv rapport (bekeken in Excel)
  
![Informatie weergeven over dubbele items in het Results.csv rapport](../media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Manifest.xml rapport (bekeken in Excel)
  
![Informatie weergeven over dubbele items in het Manifest.xml rapport](../media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
Daarnaast worden andere eigenschappen van dubbele berichten opgenomen in de exportrapporten. Dit geldt ook voor het postvak waarin het dubbele bericht zich bevindt, of het bericht is verzonden naar een distributiegroep en of het bericht CC'd of BCC'd was naar een andere gebruiker.
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>Beperkingen van het algoritme voor de duplicatie

Er zijn enkele bekende beperkingen van het algoritme voor de duplicatie, zodat unieke items als duplicaten kunnen worden gemarkeerd. Het is belangrijk om deze beperkingen te begrijpen, zodat u kunt bepalen of u de optionele deplicatiefunctie al dan niet wilt gebruiken.
  
Er is één situatie waarbij de functie voor de duplicatie een bericht mogelijk per ongeluk als een duplicaat identificeert en niet exporteert (maar het bericht nog steeds als een duplicaat in de exportrapporten noemt). Dit zijn berichten die een gebruiker bewerkt, maar niet verzendt. Stel dat een gebruiker een bericht in Outlook selecteert, de inhoud van het bericht kopieert en het vervolgens in een nieuw bericht plakt. Vervolgens wijzigt de gebruiker een van de kopieën door een bijlage te verwijderen of toe te voegen, of door de onderwerpregel of de body zelf te wijzigen. Als deze twee berichten overeenkomen met de query van een eDiscovery-zoekopdracht, wordt slechts één van de berichten geëxporteerd als de duplicatie is ingeschakeld wanneer de zoekresultaten worden geëxporteerd. Dus hoewel het oorspronkelijke bericht of het gekopieerde bericht is gewijzigd, zijn geen van de gewijzigde berichten verzonden en zijn daarom de waarden van de eigenschappen **InternetMessageId,** **ConversationTopic** en **BodyTagInfo** niet bijgewerkt. Maar zoals eerder is uitgelegd, worden beide berichten weergegeven in de exportrapporten 
  
Unieke berichten kunnen ook worden gemarkeerd als duplicaten wanneer de functie Paginabeveiliging kopiëren-op-schrijven is ingeschakeld, zoals in het geval van een postvak dat in de wacht- of In-Place staat. De functie Kopiëren op schrijven kopieert het oorspronkelijke bericht (en slaat het op in de map Versies van de map Herstelbare items van de gebruiker) voordat de revisie naar het oorspronkelijke item wordt opgeslagen. In dit geval kunnen de gewijzigde kopie en het oorspronkelijke bericht (in de map Herstelbare items) worden beschouwd als dubbele berichten, waardoor slechts één van deze berichten wordt geëxporteerd.
  
> [!IMPORTANT]
> Als de beperkingen van het algoritme voor de duplicatie van invloed kunnen zijn op de kwaliteit van uw zoekresultaten, moet u de-duplicatie niet inschakelen wanneer u items exporteert. Als de situaties die in deze sectie worden beschreven, waarschijnlijk geen factor in uw zoekresultaten zijn en u het aantal items dat het waarschijnlijkst duplicaten zal zijn, wilt verminderen, moet u overwegen de duplicatie in te stellen. 
  
## <a name="more-information"></a>Meer informatie

- De informatie in dit artikel is van toepassing bij het exporteren van zoekresultaten met behulp van een van de volgende eDiscovery-hulpprogramma's:

  - Zoeken naar inhoud in compliancecentrum in Office 365

  - In-Place eDiscovery in Exchange Online

  - Het eDiscovery-centrum in SharePoint Online

- Zie voor meer informatie over het exporteren van zoekresultaten:

  - [Inhoud zoeken exporteren](export-search-results.md)

  - [Een inhoudszoekrapport exporteren](export-a-content-search-report.md)

  - [De In-Place eDiscovery exporteren naar een PST-bestand](/exchange/security-and-compliance/in-place-ediscovery/export-search-results)

  - [Inhoud exporteren en rapporten maken in het eDiscovery-centrum](/SharePoint/governance/export-content-and-create-reports-in-the-ediscovery-center)