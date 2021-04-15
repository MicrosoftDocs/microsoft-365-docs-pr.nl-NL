---
title: Beveiliging in de cloud in microsoft Defender Antivirus in te zetten
description: Schakel beveiliging in de cloud in om te profiteren van snelle en geavanceerde beveiligingsfuncties.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, cloud, blok op het eerste gezicht
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 9f949a4cb54ca5dd64a2648bb05a5cb9ad50e44d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764961"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="bd962-104">Door cloud geleverde beveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="bd962-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bd962-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bd962-105">**Applies to:**</span></span>

- [<span data-ttu-id="bd962-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="bd962-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="bd962-107">De Microsoft Defender Antivirus-cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging aan uw netwerk en eindpunten.</span><span class="sxs-lookup"><span data-stu-id="bd962-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="bd962-108">Hoewel het een cloudservice wordt genoemd, is het niet alleen beveiliging voor bestanden die zijn opgeslagen in de cloud. in plaats van gedistribueerde resources en machine learning te gebruiken om uw eindpunten te beschermen tegen een snelheid die veel sneller is dan traditionele beveiligingsintelligentie-updates.</span><span class="sxs-lookup"><span data-stu-id="bd962-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="bd962-109">Microsoft Defender Antivirus gebruikt meerdere detectie- en preventietechnologieën om nauwkeurige, realtime en intelligente beveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="bd962-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="bd962-110">[Maak gebruik van de geavanceerde technologieën die de kern van Microsoft Defender voor endpoint-beveiliging](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)van de volgende generatie zijn.</span><span class="sxs-lookup"><span data-stu-id="bd962-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="bd962-111">![Lijst met MICROSOFT Defender AV-engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="bd962-111">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="bd962-112">U kunt beveiliging in de cloud van Microsoft Defender Antivirus op verschillende manieren in- of uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="bd962-112">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="bd962-113">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bd962-113">Microsoft Intune</span></span>
- <span data-ttu-id="bd962-114">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bd962-114">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="bd962-115">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="bd962-115">Group Policy</span></span>
- <span data-ttu-id="bd962-116">PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="bd962-116">PowerShell cmdlets.</span></span>

 <span data-ttu-id="bd962-117">U kunt de app ook in- of uitschakelen in afzonderlijke clients met de Windows Security-app.</span><span class="sxs-lookup"><span data-stu-id="bd962-117">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="bd962-118">Zie [Microsoft Cloud-beveiliging gebruiken](cloud-protection-microsoft-defender-antivirus.md) voor een overzicht van beveiliging in de cloud van Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="bd962-118">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="bd962-119">Zie Netwerkverbindingen configureren en valideren voor meer informatie over de specifieke vereisten voor netwerkconnectiviteit om ervoor te zorgen dat uw eindpunten verbinding kunnen maken met de door de cloud geleverde [beveiligingsservice.](configure-network-connections-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="bd962-119">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bd962-120">In Windows 10 is er  geen  verschil tussen de opties Voor basisrapportage en Geavanceerde rapportage die in dit onderwerp worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="bd962-120">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="bd962-121">Dit is een verouderd onderscheid en als u een instelling kiest, wordt hetzelfde niveau van beveiliging in de cloud geleverd.</span><span class="sxs-lookup"><span data-stu-id="bd962-121">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="bd962-122">Er is geen verschil in het type of de hoeveelheid informatie die wordt gedeeld.</span><span class="sxs-lookup"><span data-stu-id="bd962-122">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="bd962-123">Zie de Privacyverklaring van Microsoft voor meer informatie over wat we [verzamelen.](https://go.microsoft.com/fwlink/?linkid=521839)</span><span class="sxs-lookup"><span data-stu-id="bd962-123">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="bd962-124">Intune gebruiken om beveiliging via de cloud in te zetten</span><span class="sxs-lookup"><span data-stu-id="bd962-124">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="bd962-125">Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="bd962-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="bd962-126">Selecteer in **het deelvenster** Start de optie **Apparaatconfiguratie > Profielen.**</span><span class="sxs-lookup"><span data-stu-id="bd962-126">On the **Home** pane, select **Device configuration > Profiles**.</span></span>
3. <span data-ttu-id="bd962-127">Selecteer het **profieltype Apparaatbeperkingen** dat u wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="bd962-127">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="bd962-128">Zie **Apparaatbeperkingsinstellingen** configureren in Microsoft [Intune](/intune/device-restrictions-configure)als u een nieuw profieltype Apparaatbeperkingen wilt maken.</span><span class="sxs-lookup"><span data-stu-id="bd962-128">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
4. <span data-ttu-id="bd962-129">Selecteer **Instellingen voor**  >  **eigenschappenconfiguratie: Microsoft** Defender Antivirus  >  **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="bd962-129">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>
5. <span data-ttu-id="bd962-130">Selecteer **Inschakelen** op de schakelknop Beveiliging in de cloud.</span><span class="sxs-lookup"><span data-stu-id="bd962-130">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>
6. <span data-ttu-id="bd962-131">Selecteer in **de vervolgkeuze van** Gebruikers vragen vóór voorbeeldinzending de optie **Alle gegevens automatisch verzenden.**</span><span class="sxs-lookup"><span data-stu-id="bd962-131">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="bd962-132">Zie Wat zijn Microsoft Intune-apparaatprofielen? voor meer informatie over [Intune-apparaatprofielen,](/intune/device-profiles) waaronder hoe u hun instellingen kunt maken en configureren.</span><span class="sxs-lookup"><span data-stu-id="bd962-132">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="bd962-133">Microsoft Endpoint Manager gebruiken om beveiliging via de cloud in te zetten</span><span class="sxs-lookup"><span data-stu-id="bd962-133">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="bd962-134">Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="bd962-134">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="bd962-135">Kies **Endpoint Security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="bd962-135">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="bd962-136">Selecteer een antivirusprofiel.</span><span class="sxs-lookup"><span data-stu-id="bd962-136">Select an antivirus profile.</span></span> <span data-ttu-id="bd962-137">(Als u nog geen profiel hebt of als u een nieuw profiel wilt maken, zie Apparaatbeperkingsinstellingen [configureren in Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="bd962-137">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
4. <span data-ttu-id="bd962-138">Selecteer **Eigenschappen**.</span><span class="sxs-lookup"><span data-stu-id="bd962-138">Select **Properties**.</span></span> <span data-ttu-id="bd962-139">Kies vervolgens naast **Configuratie-instellingen** de optie **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="bd962-139">Then, next to **Configuration settings**, choose **Edit**.</span></span>
5. <span data-ttu-id="bd962-140">Vouw **Cloudbeveiliging uit** en  selecteer een van de volgende opties in de lijst beveiligingsniveau in de cloud:</span><span class="sxs-lookup"><span data-stu-id="bd962-140">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
    1. <span data-ttu-id="bd962-141">**Hoog:** Hiermee wordt een sterk detectieniveau toegepast.</span><span class="sxs-lookup"><span data-stu-id="bd962-141">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="bd962-142">**Hoog plus:** gebruikt het **hoge** niveau en past extra beveiligingsmaatregelen toe (mogelijk van invloed op de prestaties van de client).</span><span class="sxs-lookup"><span data-stu-id="bd962-142">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="bd962-143">**Nul tolerantie:** blokkeert alle onbekende uitvoerbare bestanden.</span><span class="sxs-lookup"><span data-stu-id="bd962-143">**Zero tolerance**: Blocks all unknown executables.</span></span>
6. <span data-ttu-id="bd962-144">Selecteer **Controleren+ opslaan** en kies **vervolgens Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="bd962-144">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="bd962-145">Zie Antimalware-beleid maken en implementeren voor meer informatie over het configureren van Microsoft Endpoint Configuration [Manager: Cloudbeveiligingsservice.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)</span><span class="sxs-lookup"><span data-stu-id="bd962-145">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="bd962-146">Groepsbeleid gebruiken om beveiliging via de cloud in te zetten</span><span class="sxs-lookup"><span data-stu-id="bd962-146">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="bd962-147">Open op uw apparaat voor [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="bd962-147">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="bd962-148">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="bd962-148">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="bd962-149">Selecteer **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="bd962-149">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="bd962-150">De structuur uitbreiden naar **Windows-onderdelen > Microsoft Defender Antivirus > MAPS**</span><span class="sxs-lookup"><span data-stu-id="bd962-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="bd962-151">Dubbelklik op **Deelnemen aan Microsoft MAPS.**</span><span class="sxs-lookup"><span data-stu-id="bd962-151">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="bd962-152">Controleer of de optie is ingeschakeld en ingesteld op **BasisKAARTEN** of **Geavanceerde KAARTEN.**</span><span class="sxs-lookup"><span data-stu-id="bd962-152">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="bd962-153">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd962-153">Select **OK**.</span></span>

6. <span data-ttu-id="bd962-154">Dubbelklik op **Bestandsvoorbeelden verzenden wanneer verdere analyse vereist is.**</span><span class="sxs-lookup"><span data-stu-id="bd962-154">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="bd962-155">Controleer of de eerste optie is ingesteld op **Ingeschakeld** en of de andere opties zijn ingesteld op:</span><span class="sxs-lookup"><span data-stu-id="bd962-155">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="bd962-156">**Veilige steekproeven verzenden** (1)</span><span class="sxs-lookup"><span data-stu-id="bd962-156">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="bd962-157">**Alle steekproeven verzenden** (3)</span><span class="sxs-lookup"><span data-stu-id="bd962-157">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="bd962-158">De **optie Veilige steekproeven** verzenden (1) betekent dat de meeste steekproeven automatisch worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="bd962-158">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="bd962-159">Bestanden die waarschijnlijk persoonlijke gegevens bevatten, worden nog steeds gevraagd en moeten extra worden bevestigd.</span><span class="sxs-lookup"><span data-stu-id="bd962-159">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

        > [!WARNING]
        > <span data-ttu-id="bd962-160">Als u de optie Altijd **vragen** (0) instelt, wordt de beveiligingstoestand van het apparaat lager.</span><span class="sxs-lookup"><span data-stu-id="bd962-160">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="bd962-161">Als u dit **instelt op** [](configure-block-at-first-sight-microsoft-defender-antivirus.md) Nooit verzenden (2) betekent dit dat de functie Blokkeren op het eerste gezicht van Microsoft Defender voor Eindpunt niet werkt.</span><span class="sxs-lookup"><span data-stu-id="bd962-161">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="bd962-162">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd962-162">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="bd962-163">PowerShell-cmdlets gebruiken om beveiliging via de cloud in te zetten</span><span class="sxs-lookup"><span data-stu-id="bd962-163">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="bd962-164">Met de volgende cmdlets kunt u beveiliging in de cloud in- en uit- zetten:</span><span class="sxs-lookup"><span data-stu-id="bd962-164">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="bd962-165">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/)te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="bd962-165">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="bd962-166">[Beleid CSP - Defender](/windows/client-management/mdm/policy-csp-defender) heeft ook meer informatie specifiek over [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span><span class="sxs-lookup"><span data-stu-id="bd962-166">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="bd962-167">U kunt ook **SubmitSamplesConsent instellen** op `SendSafeSamples` (de standaardinstelling), `NeverSend` of `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="bd962-167">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="bd962-168">De `SendSafeSamples` instelling betekent dat de meeste voorbeelden automatisch worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="bd962-168">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="bd962-169">Bestanden die waarschijnlijk persoonlijke gegevens bevatten, worden nog steeds gevraagd en moeten extra worden bevestigd.</span><span class="sxs-lookup"><span data-stu-id="bd962-169">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="bd962-170">Instelling **-SubmitSamplesConsent** to `NeverSend` or will lower the protection level of the `AlwaysPrompt` device.</span><span class="sxs-lookup"><span data-stu-id="bd962-170">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="bd962-171">Bovendien betekent het instellen dat de functie Blokkeren op het eerste gezicht van Microsoft Defender voor Eindpunt `NeverSend` niet werkt. [](configure-block-at-first-sight-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="bd962-171">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="bd962-172">Windows Management Instruction (WMI) gebruiken om beveiliging via de cloud in te zetten</span><span class="sxs-lookup"><span data-stu-id="bd962-172">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="bd962-173">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="bd962-173">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="bd962-174">Zie [WINDOWS Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) voor meer informatie over toegestane parameters.</span><span class="sxs-lookup"><span data-stu-id="bd962-174">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="bd962-175">Beveiliging in de cloud in te stellen voor afzonderlijke clients met de Windows Security-app</span><span class="sxs-lookup"><span data-stu-id="bd962-175">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="bd962-176">Als de instelling Lokale instelling configureren voor het rapporteren van microsoft  MAPS-groepsbeleid is ingesteld op **Uitgeschakeld,** is de instelling voor cloudbeveiliging in Windows-instellingen grijs en niet beschikbaar. </span><span class="sxs-lookup"><span data-stu-id="bd962-176">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="bd962-177">Wijzigingen die zijn aangebracht via een groepsbeleidsobject, moeten eerst worden geïmplementeerd op afzonderlijke eindpunten voordat de instelling wordt bijgewerkt in Windows-instellingen.</span><span class="sxs-lookup"><span data-stu-id="bd962-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="bd962-178">Open de Windows Security-app door het schildpictogram op de taakbalk te selecteren of door in het startmenu voor Defender te **zoeken.**</span><span class="sxs-lookup"><span data-stu-id="bd962-178">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="bd962-179">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en vervolgens het label & instellingen voor **bedreigingsbeveiliging:**</span><span class="sxs-lookup"><span data-stu-id="bd962-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Schermafbeelding van het label & beveiligingsinstellingen voor virussen in de Windows Security-app](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="bd962-181">Controleer of **cloudbeveiliging en** automatische voorbeeldinzending zijn overgeschakeld op  **Aan.**</span><span class="sxs-lookup"><span data-stu-id="bd962-181">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="bd962-182">Als automatische voorbeeldinzending is geconfigureerd met Groepsbeleid, is de instelling grijs en niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="bd962-182">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bd962-183">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="bd962-183">Related articles</span></span>

- [<span data-ttu-id="bd962-184">De time-outperiode voor cloudblokkering configureren</span><span class="sxs-lookup"><span data-stu-id="bd962-184">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="bd962-185">Blok configureren op het eerste gezicht</span><span class="sxs-lookup"><span data-stu-id="bd962-185">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="bd962-186">PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus te beheren</span><span class="sxs-lookup"><span data-stu-id="bd962-186">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="bd962-187">[Windows-pc's beveiligen met Endpoint Protection voor Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="bd962-187">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="bd962-188">Defender-cmdlets</span><span class="sxs-lookup"><span data-stu-id="bd962-188">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="bd962-189">Microsoft Cloud-beveiliging gebruiken in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="bd962-189">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="bd962-190">Antimalware-beleid maken en implementeren: Cloudbeveiligingsservice</span><span class="sxs-lookup"><span data-stu-id="bd962-190">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="bd962-191">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="bd962-191">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)