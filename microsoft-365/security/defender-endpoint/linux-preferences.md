---
title: Voorkeuren instellen voor Microsoft Defender voor Eindpunt op Linux
ms.reviewer: ''
description: Hier wordt beschreven hoe u Microsoft Defender voor Eindpunt op Linux configureert in ondernemingen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installation, deploy, uninstallation, pop, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 00f6bdac66ae286bf55a875599f7097b14b06cb3
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861549"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="80b6c-104">Voorkeuren instellen voor Microsoft Defender voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="80b6c-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="80b6c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="80b6c-105">**Applies to:**</span></span>
- [<span data-ttu-id="80b6c-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="80b6c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="80b6c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80b6c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="80b6c-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="80b6c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="80b6c-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="80b6c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="80b6c-110">Dit onderwerp bevat instructies voor het instellen van voorkeuren voor Defender voor Eindpunt op Linux in bedrijfsomgevingen.</span><span class="sxs-lookup"><span data-stu-id="80b6c-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="80b6c-111">Zie Resources als u geïnteresseerd bent in het configureren [](linux-resources.md#configure-from-the-command-line)van het product op een apparaat vanaf de opdrachtregel.</span><span class="sxs-lookup"><span data-stu-id="80b6c-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="80b6c-112">In bedrijfsomgevingen kan Defender voor Eindpunt op Linux worden beheerd via een configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="80b6c-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="80b6c-113">Dit profiel wordt geïmplementeerd vanuit het beheerprogramma van uw keuze.</span><span class="sxs-lookup"><span data-stu-id="80b6c-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="80b6c-114">Voorkeuren die door de onderneming worden beheerd, hebben voorrang op de voorkeuren die lokaal op het apparaat zijn ingesteld.</span><span class="sxs-lookup"><span data-stu-id="80b6c-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="80b6c-115">Met andere woorden: gebruikers in uw bedrijf kunnen geen voorkeuren wijzigen die zijn ingesteld via dit configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="80b6c-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="80b6c-116">In dit artikel wordt de structuur van dit profiel beschreven (inclusief een aanbevolen profiel dat u kunt gebruiken om aan de slag te gaan) en instructies voor het implementeren van het profiel.</span><span class="sxs-lookup"><span data-stu-id="80b6c-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="80b6c-117">Configuratieprofielstructuur</span><span class="sxs-lookup"><span data-stu-id="80b6c-117">Configuration profile structure</span></span>

<span data-ttu-id="80b6c-118">Het configuratieprofiel is een JSON-bestand dat bestaat uit items die zijn geïdentificeerd met een sleutel (die de naam van de voorkeur aan duidt), gevolgd door een waarde, die afhankelijk is van de aard van de voorkeur.</span><span class="sxs-lookup"><span data-stu-id="80b6c-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="80b6c-119">Waarden kunnen eenvoudig zijn, zoals een numerieke waarde of complex, zoals een geneste lijst met voorkeuren.</span><span class="sxs-lookup"><span data-stu-id="80b6c-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="80b6c-120">Meestal gebruikt u een configuratiebeheerprogramma om een bestand met de naam op de ```mdatp_managed.json``` locatie te ```/etc/opt/microsoft/mdatp/managed/``` pushen.</span><span class="sxs-lookup"><span data-stu-id="80b6c-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="80b6c-121">Het bovenste niveau van het configuratieprofiel bevat productvoorkeuren en vermeldingen voor subareas van het product, die in de volgende secties in meer detail worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="80b6c-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="80b6c-122">Voorkeuren voor antivirusprogramma's</span><span class="sxs-lookup"><span data-stu-id="80b6c-122">Antivirus engine preferences</span></span>

<span data-ttu-id="80b6c-123">De *antivirusEngine-sectie* van het configuratieprofiel wordt gebruikt om de voorkeuren van het antivirusonderdeel van het product te beheren.</span><span class="sxs-lookup"><span data-stu-id="80b6c-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-124">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-124">**Key**</span></span> | <span data-ttu-id="80b6c-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="80b6c-125">antivirusEngine</span></span> |
| <span data-ttu-id="80b6c-126">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-126">**Data type**</span></span> | <span data-ttu-id="80b6c-127">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="80b6c-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="80b6c-128">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-128">**Comments**</span></span> | <span data-ttu-id="80b6c-129">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="80b6c-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="80b6c-130">Realtime beveiliging in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="80b6c-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="80b6c-131">Hiermee bepaalt u of realtimebeveiliging (bestanden scannen terwijl ze worden toegankelijk) is ingeschakeld of niet.</span><span class="sxs-lookup"><span data-stu-id="80b6c-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-132">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-132">**Key**</span></span> | <span data-ttu-id="80b6c-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="80b6c-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="80b6c-134">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-134">**Data type**</span></span> | <span data-ttu-id="80b6c-135">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="80b6c-135">Boolean</span></span> |
| <span data-ttu-id="80b6c-136">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-136">**Possible values**</span></span> | <span data-ttu-id="80b6c-137">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="80b6c-137">true (default)</span></span> <br/> <span data-ttu-id="80b6c-138">onwaar</span><span class="sxs-lookup"><span data-stu-id="80b6c-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="80b6c-139">Passieve modus in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="80b6c-139">Enable / disable passive mode</span></span>

<span data-ttu-id="80b6c-140">Hiermee bepaalt u of de antivirusprogramma's al dan niet in de passieve modus worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="80b6c-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="80b6c-141">In de passieve modus:</span><span class="sxs-lookup"><span data-stu-id="80b6c-141">In passive mode:</span></span>
- <span data-ttu-id="80b6c-142">Realtimebeveiliging is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="80b6c-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="80b6c-143">Scannen op aanvraag is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="80b6c-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="80b6c-144">Automatische herstel van bedreigingen is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="80b6c-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="80b6c-145">Beveiligingsinformatie-updates zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="80b6c-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="80b6c-146">Pictogram statusmenu is verborgen.</span><span class="sxs-lookup"><span data-stu-id="80b6c-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-147">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-147">**Key**</span></span> | <span data-ttu-id="80b6c-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="80b6c-148">passiveMode</span></span> |
| <span data-ttu-id="80b6c-149">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-149">**Data type**</span></span> | <span data-ttu-id="80b6c-150">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="80b6c-150">Boolean</span></span> |
| <span data-ttu-id="80b6c-151">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-151">**Possible values**</span></span> | <span data-ttu-id="80b6c-152">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="80b6c-152">false (default)</span></span> <br/> <span data-ttu-id="80b6c-153">waar</span><span class="sxs-lookup"><span data-stu-id="80b6c-153">true</span></span> |
| <span data-ttu-id="80b6c-154">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-154">**Comments**</span></span> | <span data-ttu-id="80b6c-155">Beschikbaar in Defender voor Eindpunt versie 100.67.60 of hoger.</span><span class="sxs-lookup"><span data-stu-id="80b6c-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="80b6c-156">Beleid voor samenvoeging van uitsluiting</span><span class="sxs-lookup"><span data-stu-id="80b6c-156">Exclusion merge policy</span></span>

<span data-ttu-id="80b6c-157">Hiermee geeft u het samenvoegbeleid voor uitsluitingen op.</span><span class="sxs-lookup"><span data-stu-id="80b6c-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="80b6c-158">Het kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde uitsluitingen ( ) of alleen `merge` door beheerders gedefinieerde uitsluitingen ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="80b6c-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="80b6c-159">Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen uitsluitingen definiëren.</span><span class="sxs-lookup"><span data-stu-id="80b6c-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-160">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-160">**Key**</span></span> | <span data-ttu-id="80b6c-161">uitsluitingenMergePolicy</span><span class="sxs-lookup"><span data-stu-id="80b6c-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="80b6c-162">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-162">**Data type**</span></span> | <span data-ttu-id="80b6c-163">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-163">String</span></span> |
| <span data-ttu-id="80b6c-164">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-164">**Possible values**</span></span> | <span data-ttu-id="80b6c-165">samenvoegen (standaard)</span><span class="sxs-lookup"><span data-stu-id="80b6c-165">merge (default)</span></span> <br/> <span data-ttu-id="80b6c-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="80b6c-166">admin_only</span></span> |
| <span data-ttu-id="80b6c-167">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-167">**Comments**</span></span> | <span data-ttu-id="80b6c-168">Beschikbaar in Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="80b6c-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="80b6c-169">Uitsluitingen scannen</span><span class="sxs-lookup"><span data-stu-id="80b6c-169">Scan exclusions</span></span>

<span data-ttu-id="80b6c-170">Entiteiten die zijn uitgesloten van de scan.</span><span class="sxs-lookup"><span data-stu-id="80b6c-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="80b6c-171">Uitsluitingen kunnen worden opgegeven door volledige paden, extensies of bestandsnamen.</span><span class="sxs-lookup"><span data-stu-id="80b6c-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="80b6c-172">(Uitsluitingen worden opgegeven als een matrix met items, beheerder kan zo veel elementen opgeven als nodig is, in elke volgorde.)</span><span class="sxs-lookup"><span data-stu-id="80b6c-172">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-173">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-173">**Key**</span></span> | <span data-ttu-id="80b6c-174">uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="80b6c-174">exclusions</span></span> |
| <span data-ttu-id="80b6c-175">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-175">**Data type**</span></span> | <span data-ttu-id="80b6c-176">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="80b6c-176">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="80b6c-177">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-177">**Comments**</span></span> | <span data-ttu-id="80b6c-178">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="80b6c-178">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="80b6c-179">**Type uitsluiting**</span><span class="sxs-lookup"><span data-stu-id="80b6c-179">**Type of exclusion**</span></span>

<span data-ttu-id="80b6c-180">Hiermee geeft u het type inhoud op dat is uitgesloten van de scan.</span><span class="sxs-lookup"><span data-stu-id="80b6c-180">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-181">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-181">**Key**</span></span> | <span data-ttu-id="80b6c-182">$type</span><span class="sxs-lookup"><span data-stu-id="80b6c-182">$type</span></span> |
| <span data-ttu-id="80b6c-183">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-183">**Data type**</span></span> | <span data-ttu-id="80b6c-184">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-184">String</span></span> |
| <span data-ttu-id="80b6c-185">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-185">**Possible values**</span></span> | <span data-ttu-id="80b6c-186">excludedPath</span><span class="sxs-lookup"><span data-stu-id="80b6c-186">excludedPath</span></span> <br/> <span data-ttu-id="80b6c-187">uitgeslotenFileExtension</span><span class="sxs-lookup"><span data-stu-id="80b6c-187">excludedFileExtension</span></span> <br/> <span data-ttu-id="80b6c-188">uitgeslotenFileName</span><span class="sxs-lookup"><span data-stu-id="80b6c-188">excludedFileName</span></span> |
|||

<span data-ttu-id="80b6c-189">**Pad naar uitgesloten inhoud**</span><span class="sxs-lookup"><span data-stu-id="80b6c-189">**Path to excluded content**</span></span>

<span data-ttu-id="80b6c-190">Wordt gebruikt om inhoud op volledig bestandspad uit te sluiten van de scan.</span><span class="sxs-lookup"><span data-stu-id="80b6c-190">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-191">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-191">**Key**</span></span> | <span data-ttu-id="80b6c-192">pad</span><span class="sxs-lookup"><span data-stu-id="80b6c-192">path</span></span> |
| <span data-ttu-id="80b6c-193">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-193">**Data type**</span></span> | <span data-ttu-id="80b6c-194">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-194">String</span></span> |
| <span data-ttu-id="80b6c-195">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-195">**Possible values**</span></span> | <span data-ttu-id="80b6c-196">geldige paden</span><span class="sxs-lookup"><span data-stu-id="80b6c-196">valid paths</span></span> |
| <span data-ttu-id="80b6c-197">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-197">**Comments**</span></span> | <span data-ttu-id="80b6c-198">Alleen van toepassing *als $type* *is uitgeslotenPath*</span><span class="sxs-lookup"><span data-stu-id="80b6c-198">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="80b6c-199">**Padtype (bestand /adreslijst)**</span><span class="sxs-lookup"><span data-stu-id="80b6c-199">**Path type (file / directory)**</span></span>

<span data-ttu-id="80b6c-200">Hiermee wordt aangegeven of *de eigenschap pad* verwijst naar een bestand of adreslijst.</span><span class="sxs-lookup"><span data-stu-id="80b6c-200">Indicates if the *path* property refers to a file or directory.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-201">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-201">**Key**</span></span> | <span data-ttu-id="80b6c-202">isDirectory</span><span class="sxs-lookup"><span data-stu-id="80b6c-202">isDirectory</span></span> |
| <span data-ttu-id="80b6c-203">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-203">**Data type**</span></span> | <span data-ttu-id="80b6c-204">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="80b6c-204">Boolean</span></span> |
| <span data-ttu-id="80b6c-205">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-205">**Possible values**</span></span> | <span data-ttu-id="80b6c-206">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="80b6c-206">false (default)</span></span> <br/> <span data-ttu-id="80b6c-207">waar</span><span class="sxs-lookup"><span data-stu-id="80b6c-207">true</span></span> |
| <span data-ttu-id="80b6c-208">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-208">**Comments**</span></span> | <span data-ttu-id="80b6c-209">Alleen van toepassing *als $type* *is uitgeslotenPath*</span><span class="sxs-lookup"><span data-stu-id="80b6c-209">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="80b6c-210">**Bestandsextensie uitgesloten van de scan**</span><span class="sxs-lookup"><span data-stu-id="80b6c-210">**File extension excluded from the scan**</span></span>

<span data-ttu-id="80b6c-211">Wordt gebruikt om inhoud uit te sluiten van de scan via bestandsextensie.</span><span class="sxs-lookup"><span data-stu-id="80b6c-211">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-212">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-212">**Key**</span></span> | <span data-ttu-id="80b6c-213">extensie</span><span class="sxs-lookup"><span data-stu-id="80b6c-213">extension</span></span> |
| <span data-ttu-id="80b6c-214">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-214">**Data type**</span></span> | <span data-ttu-id="80b6c-215">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-215">String</span></span> |
| <span data-ttu-id="80b6c-216">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-216">**Possible values**</span></span> | <span data-ttu-id="80b6c-217">geldige bestandsextensies</span><span class="sxs-lookup"><span data-stu-id="80b6c-217">valid file extensions</span></span> |
| <span data-ttu-id="80b6c-218">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-218">**Comments**</span></span> | <span data-ttu-id="80b6c-219">Alleen van toepassing *als $type* *is uitgeslotenFileExtension*</span><span class="sxs-lookup"><span data-stu-id="80b6c-219">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="80b6c-220">**Proces uitgesloten van de scan**</span><span class="sxs-lookup"><span data-stu-id="80b6c-220">**Process excluded from the scan**</span></span>

<span data-ttu-id="80b6c-221">Hiermee geeft u een proces op waarvoor alle bestandsactiviteit niet kan worden gescand.</span><span class="sxs-lookup"><span data-stu-id="80b6c-221">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="80b6c-222">Het proces kan worden opgegeven door de naam (bijvoorbeeld) of het volledige `cat` pad `/bin/cat` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="80b6c-222">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-223">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-223">**Key**</span></span> | <span data-ttu-id="80b6c-224">naam</span><span class="sxs-lookup"><span data-stu-id="80b6c-224">name</span></span> |
| <span data-ttu-id="80b6c-225">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-225">**Data type**</span></span> | <span data-ttu-id="80b6c-226">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-226">String</span></span> |
| <span data-ttu-id="80b6c-227">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-227">**Possible values**</span></span> | <span data-ttu-id="80b6c-228">een tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-228">any string</span></span> |
| <span data-ttu-id="80b6c-229">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-229">**Comments**</span></span> | <span data-ttu-id="80b6c-230">Alleen van toepassing *als $type* *is uitgeslotenFileName*</span><span class="sxs-lookup"><span data-stu-id="80b6c-230">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="80b6c-231">Toegestane bedreigingen</span><span class="sxs-lookup"><span data-stu-id="80b6c-231">Allowed threats</span></span>

<span data-ttu-id="80b6c-232">Lijst met bedreigingen (geïdentificeerd met hun naam) die niet worden geblokkeerd door het product en die in plaats daarvan mogen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="80b6c-232">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-233">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-233">**Key**</span></span> | <span data-ttu-id="80b6c-234">toegestaanThreats</span><span class="sxs-lookup"><span data-stu-id="80b6c-234">allowedThreats</span></span> |
| <span data-ttu-id="80b6c-235">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-235">**Data type**</span></span> | <span data-ttu-id="80b6c-236">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="80b6c-236">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="80b6c-237">Niet-toegestaan bedreigingsacties</span><span class="sxs-lookup"><span data-stu-id="80b6c-237">Disallowed threat actions</span></span>

<span data-ttu-id="80b6c-238">Hiermee beperkt u de acties die de lokale gebruiker van een apparaat kan uitvoeren wanneer bedreigingen worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="80b6c-238">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="80b6c-239">De acties in deze lijst worden niet weergegeven in de gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="80b6c-239">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-240">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-240">**Key**</span></span> | <span data-ttu-id="80b6c-241">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="80b6c-241">disallowedThreatActions</span></span> |
| <span data-ttu-id="80b6c-242">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-242">**Data type**</span></span> | <span data-ttu-id="80b6c-243">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="80b6c-243">Array of strings</span></span> |
| <span data-ttu-id="80b6c-244">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-244">**Possible values**</span></span> | <span data-ttu-id="80b6c-245">toestaan (gebruikers kunnen geen bedreigingen toestaan)</span><span class="sxs-lookup"><span data-stu-id="80b6c-245">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="80b6c-246">herstellen (gebruikers kunnen geen bedreigingen herstellen vanuit de quarantaine)</span><span class="sxs-lookup"><span data-stu-id="80b6c-246">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="80b6c-247">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-247">**Comments**</span></span> | <span data-ttu-id="80b6c-248">Beschikbaar in Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="80b6c-248">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="80b6c-249">Instellingen voor bedreigingstype</span><span class="sxs-lookup"><span data-stu-id="80b6c-249">Threat type settings</span></span>

<span data-ttu-id="80b6c-250">De *threatTypeSettings-voorkeur* in de antivirus-engine wordt gebruikt om te bepalen hoe bepaalde bedreigingstypen door het product worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="80b6c-250">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-251">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-251">**Key**</span></span> | <span data-ttu-id="80b6c-252">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="80b6c-252">threatTypeSettings</span></span> |
| <span data-ttu-id="80b6c-253">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-253">**Data type**</span></span> | <span data-ttu-id="80b6c-254">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="80b6c-254">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="80b6c-255">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-255">**Comments**</span></span> | <span data-ttu-id="80b6c-256">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="80b6c-256">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="80b6c-257">**Type bedreiging**</span><span class="sxs-lookup"><span data-stu-id="80b6c-257">**Threat type**</span></span>

<span data-ttu-id="80b6c-258">Type bedreiging waarvoor het gedrag is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="80b6c-258">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-259">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-259">**Key**</span></span> | <span data-ttu-id="80b6c-260">toets</span><span class="sxs-lookup"><span data-stu-id="80b6c-260">key</span></span> |
| <span data-ttu-id="80b6c-261">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-261">**Data type**</span></span> | <span data-ttu-id="80b6c-262">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-262">String</span></span> |
| <span data-ttu-id="80b6c-263">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-263">**Possible values**</span></span> | <span data-ttu-id="80b6c-264">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="80b6c-264">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="80b6c-265">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="80b6c-265">archive_bomb</span></span> |
|||

<span data-ttu-id="80b6c-266">**Actie ondernemen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-266">**Action to take**</span></span>

<span data-ttu-id="80b6c-267">Actie die moet worden ondernomen wanneer u een bedreiging tegenkomt van het type dat is opgegeven in de vorige sectie.</span><span class="sxs-lookup"><span data-stu-id="80b6c-267">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="80b6c-268">Kan het volgende zijn:</span><span class="sxs-lookup"><span data-stu-id="80b6c-268">Can be:</span></span>

- <span data-ttu-id="80b6c-269">**Controle:** Het apparaat is niet beveiligd tegen dit type bedreiging, maar er wordt wel een vermelding over de bedreiging geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="80b6c-269">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="80b6c-270">**Blokkeren:** Het apparaat is beveiligd tegen dit type bedreiging en u wordt op de hoogte gesteld in de beveiligingsconsole.</span><span class="sxs-lookup"><span data-stu-id="80b6c-270">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="80b6c-271">**Uit:** Het apparaat is niet beveiligd tegen dit type bedreiging en er wordt niets geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="80b6c-271">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-272">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-272">**Key**</span></span> | <span data-ttu-id="80b6c-273">waarde</span><span class="sxs-lookup"><span data-stu-id="80b6c-273">value</span></span> |
| <span data-ttu-id="80b6c-274">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-274">**Data type**</span></span> | <span data-ttu-id="80b6c-275">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-275">String</span></span> |
| <span data-ttu-id="80b6c-276">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-276">**Possible values**</span></span> | <span data-ttu-id="80b6c-277">audit (standaard)</span><span class="sxs-lookup"><span data-stu-id="80b6c-277">audit (default)</span></span> <br/> <span data-ttu-id="80b6c-278">blokkering</span><span class="sxs-lookup"><span data-stu-id="80b6c-278">block</span></span> <br/> <span data-ttu-id="80b6c-279">uit</span><span class="sxs-lookup"><span data-stu-id="80b6c-279">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="80b6c-280">Samenvoegbeleid voor instellingen voor bedreigingstype</span><span class="sxs-lookup"><span data-stu-id="80b6c-280">Threat type settings merge policy</span></span>

<span data-ttu-id="80b6c-281">Hiermee geeft u het samenvoegbeleid voor instellingen voor bedreigingstype op.</span><span class="sxs-lookup"><span data-stu-id="80b6c-281">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="80b6c-282">Dit kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde instellingen ( `merge` ) of alleen door beheerders gedefinieerde instellingen ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="80b6c-282">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="80b6c-283">Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen instellingen voor verschillende bedreigingstypen definiëren.</span><span class="sxs-lookup"><span data-stu-id="80b6c-283">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-284">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-284">**Key**</span></span> | <span data-ttu-id="80b6c-285">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="80b6c-285">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="80b6c-286">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-286">**Data type**</span></span> | <span data-ttu-id="80b6c-287">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-287">String</span></span> |
| <span data-ttu-id="80b6c-288">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-288">**Possible values**</span></span> | <span data-ttu-id="80b6c-289">samenvoegen (standaard)</span><span class="sxs-lookup"><span data-stu-id="80b6c-289">merge (default)</span></span> <br/> <span data-ttu-id="80b6c-290">admin_only</span><span class="sxs-lookup"><span data-stu-id="80b6c-290">admin_only</span></span> |
| <span data-ttu-id="80b6c-291">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-291">**Comments**</span></span> | <span data-ttu-id="80b6c-292">Beschikbaar in Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="80b6c-292">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="80b6c-293">Bewaargeschiedenis van antivirusscans (in dagen)</span><span class="sxs-lookup"><span data-stu-id="80b6c-293">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="80b6c-294">Geef het aantal dagen op dat de resultaten worden bewaard in de scangeschiedenis op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="80b6c-294">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="80b6c-295">Oude scanresultaten worden uit de geschiedenis verwijderd.</span><span class="sxs-lookup"><span data-stu-id="80b6c-295">Old scan results are removed from the history.</span></span> <span data-ttu-id="80b6c-296">Oude in quarantaine geplaatste bestanden die ook van de schijf zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="80b6c-296">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-297">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-297">**Key**</span></span> | <span data-ttu-id="80b6c-298">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="80b6c-298">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="80b6c-299">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-299">**Data type**</span></span> | <span data-ttu-id="80b6c-300">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-300">String</span></span> |
| <span data-ttu-id="80b6c-301">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-301">**Possible values**</span></span> | <span data-ttu-id="80b6c-302">90 (standaard).</span><span class="sxs-lookup"><span data-stu-id="80b6c-302">90 (default).</span></span> <span data-ttu-id="80b6c-303">Toegestane waarden zijn 1 dag tot 180 dagen.</span><span class="sxs-lookup"><span data-stu-id="80b6c-303">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="80b6c-304">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-304">**Comments**</span></span> | <span data-ttu-id="80b6c-305">Beschikbaar in Defender voor Eindpunt versie 101.04.76 of hoger.</span><span class="sxs-lookup"><span data-stu-id="80b6c-305">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="80b6c-306">Maximum aantal items in de geschiedenis van de antivirusscan</span><span class="sxs-lookup"><span data-stu-id="80b6c-306">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="80b6c-307">Geef het maximum aantal items op dat u wilt behouden in de scangeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="80b6c-307">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="80b6c-308">Items zijn alle scans op aanvraag die in het verleden zijn uitgevoerd en alle antivirusdetecties.</span><span class="sxs-lookup"><span data-stu-id="80b6c-308">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-309">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-309">**Key**</span></span> | <span data-ttu-id="80b6c-310">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="80b6c-310">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="80b6c-311">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-311">**Data type**</span></span> | <span data-ttu-id="80b6c-312">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-312">String</span></span> |
| <span data-ttu-id="80b6c-313">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-313">**Possible values**</span></span> | <span data-ttu-id="80b6c-314">10000 (standaard).</span><span class="sxs-lookup"><span data-stu-id="80b6c-314">10000 (default).</span></span> <span data-ttu-id="80b6c-315">Toegestane waarden zijn van 5000 items tot 15000 items.</span><span class="sxs-lookup"><span data-stu-id="80b6c-315">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="80b6c-316">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-316">**Comments**</span></span> | <span data-ttu-id="80b6c-317">Beschikbaar in Defender voor Eindpunt versie 101.04.76 of hoger.</span><span class="sxs-lookup"><span data-stu-id="80b6c-317">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="80b6c-318">Beveiligingsvoorkeuren in de cloud</span><span class="sxs-lookup"><span data-stu-id="80b6c-318">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="80b6c-319">De *cloudService-vermelding* in het configuratieprofiel wordt gebruikt om de cloudbeveiligingsfunctie van het product te configureren.</span><span class="sxs-lookup"><span data-stu-id="80b6c-319">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-320">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-320">**Key**</span></span> | <span data-ttu-id="80b6c-321">cloudService</span><span class="sxs-lookup"><span data-stu-id="80b6c-321">cloudService</span></span> |
| <span data-ttu-id="80b6c-322">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-322">**Data type**</span></span> | <span data-ttu-id="80b6c-323">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="80b6c-323">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="80b6c-324">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="80b6c-324">**Comments**</span></span> | <span data-ttu-id="80b6c-325">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="80b6c-325">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="80b6c-326">Beveiliging via de cloud in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="80b6c-326">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="80b6c-327">Hiermee bepaalt u of beveiliging in de cloud is ingeschakeld op het apparaat of niet.</span><span class="sxs-lookup"><span data-stu-id="80b6c-327">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="80b6c-328">Als u de beveiliging van uw services wilt verbeteren, raden we u aan deze functie ingeschakeld te houden.</span><span class="sxs-lookup"><span data-stu-id="80b6c-328">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-329">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-329">**Key**</span></span> | <span data-ttu-id="80b6c-330">ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="80b6c-330">enabled</span></span> |
| <span data-ttu-id="80b6c-331">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-331">**Data type**</span></span> | <span data-ttu-id="80b6c-332">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="80b6c-332">Boolean</span></span> |
| <span data-ttu-id="80b6c-333">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-333">**Possible values**</span></span> | <span data-ttu-id="80b6c-334">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="80b6c-334">true (default)</span></span> <br/> <span data-ttu-id="80b6c-335">onwaar</span><span class="sxs-lookup"><span data-stu-id="80b6c-335">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="80b6c-336">Diagnostisch verzamelingsniveau</span><span class="sxs-lookup"><span data-stu-id="80b6c-336">Diagnostic collection level</span></span>

<span data-ttu-id="80b6c-337">Diagnostische gegevens worden gebruikt om Defender voor Eindpunt veilig en up-to-date te houden, problemen op te sporen, te diagnosticeren en op te lossen, en om productverbeteringen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="80b6c-337">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="80b6c-338">Deze instelling bepaalt het niveau van de diagnostische gegevens die door het product naar Microsoft worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="80b6c-338">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-339">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-339">**Key**</span></span> | <span data-ttu-id="80b6c-340">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="80b6c-340">diagnosticLevel</span></span> |
| <span data-ttu-id="80b6c-341">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-341">**Data type**</span></span> | <span data-ttu-id="80b6c-342">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-342">String</span></span> |
| <span data-ttu-id="80b6c-343">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-343">**Possible values**</span></span> | <span data-ttu-id="80b6c-344">optioneel (standaard)</span><span class="sxs-lookup"><span data-stu-id="80b6c-344">optional (default)</span></span> <br/> <span data-ttu-id="80b6c-345">Vereist</span><span class="sxs-lookup"><span data-stu-id="80b6c-345">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="80b6c-346">Automatische voorbeeldinzendingen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="80b6c-346">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="80b6c-347">Hiermee wordt bepaald of verdachte steekproeven (die waarschijnlijk bedreigingen bevatten) naar Microsoft worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="80b6c-347">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="80b6c-348">Er zijn drie niveaus voor het beheren van voorbeeldinzending:</span><span class="sxs-lookup"><span data-stu-id="80b6c-348">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="80b6c-349">**Geen:** er worden geen verdachte steekproeven ingediend bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80b6c-349">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="80b6c-350">**Safe:** alleen verdachte steekproeven die geen persoonlijke gegevens (PII) bevatten, worden automatisch verzonden.</span><span class="sxs-lookup"><span data-stu-id="80b6c-350">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="80b6c-351">Dit is de standaardwaarde voor deze instelling.</span><span class="sxs-lookup"><span data-stu-id="80b6c-351">This is the default value for this setting.</span></span>
- <span data-ttu-id="80b6c-352">**Alle**: alle verdachte steekproeven worden verzonden naar Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80b6c-352">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-353">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-353">**Key**</span></span> | <span data-ttu-id="80b6c-354">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="80b6c-354">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="80b6c-355">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-355">**Data type**</span></span> | <span data-ttu-id="80b6c-356">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="80b6c-356">String</span></span> |
| <span data-ttu-id="80b6c-357">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-357">**Possible values**</span></span> | <span data-ttu-id="80b6c-358">geen</span><span class="sxs-lookup"><span data-stu-id="80b6c-358">none</span></span> <br/> <span data-ttu-id="80b6c-359">veilig (standaard)</span><span class="sxs-lookup"><span data-stu-id="80b6c-359">safe (default)</span></span> <br/> <span data-ttu-id="80b6c-360">alles</span><span class="sxs-lookup"><span data-stu-id="80b6c-360">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="80b6c-361">Automatische beveiligingsinformatie-updates in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="80b6c-361">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="80b6c-362">Hiermee bepaalt u of beveiligingsinformatieupdates automatisch worden geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="80b6c-362">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="80b6c-363">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="80b6c-363">**Key**</span></span> | <span data-ttu-id="80b6c-364">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="80b6c-364">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="80b6c-365">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="80b6c-365">**Data type**</span></span> | <span data-ttu-id="80b6c-366">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="80b6c-366">Boolean</span></span> |
| <span data-ttu-id="80b6c-367">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="80b6c-367">**Possible values**</span></span> | <span data-ttu-id="80b6c-368">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="80b6c-368">true (default)</span></span> <br/> <span data-ttu-id="80b6c-369">onwaar</span><span class="sxs-lookup"><span data-stu-id="80b6c-369">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="80b6c-370">Aanbevolen configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="80b6c-370">Recommended configuration profile</span></span>

<span data-ttu-id="80b6c-371">Om aan de slag te gaan, raden we u aan het volgende configuratieprofiel voor uw bedrijf te gebruiken om te profiteren van alle beveiligingsfuncties die Defender voor Eindpunt biedt.</span><span class="sxs-lookup"><span data-stu-id="80b6c-371">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="80b6c-372">Het volgende configuratieprofiel is:</span><span class="sxs-lookup"><span data-stu-id="80b6c-372">The following configuration profile will:</span></span>

- <span data-ttu-id="80b6c-373">Realtimebeveiliging inschakelen (RTP)</span><span class="sxs-lookup"><span data-stu-id="80b6c-373">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="80b6c-374">Geef op hoe de volgende bedreigingstypen worden verwerkt:</span><span class="sxs-lookup"><span data-stu-id="80b6c-374">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="80b6c-375">**Potentieel ongewenste toepassingen (PUA)** worden geblokkeerd</span><span class="sxs-lookup"><span data-stu-id="80b6c-375">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="80b6c-376">**Archiefbommen** (bestand met een hoge compressiesnelheid) worden gecontroleerd op de productlogboeken</span><span class="sxs-lookup"><span data-stu-id="80b6c-376">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="80b6c-377">Automatische beveiligingsinformatie-updates inschakelen</span><span class="sxs-lookup"><span data-stu-id="80b6c-377">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="80b6c-378">Cloudbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="80b6c-378">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="80b6c-379">Automatische voorbeeldinzending op niveau `safe` inschakelen</span><span class="sxs-lookup"><span data-stu-id="80b6c-379">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="80b6c-380">Voorbeeldprofiel</span><span class="sxs-lookup"><span data-stu-id="80b6c-380">Sample profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="80b6c-381">Voorbeeld van volledig configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="80b6c-381">Full configuration profile example</span></span>

<span data-ttu-id="80b6c-382">Het volgende configuratieprofiel bevat vermeldingen voor alle instellingen die in dit document worden beschreven en kunnen worden gebruikt voor meer geavanceerde scenario's waarin u meer controle over het product wilt.</span><span class="sxs-lookup"><span data-stu-id="80b6c-382">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="80b6c-383">Volledig profiel</span><span class="sxs-lookup"><span data-stu-id="80b6c-383">Full profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="80b6c-384">Configuratieprofielvalidatie</span><span class="sxs-lookup"><span data-stu-id="80b6c-384">Configuration profile validation</span></span>

<span data-ttu-id="80b6c-385">Het configuratieprofiel moet een geldig bestand met JSON-indeling zijn.</span><span class="sxs-lookup"><span data-stu-id="80b6c-385">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="80b6c-386">Er zijn een aantal hulpprogramma's die kunnen worden gebruikt om dit te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="80b6c-386">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="80b6c-387">Als u bijvoorbeeld op uw apparaat `python` hebt geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="80b6c-387">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="80b6c-388">Als de JSON goed is gevormd, wordt deze met de bovenstaande opdracht terug naar de Terminal uitgevoerd en wordt een exitcode van `0` .</span><span class="sxs-lookup"><span data-stu-id="80b6c-388">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="80b6c-389">Anders wordt een fout weergegeven die het probleem beschrijft en retourneert de opdracht een exitcode van `1` .</span><span class="sxs-lookup"><span data-stu-id="80b6c-389">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="80b6c-390">Controleren of de mdatp_managed.jsbestand werkt zoals verwacht</span><span class="sxs-lookup"><span data-stu-id="80b6c-390">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="80b6c-391">Als u wilt controleren of uw /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsop naar behoren werkt, ziet u '[beheerd]' naast deze instellingen:</span><span class="sxs-lookup"><span data-stu-id="80b6c-391">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>
- <span data-ttu-id="80b6c-392">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="80b6c-392">cloud_enabled</span></span>
- <span data-ttu-id="80b6c-393">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="80b6c-393">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="80b6c-394">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="80b6c-394">passice_mode_enabled</span></span>
- <span data-ttu-id="80b6c-395">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="80b6c-395">real_time_protection_enabled</span></span>
- <span data-ttu-id="80b6c-396">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="80b6c-396">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="80b6c-397">Als de mdatp_managed.jsin werking treedt, is er geen herstart van de wdavdaemon vereist.</span><span class="sxs-lookup"><span data-stu-id="80b6c-397">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="80b6c-398">Implementatie van configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="80b6c-398">Configuration profile deployment</span></span>

<span data-ttu-id="80b6c-399">Nadat u het configuratieprofiel voor uw onderneming hebt gemaakt, kunt u het implementeren via het beheerprogramma dat uw bedrijf gebruikt.</span><span class="sxs-lookup"><span data-stu-id="80b6c-399">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="80b6c-400">Defender for Endpoint op Linux leest de beheerde configuratie voor uit het *bestand /etc/opt/microsoft/mdatp/managed/mdatp_managed.js.*</span><span class="sxs-lookup"><span data-stu-id="80b6c-400">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
