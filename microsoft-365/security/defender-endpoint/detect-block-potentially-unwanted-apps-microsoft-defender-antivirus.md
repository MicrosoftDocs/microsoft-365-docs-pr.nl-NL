---
title: Mogelijk ongewenste toepassingen blokkeren met Microsoft Defender Antivirus
description: Schakel de antivirusfunctie voor potentieel ongewenste toepassing (PUA) in om ongewenste software, zoals adware, te blokkeren.
keywords: pua, enable, ongewenste software, ongewenste apps, malware, browserwerkbalk, detecteren, blokkeren, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 808eff2074dfe1573708264590b401f3d38db982
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904008"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="f3da0-104">Potentieel ongewenste toepassingen detecteren en blokkeren</span><span class="sxs-lookup"><span data-stu-id="f3da0-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f3da0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f3da0-105">**Applies to:**</span></span>

- [<span data-ttu-id="f3da0-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f3da0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="f3da0-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f3da0-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="f3da0-108">Potentieel ongewenste toepassingen (PUA) zijn een categorie software waarmee uw computer traag kan worden uitgevoerd, onverwachte advertenties kan weergeven of in het slechtste geval andere software kan installeren die onverwacht of ongewenst kan zijn.</span><span class="sxs-lookup"><span data-stu-id="f3da0-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="f3da0-109">PUA wordt niet beschouwd als een virus, malware of ander type bedreiging, maar het kan acties uitvoeren op eindpunten die de prestaties of het gebruik van eindpunten nadelig beïnvloeden.</span><span class="sxs-lookup"><span data-stu-id="f3da0-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="f3da0-110">De term *PUA kan* ook verwijzen naar een toepassing met een slechte reputatie, zoals beoordeeld door Microsoft Defender voor Eindpunt, vanwege bepaalde soorten ongewenst gedrag.</span><span class="sxs-lookup"><span data-stu-id="f3da0-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="f3da0-111">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="f3da0-111">Here are some examples:</span></span>

- <span data-ttu-id="f3da0-112">**Reclamesoftware** waarmee advertenties of promoties worden weergegeven, inclusief software waarmee advertenties op webpagina's worden geplaatst.</span><span class="sxs-lookup"><span data-stu-id="f3da0-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="f3da0-113">**Bundeling van software die** biedt voor het installeren van andere software die niet digitaal is ondertekend door dezelfde entiteit.</span><span class="sxs-lookup"><span data-stu-id="f3da0-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="f3da0-114">Ook software die biedt voor het installeren van andere software die in aanmerking komt als PUA.</span><span class="sxs-lookup"><span data-stu-id="f3da0-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="f3da0-115">**Software voor ontwijking** die actief probeert detectie door beveiligingsproducten te omzeilen, inclusief software die zich anders gedraagt in aanwezigheid van beveiligingsproducten.</span><span class="sxs-lookup"><span data-stu-id="f3da0-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="f3da0-116">Zie Hoe Microsoft malware en potentieel ongewenste toepassingen identificeert voor meer voorbeelden en een bespreking van de criteria die we gebruiken om toepassingen te labelen voor speciale aandacht van [beveiligingsfuncties.](/windows/security/threat-protection/intelligence/criteria)</span><span class="sxs-lookup"><span data-stu-id="f3da0-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="f3da0-117">Mogelijk ongewenste toepassingen kunnen het risico vergroten dat uw netwerk wordt geïnfecteerd met werkelijke malware, malware-infecties moeilijker te identificeren of IT-bronnen verspillen door ze op te ruimen.</span><span class="sxs-lookup"><span data-stu-id="f3da0-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="f3da0-118">PUA-beveiliging wordt ondersteund in Windows 10, Windows Server 2019 en Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="f3da0-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="f3da0-119">In Windows 10 (versie 2004 en hoger) blokkeert Microsoft Defender Antivirus apps die standaard worden beschouwd als PUA voor Enterprise-apparaten (E5).</span><span class="sxs-lookup"><span data-stu-id="f3da0-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="f3da0-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f3da0-120">Microsoft Edge</span></span>

<span data-ttu-id="f3da0-121">De [nieuwe Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), die op Chromium is gebaseerd, blokkeert mogelijk ongewenste toepassingsdownloads en bijbehorende resource-URL's.</span><span class="sxs-lookup"><span data-stu-id="f3da0-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="f3da0-122">Deze functie wordt geleverd via [Microsoft Defender SmartScreen.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="f3da0-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="f3da0-123">PUA-beveiliging inschakelen in microsoft edge op basis van Chromium</span><span class="sxs-lookup"><span data-stu-id="f3da0-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="f3da0-124">Hoewel mogelijk ongewenste toepassingsbeveiliging in Microsoft Edge (op Chromium gebaseerde versie 80.0.361.50) standaard is uitgeschakeld, kan deze eenvoudig vanuit de browser worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f3da0-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="f3da0-125">Selecteer in de Edge-browser de drie puntjes en kies vervolgens **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="f3da0-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="f3da0-126">Selecteer **Privacy, zoeken en services.**</span><span class="sxs-lookup"><span data-stu-id="f3da0-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="f3da0-127">Schakel onder **de sectie** Beveiliging mogelijk ongewenste apps **blokkeren in.**</span><span class="sxs-lookup"><span data-stu-id="f3da0-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="f3da0-128">Als u Microsoft Edge (op Chromium gebaseerd) gebruikt, kunt u de URL-blokkeringsfunctie van PUA-beveiliging veilig verkennen door deze uit te testen op een van onze [Microsoft Defender SmartScreen-demopagina's.](https://demo.smartscreen.msft.net/)</span><span class="sxs-lookup"><span data-stu-id="f3da0-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="block-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="f3da0-129">URL's blokkeren met Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="f3da0-129">Block URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="f3da0-130">In op Chromium gebaseerde Edge met PUA-beveiliging ingeschakeld, beschermt Microsoft Defender SmartScreen u tegen URL's die aan PUA zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="f3da0-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="f3da0-131">Beveiligingsbeheerders kunnen [configureren hoe](/DeployEdge/configure-microsoft-edge) Microsoft Edge en Microsoft Defender SmartScreen samenwerken om groepen gebruikers te beschermen tegen URL's die aan PUA zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="f3da0-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="f3da0-132">Er zijn verschillende [groepsbeleidsinstellingen](/DeployEdge/microsoft-edge-policies#smartscreen-settings) expliciet beschikbaar voor Microsoft Defender SmartScreen, waaronder een voor het blokkeren [van PUA.](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)</span><span class="sxs-lookup"><span data-stu-id="f3da0-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="f3da0-133">Daarnaast kunnen beheerders [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) als geheel configureren met groepsbeleidsinstellingen om Microsoft Defender SmartScreen in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="f3da0-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="f3da0-134">Hoewel Microsoft Defender voor Eindpunt een eigen blokkering heeft op basis van een gegevensset die door Microsoft wordt beheerd, kunt u deze lijst aanpassen op basis van uw eigen bedreigingsinformatie.</span><span class="sxs-lookup"><span data-stu-id="f3da0-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="f3da0-135">Als u [indicatoren maakt en beheert](manage-indicators.md) in de Microsoft Defender voor Eindpunt-portal, respecteert Microsoft Defender SmartScreen de nieuwe instellingen.</span><span class="sxs-lookup"><span data-stu-id="f3da0-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus-and-pua-protection"></a><span data-ttu-id="f3da0-136">Microsoft Defender Antivirus- en PUA-beveiliging</span><span class="sxs-lookup"><span data-stu-id="f3da0-136">Microsoft Defender Antivirus and PUA protection</span></span>

<span data-ttu-id="f3da0-137">De potentieel ongewenste beveiligingsfunctie voor toepassingen (PUA) in Microsoft Defender Antivirus kan PUA detecteren en blokkeren op eindpunten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="f3da0-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUA on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="f3da0-138">Deze functie is beschikbaar in Windows 10, Windows Server 2019 en Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="f3da0-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="f3da0-139">Microsoft Defender Antivirus blokkeert gedetecteerde PUA-bestanden en eventuele pogingen om ze te downloaden, te verplaatsen, uit te voeren of te installeren.</span><span class="sxs-lookup"><span data-stu-id="f3da0-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="f3da0-140">Geblokkeerde PUA-bestanden worden vervolgens verplaatst naar quarantaine.</span><span class="sxs-lookup"><span data-stu-id="f3da0-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="f3da0-141">Wanneer een PUA-bestand wordt gedetecteerd op een eindpunt, stuurt Microsoft Defender Antivirus een melding naar de gebruiker[(tenzij](configure-notifications-microsoft-defender-antivirus.md)meldingen zijn uitgeschakeld) in dezelfde indeling als andere detecties van bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="f3da0-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="f3da0-142">De melding wordt vooraf geprefaced met `PUA:` om de inhoud aan te geven.</span><span class="sxs-lookup"><span data-stu-id="f3da0-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="f3da0-143">De melding wordt weergegeven in de gebruikelijke [quarantainelijst in de Windows Security-app.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f3da0-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="f3da0-144">PUA-beveiliging configureren in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="f3da0-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="f3da0-145">U kunt PUA-beveiliging inschakelen [met Microsoft Intune,](/mem/intune/protect/device-protect) [Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection) [Groepsbeleid](/azure/active-directory-domain-services/manage-group-policy)of via [PowerShell-cmdlets.](/powershell/module/defender/?preserve-view=true&view=win10-ps)</span><span class="sxs-lookup"><span data-stu-id="f3da0-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="f3da0-146">U kunt ook PUA-beveiliging gebruiken in de auditmodus om potentieel ongewenste toepassingen te detecteren zonder ze te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="f3da0-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="f3da0-147">De detecties worden vastgelegd in het Windows-gebeurtenislogboek.</span><span class="sxs-lookup"><span data-stu-id="f3da0-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="f3da0-148">Ga naar de demowebsite van Microsoft Defender voor Eindpunt demo.wd.microsoft.com [om](https://demo.wd.microsoft.com/Page/UrlRep) te bevestigen dat de functie werkt en bekijk deze in actie.</span><span class="sxs-lookup"><span data-stu-id="f3da0-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="f3da0-149">PUA-beveiliging in de auditmodus is handig als uw bedrijf een interne controle van de softwarebeveiliging voert en u eventuele fout-positieven wilt voorkomen.</span><span class="sxs-lookup"><span data-stu-id="f3da0-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="f3da0-150">Intune gebruiken om PUA-beveiliging te configureren</span><span class="sxs-lookup"><span data-stu-id="f3da0-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="f3da0-151">Zie [Instellingen voor apparaatbeperkingen configureren in Microsoft Intune](/intune/device-restrictions-configure) en Microsoft Defender Antivirus apparaatbeperkingen voor [Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f3da0-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="f3da0-152">Configuration Manager gebruiken om PUA-beveiliging te configureren</span><span class="sxs-lookup"><span data-stu-id="f3da0-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="f3da0-153">PUA-beveiliging is standaard ingeschakeld in Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="f3da0-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="f3da0-154">Zie [Antimalware-beleid](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) maken en implementeren: Instellingen voor geplande scans voor meer informatie over het configureren van Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="f3da0-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="f3da0-155">Voor System Center 2012 Configuration Manager, zie How to Deploy potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager (Systeemcentrum 2012 Configuration Manager) voor Het implementeren van mogelijk ongewenste toepassingsbeveiligingsbeleid [voor endpointbeveiliging in Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)</span><span class="sxs-lookup"><span data-stu-id="f3da0-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="f3da0-156">PUA-gebeurtenissen die zijn geblokkeerd door Microsoft Defender Antivirus, worden gerapporteerd in de Windows Event Viewer en niet in Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f3da0-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="f3da0-157">Groepsbeleid gebruiken om PUA-beveiliging te configureren</span><span class="sxs-lookup"><span data-stu-id="f3da0-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="f3da0-158">Beheersjablonen [(.admx) downloaden en installeren voor Windows 10 oktober 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="f3da0-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="f3da0-159">Open op uw computer voor groepsbeleidsbeheer de [console Groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="f3da0-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="f3da0-160">Selecteer het groepsbeleidsobject dat u wilt configureren en kies vervolgens **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="f3da0-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="f3da0-161">Ga in **de Groepsbeleidseditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="f3da0-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="f3da0-162">Vouw de boom uit **naar Windows Components** Microsoft Defender  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="f3da0-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="f3da0-163">Dubbelklik op **Detectie configureren voor mogelijk ongewenste toepassingen.**</span><span class="sxs-lookup"><span data-stu-id="f3da0-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="f3da0-164">Selecteer **Ingeschakeld om** PUA-beveiliging in te stellen.</span><span class="sxs-lookup"><span data-stu-id="f3da0-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="f3da0-165">Selecteer **in** Opties **Blokkeren om** mogelijk ongewenste toepassingen te blokkeren of selecteer **Auditmodus** om te testen hoe de instelling werkt in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="f3da0-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="f3da0-166">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3da0-166">Select **OK**.</span></span>

9. <span data-ttu-id="f3da0-167">Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.</span><span class="sxs-lookup"><span data-stu-id="f3da0-167">Deploy your Group Policy object as you usually do.</span></span>

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="f3da0-168">PowerShell-cmdlets gebruiken om PUA-beveiliging te configureren</span><span class="sxs-lookup"><span data-stu-id="f3da0-168">Use PowerShell cmdlets to configure PUA protection</span></span>

#### <a name="to-enable-pua-protection"></a><span data-ttu-id="f3da0-169">PUA-beveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="f3da0-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="f3da0-170">Als u de waarde voor deze cmdlet in wilt stellen, schakelt u de `Enabled` functie in als deze is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f3da0-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

#### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="f3da0-171">Pua-beveiliging instellen op auditmodus</span><span class="sxs-lookup"><span data-stu-id="f3da0-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="f3da0-172">Met `AuditMode` instelling worden PUA's gedetecteerd zonder ze te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="f3da0-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

#### <a name="to-disable-pua-protection"></a><span data-ttu-id="f3da0-173">PUA-beveiliging uitschakelen</span><span class="sxs-lookup"><span data-stu-id="f3da0-173">To disable PUA protection</span></span>

<span data-ttu-id="f3da0-174">We raden u aan om PUA-beveiliging ingeschakeld te houden.</span><span class="sxs-lookup"><span data-stu-id="f3da0-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="f3da0-175">U kunt deze echter uitschakelen met de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f3da0-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="f3da0-176">Als u de waarde voor deze cmdlet instelt, wordt de functie uitgeschakeld `Disabled` als deze is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f3da0-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="f3da0-177">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/index)te configureren en uit te voeren voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f3da0-177">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

## <a name="view-pua-events-using-powershell"></a><span data-ttu-id="f3da0-178">PUA-gebeurtenissen weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3da0-178">View PUA events using PowerShell</span></span>

<span data-ttu-id="f3da0-179">PUA-gebeurtenissen worden gerapporteerd in de Windows Event Viewer, maar niet in Microsoft Endpoint Manager of in Intune.</span><span class="sxs-lookup"><span data-stu-id="f3da0-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="f3da0-180">U kunt de `Get-MpThreat` cmdlet ook gebruiken om bedreigingen te bekijken die door Microsoft Defender Antivirus zijn afgehandeld.</span><span class="sxs-lookup"><span data-stu-id="f3da0-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="f3da0-181">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="f3da0-181">Here's an example:</span></span>

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

## <a name="get-email-notifications-about-pua-detections"></a><span data-ttu-id="f3da0-182">E-mailmeldingen over PUA-detecties ontvangen</span><span class="sxs-lookup"><span data-stu-id="f3da0-182">Get email notifications about PUA detections</span></span>

<span data-ttu-id="f3da0-183">U kunt e-mailmeldingen in- en uit- of in- of uit- zetten om e-mail over PUA-detecties te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="f3da0-183">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="f3da0-184">Zie [Problemen met gebeurtenis-ID's oplossen](troubleshoot-microsoft-defender-antivirus.md) voor meer informatie over het bekijken van Microsoft Defender Antivirus-gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="f3da0-184">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="f3da0-185">PUA-gebeurtenissen worden opgenomen onder **gebeurtenis-id 1160**.</span><span class="sxs-lookup"><span data-stu-id="f3da0-185">PUA events are recorded under event ID **1160**.</span></span>

## <a name="view-pua-events-using-advanced-hunting"></a><span data-ttu-id="f3da0-186">PUA-gebeurtenissen bekijken met behulp van geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="f3da0-186">View PUA events using advanced hunting</span></span>

<span data-ttu-id="f3da0-187">Als u Microsoft Defender voor [eindpunt](microsoft-defender-endpoint.md)gebruikt, kunt u een geavanceerde query gebruiken om PUA-gebeurtenissen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="f3da0-187">If you're using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="f3da0-188">Hier is een voorbeeldquery:</span><span class="sxs-lookup"><span data-stu-id="f3da0-188">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

<span data-ttu-id="f3da0-189">Zie Proactief op bedreigingen zoeken met geavanceerde jacht voor meer informatie over geavanceerde [jacht.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f3da0-189">To learn more about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="exclude-files-from-pua-protection"></a><span data-ttu-id="f3da0-190">Bestanden uitsluiten van PUA-beveiliging</span><span class="sxs-lookup"><span data-stu-id="f3da0-190">Exclude files from PUA protection</span></span>

<span data-ttu-id="f3da0-191">Soms wordt een bestand ten onrechte geblokkeerd door PUA-beveiliging of is een functie van een PUA vereist om een taak te voltooien.</span><span class="sxs-lookup"><span data-stu-id="f3da0-191">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="f3da0-192">In deze gevallen kan een bestand worden toegevoegd aan een uitsluitingslijst.</span><span class="sxs-lookup"><span data-stu-id="f3da0-192">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="f3da0-193">Zie Uitsluitingen [configureren en valideren op basis van bestandsextensie en maplocatie voor meer informatie.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f3da0-193">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f3da0-194">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f3da0-194">See also</span></span>

- [<span data-ttu-id="f3da0-195">Beveiliging van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="f3da0-195">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="f3da0-196">Gedrag, heuristiek en realtime bescherming configureren</span><span class="sxs-lookup"><span data-stu-id="f3da0-196">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)