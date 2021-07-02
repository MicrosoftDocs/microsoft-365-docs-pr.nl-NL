---
title: Indicatoren voor bestanden maken
ms.reviewer: ''
description: Maak indicatoren voor een bestandshash die de detectie, preventie en uitsluiting van entiteiten definieert.
keywords: bestand, hash, beheren, toegestaan, geblokkeerd, blokkeren, schoon, schadelijk, bestandshash, ip-adres, url's, domein
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256913"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="b4df9-104">Indicatoren voor bestanden maken</span><span class="sxs-lookup"><span data-stu-id="b4df9-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b4df9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b4df9-105">**Applies to:**</span></span>
- [<span data-ttu-id="b4df9-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b4df9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b4df9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4df9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="b4df9-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b4df9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b4df9-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="b4df9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="b4df9-110">Voorkom verdere verspreiding van een aanval in uw organisatie door potentieel schadelijke bestanden of vermoedelijke malware te verbieden.</span><span class="sxs-lookup"><span data-stu-id="b4df9-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="b4df9-111">Als u een potentieel schadelijk bestand voor draagbaar uitvoerbaar (PE) kent, kunt u dit blokkeren.</span><span class="sxs-lookup"><span data-stu-id="b4df9-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="b4df9-112">Deze bewerking voorkomt dat deze wordt gelezen, geschreven of uitgevoerd op apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b4df9-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="b4df9-113">U kunt op drie manieren indicatoren voor bestanden maken:</span><span class="sxs-lookup"><span data-stu-id="b4df9-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="b4df9-114">Door een indicator te maken via de pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="b4df9-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="b4df9-115">Door een contextuele indicator te maken met behulp van de knop Indicator toevoegen op de pagina met bestandsgegevens</span><span class="sxs-lookup"><span data-stu-id="b4df9-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="b4df9-116">Door een indicator te maken via de [Indicator-API](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="b4df9-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b4df9-117">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="b4df9-117">Before you begin</span></span>

<span data-ttu-id="b4df9-118">Het is belangrijk om de volgende vereisten te begrijpen voordat u indicatoren voor bestanden maakt:</span><span class="sxs-lookup"><span data-stu-id="b4df9-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="b4df9-119">Deze functie is beschikbaar als uw organisatie gebruikmaakt **van Microsoft Defender Antivirus (in** actieve modus) en **cloudbeveiliging is ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="b4df9-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="b4df9-120">Zie Beveiliging in de [cloud beheren voor meer informatie.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="b4df9-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="b4df9-121">De versie van de Antimalware-client moet 4.18.1901.x of hoger zijn.</span><span class="sxs-lookup"><span data-stu-id="b4df9-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="b4df9-122">Zie [Maandelijkse platform- en engineversies](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="b4df9-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="b4df9-123">Ondersteund op apparaten met Windows 10, versie 1703 of hoger, Windows Server 2016 en 2019.</span><span class="sxs-lookup"><span data-stu-id="b4df9-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="b4df9-124">Als u bestanden wilt blokkeren, moet u eerst de functie 'blokkeren of [toestaan'](advanced-features.md) in Instellingen.</span><span class="sxs-lookup"><span data-stu-id="b4df9-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="b4df9-125">Deze functie is ontworpen om te voorkomen dat verdachte malware (of mogelijk schadelijke bestanden) van internet wordt gedownload.</span><span class="sxs-lookup"><span data-stu-id="b4df9-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="b4df9-126">Het ondersteunt momenteel draagbare uitvoerbare (PE)-bestanden, .exe en .dll bestanden.</span><span class="sxs-lookup"><span data-stu-id="b4df9-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="b4df9-127">De dekking wordt in de tijd uitgebreid.</span><span class="sxs-lookup"><span data-stu-id="b4df9-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="b4df9-128">Een indicator voor bestanden maken op de pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="b4df9-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="b4df9-129">Selecteer in het navigatiedeelvenster **Instellingen > Indicatoren.**</span><span class="sxs-lookup"><span data-stu-id="b4df9-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="b4df9-130">Selecteer het **tabblad Bestandshash.**  </span><span class="sxs-lookup"><span data-stu-id="b4df9-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="b4df9-131">Selecteer **Indicator toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="b4df9-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="b4df9-132">Geef de volgende details op:</span><span class="sxs-lookup"><span data-stu-id="b4df9-132">Specify the following details:</span></span>
    - <span data-ttu-id="b4df9-133">Indicator: geef de details van de entiteit op en definieer de afloop van de indicator.</span><span class="sxs-lookup"><span data-stu-id="b4df9-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="b4df9-134">Actie: geef de actie op die moet worden ondernomen en geef een beschrijving op.</span><span class="sxs-lookup"><span data-stu-id="b4df9-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="b4df9-135">Bereik: definieer het bereik van de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="b4df9-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="b4df9-136">Bekijk de details op het tabblad Overzicht en selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="b4df9-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="b4df9-137">Een contextuele indicator maken op de pagina met bestandsgegevens</span><span class="sxs-lookup"><span data-stu-id="b4df9-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="b4df9-138">Een van de opties bij het [uitvoeren van antwoordacties in een bestand](respond-file-alerts.md)is het toevoegen van een indicator voor het   bestand.</span><span class="sxs-lookup"><span data-stu-id="b4df9-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="b4df9-139">Wanneer u een indicatorhash voor een bestand toevoegt, kunt u ervoor kiezen om een waarschuwing te verhogen en het bestand te blokkeren wanneer een apparaat in uw organisatie dit probeert uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="b4df9-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="b4df9-140">Bestanden die automatisch worden geblokkeerd door een indicator, worden niet weergegeven in het actiecentrum van het bestand, maar de waarschuwingen blijven wel zichtbaar in de wachtrij Waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="b4df9-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="b4df9-141">Meestal worden bestandsblokken binnen een paar minuten afgedwongen en verwijderd, maar dit kan meer dan 30 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="b4df9-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> 
>- <span data-ttu-id="b4df9-142">Als er conflicterende bestands-IoC-beleidsregels zijn met hetzelfde afdwingingstype en hetzelfde doel, wordt het beleid van de veiligere hash toegepast.</span><span class="sxs-lookup"><span data-stu-id="b4df9-142">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure hash will be applied.</span></span> <span data-ttu-id="b4df9-143">Een sha-256-bestandshash-IoC-beleid zal een SHA-1-bestandshash-IoC-beleid overnemen, dat een MD5-bestandshash-IoC-beleid overwint als de hashtypen hetzelfde bestand definiëren.</span><span class="sxs-lookup"><span data-stu-id="b4df9-143">An SHA-256 file hash IoC policy will win over an SHA-1 file hash IoC policy, which will win over an MD5 file hash IoC policy if the hash types define the same file.</span></span> <span data-ttu-id="b4df9-144">Dit geldt altijd, ongeacht de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="b4df9-144">This is always true regardless of the device group.</span></span> 
>   <span data-ttu-id="b4df9-145">Als in alle andere gevallen conflicterende bestand-IoC-beleidsregels met hetzelfde afdwingingsdoel worden toegepast op alle apparaten en op de groep van het apparaat, wordt voor een apparaat het beleid in de apparaatgroep gewonnen.</span><span class="sxs-lookup"><span data-stu-id="b4df9-145">In all other cases, if conflicting file IoC policies with the same enforcement target are applied to all devices and to the device’s group, then for a device, the policy in the device group will win.</span></span> 
>   
>- <span data-ttu-id="b4df9-146">Als het groepsbeleid EnableFileHashComputation is uitgeschakeld, wordt de blokkeringsnauwkeurigheid van de bestands-IoC verminderd.</span><span class="sxs-lookup"><span data-stu-id="b4df9-146">If the EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="b4df9-147">Het inschakelen kan `EnableFileHashComputation` echter van invloed zijn op de prestaties van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="b4df9-147">However, enabling `EnableFileHashComputation` may impact device performance.</span></span> <span data-ttu-id="b4df9-148">Het kopiëren van grote bestanden van een netwerk delen naar uw lokale apparaat, met name via een VPN-verbinding, kan bijvoorbeeld van invloed zijn op de prestaties van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="b4df9-148">For example, copying large files from a network share onto your local device, especially over a VPN connection, might have an effect on device performance.</span></span>
>
>   <span data-ttu-id="b4df9-149">Zie [Defender CSP](/windows/client-management/mdm/defender-csp) voor meer informatie over het groepsbeleid enableFileHashComputation</span><span class="sxs-lookup"><span data-stu-id="b4df9-149">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="b4df9-150">Beleidsconflictafhandeling</span><span class="sxs-lookup"><span data-stu-id="b4df9-150">Policy conflict handling</span></span>  

<span data-ttu-id="b4df9-151">Cert- en bestands-IoC-beleidsafhandelingsconflicten volgen de volgende volgorde:</span><span class="sxs-lookup"><span data-stu-id="b4df9-151">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="b4df9-152">Als het bestand niet is toegestaan Windows Defender toepassingsbeheer en AppLocker-modusbeleid/-beleid afdwingen, **blokkeert** u</span><span class="sxs-lookup"><span data-stu-id="b4df9-152">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="b4df9-153">Anders als het bestand is toegestaan door de Microsoft Defender Antivirus uitsluiting, dan **toestaan**</span><span class="sxs-lookup"><span data-stu-id="b4df9-153">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="b4df9-154">Anders als het bestand is geblokkeerd of gewaarschuwd door een blok- of waarschuwingsbestand-IoC, vervolgens **blokkeren/waarschuwen**</span><span class="sxs-lookup"><span data-stu-id="b4df9-154">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="b4df9-155">Anders als het bestand is toegestaan door een IoC-beleid voor bestand toestaan, wordt **het bestand vervolgens toegestaan**</span><span class="sxs-lookup"><span data-stu-id="b4df9-155">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="b4df9-156">Anders als het bestand is geblokkeerd door ASR-regels, CFA, AV, SmartScreen en **vervolgens Blokkeren**</span><span class="sxs-lookup"><span data-stu-id="b4df9-156">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="b4df9-157">Else Allow (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it) Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span><span class="sxs-lookup"><span data-stu-id="b4df9-157">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="b4df9-158">Als er conflicterende bestands-IoC-beleidsregels zijn met hetzelfde afdwingingstype en hetzelfde doel, wordt het beleid van de veiligere hash (wat langer betekent) toegepast.</span><span class="sxs-lookup"><span data-stu-id="b4df9-158">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="b4df9-159">Een sha-256-bestandshash-IoC-beleid zal bijvoorbeeld een IoC-beleid voor MD5-bestandshash winnen als beide hashtypen hetzelfde bestand definiëren.</span><span class="sxs-lookup"><span data-stu-id="b4df9-159">For example, an SHA-256 file hash IoC policy will win over an MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="b4df9-160">De functies voor vulnerability management en blokkering van kwetsbare toepassingen maken gebruik van de bestands-Ioc's voor handhaving en volgen de bovenstaande conflictafhandelingsvolgorde.</span><span class="sxs-lookup"><span data-stu-id="b4df9-160">Threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="b4df9-161">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="b4df9-161">Examples</span></span>

|<span data-ttu-id="b4df9-162">Onderdeel</span><span class="sxs-lookup"><span data-stu-id="b4df9-162">Component</span></span> |<span data-ttu-id="b4df9-163">Component afdwingen</span><span class="sxs-lookup"><span data-stu-id="b4df9-163">Component enforcement</span></span> |<span data-ttu-id="b4df9-164">Actie bestandsindicator</span><span class="sxs-lookup"><span data-stu-id="b4df9-164">File indicator Action</span></span> |<span data-ttu-id="b4df9-165">Resultaat</span><span class="sxs-lookup"><span data-stu-id="b4df9-165">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="b4df9-166">Uitsluiting van het surface reduction-bestandspad voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="b4df9-166">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="b4df9-167">Toestaan</span><span class="sxs-lookup"><span data-stu-id="b4df9-167">Allow</span></span> |<span data-ttu-id="b4df9-168">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="b4df9-168">Block</span></span> |<span data-ttu-id="b4df9-169">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="b4df9-169">Block</span></span>
|<span data-ttu-id="b4df9-170">Surface Reduction-regel voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="b4df9-170">Attack surface reduction rule</span></span> |<span data-ttu-id="b4df9-171">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="b4df9-171">Block</span></span> |<span data-ttu-id="b4df9-172">Toestaan</span><span class="sxs-lookup"><span data-stu-id="b4df9-172">Allow</span></span> |<span data-ttu-id="b4df9-173">Toestaan</span><span class="sxs-lookup"><span data-stu-id="b4df9-173">Allow</span></span>
|<span data-ttu-id="b4df9-174">Windows Defender-toepassingsbeheer</span><span class="sxs-lookup"><span data-stu-id="b4df9-174">Windows Defender Application Control</span></span> |<span data-ttu-id="b4df9-175">Toestaan</span><span class="sxs-lookup"><span data-stu-id="b4df9-175">Allow</span></span> |<span data-ttu-id="b4df9-176">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="b4df9-176">Block</span></span> |<span data-ttu-id="b4df9-177">Toestaan</span><span class="sxs-lookup"><span data-stu-id="b4df9-177">Allow</span></span> |
|<span data-ttu-id="b4df9-178">Windows Defender-toepassingsbeheer</span><span class="sxs-lookup"><span data-stu-id="b4df9-178">Windows Defender Application Control</span></span> |<span data-ttu-id="b4df9-179">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="b4df9-179">Block</span></span> |<span data-ttu-id="b4df9-180">Toestaan</span><span class="sxs-lookup"><span data-stu-id="b4df9-180">Allow</span></span> |<span data-ttu-id="b4df9-181">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="b4df9-181">Block</span></span>
|<span data-ttu-id="b4df9-182">Microsoft Defender Antivirus uitsluiting</span><span class="sxs-lookup"><span data-stu-id="b4df9-182">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="b4df9-183">Toestaan</span><span class="sxs-lookup"><span data-stu-id="b4df9-183">Allow</span></span> |<span data-ttu-id="b4df9-184">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="b4df9-184">Block</span></span> |<span data-ttu-id="b4df9-185">Toestaan</span><span class="sxs-lookup"><span data-stu-id="b4df9-185">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="b4df9-186">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b4df9-186">See also</span></span>

- [<span data-ttu-id="b4df9-187">Indicatoren maken</span><span class="sxs-lookup"><span data-stu-id="b4df9-187">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="b4df9-188">Indicatoren maken voor IP's en URL's/domeinen</span><span class="sxs-lookup"><span data-stu-id="b4df9-188">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="b4df9-189">Indicatoren maken op basis van certificaten</span><span class="sxs-lookup"><span data-stu-id="b4df9-189">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="b4df9-190">Indicatoren beheren</span><span class="sxs-lookup"><span data-stu-id="b4df9-190">Manage indicators</span></span>](indicator-manage.md)
