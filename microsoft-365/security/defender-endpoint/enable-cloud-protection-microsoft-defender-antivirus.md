---
title: Cloudbeveiliging inschakelen in Microsoft Defender Antivirus
description: Schakel cloudbezorgde beveiliging in om te profiteren van snelle en geavanceerde beveiligingsfuncties.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, cloud, blok op het eerste gezicht
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572055"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="a4f32-104">Door cloud geleverde beveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="a4f32-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a4f32-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a4f32-105">**Applies to:**</span></span>

- [<span data-ttu-id="a4f32-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a4f32-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="a4f32-107">De Microsoft Defender Antivirus cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging aan uw netwerk en eindpunten.</span><span class="sxs-lookup"><span data-stu-id="a4f32-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="a4f32-108">Hoewel het een cloudservice wordt genoemd, is het niet alleen bescherming voor bestanden die in de cloud zijn opgeslagen; In plaats daarvan gebruikt het gedistribueerde resources en machine learning om bescherming te bieden aan uw eind punten met een snelheid die veel sneller is dan traditionele updates voor beveiligings intelligentie.</span><span class="sxs-lookup"><span data-stu-id="a4f32-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="a4f32-109">Microsoft Defender Antivirus maakt gebruik van meerdere detectie- en preventietechnologieën om nauwkeurige, realtime en intelligente bescherming te bieden.</span><span class="sxs-lookup"><span data-stu-id="a4f32-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="a4f32-110">[Maak kennis met de geavanceerde technologieën in de kern van Microsoft Defender voor endpoint-beveiliging](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)van de volgende generatie .</span><span class="sxs-lookup"><span data-stu-id="a4f32-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="a4f32-111">U kunt Microsoft Defender Antivirus cloudbeveiliging op verschillende manieren in- of uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="a4f32-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="a4f32-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a4f32-112">Microsoft Intune</span></span>
- <span data-ttu-id="a4f32-113">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="a4f32-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="a4f32-114">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="a4f32-114">Group Policy</span></span>
- <span data-ttu-id="a4f32-115">PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a4f32-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="a4f32-116">U kunt het ook in- of uitschakelen bij afzonderlijke clients met de Windows-beveiliging-app.</span><span class="sxs-lookup"><span data-stu-id="a4f32-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="a4f32-117">Zie [Microsoft-cloudbeveiliging gebruiken](cloud-protection-microsoft-defender-antivirus.md) voor een overzicht van Microsoft Defender Antivirus cloudbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="a4f32-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="a4f32-118">Zie [Netwerkverbindingen configureren en valideren](configure-network-connections-microsoft-defender-antivirus.md)voor meer informatie over de specifieke vereisten voor netwerkverbindingen om ervoor te zorgen dat uw eind punten verbinding kunnen maken met de door de cloud geleverde beveiligingsservice.</span><span class="sxs-lookup"><span data-stu-id="a4f32-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a4f32-119">In Windows 10 is er geen verschil tussen de **basis-** en geavanceerde rapportageopties **die** in dit onderwerp worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="a4f32-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="a4f32-120">Dit is een verouderd onderscheid en het kiezen van een van beide instellingen resulteert in hetzelfde niveau van cloud-geleverde beveiliging.</span><span class="sxs-lookup"><span data-stu-id="a4f32-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="a4f32-121">Er is geen verschil in het type of de hoeveelheid informatie die wordt gedeeld.</span><span class="sxs-lookup"><span data-stu-id="a4f32-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="a4f32-122">Zie de [Privacyverklaring van Microsoft](https://go.microsoft.com/fwlink/?linkid=521839)voor meer informatie over wat we verzamelen.</span><span class="sxs-lookup"><span data-stu-id="a4f32-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="a4f32-123">Intune gebruiken om cloudbeveiliging in te schakelen</span><span class="sxs-lookup"><span data-stu-id="a4f32-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="a4f32-124">Ga naar het Microsoft Endpoint Manager admin center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) en log in.</span><span class="sxs-lookup"><span data-stu-id="a4f32-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="a4f32-125">Selecteer **apparaatconfiguratie > profielen** in het deelvenster **Start.**</span><span class="sxs-lookup"><span data-stu-id="a4f32-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="a4f32-126">Selecteer het profieltype **Apparaatbeperkingen** dat u wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="a4f32-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="a4f32-127">Zie [Apparaatbeperkingsinstellingen configureren in Microsoft Intune](/intune/device-restrictions-configure)als u een nieuw profieltype **Apparaatbeperkingen** wilt maken.</span><span class="sxs-lookup"><span data-stu-id="a4f32-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="a4f32-128">Instellingen **voor**  >  **eigenschappenconfiguratie selecteren:**  >  **Microsoft Defender Antivirus** bewerken.</span><span class="sxs-lookup"><span data-stu-id="a4f32-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="a4f32-129">Selecteer **Inschakelen op** de door de cloud **geleverde beveiligingsschakelaar** .</span><span class="sxs-lookup"><span data-stu-id="a4f32-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="a4f32-130">Selecteer **alle** gegevens automatisch verzenden in de vervolgkeuzelijst Gebruikers vragen vóór het indienen van **voorbeelden.**</span><span class="sxs-lookup"><span data-stu-id="a4f32-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="a4f32-131">Zie [Wat zijn Microsoft Intune apparaatprofielen voor](/intune/device-profiles) meer informatie over Intune-apparaatprofielen, inclusief het maken en configureren van hun instellingen.</span><span class="sxs-lookup"><span data-stu-id="a4f32-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="a4f32-132">Gebruik Microsoft Endpoint Manager om cloudbeveiliging in te schakelen</span><span class="sxs-lookup"><span data-stu-id="a4f32-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="a4f32-133">Ga naar het Microsoft Endpoint Manager admin center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) en log in.</span><span class="sxs-lookup"><span data-stu-id="a4f32-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="a4f32-134">Kies **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="a4f32-135">Selecteer een antivirusprofiel.</span><span class="sxs-lookup"><span data-stu-id="a4f32-135">Select an antivirus profile.</span></span> <span data-ttu-id="a4f32-136">(Als u er nog geen hebt of als u een nieuw profiel wilt maken, raadpleegt u [Instellingen voor apparaatbeperking configureren in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="a4f32-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="a4f32-137">Selecteer **Eigenschappen**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-137">Select **Properties**.</span></span> <span data-ttu-id="a4f32-138">Kies vervolgens naast **Configuratie-instellingen** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="a4f32-139">Vouw **Cloudbeveiliging** uit en selecteer vervolgens in de lijst **met beschermingsniveaus** die in de cloud worden geleverd een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="a4f32-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="a4f32-140">**Hoog**: Past een sterk detectieniveau toe.</span><span class="sxs-lookup"><span data-stu-id="a4f32-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="a4f32-141">**Hoog plus:** gebruikt het **hoge** niveau en past aanvullende beschermingsmaatregelen toe (kan de prestaties van de klant beïnvloeden).</span><span class="sxs-lookup"><span data-stu-id="a4f32-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="a4f32-142">**Nultolerantie:** Blokkeert alle onbekende uitvoerbare bestanden.</span><span class="sxs-lookup"><span data-stu-id="a4f32-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="a4f32-143">Selecteer **Controleren + opslaan** en kies Opslaan . </span><span class="sxs-lookup"><span data-stu-id="a4f32-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="a4f32-144">Zie Antimalwarebeleid maken en implementeren voor meer informatie over het configureren van [Microsoft Endpoint Configuration Manager: Cloudbeveiligingsservice](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span><span class="sxs-lookup"><span data-stu-id="a4f32-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="a4f32-145">Groepsbeleid gebruiken om cloudbeveiliging in te schakelen</span><span class="sxs-lookup"><span data-stu-id="a4f32-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="a4f32-146">Open op uw apparaat voor groepsbeleidsbeheer de [Console voor groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))en klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="a4f32-147">Ga in de **Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="a4f32-148">Selecteer **Beheersjablonen**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="a4f32-149">De structuur uitvouwen om **onderdelen > Microsoft Defender Antivirus > MAPS te Windows**</span><span class="sxs-lookup"><span data-stu-id="a4f32-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="a4f32-150">Dubbelklik op **Deelnemen aan Microsoft MAPS**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="a4f32-151">Zorg ervoor dat de optie is ingeschakeld en is ingesteld op **BasisKAARTEN** of **Geavanceerde MAPS**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="a4f32-152">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-152">Select **OK**.</span></span>

