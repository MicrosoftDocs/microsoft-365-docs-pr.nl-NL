---
title: Voorkeuren instellen voor Microsoft Defender ATP voor Linux
ms.reviewer: ''
description: Hier wordt beschreven hoe u Microsoft Defender ATP configureert voor Linux in ondernemingen.
keywords: microsoft, defender, atp, linux, installatie, implementeren, verwijderen, pop, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 5aedf841ddfc5a592fe4afd2f13d6470e24c438c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587513"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="c88f3-104">Voorkeuren instellen voor Microsoft Defender voor Eindpunt voor Linux</span><span class="sxs-lookup"><span data-stu-id="c88f3-104">Set preferences for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c88f3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c88f3-105">**Applies to:**</span></span>
- [<span data-ttu-id="c88f3-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c88f3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c88f3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c88f3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c88f3-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="c88f3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c88f3-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="c88f3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="c88f3-110">Dit onderwerp bevat instructies voor het instellen van voorkeuren voor Defender voor Eindpunt voor Linux in bedrijfsomgevingen.</span><span class="sxs-lookup"><span data-stu-id="c88f3-110">This topic contains instructions for how to set preferences for Defender for Endpoint for Linux in enterprise environments.</span></span> <span data-ttu-id="c88f3-111">Zie Resources als u geïnteresseerd bent in het configureren [](linux-resources.md#configure-from-the-command-line)van het product op een apparaat vanaf de opdrachtregel.</span><span class="sxs-lookup"><span data-stu-id="c88f3-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="c88f3-112">In bedrijfsomgevingen kan Defender voor Endpoint voor Linux worden beheerd via een configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="c88f3-112">In enterprise environments, Defender for Endpoint for Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="c88f3-113">Dit profiel wordt geïmplementeerd vanuit het beheerprogramma van uw keuze.</span><span class="sxs-lookup"><span data-stu-id="c88f3-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="c88f3-114">Voorkeuren die door de onderneming worden beheerd, hebben voorrang op de voorkeuren die lokaal op het apparaat zijn ingesteld.</span><span class="sxs-lookup"><span data-stu-id="c88f3-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="c88f3-115">Met andere woorden: gebruikers in uw bedrijf kunnen geen voorkeuren wijzigen die zijn ingesteld via dit configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="c88f3-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="c88f3-116">In dit artikel wordt de structuur van dit profiel beschreven (inclusief een aanbevolen profiel dat u kunt gebruiken om aan de slag te gaan) en instructies voor het implementeren van het profiel.</span><span class="sxs-lookup"><span data-stu-id="c88f3-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="c88f3-117">Configuratieprofielstructuur</span><span class="sxs-lookup"><span data-stu-id="c88f3-117">Configuration profile structure</span></span>

<span data-ttu-id="c88f3-118">Het configuratieprofiel is een JSON-bestand dat bestaat uit items die zijn geïdentificeerd met een sleutel (die de naam van de voorkeur aan duidt), gevolgd door een waarde, die afhankelijk is van de aard van de voorkeur.</span><span class="sxs-lookup"><span data-stu-id="c88f3-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="c88f3-119">Waarden kunnen eenvoudig zijn, zoals een numerieke waarde of complex, zoals een geneste lijst met voorkeuren.</span><span class="sxs-lookup"><span data-stu-id="c88f3-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="c88f3-120">Meestal gebruikt u een configuratiebeheerprogramma om een bestand met de naam op de ```mdatp_managed.json``` locatie te ```/etc/opt/microsoft/mdatp/managed/``` pushen.</span><span class="sxs-lookup"><span data-stu-id="c88f3-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="c88f3-121">Het bovenste niveau van het configuratieprofiel bevat productvoorkeuren en vermeldingen voor subareas van het product, die in de volgende secties in meer detail worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="c88f3-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="c88f3-122">Voorkeuren voor antivirusprogramma's</span><span class="sxs-lookup"><span data-stu-id="c88f3-122">Antivirus engine preferences</span></span>

<span data-ttu-id="c88f3-123">De *antivirusEngine-sectie* van het configuratieprofiel wordt gebruikt om de voorkeuren van het antivirusonderdeel van het product te beheren.</span><span class="sxs-lookup"><span data-stu-id="c88f3-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-124">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-124">**Key**</span></span> | <span data-ttu-id="c88f3-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="c88f3-125">antivirusEngine</span></span> |
| <span data-ttu-id="c88f3-126">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-126">**Data type**</span></span> | <span data-ttu-id="c88f3-127">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="c88f3-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c88f3-128">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-128">**Comments**</span></span> | <span data-ttu-id="c88f3-129">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="c88f3-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="c88f3-130">Realtime beveiliging in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="c88f3-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="c88f3-131">Hiermee bepaalt u of realtimebeveiliging (bestanden scannen terwijl ze worden toegankelijk) is ingeschakeld of niet.</span><span class="sxs-lookup"><span data-stu-id="c88f3-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-132">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-132">**Key**</span></span> | <span data-ttu-id="c88f3-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="c88f3-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="c88f3-134">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-134">**Data type**</span></span> | <span data-ttu-id="c88f3-135">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="c88f3-135">Boolean</span></span> |
| <span data-ttu-id="c88f3-136">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-136">**Possible values**</span></span> | <span data-ttu-id="c88f3-137">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="c88f3-137">true (default)</span></span> <br/> <span data-ttu-id="c88f3-138">onwaar</span><span class="sxs-lookup"><span data-stu-id="c88f3-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="c88f3-139">Passieve modus in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="c88f3-139">Enable / disable passive mode</span></span>

<span data-ttu-id="c88f3-140">Hiermee bepaalt u of de antivirusprogramma's al dan niet in de passieve modus worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c88f3-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="c88f3-141">In de passieve modus:</span><span class="sxs-lookup"><span data-stu-id="c88f3-141">In passive mode:</span></span>
- <span data-ttu-id="c88f3-142">Realtimebeveiliging is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c88f3-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="c88f3-143">Scannen op aanvraag is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c88f3-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="c88f3-144">Automatische herstel van bedreigingen is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c88f3-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="c88f3-145">Beveiligingsinformatie-updates zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c88f3-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="c88f3-146">Pictogram statusmenu is verborgen.</span><span class="sxs-lookup"><span data-stu-id="c88f3-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-147">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-147">**Key**</span></span> | <span data-ttu-id="c88f3-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="c88f3-148">passiveMode</span></span> |
| <span data-ttu-id="c88f3-149">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-149">**Data type**</span></span> | <span data-ttu-id="c88f3-150">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="c88f3-150">Boolean</span></span> |
| <span data-ttu-id="c88f3-151">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-151">**Possible values**</span></span> | <span data-ttu-id="c88f3-152">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="c88f3-152">false (default)</span></span> <br/> <span data-ttu-id="c88f3-153">waar</span><span class="sxs-lookup"><span data-stu-id="c88f3-153">true</span></span> |
| <span data-ttu-id="c88f3-154">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-154">**Comments**</span></span> | <span data-ttu-id="c88f3-155">Beschikbaar in Defender voor Eindpunt versie 100.67.60 of hoger.</span><span class="sxs-lookup"><span data-stu-id="c88f3-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="c88f3-156">Beleid voor samenvoeging van uitsluiting</span><span class="sxs-lookup"><span data-stu-id="c88f3-156">Exclusion merge policy</span></span>

<span data-ttu-id="c88f3-157">Hiermee geeft u het samenvoegbeleid voor uitsluitingen op.</span><span class="sxs-lookup"><span data-stu-id="c88f3-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="c88f3-158">Het kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde uitsluitingen ( ) of alleen `merge` door beheerders gedefinieerde uitsluitingen ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="c88f3-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="c88f3-159">Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen uitsluitingen definiëren.</span><span class="sxs-lookup"><span data-stu-id="c88f3-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-160">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-160">**Key**</span></span> | <span data-ttu-id="c88f3-161">uitsluitingenMergePolicy</span><span class="sxs-lookup"><span data-stu-id="c88f3-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="c88f3-162">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-162">**Data type**</span></span> | <span data-ttu-id="c88f3-163">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-163">String</span></span> |
| <span data-ttu-id="c88f3-164">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-164">**Possible values**</span></span> | <span data-ttu-id="c88f3-165">samenvoegen (standaard)</span><span class="sxs-lookup"><span data-stu-id="c88f3-165">merge (default)</span></span> <br/> <span data-ttu-id="c88f3-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="c88f3-166">admin_only</span></span> |
| <span data-ttu-id="c88f3-167">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-167">**Comments**</span></span> | <span data-ttu-id="c88f3-168">Beschikbaar in Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="c88f3-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="c88f3-169">Uitsluitingen scannen</span><span class="sxs-lookup"><span data-stu-id="c88f3-169">Scan exclusions</span></span>

<span data-ttu-id="c88f3-170">Entiteiten die zijn uitgesloten van de scan.</span><span class="sxs-lookup"><span data-stu-id="c88f3-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="c88f3-171">Uitsluitingen kunnen worden opgegeven door volledige paden, extensies of bestandsnamen.</span><span class="sxs-lookup"><span data-stu-id="c88f3-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-172">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-172">**Key**</span></span> | <span data-ttu-id="c88f3-173">uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="c88f3-173">exclusions</span></span> |
| <span data-ttu-id="c88f3-174">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-174">**Data type**</span></span> | <span data-ttu-id="c88f3-175">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="c88f3-175">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c88f3-176">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-176">**Comments**</span></span> | <span data-ttu-id="c88f3-177">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="c88f3-177">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="c88f3-178">**Type uitsluiting**</span><span class="sxs-lookup"><span data-stu-id="c88f3-178">**Type of exclusion**</span></span>

<span data-ttu-id="c88f3-179">Hiermee geeft u het type inhoud op dat is uitgesloten van de scan.</span><span class="sxs-lookup"><span data-stu-id="c88f3-179">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-180">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-180">**Key**</span></span> | <span data-ttu-id="c88f3-181">$type</span><span class="sxs-lookup"><span data-stu-id="c88f3-181">$type</span></span> |
| <span data-ttu-id="c88f3-182">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-182">**Data type**</span></span> | <span data-ttu-id="c88f3-183">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-183">String</span></span> |
| <span data-ttu-id="c88f3-184">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-184">**Possible values**</span></span> | <span data-ttu-id="c88f3-185">excludedPath</span><span class="sxs-lookup"><span data-stu-id="c88f3-185">excludedPath</span></span> <br/> <span data-ttu-id="c88f3-186">uitgeslotenFileExtension</span><span class="sxs-lookup"><span data-stu-id="c88f3-186">excludedFileExtension</span></span> <br/> <span data-ttu-id="c88f3-187">uitgeslotenFileName</span><span class="sxs-lookup"><span data-stu-id="c88f3-187">excludedFileName</span></span> |
|||

<span data-ttu-id="c88f3-188">**Pad naar uitgesloten inhoud**</span><span class="sxs-lookup"><span data-stu-id="c88f3-188">**Path to excluded content**</span></span>

<span data-ttu-id="c88f3-189">Wordt gebruikt om inhoud op volledig bestandspad uit te sluiten van de scan.</span><span class="sxs-lookup"><span data-stu-id="c88f3-189">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-190">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-190">**Key**</span></span> | <span data-ttu-id="c88f3-191">pad</span><span class="sxs-lookup"><span data-stu-id="c88f3-191">path</span></span> |
| <span data-ttu-id="c88f3-192">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-192">**Data type**</span></span> | <span data-ttu-id="c88f3-193">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-193">String</span></span> |
| <span data-ttu-id="c88f3-194">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-194">**Possible values**</span></span> | <span data-ttu-id="c88f3-195">geldige paden</span><span class="sxs-lookup"><span data-stu-id="c88f3-195">valid paths</span></span> |
| <span data-ttu-id="c88f3-196">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-196">**Comments**</span></span> | <span data-ttu-id="c88f3-197">Alleen van toepassing *als $type* *is uitgeslotenPath*</span><span class="sxs-lookup"><span data-stu-id="c88f3-197">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="c88f3-198">**Padtype (bestand /adreslijst)**</span><span class="sxs-lookup"><span data-stu-id="c88f3-198">**Path type (file / directory)**</span></span>

<span data-ttu-id="c88f3-199">Hiermee wordt aangegeven of *de eigenschap pad* verwijst naar een bestand of adreslijst.</span><span class="sxs-lookup"><span data-stu-id="c88f3-199">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="c88f3-200">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-200">**Key**</span></span> | <span data-ttu-id="c88f3-201">isDirectory</span><span class="sxs-lookup"><span data-stu-id="c88f3-201">isDirectory</span></span> |
| <span data-ttu-id="c88f3-202">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-202">**Data type**</span></span> | <span data-ttu-id="c88f3-203">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="c88f3-203">Boolean</span></span> |
| <span data-ttu-id="c88f3-204">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-204">**Possible values**</span></span> | <span data-ttu-id="c88f3-205">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="c88f3-205">false (default)</span></span> <br/> <span data-ttu-id="c88f3-206">waar</span><span class="sxs-lookup"><span data-stu-id="c88f3-206">true</span></span> |
| <span data-ttu-id="c88f3-207">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-207">**Comments**</span></span> | <span data-ttu-id="c88f3-208">Alleen van toepassing *als $type* *is uitgeslotenPath*</span><span class="sxs-lookup"><span data-stu-id="c88f3-208">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="c88f3-209">**Bestandsextensie uitgesloten van de scan**</span><span class="sxs-lookup"><span data-stu-id="c88f3-209">**File extension excluded from the scan**</span></span>

<span data-ttu-id="c88f3-210">Wordt gebruikt om inhoud uit te sluiten van de scan via bestandsextensie.</span><span class="sxs-lookup"><span data-stu-id="c88f3-210">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-211">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-211">**Key**</span></span> | <span data-ttu-id="c88f3-212">extensie</span><span class="sxs-lookup"><span data-stu-id="c88f3-212">extension</span></span> |
| <span data-ttu-id="c88f3-213">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-213">**Data type**</span></span> | <span data-ttu-id="c88f3-214">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-214">String</span></span> |
| <span data-ttu-id="c88f3-215">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-215">**Possible values**</span></span> | <span data-ttu-id="c88f3-216">geldige bestandsextensies</span><span class="sxs-lookup"><span data-stu-id="c88f3-216">valid file extensions</span></span> |
| <span data-ttu-id="c88f3-217">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-217">**Comments**</span></span> | <span data-ttu-id="c88f3-218">Alleen van toepassing *als $type* *is uitgeslotenFileExtension*</span><span class="sxs-lookup"><span data-stu-id="c88f3-218">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="c88f3-219">**Proces uitgesloten van de scan**</span><span class="sxs-lookup"><span data-stu-id="c88f3-219">**Process excluded from the scan**</span></span>

<span data-ttu-id="c88f3-220">Hiermee geeft u een proces op waarvoor alle bestandsactiviteit niet kan worden gescand.</span><span class="sxs-lookup"><span data-stu-id="c88f3-220">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="c88f3-221">Het proces kan worden opgegeven door de naam (bijvoorbeeld) of het volledige `cat` pad `/bin/cat` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="c88f3-221">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-222">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-222">**Key**</span></span> | <span data-ttu-id="c88f3-223">naam</span><span class="sxs-lookup"><span data-stu-id="c88f3-223">name</span></span> |
| <span data-ttu-id="c88f3-224">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-224">**Data type**</span></span> | <span data-ttu-id="c88f3-225">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-225">String</span></span> |
| <span data-ttu-id="c88f3-226">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-226">**Possible values**</span></span> | <span data-ttu-id="c88f3-227">een tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-227">any string</span></span> |
| <span data-ttu-id="c88f3-228">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-228">**Comments**</span></span> | <span data-ttu-id="c88f3-229">Alleen van toepassing *als $type* *is uitgeslotenFileName*</span><span class="sxs-lookup"><span data-stu-id="c88f3-229">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="c88f3-230">Toegestane bedreigingen</span><span class="sxs-lookup"><span data-stu-id="c88f3-230">Allowed threats</span></span>

<span data-ttu-id="c88f3-231">Lijst met bedreigingen (geïdentificeerd met hun naam) die niet worden geblokkeerd door het product en die in plaats daarvan mogen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c88f3-231">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-232">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-232">**Key**</span></span> | <span data-ttu-id="c88f3-233">toegestaanThreats</span><span class="sxs-lookup"><span data-stu-id="c88f3-233">allowedThreats</span></span> |
| <span data-ttu-id="c88f3-234">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-234">**Data type**</span></span> | <span data-ttu-id="c88f3-235">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="c88f3-235">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="c88f3-236">Niet-toegestaan bedreigingsacties</span><span class="sxs-lookup"><span data-stu-id="c88f3-236">Disallowed threat actions</span></span>

<span data-ttu-id="c88f3-237">Hiermee beperkt u de acties die de lokale gebruiker van een apparaat kan uitvoeren wanneer bedreigingen worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="c88f3-237">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="c88f3-238">De acties in deze lijst worden niet weergegeven in de gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="c88f3-238">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-239">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-239">**Key**</span></span> | <span data-ttu-id="c88f3-240">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="c88f3-240">disallowedThreatActions</span></span> |
| <span data-ttu-id="c88f3-241">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-241">**Data type**</span></span> | <span data-ttu-id="c88f3-242">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="c88f3-242">Array of strings</span></span> |
| <span data-ttu-id="c88f3-243">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-243">**Possible values**</span></span> | <span data-ttu-id="c88f3-244">toestaan (gebruikers kunnen geen bedreigingen toestaan)</span><span class="sxs-lookup"><span data-stu-id="c88f3-244">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="c88f3-245">herstellen (gebruikers kunnen geen bedreigingen herstellen vanuit de quarantaine)</span><span class="sxs-lookup"><span data-stu-id="c88f3-245">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="c88f3-246">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-246">**Comments**</span></span> | <span data-ttu-id="c88f3-247">Beschikbaar in Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="c88f3-247">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="c88f3-248">Instellingen voor bedreigingstype</span><span class="sxs-lookup"><span data-stu-id="c88f3-248">Threat type settings</span></span>

<span data-ttu-id="c88f3-249">De *threatTypeSettings-voorkeur* in de antivirus-engine wordt gebruikt om te bepalen hoe bepaalde bedreigingstypen door het product worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="c88f3-249">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-250">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-250">**Key**</span></span> | <span data-ttu-id="c88f3-251">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="c88f3-251">threatTypeSettings</span></span> |
| <span data-ttu-id="c88f3-252">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-252">**Data type**</span></span> | <span data-ttu-id="c88f3-253">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="c88f3-253">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c88f3-254">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-254">**Comments**</span></span> | <span data-ttu-id="c88f3-255">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="c88f3-255">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="c88f3-256">**Type bedreiging**</span><span class="sxs-lookup"><span data-stu-id="c88f3-256">**Threat type**</span></span>

<span data-ttu-id="c88f3-257">Type bedreiging waarvoor het gedrag is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="c88f3-257">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-258">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-258">**Key**</span></span> | <span data-ttu-id="c88f3-259">toets</span><span class="sxs-lookup"><span data-stu-id="c88f3-259">key</span></span> |
| <span data-ttu-id="c88f3-260">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-260">**Data type**</span></span> | <span data-ttu-id="c88f3-261">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-261">String</span></span> |
| <span data-ttu-id="c88f3-262">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-262">**Possible values**</span></span> | <span data-ttu-id="c88f3-263">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="c88f3-263">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="c88f3-264">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="c88f3-264">archive_bomb</span></span> |
|||

<span data-ttu-id="c88f3-265">**Actie ondernemen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-265">**Action to take**</span></span>

<span data-ttu-id="c88f3-266">Actie die moet worden ondernomen wanneer u een bedreiging tegenkomt van het type dat is opgegeven in de vorige sectie.</span><span class="sxs-lookup"><span data-stu-id="c88f3-266">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="c88f3-267">Kan het volgende zijn:</span><span class="sxs-lookup"><span data-stu-id="c88f3-267">Can be:</span></span>

- <span data-ttu-id="c88f3-268">**Controle:** Het apparaat is niet beveiligd tegen dit type bedreiging, maar er wordt wel een vermelding over de bedreiging geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="c88f3-268">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="c88f3-269">**Blokkeren:** Het apparaat is beveiligd tegen dit type bedreiging en u wordt op de hoogte gesteld in de beveiligingsconsole.</span><span class="sxs-lookup"><span data-stu-id="c88f3-269">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="c88f3-270">**Uit:** Het apparaat is niet beveiligd tegen dit type bedreiging en er wordt niets geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="c88f3-270">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-271">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-271">**Key**</span></span> | <span data-ttu-id="c88f3-272">waarde</span><span class="sxs-lookup"><span data-stu-id="c88f3-272">value</span></span> |
| <span data-ttu-id="c88f3-273">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-273">**Data type**</span></span> | <span data-ttu-id="c88f3-274">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-274">String</span></span> |
| <span data-ttu-id="c88f3-275">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-275">**Possible values**</span></span> | <span data-ttu-id="c88f3-276">audit (standaard)</span><span class="sxs-lookup"><span data-stu-id="c88f3-276">audit (default)</span></span> <br/> <span data-ttu-id="c88f3-277">blokkering</span><span class="sxs-lookup"><span data-stu-id="c88f3-277">block</span></span> <br/> <span data-ttu-id="c88f3-278">uit</span><span class="sxs-lookup"><span data-stu-id="c88f3-278">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="c88f3-279">Samenvoegbeleid voor instellingen voor bedreigingstype</span><span class="sxs-lookup"><span data-stu-id="c88f3-279">Threat type settings merge policy</span></span>

<span data-ttu-id="c88f3-280">Hiermee geeft u het samenvoegbeleid voor instellingen voor bedreigingstype op.</span><span class="sxs-lookup"><span data-stu-id="c88f3-280">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="c88f3-281">Dit kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde instellingen ( `merge` ) of alleen door beheerders gedefinieerde instellingen ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="c88f3-281">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="c88f3-282">Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen instellingen voor verschillende bedreigingstypen definiëren.</span><span class="sxs-lookup"><span data-stu-id="c88f3-282">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-283">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-283">**Key**</span></span> | <span data-ttu-id="c88f3-284">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="c88f3-284">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="c88f3-285">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-285">**Data type**</span></span> | <span data-ttu-id="c88f3-286">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-286">String</span></span> |
| <span data-ttu-id="c88f3-287">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-287">**Possible values**</span></span> | <span data-ttu-id="c88f3-288">samenvoegen (standaard)</span><span class="sxs-lookup"><span data-stu-id="c88f3-288">merge (default)</span></span> <br/> <span data-ttu-id="c88f3-289">admin_only</span><span class="sxs-lookup"><span data-stu-id="c88f3-289">admin_only</span></span> |
| <span data-ttu-id="c88f3-290">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-290">**Comments**</span></span> | <span data-ttu-id="c88f3-291">Beschikbaar in Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="c88f3-291">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="c88f3-292">Bewaargeschiedenis van antivirusscans (in dagen)</span><span class="sxs-lookup"><span data-stu-id="c88f3-292">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="c88f3-293">Geef het aantal dagen op dat de resultaten worden bewaard in de scangeschiedenis op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="c88f3-293">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="c88f3-294">Oude scanresultaten worden uit de geschiedenis verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c88f3-294">Old scan results are removed from the history.</span></span> <span data-ttu-id="c88f3-295">Oude in quarantaine geplaatste bestanden die ook van de schijf zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c88f3-295">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-296">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-296">**Key**</span></span> | <span data-ttu-id="c88f3-297">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="c88f3-297">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="c88f3-298">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-298">**Data type**</span></span> | <span data-ttu-id="c88f3-299">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-299">String</span></span> |
| <span data-ttu-id="c88f3-300">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-300">**Possible values**</span></span> | <span data-ttu-id="c88f3-301">90 (standaard).</span><span class="sxs-lookup"><span data-stu-id="c88f3-301">90 (default).</span></span> <span data-ttu-id="c88f3-302">Toegestane waarden zijn 1 dag tot 180 dagen.</span><span class="sxs-lookup"><span data-stu-id="c88f3-302">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="c88f3-303">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-303">**Comments**</span></span> | <span data-ttu-id="c88f3-304">Beschikbaar in Defender voor Eindpunt versie 101.04.76 of hoger.</span><span class="sxs-lookup"><span data-stu-id="c88f3-304">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="c88f3-305">Maximum aantal items in de geschiedenis van de antivirusscan</span><span class="sxs-lookup"><span data-stu-id="c88f3-305">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="c88f3-306">Geef het maximum aantal items op dat u wilt behouden in de scangeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="c88f3-306">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="c88f3-307">Items zijn alle scans op aanvraag die in het verleden zijn uitgevoerd en alle antivirusdetecties.</span><span class="sxs-lookup"><span data-stu-id="c88f3-307">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-308">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-308">**Key**</span></span> | <span data-ttu-id="c88f3-309">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="c88f3-309">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="c88f3-310">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-310">**Data type**</span></span> | <span data-ttu-id="c88f3-311">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-311">String</span></span> |
| <span data-ttu-id="c88f3-312">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-312">**Possible values**</span></span> | <span data-ttu-id="c88f3-313">10000 (standaard).</span><span class="sxs-lookup"><span data-stu-id="c88f3-313">10000 (default).</span></span> <span data-ttu-id="c88f3-314">Toegestane waarden zijn van 5000 items tot 15000 items.</span><span class="sxs-lookup"><span data-stu-id="c88f3-314">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="c88f3-315">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-315">**Comments**</span></span> | <span data-ttu-id="c88f3-316">Beschikbaar in Defender voor Eindpunt versie 101.04.76 of hoger.</span><span class="sxs-lookup"><span data-stu-id="c88f3-316">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="c88f3-317">Beveiligingsvoorkeuren in de cloud</span><span class="sxs-lookup"><span data-stu-id="c88f3-317">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="c88f3-318">De *cloudService-vermelding* in het configuratieprofiel wordt gebruikt om de cloudbeveiligingsfunctie van het product te configureren.</span><span class="sxs-lookup"><span data-stu-id="c88f3-318">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-319">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-319">**Key**</span></span> | <span data-ttu-id="c88f3-320">cloudService</span><span class="sxs-lookup"><span data-stu-id="c88f3-320">cloudService</span></span> |
| <span data-ttu-id="c88f3-321">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-321">**Data type**</span></span> | <span data-ttu-id="c88f3-322">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="c88f3-322">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c88f3-323">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="c88f3-323">**Comments**</span></span> | <span data-ttu-id="c88f3-324">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="c88f3-324">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="c88f3-325">Beveiliging via de cloud in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="c88f3-325">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="c88f3-326">Hiermee bepaalt u of beveiliging in de cloud is ingeschakeld op het apparaat of niet.</span><span class="sxs-lookup"><span data-stu-id="c88f3-326">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="c88f3-327">Als u de beveiliging van uw services wilt verbeteren, raden we u aan deze functie ingeschakeld te houden.</span><span class="sxs-lookup"><span data-stu-id="c88f3-327">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-328">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-328">**Key**</span></span> | <span data-ttu-id="c88f3-329">ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="c88f3-329">enabled</span></span> |
| <span data-ttu-id="c88f3-330">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-330">**Data type**</span></span> | <span data-ttu-id="c88f3-331">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="c88f3-331">Boolean</span></span> |
| <span data-ttu-id="c88f3-332">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-332">**Possible values**</span></span> | <span data-ttu-id="c88f3-333">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="c88f3-333">true (default)</span></span> <br/> <span data-ttu-id="c88f3-334">onwaar</span><span class="sxs-lookup"><span data-stu-id="c88f3-334">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="c88f3-335">Diagnostisch verzamelingsniveau</span><span class="sxs-lookup"><span data-stu-id="c88f3-335">Diagnostic collection level</span></span>

<span data-ttu-id="c88f3-336">Diagnostische gegevens worden gebruikt om Defender voor Eindpunt veilig en up-to-date te houden, problemen op te sporen, te diagnosticeren en op te lossen, en om productverbeteringen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="c88f3-336">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="c88f3-337">Deze instelling bepaalt het niveau van de diagnostische gegevens die door het product naar Microsoft worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="c88f3-337">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-338">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-338">**Key**</span></span> | <span data-ttu-id="c88f3-339">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="c88f3-339">diagnosticLevel</span></span> |
| <span data-ttu-id="c88f3-340">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-340">**Data type**</span></span> | <span data-ttu-id="c88f3-341">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-341">String</span></span> |
| <span data-ttu-id="c88f3-342">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-342">**Possible values**</span></span> | <span data-ttu-id="c88f3-343">optioneel (standaard)</span><span class="sxs-lookup"><span data-stu-id="c88f3-343">optional (default)</span></span> <br/> <span data-ttu-id="c88f3-344">Vereist</span><span class="sxs-lookup"><span data-stu-id="c88f3-344">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="c88f3-345">Automatische voorbeeldinzendingen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="c88f3-345">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="c88f3-346">Hiermee wordt bepaald of verdachte steekproeven (die waarschijnlijk bedreigingen bevatten) naar Microsoft worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="c88f3-346">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="c88f3-347">Er zijn drie niveaus voor het beheren van voorbeeldinzending:</span><span class="sxs-lookup"><span data-stu-id="c88f3-347">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="c88f3-348">**Geen:** er worden geen verdachte steekproeven ingediend bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c88f3-348">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="c88f3-349">**Veilig:** alleen verdachte steekproeven die geen persoonlijk identificeerbare gegevens (PII) bevatten, worden automatisch verzonden.</span><span class="sxs-lookup"><span data-stu-id="c88f3-349">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="c88f3-350">Dit is de standaardwaarde voor deze instelling.</span><span class="sxs-lookup"><span data-stu-id="c88f3-350">This is the default value for this setting.</span></span>
- <span data-ttu-id="c88f3-351">**Alle**: alle verdachte steekproeven worden verzonden naar Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c88f3-351">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-352">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-352">**Key**</span></span> | <span data-ttu-id="c88f3-353">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="c88f3-353">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="c88f3-354">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-354">**Data type**</span></span> | <span data-ttu-id="c88f3-355">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c88f3-355">String</span></span> |
| <span data-ttu-id="c88f3-356">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-356">**Possible values**</span></span> | <span data-ttu-id="c88f3-357">geen</span><span class="sxs-lookup"><span data-stu-id="c88f3-357">none</span></span> <br/> <span data-ttu-id="c88f3-358">veilig (standaard)</span><span class="sxs-lookup"><span data-stu-id="c88f3-358">safe (default)</span></span> <br/> <span data-ttu-id="c88f3-359">alles</span><span class="sxs-lookup"><span data-stu-id="c88f3-359">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="c88f3-360">Automatische beveiligingsinformatie-updates in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="c88f3-360">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="c88f3-361">Hiermee bepaalt u of beveiligingsinformatieupdates automatisch worden geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="c88f3-361">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="c88f3-362">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="c88f3-362">**Key**</span></span> | <span data-ttu-id="c88f3-363">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="c88f3-363">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="c88f3-364">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="c88f3-364">**Data type**</span></span> | <span data-ttu-id="c88f3-365">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="c88f3-365">Boolean</span></span> |
| <span data-ttu-id="c88f3-366">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="c88f3-366">**Possible values**</span></span> | <span data-ttu-id="c88f3-367">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="c88f3-367">true (default)</span></span> <br/> <span data-ttu-id="c88f3-368">onwaar</span><span class="sxs-lookup"><span data-stu-id="c88f3-368">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="c88f3-369">Aanbevolen configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="c88f3-369">Recommended configuration profile</span></span>

<span data-ttu-id="c88f3-370">Om aan de slag te gaan, raden we u aan het volgende configuratieprofiel voor uw bedrijf te gebruiken om te profiteren van alle beveiligingsfuncties die Defender voor Eindpunt biedt.</span><span class="sxs-lookup"><span data-stu-id="c88f3-370">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="c88f3-371">Het volgende configuratieprofiel is:</span><span class="sxs-lookup"><span data-stu-id="c88f3-371">The following configuration profile will:</span></span>

- <span data-ttu-id="c88f3-372">Realtimebeveiliging inschakelen (RTP)</span><span class="sxs-lookup"><span data-stu-id="c88f3-372">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="c88f3-373">Geef op hoe de volgende bedreigingstypen worden verwerkt:</span><span class="sxs-lookup"><span data-stu-id="c88f3-373">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="c88f3-374">**Potentieel ongewenste toepassingen (PUA)** worden geblokkeerd</span><span class="sxs-lookup"><span data-stu-id="c88f3-374">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="c88f3-375">**Archiefbommen** (bestand met een hoge compressiesnelheid) worden gecontroleerd op de productlogboeken</span><span class="sxs-lookup"><span data-stu-id="c88f3-375">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="c88f3-376">Automatische beveiligingsinformatie-updates inschakelen</span><span class="sxs-lookup"><span data-stu-id="c88f3-376">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="c88f3-377">Beveiliging via de cloud inschakelen</span><span class="sxs-lookup"><span data-stu-id="c88f3-377">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="c88f3-378">Automatische voorbeeldinzending op niveau `safe` inschakelen</span><span class="sxs-lookup"><span data-stu-id="c88f3-378">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="c88f3-379">Voorbeeldprofiel</span><span class="sxs-lookup"><span data-stu-id="c88f3-379">Sample profile</span></span>

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
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="c88f3-380">Voorbeeld van volledig configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="c88f3-380">Full configuration profile example</span></span>

<span data-ttu-id="c88f3-381">Het volgende configuratieprofiel bevat vermeldingen voor alle instellingen die in dit document worden beschreven en kunnen worden gebruikt voor meer geavanceerde scenario's waarin u meer controle over het product wilt.</span><span class="sxs-lookup"><span data-stu-id="c88f3-381">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="c88f3-382">Volledig profiel</span><span class="sxs-lookup"><span data-stu-id="c88f3-382">Full profile</span></span>

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
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
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
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="c88f3-383">Configuratieprofielvalidatie</span><span class="sxs-lookup"><span data-stu-id="c88f3-383">Configuration profile validation</span></span>

<span data-ttu-id="c88f3-384">Het configuratieprofiel moet een geldig bestand met JSON-indeling zijn.</span><span class="sxs-lookup"><span data-stu-id="c88f3-384">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="c88f3-385">Er zijn een aantal hulpprogramma's die kunnen worden gebruikt om dit te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="c88f3-385">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="c88f3-386">Als u bijvoorbeeld op uw apparaat `python` hebt geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="c88f3-386">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="c88f3-387">Als de JSON goed is gevormd, wordt deze met de bovenstaande opdracht terug naar de Terminal uitgevoerd en wordt een exitcode van `0` .</span><span class="sxs-lookup"><span data-stu-id="c88f3-387">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="c88f3-388">Anders wordt een fout weergegeven die het probleem beschrijft en retourneert de opdracht een exitcode van `1` .</span><span class="sxs-lookup"><span data-stu-id="c88f3-388">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="c88f3-389">Controleren of de mdatp_managed.jsbestand werkt zoals verwacht</span><span class="sxs-lookup"><span data-stu-id="c88f3-389">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="c88f3-390">Als u wilt controleren of uw /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsop naar behoren werkt, ziet u '[beheerd]' naast deze instellingen:</span><span class="sxs-lookup"><span data-stu-id="c88f3-390">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="c88f3-391">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="c88f3-391">cloud_enabled</span></span>
- <span data-ttu-id="c88f3-392">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="c88f3-392">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="c88f3-393">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="c88f3-393">passice_mode_enabled</span></span>
- <span data-ttu-id="c88f3-394">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="c88f3-394">real_time_protection_enabled</span></span>
- <span data-ttu-id="c88f3-395">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="c88f3-395">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="c88f3-396">Als de mdatp_managed.jsin werking treedt, is er geen herstart van de wdavdaemon vereist.</span><span class="sxs-lookup"><span data-stu-id="c88f3-396">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="c88f3-397">Implementatie van configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="c88f3-397">Configuration profile deployment</span></span>

<span data-ttu-id="c88f3-398">Nadat u het configuratieprofiel voor uw onderneming hebt gemaakt, kunt u het implementeren via het beheerprogramma dat uw bedrijf gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c88f3-398">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="c88f3-399">Defender voor Eindpunt voor Linux leest de beheerde configuratie uit het *bestand /etc/opt/microsoft/mdatp/managed/mdatp_managed.js.*</span><span class="sxs-lookup"><span data-stu-id="c88f3-399">Defender for Endpoint for Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
