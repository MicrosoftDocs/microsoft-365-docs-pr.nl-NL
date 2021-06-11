---
title: Voorbeelden van opdrachten voor Live-reacties
description: Lees hoe u eenvoudige of geavanceerde opdrachten voor livereacties voor Microsoft Defender voor Eindpunt kunt uitvoeren en voorbeelden kunt zien over hoe het wordt gebruikt.
keywords: voorbeeld, command, cli, remote, shell, connection, live, response, real-time, command, script, remediate, hunt, export, log, drop, download, file
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
ms.openlocfilehash: 389d9ad4a3e5fc876e7bded89389202e95bfda45
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879118"
---
# <a name="live-response-command-examples"></a>Voorbeelden van opdrachten voor Live-reacties

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Lees meer over veelgebruikte opdrachten die worden gebruikt in livereacties en zie voorbeelden van hoe ze gewoonlijk worden gebruikt.

Afhankelijk van de rol die aan u is verleend, kunt u eenvoudige of geavanceerde opdrachten voor livereacties uitvoeren. Zie Entiteiten onderzoeken op apparaten met livereactie voor meer informatie over basis- en [geavanceerde opdrachten.](live-response.md)


## <a name="analyze"></a>analyseren 

```console
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```console
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a>verbindingen

```console
# List active connections in json format using parameter name
connections -output json
```

```console
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a>dir

```console
# List files and sub-folders in the current folder
dir
```

```console
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```console
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a>fileinfo

```console
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a>findfile

```console
# Find file by name
findfile test.txt
```

## <a name="getfile"></a>getfile

```console
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```console
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> De volgende **bestandstypen kunnen niet** worden gedownload met deze opdracht vanuit Live Response:
>
> * [Reparse point-bestanden](/windows/desktop/fileio/reparse-points/)
> * [Spaarzame bestanden](/windows/desktop/fileio/sparse-files/)
> * Bestanden leeg maken
> * Virtuele bestanden of bestanden die niet volledig lokaal aanwezig zijn
>
> Deze **bestandstypen worden** ondersteund door [PowerShell.](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true)
>
> Gebruik PowerShell als alternatief als u problemen hebt met het gebruik van deze opdracht vanuit Live Response.

## <a name="processes"></a>processen
```console
# Show all processes
processes
```

```console
# Get process by pid
processes 123
```

```console
# Get process by pid with argument name
processes -pid 123
```

```console
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a>putfile

```console
# Upload file from library
putfile get-process-by-name.ps1
```

```console
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```console
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a>register

```console
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```console
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a>herstel

```console
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```console
# Remediate process with specific PID
remediate process 7960
```

```console
# See list of all remediated entities
remediate list
```

## <a name="run"></a>uitvoeren

```console
# Run PowerShell script from the library without arguments
run script.ps1
```

```console
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```
>[!NOTE]
>
> Voor opdrachten die lang worden uitgevoerd, zoals **'uitvoeren'** of **'getfile',** kunt u het symbool ' ' aan het einde van de opdracht gebruiken om die actie op de achtergrond uit **&** te voeren.
> Op deze manier kunt u de computer blijven onderzoeken en terugkeren naar de achtergrondopdracht wanneer u klaar bent met de **basisopdracht 'fg'.** [](live-response.md#basic-commands)
>
## <a name="scheduledtask"></a>scheduledtask

```console
# Get all scheduled tasks
scheduledtasks
```

```console
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```


## <a name="undo"></a>ongedaan maken

```console
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```console
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```


## <a name="library"></a>bibliotheek

```console
# List files in the library
library
```

```console
# Delete a file from the library
library delete script.ps1
```