6. <span data-ttu-id="a4f32-153">Dubbelklik op **Bestandsvoorbeelden verzenden wanneer verdere analyse vereist is**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="a4f32-154">Zorg ervoor dat de eerste optie is ingesteld **op Ingeschakeld** en dat de andere opties zijn ingesteld op:</span><span class="sxs-lookup"><span data-stu-id="a4f32-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="a4f32-155">**Stuur veilige monsters** (1)</span><span class="sxs-lookup"><span data-stu-id="a4f32-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="a4f32-156">**Stuur alle monsters** (3)</span><span class="sxs-lookup"><span data-stu-id="a4f32-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="a4f32-157">De optie **Veilige monsters verzenden** (1) betekent dat de meeste monsters automatisch worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="a4f32-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="a4f32-158">Bestanden die waarschijnlijk persoonlijke informatie bevatten, worden nog steeds gevraagd en vereisen extra bevestiging.</span><span class="sxs-lookup"><span data-stu-id="a4f32-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="a4f32-159">Als u de optie **instelt op Altijd vragen** (0), wordt de beveiligingsstatus van het apparaat verlaagd.</span><span class="sxs-lookup"><span data-stu-id="a4f32-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="a4f32-160">Als u deze instelt op **Nooit verzenden** (2), werkt de functie Blokkeren bij het [eerste zicht](configure-block-at-first-sight-microsoft-defender-antivirus.md) van Microsoft Defender voor eindpunt niet.</span><span class="sxs-lookup"><span data-stu-id="a4f32-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="a4f32-161">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="a4f32-162">PowerShell-cmdlets gebruiken om door de cloud geleverde beveiliging in te schakelen</span><span class="sxs-lookup"><span data-stu-id="a4f32-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="a4f32-163">De volgende cmdlets kunnen door de cloud geleverde beveiliging inschakelen:</span><span class="sxs-lookup"><span data-stu-id="a4f32-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="a4f32-164">Zie [PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus- en Defender-cmdlets te configureren en](use-powershell-cmdlets-microsoft-defender-antivirus.md) [](/powershell/module/defender/)uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a4f32-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="a4f32-165">[Beleid CSP - Defender](/windows/client-management/mdm/policy-csp-defender) heeft ook meer informatie specifiek over [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span><span class="sxs-lookup"><span data-stu-id="a4f32-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="a4f32-166">U kunt **ook -SubmitSamplesConsent** instellen op `SendSafeSamples` (de standaardinstelling), `NeverSend` of `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="a4f32-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="a4f32-167">De `SendSafeSamples` instelling betekent dat de meeste monsters automatisch worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="a4f32-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="a4f32-168">Bestanden die waarschijnlijk persoonlijke informatie bevatten, worden nog steeds gevraagd en vereisen extra bevestiging.</span><span class="sxs-lookup"><span data-stu-id="a4f32-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="a4f32-169">Instelling **-SubmitSamplesConsent** naar `NeverSend` of verlaagt het `AlwaysPrompt` beveiligingsniveau van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a4f32-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="a4f32-170">Bovendien betekent het instellen `NeverSend` dat de functie Blokkeren op het eerste [zicht](configure-block-at-first-sight-microsoft-defender-antivirus.md) van Microsoft Defender voor eindpunt niet werkt.</span><span class="sxs-lookup"><span data-stu-id="a4f32-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="a4f32-171">Gebruik Windows Management Instruction (WMI) om cloudbeveiliging in te schakelen</span><span class="sxs-lookup"><span data-stu-id="a4f32-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="a4f32-172">Gebruik de methode [ **Set** van de](/previous-versions/windows/desktop/defender/set-msft-mppreference) klasse MSFT_MpPreference voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="a4f32-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="a4f32-173">Zie [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) voor meer informatie over toegestane parameters</span><span class="sxs-lookup"><span data-stu-id="a4f32-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="a4f32-174">Cloudbeveiliging inschakelen voor individuele clients met de Windows-beveiliging-app</span><span class="sxs-lookup"><span data-stu-id="a4f32-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="a4f32-175">Als de **instelling Lokale instelling configureren voor het rapporteren van Microsoft MAPS** Group Policy is ingesteld op **Uitgeschakeld,** wordt de **cloudbeveiligingsinstelling** in Windows Instellingen grijs weergegeven en niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a4f32-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="a4f32-176">Wijzigingen die zijn aangebracht via een groepsbeleidsobject, moeten eerst worden geïmplementeerd op afzonderlijke eindpunten voordat de instelling wordt bijgewerkt in de Windows-instellingen.</span><span class="sxs-lookup"><span data-stu-id="a4f32-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="a4f32-177">Open de Windows-beveiliging app door het schildpictogram in de taakbalk te selecteren of door in het startmenu te zoeken naar **Defender**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="a4f32-178">Selecteer de tegel **Virus & bedreigingsbeveiliging** (of het schildpictogram in de linkermenubalk) en vervolgens het label **Virus & bedreigingsbeveiligingsinstellingen:**</span><span class="sxs-lookup"><span data-stu-id="a4f32-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Schermafbeelding van het instellingenlabel voor virus- en bedreigingsbeveiliging in de app voor Windows-beveiliging](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="a4f32-180">Controleer of **Cloudgebaseerde beveiliging** en **automatische voorbeeldinzending** zijn ingeschakeld **op Aan**.</span><span class="sxs-lookup"><span data-stu-id="a4f32-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="a4f32-181">Als automatische voorbeeldinzending is geconfigureerd met Groepsbeleid, wordt de instelling grijs weergegeven en is deze niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a4f32-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a4f32-182">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="a4f32-182">Related articles</span></span>

- [<span data-ttu-id="a4f32-183">De time-outperiode voor cloudblokkering configureren</span><span class="sxs-lookup"><span data-stu-id="a4f32-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a4f32-184">Blok op het eerste gezicht configureren</span><span class="sxs-lookup"><span data-stu-id="a4f32-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a4f32-185">PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus te beheren</span><span class="sxs-lookup"><span data-stu-id="a4f32-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="a4f32-186">[Help Windows pc's beveiligen met Endpoint Protection voor Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="a4f32-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="a4f32-187">Verdediger cmdlets</span><span class="sxs-lookup"><span data-stu-id="a4f32-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="a4f32-188">Microsoft-cloudbeveiliging gebruiken in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a4f32-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a4f32-189">Antimalwarebeleid maken en implementeren: cloudbeveiligingsservice</span><span class="sxs-lookup"><span data-stu-id="a4f32-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="a4f32-190">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="a4f32-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
