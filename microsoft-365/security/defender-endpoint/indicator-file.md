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
ms.openlocfilehash: 6d92cbacba72210c6accbbb1e5ecf25de660fc3c
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730532"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="11bb5-104">Indicatoren voor bestanden maken</span><span class="sxs-lookup"><span data-stu-id="11bb5-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="11bb5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="11bb5-105">**Applies to:**</span></span>
- [<span data-ttu-id="11bb5-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="11bb5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="11bb5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="11bb5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="11bb5-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="11bb5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="11bb5-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="11bb5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="11bb5-110">Voorkom verdere verspreiding van een aanval in uw organisatie door potentieel schadelijke bestanden of vermoedelijke malware te verbieden.</span><span class="sxs-lookup"><span data-stu-id="11bb5-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="11bb5-111">Als u een potentieel schadelijk bestand voor draagbaar uitvoerbaar (PE) kent, kunt u dit blokkeren.</span><span class="sxs-lookup"><span data-stu-id="11bb5-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="11bb5-112">Deze bewerking voorkomt dat deze wordt gelezen, geschreven of uitgevoerd op apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="11bb5-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="11bb5-113">U kunt op drie manieren indicatoren voor bestanden maken:</span><span class="sxs-lookup"><span data-stu-id="11bb5-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="11bb5-114">Door een indicator te maken via de pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="11bb5-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="11bb5-115">Door een contextuele indicator te maken met behulp van de knop Indicator toevoegen op de pagina met bestandsgegevens</span><span class="sxs-lookup"><span data-stu-id="11bb5-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="11bb5-116">Door een indicator te maken via de [Indicator-API](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="11bb5-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="11bb5-117">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="11bb5-117">Before you begin</span></span>

<span data-ttu-id="11bb5-118">Het is belangrijk om de volgende vereisten te begrijpen voordat u indicatoren voor bestanden maakt:</span><span class="sxs-lookup"><span data-stu-id="11bb5-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="11bb5-119">Deze functie is beschikbaar als uw organisatie gebruikmaakt **van Microsoft Defender Antivirus (in** actieve modus) en **cloudbeveiliging is ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="11bb5-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="11bb5-120">Zie Beveiliging in de [cloud beheren voor meer informatie.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="11bb5-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="11bb5-121">De versie van de Antimalware-client moet 4.18.1901.x of hoger zijn.</span><span class="sxs-lookup"><span data-stu-id="11bb5-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="11bb5-122">Zie [Maandelijkse platform- en engineversies](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="11bb5-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="11bb5-123">Ondersteund op apparaten met Windows 10, versie 1703 of hoger, Windows Server 2016 en 2019.</span><span class="sxs-lookup"><span data-stu-id="11bb5-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="11bb5-124">Als u bestanden wilt blokkeren, moet u eerst de functie 'blokkeren of [toestaan'](advanced-features.md) in Instellingen.</span><span class="sxs-lookup"><span data-stu-id="11bb5-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="11bb5-125">Deze functie is ontworpen om te voorkomen dat verdachte malware (of mogelijk schadelijke bestanden) van internet wordt gedownload.</span><span class="sxs-lookup"><span data-stu-id="11bb5-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="11bb5-126">Het ondersteunt momenteel draagbare uitvoerbare (PE)-bestanden, .exe en .dll bestanden.</span><span class="sxs-lookup"><span data-stu-id="11bb5-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="11bb5-127">De dekking wordt in de tijd uitgebreid.</span><span class="sxs-lookup"><span data-stu-id="11bb5-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="11bb5-128">Een indicator voor bestanden maken op de pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="11bb5-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="11bb5-129">Selecteer in het navigatiedeelvenster **Instellingen > Indicatoren.**</span><span class="sxs-lookup"><span data-stu-id="11bb5-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="11bb5-130">Selecteer het **tabblad Bestandshash.**  </span><span class="sxs-lookup"><span data-stu-id="11bb5-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="11bb5-131">Selecteer **Indicator toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="11bb5-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="11bb5-132">Geef de volgende details op:</span><span class="sxs-lookup"><span data-stu-id="11bb5-132">Specify the following details:</span></span>
    - <span data-ttu-id="11bb5-133">Indicator: geef de details van de entiteit op en definieer de afloop van de indicator.</span><span class="sxs-lookup"><span data-stu-id="11bb5-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="11bb5-134">Actie: geef de actie op die moet worden ondernomen en geef een beschrijving op.</span><span class="sxs-lookup"><span data-stu-id="11bb5-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="11bb5-135">Bereik: definieer het bereik van de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="11bb5-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="11bb5-136">Bekijk de details op het tabblad Overzicht en selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="11bb5-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="11bb5-137">Een contextuele indicator maken op de pagina met bestandsgegevens</span><span class="sxs-lookup"><span data-stu-id="11bb5-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="11bb5-138">Een van de opties bij het [uitvoeren van antwoordacties in een bestand](respond-file-alerts.md)is het toevoegen van een indicator voor het   bestand.</span><span class="sxs-lookup"><span data-stu-id="11bb5-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="11bb5-139">Wanneer u een indicatorhash voor een bestand toevoegt, kunt u ervoor kiezen om een waarschuwing te verhogen en het bestand te blokkeren wanneer een apparaat in uw organisatie dit probeert uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="11bb5-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="11bb5-140">Bestanden die automatisch worden geblokkeerd door een indicator, worden niet weergegeven in het actiecentrum van het bestand, maar de waarschuwingen blijven wel zichtbaar in de wachtrij Waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="11bb5-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="11bb5-141">Meestal worden bestandsblokken binnen een paar minuten afgedwongen en verwijderd, maar dit kan meer dan 30 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="11bb5-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
>- <span data-ttu-id="11bb5-142">Als er conflicterende beleidsregels voor bestandsindicatoren zijn, wordt het handhavingsbeleid van het veiligere beleid toegepast.</span><span class="sxs-lookup"><span data-stu-id="11bb5-142">If there are conflicting file indicator policies, the enforcement policy of the more secure policy is applied.</span></span> <span data-ttu-id="11bb5-143">Een sha-256-indicatorbeleid voor bestandshash heeft bijvoorbeeld voorrang op een MD5-indicatorbeleid voor bestandshash als beide hashtypen hetzelfde bestand definiëren.</span><span class="sxs-lookup"><span data-stu-id="11bb5-143">For example, a SHA-256 file hash indicator policy takes precedence over an MD5 file hash indicator policy if both hash types define the same file.</span></span>
>- <span data-ttu-id="11bb5-144">Als het groepsbeleid EnableFileHashComputation is uitgeschakeld, wordt de blokkeringsnauwkeurigheid van de bestands-IoC verminderd.</span><span class="sxs-lookup"><span data-stu-id="11bb5-144">If EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="11bb5-145">Het inschakelen van EnableFileHashComputation kan echter van invloed zijn op de prestaties van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="11bb5-145">However, enabling EnableFileHashComputation may impact device performance.</span></span>
>    - <span data-ttu-id="11bb5-146">Het kopiëren van grote bestanden van een netwerk delen naar uw lokale apparaat, met name via een VPN-verbinding, kan bijvoorbeeld van invloed zijn op de prestaties van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="11bb5-146">For example, copying large files from a network share onto your local device, especially over a VPN connection, may have an effect on device performance.</span></span>
>    - <span data-ttu-id="11bb5-147">Zie [Defender CSP](/windows/client-management/mdm/defender-csp) voor meer informatie over het groepsbeleid enableFileHashComputation</span><span class="sxs-lookup"><span data-stu-id="11bb5-147">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="11bb5-148">Beleidsconflictafhandeling</span><span class="sxs-lookup"><span data-stu-id="11bb5-148">Policy conflict handling</span></span>  

<span data-ttu-id="11bb5-149">Cert- en bestands-IoC-beleidsafhandelingsconflicten volgen de volgende volgorde:</span><span class="sxs-lookup"><span data-stu-id="11bb5-149">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="11bb5-150">Als het bestand niet is toegestaan Windows Defender toepassingsbeheer en AppLocker-modusbeleid/-beleid afdwingen, **blokkeert** u</span><span class="sxs-lookup"><span data-stu-id="11bb5-150">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="11bb5-151">Anders als het bestand is toegestaan door de Microsoft Defender Antivirus uitsluiting, dan **toestaan**</span><span class="sxs-lookup"><span data-stu-id="11bb5-151">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="11bb5-152">Anders als het bestand is geblokkeerd of gewaarschuwd door een blok- of waarschuwingsbestand-IoC, vervolgens **blokkeren/waarschuwen**</span><span class="sxs-lookup"><span data-stu-id="11bb5-152">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="11bb5-153">Anders als het bestand is toegestaan door een IoC-beleid voor bestand toestaan, wordt **het bestand vervolgens toegestaan**</span><span class="sxs-lookup"><span data-stu-id="11bb5-153">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="11bb5-154">Anders als het bestand is geblokkeerd door ASR-regels, CFA, AV, SmartScreen en **vervolgens Blokkeren**</span><span class="sxs-lookup"><span data-stu-id="11bb5-154">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="11bb5-155">Else Allow (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it) Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span><span class="sxs-lookup"><span data-stu-id="11bb5-155">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="11bb5-156">Als er conflicterende bestands-IoC-beleidsregels zijn met hetzelfde afdwingingstype en hetzelfde doel, wordt het beleid van de veiligere hash (wat langer betekent) toegepast.</span><span class="sxs-lookup"><span data-stu-id="11bb5-156">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="11bb5-157">Een sha-256-bestandshash-IoC-beleid zal bijvoorbeeld een IoC-beleid voor MD5-bestandshash winnen als beide hashtypen hetzelfde bestand definiëren.</span><span class="sxs-lookup"><span data-stu-id="11bb5-157">For example, a SHA-256 file hash IoC policy will win over a MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="11bb5-158">Houd er rekening Threat and Vulnerability Management de functies van de blokkering van kwetsbare toepassingen de bestands-Ioc's gebruiken voor handhaving en volgen de bovenstaande conflictafhandelingsvolgorde.</span><span class="sxs-lookup"><span data-stu-id="11bb5-158">Note that threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="11bb5-159">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="11bb5-159">Examples</span></span>

|<span data-ttu-id="11bb5-160">Onderdeel</span><span class="sxs-lookup"><span data-stu-id="11bb5-160">Component</span></span> |<span data-ttu-id="11bb5-161">Component afdwingen</span><span class="sxs-lookup"><span data-stu-id="11bb5-161">Component enforcement</span></span> |<span data-ttu-id="11bb5-162">Actie bestandsindicator</span><span class="sxs-lookup"><span data-stu-id="11bb5-162">File indicator Action</span></span> |<span data-ttu-id="11bb5-163">Resultaat</span><span class="sxs-lookup"><span data-stu-id="11bb5-163">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="11bb5-164">Uitsluiting van het surface reduction-bestandspad voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="11bb5-164">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="11bb5-165">Toestaan</span><span class="sxs-lookup"><span data-stu-id="11bb5-165">Allow</span></span> |<span data-ttu-id="11bb5-166">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="11bb5-166">Block</span></span> |<span data-ttu-id="11bb5-167">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="11bb5-167">Block</span></span>
|<span data-ttu-id="11bb5-168">Surface Reduction-regel voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="11bb5-168">Attack surface reduction rule</span></span> |<span data-ttu-id="11bb5-169">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="11bb5-169">Block</span></span> |<span data-ttu-id="11bb5-170">Toestaan</span><span class="sxs-lookup"><span data-stu-id="11bb5-170">Allow</span></span> |<span data-ttu-id="11bb5-171">Toestaan</span><span class="sxs-lookup"><span data-stu-id="11bb5-171">Allow</span></span>
|<span data-ttu-id="11bb5-172">Windows Defender-toepassingsbeheer</span><span class="sxs-lookup"><span data-stu-id="11bb5-172">Windows Defender Application Control</span></span> |<span data-ttu-id="11bb5-173">Toestaan</span><span class="sxs-lookup"><span data-stu-id="11bb5-173">Allow</span></span> |<span data-ttu-id="11bb5-174">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="11bb5-174">Block</span></span> |<span data-ttu-id="11bb5-175">Toestaan</span><span class="sxs-lookup"><span data-stu-id="11bb5-175">Allow</span></span> |
|<span data-ttu-id="11bb5-176">Windows Defender-toepassingsbeheer</span><span class="sxs-lookup"><span data-stu-id="11bb5-176">Windows Defender Application Control</span></span> |<span data-ttu-id="11bb5-177">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="11bb5-177">Block</span></span> |<span data-ttu-id="11bb5-178">Toestaan</span><span class="sxs-lookup"><span data-stu-id="11bb5-178">Allow</span></span> |<span data-ttu-id="11bb5-179">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="11bb5-179">Block</span></span>
|<span data-ttu-id="11bb5-180">Microsoft Defender Antivirus uitsluiting</span><span class="sxs-lookup"><span data-stu-id="11bb5-180">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="11bb5-181">Toestaan</span><span class="sxs-lookup"><span data-stu-id="11bb5-181">Allow</span></span> |<span data-ttu-id="11bb5-182">Blokkeren</span><span class="sxs-lookup"><span data-stu-id="11bb5-182">Block</span></span> |<span data-ttu-id="11bb5-183">Toestaan</span><span class="sxs-lookup"><span data-stu-id="11bb5-183">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="11bb5-184">Zie ook</span><span class="sxs-lookup"><span data-stu-id="11bb5-184">See also</span></span>

- [<span data-ttu-id="11bb5-185">Indicatoren maken</span><span class="sxs-lookup"><span data-stu-id="11bb5-185">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="11bb5-186">Indicatoren maken voor IP's en URL's/domeinen</span><span class="sxs-lookup"><span data-stu-id="11bb5-186">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="11bb5-187">Indicatoren maken op basis van certificaten</span><span class="sxs-lookup"><span data-stu-id="11bb5-187">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="11bb5-188">Indicatoren beheren</span><span class="sxs-lookup"><span data-stu-id="11bb5-188">Manage indicators</span></span>](indicator-manage.md)
