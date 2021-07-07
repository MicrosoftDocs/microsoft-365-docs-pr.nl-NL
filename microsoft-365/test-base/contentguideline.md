---
title: Richtlijnen voor testpakketten
description: De richtlijnen rond testpakket bekijken
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322757"
---
# <a name="test-package-guidelines"></a>Richtlijnen voor testpakketten

## <a name="1---script-referencing"></a>1. Referencing van scripts

Wanneer u een .zip naar de portal uploadt, wordt alle inhoud van dat bestand in een hoofdmap opgeslagen. U hoeft geen code te schrijven om deze eerste bewerking uit te voeren. U kunt ook verwijzen naar een bestand in de .zip met behulp van het pad ten opzichte van het zip-bestand dat is geüpload.

In het onderstaande voorbeeld laten we zien hoe u vanuit het invoerveld op het tabblad Taken naar uw binaries/scripts kunt verwijzen. De tekst in blauw moet zonder aanhalingstekens worden ingevoerd in het **veld** **Scriptpad.**

Het is belangrijk dat u op de hoogte bent van de inhoud in het zip-bestand voordat u deze uploadt. Vaak maakt uw lokale computer een hoofdmap onder het zip-bestand wanneer u een map omsingelt. In dit geval wordt de verwijzing weergegeven in vet **hieronder:**

 **Contoso_App_Folder.zip**
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**
  - Script.ps1 – **"Contoso_App_Folder/map1/script.ps1"**

In andere tijden staan uw bestanden of inhoud mogelijk onder het zip-bestand, dat wil zeggen geen map op het tweede niveau:

 **Zip_file_uploaded.zip**
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - ScriptX.ps1 – **'ScriptX.ps1'**
  - Script.ps1 - **'map1/script.ps1'**
  
## <a name="2---script-execution"></a>2. Scriptuitvoering

**Out-of-Box-tests:** Het toepassingspakket moet ten minste drie PowerShell-scripts bevatten die onbeheerd het installeren, starten en sluiten van de toepassing en de afhankelijkheden ervan uitvoeren. Elk script moet het controleren van zijn eigen vereisten afhandelen, het valideren van het is gelukt, evenals het opruimen na zichzelf (indien nodig).

**Functionele tests:** Het toepassingspakket moet ten minste één PowerShell-script bevatten. Wanneer meer dan één script wordt geleverd, worden de scripts uitgevoerd in de uploadreeks en wordt het uitvoeren van de volgende scripts door een fout in een bepaald script gestopt.

### <a name="script-requirements"></a>Scriptvereisten

• PowerShell versie 5.1+     

• Onbeheerde uitvoering    

• Foutmeldingscode               

• Succes valideren            

• Logboekregistratie voor een specifieke logboekmap

Elk script moet volledig onbeheerd worden uitgevoerd om de testpijplijn uit te voeren.

> [!Note]
> Scripts moeten '0' retourneren bij geslaagde voltooiing en een foutcode zonder nul als er een fout optreedt tijdens de uitvoering.

Elk script moet valideren dat het is uitgevoerd. Bijvoorbeeld. het installatiescript moet controleren op het bestaan van bepaalde binaries en/of registersleutels op het systeem, nadat de binaire installatie is uitgevoerd om er met een redelijke mate van vertrouwen voor te zorgen dat de installatie is geslaagd. 

Dit is nodig om goed te kunnen vaststellen waar fouten optreden tijdens een test, bijvoorbeeld niet in staat om de toepassing te installeren of om de toepassing niet te kunnen starten.

> [!Important]
> **Vermijd het volgende:** Scripts moeten de computer niet opnieuw opstarten, als een herstart noodzakelijk is, moet u dit opgeven tijdens het uploaden van uw scripts.

## <a name="3---log-collection"></a>3. Logboekverzameling

Elk script moet alle logboeken die het genereert, uitvoeren in een map met de naam ```logs``` . Alle mappen in de map met de naam worden gekopieerd en ```logs``` gepresenteerd om te worden gedownload op de ```Test Results``` pagina.

Met het installatiescript (dat zich mogelijk in de **map App/scripts/install** bevindt) kunnen de logboeken bijvoorbeeld worden uitgevoerd naar: **logs/install.log,** zodat het uiteindelijke logboek zich bevindt op: **Apps/scripts/install/logs/install.log.**

Het systeem haalt het bestand samen met andere bestanden in andere mappen op en colleert het om ```install.log``` ```logs``` het te downloaden.


## <a name="4---application-binaries"></a>4. Toepassings binaries

Binaries en afhankelijkheden moeten worden opgenomen in het enkele zip-bestand. 

Deze moeten alle benodigde gegevens bevatten voor de installatie van de toepassing (bijvoorbeeld het installatieprogramma van de toepassing); als de toepassing afhankelijk is van frameworks, zoals .NET Core/Standard of .NET Framework, moeten deze in het bestand worden opgenomen en correct worden verwezen in de meegeleverde scripts.


> [!Note]
> Het geüploade zip-bestand mag geen spaties of speciale tekens in de naam hebben

## <a name="next-steps"></a>Volgende stappen

Naar het volgende artikel gaan om enkele veelgestelde vragen **(veelgestelde vragen) weer te geven**
> [!div class="nextstepaction"]
> [Volgende stap](faq.md)
