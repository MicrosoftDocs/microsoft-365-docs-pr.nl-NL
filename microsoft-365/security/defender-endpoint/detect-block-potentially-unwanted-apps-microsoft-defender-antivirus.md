---
title: Mogelijk ongewenste toepassingen blokkeren met Microsoft Defender Antivirus
description: Schakel de antivirusfunctie voor potentieel ongewenste toepassing (PUA) in om ongewenste software, zoals adware, te blokkeren.
keywords: pua, enable, ongewenste software, ongewenste apps, malware, browserwerkbalk, detecteren, blokkeren, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bee92dfa998596578c27bda579a86776bc77c07b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690719"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="89e63-104">Potentieel ongewenste toepassingen detecteren en blokkeren</span><span class="sxs-lookup"><span data-stu-id="89e63-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="89e63-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="89e63-105">**Applies to:**</span></span>

- [<span data-ttu-id="89e63-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="89e63-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="89e63-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="89e63-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> <span data-ttu-id="89e63-108">Potentieel ongewenste toepassingen (PUA) zijn een categorie software waarmee uw computer traag kan worden uitgevoerd, onverwachte advertenties kan weergeven of in het slechtste geval andere software kan installeren die onverwacht of ongewenst kan zijn.</span><span class="sxs-lookup"><span data-stu-id="89e63-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> <span data-ttu-id="89e63-109">Standaard in Windows 10 (versie 2004 en hoger) blokkeert Microsoft Defender Antivirus apps die worden beschouwd als PUA, voor Enterprise-apparaten (E5).</span><span class="sxs-lookup"><span data-stu-id="89e63-109">By default in Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA, for Enterprise (E5) devices.</span></span>

<span data-ttu-id="89e63-110">Potentieel ongewenste toepassingen (PUA) worden niet beschouwd als virussen, malware of andere soorten bedreigingen, maar ze kunnen acties uitvoeren op eindpunten die de prestaties of het gebruik van eindpunten nadelig beïnvloeden.</span><span class="sxs-lookup"><span data-stu-id="89e63-110">Potentially unwanted applications (PUA) are not considered viruses, malware, or other types of threats, but they might perform actions on endpoints which adversely affect endpoint performance or use.</span></span> <span data-ttu-id="89e63-111">_PUA_ kan ook verwijzen naar een toepassing met een slechte reputatie, zoals beoordeeld door Microsoft Defender voor Eindpunt, vanwege bepaalde soorten ongewenst gedrag.</span><span class="sxs-lookup"><span data-stu-id="89e63-111">_PUA_ can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="89e63-112">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="89e63-112">Here are some examples:</span></span>

- <span data-ttu-id="89e63-113">**Reclamesoftware** waarmee advertenties of promoties worden weergegeven, inclusief software waarmee advertenties op webpagina's worden geplaatst.</span><span class="sxs-lookup"><span data-stu-id="89e63-113">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="89e63-114">**Bundeling van software die** biedt voor het installeren van andere software die niet digitaal is ondertekend door dezelfde entiteit.</span><span class="sxs-lookup"><span data-stu-id="89e63-114">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="89e63-115">Ook software die biedt voor het installeren van andere software die in aanmerking komt als PUA.</span><span class="sxs-lookup"><span data-stu-id="89e63-115">Also, software that offers to install other software that qualify as PUA.</span></span>
- <span data-ttu-id="89e63-116">**Software voor ontwijking** die actief probeert detectie door beveiligingsproducten te omzeilen, inclusief software die zich anders gedraagt in aanwezigheid van beveiligingsproducten.</span><span class="sxs-lookup"><span data-stu-id="89e63-116">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="89e63-117">Zie Hoe Microsoft malware en potentieel ongewenste toepassingen identificeert voor meer voorbeelden en een bespreking van de criteria die we gebruiken om toepassingen te labelen voor speciale aandacht van [beveiligingsfuncties.](/windows/security/threat-protection/intelligence/criteria)</span><span class="sxs-lookup"><span data-stu-id="89e63-117">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="89e63-118">Mogelijk ongewenste toepassingen kunnen het risico vergroten dat uw netwerk wordt geïnfecteerd met werkelijke malware, malware-infecties moeilijker te identificeren of IT-bronnen verspillen door ze op te ruimen.</span><span class="sxs-lookup"><span data-stu-id="89e63-118">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="89e63-119">PUA-beveiliging wordt ondersteund in Windows 10, Windows Server 2019 en Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="89e63-119">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="89e63-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="89e63-120">Microsoft Edge</span></span>

<span data-ttu-id="89e63-121">De [nieuwe Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), die op Chromium is gebaseerd, blokkeert mogelijk ongewenste toepassingsdownloads en bijbehorende resource-URL's.</span><span class="sxs-lookup"><span data-stu-id="89e63-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="89e63-122">Deze functie wordt geleverd via [Microsoft Defender SmartScreen.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="89e63-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="89e63-123">PUA-beveiliging inschakelen in microsoft edge op basis van Chromium</span><span class="sxs-lookup"><span data-stu-id="89e63-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="89e63-124">Hoewel mogelijk ongewenste toepassingsbeveiliging in Microsoft Edge (op Chromium gebaseerde versie 80.0.361.50) standaard is uitgeschakeld, kan deze eenvoudig vanuit de browser worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="89e63-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="89e63-125">Selecteer de drie puntjes en kies vervolgens **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="89e63-125">Select the ellipses, and then choose **Settings**.</span></span>
2. <span data-ttu-id="89e63-126">Selecteer **Privacy, zoeken en services.**</span><span class="sxs-lookup"><span data-stu-id="89e63-126">Select **Privacy, search, and services**.</span></span>
3. <span data-ttu-id="89e63-127">Schakel onder **de sectie** Beveiliging mogelijk ongewenste apps **blokkeren in.**</span><span class="sxs-lookup"><span data-stu-id="89e63-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="89e63-128">Als u Microsoft Edge (op Chromium gebaseerd) gebruikt, kunt u de URL-blokkeringsfunctie van PUA-beveiliging veilig verkennen door deze uit te testen op een van onze [Microsoft Defender SmartScreen-demopagina's.](https://demo.smartscreen.msft.net/)</span><span class="sxs-lookup"><span data-stu-id="89e63-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="89e63-129">URL's blokkeren met Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="89e63-129">Blocking URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="89e63-130">In op Chromium gebaseerde Edge met PUA-beveiliging ingeschakeld, beschermt Microsoft Defender SmartScreen u tegen URL's die aan PUA zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="89e63-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="89e63-131">Beveiligingsbeheerders kunnen [configureren hoe](/DeployEdge/configure-microsoft-edge) Microsoft Edge en Microsoft Defender SmartScreen samenwerken om groepen gebruikers te beschermen tegen URL's die aan PUA zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="89e63-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="89e63-132">Er zijn verschillende [groepsbeleidsinstellingen](/DeployEdge/microsoft-edge-policies#smartscreen-settings) expliciet beschikbaar voor Microsoft Defender SmartScreen, waaronder een voor het blokkeren [van PUA.](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)</span><span class="sxs-lookup"><span data-stu-id="89e63-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="89e63-133">Daarnaast kunnen beheerders [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) als geheel configureren met groepsbeleidsinstellingen om Microsoft Defender SmartScreen in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="89e63-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="89e63-134">Hoewel Microsoft Defender voor Eindpunt een eigen blokkeringslijst heeft op basis van een gegevensset die door Microsoft wordt beheerd, kunt u deze lijst aanpassen op basis van uw eigen bedreigingsinformatie.</span><span class="sxs-lookup"><span data-stu-id="89e63-134">Although Microsoft Defender for Endpoint has its own block list based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="89e63-135">Als u [indicatoren maakt en beheert](/microsoft-365/security/defender-endpoint/manage-indicators) in de Microsoft Defender voor Eindpunt-portal, respecteert Microsoft Defender SmartScreen de nieuwe instellingen.</span><span class="sxs-lookup"><span data-stu-id="89e63-135">If you [create and manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus"></a><span data-ttu-id="89e63-136">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="89e63-136">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="89e63-137">De mogelijk ongewenste beveiligingsfunctie voor toepassingen (PUA) in Microsoft Defender Antivirus kan PUA's detecteren en blokkeren op eindpunten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="89e63-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUAs on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="89e63-138">Deze functie is beschikbaar in Windows 10, Windows Server 2019 en Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="89e63-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="89e63-139">Microsoft Defender Antivirus blokkeert gedetecteerde PUA-bestanden en eventuele pogingen om ze te downloaden, te verplaatsen, uit te voeren of te installeren.</span><span class="sxs-lookup"><span data-stu-id="89e63-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="89e63-140">Geblokkeerde PUA-bestanden worden vervolgens verplaatst naar quarantaine.</span><span class="sxs-lookup"><span data-stu-id="89e63-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="89e63-141">Wanneer een PUA-bestand wordt gedetecteerd op een eindpunt, stuurt Microsoft Defender Antivirus een melding naar de gebruiker[(tenzij](configure-notifications-microsoft-defender-antivirus.md)meldingen zijn uitgeschakeld) in dezelfde indeling als andere detecties van bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="89e63-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="89e63-142">De melding wordt vooraf geprefaced met `PUA:` om de inhoud aan te geven.</span><span class="sxs-lookup"><span data-stu-id="89e63-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="89e63-143">De melding wordt weergegeven in de gebruikelijke [quarantainelijst in de Windows Security-app.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="89e63-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="89e63-144">PUA-beveiliging configureren in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="89e63-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="89e63-145">U kunt PUA-beveiliging inschakelen [met Microsoft Intune,](/mem/intune/protect/device-protect) [Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection) [Groepsbeleid](/azure/active-directory-domain-services/manage-group-policy)of via [PowerShell-cmdlets.](/powershell/module/defender/?preserve-view=true&view=win10-ps)</span><span class="sxs-lookup"><span data-stu-id="89e63-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="89e63-146">U kunt ook PUA-beveiliging gebruiken in de auditmodus om potentieel ongewenste toepassingen te detecteren zonder ze te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="89e63-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="89e63-147">De detecties worden vastgelegd in het Windows-gebeurtenislogboek.</span><span class="sxs-lookup"><span data-stu-id="89e63-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="89e63-148">Ga naar de demowebsite van Microsoft Defender voor Eindpunt demo.wd.microsoft.com [om](https://demo.wd.microsoft.com/Page/UrlRep) te bevestigen dat de functie werkt en bekijk deze in actie.</span><span class="sxs-lookup"><span data-stu-id="89e63-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="89e63-149">PUA-beveiliging in de auditmodus is handig als uw bedrijf een interne controle van de softwarebeveiliging voert en u eventuele fout-positieven wilt voorkomen.</span><span class="sxs-lookup"><span data-stu-id="89e63-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

#### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="89e63-150">Intune gebruiken om PUA-beveiliging te configureren</span><span class="sxs-lookup"><span data-stu-id="89e63-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="89e63-151">Zie [Instellingen voor apparaatbeperkingen configureren in Microsoft Intune](/intune/device-restrictions-configure) en Microsoft Defender Antivirus apparaatbeperkingen voor [Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="89e63-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

#### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="89e63-152">Configuration Manager gebruiken om PUA-beveiliging te configureren</span><span class="sxs-lookup"><span data-stu-id="89e63-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="89e63-153">PUA-beveiliging is standaard ingeschakeld in Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="89e63-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="89e63-154">Zie [Antimalware-beleid](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) maken en implementeren: Instellingen voor geplande scans voor meer informatie over het configureren van Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="89e63-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="89e63-155">Voor System Center 2012 Configuration Manager, zie How to Deploy potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager (Systeemcentrum 2012 Configuration Manager) voor Het implementeren van mogelijk ongewenste toepassingsbeveiligingsbeleid [voor endpointbeveiliging in Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)</span><span class="sxs-lookup"><span data-stu-id="89e63-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="89e63-156">PUA-gebeurtenissen die zijn geblokkeerd door Microsoft Defender Antivirus, worden gerapporteerd in de Windows Event Viewer en niet in Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="89e63-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

#### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="89e63-157">Groepsbeleid gebruiken om PUA-beveiliging te configureren</span><span class="sxs-lookup"><span data-stu-id="89e63-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="89e63-158">Beheersjablonen [(.admx) downloaden en installeren voor Windows 10 oktober 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="89e63-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="89e63-159">Open op uw computer voor groepsbeleidsbeheer de [console Groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="89e63-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="89e63-160">Selecteer het groepsbeleidsobject dat u wilt configureren en kies vervolgens **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="89e63-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="89e63-161">Ga in **de Groepsbeleidseditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="89e63-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="89e63-162">Vouw de boom uit **naar Windows Components** Microsoft Defender  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="89e63-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="89e63-163">Dubbelklik op **Detectie configureren voor mogelijk ongewenste toepassingen.**</span><span class="sxs-lookup"><span data-stu-id="89e63-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="89e63-164">Selecteer **Ingeschakeld om** PUA-beveiliging in te stellen.</span><span class="sxs-lookup"><span data-stu-id="89e63-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="89e63-165">Selecteer **in** Opties **Blokkeren om** mogelijk ongewenste toepassingen te blokkeren of selecteer **Auditmodus** om te testen hoe de instelling werkt in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="89e63-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="89e63-166">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="89e63-166">Select **OK**.</span></span>

9. <span data-ttu-id="89e63-167">Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.</span><span class="sxs-lookup"><span data-stu-id="89e63-167">Deploy your Group Policy object as you usually do.</span></span>

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="89e63-168">PowerShell-cmdlets gebruiken om PUA-beveiliging te configureren</span><span class="sxs-lookup"><span data-stu-id="89e63-168">Use PowerShell cmdlets to configure PUA protection</span></span>

##### <a name="to-enable-pua-protection"></a><span data-ttu-id="89e63-169">PUA-beveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="89e63-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="89e63-170">De waarde voor deze cmdlet instellen om de `Enabled` functie in te stellen als deze is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="89e63-170">Setting the value for this cmdlet to `Enabled` turns the feature on if it has been disabled.</span></span>

##### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="89e63-171">Pua-beveiliging instellen op auditmodus</span><span class="sxs-lookup"><span data-stu-id="89e63-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="89e63-172">Met `AuditMode` instelling worden PUA's gedetecteerd zonder ze te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="89e63-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

##### <a name="to-disable-pua-protection"></a><span data-ttu-id="89e63-173">PUA-beveiliging uitschakelen</span><span class="sxs-lookup"><span data-stu-id="89e63-173">To disable PUA protection</span></span>

<span data-ttu-id="89e63-174">We raden u aan om PUA-beveiliging ingeschakeld te houden.</span><span class="sxs-lookup"><span data-stu-id="89e63-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="89e63-175">U kunt deze echter uitschakelen met de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="89e63-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="89e63-176">Als u de waarde voor deze cmdlet wilt instellen, wordt de `Disabled` functie uitgeschakeld als deze is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="89e63-176">Setting the value for this cmdlet to `Disabled` turns the feature off if it has been enabled.</span></span>

<span data-ttu-id="89e63-177">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/index) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="89e63-177">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="view-pua-events"></a><span data-ttu-id="89e63-178">PUA-gebeurtenissen weergeven</span><span class="sxs-lookup"><span data-stu-id="89e63-178">View PUA events</span></span>

<span data-ttu-id="89e63-179">PUA-gebeurtenissen worden gerapporteerd in de Windows Event Viewer, maar niet in Microsoft Endpoint Manager of in Intune.</span><span class="sxs-lookup"><span data-stu-id="89e63-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="89e63-180">U kunt de `Get-MpThreat` cmdlet ook gebruiken om bedreigingen te bekijken die door Microsoft Defender Antivirus zijn afgehandeld.</span><span class="sxs-lookup"><span data-stu-id="89e63-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="89e63-181">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="89e63-181">Here's an example:</span></span>

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

<span data-ttu-id="89e63-182">U kunt e-mailmeldingen in- en uit- of in- of uit- zetten om e-mail over PUA-detecties te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="89e63-182">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="89e63-183">Zie [Problemen met gebeurtenis-ID's oplossen](troubleshoot-microsoft-defender-antivirus.md) voor meer informatie over het bekijken van Microsoft Defender Antivirus-gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="89e63-183">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="89e63-184">PUA-gebeurtenissen worden opgenomen onder **gebeurtenis-id 1160**.</span><span class="sxs-lookup"><span data-stu-id="89e63-184">PUA events are recorded under event ID **1160**.</span></span>

## <a name="excluding-files"></a><span data-ttu-id="89e63-185">Bestanden uitsluiten</span><span class="sxs-lookup"><span data-stu-id="89e63-185">Excluding files</span></span>

<span data-ttu-id="89e63-186">Soms wordt een bestand ten onrechte geblokkeerd door PUA-beveiliging of is een functie van een PUA vereist om een taak te voltooien.</span><span class="sxs-lookup"><span data-stu-id="89e63-186">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="89e63-187">In deze gevallen kan een bestand worden toegevoegd aan een uitsluitingslijst.</span><span class="sxs-lookup"><span data-stu-id="89e63-187">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="89e63-188">Zie Uitsluitingen [configureren en valideren op basis van bestandsextensie en maplocatie voor meer informatie.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="89e63-188">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="89e63-189">Zie ook</span><span class="sxs-lookup"><span data-stu-id="89e63-189">See also</span></span>

- [<span data-ttu-id="89e63-190">Beveiliging van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="89e63-190">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="89e63-191">Gedrags-, heuristische en realtimebeveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="89e63-191">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)