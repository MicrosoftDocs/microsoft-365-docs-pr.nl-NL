---
title: Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen
description: Vermijd veelvoorkomende fouten bij het definiëren van uitsluitingen voor Microsoft Defender Antivirus scans.
keywords: uitsluitingen, bestanden, extensie, bestandstype, mapnaam, bestandsnaam, scans
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/15/2021
ms.openlocfilehash: f9ca83fcfba4b79898a0fed527e38947a4c230d6
ms.sourcegitcommit: 959c3c3633e40b7b0f5e2c8372409778005a24db
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/15/2021
ms.locfileid: "52950129"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="30a75-104">Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen</span><span class="sxs-lookup"><span data-stu-id="30a75-104">Common mistakes to avoid when defining exclusions</span></span>

<span data-ttu-id="30a75-105">U kunt een uitsluitingslijst definiëren voor items die u niet wilt Microsoft Defender Antivirus scannen.</span><span class="sxs-lookup"><span data-stu-id="30a75-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="30a75-106">Dergelijke uitgesloten items kunnen bedreigingen bevatten die uw apparaat kwetsbaar maken.</span><span class="sxs-lookup"><span data-stu-id="30a75-106">Such excluded items could contain threats that make your device vulnerable.</span></span> <span data-ttu-id="30a75-107">In dit artikel wordt een veelvoorkomende fout beschreven die u moet vermijden bij het definiëren van uitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="30a75-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="30a75-108">Voordat u uw uitsluitingslijsten definieert, [Aanbevelingen voor het definiëren van uitsluitingen.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)</span><span class="sxs-lookup"><span data-stu-id="30a75-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="30a75-109">Bepaalde vertrouwde items uitsluiten</span><span class="sxs-lookup"><span data-stu-id="30a75-109">Excluding certain trusted items</span></span>

<span data-ttu-id="30a75-110">Bepaalde bestanden, bestandstypen, mappen of processen mogen niet worden uitgesloten van scannen, ook al vertrouwt u erop dat ze niet schadelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="30a75-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="30a75-111">Definieer geen uitsluitingen voor de maplocaties, bestandsextensies en processen die in de volgende secties worden vermeld:</span><span class="sxs-lookup"><span data-stu-id="30a75-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following sections:</span></span>
- <span data-ttu-id="30a75-112">Maplocaties</span><span class="sxs-lookup"><span data-stu-id="30a75-112">Folder locations</span></span>
- <span data-ttu-id="30a75-113">Bestandsextensies</span><span class="sxs-lookup"><span data-stu-id="30a75-113">File extensions</span></span>
- <span data-ttu-id="30a75-114">Processen</span><span class="sxs-lookup"><span data-stu-id="30a75-114">Processes</span></span>

### <a name="folder-locations"></a><span data-ttu-id="30a75-115">Maplocaties</span><span class="sxs-lookup"><span data-stu-id="30a75-115">Folder locations</span></span>

<span data-ttu-id="30a75-116">Definieer over het algemeen geen uitsluitingen voor de volgende maplocaties:</span><span class="sxs-lookup"><span data-stu-id="30a75-116">In general, do not define exclusions for the following folder locations:</span></span>

`%systemdrive%` 

`C:`

