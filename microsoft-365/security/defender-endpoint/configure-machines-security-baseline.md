---
title: Naleving van de beveiligingslijn van Microsoft Defender voor eindpunten verhogen
description: De beveiligingslijn van Microsoft Defender voor eindpunt stelt beveiligingsbesturingselementen in om optimale beveiliging te bieden.
keywords: Intune-beheer, Microsoft Defender voor Eindpunt, Microsoft Defender, Microsoft Defender voor Endpoint ASR, beveiligingslijn
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a5f3d2de452a8a1ab201f558b93d45dfa6ded3e6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841544"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="8243f-104">Naleving van de beveiligingslijn van Microsoft Defender voor eindpunten verhogen</span><span class="sxs-lookup"><span data-stu-id="8243f-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8243f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8243f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8243f-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8243f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8243f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8243f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8243f-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8243f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8243f-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8243f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="8243f-110">Beveiligingslijnlijnen zorgen ervoor dat beveiligingsfuncties zijn geconfigureerd op basis van richtlijnen van zowel beveiligingsdeskundigen als Windows systeembeheerders.</span><span class="sxs-lookup"><span data-stu-id="8243f-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="8243f-111">Wanneer de beveiligingslijn defender voor eindpunt wordt geïmplementeerd, stelt de beveiligingslijn Defender voor eindpuntbeveiligingsbesturingselementen in om optimale beveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="8243f-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="8243f-112">Lees deze veelgestelde vragen voor meer informatie over beveiligingslijnlijnen en hoe deze zijn toegewezen aan Intune met behulp [van configuratieprofielen.](/intune/security-baselines#q--a)</span><span class="sxs-lookup"><span data-stu-id="8243f-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="8243f-113">Voordat u compliance kunt implementeren en bijhouden naar beveiligingslijnlijnen:</span><span class="sxs-lookup"><span data-stu-id="8243f-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="8243f-114">Uw apparaten registreren voor Intune-beheer</span><span class="sxs-lookup"><span data-stu-id="8243f-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="8243f-115">Zorg ervoor dat u de benodigde machtigingen hebt</span><span class="sxs-lookup"><span data-stu-id="8243f-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a><span data-ttu-id="8243f-116">Vergelijk de Microsoft Defender voor Eindpunt en de Windows intune-beveiligingslijnlijnen</span><span class="sxs-lookup"><span data-stu-id="8243f-116">Compare the Microsoft Defender for Endpoint and the Windows Intune security baselines</span></span>
<span data-ttu-id="8243f-117">De Windows Beveiligingslijn van Intune bevat een uitgebreide set aanbevolen instellingen die nodig zijn om apparaten met Windows veilig te configureren, waaronder browserinstellingen, PowerShell-instellingen en instellingen voor sommige beveiligingsfuncties, zoals Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8243f-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="8243f-118">De basislijn van Defender voor eindpunt biedt daarentegen instellingen voor het optimaliseren van alle beveiligingsbesturingselementen in de Defender for Endpoint-stapel, inclusief instellingen voor eindpuntdetectie en -respons (EDR) en instellingen die ook worden gevonden in de beveiligingslijn van Windows Intune.</span><span class="sxs-lookup"><span data-stu-id="8243f-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="8243f-119">Zie voor meer informatie over elke basislijn:</span><span class="sxs-lookup"><span data-stu-id="8243f-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="8243f-120">Windows beveiligingslijninstellingen voor Intune</span><span class="sxs-lookup"><span data-stu-id="8243f-120">Windows security baseline settings for Intune</span></span>](/intune/security-baseline-settings-windows)
- [<span data-ttu-id="8243f-121">Basislijninstellingen voor Microsoft Defender voor Eindpunt voor Intune</span><span class="sxs-lookup"><span data-stu-id="8243f-121">Microsoft Defender for Endpoint baseline settings for Intune</span></span>](/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="8243f-122">In het ideale ideale moment worden apparaten die zijn aan boord van Defender voor Eindpunt, beide basislijnen geïmplementeerd: de beveiligingslijn Windows Intune om Windows in eerste instantie te beveiligen en vervolgens de beveiligingslijn van Defender voor eindpunt boven aan elkaar om de beveiligingsbesturingselementen van Defender voor eindpunten optimaal te configureren.</span><span class="sxs-lookup"><span data-stu-id="8243f-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="8243f-123">Als u wilt profiteren van de meest recente gegevens over risico's en bedreigingen en conflicten wilt minimaliseren naarmate basislijnen zich ontwikkelen, moet u altijd de meest recente versies van de basislijnen toepassen op alle producten zodra ze worden uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="8243f-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="8243f-124">De beveiligingslijn van Defender voor eindpunt is geoptimaliseerd voor fysieke apparaten en wordt momenteel niet aanbevolen voor gebruik op virtuele machine- of VDI-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="8243f-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="8243f-125">Bepaalde basislijninstellingen kunnen van invloed zijn op interactieve sessies op afstand in gevirtualiseerde omgevingen.</span><span class="sxs-lookup"><span data-stu-id="8243f-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="8243f-126">Naleving van de beveiligingslijn van Defender voor Eindpunt controleren</span><span class="sxs-lookup"><span data-stu-id="8243f-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="8243f-127">De **basislijnkaart** Beveiliging voor [apparaatconfiguratiebeheer](configure-machines.md) biedt een overzicht van de naleving op Windows 10 apparaten die zijn toegewezen aan de beveiligingslijn Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="8243f-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="8243f-128">![Beveiligingslijnkaart](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="8243f-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="8243f-129">*Kaart met naleving van de beveiligingslijn van Defender voor Eindpunt*</span><span class="sxs-lookup"><span data-stu-id="8243f-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="8243f-130">Elk apparaat krijgt een van de volgende statustypen:</span><span class="sxs-lookup"><span data-stu-id="8243f-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="8243f-131">**Komt overeen met basislijn**: apparaatinstellingen komen overeen met alle instellingen in de basislijn</span><span class="sxs-lookup"><span data-stu-id="8243f-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="8243f-132">**Komt niet overeen met basislijn:** ten minste één apparaatinstelling komt niet overeen met de basislijn</span><span class="sxs-lookup"><span data-stu-id="8243f-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="8243f-133">**Verkeerd geconfigureerd:** ten minste één basislijninstelling is niet correct geconfigureerd op het apparaat en heeft een conflict, fout of status in behandeling</span><span class="sxs-lookup"><span data-stu-id="8243f-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="8243f-134">**Niet van toepassing:** ten minste één basislijninstelling is niet van toepassing op het apparaat</span><span class="sxs-lookup"><span data-stu-id="8243f-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="8243f-135">Als u specifieke apparaten wilt controleren, **selecteert u Beveiligingslijn configureren** op de kaart.</span><span class="sxs-lookup"><span data-stu-id="8243f-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="8243f-136">Hiermee gaat u naar Intune-apparaatbeheer.</span><span class="sxs-lookup"><span data-stu-id="8243f-136">This takes you to Intune device management.</span></span> <span data-ttu-id="8243f-137">Selecteer vervolgens **Apparaatstatus voor** de namen en statussen van de apparaten.</span><span class="sxs-lookup"><span data-stu-id="8243f-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="8243f-138">Er kunnen verschillen zijn in samengevoegde gegevens die worden weergegeven op de pagina apparaatconfiguratiebeheer en die worden weergegeven op overzichtsschermen in Intune.</span><span class="sxs-lookup"><span data-stu-id="8243f-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="8243f-139">De beveiligingslijn van Microsoft Defender voor eindpunten controleren en toewijzen</span><span class="sxs-lookup"><span data-stu-id="8243f-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="8243f-140">Apparaatconfiguratiebeheer controleert alleen de naleving van basislijn van Windows 10 apparaten die specifiek zijn toegewezen aan de beveiligingslijn van Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="8243f-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="8243f-141">U kunt de basislijn eenvoudig bekijken en deze toewijzen aan apparaten op Intune-apparaatbeheer.</span><span class="sxs-lookup"><span data-stu-id="8243f-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="8243f-142">Selecteer **Beveiligingslijn configureren** op de **basislijnkaart** Beveiliging om naar Apparaatbeheer in Intune te gaan.</span><span class="sxs-lookup"><span data-stu-id="8243f-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="8243f-143">Er wordt een vergelijkbaar overzicht van de naleving van de basislijn weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8243f-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="8243f-144">U kunt ook naar de beveiligingslijn van Defender voor eindpunt in de Microsoft Azure-portal gaan vanuit Alle **services > Intune > Beveiligings- > Beveiligingslijnlijnen > Microsoft Defender ATP basislijn.**</span><span class="sxs-lookup"><span data-stu-id="8243f-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="8243f-145">Een nieuw profiel maken.</span><span class="sxs-lookup"><span data-stu-id="8243f-145">Create a new profile.</span></span>

   <span data-ttu-id="8243f-146">![Overzicht van beveiligingslijn van Microsoft Defender voor eindpunt op Intune](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="8243f-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="8243f-147">*Overzicht van beveiligingslijn van Microsoft Defender voor eindpunt op Intune*</span><span class="sxs-lookup"><span data-stu-id="8243f-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="8243f-148">Tijdens het maken van een profiel kunt u specifieke instellingen op de basislijn controleren en aanpassen.</span><span class="sxs-lookup"><span data-stu-id="8243f-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="8243f-149">![Opties voor beveiligingslijn tijdens het maken van een profiel op Intune](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="8243f-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="8243f-150">*Opties voor beveiligingslijn tijdens het maken van een profiel op Intune*</span><span class="sxs-lookup"><span data-stu-id="8243f-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="8243f-151">Wijs het profiel toe aan de juiste apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="8243f-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="8243f-152">![Beveiligingslijnprofielen op Intune](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="8243f-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="8243f-153">*Het beveiligingslijnprofiel toewijzen aan Intune*</span><span class="sxs-lookup"><span data-stu-id="8243f-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="8243f-154">Maak het profiel om het op te slaan en te implementeren in de toegewezen apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="8243f-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="8243f-155">![De beveiligingslijn toewijzen aan Intune](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="8243f-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="8243f-156">*Het beveiligingslijnprofiel maken op Intune*</span><span class="sxs-lookup"><span data-stu-id="8243f-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="8243f-157">Beveiligingslijnlijnen op Intune bieden een handige manier om uw apparaten volledig te beveiligen en te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="8243f-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="8243f-158">[Meer informatie over beveiligingslijnlijnen op Intune](/intune/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="8243f-158">[Learn more about security baselines on Intune](/intune/security-baselines).</span></span>

><span data-ttu-id="8243f-159">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8243f-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8243f-160">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8243f-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="8243f-161">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8243f-161">Related topics</span></span>
- [<span data-ttu-id="8243f-162">Controleren of uw apparaten juist zijn geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="8243f-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="8243f-163">Apparaten in gebruik nemen bij Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8243f-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="8243f-164">Asr-regelimplementatie en -detecties optimaliseren</span><span class="sxs-lookup"><span data-stu-id="8243f-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
