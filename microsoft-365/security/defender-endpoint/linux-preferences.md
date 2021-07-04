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
ms.openlocfilehash: 7998e878ad03fdfb64c314dc8b7234ece46164ce
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289485"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="48f94-104">Voorkeuren instellen voor Microsoft Defender voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="48f94-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="48f94-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="48f94-105">**Applies to:**</span></span>
- [<span data-ttu-id="48f94-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="48f94-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="48f94-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48f94-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="48f94-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="48f94-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="48f94-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="48f94-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="48f94-110">Dit onderwerp bevat instructies voor het instellen van voorkeuren voor Defender voor Eindpunt op Linux in bedrijfsomgevingen.</span><span class="sxs-lookup"><span data-stu-id="48f94-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="48f94-111">Zie Resources als u geïnteresseerd bent in het configureren [](linux-resources.md#configure-from-the-command-line)van het product op een apparaat vanaf de opdrachtregel.</span><span class="sxs-lookup"><span data-stu-id="48f94-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="48f94-112">In bedrijfsomgevingen kan Defender voor Eindpunt op Linux worden beheerd via een configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="48f94-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="48f94-113">Dit profiel wordt geïmplementeerd vanuit het beheerprogramma van uw keuze.</span><span class="sxs-lookup"><span data-stu-id="48f94-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="48f94-114">Voorkeuren die door de onderneming worden beheerd, hebben voorrang op de voorkeuren die lokaal op het apparaat zijn ingesteld.</span><span class="sxs-lookup"><span data-stu-id="48f94-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="48f94-115">Met andere woorden: gebruikers in uw bedrijf kunnen geen voorkeuren wijzigen die zijn ingesteld via dit configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="48f94-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="48f94-116">In dit artikel wordt de structuur van dit profiel beschreven (inclusief een aanbevolen profiel dat u kunt gebruiken om aan de slag te gaan) en instructies voor het implementeren van het profiel.</span><span class="sxs-lookup"><span data-stu-id="48f94-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="48f94-117">Configuratieprofielstructuur</span><span class="sxs-lookup"><span data-stu-id="48f94-117">Configuration profile structure</span></span>

<span data-ttu-id="48f94-118">Het configuratieprofiel is een JSON-bestand dat bestaat uit items die zijn geïdentificeerd met een sleutel (die de naam van de voorkeur aan duidt), gevolgd door een waarde, die afhankelijk is van de aard van de voorkeur.</span><span class="sxs-lookup"><span data-stu-id="48f94-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="48f94-119">Waarden kunnen eenvoudig zijn, zoals een numerieke waarde of complex, zoals een geneste lijst met voorkeuren.</span><span class="sxs-lookup"><span data-stu-id="48f94-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="48f94-120">Meestal gebruikt u een configuratiebeheerprogramma om een bestand met de naam op de ```mdatp_managed.json``` locatie te ```/etc/opt/microsoft/mdatp/managed/``` pushen.</span><span class="sxs-lookup"><span data-stu-id="48f94-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="48f94-121">Het bovenste niveau van het configuratieprofiel bevat productvoorkeuren en vermeldingen voor subareas van het product, die in de volgende secties in meer detail worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="48f94-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="48f94-122">Voorkeuren voor antivirusprogramma's</span><span class="sxs-lookup"><span data-stu-id="48f94-122">Antivirus engine preferences</span></span>

<span data-ttu-id="48f94-123">De *antivirusEngine-sectie* van het configuratieprofiel wordt gebruikt om de voorkeuren van het antivirusonderdeel van het product te beheren.</span><span class="sxs-lookup"><span data-stu-id="48f94-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

<br>

****

|<span data-ttu-id="48f94-124">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-124">Description</span></span>|<span data-ttu-id="48f94-125">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-125">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-126">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-126">**Key**</span></span>|<span data-ttu-id="48f94-127">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="48f94-127">antivirusEngine</span></span>|
|<span data-ttu-id="48f94-128">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-128">**Data type**</span></span>|<span data-ttu-id="48f94-129">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="48f94-129">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="48f94-130">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-130">**Comments**</span></span>|<span data-ttu-id="48f94-131">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="48f94-131">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="48f94-132">Realtime beveiliging in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="48f94-132">Enable / disable real-time protection</span></span>

<span data-ttu-id="48f94-133">Hiermee bepaalt u of realtimebeveiliging (bestanden scannen terwijl ze worden toegankelijk) is ingeschakeld of niet.</span><span class="sxs-lookup"><span data-stu-id="48f94-133">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

<br>

****

|<span data-ttu-id="48f94-134">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-134">Description</span></span>|<span data-ttu-id="48f94-135">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-135">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-136">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-136">**Key**</span></span>|<span data-ttu-id="48f94-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="48f94-137">enableRealTimeProtection</span></span>|
|<span data-ttu-id="48f94-138">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-138">**Data type**</span></span>|<span data-ttu-id="48f94-139">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-139">Boolean</span></span>|
|<span data-ttu-id="48f94-140">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-140">**Possible values**</span></span>|<span data-ttu-id="48f94-141">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="48f94-141">true (default)</span></span> <p> <span data-ttu-id="48f94-142">onwaar</span><span class="sxs-lookup"><span data-stu-id="48f94-142">false</span></span>|
|

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="48f94-143">Passieve modus in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="48f94-143">Enable / disable passive mode</span></span>

<span data-ttu-id="48f94-144">Hiermee bepaalt u of de antivirusprogramma's al dan niet in de passieve modus worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="48f94-144">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="48f94-145">In de passieve modus:</span><span class="sxs-lookup"><span data-stu-id="48f94-145">In passive mode:</span></span>

- <span data-ttu-id="48f94-146">Realtimebeveiliging is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="48f94-146">Real-time protection is turned off.</span></span>
- <span data-ttu-id="48f94-147">Scannen op aanvraag is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="48f94-147">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="48f94-148">Automatische herstel van bedreigingen is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="48f94-148">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="48f94-149">Beveiligingsinformatie-updates zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="48f94-149">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="48f94-150">Pictogram statusmenu is verborgen.</span><span class="sxs-lookup"><span data-stu-id="48f94-150">Status menu icon is hidden.</span></span>

<br>

****

|<span data-ttu-id="48f94-151">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-151">Description</span></span>|<span data-ttu-id="48f94-152">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-152">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-153">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-153">**Key**</span></span>|<span data-ttu-id="48f94-154">passiveMode</span><span class="sxs-lookup"><span data-stu-id="48f94-154">passiveMode</span></span>|
|<span data-ttu-id="48f94-155">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-155">**Data type**</span></span>|<span data-ttu-id="48f94-156">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-156">Boolean</span></span>|
|<span data-ttu-id="48f94-157">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-157">**Possible values**</span></span>|<span data-ttu-id="48f94-158">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="48f94-158">false (default)</span></span> <p> <span data-ttu-id="48f94-159">waar</span><span class="sxs-lookup"><span data-stu-id="48f94-159">true</span></span>|
|<span data-ttu-id="48f94-160">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-160">**Comments**</span></span>|<span data-ttu-id="48f94-161">Beschikbaar in Defender voor Eindpunt versie 100.67.60 of hoger.</span><span class="sxs-lookup"><span data-stu-id="48f94-161">Available in Defender for Endpoint version 100.67.60 or higher.</span></span>|
|

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="48f94-162">Beleid voor samenvoeging van uitsluiting</span><span class="sxs-lookup"><span data-stu-id="48f94-162">Exclusion merge policy</span></span>

<span data-ttu-id="48f94-163">Hiermee geeft u het samenvoegbeleid voor uitsluitingen op.</span><span class="sxs-lookup"><span data-stu-id="48f94-163">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="48f94-164">Het kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde uitsluitingen ( ) of alleen `merge` door beheerders gedefinieerde uitsluitingen ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="48f94-164">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="48f94-165">Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen uitsluitingen definiëren.</span><span class="sxs-lookup"><span data-stu-id="48f94-165">This setting can be used to restrict local users from defining their own exclusions.</span></span>

<br>

****

|<span data-ttu-id="48f94-166">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-166">Description</span></span>|<span data-ttu-id="48f94-167">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-167">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-168">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-168">**Key**</span></span>|<span data-ttu-id="48f94-169">uitsluitingenMergePolicy</span><span class="sxs-lookup"><span data-stu-id="48f94-169">exclusionsMergePolicy</span></span>|
|<span data-ttu-id="48f94-170">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-170">**Data type**</span></span>|<span data-ttu-id="48f94-171">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-171">String</span></span>|
|<span data-ttu-id="48f94-172">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-172">**Possible values**</span></span>|<span data-ttu-id="48f94-173">samenvoegen (standaard)</span><span class="sxs-lookup"><span data-stu-id="48f94-173">merge (default)</span></span> <p> <span data-ttu-id="48f94-174">admin_only</span><span class="sxs-lookup"><span data-stu-id="48f94-174">admin_only</span></span>|
|<span data-ttu-id="48f94-175">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-175">**Comments**</span></span>|<span data-ttu-id="48f94-176">Beschikbaar in Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="48f94-176">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="scan-exclusions"></a><span data-ttu-id="48f94-177">Uitsluitingen scannen</span><span class="sxs-lookup"><span data-stu-id="48f94-177">Scan exclusions</span></span>

<span data-ttu-id="48f94-178">Entiteiten die zijn uitgesloten van de scan.</span><span class="sxs-lookup"><span data-stu-id="48f94-178">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="48f94-179">Uitsluitingen kunnen worden opgegeven door volledige paden, extensies of bestandsnamen.</span><span class="sxs-lookup"><span data-stu-id="48f94-179">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="48f94-180">(Uitsluitingen worden opgegeven als een matrix met items, beheerder kan zo veel elementen opgeven als nodig is, in elke volgorde.)</span><span class="sxs-lookup"><span data-stu-id="48f94-180">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

<br>

****

|<span data-ttu-id="48f94-181">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-181">Description</span></span>|<span data-ttu-id="48f94-182">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-182">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-183">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-183">**Key**</span></span>|<span data-ttu-id="48f94-184">uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="48f94-184">exclusions</span></span>|
|<span data-ttu-id="48f94-185">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-185">**Data type**</span></span>|<span data-ttu-id="48f94-186">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="48f94-186">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="48f94-187">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-187">**Comments**</span></span>|<span data-ttu-id="48f94-188">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="48f94-188">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="type-of-exclusion"></a><span data-ttu-id="48f94-189">Type uitsluiting</span><span class="sxs-lookup"><span data-stu-id="48f94-189">Type of exclusion</span></span>

<span data-ttu-id="48f94-190">Hiermee geeft u het type inhoud op dat is uitgesloten van de scan.</span><span class="sxs-lookup"><span data-stu-id="48f94-190">Specifies the type of content excluded from the scan.</span></span>

<br>

****

|<span data-ttu-id="48f94-191">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-191">Description</span></span>|<span data-ttu-id="48f94-192">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-192">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-193">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-193">**Key**</span></span>|<span data-ttu-id="48f94-194">$type</span><span class="sxs-lookup"><span data-stu-id="48f94-194">$type</span></span>|
|<span data-ttu-id="48f94-195">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-195">**Data type**</span></span>|<span data-ttu-id="48f94-196">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-196">String</span></span>|
|<span data-ttu-id="48f94-197">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-197">**Possible values**</span></span>|<span data-ttu-id="48f94-198">excludedPath</span><span class="sxs-lookup"><span data-stu-id="48f94-198">excludedPath</span></span> <p> <span data-ttu-id="48f94-199">uitgeslotenFileExtension</span><span class="sxs-lookup"><span data-stu-id="48f94-199">excludedFileExtension</span></span> <p> <span data-ttu-id="48f94-200">uitgeslotenFileName</span><span class="sxs-lookup"><span data-stu-id="48f94-200">excludedFileName</span></span>|
|

##### <a name="path-to-excluded-content"></a><span data-ttu-id="48f94-201">Pad naar uitgesloten inhoud</span><span class="sxs-lookup"><span data-stu-id="48f94-201">Path to excluded content</span></span>

<span data-ttu-id="48f94-202">Wordt gebruikt om inhoud op volledig bestandspad uit te sluiten van de scan.</span><span class="sxs-lookup"><span data-stu-id="48f94-202">Used to exclude content from the scan by full file path.</span></span>

<br>

****

|<span data-ttu-id="48f94-203">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-203">Description</span></span>|<span data-ttu-id="48f94-204">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-204">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-205">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-205">**Key**</span></span>|<span data-ttu-id="48f94-206">pad</span><span class="sxs-lookup"><span data-stu-id="48f94-206">path</span></span>|
|<span data-ttu-id="48f94-207">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-207">**Data type**</span></span>|<span data-ttu-id="48f94-208">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-208">String</span></span>|
|<span data-ttu-id="48f94-209">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-209">**Possible values**</span></span>|<span data-ttu-id="48f94-210">geldige paden</span><span class="sxs-lookup"><span data-stu-id="48f94-210">valid paths</span></span>|
|<span data-ttu-id="48f94-211">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-211">**Comments**</span></span>|<span data-ttu-id="48f94-212">Alleen van toepassing *als $type* *is uitgeslotenPath*</span><span class="sxs-lookup"><span data-stu-id="48f94-212">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="path-type-file--directory"></a><span data-ttu-id="48f94-213">Padtype (bestand /adreslijst)</span><span class="sxs-lookup"><span data-stu-id="48f94-213">Path type (file / directory)</span></span>

<span data-ttu-id="48f94-214">Hiermee wordt aangegeven of *de eigenschap pad* verwijst naar een bestand of adreslijst.</span><span class="sxs-lookup"><span data-stu-id="48f94-214">Indicates if the *path* property refers to a file or directory.</span></span>

<br>

****

|<span data-ttu-id="48f94-215">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-215">Description</span></span>|<span data-ttu-id="48f94-216">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-216">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-217">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-217">**Key**</span></span>|<span data-ttu-id="48f94-218">isDirectory</span><span class="sxs-lookup"><span data-stu-id="48f94-218">isDirectory</span></span>|
|<span data-ttu-id="48f94-219">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-219">**Data type**</span></span>|<span data-ttu-id="48f94-220">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-220">Boolean</span></span>|
|<span data-ttu-id="48f94-221">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-221">**Possible values**</span></span>|<span data-ttu-id="48f94-222">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="48f94-222">false (default)</span></span> <p> <span data-ttu-id="48f94-223">waar</span><span class="sxs-lookup"><span data-stu-id="48f94-223">true</span></span>|
|<span data-ttu-id="48f94-224">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-224">**Comments**</span></span>|<span data-ttu-id="48f94-225">Alleen van toepassing *als $type* *is uitgeslotenPath*</span><span class="sxs-lookup"><span data-stu-id="48f94-225">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="48f94-226">Bestandsextensie uitgesloten van de scan</span><span class="sxs-lookup"><span data-stu-id="48f94-226">File extension excluded from the scan</span></span>

<span data-ttu-id="48f94-227">Wordt gebruikt om inhoud uit te sluiten van de scan via bestandsextensie.</span><span class="sxs-lookup"><span data-stu-id="48f94-227">Used to exclude content from the scan by file extension.</span></span>

<br>

****

|<span data-ttu-id="48f94-228">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-228">Description</span></span>|<span data-ttu-id="48f94-229">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-229">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-230">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-230">**Key**</span></span>|<span data-ttu-id="48f94-231">extensie</span><span class="sxs-lookup"><span data-stu-id="48f94-231">extension</span></span>|
|<span data-ttu-id="48f94-232">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-232">**Data type**</span></span>|<span data-ttu-id="48f94-233">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-233">String</span></span>|
|<span data-ttu-id="48f94-234">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-234">**Possible values**</span></span>|<span data-ttu-id="48f94-235">geldige bestandsextensies</span><span class="sxs-lookup"><span data-stu-id="48f94-235">valid file extensions</span></span>|
|<span data-ttu-id="48f94-236">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-236">**Comments**</span></span>|<span data-ttu-id="48f94-237">Alleen van toepassing *als $type* *is uitgeslotenFileExtension*</span><span class="sxs-lookup"><span data-stu-id="48f94-237">Applicable only if *$type* is *excludedFileExtension*</span></span>|
|

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="48f94-238">Proces uitgesloten van de scan\*</span><span class="sxs-lookup"><span data-stu-id="48f94-238">Process excluded from the scan\*</span></span>

<span data-ttu-id="48f94-239">Hiermee geeft u een proces op waarvoor alle bestandsactiviteit niet kan worden gescand.</span><span class="sxs-lookup"><span data-stu-id="48f94-239">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="48f94-240">Het proces kan worden opgegeven door de naam (bijvoorbeeld) of het volledige `cat` pad `/bin/cat` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="48f94-240">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

<br>

****

|<span data-ttu-id="48f94-241">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-241">Description</span></span>|<span data-ttu-id="48f94-242">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-242">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-243">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-243">**Key**</span></span>|<span data-ttu-id="48f94-244">naam</span><span class="sxs-lookup"><span data-stu-id="48f94-244">name</span></span>|
|<span data-ttu-id="48f94-245">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-245">**Data type**</span></span>|<span data-ttu-id="48f94-246">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-246">String</span></span>|
|<span data-ttu-id="48f94-247">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-247">**Possible values**</span></span>|<span data-ttu-id="48f94-248">een tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-248">any string</span></span>|
|<span data-ttu-id="48f94-249">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-249">**Comments**</span></span>|<span data-ttu-id="48f94-250">Alleen van toepassing *als $type* *is uitgeslotenFileName*</span><span class="sxs-lookup"><span data-stu-id="48f94-250">Applicable only if *$type* is *excludedFileName*</span></span>|
|

#### <a name="allowed-threats"></a><span data-ttu-id="48f94-251">Toegestane bedreigingen</span><span class="sxs-lookup"><span data-stu-id="48f94-251">Allowed threats</span></span>

<span data-ttu-id="48f94-252">Lijst met bedreigingen (geïdentificeerd met hun naam) die niet worden geblokkeerd door het product en die in plaats daarvan mogen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="48f94-252">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

<br>

****

|<span data-ttu-id="48f94-253">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-253">Description</span></span>|<span data-ttu-id="48f94-254">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-254">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-255">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-255">**Key**</span></span>|<span data-ttu-id="48f94-256">toegestaanThreats</span><span class="sxs-lookup"><span data-stu-id="48f94-256">allowedThreats</span></span>|
|<span data-ttu-id="48f94-257">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-257">**Data type**</span></span>|<span data-ttu-id="48f94-258">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="48f94-258">Array of strings</span></span>|
|

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="48f94-259">Niet-toegestaan bedreigingsacties</span><span class="sxs-lookup"><span data-stu-id="48f94-259">Disallowed threat actions</span></span>

<span data-ttu-id="48f94-260">Hiermee beperkt u de acties die de lokale gebruiker van een apparaat kan uitvoeren wanneer bedreigingen worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="48f94-260">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="48f94-261">De acties in deze lijst worden niet weergegeven in de gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="48f94-261">The actions included in this list are not displayed in the user interface.</span></span>

<br>

****

|<span data-ttu-id="48f94-262">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-262">Description</span></span>|<span data-ttu-id="48f94-263">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-263">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-264">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-264">**Key**</span></span>|<span data-ttu-id="48f94-265">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="48f94-265">disallowedThreatActions</span></span>|
|<span data-ttu-id="48f94-266">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-266">**Data type**</span></span>|<span data-ttu-id="48f94-267">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="48f94-267">Array of strings</span></span>|
|<span data-ttu-id="48f94-268">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-268">**Possible values**</span></span>|<span data-ttu-id="48f94-269">toestaan (gebruikers kunnen geen bedreigingen toestaan)</span><span class="sxs-lookup"><span data-stu-id="48f94-269">allow (restricts users from allowing threats)</span></span> <p> <span data-ttu-id="48f94-270">herstellen (gebruikers kunnen geen bedreigingen herstellen vanuit de quarantaine)</span><span class="sxs-lookup"><span data-stu-id="48f94-270">restore (restricts users from restoring threats from the quarantine)</span></span>|
|<span data-ttu-id="48f94-271">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-271">**Comments**</span></span>|<span data-ttu-id="48f94-272">Beschikbaar in Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="48f94-272">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="threat-type-settings"></a><span data-ttu-id="48f94-273">Instellingen voor bedreigingstype</span><span class="sxs-lookup"><span data-stu-id="48f94-273">Threat type settings</span></span>

<span data-ttu-id="48f94-274">De *threatTypeSettings-voorkeur* in de antivirus-engine wordt gebruikt om te bepalen hoe bepaalde bedreigingstypen door het product worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="48f94-274">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

<br>

****

|<span data-ttu-id="48f94-275">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-275">Description</span></span>|<span data-ttu-id="48f94-276">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-276">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-277">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-277">**Key**</span></span>|<span data-ttu-id="48f94-278">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="48f94-278">threatTypeSettings</span></span>|
|<span data-ttu-id="48f94-279">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-279">**Data type**</span></span>|<span data-ttu-id="48f94-280">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="48f94-280">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="48f94-281">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-281">**Comments**</span></span>|<span data-ttu-id="48f94-282">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="48f94-282">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="threat-type"></a><span data-ttu-id="48f94-283">Type bedreiging</span><span class="sxs-lookup"><span data-stu-id="48f94-283">Threat type</span></span>

<span data-ttu-id="48f94-284">Type bedreiging waarvoor het gedrag is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="48f94-284">Type of threat for which the behavior is configured.</span></span>

<br>

****

|<span data-ttu-id="48f94-285">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-285">Description</span></span>|<span data-ttu-id="48f94-286">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-286">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-287">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-287">**Key**</span></span>|<span data-ttu-id="48f94-288">toets</span><span class="sxs-lookup"><span data-stu-id="48f94-288">key</span></span>|
|<span data-ttu-id="48f94-289">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-289">**Data type**</span></span>|<span data-ttu-id="48f94-290">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-290">String</span></span>|
|<span data-ttu-id="48f94-291">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-291">**Possible values**</span></span>|<span data-ttu-id="48f94-292">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="48f94-292">potentially_unwanted_application</span></span> <p> <span data-ttu-id="48f94-293">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="48f94-293">archive_bomb</span></span>|
|

##### <a name="action-to-take"></a><span data-ttu-id="48f94-294">Actie ondernemen</span><span class="sxs-lookup"><span data-stu-id="48f94-294">Action to take</span></span>

<span data-ttu-id="48f94-295">Actie die moet worden ondernomen wanneer u een bedreiging tegenkomt van het type dat is opgegeven in de vorige sectie.</span><span class="sxs-lookup"><span data-stu-id="48f94-295">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="48f94-296">Kan het volgende zijn:</span><span class="sxs-lookup"><span data-stu-id="48f94-296">Can be:</span></span>

- <span data-ttu-id="48f94-297">**Controle:** Het apparaat is niet beveiligd tegen dit type bedreiging, maar er wordt wel een vermelding over de bedreiging geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="48f94-297">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="48f94-298">**Blokkeren:** Het apparaat is beveiligd tegen dit type bedreiging en u wordt op de hoogte gesteld in de beveiligingsconsole.</span><span class="sxs-lookup"><span data-stu-id="48f94-298">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="48f94-299">**Uit:** Het apparaat is niet beveiligd tegen dit type bedreiging en er wordt niets geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="48f94-299">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

<br>

****

|<span data-ttu-id="48f94-300">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-300">Description</span></span>|<span data-ttu-id="48f94-301">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-301">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-302">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-302">**Key**</span></span>|<span data-ttu-id="48f94-303">waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-303">value</span></span>|
|<span data-ttu-id="48f94-304">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-304">**Data type**</span></span>|<span data-ttu-id="48f94-305">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-305">String</span></span>|
|<span data-ttu-id="48f94-306">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-306">**Possible values**</span></span>|<span data-ttu-id="48f94-307">audit (standaard)</span><span class="sxs-lookup"><span data-stu-id="48f94-307">audit (default)</span></span> <p> <span data-ttu-id="48f94-308">blokkering</span><span class="sxs-lookup"><span data-stu-id="48f94-308">block</span></span> <p> <span data-ttu-id="48f94-309">uit</span><span class="sxs-lookup"><span data-stu-id="48f94-309">off</span></span>|
|

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="48f94-310">Samenvoegbeleid voor instellingen voor bedreigingstype</span><span class="sxs-lookup"><span data-stu-id="48f94-310">Threat type settings merge policy</span></span>

<span data-ttu-id="48f94-311">Hiermee geeft u het samenvoegbeleid voor instellingen voor bedreigingstype op.</span><span class="sxs-lookup"><span data-stu-id="48f94-311">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="48f94-312">Dit kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde instellingen ( `merge` ) of alleen door beheerders gedefinieerde instellingen ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="48f94-312">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="48f94-313">Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen instellingen voor verschillende bedreigingstypen definiëren.</span><span class="sxs-lookup"><span data-stu-id="48f94-313">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

<br>

****

|<span data-ttu-id="48f94-314">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-314">Description</span></span>|<span data-ttu-id="48f94-315">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-315">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-316">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-316">**Key**</span></span>|<span data-ttu-id="48f94-317">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="48f94-317">threatTypeSettingsMergePolicy</span></span>|
|<span data-ttu-id="48f94-318">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-318">**Data type**</span></span>|<span data-ttu-id="48f94-319">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-319">String</span></span>|
|<span data-ttu-id="48f94-320">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-320">**Possible values**</span></span>|<span data-ttu-id="48f94-321">samenvoegen (standaard)</span><span class="sxs-lookup"><span data-stu-id="48f94-321">merge (default)</span></span> <p> <span data-ttu-id="48f94-322">admin_only</span><span class="sxs-lookup"><span data-stu-id="48f94-322">admin_only</span></span>|
|<span data-ttu-id="48f94-323">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-323">**Comments**</span></span>|<span data-ttu-id="48f94-324">Beschikbaar in Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="48f94-324">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="48f94-325">Bewaargeschiedenis van antivirusscans (in dagen)</span><span class="sxs-lookup"><span data-stu-id="48f94-325">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="48f94-326">Geef het aantal dagen op dat de resultaten worden bewaard in de scangeschiedenis op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="48f94-326">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="48f94-327">Oude scanresultaten worden uit de geschiedenis verwijderd.</span><span class="sxs-lookup"><span data-stu-id="48f94-327">Old scan results are removed from the history.</span></span> <span data-ttu-id="48f94-328">Oude in quarantaine geplaatste bestanden die ook van de schijf zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="48f94-328">Old quarantined files that are also removed from the disk.</span></span>

<br>

****

|<span data-ttu-id="48f94-329">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-329">Description</span></span>|<span data-ttu-id="48f94-330">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-330">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-331">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-331">**Key**</span></span>|<span data-ttu-id="48f94-332">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="48f94-332">scanResultsRetentionDays</span></span>|
|<span data-ttu-id="48f94-333">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-333">**Data type**</span></span>|<span data-ttu-id="48f94-334">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-334">String</span></span>|
|<span data-ttu-id="48f94-335">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-335">**Possible values**</span></span>|<span data-ttu-id="48f94-336">90 (standaard).</span><span class="sxs-lookup"><span data-stu-id="48f94-336">90 (default).</span></span> <span data-ttu-id="48f94-337">Toegestane waarden zijn 1 dag tot 180 dagen.</span><span class="sxs-lookup"><span data-stu-id="48f94-337">Allowed values are from 1 day to 180 days.</span></span>|
|<span data-ttu-id="48f94-338">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-338">**Comments**</span></span>|<span data-ttu-id="48f94-339">Beschikbaar in Defender voor Eindpunt versie 101.04.76 of hoger.</span><span class="sxs-lookup"><span data-stu-id="48f94-339">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="48f94-340">Maximum aantal items in de geschiedenis van de antivirusscan</span><span class="sxs-lookup"><span data-stu-id="48f94-340">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="48f94-341">Geef het maximum aantal items op dat u wilt behouden in de scangeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="48f94-341">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="48f94-342">Items zijn alle scans op aanvraag die in het verleden zijn uitgevoerd en alle antivirusdetecties.</span><span class="sxs-lookup"><span data-stu-id="48f94-342">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

<br>

****

|<span data-ttu-id="48f94-343">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-343">Description</span></span>|<span data-ttu-id="48f94-344">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-344">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-345">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-345">**Key**</span></span>|<span data-ttu-id="48f94-346">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="48f94-346">scanHistoryMaximumItems</span></span>|
|<span data-ttu-id="48f94-347">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-347">**Data type**</span></span>|<span data-ttu-id="48f94-348">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-348">String</span></span>|
|<span data-ttu-id="48f94-349">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-349">**Possible values**</span></span>|<span data-ttu-id="48f94-350">10000 (standaard).</span><span class="sxs-lookup"><span data-stu-id="48f94-350">10000 (default).</span></span> <span data-ttu-id="48f94-351">Toegestane waarden zijn van 5000 items tot 15000 items.</span><span class="sxs-lookup"><span data-stu-id="48f94-351">Allowed values are from 5000 items to 15000 items.</span></span>|
|<span data-ttu-id="48f94-352">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-352">**Comments**</span></span>|<span data-ttu-id="48f94-353">Beschikbaar in Defender voor Eindpunt versie 101.04.76 of hoger.</span><span class="sxs-lookup"><span data-stu-id="48f94-353">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="48f94-354">Beveiligingsvoorkeuren in de cloud</span><span class="sxs-lookup"><span data-stu-id="48f94-354">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="48f94-355">De *cloudService-vermelding* in het configuratieprofiel wordt gebruikt om de cloudbeveiligingsfunctie van het product te configureren.</span><span class="sxs-lookup"><span data-stu-id="48f94-355">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

<br>

****

|<span data-ttu-id="48f94-356">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-356">Description</span></span>|<span data-ttu-id="48f94-357">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-357">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-358">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-358">**Key**</span></span>|<span data-ttu-id="48f94-359">cloudService</span><span class="sxs-lookup"><span data-stu-id="48f94-359">cloudService</span></span>|
|<span data-ttu-id="48f94-360">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-360">**Data type**</span></span>|<span data-ttu-id="48f94-361">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="48f94-361">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="48f94-362">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="48f94-362">**Comments**</span></span>|<span data-ttu-id="48f94-363">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="48f94-363">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="48f94-364">Beveiliging via de cloud in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="48f94-364">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="48f94-365">Hiermee bepaalt u of beveiliging in de cloud is ingeschakeld op het apparaat of niet.</span><span class="sxs-lookup"><span data-stu-id="48f94-365">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="48f94-366">Als u de beveiliging van uw services wilt verbeteren, raden we u aan deze functie ingeschakeld te houden.</span><span class="sxs-lookup"><span data-stu-id="48f94-366">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

<br>

****

|<span data-ttu-id="48f94-367">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-367">Description</span></span>|<span data-ttu-id="48f94-368">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-368">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-369">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-369">**Key**</span></span>|<span data-ttu-id="48f94-370">ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="48f94-370">enabled</span></span>|
|<span data-ttu-id="48f94-371">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-371">**Data type**</span></span>|<span data-ttu-id="48f94-372">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-372">Boolean</span></span>|
|<span data-ttu-id="48f94-373">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-373">**Possible values**</span></span>|<span data-ttu-id="48f94-374">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="48f94-374">true (default)</span></span> <p> <span data-ttu-id="48f94-375">onwaar</span><span class="sxs-lookup"><span data-stu-id="48f94-375">false</span></span>|
|

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="48f94-376">Diagnostisch verzamelingsniveau</span><span class="sxs-lookup"><span data-stu-id="48f94-376">Diagnostic collection level</span></span>

<span data-ttu-id="48f94-377">Diagnostische gegevens worden gebruikt om Defender voor Eindpunt veilig en up-to-date te houden, problemen op te sporen, te diagnosticeren en op te lossen, en om productverbeteringen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="48f94-377">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="48f94-378">Deze instelling bepaalt het niveau van de diagnostische gegevens die door het product naar Microsoft worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="48f94-378">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="48f94-379">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-379">Description</span></span>|<span data-ttu-id="48f94-380">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-380">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-381">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-381">**Key**</span></span>|<span data-ttu-id="48f94-382">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="48f94-382">diagnosticLevel</span></span>|
|<span data-ttu-id="48f94-383">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-383">**Data type**</span></span>|<span data-ttu-id="48f94-384">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-384">String</span></span>|
|<span data-ttu-id="48f94-385">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-385">**Possible values**</span></span>|<span data-ttu-id="48f94-386">optioneel (standaard)</span><span class="sxs-lookup"><span data-stu-id="48f94-386">optional (default)</span></span> <p> <span data-ttu-id="48f94-387">Vereist</span><span class="sxs-lookup"><span data-stu-id="48f94-387">required</span></span>|
|

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="48f94-388">Automatische voorbeeldinzendingen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="48f94-388">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="48f94-389">Hiermee wordt bepaald of verdachte steekproeven (die waarschijnlijk bedreigingen bevatten) naar Microsoft worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="48f94-389">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="48f94-390">Er zijn drie niveaus voor het beheren van voorbeeldinzending:</span><span class="sxs-lookup"><span data-stu-id="48f94-390">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="48f94-391">**Geen:** er worden geen verdachte steekproeven ingediend bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="48f94-391">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="48f94-392">**Safe:** alleen verdachte steekproeven die geen persoonlijke gegevens (PII) bevatten, worden automatisch verzonden.</span><span class="sxs-lookup"><span data-stu-id="48f94-392">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="48f94-393">Dit is de standaardwaarde voor deze instelling.</span><span class="sxs-lookup"><span data-stu-id="48f94-393">This is the default value for this setting.</span></span>
- <span data-ttu-id="48f94-394">**Alle**: alle verdachte steekproeven worden verzonden naar Microsoft.</span><span class="sxs-lookup"><span data-stu-id="48f94-394">**All**: all suspicious samples are submitted to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="48f94-395">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-395">Description</span></span>|<span data-ttu-id="48f94-396">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-396">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-397">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-397">**Key**</span></span>|<span data-ttu-id="48f94-398">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="48f94-398">automaticSampleSubmissionConsent</span></span>|
|<span data-ttu-id="48f94-399">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-399">**Data type**</span></span>|<span data-ttu-id="48f94-400">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48f94-400">String</span></span>|
|<span data-ttu-id="48f94-401">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-401">**Possible values**</span></span>|<span data-ttu-id="48f94-402">geen</span><span class="sxs-lookup"><span data-stu-id="48f94-402">none</span></span> <p> <span data-ttu-id="48f94-403">veilig (standaard)</span><span class="sxs-lookup"><span data-stu-id="48f94-403">safe (default)</span></span> <p> <span data-ttu-id="48f94-404">alles</span><span class="sxs-lookup"><span data-stu-id="48f94-404">all</span></span>|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="48f94-405">Automatische beveiligingsinformatie-updates in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="48f94-405">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="48f94-406">Hiermee bepaalt u of beveiligingsinformatieupdates automatisch worden geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="48f94-406">Determines whether security intelligence updates are installed automatically:</span></span>

<br>

****

|<span data-ttu-id="48f94-407">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="48f94-407">Description</span></span>|<span data-ttu-id="48f94-408">Waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-408">Value</span></span>|
|---|---|
|<span data-ttu-id="48f94-409">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="48f94-409">**Key**</span></span>|<span data-ttu-id="48f94-410">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="48f94-410">automaticDefinitionUpdateEnabled</span></span>|
|<span data-ttu-id="48f94-411">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="48f94-411">**Data type**</span></span>|<span data-ttu-id="48f94-412">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="48f94-412">Boolean</span></span>|
|<span data-ttu-id="48f94-413">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="48f94-413">**Possible values**</span></span>|<span data-ttu-id="48f94-414">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="48f94-414">true (default)</span></span> <p> <span data-ttu-id="48f94-415">onwaar</span><span class="sxs-lookup"><span data-stu-id="48f94-415">false</span></span>|
|

## <a name="recommended-configuration-profile"></a><span data-ttu-id="48f94-416">Aanbevolen configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="48f94-416">Recommended configuration profile</span></span>

<span data-ttu-id="48f94-417">Om aan de slag te gaan, raden we u aan het volgende configuratieprofiel voor uw bedrijf te gebruiken om te profiteren van alle beveiligingsfuncties die Defender voor Eindpunt biedt.</span><span class="sxs-lookup"><span data-stu-id="48f94-417">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="48f94-418">Het volgende configuratieprofiel is:</span><span class="sxs-lookup"><span data-stu-id="48f94-418">The following configuration profile will:</span></span>

- <span data-ttu-id="48f94-419">Realtimebeveiliging inschakelen (RTP)</span><span class="sxs-lookup"><span data-stu-id="48f94-419">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="48f94-420">Geef op hoe de volgende bedreigingstypen worden verwerkt:</span><span class="sxs-lookup"><span data-stu-id="48f94-420">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="48f94-421">**Potentieel ongewenste toepassingen (PUA)** worden geblokkeerd</span><span class="sxs-lookup"><span data-stu-id="48f94-421">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="48f94-422">**Archiefbommen** (bestand met een hoge compressiesnelheid) worden gecontroleerd op de productlogboeken</span><span class="sxs-lookup"><span data-stu-id="48f94-422">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="48f94-423">Automatische beveiligingsinformatie-updates inschakelen</span><span class="sxs-lookup"><span data-stu-id="48f94-423">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="48f94-424">Cloudbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="48f94-424">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="48f94-425">Automatische voorbeeldinzending op niveau `safe` inschakelen</span><span class="sxs-lookup"><span data-stu-id="48f94-425">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="48f94-426">Voorbeeldprofiel</span><span class="sxs-lookup"><span data-stu-id="48f94-426">Sample profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="48f94-427">Voorbeeld van volledig configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="48f94-427">Full configuration profile example</span></span>

<span data-ttu-id="48f94-428">Het volgende configuratieprofiel bevat vermeldingen voor alle instellingen die in dit document worden beschreven en kunnen worden gebruikt voor meer geavanceerde scenario's waarin u meer controle over het product wilt.</span><span class="sxs-lookup"><span data-stu-id="48f94-428">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="48f94-429">Volledig profiel</span><span class="sxs-lookup"><span data-stu-id="48f94-429">Full profile</span></span>

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

## <a name="configuration-profile-validation"></a><span data-ttu-id="48f94-430">Configuratieprofielvalidatie</span><span class="sxs-lookup"><span data-stu-id="48f94-430">Configuration profile validation</span></span>

<span data-ttu-id="48f94-431">Het configuratieprofiel moet een geldig bestand met JSON-indeling zijn.</span><span class="sxs-lookup"><span data-stu-id="48f94-431">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="48f94-432">Er zijn een aantal hulpprogramma's die kunnen worden gebruikt om dit te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="48f94-432">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="48f94-433">Als u bijvoorbeeld op uw apparaat `python` hebt geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="48f94-433">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="48f94-434">Als de JSON goed is gevormd, wordt deze met de bovenstaande opdracht terug naar de Terminal uitgevoerd en wordt een exitcode van `0` .</span><span class="sxs-lookup"><span data-stu-id="48f94-434">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="48f94-435">Anders wordt een fout weergegeven die het probleem beschrijft en retourneert de opdracht een exitcode van `1` .</span><span class="sxs-lookup"><span data-stu-id="48f94-435">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="48f94-436">Controleren of de mdatp_managed.jsbestand werkt zoals verwacht</span><span class="sxs-lookup"><span data-stu-id="48f94-436">Verifying that the mdatp_managed.json file is working as expected</span></span>

<span data-ttu-id="48f94-437">Als u wilt controleren of uw /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsop naar behoren werkt, ziet u '[beheerd]' naast deze instellingen:</span><span class="sxs-lookup"><span data-stu-id="48f94-437">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>

- <span data-ttu-id="48f94-438">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="48f94-438">cloud_enabled</span></span>
- <span data-ttu-id="48f94-439">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="48f94-439">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="48f94-440">passive_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="48f94-440">passive_mode_enabled</span></span>
- <span data-ttu-id="48f94-441">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="48f94-441">real_time_protection_enabled</span></span>
- <span data-ttu-id="48f94-442">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="48f94-442">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="48f94-443">Als de mdatp_managed.jsin werking treedt, is er geen herstart van de wdavdaemon vereist.</span><span class="sxs-lookup"><span data-stu-id="48f94-443">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="48f94-444">Implementatie van configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="48f94-444">Configuration profile deployment</span></span>

<span data-ttu-id="48f94-445">Nadat u het configuratieprofiel voor uw onderneming hebt gemaakt, kunt u het implementeren via het beheerprogramma dat uw bedrijf gebruikt.</span><span class="sxs-lookup"><span data-stu-id="48f94-445">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="48f94-446">Defender for Endpoint op Linux leest de beheerde configuratie voor uit het *bestand /etc/opt/microsoft/mdatp/managed/mdatp_managed.js.*</span><span class="sxs-lookup"><span data-stu-id="48f94-446">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
