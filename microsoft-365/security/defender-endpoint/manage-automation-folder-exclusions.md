---
title: Uitsluitingen van automatiseringsmappen beheren
description: Voeg uitsluitingen van automatiseringsmappen toe om de bestanden te beheren die zijn uitgesloten van een geautomatiseerd onderzoek.
keywords: manage, automation, exclusion, block, clean, malicious
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 05c103cba051c7d5e7f45e5dd3feb288013ee367
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454815"
---
# <a name="manage-automation-folder-exclusions"></a>Uitsluitingen van automatiseringsmappen beheren 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

Met uitsluitingen van automatiseringsmappen kunt u mappen opgeven die door het geautomatiseerde onderzoek worden overgeslagen. 

U kunt de volgende kenmerken van de map die u wilt overslaan, bepalen:
- Mappen 
- Uitbreidingen van de bestanden
- Bestandsnamen


**Mappen**<br>
U kunt opgeven dat een map en de submappen moeten worden overgeslagen. 


>[!NOTE]
>Op dit moment wordt het gebruik van jokerkaarten als een manier om bestanden onder een adreslijst uit te sluiten nog niet ondersteund. 


**Extensies**<br>
U kunt de extensies opgeven die u wilt uitsluiten in een specifieke adreslijst. De extensies zijn een manier om te voorkomen dat een aanvaller een uitgesloten map gebruikt om een exploit te verbergen. De extensies definiëren expliciet welke bestanden moeten worden genegeerd. 

**Bestandsnamen**<br>
U kunt de bestandsnamen opgeven die u wilt uitsluiten in een specifieke adreslijst. De namen zijn een manier om te voorkomen dat een aanvaller een uitgesloten map gebruikt om een exploit te verbergen. De namen definiëren expliciet welke bestanden moeten worden genegeerd. 



## <a name="add-an-automation-folder-exclusion"></a>Een uitsluiting van automatiseringsmappen toevoegen
1. Selecteer in het navigatiedeelvenster **Instellingen** uitsluitingen van de map  >    >    >  **Regelautomatisering van eindpunten.**  

2. Klik **op Nieuwe mapuitsluiting.**  

3. Voer de mapdetails in:

    - Map
    - Extensies
    - Bestandsnamen
    - Omschrijving

4. Klik op **Opslaan**.

>[!NOTE]
> Opdrachten voor livereactie om uitgesloten bestanden te verzamelen of te onderzoeken, mislukken met de fout: 'Bestand is uitgesloten'. Bovendien worden de uitgesloten items genegeerd door automatisch onderzoek.

## <a name="edit-an-automation-folder-exclusion"></a>Een uitsluiting van automatiseringsmappen bewerken 
1. Selecteer in het navigatiedeelvenster **Instellingen** uitsluitingen van de map  >    >    >  **Regelautomatisering van eindpunten.** 

2. Klik **op Bewerken** op de mapuitsluiting.  

3. Werk de details van de regel bij en klik op **Opslaan.**

## <a name="remove-an-automation-folder-exclusion"></a>Een uitsluiting van automatiseringsmappen verwijderen 
1. Selecteer in het navigatiedeelvenster **Instellingen** uitsluitingen van de map  >    >    >  **Regelautomatisering van eindpunten.**  
2. Klik **op Uitsluiting verwijderen.** 


## <a name="related-topics"></a>Gerelateerde onderwerpen
- [Toegestane/geblokkeerde lijsten voor automatisering beheren](manage-indicators.md)
- [Automatiseringsbestandsuploads beheren](manage-automation-file-uploads.md)
