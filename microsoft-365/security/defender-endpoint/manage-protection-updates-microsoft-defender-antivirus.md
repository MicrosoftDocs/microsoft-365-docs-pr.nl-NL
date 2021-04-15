---
title: Beheren hoe en waar Microsoft Defender Antivirus updates ontvangt
description: Beheer de terugvalorder voor de manier waarop Microsoft Defender Antivirus beveiligingsupdates ontvangt.
keywords: updates, beveiligingslijnlijnen, beveiliging, fallback order, ADL, MMPC, UNC, bestandspad, delen, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 9b1c9bc8c86c5b348e3c4d2a51e0bfafaf3e7174
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765465"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a><span data-ttu-id="713a4-104">De bronnen beheren voor updates voor de Microsoft Defender Antivirus-beveiliging</span><span class="sxs-lookup"><span data-stu-id="713a4-104">Manage the sources for Microsoft Defender Antivirus protection updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="713a4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="713a4-105">**Applies to:**</span></span>

- [<span data-ttu-id="713a4-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="713a4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

<span data-ttu-id="713a4-107">Het up-to-date houden van uw antivirusbeveiliging is essentieel.</span><span class="sxs-lookup"><span data-stu-id="713a4-107">Keeping your antivirus protection up to date is critical.</span></span> <span data-ttu-id="713a4-108">Er zijn twee onderdelen voor het beheren van beveiligingsupdates voor Microsoft Defender Antivirus:</span><span class="sxs-lookup"><span data-stu-id="713a4-108">There are two components to managing protection updates for Microsoft Defender Antivirus:</span></span> 
- <span data-ttu-id="713a4-109">*Waar* de updates van worden gedownload; en</span><span class="sxs-lookup"><span data-stu-id="713a4-109">*Where* the updates are downloaded from; and</span></span> 
- <span data-ttu-id="713a4-110">*Wanneer* updates worden gedownload en toegepast.</span><span class="sxs-lookup"><span data-stu-id="713a4-110">*When* updates are downloaded and applied.</span></span> 

<span data-ttu-id="713a4-111">In dit artikel wordt beschreven hoe u kunt opgeven waar updates moeten worden gedownload (dit wordt ook wel de terugvalorder genoemd).</span><span class="sxs-lookup"><span data-stu-id="713a4-111">This article describes how to specify from where updates should be downloaded (this is also known as the fallback order).</span></span> <span data-ttu-id="713a4-112">Zie [Microsoft Defender Antivirus-updates beheren](manage-updates-baselines-microsoft-defender-antivirus.md) en basislijnen toepassen voor een overzicht van hoe updates werken en hoe u andere aspecten van updates configureert (zoals het plannen van updates).</span><span class="sxs-lookup"><span data-stu-id="713a4-112">See [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md) topic for an overview on how updates work, and how to configure other aspects of updates (such as scheduling updates).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="713a4-113">Microsoft Defender Antivirus Security Intelligence-updates worden geleverd via Windows Update en vanaf maandag 21 oktober 2019 zijn alle beveiligingsinformatie-updates sha-2 exclusief ondertekend.</span><span class="sxs-lookup"><span data-stu-id="713a4-113">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update and starting Monday, October 21, 2019, all security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="713a4-114">Uw apparaten moeten worden bijgewerkt ter ondersteuning van SHA-2 om uw beveiligingsinformatie bij te werken.</span><span class="sxs-lookup"><span data-stu-id="713a4-114">Your devices must be updated to support SHA-2 in order to update your security intelligence.</span></span> <span data-ttu-id="713a4-115">Zie [SHA-2 Code Signing Support requirement 2019 voor Windows en WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="713a4-115">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>  


<a id="fallback-order"></a>

## <a name="fallback-order"></a><span data-ttu-id="713a4-116">Terugvalorder</span><span class="sxs-lookup"><span data-stu-id="713a4-116">Fallback order</span></span>

<span data-ttu-id="713a4-117">Meestal configureert u eindpunten om updates afzonderlijk te downloaden van een primaire bron, gevolgd door andere bronnen in volgorde van prioriteit, op basis van uw netwerkconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="713a4-117">Typically, you configure endpoints to individually download updates from a primary source followed by other sources in order of priority, based on your network configuration.</span></span> <span data-ttu-id="713a4-118">Updates worden verkregen uit bronnen in de volgorde die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="713a4-118">Updates are obtained from sources in the order you specify.</span></span> <span data-ttu-id="713a4-119">Als een bron niet beschikbaar is, wordt de volgende bron in de lijst onmiddellijk gebruikt.</span><span class="sxs-lookup"><span data-stu-id="713a4-119">If a source is not available, the next source in the list is used immediately.</span></span>

<span data-ttu-id="713a4-120">Wanneer updates worden gepubliceerd, wordt enige logica toegepast om de grootte van de update te minimaliseren.</span><span class="sxs-lookup"><span data-stu-id="713a4-120">When updates are published, some logic is applied to minimize the size of the update.</span></span> <span data-ttu-id="713a4-121">In de meeste gevallen worden alleen de verschillen tussen de meest recente update en de update die momenteel is geïnstalleerd (dit wordt de delta genoemd) op het apparaat gedownload en toegepast.</span><span class="sxs-lookup"><span data-stu-id="713a4-121">In most cases, only the differences between the latest update and the update that is currently installed (this is referred to as the delta) on the device is downloaded and applied.</span></span> <span data-ttu-id="713a4-122">De grootte van de delta is echter afhankelijk van twee belangrijke factoren:</span><span class="sxs-lookup"><span data-stu-id="713a4-122">However, the size of the delta depends on two main factors:</span></span>
- <span data-ttu-id="713a4-123">De leeftijd van de laatste update op het apparaat; en</span><span class="sxs-lookup"><span data-stu-id="713a4-123">The age of the last update on the device; and</span></span> 
- <span data-ttu-id="713a4-124">De bron die wordt gebruikt om updates te downloaden en toe te passen.</span><span class="sxs-lookup"><span data-stu-id="713a4-124">The source used to download and apply updates.</span></span> 

<span data-ttu-id="713a4-125">Hoe ouder de updates op een eindpunt, hoe groter de download.</span><span class="sxs-lookup"><span data-stu-id="713a4-125">The older the updates on an endpoint, the larger the download will be.</span></span> <span data-ttu-id="713a4-126">U moet echter ook rekening houden met de downloadfrequentie.</span><span class="sxs-lookup"><span data-stu-id="713a4-126">However, you must also consider download frequency as well.</span></span> <span data-ttu-id="713a4-127">Een vaker bijgewerkte planning kan leiden tot meer netwerkgebruik, terwijl een minder frequent schema kan leiden tot grotere bestandsgrootten per download.</span><span class="sxs-lookup"><span data-stu-id="713a4-127">A more frequent update schedule can result in more network usage, whereas a less-frequent schedule can result in larger file sizes per download.</span></span> 

<span data-ttu-id="713a4-128">Er zijn vijf locaties waar u kunt opgeven waar een eindpunt updates moet krijgen:</span><span class="sxs-lookup"><span data-stu-id="713a4-128">There are five locations where you can specify where an endpoint should obtain updates:</span></span> 

- [<span data-ttu-id="713a4-129">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="713a4-129">Microsoft Update</span></span>](https://support.microsoft.com/help/12373/windows-update-faq)
- [<span data-ttu-id="713a4-130">Windows Server Update Service</span><span class="sxs-lookup"><span data-stu-id="713a4-130">Windows Server Update Service</span></span>](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [<span data-ttu-id="713a4-131">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="713a4-131">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/core/servers/manage/updates)
- [<span data-ttu-id="713a4-132">Netwerkbestands delen</span><span class="sxs-lookup"><span data-stu-id="713a4-132">Network file share</span></span>](#unc-share)
- <span data-ttu-id="713a4-133">[Beveiligingsintelligentie-updates](https://www.microsoft.com/en-us/wdsi/defenderupdates) voor Microsoft Defender Antivirus en andere microsoft-antimalware (Uw beleid en register kunnen dit vermeld hebben als beveiligingsinformatie van Microsoft Malware Protection Center (MMPC), de voormalige naam.)</span><span class="sxs-lookup"><span data-stu-id="713a4-133">[Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates) (Your policy and registry might have this listed as Microsoft Malware Protection Center (MMPC) security intelligence, its former name.)</span></span>

<span data-ttu-id="713a4-134">Om het beste beschermingsniveau te garanderen, zorgt Microsoft Update voor snelle versies, wat betekent dat er regelmatig kleinere downloads worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="713a4-134">To ensure the best level of protection, Microsoft Update allows for rapid releases, which means smaller downloads on a frequent basis.</span></span> <span data-ttu-id="713a4-135">De Windows Server Update Service, Microsoft Endpoint Configuration Manager en microsoft beveiligingsinformatieupdates leveren minder frequente updates.</span><span class="sxs-lookup"><span data-stu-id="713a4-135">The Windows Server Update Service, Microsoft Endpoint Configuration Manager, and Microsoft security intelligence updates sources deliver less frequent updates.</span></span> <span data-ttu-id="713a4-136">De delta kan dus groter zijn, wat resulteert in grotere downloads.</span><span class="sxs-lookup"><span data-stu-id="713a4-136">Thus, the delta can be larger, resulting in larger downloads.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="713a4-137">Als u [](https://www.microsoft.com/security/portal/definitions/adl.aspx) microsoft beveiligingsinformatiepagina-updates hebt ingesteld als een terugvalbron na Windows Server Update Service of Microsoft Update, worden updates alleen gedownload van beveiligingsinformatie-updates wanneer de huidige update als verouderd wordt beschouwd.</span><span class="sxs-lookup"><span data-stu-id="713a4-137">If you have set [Microsoft Security intelligence page](https://www.microsoft.com/security/portal/definitions/adl.aspx) updates as a fallback source after Windows Server Update Service or Microsoft Update, updates are only downloaded from security intelligence updates when the current update is considered out-of-date.</span></span> <span data-ttu-id="713a4-138">(Dit is standaard zeven opeenvolgende dagen om geen updates van de Windows Server Update Service of Microsoft Update-services toe te passen).</span><span class="sxs-lookup"><span data-stu-id="713a4-138">(By default, this is seven consecutive days of not being able to apply updates from the Windows Server Update Service or Microsoft Update services).</span></span>
> <span data-ttu-id="713a4-139">U kunt echter wel het aantal dagen instellen voordat de beveiliging als verouderd [wordt gerapporteerd.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)</span><span class="sxs-lookup"><span data-stu-id="713a4-139">You can, however, [set the number of days before protection is reported as out-of-date](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span><p>
> <span data-ttu-id="713a4-140">Vanaf maandag 21 oktober 2019 zijn beveiligingsintelligentie-updates uitsluitend SHA-2 ondertekend.</span><span class="sxs-lookup"><span data-stu-id="713a4-140">Starting Monday, October 21, 2019, security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="713a4-141">Apparaten moeten worden bijgewerkt ter ondersteuning van SHA-2 om de meest recente beveiligingsinformatie-updates te krijgen.</span><span class="sxs-lookup"><span data-stu-id="713a4-141">Devices must be updated to support SHA-2 in order to get the latest security intelligence updates.</span></span> <span data-ttu-id="713a4-142">Zie [SHA-2 Code Signing Support requirement 2019 voor Windows en WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="713a4-142">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>

<span data-ttu-id="713a4-143">Elke bron heeft standaardscenario's die afhankelijk zijn van de configuratie van uw netwerk, naast hoe vaak updates worden gepubliceerd, zoals wordt beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="713a4-143">Each source has typical scenarios that depend on how your network is configured, in addition to how often they publish updates, as described in the following table:</span></span>

|<span data-ttu-id="713a4-144">Locatie</span><span class="sxs-lookup"><span data-stu-id="713a4-144">Location</span></span> | <span data-ttu-id="713a4-145">Voorbeeldscenario</span><span class="sxs-lookup"><span data-stu-id="713a4-145">Sample scenario</span></span> |
|---|---|
|<span data-ttu-id="713a4-146">Windows Server Update Service</span><span class="sxs-lookup"><span data-stu-id="713a4-146">Windows Server Update Service</span></span> | <span data-ttu-id="713a4-147">U gebruikt Windows Server Update Service om updates voor uw netwerk te beheren.</span><span class="sxs-lookup"><span data-stu-id="713a4-147">You are using Windows Server Update Service to manage updates for your network.</span></span>|
|<span data-ttu-id="713a4-148">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="713a4-148">Microsoft Update</span></span> | <span data-ttu-id="713a4-149">U wilt dat uw eindpunten rechtstreeks verbinding maken met Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="713a4-149">You want your endpoints to connect directly to Microsoft Update.</span></span> <span data-ttu-id="713a4-150">Dit kan handig zijn voor eindpunten die onregelmatig verbinding maken met uw bedrijfsnetwerk of als u Windows Server Update Service niet gebruikt om uw updates te beheren.</span><span class="sxs-lookup"><span data-stu-id="713a4-150">This can be useful for endpoints that irregularly connect to your enterprise network, or if you do not use Windows Server Update Service to manage your updates.</span></span>|
|<span data-ttu-id="713a4-151">Bestands delen</span><span class="sxs-lookup"><span data-stu-id="713a4-151">File share</span></span> | <span data-ttu-id="713a4-152">U hebt apparaten die niet met internet zijn verbonden (zoals VM's).</span><span class="sxs-lookup"><span data-stu-id="713a4-152">You have non-Internet-connected devices (such as VMs).</span></span> <span data-ttu-id="713a4-153">U kunt uw VM-host met internetverbinding gebruiken om de updates naar een netwerk delen te downloaden, waaruit de VM's de updates kunnen verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="713a4-153">You can use your Internet-connected VM host to download the updates to a network share, from which the VMs can obtain the updates.</span></span> <span data-ttu-id="713a4-154">Zie de [VDI-implementatiehandleiding](deployment-vdi-microsoft-defender-antivirus.md) voor de manier waarop bestandsaandelen kunnen worden gebruikt in VDI-omgevingen (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="713a4-154">See the [VDI deployment guide](deployment-vdi-microsoft-defender-antivirus.md) for how file shares can be used in virtual desktop infrastructure (VDI) environments.</span></span>|
|<span data-ttu-id="713a4-155">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="713a4-155">Microsoft Endpoint Manager</span></span> | <span data-ttu-id="713a4-156">U gebruikt Microsoft Endpoint Manager om uw eindpunten bij te werken.</span><span class="sxs-lookup"><span data-stu-id="713a4-156">You are using Microsoft Endpoint Manager to update your endpoints.</span></span>|
|<span data-ttu-id="713a4-157">Beveiligingsintelligentieupdates voor Microsoft Defender Antivirus en andere Microsoft-antimalware (voorheen MMPC genoemd)</span><span class="sxs-lookup"><span data-stu-id="713a4-157">Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware (formerly referred to as MMPC)</span></span> |<span data-ttu-id="713a4-158">[Zorg ervoor dat uw apparaten worden bijgewerkt om SHA-2 te ondersteunen.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)</span><span class="sxs-lookup"><span data-stu-id="713a4-158">[Make sure your devices are updated to support SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span> <span data-ttu-id="713a4-159">Microsoft Defender Antivirus Security Intelligence-updates worden geleverd via Windows Update en vanaf maandag 21 oktober 2019 zijn beveiligingsinformatie-updates sha-2 exclusief ondertekend.</span><span class="sxs-lookup"><span data-stu-id="713a4-159">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update, and starting Monday October 21, 2019 security intelligence updates will be SHA-2 signed exclusively.</span></span> <br/><span data-ttu-id="713a4-160">Download de meest recente beveiligingsupdates vanwege een recente infectie of om een sterke basisafbeelding in te stellen voor [VDI-implementatie.](deployment-vdi-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="713a4-160">Download the latest protection updates because of a recent infection or to help provision a strong, base image for [VDI deployment](deployment-vdi-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="713a4-161">Deze optie moet over het algemeen alleen worden gebruikt als een definitieve fallbackbron en niet als primaire bron.</span><span class="sxs-lookup"><span data-stu-id="713a4-161">This option should generally be used only as a final fallback source, and not the primary source.</span></span> <span data-ttu-id="713a4-162">Deze wordt alleen gebruikt als updates niet kunnen worden gedownload van Windows Server Update Service of Microsoft Update voor een [bepaald aantal dagen.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)</span><span class="sxs-lookup"><span data-stu-id="713a4-162">It will only be used if updates cannot be downloaded from Windows Server Update Service or Microsoft Update for [a specified number of days](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span>|

<span data-ttu-id="713a4-163">U kunt de volgorde beheren waarin updatebronnen worden gebruikt met groepsbeleid, Microsoft Endpoint Configuration Manager, PowerShell-cmdlets en WMI.</span><span class="sxs-lookup"><span data-stu-id="713a4-163">You can manage the order in which update sources are used with Group Policy, Microsoft Endpoint Configuration Manager, PowerShell cmdlets, and WMI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="713a4-164">Als u Windows Server Update Service als downloadlocatie in stelt, moet u de updates goedkeuren, ongeacht het beheerprogramma dat u gebruikt om de locatie op te geven.</span><span class="sxs-lookup"><span data-stu-id="713a4-164">If you set Windows Server Update Service as a download location, you must approve the updates, regardless of the management tool you use to specify the location.</span></span> <span data-ttu-id="713a4-165">U kunt een automatische goedkeuringsregel instellen met Windows Server Update Service, wat handig kan zijn als updates ten minste eenmaal per dag binnenkomen.</span><span class="sxs-lookup"><span data-stu-id="713a4-165">You can set up an automatic approval rule with Windows Server Update Service, which might be useful as updates arrive at least once a day.</span></span> <span data-ttu-id="713a4-166">Zie Updates voor eindpuntbeveiliging synchroniseren in zelfstandige Windows Server Update Service voor [meer informatie.](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="713a4-166">To learn more, see [synchronize endpoint protection updates in standalone Windows Server Update Service](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

<span data-ttu-id="713a4-167">In de procedures in dit artikel wordt eerst beschreven hoe  u de volgorde instelt en vervolgens hoe u de optie Bestands delen instelt als u deze hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="713a4-167">The procedures in this article first describe how to set the order, and then how to set up the **File share** option if you have enabled it.</span></span>

## <a name="use-group-policy-to-manage-the-update-location"></a><span data-ttu-id="713a4-168">Groepsbeleid gebruiken om de updatelocatie te beheren</span><span class="sxs-lookup"><span data-stu-id="713a4-168">Use Group Policy to manage the update location</span></span>

1. <span data-ttu-id="713a4-169">Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="713a4-169">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="713a4-170">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="713a4-170">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="713a4-171">Klik **op Beleid** en vervolgens op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="713a4-171">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="713a4-172">Vouw de structuur uit naar **Windows-onderdelen > Windows Defender > signature-updates** en configureer de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="713a4-172">Expand the tree to **Windows components > Windows Defender > Signature updates** and configure the following settings:</span></span>

   1.  <span data-ttu-id="713a4-173">Dubbelklik op de instelling De volgorde van bronnen definiëren voor het downloaden van **beveiligingsinformatieupdates** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="713a4-173">Double-click the **Define the order of sources for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   2.  <span data-ttu-id="713a4-174">Voer de volgorde van bronnen in, gescheiden door één pijp, bijvoorbeeld: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` , zoals wordt weergegeven in de volgende schermafbeelding.</span><span class="sxs-lookup"><span data-stu-id="713a4-174">Enter the order of sources, separated by a single pipe, for example: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC`, as shown in the following screenshot.</span></span>

   ![Schermafbeelding van groepsbeleidsinstelling met de volgorde van bronnen](images/defender/wdav-order-update-sources.png)

   3. <span data-ttu-id="713a4-176">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="713a4-176">Click **OK**.</span></span> <span data-ttu-id="713a4-177">Hiermee wordt de volgorde van beveiligingsupdatebronnen ingesteld.</span><span class="sxs-lookup"><span data-stu-id="713a4-177">This will set the order of protection update sources.</span></span>

   4. <span data-ttu-id="713a4-178">Dubbelklik op de **instelling Bestandsaandelen definiëren voor het downloaden van beveiligingsinformatieupdates** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="713a4-178">Double-click the **Define file shares for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   5. <span data-ttu-id="713a4-179">Voer de bestandsbestandsbron in.</span><span class="sxs-lookup"><span data-stu-id="713a4-179">Enter the file share source.</span></span> <span data-ttu-id="713a4-180">Als u meerdere bronnen hebt, voert u elke bron in in de volgorde waarin deze moet worden gebruikt, gescheiden door één pijp.</span><span class="sxs-lookup"><span data-stu-id="713a4-180">If you have multiple sources, enter each source in the order they should be used, separated by a single pipe.</span></span> <span data-ttu-id="713a4-181">Gebruik [standaard UNC-notatie om](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) het pad aan te geven, bijvoorbeeld: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` .</span><span class="sxs-lookup"><span data-stu-id="713a4-181">Use [standard UNC notation](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) for denoting the path, for example: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name`.</span></span>  <span data-ttu-id="713a4-182">Als u geen paden typt, wordt deze bron overgeslagen wanneer de VM updates downloadt.</span><span class="sxs-lookup"><span data-stu-id="713a4-182">If you do not enter any paths, then this source will be skipped when the VM downloads updates.</span></span>

   6. <span data-ttu-id="713a4-183">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="713a4-183">Click **OK**.</span></span> <span data-ttu-id="713a4-184">Hiermee wordt de volgorde van bestandsaandelen ingesteld wanneer naar die bron wordt verwezen in de groepsbeleidsinstelling De **volgorde van bronnen definiëren...**</span><span class="sxs-lookup"><span data-stu-id="713a4-184">This will set the order of file shares when that source is referenced in the **Define the order of sources...** group policy setting.</span></span>

> [!NOTE]
> <span data-ttu-id="713a4-185">Voor Windows 10, versies 1703 tot en met 1809, is het beleidspad **Windows Components > Microsoft Defender Antivirus > Signature Updates** For Windows 10, version 1903, the policy path is Windows Components > Microsoft Defender Antivirus > Security Intelligence **Updates**</span><span class="sxs-lookup"><span data-stu-id="713a4-185">For Windows 10, versions 1703 up to and including 1809, the policy path is **Windows Components > Microsoft Defender Antivirus > Signature Updates** For Windows 10, version 1903, the policy path is **Windows Components > Microsoft Defender Antivirus > Security Intelligence Updates**</span></span>

## <a name="use-configuration-manager-to-manage-the-update-location"></a><span data-ttu-id="713a4-186">Configuration Manager gebruiken om de updatelocatie te beheren</span><span class="sxs-lookup"><span data-stu-id="713a4-186">Use Configuration Manager to manage the update location</span></span>

<span data-ttu-id="713a4-187">Zie [Beveiligingsintelligentie-updates configureren voor Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) voor meer informatie over het configureren van Microsoft Endpoint Manager (huidige vertakking).</span><span class="sxs-lookup"><span data-stu-id="713a4-187">See [Configure Security intelligence Updates for Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a><span data-ttu-id="713a4-188">PowerShell-cmdlets gebruiken om de updatelocatie te beheren</span><span class="sxs-lookup"><span data-stu-id="713a4-188">Use PowerShell cmdlets to manage the update location</span></span>

<span data-ttu-id="713a4-189">Gebruik de volgende PowerShell-cmdlets om de updatevolgorde in te stellen.</span><span class="sxs-lookup"><span data-stu-id="713a4-189">Use the following PowerShell cmdlets to set the update order.</span></span>

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
<span data-ttu-id="713a4-190">Zie de volgende artikelen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="713a4-190">See the following articles for more information:</span></span>
- [<span data-ttu-id="713a4-191">Set-MpPreference -SignatureFallbackOrder</span><span class="sxs-lookup"><span data-stu-id="713a4-191">Set-MpPreference -SignatureFallbackOrder</span></span>](/powershell/module/defender/set-mppreference)
- [<span data-ttu-id="713a4-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span><span class="sxs-lookup"><span data-stu-id="713a4-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span></span>](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [<span data-ttu-id="713a4-193">PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus te configureren en uit te voeren</span><span class="sxs-lookup"><span data-stu-id="713a4-193">Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="713a4-194">Defender-cmdlets</span><span class="sxs-lookup"><span data-stu-id="713a4-194">Defender cmdlets</span></span>](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a><span data-ttu-id="713a4-195">Windows Management Instruction (WMI) gebruiken om de updatelocatie te beheren</span><span class="sxs-lookup"><span data-stu-id="713a4-195">Use Windows Management Instruction (WMI) to manage the update location</span></span>

<span data-ttu-id="713a4-196">Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="713a4-196">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

<span data-ttu-id="713a4-197">Zie de volgende artikelen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="713a4-197">See the following articles for more information:</span></span>
- [<span data-ttu-id="713a4-198">Windows Defender WMIv2-API's</span><span class="sxs-lookup"><span data-stu-id="713a4-198">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a><span data-ttu-id="713a4-199">Mobile Device Management (MDM) gebruiken om de updatelocatie te beheren</span><span class="sxs-lookup"><span data-stu-id="713a4-199">Use Mobile Device Management (MDM) to manage the update location</span></span>

<span data-ttu-id="713a4-200">Zie [Beleid CSP - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) voor meer informatie over het configureren van MDM.</span><span class="sxs-lookup"><span data-stu-id="713a4-200">See [Policy CSP - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) for details on configuring MDM.</span></span>

## <a name="what-if-were-using-a-third-party-vendor"></a><span data-ttu-id="713a4-201">Wat gebeurt er als we een externe leverancier gebruiken?</span><span class="sxs-lookup"><span data-stu-id="713a4-201">What if we're using a third-party vendor?</span></span>

<span data-ttu-id="713a4-202">In dit artikel wordt beschreven hoe u updates voor Microsoft Defender Antivirus configureert en beheert.</span><span class="sxs-lookup"><span data-stu-id="713a4-202">This article describes how to configure and manage updates for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="713a4-203">Leveranciers van derden kunnen echter worden gebruikt om deze taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="713a4-203">However, third-party vendors can be used to perform these tasks.</span></span> 

<span data-ttu-id="713a4-204">Stel dat Contoso Fabrikam heeft aangenomen om de beveiligingsoplossing te beheren, waaronder Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="713a4-204">For example, suppose that Contoso has hired Fabrikam to manage their security solution, which includes Microsoft Defender Antivirus.</span></span> <span data-ttu-id="713a4-205">Fabrikam gebruikt meestal [Windows Management Instrumentation,](./use-wmi-microsoft-defender-antivirus.md) [PowerShell-cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md)of [Windows-opdrachtregel](./command-line-arguments-microsoft-defender-antivirus.md) om patches en updates te implementeren.</span><span class="sxs-lookup"><span data-stu-id="713a4-205">Fabrikam typically uses [Windows Management Instrumentation](./use-wmi-microsoft-defender-antivirus.md), [PowerShell cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md), or [Windows command-line](./command-line-arguments-microsoft-defender-antivirus.md) to deploy patches and updates.</span></span> 

> [!NOTE]
> <span data-ttu-id="713a4-206">Microsoft test geen oplossingen van derden voor het beheren van Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="713a4-206">Microsoft does not test third-party solutions for managing Microsoft Defender Antivirus.</span></span>

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a><span data-ttu-id="713a4-207">Een UNC-share maken voor beveiligingsinformatie-updates</span><span class="sxs-lookup"><span data-stu-id="713a4-207">Create a UNC share for security intelligence updates</span></span>

<span data-ttu-id="713a4-208">Stel een netwerkbestands delen (UNC/mapped station) in om beveiligingsinformatieupdates van de MMPC-site te downloaden met behulp van een geplande taak.</span><span class="sxs-lookup"><span data-stu-id="713a4-208">Set up a network file share (UNC/mapped drive) to download security intelligence updates from the MMPC site by using a scheduled task.</span></span>

1. <span data-ttu-id="713a4-209">Maak in het systeem waarop u het delen wilt inrichten en de updates wilt downloaden, een map waarop u het script wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="713a4-209">On the system on which you want to provision the share and download the updates, create a folder to which you will save the script.</span></span>
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. <span data-ttu-id="713a4-210">Maak de map waarop u de handtekeningupdates wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="713a4-210">Create the folder to which you will save the signature updates.</span></span>
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. <span data-ttu-id="713a4-211">Download het PowerShell-script van [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4.](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)</span><span class="sxs-lookup"><span data-stu-id="713a4-211">Download the PowerShell script from [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).</span></span>

4. <span data-ttu-id="713a4-212">Klik **op Handmatig downloaden.**</span><span class="sxs-lookup"><span data-stu-id="713a4-212">Click **Manual Download**.</span></span>

5. <span data-ttu-id="713a4-213">Klik **op Het onbewerkte nupkg-bestand downloaden.**</span><span class="sxs-lookup"><span data-stu-id="713a4-213">Click **Download the raw nupkg file**.</span></span>

6. <span data-ttu-id="713a4-214">Haal het bestand op.</span><span class="sxs-lookup"><span data-stu-id="713a4-214">Extract the file.</span></span>

7. <span data-ttu-id="713a4-215">Kopieer het bestand SignatureDownloadCustomTask.ps1 naar de map die u eerder hebt gemaakt, C:\Tool\PS-Scripts\ .</span><span class="sxs-lookup"><span data-stu-id="713a4-215">Copy the file SignatureDownloadCustomTask.ps1 to the folder you previously created, C:\Tool\PS-Scripts\ .</span></span>

8. <span data-ttu-id="713a4-216">Gebruik de opdrachtregel om de geplande taak in te stellen.</span><span class="sxs-lookup"><span data-stu-id="713a4-216">Use the command line to set up the scheduled task.</span></span>
    > [!NOTE]
    > <span data-ttu-id="713a4-217">Er zijn twee soorten updates: volledig en delta.</span><span class="sxs-lookup"><span data-stu-id="713a4-217">There are two types of updates: full and delta.</span></span>
   - <span data-ttu-id="713a4-218">Voor x64 delta:</span><span class="sxs-lookup"><span data-stu-id="713a4-218">For x64 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - <span data-ttu-id="713a4-219">Voor x64 full:</span><span class="sxs-lookup"><span data-stu-id="713a4-219">For x64 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - <span data-ttu-id="713a4-220">Voor x86 delta:</span><span class="sxs-lookup"><span data-stu-id="713a4-220">For x86 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - <span data-ttu-id="713a4-221">Voor x86 full:</span><span class="sxs-lookup"><span data-stu-id="713a4-221">For x86 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

    > [!NOTE]
    > <span data-ttu-id="713a4-222">Wanneer de geplande taken worden gemaakt, vindt u deze in de taakplanning onder Microsoft\Windows\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="713a4-222">When the scheduled tasks are created, you can find these in the Task Scheduler under Microsoft\Windows\Windows Defender</span></span>
9. <span data-ttu-id="713a4-223">Voer elke taak handmatig uit en controleer of u gegevens (mpam-d.exe, mpam-fe.exe en nis_full.exe) in de volgende mappen hebt (mogelijk hebt u verschillende locaties gekozen):</span><span class="sxs-lookup"><span data-stu-id="713a4-223">Run each task manually and verify that you have data (mpam-d.exe, mpam-fe.exe, and nis_full.exe) in the following folders (you might have chosen different locations):</span></span>

   - <span data-ttu-id="713a4-224">C:\Temp\TempSigs\x86</span><span class="sxs-lookup"><span data-stu-id="713a4-224">C:\Temp\TempSigs\x86</span></span>
   - <span data-ttu-id="713a4-225">C:\Temp\TempSigs\x64</span><span class="sxs-lookup"><span data-stu-id="713a4-225">C:\Temp\TempSigs\x64</span></span>

   <span data-ttu-id="713a4-226">Als de geplande taak mislukt, voert u de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="713a4-226">If the scheduled task fails, run the following commands:</span></span>

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86″
    ```
    > [!NOTE]
    > <span data-ttu-id="713a4-227">Problemen kunnen ook het gevolg zijn van het uitvoeringsbeleid.</span><span class="sxs-lookup"><span data-stu-id="713a4-227">Issues could also be due to execution policy.</span></span>
    
10. <span data-ttu-id="713a4-228">Een share maken die verwijst naar C:\Temp\TempSigs (bijvoorbeeld \\ server\updates).</span><span class="sxs-lookup"><span data-stu-id="713a4-228">Create a share pointing to C:\Temp\TempSigs (e.g. \\server\updates).</span></span>
    > [!NOTE]
    > <span data-ttu-id="713a4-229">Geverifieerde gebruikers moeten minimaal 'Lees'-toegang hebben.</span><span class="sxs-lookup"><span data-stu-id="713a4-229">At a minimum, authenticated users must have “Read” access.</span></span>
11. <span data-ttu-id="713a4-230">Stel de locatie voor delen in het beleid in op het delen.</span><span class="sxs-lookup"><span data-stu-id="713a4-230">Set the share location in the policy to the share.</span></span>

    > [!NOTE]
    > <span data-ttu-id="713a4-231">Voeg de map x64 (of x86) niet toe aan het pad.</span><span class="sxs-lookup"><span data-stu-id="713a4-231">Do not add the x64 (or x86) folder in the path.</span></span> <span data-ttu-id="713a4-232">Het mpcmdrun.exe wordt automatisch toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="713a4-232">The mpcmdrun.exe process adds it automatically.</span></span>

## <a name="related-articles"></a><span data-ttu-id="713a4-233">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="713a4-233">Related articles</span></span>

- [<span data-ttu-id="713a4-234">Microsoft Defender Antivirus implementeren</span><span class="sxs-lookup"><span data-stu-id="713a4-234">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="713a4-235">Microsoft Defender Antivirus-updates beheren en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="713a4-235">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="713a4-236">Updates beheren voor eindpunten die verouderd zijn</span><span class="sxs-lookup"><span data-stu-id="713a4-236">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="713a4-237">Op basis van gebeurtenissen afgedwongen updates beheren</span><span class="sxs-lookup"><span data-stu-id="713a4-237">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="713a4-238">Updates voor mobiele apparaten en VM's beheren</span><span class="sxs-lookup"><span data-stu-id="713a4-238">Manage updates for mobile devices and VMs</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="713a4-239">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="713a4-239">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)