---
title: Het door de cloud geleverde beveiligingsniveau opgeven voor Microsoft Defender Antivirus
description: Stel uw niveau van beveiliging in de cloud in voor Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, defender, cloud, agressiviteit, beschermingsniveau
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: a0c73c8dd341c4940e3eddd4ede75240e57502d6
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764119"
---
# <a name="specify-the-cloud-delivered-protection-level"></a><span data-ttu-id="4e4ff-104">Niveau voor door cloud geleverde beveiliging opgeven</span><span class="sxs-lookup"><span data-stu-id="4e4ff-104">Specify the cloud-delivered protection level</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4e4ff-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4e4ff-105">**Applies to:**</span></span>

- [<span data-ttu-id="4e4ff-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4e4ff-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4e4ff-107">U kunt uw niveau van beveiliging in de cloud opgeven dat wordt aangeboden door Microsoft Defender Antivirus met Behulp van Microsoft Endpoint Manager (aanbevolen) of Groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-107">You can specify your level of cloud-delivered protection offered by Microsoft Defender Antivirus by using Microsoft Endpoint Manager (recommended) or Group Policy.</span></span>

> [!TIP]
> <span data-ttu-id="4e4ff-108">Cloudbeveiliging is niet alleen beveiliging voor bestanden die zijn opgeslagen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-108">Cloud protection is not simply protection for files that are stored in the cloud.</span></span> <span data-ttu-id="4e4ff-109">De Microsoft Defender Antivirus-cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging op uw netwerk en apparaten (ook wel eindpunten genoemd).</span><span class="sxs-lookup"><span data-stu-id="4e4ff-109">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and devices (also called endpoints).</span></span> <span data-ttu-id="4e4ff-110">Cloudbeveiliging met Microsoft Defender Antivirus maakt gebruik van gedistribueerde resources en machine learning om uw eindpunten te beschermen tegen een snelheid die veel sneller is dan traditionele beveiligingsinformatie-updates.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span></span> <span data-ttu-id="4e4ff-111">Microsoft Intune en Microsoft Endpoint Manager maken nu deel uit van [Microsoft Endpoint Manager.](/mem/endpoint-manager-overview)</span><span class="sxs-lookup"><span data-stu-id="4e4ff-111">Microsoft Intune and Microsoft Endpoint Manager are now part of [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span></span> 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="4e4ff-112">Microsoft Endpoint Manager gebruiken om het niveau van door de cloud geleverde beveiliging op te geven</span><span class="sxs-lookup"><span data-stu-id="4e4ff-112">Use Microsoft Endpoint Manager to specify the level of cloud-delivered protection</span></span>

1. <span data-ttu-id="4e4ff-113">Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-113">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="4e4ff-114">Kies **Endpoint Security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-114">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="4e4ff-115">Selecteer een antivirusprofiel.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-115">Select an antivirus profile.</span></span> <span data-ttu-id="4e4ff-116">(Als u nog geen profiel hebt of als u een nieuw profiel wilt maken, zie Apparaatbeperkingsinstellingen [configureren in Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="4e4ff-116">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="4e4ff-117">Selecteer **Eigenschappen**.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-117">Select **Properties**.</span></span> <span data-ttu-id="4e4ff-118">Kies vervolgens naast **Configuratie-instellingen** de optie **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="4e4ff-118">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="4e4ff-119">Vouw **Cloudbeveiliging uit** en  selecteer een van de volgende opties in de lijst beveiligingsniveau in de cloud:</span><span class="sxs-lookup"><span data-stu-id="4e4ff-119">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>

    1. <span data-ttu-id="4e4ff-120">**Hoog:** Hiermee wordt een sterk detectieniveau toegepast.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-120">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="4e4ff-121">**Hoog plus:** gebruikt het **hoge** niveau en past extra beveiligingsmaatregelen toe (mogelijk van invloed op de prestaties van de client).</span><span class="sxs-lookup"><span data-stu-id="4e4ff-121">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="4e4ff-122">**Nul tolerantie:** blokkeert alle onbekende uitvoerbare bestanden.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-122">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="4e4ff-123">Kies **Controleren+ opslaan** en kies vervolgens **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="4e4ff-123">Choose **Review + save**, and then choose **Save**.</span></span> 

> [!TIP]
> <span data-ttu-id="4e4ff-124">Hebt u hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="4e4ff-124">Need some help?</span></span> <span data-ttu-id="4e4ff-125">Zie de volgende bronnen:</span><span class="sxs-lookup"><span data-stu-id="4e4ff-125">See the following resources:</span></span>
> - [<span data-ttu-id="4e4ff-126">Endpoint Protection configureren</span><span class="sxs-lookup"><span data-stu-id="4e4ff-126">Configure Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [<span data-ttu-id="4e4ff-127">Instellingen voor eindpuntbeveiliging toevoegen in Intune</span><span class="sxs-lookup"><span data-stu-id="4e4ff-127">Add endpoint protection settings in Intune</span></span>](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="4e4ff-128">Groepsbeleid gebruiken om het niveau van door de cloud geleverde beveiliging op te geven</span><span class="sxs-lookup"><span data-stu-id="4e4ff-128">Use Group Policy to specify the level of cloud-delivered protection</span></span>

1.  <span data-ttu-id="4e4ff-129">Open op uw groepsbeleidsbeheercomputer de [console Groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="4e4ff-129">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="4e4ff-130">Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik vervolgens op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="4e4ff-130">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

3.  <span data-ttu-id="4e4ff-131">Ga in **de Editor voor groepsbeleidsbeheer** naar **Beheersjablonen voor computerconfiguratie.**  >  </span><span class="sxs-lookup"><span data-stu-id="4e4ff-131">In the **Group Policy Management Editor** go to **Computer Configuration** > **Administrative templates**.</span></span>

4.  <span data-ttu-id="4e4ff-132">Vouw de boom uit **naar Windows Components** Microsoft Defender  >  **Antivirus**  >  **MpEngine**.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-132">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

5.  <span data-ttu-id="4e4ff-133">Dubbelklik op de **instelling Beveiligingsniveau voor de cloud** selecteren en stel deze in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="4e4ff-133">Double-click the **Select cloud protection level** setting and set it to **Enabled**.</span></span> <span data-ttu-id="4e4ff-134">Selecteer het beveiligingsniveau:</span><span class="sxs-lookup"><span data-stu-id="4e4ff-134">Select the level of protection:</span></span>
    - <span data-ttu-id="4e4ff-135">**Standaardblokkeringsniveau** biedt een sterke detectie zonder het risico op het detecteren van legitieme bestanden te vergroten.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-135">**Default blocking level** provides strong detection without increasing the risk of detecting legitimate files.</span></span>
    - <span data-ttu-id="4e4ff-136">**Matig blokkeringsniveau** biedt alleen gemiddeld voor detecties met hoog vertrouwen</span><span class="sxs-lookup"><span data-stu-id="4e4ff-136">**Moderate blocking level** provides moderate only for high confidence detections</span></span>
    - <span data-ttu-id="4e4ff-137">**Met hoog blokkeringsniveau** wordt een sterk detectieniveau toegepast terwijl de prestaties van de client worden geoptimaliseerd (maar kunt u ook een grotere kans op onwaar-positieven bieden).</span><span class="sxs-lookup"><span data-stu-id="4e4ff-137">**High blocking level** applies a strong level of detection while optimizing client performance (but can also give you a greater chance of false positives).</span></span>
    - <span data-ttu-id="4e4ff-138">**Hoog + blokkeringsniveau** past extra beveiligingsmaatregelen toe (mogelijk van invloed op de prestaties van de client en vergroot de kans op onwaar positieven).</span><span class="sxs-lookup"><span data-stu-id="4e4ff-138">**High + blocking level** applies additional protection measures (might impact client performance and increase your chance of false positives).</span></span>
    - <span data-ttu-id="4e4ff-139">**Het blokkeringsniveau nul** tolerantie blokkeert alle onbekende uitvoerbare bestanden.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-139">**Zero tolerance blocking level** blocks all unknown executables.</span></span>
    
    > [!WARNING]
    > <span data-ttu-id="4e4ff-140">Hoewel het onwaarschijnlijk is dat u deze overstap naar **Hoog** of Hoog **+** inschakelt, kunnen sommige legitieme bestanden worden gedetecteerd (hoewel u de optie hebt om de blokkering te deblokkeren of te betwisten).</span><span class="sxs-lookup"><span data-stu-id="4e4ff-140">While unlikely, setting this switch to **High** or **High +** may cause some legitimate files to be detected (although you will have the option to unblock or dispute that detection).</span></span>

6. <span data-ttu-id="4e4ff-141">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-141">Click **OK**.</span></span>

7. <span data-ttu-id="4e4ff-142">Implementeer het bijgewerkte groepsbeleidsobject.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-142">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="4e4ff-143">Zie [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="4e4ff-143">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span></span>

> [!TIP]
> <span data-ttu-id="4e4ff-144">Gebruikt u on-premises groepsbeleidsobjecten?</span><span class="sxs-lookup"><span data-stu-id="4e4ff-144">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="4e4ff-145">Bekijk hoe ze vertalen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="4e4ff-145">See how they translate in the cloud.</span></span> <span data-ttu-id="4e4ff-146">[Analyseer uw on-premises groepsbeleidsobjecten met groepsbeleidsanalyse in Microsoft Endpoint Manager - Preview.](/mem/intune/configuration/group-policy-analytics)</span><span class="sxs-lookup"><span data-stu-id="4e4ff-146">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="4e4ff-147">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="4e4ff-147">Related articles</span></span>

- [<span data-ttu-id="4e4ff-148">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="4e4ff-148">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="4e4ff-149">Beveiliging via de cloud inschakelen</span><span class="sxs-lookup"><span data-stu-id="4e4ff-149">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4e4ff-150">Antimalware-beleid maken en implementeren: Cloudbeveiligingsservice</span><span class="sxs-lookup"><span data-stu-id="4e4ff-150">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)