`C:\`

`C:\*`

`%ProgramFiles%\Java`

`C:\Program Files\Java` 

`%ProgramFiles%\Contoso\` 

`C:\Program Files\Contoso\` 

`%ProgramFiles(x86)%\Contoso\` 

`C:\Program Files (x86)\Contoso\`

`C:\Temp`

`C:\Temp\`

`C:\Temp\*`

`C:\Users\`

`C:\Users\*`

<span data-ttu-id="30a75-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Let op de volgende uitzondering voor SharePoint**: Sluit dit uit wanneer u antivirusbeveiliging op bestandsniveau gebruikt in `C:\Users\ServiceAccount\AppData\Local\Temp` [SharePoint.](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)</span><span class="sxs-lookup"><span data-stu-id="30a75-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\ServiceAccount\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

<span data-ttu-id="30a75-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Let op de volgende uitzondering voor SharePoint**: Sluit dit uit wanneer u antivirusbeveiliging op bestandsniveau gebruikt in `C:\Users\Default\AppData\Local\Temp` [SharePoint.](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)</span><span class="sxs-lookup"><span data-stu-id="30a75-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\Default\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

`%Windir%\Prefetch`

`C:\Windows\Prefetch`

`C:\Windows\Prefetch\`

`C:\Windows\Prefetch\*`

`%Windir%\System32\Spool`

`C:\Windows\System32\Spool`

`C:\Windows\System32\CatRoot2`
`%Windir%\Temp`

`C:\Windows\Temp`

`C:\Windows\Temp\`

`C:\Windows\Temp\*`

### <a name="file-extensions"></a><span data-ttu-id="30a75-119">Bestandsextensies</span><span class="sxs-lookup"><span data-stu-id="30a75-119">File extensions</span></span>

<span data-ttu-id="30a75-120">Definieer over het algemeen geen uitsluitingen voor de volgende bestandsextensies:</span><span class="sxs-lookup"><span data-stu-id="30a75-120">In general, do not define exclusions for the following file extensions:</span></span>

`.7z`

`.bat`

`.bin`

`.cab`

`.cmd`

`.com` 

`.cpl`

`.dll`

`.exe`

`.fla`

`.gif`

`.gz`

`.hta`

`.inf`

`.java`

`.jar`

`.job`

`.jpeg`

`.jpg`

`.js`

`.ko`

`.ko.gz`

`.msi`

`.ocx`

`.png`

`.ps1`

`.py`

`.rar`

`.reg`

`.scr`

`.sys`

`.tar`

`.tmp`

`.url`

`.vbe`

`.vbs`

`.wsf`

`.zip`

### <a name="processes"></a><span data-ttu-id="30a75-121">Processen</span><span class="sxs-lookup"><span data-stu-id="30a75-121">Processes</span></span> 

<span data-ttu-id="30a75-122">Definieer over het algemeen geen uitsluitingen voor de volgende processen:</span><span class="sxs-lookup"><span data-stu-id="30a75-122">In general, do not define exclusions for the following processes:</span></span>

`AcroRd32.exe`  

`bitsadmin.exe`  

`excel.exe`  

`iexplore.exe`  

`java.exe`  

`outlook.exe`  

`psexec.exe`  

`powerpnt.exe`  

`powershell.exe`  

`schtasks.exe`

`svchost.exe` 

`wmic.exe`  

`winword.exe`  

`wuauclt.exe`  

`addinprocess.exe`  

`addinprocess32.exe`  

`addinutil.exe`  

`bash.exe`  

`bginfo.exe` 

`cdb.exe`  

`csi.exe`  

`dbghost.exe`  

`dbgsvc.exe`  

`dnx.exe`

`dotnet.exe`

`fsi.exe`  

`fsiAnyCpu.exe`  

`kd.exe`  

`ntkd.exe`  

`lxssmanager.dll`  

`msbuild.exe` 

`mshta.exe`  

`ntsd.exe`  

`rcsi.exe`  

`system.management.automation.dll`  

`windbg.exe`

> [!NOTE]
> <span data-ttu-id="30a75-123">U kunt ervoor kiezen om bestandstypen uit te sluiten, zoals , of als uw omgeving een `.gif` `.jpg` `.jpeg` moderne, up-to-date software heeft met een strikt updatebeleid om eventuele beveiligingslekken `.png` te behandelen.</span><span class="sxs-lookup"><span data-stu-id="30a75-123">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="30a75-124">Alleen de bestandsnaam in de uitsluitingslijst gebruiken</span><span class="sxs-lookup"><span data-stu-id="30a75-124">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="30a75-125">Een malware kan dezelfde naam hebben als het bestand dat u vertrouwt en wilt uitsluiten van scannen.</span><span class="sxs-lookup"><span data-stu-id="30a75-125">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="30a75-126">Gebruik daarom een volledig gekwalificeerd pad naar het bestand dat u wilt uitsluiten in plaats van alleen de bestandsnaam te gebruiken om te voorkomen dat een potentiële malware wordt gescand.</span><span class="sxs-lookup"><span data-stu-id="30a75-126">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="30a75-127">Als u bijvoorbeeld het scannen wilt uitsluiten, gebruikt u het volledige pad naar `Filename.exe` het bestand, zoals `C:\program files\contoso\Filename.exe` .</span><span class="sxs-lookup"><span data-stu-id="30a75-127">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="30a75-128">Eén uitsluitingslijst gebruiken voor meerdere serverwerkbelastingen</span><span class="sxs-lookup"><span data-stu-id="30a75-128">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="30a75-129">Gebruik geen enkele uitsluitingslijst om uitsluitingen voor meerdere serverbelastingen te definiëren.</span><span class="sxs-lookup"><span data-stu-id="30a75-129">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="30a75-130">Splits de uitsluitingen voor verschillende toepassings- of servicewerkbelastingen in meerdere uitsluitingslijsten.</span><span class="sxs-lookup"><span data-stu-id="30a75-130">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="30a75-131">De uitsluitingslijst voor uw IIS Server-werkbelasting moet bijvoorbeeld verschillen van de uitsluitingslijst voor uw SQL Server werkbelasting.</span><span class="sxs-lookup"><span data-stu-id="30a75-131">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="30a75-132">Onjuiste omgevingsvariabelen gebruiken als jokertekens in de lijsten met bestandsnaam en mappad of extensieuitsluiting</span><span class="sxs-lookup"><span data-stu-id="30a75-132">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="30a75-133">Microsoft Defender Antivirus Service wordt uitgevoerd in systeemcontext met behulp van het LocalSystem-account, wat betekent dat de service informatie krijgt van de systeemomgevingsvariabele en niet van de variabele voor de gebruikersomgeving.</span><span class="sxs-lookup"><span data-stu-id="30a75-133">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="30a75-134">Het gebruik van omgevingsvariabelen als jokerteken in uitsluitingslijsten is beperkt tot systeemvariabelen en die van toepassing op processen die als NT AUTHORITY\SYSTEM-account worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="30a75-134">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="30a75-135">Gebruik daarom geen variabelen in de gebruikersomgeving als jokertekens bij het toevoegen van Microsoft Defender Antivirus map en procesuitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="30a75-135">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="30a75-136">Zie de tabel onder [Systeemomgevingvariabelen](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) voor een volledige lijst met systeemomgevingvariabelen.</span><span class="sxs-lookup"><span data-stu-id="30a75-136">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="30a75-137">Zie [Jokertekens gebruiken in de](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) lijst met uitsluitingslijsten voor bestandsnaam en mappen of extensies voor informatie over het gebruik van jokertekens in uitsluitingslijsten.</span><span class="sxs-lookup"><span data-stu-id="30a75-137">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

