---
title: Blok op het eerste gezicht inschakelen om malware binnen enkele seconden te detecteren
description: Schakel het blok op het eerste gezicht in om malware binnen enkele seconden te detecteren en te blokkeren.
keywords: scan, BAFS, malware, first seen, first sight, cloud, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 837b7899368e69b274323125c97169bbe4f823b7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690761"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="c6b6a-104">Blok op het eerste gezicht in-</span><span class="sxs-lookup"><span data-stu-id="c6b6a-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c6b6a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-105">**Applies to:**</span></span>

- [<span data-ttu-id="c6b6a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c6b6a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c6b6a-107">Blokkeren op het eerste gezicht biedt een manier om nieuwe malware binnen enkele seconden te detecteren en te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-107">Block at first sight provides a way to detect and block new malware within seconds.</span></span> <span data-ttu-id="c6b6a-108">Deze beveiliging is standaard ingeschakeld wanneer bepaalde vereisteninstellingen zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-108">This protection is enabled by default when certain prerequisite settings are enabled.</span></span> <span data-ttu-id="c6b6a-109">Deze instellingen omvatten beveiliging in de cloud, een opgegeven voorbeeldinzendings time-out (zoals 50 seconden) en een hoog bestandsblokkeringsniveau.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-109">These settings include cloud-delivered protection, a specified sample submission timeout (such as 50 seconds), and a file-blocking level of high.</span></span> <span data-ttu-id="c6b6a-110">In de meeste bedrijfsorganisaties zijn deze instellingen standaard ingeschakeld met Microsoft Defender Antivirus-implementaties.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-110">In most enterprise organizations, these settings are enabled by default with Microsoft Defender Antivirus deployments.</span></span> 

<span data-ttu-id="c6b6a-111">U kunt [opgeven hoelang een bestand niet mag](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) worden uitgevoerd terwijl het bestand wordt geanalyseerd door de beveiligingsservice in de cloud.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-111">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="c6b6a-112">En u kunt het bericht aanpassen dat op de [bureaubladen](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) van gebruikers wordt weergegeven wanneer een bestand wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-112">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="c6b6a-113">U kunt de bedrijfsnaam, contactgegevens en bericht-URL wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-113">You can change the company name, contact information, and message URL.</span></span>

>[!TIP]
><span data-ttu-id="c6b6a-114">Ga naar de demowebsite van [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Microsoft Defender voor Eindpunt demo.wd.microsoft.com om te bevestigen dat de functies werken en te zien hoe ze werken.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-114">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="c6b6a-115">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="c6b6a-115">How it works</span></span>

<span data-ttu-id="c6b6a-116">Wanneer Microsoft Defender Antivirus een verdacht, maar niet-gedetecteerd bestand tegenkomt, wordt de back-over van onze cloudbeveiliging opgevraagd.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-116">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="c6b6a-117">Met de cloudbackend worden heuristiek, machine learning en geautomatiseerde analyse van het bestand toegepast om te bepalen of de bestanden schadelijk zijn of niet.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-117">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="c6b6a-118">Microsoft Defender Antivirus gebruikt meerdere detectie- en preventietechnologieën om nauwkeurige, intelligente en realtime beveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-118">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> <span data-ttu-id="c6b6a-119">Zie deze blog voor meer informatie: Maak kennis met de geavanceerde technologieën die centraal staan in de volgende generatie beveiliging van Microsoft Defender voor [Endpoint.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="c6b6a-119">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="c6b6a-120">![Lijst met MICROSOFT Defender AV-engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="c6b6a-120">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="c6b6a-121">In Windows 10, versie 1803 of hoger, kan blokkering op het eerste gezicht niet-draagbare uitvoerbare bestanden (zoals JS, VBS of macro's) en uitvoerbare bestanden blokkeren.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-121">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) as well as executable files.</span></span>

<span data-ttu-id="c6b6a-122">Blokkeren gebruikt op het eerste gezicht alleen de back-mail voor cloudbeveiliging voor uitvoerbare bestanden en niet-draagbare uitvoerbare bestanden die van internet worden gedownload of die afkomstig zijn uit de internetzone.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-122">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="c6b6a-123">Een hashwaarde van het EXE-bestand wordt gecontroleerd via de back-mail van de cloud om te bepalen of het bestand een eerder niet-gedetecteerd bestand is.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-123">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

<span data-ttu-id="c6b6a-124">Als de cloudback-up geen bepaling kan maken, wordt het bestand vergrendeld door Microsoft Defender Antivirus en wordt een kopie naar de cloud geüpload.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-124">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="c6b6a-125">De cloud voert extra analyses uit om tot een bepaling te komen voordat het bestand kan worden uitgevoerd of blokkeert in alle toekomstige ontmoetingen, afhankelijk van of het bestand schadelijk of veilig is.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-125">The cloud performs additional analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or safe.</span></span>

<span data-ttu-id="c6b6a-126">In veel gevallen kan dit proces de reactietijd voor nieuwe malware beperken van uren tot seconden.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-126">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="c6b6a-127">Blok op het eerste gezicht in- en uit- zetten met Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c6b6a-127">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="c6b6a-128">Microsoft Intune maakt nu deel uit van Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-128">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="c6b6a-129">Navigeer in het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () naar   >  **Apparatenconfiguratieprofielen.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-129">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="c6b6a-130">Selecteer of maak een profiel met het **profieltype Apparaatbeperkingen.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-130">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="c6b6a-131">Stel in **de configuratie-instellingen** voor het apparaatbeperkingenprofiel de volgende instellingen in of bevestig deze onder **Microsoft Defender Antivirus:**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-131">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="c6b6a-132">**Beveiliging in de cloud:** ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="c6b6a-132">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="c6b6a-133">**Bestandsblokkeringsniveau:** hoog</span><span class="sxs-lookup"><span data-stu-id="c6b6a-133">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="c6b6a-134">**Tijdsextensie voor het scannen van bestanden door de cloud:** 50</span><span class="sxs-lookup"><span data-stu-id="c6b6a-134">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="c6b6a-135">**Gebruikers vragen vóór voorbeeldinzending:** Alle gegevens verzenden zonder dat u daarom wordt gevraagd</span><span class="sxs-lookup"><span data-stu-id="c6b6a-135">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Config in Intune](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="c6b6a-137">Sla uw instellingen op.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-137">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="c6b6a-138">Als u het blokkeringsniveau voor bestanden **instelt op Hoog,** wordt een sterk detectieniveau toegepast.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-138">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="c6b6a-139">In het onwaarschijnlijke geval dat bestandsblokkering een fout-positieve detectie van legitieme bestanden veroorzaakt, kunt u [in quarantaine geplaatste](./restore-quarantined-files-microsoft-defender-antivirus.md)bestanden herstellen.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-139">In the unlikely event that file blocking causes a false positive detection of legitimate files, you can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="c6b6a-140">Zie Apparaatbeperkingen configureren in Microsoft Intune voor meer informatie over het configureren van beperkingen voor Microsoft Defender [Antivirus-apparaten in Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="c6b6a-140">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="c6b6a-141">Zie Apparaatbeperkingen voor [Windows 10 (en nieuwere) instellingen in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)voor een lijst met beperkingen voor Microsoft Defender Antivirus-apparaten in Intune.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-141">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="c6b6a-142">Blok op het eerste gezicht in- en uit- zetten met Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="c6b6a-142">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="c6b6a-143">Als u op zoek bent naar Microsoft Endpoint Configuration Manager, is het nu onderdeel van Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-143">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="c6b6a-144">Ga in Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) naar **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-144">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="c6b6a-145">Selecteer een bestaand beleid of maak een nieuw beleid met het **profieltype Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-145">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="c6b6a-146">Stel de volgende configuratie-instellingen in of bevestig deze:</span><span class="sxs-lookup"><span data-stu-id="c6b6a-146">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="c6b6a-147">**Beveiliging in de cloud in- en uit-** zetten: Ja</span><span class="sxs-lookup"><span data-stu-id="c6b6a-147">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="c6b6a-148">**Beveiligingsniveau in de cloud:** hoog</span><span class="sxs-lookup"><span data-stu-id="c6b6a-148">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="c6b6a-149">**Defender Cloud Extended Timeout in Seconds**: 50</span><span class="sxs-lookup"><span data-stu-id="c6b6a-149">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Instellingen blokkeren op het eerste gezicht in Endpoint Manager":::

4. <span data-ttu-id="c6b6a-151">Het Microsoft Defender Antivirus-profiel toepassen op een groep, zoals **Alle gebruikers,** **Alle apparaten** of Alle gebruikers **en apparaten.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-151">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="c6b6a-152">Blok op het eerste gezicht in- en uit- zetten met Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="c6b6a-152">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="c6b6a-153">Het is raadzaam Intune of Microsoft Endpoint Manager te gebruiken om blok op het eerste gezicht in te zetten.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-153">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="c6b6a-154">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.** [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="c6b6a-154">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="c6b6a-155">Ga met **de Editor voor groepsbeleidsbeheer** naar **Beheersjablonen voor**  >    >  **computerconfiguratie Windows Components** Microsoft Defender  >  **Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-155">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="c6b6a-156">Dubbelklik in de sectie KAARTEN op De functie **Blokkeren** op het eerste gezicht configureren en stel deze in op **Ingeschakeld** en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-156">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c6b6a-157">Als u **de instelling Altijd vragen (0) instelt,** wordt de beveiligingstoestand van het apparaat lager.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-157">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="c6b6a-158">Instelling voor **Nooit verzenden (2)** betekent dat blok op het eerste gezicht niet werkt.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-158">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="c6b6a-159">Dubbelklik in de sectie KAARTEN op Bestandsvoorbeelden verzenden wanneer verdere analyse **is** vereist en stel deze in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-159">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="c6b6a-160">Selecteer **onder Bestandsvoorbeelden verzenden wanneer verdere analyse is vereist** de optie Alle **steekproeven verzenden** en klik vervolgens op **OK.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-160">Under **Send file samples when further analysis is required**, select **Send all samples**, and then click **OK**.</span></span>

5. <span data-ttu-id="c6b6a-161">Als u instellingen hebt gewijzigd, kunt u het groepsbeleidsobject opnieuw in uw netwerk herschikken om ervoor te zorgen dat alle eindpunten worden gedekt.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-161">If you changed any settings, redeploy the Group Policy Object across your network to ensure all endpoints are covered.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a><span data-ttu-id="c6b6a-162">Blok op het eerste gezicht bevestigen is ingeschakeld voor afzonderlijke clients</span><span class="sxs-lookup"><span data-stu-id="c6b6a-162">Confirm block at first sight is enabled on individual clients</span></span>

<span data-ttu-id="c6b6a-163">U kunt bevestigen dat blok op het eerste gezicht is ingeschakeld voor afzonderlijke clients met windows-beveiligingsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-163">You can confirm that block at first sight is enabled on individual clients using Windows security settings.</span></span>

<span data-ttu-id="c6b6a-164">Blok op het eerste gezicht wordt automatisch ingeschakeld, zolang beveiliging in de **cloud** en Automatische **voorbeeldinzending** beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-164">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="c6b6a-165">Open de Windows Security-app.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-165">Open the Windows Security app.</span></span>

2. <span data-ttu-id="c6b6a-166">Selecteer **Virusbeveiliging & bedreiging** en selecteer vervolgens onder **Virusbeveiliging**& instellingen voor bedreigingsbeveiliging de optie **Instellingen beheren.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-166">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Schermafbeelding van het label & beveiligingsinstellingen voor virussen in de Windows Security-app](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="c6b6a-168">Controleer of **beveiliging in de cloud en** Automatische **voorbeeldinzending** beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-168">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="c6b6a-169">Als de vereiste instellingen zijn geconfigureerd en geïmplementeerd met groepsbeleid, zijn de instellingen die in deze sectie worden beschreven grijs en niet beschikbaar voor gebruik op afzonderlijke eindpunten.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-169">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="c6b6a-170">Wijzigingen die zijn aangebracht via een groepsbeleidsobject, moeten eerst worden geïmplementeerd op afzonderlijke eindpunten voordat de instelling wordt bijgewerkt in Windows-instellingen.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-170">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="c6b6a-171">Blok op het eerste gezicht valideren werkt</span><span class="sxs-lookup"><span data-stu-id="c6b6a-171">Validate block at first sight is working</span></span>

<span data-ttu-id="c6b6a-172">Als u wilt controleren of de functie werkt, volgt u de richtlijnen in Verbindingen tussen uw netwerk en [de cloud valideren.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="c6b6a-172">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="c6b6a-173">Blok op het eerste gezicht uitschakelen</span><span class="sxs-lookup"><span data-stu-id="c6b6a-173">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="c6b6a-174">Als u blokkering op het eerste gezicht uit schakelen, wordt de beveiligingstoestand van uw apparaat(en) en uw netwerk lager.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-174">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="c6b6a-175">U kunt blokkering op het eerste gezicht uitschakelen als u de vereiste instellingen wilt behouden zonder blokkering op het eerste gezicht te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-175">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="c6b6a-176">U kunt blokkering op het eerste gezicht tijdelijk uitschakelen als u latentieproblemen ondervindt of als u de invloed van de functie op uw netwerk wilt testen.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-176">You might do temporarily turn block at first sight off if you are experiencing latency issues or you want to test the feature's impact on your network.</span></span> <span data-ttu-id="c6b6a-177">Het is echter niet raadzaam om blokkering op het eerste gezicht permanent uit te uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-177">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="c6b6a-178">Blok op het eerste gezicht uitschakelen met Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="c6b6a-178">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="c6b6a-179">Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-179">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="c6b6a-180">Ga naar **Endpoint Security**  >  **Antivirus** en selecteer vervolgens uw Microsoft Defender Antivirusbeleid.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-180">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="c6b6a-181">Kies **onder** Beheren de optie **Eigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-181">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="c6b6a-182">Kies naast **Configuratie-instellingen** de optie **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-182">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="c6b6a-183">Een of meer van de volgende instellingen wijzigen:</span><span class="sxs-lookup"><span data-stu-id="c6b6a-183">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="c6b6a-184">Stel **Beveiliging in de cloud in op** **Nee** of **Niet geconfigureerd.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-184">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="c6b6a-185">Stel **beveiligingsniveau in de cloud in** op Niet **geconfigureerd.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-185">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="c6b6a-186">Het vak **Verlengde time-out** defender cloud in seconden uit.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-186">Clear the **Defender Cloud Extended Timeout In Seconds** box.</span></span>

6. <span data-ttu-id="c6b6a-187">Controleer uw instellingen en sla deze op.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-187">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="c6b6a-188">Blok op het eerste gezicht uitschakelen met Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="c6b6a-188">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="c6b6a-189">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik vervolgens op **Bewerken.** [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="c6b6a-189">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="c6b6a-190">Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en klik op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-190">Using the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="c6b6a-191">Vouw de boom uit via **Windows-onderdelen**  >  **Microsoft Defender Antivirus**  >  **MAPS.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-191">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="c6b6a-192">Dubbelklik op **De functie 'Blokkeren op het eerste gezicht' configureren** en stel de optie in op **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="c6b6a-192">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c6b6a-193">Door blokkering op het eerste gezicht uit te schakelen, wordt het vereiste groepsbeleid niet uitgeschakeld of gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="c6b6a-193">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6b6a-194">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c6b6a-194">See also</span></span>

- [<span data-ttu-id="c6b6a-195">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="c6b6a-195">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="c6b6a-196">Beveiliging via de cloud inschakelen</span><span class="sxs-lookup"><span data-stu-id="c6b6a-196">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)