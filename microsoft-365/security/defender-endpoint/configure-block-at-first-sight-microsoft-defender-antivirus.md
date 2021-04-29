---
title: Blok op het eerste gezicht inschakelen om malware binnen enkele seconden te detecteren
description: Schakel het blok op het eerste gezicht in om malware binnen enkele seconden te detecteren en te blokkeren.
keywords: scannen, blokkeren op het eerste gezicht, malware, first sight, cloud, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079201"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="8137b-104">Blokkeren op het eerste gezicht inschakelen</span><span class="sxs-lookup"><span data-stu-id="8137b-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8137b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8137b-105">**Applies to:**</span></span>

- [<span data-ttu-id="8137b-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8137b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8137b-107">In dit artikel wordt een antivirus-/antimalwarefunctie beschreven die 'blok op het eerste gezicht' wordt genoemd en wordt beschreven hoe u blokkering op het eerste gezicht voor uw organisatie kunt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="8137b-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="8137b-108">Dit artikel is bedoeld voor bedrijfsbeheerders en IT-professionals die beveiligingsinstellingen voor organisaties beheren.</span><span class="sxs-lookup"><span data-stu-id="8137b-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="8137b-109">Als u geen beheerder of IT-beheerder bent, maar u op het eerste gezicht vragen hebt over blokkering, zie Geen ondernemingsbeheerder of [IT-professional?](#not-an-enterprise-admin-or-it-pro).</span><span class="sxs-lookup"><span data-stu-id="8137b-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="8137b-110">Wat is 'blok op het eerste gezicht'?</span><span class="sxs-lookup"><span data-stu-id="8137b-110">What is "block at first sight"?</span></span>

<span data-ttu-id="8137b-111">Blokkering op het eerste gezicht is een bedreigingsbeveiligingsfunctie van de volgende generatie die nieuwe malware detecteert en deze binnen enkele seconden blokkeert.</span><span class="sxs-lookup"><span data-stu-id="8137b-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="8137b-112">Blokkeren op het eerste gezicht is ingeschakeld wanneer bepaalde beveiligingsinstellingen zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8137b-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="8137b-113">Deze instellingen zijn:</span><span class="sxs-lookup"><span data-stu-id="8137b-113">These settings include:</span></span>

- <span data-ttu-id="8137b-114">Beveiliging in de cloud;</span><span class="sxs-lookup"><span data-stu-id="8137b-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="8137b-115">Een opgegeven voorbeeldinzendings time-out (zoals 50 seconden); en</span><span class="sxs-lookup"><span data-stu-id="8137b-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="8137b-116">Een bestandsblokkeringsniveau van hoog.</span><span class="sxs-lookup"><span data-stu-id="8137b-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="8137b-117">In de meeste bedrijfsorganisaties zijn de instellingen die nodig zijn om blokkering op het eerste gezicht in te stellen, geconfigureerd met Microsoft Defender Antivirus-implementaties.</span><span class="sxs-lookup"><span data-stu-id="8137b-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="8137b-118">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="8137b-118">How it works</span></span>

<span data-ttu-id="8137b-119">Wanneer Microsoft Defender Antivirus een verdacht, maar niet-gedetecteerd bestand tegenkomt, wordt de back-over van onze cloudbeveiliging opgevraagd.</span><span class="sxs-lookup"><span data-stu-id="8137b-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="8137b-120">Met de cloudbackend worden heuristiek, machine learning en geautomatiseerde analyse van het bestand toegepast om te bepalen of de bestanden schadelijk zijn of niet.</span><span class="sxs-lookup"><span data-stu-id="8137b-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="8137b-121">Microsoft Defender Antivirus gebruikt meerdere detectie- en preventietechnologieën om nauwkeurige, intelligente en realtime beveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="8137b-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Lijst met MICROSOFT Defender AV-engines](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="8137b-123">Zie deze blog voor meer informatie: Maak kennis met de geavanceerde technologieën die centraal staan in de volgende generatie beveiliging van Microsoft Defender voor [Endpoint.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="8137b-123">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="8137b-124">Een paar dingen die u moet weten over blokkeren op het eerste gezicht</span><span class="sxs-lookup"><span data-stu-id="8137b-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="8137b-125">In Windows 10, versie 1803 of hoger, kan blokkering op het eerste gezicht niet-draagbare uitvoerbare bestanden (zoals JS, VBS of macro's) en uitvoerbare bestanden blokkeren.</span><span class="sxs-lookup"><span data-stu-id="8137b-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="8137b-126">Blokkeren gebruikt op het eerste gezicht alleen de back-mail voor cloudbeveiliging voor uitvoerbare bestanden en niet-draagbare uitvoerbare bestanden die van internet worden gedownload of die afkomstig zijn uit de internetzone.</span><span class="sxs-lookup"><span data-stu-id="8137b-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="8137b-127">Een hashwaarde van het EXE-bestand wordt gecontroleerd via de back-mail van de cloud om te bepalen of het bestand een eerder niet-gedetecteerd bestand is.</span><span class="sxs-lookup"><span data-stu-id="8137b-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="8137b-128">Als de cloudback-up geen bepaling kan maken, wordt het bestand vergrendeld door Microsoft Defender Antivirus en wordt een kopie naar de cloud geüpload.</span><span class="sxs-lookup"><span data-stu-id="8137b-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="8137b-129">De cloud voert meer analyses uit om tot een bepaling te komen voordat het bestand kan worden uitgevoerd of blokkeert in alle toekomstige ontmoetingen, afhankelijk van of het bestand schadelijk is of niet een bedreiging.</span><span class="sxs-lookup"><span data-stu-id="8137b-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="8137b-130">In veel gevallen kan dit proces de reactietijd voor nieuwe malware beperken van uren tot seconden.</span><span class="sxs-lookup"><span data-stu-id="8137b-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="8137b-131">U kunt [opgeven hoelang een bestand niet mag](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) worden uitgevoerd terwijl het bestand wordt geanalyseerd door de beveiligingsservice in de cloud.</span><span class="sxs-lookup"><span data-stu-id="8137b-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="8137b-132">En u kunt het bericht aanpassen dat op de [bureaubladen](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) van gebruikers wordt weergegeven wanneer een bestand wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="8137b-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="8137b-133">U kunt de bedrijfsnaam, contactgegevens en bericht-URL wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8137b-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="8137b-134">Blok op het eerste gezicht in- en uit- zetten met Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8137b-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="8137b-135">Microsoft Intune maakt nu deel uit van Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="8137b-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="8137b-136">Navigeer in het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () naar   >  **Apparatenconfiguratieprofielen.**</span><span class="sxs-lookup"><span data-stu-id="8137b-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="8137b-137">Selecteer of maak een profiel met het **profieltype Apparaatbeperkingen.**</span><span class="sxs-lookup"><span data-stu-id="8137b-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="8137b-138">Stel in **de configuratie-instellingen** voor het apparaatbeperkingenprofiel de volgende instellingen in of bevestig deze onder **Microsoft Defender Antivirus:**</span><span class="sxs-lookup"><span data-stu-id="8137b-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="8137b-139">**Beveiliging in de cloud:** ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="8137b-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="8137b-140">**Bestandsblokkeringsniveau:** hoog</span><span class="sxs-lookup"><span data-stu-id="8137b-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="8137b-141">**Tijdsextensie voor het scannen van bestanden door de cloud:** 50</span><span class="sxs-lookup"><span data-stu-id="8137b-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="8137b-142">**Gebruikers vragen vóór voorbeeldinzending:** Alle gegevens verzenden zonder dat u daarom wordt gevraagd</span><span class="sxs-lookup"><span data-stu-id="8137b-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Config in Intune](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="8137b-144">Sla uw instellingen op.</span><span class="sxs-lookup"><span data-stu-id="8137b-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="8137b-145">Als u het blokkeringsniveau voor bestanden **instelt op Hoog,** wordt een sterk detectieniveau toegepast.</span><span class="sxs-lookup"><span data-stu-id="8137b-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="8137b-146">In het onwaarschijnlijke geval dat bestandsblokkering een fout-positieve detectie van legitieme bestanden veroorzaakt, kan uw beveiligingsteam in quarantaine geplaatste bestanden [herstellen.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8137b-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="8137b-147">Zie Apparaatbeperkingen configureren in Microsoft Intune voor meer informatie over het configureren van beperkingen voor Microsoft Defender [Antivirus-apparaten in Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="8137b-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="8137b-148">Zie Apparaatbeperkingen voor [Windows 10 (en nieuwere) instellingen in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)voor een lijst met beperkingen voor Microsoft Defender Antivirus-apparaten in Intune.</span><span class="sxs-lookup"><span data-stu-id="8137b-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="8137b-149">Blok op het eerste gezicht in- en uit- zetten met Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="8137b-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="8137b-150">Als u op zoek bent naar Microsoft Endpoint Configuration Manager, is het nu onderdeel van Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="8137b-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="8137b-151">Ga in Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) naar **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="8137b-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="8137b-152">Selecteer een bestaand beleid of maak een nieuw beleid met het **profieltype Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="8137b-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="8137b-153">Stel de volgende configuratie-instellingen in of bevestig deze:</span><span class="sxs-lookup"><span data-stu-id="8137b-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="8137b-154">**Beveiliging in de cloud in- en uit-** zetten: Ja</span><span class="sxs-lookup"><span data-stu-id="8137b-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="8137b-155">**Beveiligingsniveau in de cloud:** hoog</span><span class="sxs-lookup"><span data-stu-id="8137b-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="8137b-156">**Defender Cloud Extended Timeout in Seconds**: 50</span><span class="sxs-lookup"><span data-stu-id="8137b-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Instellingen blokkeren op het eerste gezicht in Endpoint Manager":::

4. <span data-ttu-id="8137b-158">Het Microsoft Defender Antivirus-profiel toepassen op een groep, zoals **Alle gebruikers,** **Alle apparaten** of Alle gebruikers **en apparaten.**</span><span class="sxs-lookup"><span data-stu-id="8137b-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="8137b-159">Blok op het eerste gezicht in- en uit- zetten met Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="8137b-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="8137b-160">Het is raadzaam Intune of Microsoft Endpoint Manager te gebruiken om blok op het eerste gezicht in te zetten.</span><span class="sxs-lookup"><span data-stu-id="8137b-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="8137b-161">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.** [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="8137b-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="8137b-162">Ga met **de Editor voor groepsbeleidsbeheer** naar **Beheersjablonen voor**  >    >  **computerconfiguratie Windows Components** Microsoft Defender  >  **Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="8137b-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="8137b-163">Dubbelklik in de sectie KAARTEN op De functie **Blokkeren** op het eerste gezicht configureren en stel deze in op **Ingeschakeld** en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="8137b-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8137b-164">Als u **de instelling Altijd vragen (0) instelt,** wordt de beveiligingstoestand van het apparaat lager.</span><span class="sxs-lookup"><span data-stu-id="8137b-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="8137b-165">Instelling voor **Nooit verzenden (2)** betekent dat blok op het eerste gezicht niet werkt.</span><span class="sxs-lookup"><span data-stu-id="8137b-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="8137b-166">Dubbelklik in de sectie KAARTEN op Bestandsvoorbeelden verzenden wanneer verdere analyse **is** vereist en stel deze in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8137b-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="8137b-167">Selecteer **onder Bestandsvoorbeelden verzenden wanneer verdere analyse is vereist** de optie Alle **steekproeven verzenden** en selecteer **ok.**</span><span class="sxs-lookup"><span data-stu-id="8137b-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="8137b-168">U kunt het groepsbeleidsobject opnieuw in uw netwerk herschikken, zoals u gewoonlijk doet.</span><span class="sxs-lookup"><span data-stu-id="8137b-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="8137b-169">Op het eerste gezicht bevestigen dat blok is ingeschakeld op afzonderlijke clientapparaten</span><span class="sxs-lookup"><span data-stu-id="8137b-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="8137b-170">U kunt bevestigen dat blok op het eerste gezicht is ingeschakeld op afzonderlijke clientapparaten met de Windows Security-app.</span><span class="sxs-lookup"><span data-stu-id="8137b-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="8137b-171">Blok op het eerste gezicht wordt automatisch ingeschakeld, zolang beveiliging in de **cloud** en Automatische **voorbeeldinzending** beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8137b-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="8137b-172">Open de Windows Security-app.</span><span class="sxs-lookup"><span data-stu-id="8137b-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="8137b-173">Selecteer **Virusbeveiliging & bedreiging** en selecteer vervolgens onder **Virusbeveiliging**& instellingen voor bedreigingsbeveiliging de optie **Instellingen beheren.**</span><span class="sxs-lookup"><span data-stu-id="8137b-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Schermafbeelding van het label & beveiligingsinstellingen voor virussen in de Windows Security-app](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="8137b-175">Controleer of **beveiliging in de cloud en** Automatische **voorbeeldinzending** beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8137b-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="8137b-176">Als de vereiste instellingen zijn geconfigureerd en geïmplementeerd met groepsbeleid, zijn de instellingen die in deze sectie worden beschreven grijs en niet beschikbaar voor gebruik op afzonderlijke eindpunten.</span><span class="sxs-lookup"><span data-stu-id="8137b-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="8137b-177">Wijzigingen die zijn aangebracht via een groepsbeleidsobject, moeten eerst worden geïmplementeerd op afzonderlijke eindpunten voordat de instelling wordt bijgewerkt in Windows-instellingen.</span><span class="sxs-lookup"><span data-stu-id="8137b-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="8137b-178">Blok op het eerste gezicht valideren werkt</span><span class="sxs-lookup"><span data-stu-id="8137b-178">Validate block at first sight is working</span></span>

<span data-ttu-id="8137b-179">Als u wilt controleren of de functie werkt, volgt u de richtlijnen in Verbindingen tussen uw netwerk en [de cloud valideren.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="8137b-179">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="8137b-180">Blok op het eerste gezicht uitschakelen</span><span class="sxs-lookup"><span data-stu-id="8137b-180">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="8137b-181">Als u blokkering op het eerste gezicht uit schakelen, wordt de beveiligingstoestand van uw apparaat(en) en uw netwerk lager.</span><span class="sxs-lookup"><span data-stu-id="8137b-181">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="8137b-182">U kunt blokkering op het eerste gezicht uitschakelen als u de vereiste instellingen wilt behouden zonder blokkering op het eerste gezicht te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8137b-182">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="8137b-183">U kunt blokkering op het eerste gezicht tijdelijk uitschakelen om te zien hoe deze functie van invloed is op uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="8137b-183">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="8137b-184">Het is echter niet raadzaam om blokkering op het eerste gezicht permanent uit te uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="8137b-184">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="8137b-185">Blok op het eerste gezicht uitschakelen met Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="8137b-185">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="8137b-186">Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="8137b-186">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="8137b-187">Ga naar **Endpoint Security**  >  **Antivirus** en selecteer vervolgens uw Microsoft Defender Antivirusbeleid.</span><span class="sxs-lookup"><span data-stu-id="8137b-187">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="8137b-188">Kies **onder** Beheren de optie **Eigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="8137b-188">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="8137b-189">Kies naast **Configuratie-instellingen** de optie **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="8137b-189">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="8137b-190">Een of meer van de volgende instellingen wijzigen:</span><span class="sxs-lookup"><span data-stu-id="8137b-190">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="8137b-191">Stel **Beveiliging in de cloud in op** **Nee** of **Niet geconfigureerd.**</span><span class="sxs-lookup"><span data-stu-id="8137b-191">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="8137b-192">Stel **beveiligingsniveau in de cloud in** op Niet **geconfigureerd.**</span><span class="sxs-lookup"><span data-stu-id="8137b-192">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="8137b-193">Het selectievakje voor **defender cloud verlengde time-out in** seconden uit.</span><span class="sxs-lookup"><span data-stu-id="8137b-193">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="8137b-194">Controleer uw instellingen en sla deze op.</span><span class="sxs-lookup"><span data-stu-id="8137b-194">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="8137b-195">Blok op het eerste gezicht uitschakelen met Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="8137b-195">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="8137b-196">Open op uw groepsbeleidscomputer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="8137b-196">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="8137b-197">Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="8137b-197">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="8137b-198">Vouw de boom uit via **Windows-onderdelen**  >  **Microsoft Defender Antivirus**  >  **MAPS.**</span><span class="sxs-lookup"><span data-stu-id="8137b-198">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="8137b-199">Dubbelklik op **De functie 'Blokkeren op het eerste gezicht' configureren** en stel de optie in op **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8137b-199">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8137b-200">Door blokkering op het eerste gezicht uit te schakelen, wordt het vereiste groepsbeleid niet uitgeschakeld of gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="8137b-200">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="8137b-201">Geen ondernemingsbeheerder of IT-professional?</span><span class="sxs-lookup"><span data-stu-id="8137b-201">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="8137b-202">Als u geen ondernemingsbeheerder of IT-professional bent, maar u op het eerste gezicht vragen hebt over blokkering, is deze sectie voor u.</span><span class="sxs-lookup"><span data-stu-id="8137b-202">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="8137b-203">Blokkering op het eerste gezicht is een functie voor bedreigingsbeveiliging waarmee malware binnen enkele seconden wordt gedetecteerd en geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="8137b-203">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="8137b-204">Hoewel er op het eerste gezicht geen specifieke instelling met de naam 'Blokkeren' is, is de functie ingeschakeld wanneer bepaalde instellingen zijn geconfigureerd op uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="8137b-204">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="8137b-205">Blok beheren op het eerste gezicht in of uit op uw eigen apparaat</span><span class="sxs-lookup"><span data-stu-id="8137b-205">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="8137b-206">Als u een persoonlijk apparaat hebt dat niet door een organisatie wordt beheerd, vraagt u zich misschien af hoe u blok op het eerste gezicht in- of uit kunt schakelen.</span><span class="sxs-lookup"><span data-stu-id="8137b-206">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="8137b-207">U kunt de Windows Security-app gebruiken om blok op het eerste gezicht te beheren.</span><span class="sxs-lookup"><span data-stu-id="8137b-207">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="8137b-208">Open de Windows Security-app op uw Windows 10-computer.</span><span class="sxs-lookup"><span data-stu-id="8137b-208">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="8137b-209">Selecteer **Virusbeveiliging & bedreiging**.</span><span class="sxs-lookup"><span data-stu-id="8137b-209">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="8137b-210">Selecteer **onder Virusbeveiliging & instellingen** voor bedreigingsbeveiliging de optie **Instellingen beheren.**</span><span class="sxs-lookup"><span data-stu-id="8137b-210">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="8137b-211">Volg een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="8137b-211">Take one of the following steps:</span></span>

   - <span data-ttu-id="8137b-212">Als u blok op het eerste  gezicht wilt inschakelen, moet u ervoor zorgen dat zowel cloudbeveiliging als Automatische **voorbeeldinzending** beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8137b-212">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="8137b-213">Als u blokkering op het eerste gezicht wilt uitschakelen, schakelt u **beveiliging in** de cloud of **Automatische voorbeeldinzending uit.**</span><span class="sxs-lookup"><span data-stu-id="8137b-213">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="8137b-214">Als u blok op het eerste gezicht uit wilt schakelen, wordt het beveiligingsniveau voor uw apparaat verlaagd.</span><span class="sxs-lookup"><span data-stu-id="8137b-214">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="8137b-215">Het is niet raadzaam blok op het eerste gezicht permanent uit te uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="8137b-215">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="8137b-216">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8137b-216">See also</span></span>

- [<span data-ttu-id="8137b-217">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="8137b-217">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="8137b-218">Beveiliging via de cloud inschakelen</span><span class="sxs-lookup"><span data-stu-id="8137b-218">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8137b-219">Beschermd blijven met Windows-beveiliging</span><span class="sxs-lookup"><span data-stu-id="8137b-219">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)