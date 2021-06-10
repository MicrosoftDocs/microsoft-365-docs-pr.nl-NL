---
title: Diagnostische gegevens verzamelen voor naleving en Windows Defender Microsoft Defender Antivirus
description: Een hulpprogramma gebruiken om gegevens te verzamelen om problemen met update compliance op te lossen bij het gebruik van Microsoft Defender Antivirus toevoegen aan evaluatie
keywords: probleemoplossing, fout, fix, update compliance, oms, monitor, rapport, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2aaf3d1c650713a7f6cfb7b9abb9f2232013d6db
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274794"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a><span data-ttu-id="2b778-104">Diagnostische gegevens voor update compliance verzamelen voor Microsoft Defender AV Assessment</span><span class="sxs-lookup"><span data-stu-id="2b778-104">Collect Update Compliance diagnostic data for Microsoft Defender AV Assessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2b778-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2b778-105">**Applies to:**</span></span>

- [<span data-ttu-id="2b778-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2b778-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2b778-107">In dit artikel wordt beschreven hoe u diagnostische gegevens verzamelt die kunnen worden gebruikt door microsoft-ondersteunings- en technische teams om problemen op te lossen die u mogelijk ondervindt bij het gebruik van de sectie Microsoft Defender AV-evaluatie in de invoeging Update compliance.</span><span class="sxs-lookup"><span data-stu-id="2b778-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you may encounter when using the Microsoft Defender AV Assessment section in the Update Compliance add-in.</span></span>

<span data-ttu-id="2b778-108">Voordat u dit proces probeert, controleert u of u Probleemoplossing Microsoft Defender Antivirus [hebt](troubleshoot-reporting.md)gelezen, aan alle vereisten hebt voldaan en andere voorgestelde stappen voor probleemoplossing hebt genomen.</span><span class="sxs-lookup"><span data-stu-id="2b778-108">Before attempting this process, ensure you have read [Troubleshoot Microsoft Defender Antivirus reporting](troubleshoot-reporting.md), met all require prerequisites, and taken any other suggested troubleshooting steps.</span></span>

<span data-ttu-id="2b778-109">Op ten minste twee apparaten die niet rapporteren of worden weergegeven in Update compliance, kunt u het diagnostische .cab downloaden door de volgende stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="2b778-109">On at least two devices that are not reporting or showing up in Update Compliance, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="2b778-110">Open als volgt een versie op beheerdersniveau van de opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="2b778-110">Open an administrator-level version of the command prompt as follows:</span></span>
        
    <span data-ttu-id="2b778-111">a.</span><span class="sxs-lookup"><span data-stu-id="2b778-111">a.</span></span> <span data-ttu-id="2b778-112">Open het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="2b778-112">Open the **Start** menu.</span></span>

    <span data-ttu-id="2b778-113">b.</span><span class="sxs-lookup"><span data-stu-id="2b778-113">b.</span></span> <span data-ttu-id="2b778-114">Typ **cmd**.</span><span class="sxs-lookup"><span data-stu-id="2b778-114">Type **cmd**.</span></span> <span data-ttu-id="2b778-115">Klik met de rechtermuisknop op **Opdrachtprompt** en klik **op Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="2b778-115">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="2b778-116">c.</span><span class="sxs-lookup"><span data-stu-id="2b778-116">c.</span></span> <span data-ttu-id="2b778-117">Voer beheerdersreferenties in of keur de prompt goed.</span><span class="sxs-lookup"><span data-stu-id="2b778-117">Enter administrator credentials or approve the prompt.</span></span>
        
2. <span data-ttu-id="2b778-118">Ga naar de Windows Defender adreslijst.</span><span class="sxs-lookup"><span data-stu-id="2b778-118">Navigate to the Windows Defender directory.</span></span> <span data-ttu-id="2b778-119">Dit is standaard `C:\Program Files\Windows Defender` .</span><span class="sxs-lookup"><span data-stu-id="2b778-119">By default, this is `C:\Program Files\Windows Defender`.</span></span>

3. <span data-ttu-id="2b778-120">Typ de volgende opdracht en druk op **Enter**</span><span class="sxs-lookup"><span data-stu-id="2b778-120">Type the following command, and then press **Enter**</span></span>
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. <span data-ttu-id="2b778-121">Er .cab een bestand gegenereerd dat verschillende diagnostische logboeken bevat.</span><span class="sxs-lookup"><span data-stu-id="2b778-121">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="2b778-122">De locatie van het bestand wordt opgegeven in de uitvoer in de opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="2b778-122">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="2b778-123">Standaard is de locatie `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="2b778-123">By default, the location is `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span>

5. <span data-ttu-id="2b778-124">Kopieer deze .cab bestanden naar een locatie die kan worden gebruikt door Microsoft-ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="2b778-124">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="2b778-125">Een voorbeeld hiervan kan een met een wachtwoord beveiligde map OneDrive die u met ons kunt delen.</span><span class="sxs-lookup"><span data-stu-id="2b778-125">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

6. <span data-ttu-id="2b778-126">Verzend een e-mail <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">met</a>behulp van de e-mailsjabloon Ondersteuning bijwerken en vul de sjabloon in met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="2b778-126">Send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a><span data-ttu-id="2b778-127">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2b778-127">See also</span></span>

- [<span data-ttu-id="2b778-128">Problemen met Windows Defender Microsoft Defender Antivirus rapportage oplossen</span><span class="sxs-lookup"><span data-stu-id="2b778-128">Troubleshoot Windows Defender Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)