---
title: Voorkeuren instellen voor Microsoft Defender ATP voor Mac
description: Microsoft Defender ATP voor Mac configureren in bedrijfsorganisaties.
keywords: microsoft, defender, atp, mac, management, voorkeuren, onderneming, intune, jamf, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 951c51c767ba09ebc6056481b4fac45da09c5671
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688547"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="06b65-104">Voorkeuren instellen voor Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="06b65-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="06b65-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="06b65-105">**Applies to:**</span></span>

- [<span data-ttu-id="06b65-106">Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="06b65-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="06b65-107">Dit artikel bevat instructies voor het instellen van voorkeuren voor Microsoft Defender voor Eindpunt voor macOS in bedrijfsorganisaties.</span><span class="sxs-lookup"><span data-stu-id="06b65-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="06b65-108">Zie Resources als u Microsoft Defender voor Eindpunt op [](mac-resources.md#configuring-from-the-command-line)macOS wilt configureren met behulp van de opdrachtregelinterface.</span><span class="sxs-lookup"><span data-stu-id="06b65-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="06b65-109">Samenvatting</span><span class="sxs-lookup"><span data-stu-id="06b65-109">Summary</span></span>

<span data-ttu-id="06b65-110">In ondernemingsorganisaties kan Microsoft Defender voor Eindpunt op macOS worden beheerd via een configuratieprofiel dat wordt geïmplementeerd met behulp van een van de verschillende beheerhulpmiddelen.</span><span class="sxs-lookup"><span data-stu-id="06b65-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="06b65-111">Voorkeuren die worden beheerd door uw beveiligingsbewerkingsteam, hebben voorrang op voorkeuren die lokaal op het apparaat zijn ingesteld.</span><span class="sxs-lookup"><span data-stu-id="06b65-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="06b65-112">Het wijzigen van de voorkeuren die zijn ingesteld via het configuratieprofiel vereist geëscaleerde bevoegdheden en is niet beschikbaar voor gebruikers zonder beheerdersmachtigingen.</span><span class="sxs-lookup"><span data-stu-id="06b65-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="06b65-113">In dit artikel wordt de structuur van het configuratieprofiel beschreven, wordt een aanbevolen profiel beschreven dat u kunt gebruiken om aan de slag te gaan en worden instructies gegeven over het implementeren van het profiel.</span><span class="sxs-lookup"><span data-stu-id="06b65-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="06b65-114">Configuratieprofielstructuur</span><span class="sxs-lookup"><span data-stu-id="06b65-114">Configuration profile structure</span></span>

<span data-ttu-id="06b65-115">Het configuratieprofiel is een *PLIST-bestand* dat bestaat uit items die zijn geïdentificeerd met een sleutel (die de naam van de voorkeur aan duidt), gevolgd door een waarde, die afhankelijk is van de aard van de voorkeur.</span><span class="sxs-lookup"><span data-stu-id="06b65-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="06b65-116">Waarden kunnen eenvoudig zijn (zoals een numerieke waarde) of complex, zoals een geneste lijst met voorkeuren.</span><span class="sxs-lookup"><span data-stu-id="06b65-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="06b65-117">De indeling van het configuratieprofiel is afhankelijk van de beheerconsole die u gebruikt.</span><span class="sxs-lookup"><span data-stu-id="06b65-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="06b65-118">De volgende secties bevatten voorbeelden van configuratieprofielen voor JAMF en Intune.</span><span class="sxs-lookup"><span data-stu-id="06b65-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="06b65-119">Het bovenste niveau van het configuratieprofiel bevat productvoorkeuren en vermeldingen voor subareas van Microsoft Defender voor Eindpunt, die in de volgende secties in meer detail worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="06b65-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="06b65-120">Voorkeuren voor antivirusprogramma's</span><span class="sxs-lookup"><span data-stu-id="06b65-120">Antivirus engine preferences</span></span>

<span data-ttu-id="06b65-121">De *antivirusEngine-sectie* van het configuratieprofiel wordt gebruikt om de voorkeuren van het antivirusonderdeel van Microsoft Defender voor Eindpunt te beheren.</span><span class="sxs-lookup"><span data-stu-id="06b65-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="06b65-122">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-122">Section</span></span>|<span data-ttu-id="06b65-123">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-124">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-125">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-125">**Key**</span></span> | <span data-ttu-id="06b65-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="06b65-126">antivirusEngine</span></span> |
| <span data-ttu-id="06b65-127">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-127">**Data type**</span></span> | <span data-ttu-id="06b65-128">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="06b65-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="06b65-129">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-129">**Comments**</span></span> | <span data-ttu-id="06b65-130">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="06b65-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="06b65-131">Realtime beveiliging in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="06b65-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="06b65-132">Geef op of u realtimebeveiliging wilt inschakelen, waarmee bestanden worden gescand wanneer ze worden toegankelijk.</span><span class="sxs-lookup"><span data-stu-id="06b65-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="06b65-133">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-133">Section</span></span>|<span data-ttu-id="06b65-134">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-135">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-136">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-136">**Key**</span></span> | <span data-ttu-id="06b65-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="06b65-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="06b65-138">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-138">**Data type**</span></span> | <span data-ttu-id="06b65-139">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-139">Boolean</span></span> |
| <span data-ttu-id="06b65-140">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-140">**Possible values**</span></span> | <span data-ttu-id="06b65-141">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="06b65-141">true (default)</span></span> <br/> <span data-ttu-id="06b65-142">onwaar</span><span class="sxs-lookup"><span data-stu-id="06b65-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="06b65-143">Passieve modus in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="06b65-143">Enable / disable passive mode</span></span>

<span data-ttu-id="06b65-144">Geef op of de antivirusprogramma's in de passieve modus worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="06b65-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="06b65-145">De passieve modus heeft de volgende gevolgen:</span><span class="sxs-lookup"><span data-stu-id="06b65-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="06b65-146">Realtimebeveiliging is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="06b65-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="06b65-147">Scannen op aanvraag is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="06b65-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="06b65-148">Automatische herstel van bedreigingen is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="06b65-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="06b65-149">Beveiligingsinformatie-updates zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="06b65-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="06b65-150">Pictogram statusmenu is verborgen</span><span class="sxs-lookup"><span data-stu-id="06b65-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="06b65-151">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-151">Section</span></span>|<span data-ttu-id="06b65-152">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-153">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-154">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-154">**Key**</span></span> | <span data-ttu-id="06b65-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="06b65-155">passiveMode</span></span> |
| <span data-ttu-id="06b65-156">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-156">**Data type**</span></span> | <span data-ttu-id="06b65-157">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-157">Boolean</span></span> |
| <span data-ttu-id="06b65-158">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-158">**Possible values**</span></span> | <span data-ttu-id="06b65-159">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="06b65-159">false (default)</span></span> <br/> <span data-ttu-id="06b65-160">waar</span><span class="sxs-lookup"><span data-stu-id="06b65-160">true</span></span> |
| <span data-ttu-id="06b65-161">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-161">**Comments**</span></span> | <span data-ttu-id="06b65-162">Beschikbaar in Microsoft Defender voor Eindpunt versie 100.67.60 of hoger.</span><span class="sxs-lookup"><span data-stu-id="06b65-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="06b65-163">Beleid voor samenvoeging van uitsluiting</span><span class="sxs-lookup"><span data-stu-id="06b65-163">Exclusion merge policy</span></span>

<span data-ttu-id="06b65-164">Geef het samenvoegbeleid op voor uitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="06b65-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="06b65-165">Dit kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde uitsluitingen ( ) of alleen `merge` door beheerders gedefinieerde uitsluitingen ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="06b65-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="06b65-166">Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen uitsluitingen definiëren.</span><span class="sxs-lookup"><span data-stu-id="06b65-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="06b65-167">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-167">Section</span></span>|<span data-ttu-id="06b65-168">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-169">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-170">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-170">**Key**</span></span> | <span data-ttu-id="06b65-171">uitsluitingenMergePolicy</span><span class="sxs-lookup"><span data-stu-id="06b65-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="06b65-172">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-172">**Data type**</span></span> | <span data-ttu-id="06b65-173">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-173">String</span></span> |
| <span data-ttu-id="06b65-174">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-174">**Possible values**</span></span> | <span data-ttu-id="06b65-175">samenvoegen (standaard)</span><span class="sxs-lookup"><span data-stu-id="06b65-175">merge (default)</span></span> <br/> <span data-ttu-id="06b65-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="06b65-176">admin_only</span></span> |
| <span data-ttu-id="06b65-177">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-177">**Comments**</span></span> | <span data-ttu-id="06b65-178">Beschikbaar in Microsoft Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="06b65-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="06b65-179">Uitsluitingen scannen</span><span class="sxs-lookup"><span data-stu-id="06b65-179">Scan exclusions</span></span>

<span data-ttu-id="06b65-180">Geef entiteiten op die niet mogen worden gescand.</span><span class="sxs-lookup"><span data-stu-id="06b65-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="06b65-181">Uitsluitingen kunnen worden opgegeven door volledige paden, extensies of bestandsnamen.</span><span class="sxs-lookup"><span data-stu-id="06b65-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="06b65-182">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-182">Section</span></span>|<span data-ttu-id="06b65-183">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-184">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-185">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-185">**Key**</span></span> | <span data-ttu-id="06b65-186">uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="06b65-186">exclusions</span></span> |
| <span data-ttu-id="06b65-187">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-187">**Data type**</span></span> | <span data-ttu-id="06b65-188">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="06b65-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="06b65-189">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-189">**Comments**</span></span> | <span data-ttu-id="06b65-190">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="06b65-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="06b65-191">Type uitsluiting</span><span class="sxs-lookup"><span data-stu-id="06b65-191">Type of exclusion</span></span>

<span data-ttu-id="06b65-192">Geef inhoud op die niet per type kan worden gescand.</span><span class="sxs-lookup"><span data-stu-id="06b65-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="06b65-193">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-193">Section</span></span>|<span data-ttu-id="06b65-194">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-195">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-196">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-196">**Key**</span></span> | <span data-ttu-id="06b65-197">$type</span><span class="sxs-lookup"><span data-stu-id="06b65-197">$type</span></span> |
| <span data-ttu-id="06b65-198">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-198">**Data type**</span></span> | <span data-ttu-id="06b65-199">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-199">String</span></span> |
| <span data-ttu-id="06b65-200">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-200">**Possible values**</span></span> | <span data-ttu-id="06b65-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="06b65-201">excludedPath</span></span> <br/> <span data-ttu-id="06b65-202">uitgeslotenFileExtension</span><span class="sxs-lookup"><span data-stu-id="06b65-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="06b65-203">uitgeslotenFileName</span><span class="sxs-lookup"><span data-stu-id="06b65-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="06b65-204">Pad naar uitgesloten inhoud</span><span class="sxs-lookup"><span data-stu-id="06b65-204">Path to excluded content</span></span>

<span data-ttu-id="06b65-205">Geef inhoud op die niet kan worden gescand via een volledig bestandspad.</span><span class="sxs-lookup"><span data-stu-id="06b65-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="06b65-206">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-206">Section</span></span>|<span data-ttu-id="06b65-207">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-208">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-209">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-209">**Key**</span></span> | <span data-ttu-id="06b65-210">pad</span><span class="sxs-lookup"><span data-stu-id="06b65-210">path</span></span> |
| <span data-ttu-id="06b65-211">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-211">**Data type**</span></span> | <span data-ttu-id="06b65-212">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-212">String</span></span> |
| <span data-ttu-id="06b65-213">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-213">**Possible values**</span></span> | <span data-ttu-id="06b65-214">geldige paden</span><span class="sxs-lookup"><span data-stu-id="06b65-214">valid paths</span></span> |
| <span data-ttu-id="06b65-215">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-215">**Comments**</span></span> | <span data-ttu-id="06b65-216">Alleen van toepassing *als $type* *is uitgeslotenPath*</span><span class="sxs-lookup"><span data-stu-id="06b65-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="06b65-217">Padtype (bestand /adreslijst)</span><span class="sxs-lookup"><span data-stu-id="06b65-217">Path type (file / directory)</span></span>

<span data-ttu-id="06b65-218">Geef aan of *de eigenschap pad* verwijst naar een bestand of adreslijst.</span><span class="sxs-lookup"><span data-stu-id="06b65-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="06b65-219">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-219">Section</span></span>|<span data-ttu-id="06b65-220">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-221">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-222">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-222">**Key**</span></span> | <span data-ttu-id="06b65-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="06b65-223">isDirectory</span></span> |
| <span data-ttu-id="06b65-224">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-224">**Data type**</span></span> | <span data-ttu-id="06b65-225">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-225">Boolean</span></span> |
| <span data-ttu-id="06b65-226">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-226">**Possible values**</span></span> | <span data-ttu-id="06b65-227">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="06b65-227">false (default)</span></span> <br/> <span data-ttu-id="06b65-228">waar</span><span class="sxs-lookup"><span data-stu-id="06b65-228">true</span></span> |
| <span data-ttu-id="06b65-229">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-229">**Comments**</span></span> | <span data-ttu-id="06b65-230">Alleen van toepassing *als $type* *is uitgeslotenPath*</span><span class="sxs-lookup"><span data-stu-id="06b65-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="06b65-231">Bestandsextensie uitgesloten van de scan</span><span class="sxs-lookup"><span data-stu-id="06b65-231">File extension excluded from the scan</span></span>

<span data-ttu-id="06b65-232">Geef inhoud op die niet kan worden gescand door bestandsextensie.</span><span class="sxs-lookup"><span data-stu-id="06b65-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="06b65-233">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-233">Section</span></span>|<span data-ttu-id="06b65-234">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-235">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-236">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-236">**Key**</span></span> | <span data-ttu-id="06b65-237">extensie</span><span class="sxs-lookup"><span data-stu-id="06b65-237">extension</span></span> |
| <span data-ttu-id="06b65-238">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-238">**Data type**</span></span> | <span data-ttu-id="06b65-239">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-239">String</span></span> |
| <span data-ttu-id="06b65-240">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-240">**Possible values**</span></span> | <span data-ttu-id="06b65-241">geldige bestandsextensies</span><span class="sxs-lookup"><span data-stu-id="06b65-241">valid file extensions</span></span> |
| <span data-ttu-id="06b65-242">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-242">**Comments**</span></span> | <span data-ttu-id="06b65-243">Alleen van toepassing *als $type* *is uitgeslotenFileExtension*</span><span class="sxs-lookup"><span data-stu-id="06b65-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="06b65-244">Proces uitgesloten van de scan</span><span class="sxs-lookup"><span data-stu-id="06b65-244">Process excluded from the scan</span></span>

<span data-ttu-id="06b65-245">Geef een proces op waarvoor alle bestandsactiviteit is uitgesloten van scannen.</span><span class="sxs-lookup"><span data-stu-id="06b65-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="06b65-246">Het proces kan worden opgegeven door de naam (bijvoorbeeld) of het volledige `cat` pad `/bin/cat` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="06b65-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="06b65-247">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-247">Section</span></span>|<span data-ttu-id="06b65-248">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-249">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-250">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-250">**Key**</span></span> | <span data-ttu-id="06b65-251">naam</span><span class="sxs-lookup"><span data-stu-id="06b65-251">name</span></span> |
| <span data-ttu-id="06b65-252">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-252">**Data type**</span></span> | <span data-ttu-id="06b65-253">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-253">String</span></span> |
| <span data-ttu-id="06b65-254">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-254">**Possible values**</span></span> | <span data-ttu-id="06b65-255">een tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-255">any string</span></span> |
| <span data-ttu-id="06b65-256">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-256">**Comments**</span></span> | <span data-ttu-id="06b65-257">Alleen van toepassing *als $type* *is uitgeslotenFileName*</span><span class="sxs-lookup"><span data-stu-id="06b65-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="06b65-258">Toegestane bedreigingen</span><span class="sxs-lookup"><span data-stu-id="06b65-258">Allowed threats</span></span>

<span data-ttu-id="06b65-259">Geef bedreigingen op op naam die niet worden geblokkeerd door Defender voor Eindpunt voor Mac.</span><span class="sxs-lookup"><span data-stu-id="06b65-259">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="06b65-260">Deze bedreigingen kunnen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="06b65-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="06b65-261">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-261">Section</span></span>|<span data-ttu-id="06b65-262">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-263">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-264">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-264">**Key**</span></span> | <span data-ttu-id="06b65-265">toegestaanThreats</span><span class="sxs-lookup"><span data-stu-id="06b65-265">allowedThreats</span></span> |
| <span data-ttu-id="06b65-266">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-266">**Data type**</span></span> | <span data-ttu-id="06b65-267">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="06b65-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="06b65-268">Niet-toegestaan bedreigingsacties</span><span class="sxs-lookup"><span data-stu-id="06b65-268">Disallowed threat actions</span></span>

<span data-ttu-id="06b65-269">Hiermee beperkt u de acties die de lokale gebruiker van een apparaat kan uitvoeren wanneer bedreigingen worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="06b65-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="06b65-270">De acties in deze lijst worden niet weergegeven in de gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="06b65-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="06b65-271">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-271">Section</span></span>|<span data-ttu-id="06b65-272">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-273">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-274">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-274">**Key**</span></span> | <span data-ttu-id="06b65-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="06b65-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="06b65-276">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-276">**Data type**</span></span> | <span data-ttu-id="06b65-277">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="06b65-277">Array of strings</span></span> |
| <span data-ttu-id="06b65-278">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-278">**Possible values**</span></span> | <span data-ttu-id="06b65-279">toestaan (gebruikers kunnen geen bedreigingen toestaan)</span><span class="sxs-lookup"><span data-stu-id="06b65-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="06b65-280">herstellen (gebruikers kunnen geen bedreigingen herstellen vanuit de quarantaine)</span><span class="sxs-lookup"><span data-stu-id="06b65-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="06b65-281">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-281">**Comments**</span></span> | <span data-ttu-id="06b65-282">Beschikbaar in Microsoft Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="06b65-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="06b65-283">Instellingen voor bedreigingstype</span><span class="sxs-lookup"><span data-stu-id="06b65-283">Threat type settings</span></span>

<span data-ttu-id="06b65-284">Geef op hoe bepaalde bedreigingstypen worden verwerkt door Microsoft Defender voor Eindpunt in macOS.</span><span class="sxs-lookup"><span data-stu-id="06b65-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="06b65-285">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-285">Section</span></span>|<span data-ttu-id="06b65-286">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-287">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-288">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-288">**Key**</span></span> | <span data-ttu-id="06b65-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="06b65-289">threatTypeSettings</span></span> |
| <span data-ttu-id="06b65-290">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-290">**Data type**</span></span> | <span data-ttu-id="06b65-291">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="06b65-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="06b65-292">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-292">**Comments**</span></span> | <span data-ttu-id="06b65-293">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="06b65-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="06b65-294">Type bedreiging</span><span class="sxs-lookup"><span data-stu-id="06b65-294">Threat type</span></span>

<span data-ttu-id="06b65-295">Geef bedreigingstypen op.</span><span class="sxs-lookup"><span data-stu-id="06b65-295">Specify threat types.</span></span>

|<span data-ttu-id="06b65-296">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-296">Section</span></span>|<span data-ttu-id="06b65-297">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-298">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-299">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-299">**Key**</span></span> | <span data-ttu-id="06b65-300">toets</span><span class="sxs-lookup"><span data-stu-id="06b65-300">key</span></span> |
| <span data-ttu-id="06b65-301">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-301">**Data type**</span></span> | <span data-ttu-id="06b65-302">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-302">String</span></span> |
| <span data-ttu-id="06b65-303">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-303">**Possible values**</span></span> | <span data-ttu-id="06b65-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="06b65-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="06b65-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="06b65-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="06b65-306">Actie ondernemen</span><span class="sxs-lookup"><span data-stu-id="06b65-306">Action to take</span></span>

<span data-ttu-id="06b65-307">Geef op welke actie moet worden ondernomen wanneer er een bedreiging wordt gedetecteerd van het type dat is opgegeven in de vorige sectie.</span><span class="sxs-lookup"><span data-stu-id="06b65-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="06b65-308">Kies uit de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="06b65-308">Choose from the following options:</span></span>

- <span data-ttu-id="06b65-309">**Audit:** uw apparaat is niet beveiligd tegen dit type bedreiging, maar er wordt wel een vermelding over de bedreiging geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="06b65-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="06b65-310">**Blokkeren:** uw apparaat is beveiligd tegen dit type bedreiging en u krijgt een melding in de gebruikersinterface en de beveiligingsconsole.</span><span class="sxs-lookup"><span data-stu-id="06b65-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="06b65-311">**Uit:** uw apparaat is niet beveiligd tegen dit type bedreiging en er wordt niets geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="06b65-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="06b65-312">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-312">Section</span></span>|<span data-ttu-id="06b65-313">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-314">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-315">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-315">**Key**</span></span> | <span data-ttu-id="06b65-316">waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-316">value</span></span> |
| <span data-ttu-id="06b65-317">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-317">**Data type**</span></span> | <span data-ttu-id="06b65-318">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-318">String</span></span> |
| <span data-ttu-id="06b65-319">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-319">**Possible values**</span></span> | <span data-ttu-id="06b65-320">audit (standaard)</span><span class="sxs-lookup"><span data-stu-id="06b65-320">audit (default)</span></span> <br/> <span data-ttu-id="06b65-321">blokkering</span><span class="sxs-lookup"><span data-stu-id="06b65-321">block</span></span> <br/> <span data-ttu-id="06b65-322">uit</span><span class="sxs-lookup"><span data-stu-id="06b65-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="06b65-323">Samenvoegbeleid voor instellingen voor bedreigingstype</span><span class="sxs-lookup"><span data-stu-id="06b65-323">Threat type settings merge policy</span></span>

<span data-ttu-id="06b65-324">Geef het samenvoegbeleid op voor instellingen voor bedreigingstype.</span><span class="sxs-lookup"><span data-stu-id="06b65-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="06b65-325">Dit kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde instellingen ( `merge` ) of alleen door beheerders gedefinieerde instellingen ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="06b65-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="06b65-326">Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen instellingen voor verschillende bedreigingstypen definiëren.</span><span class="sxs-lookup"><span data-stu-id="06b65-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="06b65-327">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-327">Section</span></span>|<span data-ttu-id="06b65-328">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-329">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-330">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-330">**Key**</span></span> | <span data-ttu-id="06b65-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="06b65-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="06b65-332">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-332">**Data type**</span></span> | <span data-ttu-id="06b65-333">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-333">String</span></span> |
| <span data-ttu-id="06b65-334">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-334">**Possible values**</span></span> | <span data-ttu-id="06b65-335">samenvoegen (standaard)</span><span class="sxs-lookup"><span data-stu-id="06b65-335">merge (default)</span></span> <br/> <span data-ttu-id="06b65-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="06b65-336">admin_only</span></span> |
| <span data-ttu-id="06b65-337">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-337">**Comments**</span></span> | <span data-ttu-id="06b65-338">Beschikbaar in Microsoft Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="06b65-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="06b65-339">Bewaargeschiedenis van antivirusscans (in dagen)</span><span class="sxs-lookup"><span data-stu-id="06b65-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="06b65-340">Geef het aantal dagen op dat de resultaten worden bewaard in de scangeschiedenis op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="06b65-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="06b65-341">Oude scanresultaten worden uit de geschiedenis verwijderd.</span><span class="sxs-lookup"><span data-stu-id="06b65-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="06b65-342">Oude in quarantaine geplaatste bestanden die ook van de schijf zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="06b65-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="06b65-343">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-343">Section</span></span>|<span data-ttu-id="06b65-344">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-345">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-346">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-346">**Key**</span></span> | <span data-ttu-id="06b65-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="06b65-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="06b65-348">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-348">**Data type**</span></span> | <span data-ttu-id="06b65-349">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-349">String</span></span> |
| <span data-ttu-id="06b65-350">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-350">**Possible values**</span></span> | <span data-ttu-id="06b65-351">90 (standaard).</span><span class="sxs-lookup"><span data-stu-id="06b65-351">90 (default).</span></span> <span data-ttu-id="06b65-352">Toegestane waarden zijn 1 dag tot 180 dagen.</span><span class="sxs-lookup"><span data-stu-id="06b65-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="06b65-353">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-353">**Comments**</span></span> | <span data-ttu-id="06b65-354">Beschikbaar in Microsoft Defender voor Eindpunt versie 101.07.23 of hoger.</span><span class="sxs-lookup"><span data-stu-id="06b65-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="06b65-355">Maximum aantal items in de geschiedenis van de antivirusscan</span><span class="sxs-lookup"><span data-stu-id="06b65-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="06b65-356">Geef het maximum aantal items op dat u wilt behouden in de scangeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="06b65-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="06b65-357">Items zijn alle scans op aanvraag die in het verleden zijn uitgevoerd en alle antivirusdetecties.</span><span class="sxs-lookup"><span data-stu-id="06b65-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="06b65-358">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-358">Section</span></span>|<span data-ttu-id="06b65-359">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-360">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-361">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-361">**Key**</span></span> | <span data-ttu-id="06b65-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="06b65-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="06b65-363">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-363">**Data type**</span></span> | <span data-ttu-id="06b65-364">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-364">String</span></span> |
| <span data-ttu-id="06b65-365">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-365">**Possible values**</span></span> | <span data-ttu-id="06b65-366">10000 (standaard).</span><span class="sxs-lookup"><span data-stu-id="06b65-366">10000 (default).</span></span> <span data-ttu-id="06b65-367">Toegestane waarden zijn van 5000 items tot 15000 items.</span><span class="sxs-lookup"><span data-stu-id="06b65-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="06b65-368">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-368">**Comments**</span></span> | <span data-ttu-id="06b65-369">Beschikbaar in Microsoft Defender voor Eindpunt versie 101.07.23 of hoger.</span><span class="sxs-lookup"><span data-stu-id="06b65-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="06b65-370">Beveiligingsvoorkeuren in de cloud</span><span class="sxs-lookup"><span data-stu-id="06b65-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="06b65-371">Configureer de cloudbeveiligingsfuncties van Microsoft Defender voor Eindpunt op macOS.</span><span class="sxs-lookup"><span data-stu-id="06b65-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="06b65-372">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-372">Section</span></span>|<span data-ttu-id="06b65-373">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-374">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-375">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-375">**Key**</span></span> | <span data-ttu-id="06b65-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="06b65-376">cloudService</span></span> |
| <span data-ttu-id="06b65-377">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-377">**Data type**</span></span> | <span data-ttu-id="06b65-378">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="06b65-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="06b65-379">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-379">**Comments**</span></span> | <span data-ttu-id="06b65-380">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="06b65-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="06b65-381">Beveiliging via de cloud in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="06b65-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="06b65-382">Geef op of u de beveiliging van het apparaat al dan niet wilt inschakelen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="06b65-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="06b65-383">Als u de beveiliging van uw services wilt verbeteren, raden we u aan deze functie ingeschakeld te houden.</span><span class="sxs-lookup"><span data-stu-id="06b65-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="06b65-384">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-384">Section</span></span>|<span data-ttu-id="06b65-385">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-386">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-387">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-387">**Key**</span></span> | <span data-ttu-id="06b65-388">ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="06b65-388">enabled</span></span> |
| <span data-ttu-id="06b65-389">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-389">**Data type**</span></span> | <span data-ttu-id="06b65-390">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-390">Boolean</span></span> |
| <span data-ttu-id="06b65-391">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-391">**Possible values**</span></span> | <span data-ttu-id="06b65-392">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="06b65-392">true (default)</span></span> <br/> <span data-ttu-id="06b65-393">onwaar</span><span class="sxs-lookup"><span data-stu-id="06b65-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="06b65-394">Diagnostisch verzamelingsniveau</span><span class="sxs-lookup"><span data-stu-id="06b65-394">Diagnostic collection level</span></span>

<span data-ttu-id="06b65-395">Diagnostische gegevens worden gebruikt om Microsoft Defender voor Eindpunt veilig en up-to-date te houden, problemen op te sporen, te diagnosticeren en op te lossen, en om productverbeteringen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="06b65-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="06b65-396">Deze instelling bepaalt het niveau van de diagnostische gegevens die door Microsoft Defender voor Eindpunt naar Microsoft worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="06b65-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="06b65-397">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-397">Section</span></span>|<span data-ttu-id="06b65-398">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-399">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-400">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-400">**Key**</span></span> | <span data-ttu-id="06b65-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="06b65-401">diagnosticLevel</span></span> |
| <span data-ttu-id="06b65-402">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-402">**Data type**</span></span> | <span data-ttu-id="06b65-403">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-403">String</span></span> |
| <span data-ttu-id="06b65-404">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-404">**Possible values**</span></span> | <span data-ttu-id="06b65-405">optioneel (standaard)</span><span class="sxs-lookup"><span data-stu-id="06b65-405">optional (default)</span></span> <br/> <span data-ttu-id="06b65-406">Vereist</span><span class="sxs-lookup"><span data-stu-id="06b65-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="06b65-407">Automatische voorbeeldinzendingen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="06b65-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="06b65-408">Hiermee wordt bepaald of verdachte steekproeven (die waarschijnlijk bedreigingen bevatten) naar Microsoft worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="06b65-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="06b65-409">U wordt gevraagd of het ingediende bestand waarschijnlijk persoonlijke gegevens bevat.</span><span class="sxs-lookup"><span data-stu-id="06b65-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="06b65-410">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-410">Section</span></span>|<span data-ttu-id="06b65-411">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-412">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-413">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-413">**Key**</span></span> | <span data-ttu-id="06b65-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="06b65-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="06b65-415">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-415">**Data type**</span></span> | <span data-ttu-id="06b65-416">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-416">Boolean</span></span> |
| <span data-ttu-id="06b65-417">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-417">**Possible values**</span></span> | <span data-ttu-id="06b65-418">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="06b65-418">true (default)</span></span> <br/> <span data-ttu-id="06b65-419">onwaar</span><span class="sxs-lookup"><span data-stu-id="06b65-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="06b65-420">Automatische beveiligingsinformatie-updates in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="06b65-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="06b65-421">Hiermee bepaalt u of beveiligingsinformatieupdates automatisch worden geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="06b65-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="06b65-422">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-422">Section</span></span>|<span data-ttu-id="06b65-423">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-424">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-424">**Key**</span></span> | <span data-ttu-id="06b65-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="06b65-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="06b65-426">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-426">**Data type**</span></span> | <span data-ttu-id="06b65-427">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-427">Boolean</span></span> |
| <span data-ttu-id="06b65-428">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-428">**Possible values**</span></span> | <span data-ttu-id="06b65-429">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="06b65-429">true (default)</span></span> <br/> <span data-ttu-id="06b65-430">onwaar</span><span class="sxs-lookup"><span data-stu-id="06b65-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="06b65-431">Gebruikersinterfacevoorkeuren</span><span class="sxs-lookup"><span data-stu-id="06b65-431">User interface preferences</span></span>

<span data-ttu-id="06b65-432">Beheer de voorkeuren voor de gebruikersinterface van Microsoft Defender voor Eindpunt op macOS.</span><span class="sxs-lookup"><span data-stu-id="06b65-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="06b65-433">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-433">Section</span></span>|<span data-ttu-id="06b65-434">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-435">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-436">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-436">**Key**</span></span> | <span data-ttu-id="06b65-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="06b65-437">userInterface</span></span> |
| <span data-ttu-id="06b65-438">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-438">**Data type**</span></span> | <span data-ttu-id="06b65-439">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="06b65-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="06b65-440">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-440">**Comments**</span></span> | <span data-ttu-id="06b65-441">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="06b65-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="06b65-442">Pictogram statusmenu weergeven/verbergen</span><span class="sxs-lookup"><span data-stu-id="06b65-442">Show / hide status menu icon</span></span>

<span data-ttu-id="06b65-443">Geef op of u het statusmenupictogram wilt weergeven of verbergen in de rechterbovenhoek van het scherm.</span><span class="sxs-lookup"><span data-stu-id="06b65-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="06b65-444">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-444">Section</span></span>|<span data-ttu-id="06b65-445">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-446">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-447">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-447">**Key**</span></span> | <span data-ttu-id="06b65-448">StatusMenuIcon verbergen</span><span class="sxs-lookup"><span data-stu-id="06b65-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="06b65-449">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-449">**Data type**</span></span> | <span data-ttu-id="06b65-450">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-450">Boolean</span></span> |
| <span data-ttu-id="06b65-451">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-451">**Possible values**</span></span> | <span data-ttu-id="06b65-452">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="06b65-452">false (default)</span></span> <br/> <span data-ttu-id="06b65-453">waar</span><span class="sxs-lookup"><span data-stu-id="06b65-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="06b65-454">Optie weergeven/verbergen om feedback te verzenden</span><span class="sxs-lookup"><span data-stu-id="06b65-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="06b65-455">Geef op of gebruikers feedback kunnen verzenden naar Microsoft door naar `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="06b65-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="06b65-456">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-456">Section</span></span>|<span data-ttu-id="06b65-457">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-458">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-459">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-459">**Key**</span></span> | <span data-ttu-id="06b65-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="06b65-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="06b65-461">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-461">**Data type**</span></span> | <span data-ttu-id="06b65-462">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-462">String</span></span> |
| <span data-ttu-id="06b65-463">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-463">**Possible values**</span></span> | <span data-ttu-id="06b65-464">ingeschakeld (standaard)</span><span class="sxs-lookup"><span data-stu-id="06b65-464">enabled (default)</span></span> <br/> <span data-ttu-id="06b65-465">uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="06b65-465">disabled</span></span> |
| <span data-ttu-id="06b65-466">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-466">**Comments**</span></span> | <span data-ttu-id="06b65-467">Beschikbaar in Microsoft Defender voor Eindpunt versie 101.19.61 of hoger.</span><span class="sxs-lookup"><span data-stu-id="06b65-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="06b65-468">Eindpuntdetectie- en antwoordvoorkeuren</span><span class="sxs-lookup"><span data-stu-id="06b65-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="06b65-469">Beheer de voorkeuren van het onderdeel eindpuntdetectie en -antwoord (EDR) van Microsoft Defender voor Eindpunt in macOS.</span><span class="sxs-lookup"><span data-stu-id="06b65-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="06b65-470">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-470">Section</span></span>|<span data-ttu-id="06b65-471">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-472">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-473">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-473">**Key**</span></span> | <span data-ttu-id="06b65-474">edr</span><span class="sxs-lookup"><span data-stu-id="06b65-474">edr</span></span> |
| <span data-ttu-id="06b65-475">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-475">**Data type**</span></span> | <span data-ttu-id="06b65-476">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="06b65-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="06b65-477">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-477">**Comments**</span></span> | <span data-ttu-id="06b65-478">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="06b65-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="06b65-479">Apparaatlabels</span><span class="sxs-lookup"><span data-stu-id="06b65-479">Device tags</span></span>

<span data-ttu-id="06b65-480">Geef een tagnaam en de waarde op.</span><span class="sxs-lookup"><span data-stu-id="06b65-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="06b65-481">Met de tag GROEP wordt het apparaat gelabeld met de opgegeven waarde.</span><span class="sxs-lookup"><span data-stu-id="06b65-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="06b65-482">De tag wordt weergegeven in de portal onder de apparaatpagina en kan worden gebruikt voor het filteren en groeperen van apparaten.</span><span class="sxs-lookup"><span data-stu-id="06b65-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="06b65-483">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-483">Section</span></span>|<span data-ttu-id="06b65-484">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-485">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-486">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-486">**Key**</span></span> | <span data-ttu-id="06b65-487">tags</span><span class="sxs-lookup"><span data-stu-id="06b65-487">tags</span></span> |
| <span data-ttu-id="06b65-488">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-488">**Data type**</span></span> | <span data-ttu-id="06b65-489">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="06b65-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="06b65-490">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="06b65-490">**Comments**</span></span> | <span data-ttu-id="06b65-491">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="06b65-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="06b65-492">Type tag</span><span class="sxs-lookup"><span data-stu-id="06b65-492">Type of tag</span></span>

<span data-ttu-id="06b65-493">Geeft het type tag op</span><span class="sxs-lookup"><span data-stu-id="06b65-493">Specifies the type of tag</span></span>

|<span data-ttu-id="06b65-494">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-494">Section</span></span>|<span data-ttu-id="06b65-495">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-496">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-497">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-497">**Key**</span></span> | <span data-ttu-id="06b65-498">toets</span><span class="sxs-lookup"><span data-stu-id="06b65-498">key</span></span> |
| <span data-ttu-id="06b65-499">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-499">**Data type**</span></span> | <span data-ttu-id="06b65-500">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-500">String</span></span> |
| <span data-ttu-id="06b65-501">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="06b65-502">Waarde van tag</span><span class="sxs-lookup"><span data-stu-id="06b65-502">Value of tag</span></span>

<span data-ttu-id="06b65-503">Geeft de waarde van de tag op</span><span class="sxs-lookup"><span data-stu-id="06b65-503">Specifies the value of tag</span></span>

|<span data-ttu-id="06b65-504">Sectie</span><span class="sxs-lookup"><span data-stu-id="06b65-504">Section</span></span>|<span data-ttu-id="06b65-505">Waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="06b65-506">**Domein**</span><span class="sxs-lookup"><span data-stu-id="06b65-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="06b65-507">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="06b65-507">**Key**</span></span> | <span data-ttu-id="06b65-508">waarde</span><span class="sxs-lookup"><span data-stu-id="06b65-508">value</span></span> |
| <span data-ttu-id="06b65-509">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="06b65-509">**Data type**</span></span> | <span data-ttu-id="06b65-510">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-510">String</span></span> |
| <span data-ttu-id="06b65-511">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="06b65-511">**Possible values**</span></span> | <span data-ttu-id="06b65-512">een tekenreeks</span><span class="sxs-lookup"><span data-stu-id="06b65-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="06b65-513">Er kan slechts één waarde per tagtype worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="06b65-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="06b65-514">Het type tags is uniek en mag niet worden herhaald in hetzelfde configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="06b65-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="06b65-515">Aanbevolen configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="06b65-515">Recommended configuration profile</span></span>

<span data-ttu-id="06b65-516">Om aan de slag te gaan, wordt u aangeraden de volgende configuratie voor uw bedrijf te gebruiken om te profiteren van alle beveiligingsfuncties die Microsoft Defender voor Eindpunt biedt.</span><span class="sxs-lookup"><span data-stu-id="06b65-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="06b65-517">Het volgende configuratieprofiel (of, in het geval van JAMF, een eigenschappenlijst die kan worden geüpload naar het configuratieprofiel voor aangepaste instellingen) wordt als volgt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="06b65-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="06b65-518">Realtimebeveiliging inschakelen (RTP)</span><span class="sxs-lookup"><span data-stu-id="06b65-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="06b65-519">Geef op hoe de volgende bedreigingstypen worden verwerkt:</span><span class="sxs-lookup"><span data-stu-id="06b65-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="06b65-520">**Potentieel ongewenste toepassingen (PUA)** worden geblokkeerd</span><span class="sxs-lookup"><span data-stu-id="06b65-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="06b65-521">**Archiefbommen** (bestand met een hoge compressiesnelheid) worden gecontroleerd op Microsoft Defender voor eindpuntlogboeken</span><span class="sxs-lookup"><span data-stu-id="06b65-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="06b65-522">Automatische beveiligingsinformatie-updates inschakelen</span><span class="sxs-lookup"><span data-stu-id="06b65-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="06b65-523">Beveiliging via de cloud inschakelen</span><span class="sxs-lookup"><span data-stu-id="06b65-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="06b65-524">Automatische voorbeeldinzending inschakelen</span><span class="sxs-lookup"><span data-stu-id="06b65-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="06b65-525">Eigenschappenlijst voor HET CONFIGURATIEprofiel VAN JAMF</span><span class="sxs-lookup"><span data-stu-id="06b65-525">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="06b65-526">Intune-profiel</span><span class="sxs-lookup"><span data-stu-id="06b65-526">Intune profile</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="06b65-527">Voorbeeld van volledig configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="06b65-527">Full configuration profile example</span></span>

<span data-ttu-id="06b65-528">De volgende sjablonen bevatten vermeldingen voor alle instellingen die in dit document worden beschreven en kunnen worden gebruikt voor meer geavanceerde scenario's waarin u meer controle wilt over Microsoft Defender voor Eindpunt in macOS.</span><span class="sxs-lookup"><span data-stu-id="06b65-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="06b65-529">Eigenschappenlijst voor HET CONFIGURATIEprofiel VAN JAMF</span><span class="sxs-lookup"><span data-stu-id="06b65-529">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="06b65-530">Intune-profiel</span><span class="sxs-lookup"><span data-stu-id="06b65-530">Intune profile</span></span>

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a><span data-ttu-id="06b65-531">Validatie van eigenschappenlijst</span><span class="sxs-lookup"><span data-stu-id="06b65-531">Property list validation</span></span>

<span data-ttu-id="06b65-532">De lijst met eigenschappen moet een geldig *PLIST-bestand* zijn.</span><span class="sxs-lookup"><span data-stu-id="06b65-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="06b65-533">U kunt dit controleren door het volgende uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="06b65-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="06b65-534">Als het bestand goed is gevormd, wordt met de bovenstaande opdracht een exitcode van `OK` `0` .</span><span class="sxs-lookup"><span data-stu-id="06b65-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="06b65-535">Anders wordt een fout weergegeven die het probleem beschrijft en retourneert de opdracht een exitcode van `1` .</span><span class="sxs-lookup"><span data-stu-id="06b65-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="06b65-536">Implementatie van configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="06b65-536">Configuration profile deployment</span></span>

<span data-ttu-id="06b65-537">Nadat u het configuratieprofiel voor uw bedrijf hebt gemaakt, kunt u het implementeren via de beheerconsole die uw bedrijf gebruikt.</span><span class="sxs-lookup"><span data-stu-id="06b65-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="06b65-538">In de volgende secties worden instructies gegeven voor het implementeren van dit profiel met BEHULP van JAMF en Intune.</span><span class="sxs-lookup"><span data-stu-id="06b65-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="06b65-539">JAMF-implementatie</span><span class="sxs-lookup"><span data-stu-id="06b65-539">JAMF deployment</span></span>

<span data-ttu-id="06b65-540">Open in de JAMF-console **De configuratieprofielen van computers,** ga naar het configuratieprofiel dat u wilt gebruiken  >  en selecteer vervolgens **Aangepaste instellingen.**</span><span class="sxs-lookup"><span data-stu-id="06b65-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="06b65-541">Maak een item met `com.microsoft.wdav` als voorkeursdomein en upload de *.plist die* eerder is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="06b65-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="06b65-542">U moet het juiste voorkeursdomein invoeren ( ); anders worden de voorkeuren niet herkend `com.microsoft.wdav` door Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="06b65-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="06b65-543">Intune-implementatie</span><span class="sxs-lookup"><span data-stu-id="06b65-543">Intune deployment</span></span>

1. <span data-ttu-id="06b65-544">Open   >  **Apparaatconfiguratie beheren.**</span><span class="sxs-lookup"><span data-stu-id="06b65-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="06b65-545">Selecteer **Profielen beheren**  >  **Profiel**  >  **maken.**</span><span class="sxs-lookup"><span data-stu-id="06b65-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="06b65-546">Kies een naam voor het profiel.</span><span class="sxs-lookup"><span data-stu-id="06b65-546">Choose a name for the profile.</span></span> <span data-ttu-id="06b65-547">**Platform=macOS wijzigen** in **Profieltype=Aangepast**.</span><span class="sxs-lookup"><span data-stu-id="06b65-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="06b65-548">Selecteer Configureren.</span><span class="sxs-lookup"><span data-stu-id="06b65-548">Select Configure.</span></span>

3. <span data-ttu-id="06b65-549">Sla de eerder geproduceerde PLIST op als `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="06b65-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="06b65-550">Voer `com.microsoft.wdav` de naam van het aangepaste **configuratieprofiel in.**</span><span class="sxs-lookup"><span data-stu-id="06b65-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="06b65-551">Open het configuratieprofiel en upload het `com.microsoft.wdav.xml` bestand.</span><span class="sxs-lookup"><span data-stu-id="06b65-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="06b65-552">(Dit bestand is gemaakt in stap 3.)</span><span class="sxs-lookup"><span data-stu-id="06b65-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="06b65-553">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="06b65-553">Select **OK**.</span></span>

7. <span data-ttu-id="06b65-554">Selecteer **Opdrachten**  >  **beheren.**</span><span class="sxs-lookup"><span data-stu-id="06b65-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="06b65-555">Selecteer op **het** tabblad Opnemen de optie Toewijzen aan **alle & alle apparaten.**</span><span class="sxs-lookup"><span data-stu-id="06b65-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="06b65-556">U moet de juiste naam van het aangepaste configuratieprofiel invoeren. Anders worden deze voorkeuren niet herkend door Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="06b65-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="06b65-557">Resources</span><span class="sxs-lookup"><span data-stu-id="06b65-557">Resources</span></span>

- [<span data-ttu-id="06b65-558">Documentatie over configuratieprofielen (documentatie van Apple voor ontwikkelaars, Engelstalig)</span><span class="sxs-lookup"><span data-stu-id="06b65-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
