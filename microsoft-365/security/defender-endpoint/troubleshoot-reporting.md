---
title: Problemen met rapportagehulpmiddelen voor Microsoft Defender AV oplossen
description: Veelvoorkomende problemen identificeren en oplossen wanneer u probeert te rapporteren in de AV-beveiligingsstatus van Microsoft Defender in Update Compliance
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
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ab987089c20d0a1d0baed152e7ddcfdd2878cc65
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843456"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a><span data-ttu-id="f5836-104">Problemen met Microsoft Defender Antivirus-rapportage oplossen in Naleving van updates</span><span class="sxs-lookup"><span data-stu-id="f5836-104">Troubleshoot Microsoft Defender Antivirus reporting in Update Compliance</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f5836-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f5836-105">**Applies to:**</span></span>

- [<span data-ttu-id="f5836-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f5836-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="f5836-107">Op 31 maart 2020 wordt de Microsoft Defender Antivirus van Update Compliance verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f5836-107">On March 31, 2020, the Microsoft Defender Antivirus reporting feature of Update Compliance will be removed.</span></span> <span data-ttu-id="f5836-108">U kunt beleidsregels voor beveiligings compliance blijven definiëren en controleren met [Microsoft Endpoint Manager,](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)waardoor u meer controle hebt over beveiligingsfuncties en updates.</span><span class="sxs-lookup"><span data-stu-id="f5836-108">You can continue to define and review security compliance policies using [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), which allows finer control over security features and updates.</span></span>

<span data-ttu-id="f5836-109">U kunt een Microsoft Defender Antivirus update compliance gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f5836-109">You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="f5836-110">U ziet de status voor E3-, B-, F1-, VL- en Pro licenties.</span><span class="sxs-lookup"><span data-stu-id="f5836-110">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="f5836-111">Voor E5-licenties moet u echter de [Microsoft Defender for Endpoint-portal gebruiken.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="f5836-111">However, for E5 licenses, you need to use the [Microsoft Defender for Endpoint portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="f5836-112">Zie voor meer informatie over licentieopties [Windows 10 opties voor productlicenties.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)</span><span class="sxs-lookup"><span data-stu-id="f5836-112">To learn more about licensing options, see [Windows 10 product licensing options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span></span>

<span data-ttu-id="f5836-113">Wanneer u [Windows Analytics Update Compliance](/windows/deployment/update/update-compliance-using#wdav-assessment) gebruikt om rapportage te verkrijgen over de beveiligingsstatus van apparaten of eindpunten in uw netwerk die Microsoft Defender Antivirus gebruiken, kunnen er problemen of problemen zijn.</span><span class="sxs-lookup"><span data-stu-id="f5836-113">When you use [Windows Analytics Update Compliance to obtain reporting into the protection status of devices or endpoints](/windows/deployment/update/update-compliance-using#wdav-assessment) in your network that are using Microsoft Defender Antivirus, you might encounter problems or issues.</span></span>

<span data-ttu-id="f5836-114">Meestal zijn de meest voorkomende indicatoren van een probleem:</span><span class="sxs-lookup"><span data-stu-id="f5836-114">Typically, the most common indicators of a problem are:</span></span>
- <span data-ttu-id="f5836-115">U ziet slechts een klein aantal of een subset van alle apparaten die u verwachtte te zien</span><span class="sxs-lookup"><span data-stu-id="f5836-115">You only see a small number or subset of all the devices you were expecting to see</span></span>
- <span data-ttu-id="f5836-116">U ziet helemaal geen apparaten</span><span class="sxs-lookup"><span data-stu-id="f5836-116">You do not see any devices at all</span></span>
- <span data-ttu-id="f5836-117">De rapporten en informatie die u ziet, zijn verouderd (ouder dan een paar dagen)</span><span class="sxs-lookup"><span data-stu-id="f5836-117">The reports and information you do see is outdated (older than a few days)</span></span>

<span data-ttu-id="f5836-118">Voor veelvoorkomende foutcodes en gebeurtenis-ID's met betrekking tot de Microsoft Defender Antivirus service die niet gerelateerd zijn aan Compliance bijwerken, zie [Microsoft Defender Antivirus gebeurtenissen.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f5836-118">For common error codes and event IDs related to the Microsoft Defender Antivirus service that are not related to Update Compliance, see [Microsoft Defender Antivirus events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="f5836-119">Er zijn drie stappen om deze problemen op te lossen:</span><span class="sxs-lookup"><span data-stu-id="f5836-119">There are three steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="f5836-120">Controleren of u aan alle vereisten hebt voldaan</span><span class="sxs-lookup"><span data-stu-id="f5836-120">Confirm that you have met all prerequisites</span></span>
2. <span data-ttu-id="f5836-121">Uw connectiviteit met de Windows Defender cloudservice controleren</span><span class="sxs-lookup"><span data-stu-id="f5836-121">Check your connectivity to the Windows Defender cloud-based service</span></span>
3. <span data-ttu-id="f5836-122">Ondersteuningslogboeken verzenden</span><span class="sxs-lookup"><span data-stu-id="f5836-122">Submit support logs</span></span>

>[!IMPORTANT]
><span data-ttu-id="f5836-123">Het duurt meestal 3 dagen voordat apparaten worden weergegeven in Naleving bijwerken.</span><span class="sxs-lookup"><span data-stu-id="f5836-123">It typically takes 3 days for devices to start appearing in Update Compliance.</span></span>


## <a name="confirm-prerequisites"></a><span data-ttu-id="f5836-124">Vereisten bevestigen</span><span class="sxs-lookup"><span data-stu-id="f5836-124">Confirm prerequisites</span></span>

<span data-ttu-id="f5836-125">Om ervoor te zorgen dat apparaten correct worden uitgevoerd in Update compliance, moet u voldoen aan bepaalde vereisten voor zowel de Update Compliance-service als voor Microsoft Defender Antivirus:</span><span class="sxs-lookup"><span data-stu-id="f5836-125">In order for devices to properly show up in Update Compliance, you have to meet certain prerequisites for both the Update Compliance service and for Microsoft Defender Antivirus:</span></span>

>[!div class="checklist"]
>- <span data-ttu-id="f5836-126">Eindpunten gebruiken Microsoft Defender Antivirus als de enige antivirusbeveiligingsapp.</span><span class="sxs-lookup"><span data-stu-id="f5836-126">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="f5836-127">[Als u een andere antivirus-app gebruikt,](microsoft-defender-antivirus-compatibility.md) wordt Microsoft Defender AV uitgeschakeld en wordt het eindpunt niet gerapporteerd in Naleving bijwerken.</span><span class="sxs-lookup"><span data-stu-id="f5836-127">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](microsoft-defender-antivirus-compatibility.md) and the endpoint will not be reported in Update Compliance.</span></span>
> - <span data-ttu-id="f5836-128">[Beveiliging in de cloud is ingeschakeld.](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f5836-128">[Cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="f5836-129">Eindpunten kunnen verbinding [maken met de MICROSOFT Defender AV-cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="f5836-129">Endpoints can [connect to the Microsoft Defender AV cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span></span>
> - <span data-ttu-id="f5836-130">Als het eindpunt wordt uitgevoerd Windows 10 versie 1607 of eerder, moeten Windows 10 diagnostische gegevens zijn ingesteld op [het niveau Verbeterd.](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)</span><span class="sxs-lookup"><span data-stu-id="f5836-130">If the endpoint is running Windows 10 version 1607 or earlier, [Windows 10 diagnostic data must be set to the Enhanced level](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span></span>
> - <span data-ttu-id="f5836-131">Het is 3 dagen geleden dat aan alle vereisten is voldaan</span><span class="sxs-lookup"><span data-stu-id="f5836-131">It has been 3 days since all requirements have been met</span></span>

<span data-ttu-id="f5836-132">"U kunt een Microsoft Defender Antivirus update compliance gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f5836-132">“You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="f5836-133">U ziet de status voor E3-, B-, F1-, VL- en Pro licenties.</span><span class="sxs-lookup"><span data-stu-id="f5836-133">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="f5836-134">Voor E5-licenties moet u echter de Microsoft Defender for Endpoint-portal (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f5836-134">However, for E5 licenses, you need to use the Microsoft Defender for Endpoint portal (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="f5836-135">Zie voor meer informatie over licentieopties Windows 10 opties voor productlicenties"</span><span class="sxs-lookup"><span data-stu-id="f5836-135">To learn more about licensing options, see Windows 10 product licensing options"</span></span>

<span data-ttu-id="f5836-136">Als aan de bovenstaande vereisten is voldaan, moet u mogelijk verder gaan met de volgende stap om diagnostische gegevens te verzamelen en naar ons te verzenden.</span><span class="sxs-lookup"><span data-stu-id="f5836-136">If the above prerequisites have all been met, you might need to proceed to the next step to collect diagnostic information and send it to us.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f5836-137">Diagnostische gegevens verzamelen voor probleemoplossing voor update compliance</span><span class="sxs-lookup"><span data-stu-id="f5836-137">Collect diagnostic data for Update Compliance troubleshooting</span></span>](collect-diagnostic-data.md)  

## <a name="related-topics"></a><span data-ttu-id="f5836-138">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f5836-138">Related topics</span></span>

- [<span data-ttu-id="f5836-139">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="f5836-139">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="f5836-140">Implementatie van Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="f5836-140">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)