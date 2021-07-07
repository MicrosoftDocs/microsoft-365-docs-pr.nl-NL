---
title: Testtaken instellen
description: Testtaken instellen
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
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322560"
---
# <a name="step-4-the-tasks-tab"></a>Stap 4: het tabblad Taken

Op het tabblad Taken worden de paden naar de testscripts verwacht in de zipmap die u hebt geüpload onder het tabblad Binaries.

  - **Out-of-box testscripts:** Typ de relatieve paden naar uw installatie, start, sluit en verwijder scripts. U hebt ook de optie om extra instellingen voor het installatiescript te selecteren.
  - **Functionele testscripts:** Typ het relatieve pad naar elk functioneel testscript dat is geüpload. U kunt extra functionele testscripts toevoegen met behulp van de ```Add Script``` knop. U hebt minimaal één (1) script nodig en kunt maximaal acht (8) functionele testscripts toevoegen. 
  
    De scripts worden in de volgorde van uploaden uitgevoerd en een fout in een bepaald script stopt met het uitvoeren van de volgende scripts.
    U hebt ook de optie om extra instellingen voor elk script te selecteren.

## <a name="set-script-path"></a>Scriptpad instellen

![Afbeelding van testtaak](Media/testtask.png)

Voorbeeld van het geven van het relatieve pad in een mapstructuur vindt u hieronder:

_**Zip_file_uploaded**_
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - **ScriptX.ps1** zou hebben. _ScriptX.ps1_ als het relatieve pad.
  - **Script.ps1** _map1/script.ps1als_ het relatieve pad.


## <a name="next-steps"></a>Volgende stappen

Details van het tabblad Testopties weergeven in het volgende artikel 
> [!div class="nextstepaction"]
> [Volgende stap](testoptions.md)
