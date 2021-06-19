---
title: Blokkeren bij eerste detectie inschakelen om malware binnen enkele seconden te detecteren
description: De blokkeren bij eerste detectiefunctie inschakelen om malware binnen enkele seconden te detecteren en te blokkeren.
keywords: scannen, blokkeren bij eerste detectie, malware, eerste detectie, cloud, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/17/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a6bcc023571e544819ae7f276e6c3af5c1fc1335
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007394"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="8f76b-104">Blokkeren bij eerste detectie inschakelen</span><span class="sxs-lookup"><span data-stu-id="8f76b-104">Turn on block at first sight</span></span>

<span data-ttu-id="8f76b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8f76b-105">**Applies to:**</span></span>

- [<span data-ttu-id="8f76b-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8f76b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8f76b-107">In dit artikel wordt een antivirus-/antimalwarefunctie beschreven genaamd 'blokkeren bij eerste detectie' en wordt beschreven hoe u blokkeren bij eerste detectie in kunt schakelen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="8f76b-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="8f76b-108">Dit artikel is bedoeld voor bedrijfsbeheerders en IT-professionals die beveiligingsinstellingen voor organisaties beheren.</span><span class="sxs-lookup"><span data-stu-id="8f76b-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="8f76b-109">Zie [Geen ondernemingsbeheerder of IT-professional?](#not-an-enterprise-admin-or-it-pro) als u geen ondernemingsbeheerder of IT-professional bent, maar toch vragen hebt over blokkering bij eerste detectie.</span><span class="sxs-lookup"><span data-stu-id="8f76b-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see the [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro) section.</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="8f76b-110">Wat is 'blokkeren bij eerste detectie'?</span><span class="sxs-lookup"><span data-stu-id="8f76b-110">What is "block at first sight"?</span></span>

<span data-ttu-id="8f76b-111">Blokkeren bij eerste detectie is een bedreigingsbeveiligingsfunctie van volgende generatie-beveiliging waarmee nieuwe malware wordt gedetecteerd en binnen enkele seconden wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="8f76b-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="8f76b-112">Blokkering bij eerste detectie is ingeschakeld wanneer bepaalde beveiligingsinstellingen zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8f76b-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="8f76b-113">Deze instellingen omvatten:</span><span class="sxs-lookup"><span data-stu-id="8f76b-113">These settings include:</span></span>

- <span data-ttu-id="8f76b-114">cloudbeveiliging;</span><span class="sxs-lookup"><span data-stu-id="8f76b-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="8f76b-115">een opgegeven time-out voor sample indienen (zoals 50 seconden); en</span><span class="sxs-lookup"><span data-stu-id="8f76b-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="8f76b-116">een hoog bestandsblokkeringsniveau.</span><span class="sxs-lookup"><span data-stu-id="8f76b-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="8f76b-117">In de meeste ondernemingen zijn de instellingen geconfigureerd die nodig zijn om blokkeren bij eerste detectie mogelijk te maken met implementaties van Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8f76b-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="8f76b-118">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="8f76b-118">How it works</span></span>

<span data-ttu-id="8f76b-119">Als Microsoft Defender Antivirus een verdacht, maar niet-gedetecteerd bestand aantreft, wordt een query uitgevoerd op onze cloudbeveiligingsback-end.</span><span class="sxs-lookup"><span data-stu-id="8f76b-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="8f76b-120">In de cloudback-end worden heuristische, machine learning- en geautomatiseerde analyses van het bestand toegepast om te bepalen of de bestanden schadelijk zijn dan wel geen bedreiging vormen.</span><span class="sxs-lookup"><span data-stu-id="8f76b-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="8f76b-121">Microsoft Defender Antivirus gebruikt meerdere technologieën voor detectie en preventie om nauwkeurige, intelligente en realtime bescherming te bieden.</span><span class="sxs-lookup"><span data-stu-id="8f76b-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Lijst met AV-engines voor Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="8f76b-123">Lees deze blog voor meer informatie: [Maak kennis met de geavanceerde technologieën die de kern vormen van de volgende generatie-beveiliging van Microsoft Defender voor Eindpunt](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span><span class="sxs-lookup"><span data-stu-id="8f76b-123">To learn more, see [(Blog) Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="8f76b-124">Enkele dingen die u moet weten over blokkeren bij eerste detectie</span><span class="sxs-lookup"><span data-stu-id="8f76b-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="8f76b-125">In Windows 10, versie 1803 of hoger, kunnen door blokkeren bij eerste detectie niet-draagbare uitvoerbare bestanden (zoals JS-, VBS- of macro's) en uitvoerbare bestanden worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="8f76b-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="8f76b-126">Blokkeren bij eerste detectie maakt alleen gebruik van de cloudbeveiligingsback-end voor uitvoerbare bestanden en niet-draagbare uitvoerbare bestanden die van het internet worden gedownload of die afkomstig zijn uit de Internetzone.</span><span class="sxs-lookup"><span data-stu-id="8f76b-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="8f76b-127">Een hashwaarde van het EXE-bestand wordt gecontroleerd via de cloudback-end om te bepalen of het bestand een eerder niet-gedetecteerd bestand is.</span><span class="sxs-lookup"><span data-stu-id="8f76b-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="8f76b-128">Als er in de cloudback-end geen bepaling kan worden gemaakt, vergrendelt Microsoft Defender Antivirus het bestand en uploadt het een kopie naar de cloud.</span><span class="sxs-lookup"><span data-stu-id="8f76b-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="8f76b-129">De cloud voert meer analyses uit om te bepalen of het bestand kan worden uitgevoerd dan wel dient te worden geblokkeerd in alle toekomstige gevallen, afhankelijk van of het bestand schadelijk is dan wel geen bedreiging vormt.</span><span class="sxs-lookup"><span data-stu-id="8f76b-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="8f76b-130">In veel gevallen kan dit proces de reactietijd voor nieuwe malware verminderen van uren tot seconden.</span><span class="sxs-lookup"><span data-stu-id="8f76b-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="8f76b-131">U kunt [opgeven hoelang een bestand niet mag worden uitgevoerd](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) terwijl de cloudbeveiligingsservice het bestand analyseert.</span><span class="sxs-lookup"><span data-stu-id="8f76b-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="8f76b-132">En u kunt [het bericht aanpassen dat wordt weergegeven op de desktopcomputers van gebruikers](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) wanneer een bestand wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="8f76b-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="8f76b-133">U kunt de bedrijfsnaam, contactgegevens en bericht-URL wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8f76b-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="8f76b-134">Blokkeren bij eerste detectie inschakelen met Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8f76b-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="8f76b-135">Microsoft Intune maakt nu deel uit van Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="8f76b-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="8f76b-136">Navigeer in het beheercentrum van Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) naar **Apparaten** > **Configuratieprofielen**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="8f76b-137">Selecteer of maak een profiel met het **Apparaatbeperkingen** profieltype.</span><span class="sxs-lookup"><span data-stu-id="8f76b-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="8f76b-138">Stel in of bevestig in **Configuratie-instellingen** voor het apparaatbeperkingenprofiel de volgende instellingen onder **Microsoft Defender Antivirus**:</span><span class="sxs-lookup"><span data-stu-id="8f76b-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="8f76b-139">**Cloudbeveiliging**: Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="8f76b-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="8f76b-140">**Niveau voor bestandsblokkering**: Hoog</span><span class="sxs-lookup"><span data-stu-id="8f76b-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="8f76b-141">**Tijdsextensie voor het scannen van bestanden door de cloud**: 50</span><span class="sxs-lookup"><span data-stu-id="8f76b-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="8f76b-142">**Gebruikers vragen vóór sample indienen**: Alle gegevens verzenden zonder te vragen</span><span class="sxs-lookup"><span data-stu-id="8f76b-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   :::image type="content" source="../../media/intune-block-at-first-sight.png" alt-text="Intune-configuratie blokkeren bij eerste detectie":::

4. <span data-ttu-id="8f76b-144">Sla de instellingen op.</span><span class="sxs-lookup"><span data-stu-id="8f76b-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="8f76b-145">Door het niveau voor bestandsblokkering in te stellen op **Hoog** wordt een sterk detectieniveau toegepast.</span><span class="sxs-lookup"><span data-stu-id="8f76b-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="8f76b-146">In het onwaarschijnlijke geval dat bestandsblokkering een fout-positieve detectie van legitieme bestanden veroorzaakt, kan uw beveiligingsteam [bestanden in quarantaine herstellen](./restore-quarantined-files-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="8f76b-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="8f76b-147">Zie voor meer informatie over het configureren van apparaatbeperkingen voor Microsoft Defender Antivirus in Intune [Instellingen voor apparaatbeperkingen configureren in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="8f76b-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="8f76b-148">Zie [Apparaatbeperkingsinstellingen in Intune voor Windows 10 (en hoger)](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)voor een lijst met apparaatbeperkingen in Intune voor Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8f76b-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="8f76b-149">Blokkeren bij eerste detectie inschakelen met Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="8f76b-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="8f76b-150">Als u op zoek bent naar Microsoft Endpoint Configuration Manager: het maakt nu deel uit van Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="8f76b-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="8f76b-151">Ga in Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) naar **Eindpuntbeveiliging** > **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="8f76b-152">Selecteer een bestaand beleid of maak een nieuw beleid met het **Microsoft Defender Antivirus**-profieltype.</span><span class="sxs-lookup"><span data-stu-id="8f76b-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="8f76b-153">Stel de volgende configuratie-instellingen in of bevestig deze:</span><span class="sxs-lookup"><span data-stu-id="8f76b-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="8f76b-154">**Cloudbeveiliging inschakelen**: Ja</span><span class="sxs-lookup"><span data-stu-id="8f76b-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="8f76b-155">**Cloudbeveiligingsniveau**: Hoog</span><span class="sxs-lookup"><span data-stu-id="8f76b-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="8f76b-156">**Defender Cloud Extended Timeout in seconden**: 50</span><span class="sxs-lookup"><span data-stu-id="8f76b-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Blokkeren bij eerste detectie-instellingen in Endpoint Manager":::

4. <span data-ttu-id="8f76b-158">Pas het Microsoft Defender Antivirus-profiel toe op een groep, zoals **Alle gebruikers**, **Alle apparaten** of **Alle gebruikers en apparaten**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="8f76b-159">Blokkeren bij eerste detectie inschakelen met Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="8f76b-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="8f76b-160">U wordt aangeraden Intune of Microsoft Endpoint Manager te gebruiken om blokkeren bij eerste detectie in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="8f76b-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="8f76b-161">Open op uw computer voor groepsbeleidsbeheer de [Groepsbeleidsbeheerconsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="8f76b-162">Met de **Groepsbeleidsbeheerseditor** gaat u naar **Computerconfiguratie** > **Beheersjablonen** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="8f76b-163">Dubbelklik in de sectie MAPS op **De functie 'Blokkeren bij eerste detectie' configureren**, stel deze in op **Ingeschakeld** en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8f76b-164">Als u **Altijd vragen (0)** inschakelt, wordt de beveiligingstoestand van het apparaat verlaagd.</span><span class="sxs-lookup"><span data-stu-id="8f76b-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="8f76b-165">Instellen op **Verzend nooit (2)** betekent dat blokkeren bij eerste detectie niet werkt.</span><span class="sxs-lookup"><span data-stu-id="8f76b-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="8f76b-166">Dubbelklik in de sectie MAPS op **Bestandsvoorbeelden verzenden wanneer verdere analyse vereist is** en stel dit in op **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="8f76b-167">Selecteer **Bestandsvoorbeelden verzenden wanneer verdere analyse vereist is** **Alle voorbeelden verzenden** en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="8f76b-168">Implementeer uw groepsbeleidsobject opnieuw in uw netwerk, zoals u dat gewoonlijk doet.</span><span class="sxs-lookup"><span data-stu-id="8f76b-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="8f76b-169">Bevestigen dat blokkeren bij eerste detectie is ingeschakeld op afzonderlijke clientapparaten</span><span class="sxs-lookup"><span data-stu-id="8f76b-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="8f76b-170">U kunt met de app voor Windows-beveiliging bevestigen dat blokkeren bij eerste detectie is ingeschakeld op afzonderlijke clientapparaten.</span><span class="sxs-lookup"><span data-stu-id="8f76b-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="8f76b-171">Blokkeren bij eerste detectie wordt automatisch ingeschakeld mits **Cloudbeveiliging** en **Automatisch sample indienen** beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8f76b-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="8f76b-172">Open de app voor Windows-beveiliging.</span><span class="sxs-lookup"><span data-stu-id="8f76b-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="8f76b-173">Selecteer **Beveiliging tegen virussen en bedreigingen** en selecteer vervolgens onder **Instellingen voor virus- en bedreigingsbeveiliging** de optie **Instellingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Schermafbeelding van het instellingenlabel voor virus- en bedreigingsbeveiliging in de app voor Windows-beveiliging":::

3. <span data-ttu-id="8f76b-175">Controleer of **Cloudbeveiliging** en **Automatisch sample indienen** beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8f76b-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="8f76b-176">Als de vereiste instellingen zijn geconfigureerd en geïmplementeerd via groepsbeleid, worden de instellingen die in deze sectie worden beschreven, grijs gemaakt en zijn ze niet beschikbaar voor gebruik op afzonderlijke eindpunten.</span><span class="sxs-lookup"><span data-stu-id="8f76b-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="8f76b-177">Wijzigingen die zijn aangebracht via een groepsbeleidsobject, moeten eerst worden geïmplementeerd op afzonderlijke eindpunten voordat de instelling wordt bijgewerkt in de Windows-instellingen.</span><span class="sxs-lookup"><span data-stu-id="8f76b-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="8f76b-178">Controleren of blokkeren bij eerste detectie werkt</span><span class="sxs-lookup"><span data-stu-id="8f76b-178">Validate block at first sight is working</span></span>

<span data-ttu-id="8f76b-179">Als u wilt controleren of de functie werkt, downloadt u het voorbeeldbestand [Blokkeren bij eerste detectie](https://demo.wd.microsoft.com/Page/BAFS).</span><span class="sxs-lookup"><span data-stu-id="8f76b-179">To validate that the feature is working, download the [Block at first sight sample file](https://demo.wd.microsoft.com/Page/BAFS).</span></span> <span data-ttu-id="8f76b-180">Als u het bestand wilt downloaden, hebt u een account in Azure AD nodig waaraan de rol Beveiligingsbeheerder of Globale beheerder is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="8f76b-180">To download the file, you will need an account in Azure AD that has either the Security Administrator or Global Administrator role assigned.</span></span>

<span data-ttu-id="8f76b-181">Als u wilt controleren of de met de cloud ingeschakelde beveiliging werkt, volgt u de richtlijnen in [Verbindingen tussen uw netwerk en de cloud valideren](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span><span class="sxs-lookup"><span data-stu-id="8f76b-181">To validate that cloud-enabled protection is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span> 

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="8f76b-182">Blokkeren bij eerste detectie uitschakelen</span><span class="sxs-lookup"><span data-stu-id="8f76b-182">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="8f76b-183">Als u blokkeren bij eerste detectie uitschakelt, wordt de beveiligingstoestand van uw apparaat(en) en uw netwerk verlaagd.</span><span class="sxs-lookup"><span data-stu-id="8f76b-183">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="8f76b-184">U kunt blokkering bij eerste detectie uitschakelen als u de vereiste instellingen wilt behouden zonder daadwerkelijk blokkering bij eerste detectie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8f76b-184">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="8f76b-185">U kunt blokkeren bij eerste detectie tijdelijk uitschakelen om te zien wat de invloed van deze functie is op uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="8f76b-185">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="8f76b-186">Het wordt echter afgeraden de blokkeren bij eerste detectiebeveiliging permanent uit te uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="8f76b-186">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="8f76b-187">Blokkeren bij eerste detectie uitschakelen met Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="8f76b-187">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="8f76b-188">Ga naar het Beheercentrum van Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="8f76b-188">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="8f76b-189">Ga naar **Eindpuntbeveiliging** > **Antivirus** en selecteer vervolgens uw Microsoft Defender Antivirus-beleid.</span><span class="sxs-lookup"><span data-stu-id="8f76b-189">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="8f76b-190">Klik onder **Beheren** op **Eigenschappen**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-190">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="8f76b-191">Kies na **Configuratie-instellingen** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-191">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="8f76b-192">Wijzig een of meer van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="8f76b-192">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="8f76b-193">Zet **Cloudbeveiliging instellen** op **Nee** of **Niet geconfigureerd**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-193">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="8f76b-194">Stel **Cloudbeveiligingsniveau** in op **Niet geconfigureerd**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-194">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="8f76b-195">Schakel het selectievakje uit voor **Defender Cloud Extended Timeout in seconden**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-195">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="8f76b-196">Controleer uw instellingen en sla deze op.</span><span class="sxs-lookup"><span data-stu-id="8f76b-196">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="8f76b-197">Blokkeren bij eerste detectie uitschakelen met Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="8f76b-197">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="8f76b-198">Open op uw computer voor groepsbeleidsbeheer de [Groepsbeleidsbeheerconsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer vervolgens **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-198">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="8f76b-199">Ga via **Groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-199">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="8f76b-200">Vouw de boomstructuur uit via **Windows-onderdelen** > **Microsoft Defender Antivirus** > **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-200">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="8f76b-201">Dubbelklik op **De functie 'Blokkeren bij eerste detectie' configureren** en stel de optie in op **Uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-201">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8f76b-202">Als u blokkeren bij eerste detectie uitschakelt, wordt het vereiste groepsbeleid niet uitgeschakeld of gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="8f76b-202">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="8f76b-203">Bent u geen ondernemingsbeheerder of IT-professional?</span><span class="sxs-lookup"><span data-stu-id="8f76b-203">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="8f76b-204">Als u geen ondernemingsbeheerder of IT-professional bent, maar vragen hebt over blokkeren bij eerste detectie, is deze sectie iets voor u.</span><span class="sxs-lookup"><span data-stu-id="8f76b-204">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="8f76b-205">Blokkeren bij eerste detectie is een bedreigingsbeveiligingsfunctie waarmee malware wordt gedetecteerd en geblokkeerd binnen enkele seconden.</span><span class="sxs-lookup"><span data-stu-id="8f76b-205">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="8f76b-206">Hoewel er geen specifieke instelling met de naam 'Blokkeren bij eerste detectie' is, is de functie ingeschakeld wanneer bepaalde instellingen op uw apparaat zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="8f76b-206">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="8f76b-207">Blokkeren bij eerste detectie met of zonder uw eigen apparaat beheren</span><span class="sxs-lookup"><span data-stu-id="8f76b-207">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="8f76b-208">Als u een persoonlijk apparaat hebt dat niet wordt beheerd door een organisatie, vraagt u zich misschien af hoe u blokkeren bij eerste detectie in- of uit moet schakelen.</span><span class="sxs-lookup"><span data-stu-id="8f76b-208">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="8f76b-209">U kunt blokkeren bij eerste detectie beheren met de app voor Windows-beveiliging.</span><span class="sxs-lookup"><span data-stu-id="8f76b-209">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="8f76b-210">Open de app voor Windows-beveiliging op uw Windows 10-computer.</span><span class="sxs-lookup"><span data-stu-id="8f76b-210">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="8f76b-211">Selecteer **Virus- & bedreigingsbeveiliging**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-211">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="8f76b-212">Selecteer onder **Virus- & bedreigingsbeveiliging**,**Instellingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="8f76b-212">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="8f76b-213">Voer een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="8f76b-213">Take one of the following steps:</span></span>

   - <span data-ttu-id="8f76b-214">Als u blokkeren bij eerste detectie wilt inschakelen, moet u er voor zorgen dat **Cloudbeveiliging** en **Automatisch sample indienen** beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8f76b-214">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="8f76b-215">Als u blokkeren bij eerste detectie wilt uitschakelen, schakelt u **Cloudbeveiliging** of **Automatisch sample indienen** uit.</span><span class="sxs-lookup"><span data-stu-id="8f76b-215">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="8f76b-216">Door blokkeren bij eerste detectie uit te schakelen, verlaagt u het beveiligingsniveau voor uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="8f76b-216">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="8f76b-217">Het wordt echter afgeraden blokkeren bij eerste detectie permanent uit te uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="8f76b-217">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="8f76b-218">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8f76b-218">See also</span></span>

- [<span data-ttu-id="8f76b-219">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="8f76b-219">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="8f76b-220">Cloudbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="8f76b-220">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8f76b-221">Beveiligd blijven met Windows-beveiliging</span><span class="sxs-lookup"><span data-stu-id="8f76b-221">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
