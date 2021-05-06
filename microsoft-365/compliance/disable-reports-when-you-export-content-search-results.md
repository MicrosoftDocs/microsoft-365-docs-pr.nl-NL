---
title: Rapporten uitschakelen wanneer u inhoudszoekresultaten exporteert
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Bewerk het Windows register op uw lokale computer om rapporten uit te schakelen wanneer u de resultaten van een inhoudszoekactie exporteert vanuit het Beveiligings- & Compliancecentrum.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "52161473"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>Rapporten uitschakelen wanneer u inhoudszoekresultaten exporteert

Wanneer u het hulpprogramma eDiscovery Export gebruikt om de resultaten van een inhoudszoekactie te exporteren in het Beveiligings- & Compliancecentrum, worden met het hulpprogramma automatisch twee rapporten gemaakt en geëxporteerd die aanvullende informatie over de geëxporteerde inhoud bevatten. Deze rapporten zijn het Results.csv en het Manifest.xml-bestand (zie de sectie Veelgestelde vragen over het uitschakelen van [exportrapporten](#frequently-asked-questions-about-disabling-export-reports) in dit onderwerp voor gedetailleerde beschrijvingen van deze rapporten). Omdat deze bestanden erg groot kunnen zijn, kunt u de downloadtijd versnellen en schijfruimte besparen door te voorkomen dat deze bestanden worden geëxporteerd. U kunt dit doen door de Windows register op de computer te wijzigen die u gebruikt om de zoekresultaten te exporteren. Als u de rapporten op een later tijdstip wilt opnemen, kunt u de registerinstelling bewerken. 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>Registerinstellingen maken om de exportrapporten uit te schakelen

Voer de volgende procedure uit op de computer die u gebruikt om de resultaten te exporteren naar een inhoudszoekactie.
  
1. Sluit het hulpprogramma eDiscovery-export als deze is geopend.
    
2. Voer een of beide van de volgende stappen uit, afhankelijk van het exportrapport dat u wilt uitschakelen.
    
    - **Results.csv**
    
      Sla de volgende tekst op in een Windows registerbestand met behulp van een bestandsnaamachtervoegsel van .reg; bijvoorbeeld DisableResultsCsv.reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      Sla de volgende tekst op in een Windows registerbestand met behulp van een bestandsnaamachtervoegsel van .reg; bijvoorbeeld DisableManifestXml.reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. Klik Windows Explorer op het REG-bestand dat u in de vorige stappen hebt gemaakt of dubbelklik erop.
    
4. Klik in het venster Gebruikerstoegangsbeheer op **Ja om** de registereditor de wijziging te laten maken. 
    
5. Klik op Ja wanneer u wordt gevraagd om door te **gaan.**
    
    In de registereditor wordt een bericht weergegeven dat de instelling is toegevoegd aan het register.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Registerinstellingen bewerken om de exportrapporten opnieuw in te stellen

Als u de Results.csv- en Manifest.xml-rapporten hebt uitgeschakeld door de REG-bestanden in de vorige procedure te maken, kunt u deze bestanden bewerken om een rapport opnieuw in te stellen, zodat het wordt geëxporteerd met de zoekresultaten. Voer nogmaals de volgende procedure uit op de computer die u gebruikt om de resultaten te exporteren naar een inhoudszoekactie.
  
1. Sluit het hulpprogramma eDiscovery-export als deze is geopend.
    
2. Bewerk een of beide .reg-bestanden die u in de vorige procedure hebt gemaakt.
    
    - **Results.csv**
    
        Open het bestand DisableResultsCsv.reg in Kladblok, wijzig de waarde in `False` en sla het bestand `True` op. Nadat u het bestand hebt bewerkt, ziet het er bijvoorbeeld als volgende uit:
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        Open het bestand DisableManifestXml.reg in Kladblok, wijzig de waarde in `False` en sla het bestand `True` op. Nadat u het bestand hebt bewerkt, ziet het er bijvoorbeeld als volgende uit:
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. Klik Windows Explorer op een REG-bestand dat u in de vorige stap hebt bewerkt of dubbelklikt.
    
4. Klik in het venster Gebruikerstoegangsbeheer op **Ja om** de registereditor de wijziging te laten maken. 
    
5. Klik op Ja wanneer u wordt gevraagd om door te **gaan.**
    
    In de registereditor wordt een bericht weergegeven dat de instelling is toegevoegd aan het register.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Veelgestelde vragen over het uitschakelen van exportrapporten

 **Wat zijn de Results.csv en Manifest.xml rapporten?**
  
De Results.csv en Manifest.xml bevatten aanvullende informatie over de inhoud die is geëxporteerd.
  
- **Results.csv** Een Excel document met informatie over elk item dat als zoekresultaat wordt gedownload. Voor e-mail bevat het resultatenlogboek informatie over elk bericht, waaronder: 
    
  - De locatie van het bericht in het bronpostvak (inclusief of het bericht zich in het primaire of archiefpostvak bevindt).
    
  - De datum waarop het bericht is verzonden of ontvangen.
    
  - De onderwerpregel van het bericht.
    
  - De afzender en geadresseerden van het bericht.
    
  - Of het bericht een duplicaatbericht is als u de-duplicatie hebt ingeschakeld bij het exporteren van de zoekresultaten. Dubbele berichten hebben een waarde in de kolom **Bovenliggend itemid** die het bericht als een duplicaat identificeert. De waarde in de **kolom Bovenliggende item-id** is hetzelfde als de waarde in de **kolom ItemDocumentId** van het bericht dat is geëxporteerd. 
    
    Voor documenten van SharePoint en OneDrive voor Bedrijven sites bevat het resultatenlogboek informatie over elk document, waaronder:
    
  - De URL voor het document.
    
  - De URL voor de siteverzameling waar het document zich bevindt.
    
  - De datum waarop het document voor het laatst is gewijzigd.
    
  - De naam van het document (dat zich in de kolom Onderwerp in het resultatenlogboek bevindt).
    
- **Manifest.xml** Een manifestbestand (in XML-indeling) dat informatie bevat over elk item dat in de zoekresultaten wordt opgenomen. De informatie in dit rapport is hetzelfde als het Results.csv rapport, maar is in de indeling die is opgegeven door het EDRM (Electronic Discovery Reference Model). Voor meer informatie over EDRM gaat u naar [https://www.edrm.net](https://www.edrm.net) .
    
 **Wanneer moet ik het exporteren van deze rapporten uitschakelen?**
  
Dit hangt af van uw specifieke behoeften. Veel organisaties hebben geen aanvullende informatie over zoekresultaten nodig en hebben deze rapporten niet nodig.
  
 **Op welke computer moet ik dit doen?**
  
 U moet de registerinstelling wijzigen op een lokale computer waar u het hulpprogramma eDiscovery-export op uitvoert. 
  
 **Moet ik de computer opnieuw starten nadat ik deze instelling heb gewijzigd?**
  
Nee, u hoeft de computer niet opnieuw op te starten. Maar als het hulpprogramma eDiscovery-export wordt uitgevoerd, moet u het programma sluiten en opnieuw starten nadat u de registerinstelling hebt gewijzigd.
  
 **Wordt een bestaande registersleutel bewerkt of wordt er een nieuwe sleutel gemaakt?**
  
De eerste keer dat u het REG-bestand dat u in de procedure in dit onderwerp hebt gemaakt, wordt een nieuwe registersleutel gemaakt. Vervolgens wordt de instelling telkens bewerkt wanneer u het .reg-bewerkingsbestand wijzigt en opnieuw uitwerkt.
