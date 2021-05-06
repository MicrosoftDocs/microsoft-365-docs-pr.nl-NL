---
title: De grootte van PST-bestanden wijzigen bij het exporteren van eDiscovery-zoekresultaten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: U kunt de standaardgrootte wijzigen van PST-bestanden die naar uw computer worden gedownload wanneer u eDiscovery-zoekresultaten exporteert.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "52161451"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>De grootte van PST-bestanden wijzigen bij het exporteren van eDiscovery-zoekresultaten

Wanneer u het hulpprogramma eDiscovery Export gebruikt om de e-mailresultaten van een eDiscovery-zoekopdracht te exporteren vanuit de verschillende Microsoft eDiscovery-hulpprogramma's, is de standaardgrootte van een PST-bestand dat kan worden geëxporteerd 10 GB. Als u deze standaardgrootte wilt wijzigen, kunt u het register Windows bewerken op de computer die u gebruikt om de zoekresultaten te exporteren. Een van de redenen hiervoor is dat een PST-bestand kan passen op verwisselbare media, zoals een dvd, een compacte schijf of een USB-station. 
  
> [!NOTE]
> Het hulpprogramma eDiscovery-export wordt gebruikt om de zoekresultaten te exporteren wanneer u het hulpprogramma Inhoud zoeken gebruikt in het Beveiligings- & Compliancecentrum, In-Place eDiscovery in Exchange Online en het eDiscovery-centrum in SharePoint Online.
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Een registerinstelling maken om de grootte van PST-bestanden te wijzigen wanneer u eDiscovery-zoekresultaten exporteert

Voer de volgende procedure uit op de computer die u gebruikt om de resultaten van een eDiscovery-zoekopdracht te exporteren.
  
1. Sluit het hulpprogramma eDiscovery-export als deze is geopend. 
    
2. Sla de volgende tekst op in een registerbestand van venster met een achtervoegsel van .reg; bijvoorbeeld PstExportSize.reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    In het bovenstaande voorbeeld wordt de waarde ingesteld op  `PstSizeLimitInBytes` 1.073.741.824 bytes of ongeveer 1 GB. Hier zijn enkele andere voorbeeldwaarden voor de  `PstSizeLimitInBytes` instelling. 
    
    |**Grootte in GB (ca.**|**Grootte in bytes**|
    |:-----|:-----|
    |0,7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Wijzig de `PstSizeLimitInBytes` waarde in de gewenste maximale grootte van een PST-bestand wanneer u zoekresultaten exporteert en sla het bestand vervolgens op. 
    
4. Klik Windows Explorer op het REG-bestand dat u in de vorige stappen hebt gemaakt of dubbelklik erop.
    
5. Klik in het venster Gebruikerstoegangsbeheer op **Ja om** de registereditor de wijziging te laten maken. 
    
6. Klik op Ja wanneer u wordt gevraagd om door te **gaan.**
    
    In de registereditor wordt een bericht weergegeven dat de instelling is toegevoegd aan het register.
    
7. U kunt stap 3 tot en met 6 herhalen om de waarde voor de registerinstelling  `PstSizeLimitInBytes` te wijzigen. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Veelgestelde vragen over het wijzigen van de standaardgrootte van PST-bestanden wanneer u eDiscovery-zoekresultaten exporteert

 **Waarom is de standaardgrootte 10 GB?**
  
De standaardgrootte van 10 GB is gebaseerd op feedback van klanten. 10 GB is een goede balans tussen de optimale hoeveelheid inhoud in één PST en met een minimale kans op bestandscorruptie.
  
 **Moet ik de standaardgrootte van PST-bestanden vergroten of verlagen?**
  
Klanten hebben de neiging om de groottelimiet te verlagen, zodat de zoekresultaten passen op verwisselbare media die ze fysiek naar andere locaties in hun organisatie kunnen verzenden. U wordt niet aangeraden de standaardgrootte te vergroten, omdat PST-bestanden groter dan 10 GB mogelijk beschadigingsproblemen hebben.
  
 **Op welke computer moet ik dit doen?**
  
U moet de registerinstelling wijzigen op een lokale computer waar u het hulpprogramma eDiscovery-export op hebt uitgevoerd.
  
 **Moet ik de computer opnieuw opstarten nadat ik deze instelling heb gewijzigd?**
  
Nee, u hoeft de computer niet opnieuw op te starten. Maar als het hulpprogramma voor eDiscovery-export wordt uitgevoerd, moet u het programma sluiten en opnieuw starten nadat u deze instelling hebt gewijzigd.
  
 **Wordt een bestaande registersleutel bewerkt of wordt er een nieuwe sleutel gemaakt?**
  
De eerste keer dat u het REG-bestand dat u in deze procedure hebt gemaakt, wordt een nieuwe registersleutel gemaakt. Vervolgens wordt de instelling telkens bewerkt wanneer u het .reg-bewerkingsbestand wijzigt en opnieuw uitwerkt.
