---
title: Problemen met AzCopy oplossen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Problemen met Azure AzCopy oplossen bij het laden van niet-Office 365 gegevens voor foutsanering in Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161958"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Problemen met AzCopy oplossen in Advanced eDiscovery

Wanneer u niet-Microsoft 365-gegevens of documenten laadt voor foutsanering in Advanced eDiscovery, levert de gebruikersinterface een Azure AzCopy-opdracht die parameters bevat met de locatie waar de bestanden die u wilt uploaden zijn opgeslagen en de Azure-opslaglocatie waar de bestanden naar worden geüpload. Als u uw documenten wilt uploaden, kopieert u deze opdracht en voer u deze uit in een opdrachtprompt op uw lokale computer.  In de volgende schermafbeelding ziet u een voorbeeld van een AzCopy-opdracht:

![Upload niet-Microsoft 365 bestanden](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

Meestal werkt de opdracht die wordt geleverd wanneer u deze uitwerkt. Er kunnen echter gevallen zijn waarin de weergegeven opdracht niet wordt uitgevoerd. Hier zijn een paar mogelijke redenen.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>De ondersteunde versie van AzCopy is niet geïnstalleerd op de lokale computer

Op dit moment moet u AzCopy v8.1 gebruiken om niet-Microsoft 365 gegevens in Advanced eDiscovery. De opdracht AzCopy die wordt weergegeven op de **pagina Upload** bestanden die in de vorige schermafbeelding wordt weergegeven, geeft een fout als u AzCopy v8.1 niet gebruikt. Zie Gegevens overbrengen met [de AzCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)op Windows .

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy is niet geïnstalleerd op de lokale computer of niet op de standaardlocatie

Als AzCopy niet is geïnstalleerd of is geïnstalleerd op een andere locatie dan de standaardlocatie voor installeren (dat wil zeggen), wordt mogelijk de volgende fout weergegeven wanneer u de `%ProgramFiles(x86)%` opdracht AzCopy uit te voeren:

> Het systeem kan het opgegeven pad niet vinden.

Als AzCopy niet is geïnstalleerd op de lokale computer, vindt u installatiegegevens in Gegevens overbrengen met [de AzCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)op Windows. Installeer deze op de standaardlocatie.

Als AzCopy is geïnstalleerd, maar deze is geïnstalleerd op een andere locatie dan de standaardlocatie, kunt u de opdracht kopiëren, plakken in een tekstbestand en vervolgens het pad wijzigen naar de locatie waar AzCopy is geïnstalleerd. Als Azcopy zich bijvoorbeeld in bevindt, kunt u het eerste deel van de `%ProgramFiles%` opdracht wijzigen in `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` . Nadat u deze wijziging hebt gemaakt, kopieert u deze uit het tekstbestand en voer u de opdrachtprompt uit.

> [!TIP]
> Als AzCopy is geïnstalleerd op een andere locatie dan de standaardinstallatielocatie, kunt u overwegen deze te verwijderen en vervolgens opnieuw te installeren op de standaardlocatie. Dit helpt dit probleem in de toekomst te voorkomen.