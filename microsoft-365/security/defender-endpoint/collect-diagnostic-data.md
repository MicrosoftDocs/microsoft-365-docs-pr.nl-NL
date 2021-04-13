---
title: Diagnostische gegevens van Microsoft Defender Antivirus verzamelen
description: Een hulpprogramma gebruiken om gegevens te verzamelen om problemen met Microsoft Defender Antivirus op te lossen
keywords: probleemoplossing, fout, fix, update compliance, oms, monitor, rapport, Microsoft Defender av, groepsbeleidsobject, instelling, diagnostische gegevens
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b7c07bace86a2a4651e5c951c6e0b7d954f0982
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690477"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a><span data-ttu-id="b5ad0-104">Diagnostische gegevens van Microsoft Defender AV verzamelen</span><span class="sxs-lookup"><span data-stu-id="b5ad0-104">Collect Microsoft Defender AV diagnostic data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b5ad0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b5ad0-105">**Applies to:**</span></span>

- [<span data-ttu-id="b5ad0-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b5ad0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b5ad0-107">In dit artikel wordt beschreven hoe u diagnostische gegevens verzamelt die kunnen worden gebruikt door microsoft-ondersteunings- en technische teams om problemen op te lossen die u mogelijk ondervindt bij het gebruik van microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you might encounter when using the Microsoft Defender AV.</span></span>

> [!NOTE]
> <span data-ttu-id="b5ad0-108">Als onderdeel van het onderzoek- of antwoordproces kunt u een onderzoekspakket verzamelen vanaf een apparaat.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-108">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="b5ad0-109">Dit doet u als: [Onderzoekspakket van apparaten verzamelen.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)</span><span class="sxs-lookup"><span data-stu-id="b5ad0-109">Here's how: [Collect investigation package from devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="b5ad0-110">Op ten minste twee apparaten die met hetzelfde probleem te maken hebben, kunt u het diagnostische .cab-bestand verkrijgen door de volgende stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="b5ad0-110">On at least two devices that are experiencing the same issue, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="b5ad0-111">Open als volgt een versie op beheerdersniveau van de opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="b5ad0-111">Open an administrator-level version of the command prompt as follows:</span></span>

    <span data-ttu-id="b5ad0-112">a.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-112">a.</span></span> <span data-ttu-id="b5ad0-113">Open het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-113">Open the **Start** menu.</span></span>

    <span data-ttu-id="b5ad0-114">b.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-114">b.</span></span> <span data-ttu-id="b5ad0-115">Typ **cmd**.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-115">Type **cmd**.</span></span> <span data-ttu-id="b5ad0-116">Klik met de rechtermuisknop op **Opdrachtprompt** en klik **op Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="b5ad0-116">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="b5ad0-117">c.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-117">c.</span></span> <span data-ttu-id="b5ad0-118">Voer beheerdersreferenties in of keur de prompt goed.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-118">Enter administrator credentials or approve the prompt.</span></span>

2. <span data-ttu-id="b5ad0-119">Ga naar de Microsoft Defender-adreslijst.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-119">Navigate to the Microsoft Defender directory.</span></span> <span data-ttu-id="b5ad0-120">Dit is standaard `C:\Program Files\Windows Defender` .</span><span class="sxs-lookup"><span data-stu-id="b5ad0-120">By default, this is `C:\Program Files\Windows Defender`.</span></span>

> [!NOTE]
> <span data-ttu-id="b5ad0-121">Als u een bijgewerkte Versie van [het Microsoft Defender-platform gebruikt,](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)kunt u vanaf `MpCmdRun` de volgende locatie uitvoeren: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .</span><span class="sxs-lookup"><span data-stu-id="b5ad0-121">If you're running an [updated Microsoft Defender Platform version](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform), please run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

3. <span data-ttu-id="b5ad0-122">Typ de volgende opdracht en druk op **Enter**</span><span class="sxs-lookup"><span data-stu-id="b5ad0-122">Type the following command, and then press **Enter**</span></span>  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. <span data-ttu-id="b5ad0-123">Er wordt een CAB-bestand gegenereerd dat verschillende diagnostische logboeken bevat.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-123">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="b5ad0-124">De locatie van het bestand wordt opgegeven in de uitvoer in de opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-124">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="b5ad0-125">Standaard is de locatie `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="b5ad0-125">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

> [!NOTE]
> <span data-ttu-id="b5ad0-126">Als u het cabbestand wilt omleiden naar een ander pad of unc-share, gebruikt u de volgende opdracht: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span><span class="sxs-lookup"><span data-stu-id="b5ad0-126">To redirect the cab file to a a different path or UNC share, use the following command: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span></span>  <br/><span data-ttu-id="b5ad0-127">Zie Diagnostische gegevens [omleiden naar een UNC-share](#redirect-diagnostic-data-to-a-unc-share)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-127">For more information, see [Redirect diagnostic data to a UNC share](#redirect-diagnostic-data-to-a-unc-share).</span></span>

5. <span data-ttu-id="b5ad0-128">Kopieer deze CAB-bestanden naar een locatie die kan worden gebruikt door Microsoft-ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-128">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="b5ad0-129">Een voorbeeld hiervan kan een met een wachtwoord beveiligde OneDrive-map zijn die u met ons kunt delen.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-129">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

> [!NOTE]
><span data-ttu-id="b5ad0-130">Als u een probleem hebt met de <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a"></a>naleving bijwerken, verzendt u een e-mail met de e-mailsjabloon Ondersteuning bijwerken en vult u de sjabloon in met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="b5ad0-130">If you have a problem with Update compliance, send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a><span data-ttu-id="b5ad0-131">Diagnostische gegevens omleiden naar een UNC-share</span><span class="sxs-lookup"><span data-stu-id="b5ad0-131">Redirect diagnostic data to a UNC share</span></span>
<span data-ttu-id="b5ad0-132">Als u diagnostische gegevens wilt verzamelen in een centrale opslagplaats, kunt u de parameter SupportLogLocation opgeven.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-132">To collect diagnostic data on a central repository, you can specify the SupportLogLocation parameter.</span></span>

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

<span data-ttu-id="b5ad0-133">Kopieert de diagnostische gegevens naar het opgegeven pad.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-133">Copies the diagnostic data to the specified path.</span></span> <span data-ttu-id="b5ad0-134">Als het pad niet is opgegeven, worden de diagnostische gegevens gekopieerd naar de locatie die is opgegeven in de ondersteuningslogboeklocatieconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-134">If the path is not specified, the diagnostic data will be copied to the location specified in the Support Log Location Configuration.</span></span>

<span data-ttu-id="b5ad0-135">Wanneer de parameter SupportLogLocation wordt gebruikt, wordt een mapstructuur als volgt gemaakt in het doelpad:</span><span class="sxs-lookup"><span data-stu-id="b5ad0-135">When the SupportLogLocation parameter is used, a folder structure like as follows will be created in the destination path:</span></span>

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| <span data-ttu-id="b5ad0-136">veld</span><span class="sxs-lookup"><span data-stu-id="b5ad0-136">field</span></span>  | <span data-ttu-id="b5ad0-137">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="b5ad0-137">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="b5ad0-138">pad</span><span class="sxs-lookup"><span data-stu-id="b5ad0-138">path</span></span> | <span data-ttu-id="b5ad0-139">Het pad zoals opgegeven op de opdrachtregel of opgehaald uit configuratie</span><span class="sxs-lookup"><span data-stu-id="b5ad0-139">The path as specified on the command line or retrieved from configuration</span></span>
| <span data-ttu-id="b5ad0-140">MMDD</span><span class="sxs-lookup"><span data-stu-id="b5ad0-140">MMDD</span></span> | <span data-ttu-id="b5ad0-141">Maand en dag waarop de diagnostische gegevens zijn verzameld (bijvoorbeeld 0530)</span><span class="sxs-lookup"><span data-stu-id="b5ad0-141">Month and day when the diagnostic data was collected (for example, 0530)</span></span>
| <span data-ttu-id="b5ad0-142">hostnaam</span><span class="sxs-lookup"><span data-stu-id="b5ad0-142">hostname</span></span> | <span data-ttu-id="b5ad0-143">De hostnaam van het apparaat waarop de diagnostische gegevens zijn verzameld</span><span class="sxs-lookup"><span data-stu-id="b5ad0-143">The hostname of the device on which the diagnostic data was collected</span></span>
| <span data-ttu-id="b5ad0-144">HHMM</span><span class="sxs-lookup"><span data-stu-id="b5ad0-144">HHMM</span></span> | <span data-ttu-id="b5ad0-145">Uren en minuten waarop de diagnostische gegevens zijn verzameld (bijvoorbeeld 1422)</span><span class="sxs-lookup"><span data-stu-id="b5ad0-145">Hours and minutes when the diagnostic data was collected (for example, 1422)</span></span>

> [!NOTE]
> <span data-ttu-id="b5ad0-146">Wanneer u een bestands delen gebruikt, moet u ervoor zorgen dat het account dat wordt gebruikt om het diagnostische pakket te verzamelen, schrijftoegang heeft tot de share.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-146">When using a file share please make sure that account used to collect the diagnostic package has write access to the share.</span></span>  

## <a name="specify-location-where-diagnostic-data-is-created"></a><span data-ttu-id="b5ad0-147">Locatie opgeven waar diagnostische gegevens worden gemaakt</span><span class="sxs-lookup"><span data-stu-id="b5ad0-147">Specify location where diagnostic data is created</span></span>

<span data-ttu-id="b5ad0-148">U kunt ook opgeven waar het diagnostische CAB-bestand wordt gemaakt met een groepsbeleidsobject (GPO).</span><span class="sxs-lookup"><span data-stu-id="b5ad0-148">You can also specify where the diagnostic .cab file will be created using a Group Policy Object (GPO).</span></span> 

1. <span data-ttu-id="b5ad0-149">Open de editor voor lokaal groepsbeleid en zoek de OndersteuningLogLocation-GPO op: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span><span class="sxs-lookup"><span data-stu-id="b5ad0-149">Open the Local Group Policy Editor and find the SupportLogLocation GPO at: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span></span>
   
1. <span data-ttu-id="b5ad0-150">Selecteer **Het adreslijstpad definiëren om ondersteuningslogboekbestanden te kopiëren.**</span><span class="sxs-lookup"><span data-stu-id="b5ad0-150">Select **Define the directory path to copy support log files**.</span></span>

    ![Schermafbeelding van de editor voor lokaal groepsbeleid](images/GPO1-SupportLogLocationDefender.png)  
        
     ![Schermafbeelding van de instelling pad definiëren voor logboekbestanden](images/GPO2-SupportLogLocationGPPage.png)  
3. <span data-ttu-id="b5ad0-153">Selecteer ingeschakeld in de beleidseditor.</span><span class="sxs-lookup"><span data-stu-id="b5ad0-153">Inside the policy editor, select **Enabled**.</span></span>
       
4. <span data-ttu-id="b5ad0-154">Geef het adreslijstpad op waar u de ondersteuningslogboekbestanden wilt kopiëren in **het veld Opties.**</span><span class="sxs-lookup"><span data-stu-id="b5ad0-154">Specify the directory path where you want to copy the support log files in the **Options** field.</span></span>
     <span data-ttu-id="b5ad0-155">![Schermafbeelding van aangepaste instelling voor ingeschakeld adreslijstpad](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span><span class="sxs-lookup"><span data-stu-id="b5ad0-155">![Screenshot of Enabled directory path custom setting](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span></span> 
5. <span data-ttu-id="b5ad0-156">Selecteer **OK** of **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="b5ad0-156">Select **OK** or **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5ad0-157">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b5ad0-157">See also</span></span>

- [<span data-ttu-id="b5ad0-158">Problemen met Microsoft Defender Antivirusrapportage oplossen</span><span class="sxs-lookup"><span data-stu-id="b5ad0-158">Troubleshoot Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)