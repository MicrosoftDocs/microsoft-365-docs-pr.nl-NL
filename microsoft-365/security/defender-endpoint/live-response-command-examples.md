---
title: Voorbeelden van livereactieopdracht
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
ms.openlocfilehash: b25712e331597dc38d3f1cf98fdf70886406432e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059714"
---
# <a name="live-response-command-examples"></a><span data-ttu-id="2c15e-104">Voorbeelden van livereactieopdracht</span><span class="sxs-lookup"><span data-stu-id="2c15e-104">Live response command examples</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2c15e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2c15e-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c15e-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c15e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2c15e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c15e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2c15e-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="2c15e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2c15e-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="2c15e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="2c15e-110">Lees meer over veelgebruikte opdrachten die worden gebruikt in livereacties en zie voorbeelden van hoe ze gewoonlijk worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2c15e-110">Learn about common commands used in live response and see examples on how they are typically used.</span></span>

<span data-ttu-id="2c15e-111">Afhankelijk van de rol die aan u is verleend, kunt u eenvoudige of geavanceerde opdrachten voor livereacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2c15e-111">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="2c15e-112">Zie Entiteiten onderzoeken op apparaten met livereactie voor meer informatie over basis- en [geavanceerde opdrachten.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="2c15e-112">For more information on basic and advanced commands, see [Investigate entities on devices using live response](live-response.md).</span></span>


## <a name="analyze"></a><span data-ttu-id="2c15e-113">analyseren</span><span class="sxs-lookup"><span data-stu-id="2c15e-113">analyze</span></span> 

```
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a><span data-ttu-id="2c15e-114">verbindingen</span><span class="sxs-lookup"><span data-stu-id="2c15e-114">connections</span></span>

```
# List active connections in json format using parameter name
connections -output json
```

```
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a><span data-ttu-id="2c15e-115">dir</span><span class="sxs-lookup"><span data-stu-id="2c15e-115">dir</span></span>

```
# List files and sub-folders in the current folder
dir
```

```
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a><span data-ttu-id="2c15e-116">fileinfo</span><span class="sxs-lookup"><span data-stu-id="2c15e-116">fileinfo</span></span>

```
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a><span data-ttu-id="2c15e-117">findfile</span><span class="sxs-lookup"><span data-stu-id="2c15e-117">findfile</span></span>

```
# Find file by name
findfile test.txt
```

## <a name="getfile"></a><span data-ttu-id="2c15e-118">getfile</span><span class="sxs-lookup"><span data-stu-id="2c15e-118">getfile</span></span>

```
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> <span data-ttu-id="2c15e-119">De volgende **bestandstypen kunnen niet** worden gedownload met deze opdracht vanuit Live Response:</span><span class="sxs-lookup"><span data-stu-id="2c15e-119">The following file types **cannot** be downloaded using this command from within Live Response:</span></span>
>
> * [<span data-ttu-id="2c15e-120">Reparse point-bestanden</span><span class="sxs-lookup"><span data-stu-id="2c15e-120">Reparse point files</span></span>](/windows/desktop/fileio/reparse-points/)
> * [<span data-ttu-id="2c15e-121">Spaarzame bestanden</span><span class="sxs-lookup"><span data-stu-id="2c15e-121">Sparse files</span></span>](/windows/desktop/fileio/sparse-files/)
> * <span data-ttu-id="2c15e-122">Bestanden leeg maken</span><span class="sxs-lookup"><span data-stu-id="2c15e-122">Empty files</span></span>
> * <span data-ttu-id="2c15e-123">Virtuele bestanden of bestanden die niet volledig lokaal aanwezig zijn</span><span class="sxs-lookup"><span data-stu-id="2c15e-123">Virtual files, or files that are not fully present locally</span></span>
>
> <span data-ttu-id="2c15e-124">Deze **bestandstypen worden** ondersteund door [PowerShell.](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="2c15e-124">These file types **are** supported by [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).</span></span>
>
> <span data-ttu-id="2c15e-125">Gebruik PowerShell als alternatief als u problemen hebt met het gebruik van deze opdracht vanuit Live Response.</span><span class="sxs-lookup"><span data-stu-id="2c15e-125">Use PowerShell as an alternative, if you have problems using this command from within Live Response.</span></span>

## <a name="processes"></a><span data-ttu-id="2c15e-126">processen</span><span class="sxs-lookup"><span data-stu-id="2c15e-126">processes</span></span>
```
# Show all processes
processes
```

```
# Get process by pid
processes 123
```

```
# Get process by pid with argument name
processes -pid 123
```

```
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a><span data-ttu-id="2c15e-127">putfile</span><span class="sxs-lookup"><span data-stu-id="2c15e-127">putfile</span></span>

```
# Upload file from library
putfile get-process-by-name.ps1
```

```
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a><span data-ttu-id="2c15e-128">register</span><span class="sxs-lookup"><span data-stu-id="2c15e-128">registry</span></span>

```
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a><span data-ttu-id="2c15e-129">herstel</span><span class="sxs-lookup"><span data-stu-id="2c15e-129">remediate</span></span>

```
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```
# Remediate process with specific PID
remediate process 7960
```

```
# See list of all remediated entities
remediate list
```

## <a name="run"></a><span data-ttu-id="2c15e-130">uitvoeren</span><span class="sxs-lookup"><span data-stu-id="2c15e-130">run</span></span>

```
# Run PowerShell script from the library without arguments
run script.ps1
```

```
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```

## <a name="scheduledtask"></a><span data-ttu-id="2c15e-131">scheduledtask</span><span class="sxs-lookup"><span data-stu-id="2c15e-131">scheduledtask</span></span>

```
# Get all scheduled tasks
scheduledtasks
```

```
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```


## <a name="undo"></a><span data-ttu-id="2c15e-132">ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="2c15e-132">undo</span></span>

```
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```

