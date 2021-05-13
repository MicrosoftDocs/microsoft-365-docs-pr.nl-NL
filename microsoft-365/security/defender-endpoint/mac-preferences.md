---
title: Voorkeuren instellen voor Microsoft Defender voor Eindpunt op Mac
description: Configureer MMicrosoft Defender voor Endpoint op Mac in bedrijfsorganisaties.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346400"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="7a251-104">Voorkeuren instellen voor Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="7a251-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7a251-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7a251-105">**Applies to:**</span></span>

- [<span data-ttu-id="7a251-106">Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="7a251-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="7a251-107">Dit artikel bevat instructies voor het instellen van voorkeuren voor Microsoft Defender voor Eindpunt voor macOS in bedrijfsorganisaties.</span><span class="sxs-lookup"><span data-stu-id="7a251-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="7a251-108">Zie Resources als u Microsoft Defender voor Eindpunt op [](mac-resources.md#configuring-from-the-command-line)macOS wilt configureren met behulp van de opdrachtregelinterface.</span><span class="sxs-lookup"><span data-stu-id="7a251-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="7a251-109">Samenvatting</span><span class="sxs-lookup"><span data-stu-id="7a251-109">Summary</span></span>

<span data-ttu-id="7a251-110">In ondernemingsorganisaties kan Microsoft Defender voor Eindpunt op macOS worden beheerd via een configuratieprofiel dat wordt geïmplementeerd met behulp van een van de verschillende beheerhulpmiddelen.</span><span class="sxs-lookup"><span data-stu-id="7a251-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="7a251-111">Voorkeuren die worden beheerd door uw beveiligingsbewerkingsteam, hebben voorrang op voorkeuren die lokaal op het apparaat zijn ingesteld.</span><span class="sxs-lookup"><span data-stu-id="7a251-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="7a251-112">Het wijzigen van de voorkeuren die zijn ingesteld via het configuratieprofiel vereist geëscaleerde bevoegdheden en is niet beschikbaar voor gebruikers zonder beheerdersmachtigingen.</span><span class="sxs-lookup"><span data-stu-id="7a251-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="7a251-113">In dit artikel wordt de structuur van het configuratieprofiel beschreven, wordt een aanbevolen profiel beschreven dat u kunt gebruiken om aan de slag te gaan en worden instructies gegeven over het implementeren van het profiel.</span><span class="sxs-lookup"><span data-stu-id="7a251-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="7a251-114">Configuratieprofielstructuur</span><span class="sxs-lookup"><span data-stu-id="7a251-114">Configuration profile structure</span></span>

<span data-ttu-id="7a251-115">Het configuratieprofiel is een *PLIST-bestand* dat bestaat uit items die zijn geïdentificeerd met een sleutel (die de naam van de voorkeur aan duidt), gevolgd door een waarde, die afhankelijk is van de aard van de voorkeur.</span><span class="sxs-lookup"><span data-stu-id="7a251-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="7a251-116">Waarden kunnen eenvoudig zijn (zoals een numerieke waarde) of complex, zoals een geneste lijst met voorkeuren.</span><span class="sxs-lookup"><span data-stu-id="7a251-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="7a251-117">De indeling van het configuratieprofiel is afhankelijk van de beheerconsole die u gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7a251-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="7a251-118">De volgende secties bevatten voorbeelden van configuratieprofielen voor JAMF en Intune.</span><span class="sxs-lookup"><span data-stu-id="7a251-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="7a251-119">Het bovenste niveau van het configuratieprofiel bevat productvoorkeuren en vermeldingen voor subareas van Microsoft Defender voor Eindpunt, die in de volgende secties in meer detail worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="7a251-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="7a251-120">Voorkeuren voor antivirusprogramma's</span><span class="sxs-lookup"><span data-stu-id="7a251-120">Antivirus engine preferences</span></span>

<span data-ttu-id="7a251-121">De *antivirusEngine-sectie* van het configuratieprofiel wordt gebruikt om de voorkeuren van het antivirusonderdeel van Microsoft Defender voor Eindpunt te beheren.</span><span class="sxs-lookup"><span data-stu-id="7a251-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="7a251-122">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-122">Section</span></span>|<span data-ttu-id="7a251-123">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-124">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-125">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-125">**Key**</span></span> | <span data-ttu-id="7a251-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="7a251-126">antivirusEngine</span></span> |
| <span data-ttu-id="7a251-127">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-127">**Data type**</span></span> | <span data-ttu-id="7a251-128">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="7a251-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="7a251-129">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-129">**Comments**</span></span> | <span data-ttu-id="7a251-130">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="7a251-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="7a251-131">Realtime beveiliging in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="7a251-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="7a251-132">Geef op of u realtimebeveiliging wilt inschakelen, waarmee bestanden worden gescand wanneer ze worden toegankelijk.</span><span class="sxs-lookup"><span data-stu-id="7a251-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="7a251-133">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-133">Section</span></span>|<span data-ttu-id="7a251-134">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-135">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-136">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-136">**Key**</span></span> | <span data-ttu-id="7a251-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="7a251-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="7a251-138">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-138">**Data type**</span></span> | <span data-ttu-id="7a251-139">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-139">Boolean</span></span> |
| <span data-ttu-id="7a251-140">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-140">**Possible values**</span></span> | <span data-ttu-id="7a251-141">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="7a251-141">true (default)</span></span> <br/> <span data-ttu-id="7a251-142">onwaar</span><span class="sxs-lookup"><span data-stu-id="7a251-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="7a251-143">Passieve modus in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="7a251-143">Enable / disable passive mode</span></span>

<span data-ttu-id="7a251-144">Geef op of de antivirusprogramma's in de passieve modus worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="7a251-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="7a251-145">De passieve modus heeft de volgende gevolgen:</span><span class="sxs-lookup"><span data-stu-id="7a251-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="7a251-146">Realtimebeveiliging is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="7a251-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="7a251-147">Scannen op aanvraag is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="7a251-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="7a251-148">Automatische herstel van bedreigingen is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="7a251-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="7a251-149">Beveiligingsinformatie-updates zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="7a251-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="7a251-150">Pictogram statusmenu is verborgen</span><span class="sxs-lookup"><span data-stu-id="7a251-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="7a251-151">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-151">Section</span></span>|<span data-ttu-id="7a251-152">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-153">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-154">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-154">**Key**</span></span> | <span data-ttu-id="7a251-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="7a251-155">passiveMode</span></span> |
| <span data-ttu-id="7a251-156">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-156">**Data type**</span></span> | <span data-ttu-id="7a251-157">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-157">Boolean</span></span> |
| <span data-ttu-id="7a251-158">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-158">**Possible values**</span></span> | <span data-ttu-id="7a251-159">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="7a251-159">false (default)</span></span> <br/> <span data-ttu-id="7a251-160">waar</span><span class="sxs-lookup"><span data-stu-id="7a251-160">true</span></span> |
| <span data-ttu-id="7a251-161">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-161">**Comments**</span></span> | <span data-ttu-id="7a251-162">Beschikbaar in Microsoft Defender voor Eindpunt versie 100.67.60 of hoger.</span><span class="sxs-lookup"><span data-stu-id="7a251-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="7a251-163">Beleid voor samenvoeging van uitsluiting</span><span class="sxs-lookup"><span data-stu-id="7a251-163">Exclusion merge policy</span></span>

<span data-ttu-id="7a251-164">Geef het samenvoegbeleid op voor uitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="7a251-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="7a251-165">Dit kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde uitsluitingen ( ) of alleen `merge` door beheerders gedefinieerde uitsluitingen ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="7a251-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="7a251-166">Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen uitsluitingen definiëren.</span><span class="sxs-lookup"><span data-stu-id="7a251-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="7a251-167">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-167">Section</span></span>|<span data-ttu-id="7a251-168">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-169">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-170">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-170">**Key**</span></span> | <span data-ttu-id="7a251-171">uitsluitingenMergePolicy</span><span class="sxs-lookup"><span data-stu-id="7a251-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="7a251-172">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-172">**Data type**</span></span> | <span data-ttu-id="7a251-173">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-173">String</span></span> |
| <span data-ttu-id="7a251-174">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-174">**Possible values**</span></span> | <span data-ttu-id="7a251-175">samenvoegen (standaard)</span><span class="sxs-lookup"><span data-stu-id="7a251-175">merge (default)</span></span> <br/> <span data-ttu-id="7a251-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="7a251-176">admin_only</span></span> |
| <span data-ttu-id="7a251-177">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-177">**Comments**</span></span> | <span data-ttu-id="7a251-178">Beschikbaar in Microsoft Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="7a251-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="7a251-179">Uitsluitingen scannen</span><span class="sxs-lookup"><span data-stu-id="7a251-179">Scan exclusions</span></span>

<span data-ttu-id="7a251-180">Geef entiteiten op die niet mogen worden gescand.</span><span class="sxs-lookup"><span data-stu-id="7a251-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="7a251-181">Uitsluitingen kunnen worden opgegeven door volledige paden, extensies of bestandsnamen.</span><span class="sxs-lookup"><span data-stu-id="7a251-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="7a251-182">(Uitsluitingen worden opgegeven als een matrix met items, beheerder kan zo veel elementen opgeven als nodig is, in elke volgorde.)</span><span class="sxs-lookup"><span data-stu-id="7a251-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="7a251-183">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-183">Section</span></span>|<span data-ttu-id="7a251-184">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-185">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-186">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-186">**Key**</span></span> | <span data-ttu-id="7a251-187">uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="7a251-187">exclusions</span></span> |
| <span data-ttu-id="7a251-188">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-188">**Data type**</span></span> | <span data-ttu-id="7a251-189">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="7a251-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="7a251-190">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-190">**Comments**</span></span> | <span data-ttu-id="7a251-191">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="7a251-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="7a251-192">Type uitsluiting</span><span class="sxs-lookup"><span data-stu-id="7a251-192">Type of exclusion</span></span>

<span data-ttu-id="7a251-193">Geef inhoud op die niet per type kan worden gescand.</span><span class="sxs-lookup"><span data-stu-id="7a251-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="7a251-194">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-194">Section</span></span>|<span data-ttu-id="7a251-195">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-196">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-197">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-197">**Key**</span></span> | <span data-ttu-id="7a251-198">$type</span><span class="sxs-lookup"><span data-stu-id="7a251-198">$type</span></span> |
| <span data-ttu-id="7a251-199">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-199">**Data type**</span></span> | <span data-ttu-id="7a251-200">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-200">String</span></span> |
| <span data-ttu-id="7a251-201">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-201">**Possible values**</span></span> | <span data-ttu-id="7a251-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="7a251-202">excludedPath</span></span> <br/> <span data-ttu-id="7a251-203">uitgeslotenFileExtension</span><span class="sxs-lookup"><span data-stu-id="7a251-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="7a251-204">uitgeslotenFileName</span><span class="sxs-lookup"><span data-stu-id="7a251-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="7a251-205">Pad naar uitgesloten inhoud</span><span class="sxs-lookup"><span data-stu-id="7a251-205">Path to excluded content</span></span>

<span data-ttu-id="7a251-206">Geef inhoud op die niet kan worden gescand via een volledig bestandspad.</span><span class="sxs-lookup"><span data-stu-id="7a251-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="7a251-207">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-207">Section</span></span>|<span data-ttu-id="7a251-208">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-209">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-210">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-210">**Key**</span></span> | <span data-ttu-id="7a251-211">pad</span><span class="sxs-lookup"><span data-stu-id="7a251-211">path</span></span> |
| <span data-ttu-id="7a251-212">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-212">**Data type**</span></span> | <span data-ttu-id="7a251-213">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-213">String</span></span> |
| <span data-ttu-id="7a251-214">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-214">**Possible values**</span></span> | <span data-ttu-id="7a251-215">geldige paden</span><span class="sxs-lookup"><span data-stu-id="7a251-215">valid paths</span></span> |
| <span data-ttu-id="7a251-216">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-216">**Comments**</span></span> | <span data-ttu-id="7a251-217">Alleen van toepassing *als $type* *is uitgeslotenPath*</span><span class="sxs-lookup"><span data-stu-id="7a251-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="7a251-218">Ondersteunde uitsluitingstypen</span><span class="sxs-lookup"><span data-stu-id="7a251-218">Supported exclusion types</span></span>

<span data-ttu-id="7a251-219">In de volgende tabel ziet u de uitsluitingstypen die worden ondersteund door Defender voor Eindpunt op Mac.</span><span class="sxs-lookup"><span data-stu-id="7a251-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="7a251-220">Uitsluiting</span><span class="sxs-lookup"><span data-stu-id="7a251-220">Exclusion</span></span> | <span data-ttu-id="7a251-221">Definitie</span><span class="sxs-lookup"><span data-stu-id="7a251-221">Definition</span></span> | <span data-ttu-id="7a251-222">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="7a251-222">Examples</span></span>
---|---|---
<span data-ttu-id="7a251-223">Bestandsextensie</span><span class="sxs-lookup"><span data-stu-id="7a251-223">File extension</span></span> | <span data-ttu-id="7a251-224">Alle bestanden met de extensie, overal op het apparaat</span><span class="sxs-lookup"><span data-stu-id="7a251-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="7a251-225">Bestand</span><span class="sxs-lookup"><span data-stu-id="7a251-225">File</span></span> | <span data-ttu-id="7a251-226">Een specifiek bestand dat is geïdentificeerd door het volledige pad</span><span class="sxs-lookup"><span data-stu-id="7a251-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="7a251-227">Map</span><span class="sxs-lookup"><span data-stu-id="7a251-227">Folder</span></span> | <span data-ttu-id="7a251-228">Alle bestanden onder de opgegeven map (recursief)</span><span class="sxs-lookup"><span data-stu-id="7a251-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="7a251-229">Proces</span><span class="sxs-lookup"><span data-stu-id="7a251-229">Process</span></span> | <span data-ttu-id="7a251-230">Een specifiek proces (opgegeven door het volledige pad of de bestandsnaam) en alle bestanden die hiermee worden geopend</span><span class="sxs-lookup"><span data-stu-id="7a251-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="7a251-231">De bovenstaande paden moeten harde koppelingen zijn, geen symbolische koppelingen, om te kunnen worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="7a251-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="7a251-232">U kunt controleren of een pad een symbolische koppeling is door te `file <path-name>` lopen.</span><span class="sxs-lookup"><span data-stu-id="7a251-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="7a251-233">Bestands-, map- en procesuitsluitingen ondersteunen de volgende jokertekens:</span><span class="sxs-lookup"><span data-stu-id="7a251-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="7a251-234">Jokerteken</span><span class="sxs-lookup"><span data-stu-id="7a251-234">Wildcard</span></span> | <span data-ttu-id="7a251-235">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="7a251-235">Description</span></span> | <span data-ttu-id="7a251-236">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="7a251-236">Example</span></span> | <span data-ttu-id="7a251-237">Overeenkomsten</span><span class="sxs-lookup"><span data-stu-id="7a251-237">Matches</span></span> | <span data-ttu-id="7a251-238">Komt niet overeen met</span><span class="sxs-lookup"><span data-stu-id="7a251-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="7a251-239">Komt overeen met een aantal tekens, inclusief geen tekens (houd er rekening mee dat wanneer dit jokerteken binnen een pad wordt gebruikt, dit slechts één map vervangt)</span><span class="sxs-lookup"><span data-stu-id="7a251-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="7a251-240">?</span><span class="sxs-lookup"><span data-stu-id="7a251-240">?</span></span> | <span data-ttu-id="7a251-241">Komt overeen met een enkel teken</span><span class="sxs-lookup"><span data-stu-id="7a251-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="7a251-242">Padtype (bestand /adreslijst)</span><span class="sxs-lookup"><span data-stu-id="7a251-242">Path type (file / directory)</span></span>

<span data-ttu-id="7a251-243">Geef aan of *de eigenschap pad* verwijst naar een bestand of adreslijst.</span><span class="sxs-lookup"><span data-stu-id="7a251-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="7a251-244">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-244">Section</span></span>|<span data-ttu-id="7a251-245">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-246">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-247">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-247">**Key**</span></span> | <span data-ttu-id="7a251-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="7a251-248">isDirectory</span></span> |
| <span data-ttu-id="7a251-249">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-249">**Data type**</span></span> | <span data-ttu-id="7a251-250">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-250">Boolean</span></span> |
| <span data-ttu-id="7a251-251">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-251">**Possible values**</span></span> | <span data-ttu-id="7a251-252">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="7a251-252">false (default)</span></span> <br/> <span data-ttu-id="7a251-253">waar</span><span class="sxs-lookup"><span data-stu-id="7a251-253">true</span></span> |
| <span data-ttu-id="7a251-254">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-254">**Comments**</span></span> | <span data-ttu-id="7a251-255">Alleen van toepassing *als $type* *is uitgeslotenPath*</span><span class="sxs-lookup"><span data-stu-id="7a251-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="7a251-256">Bestandsextensie uitgesloten van de scan</span><span class="sxs-lookup"><span data-stu-id="7a251-256">File extension excluded from the scan</span></span>

<span data-ttu-id="7a251-257">Geef inhoud op die niet kan worden gescand door bestandsextensie.</span><span class="sxs-lookup"><span data-stu-id="7a251-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="7a251-258">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-258">Section</span></span>|<span data-ttu-id="7a251-259">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-260">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-261">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-261">**Key**</span></span> | <span data-ttu-id="7a251-262">extensie</span><span class="sxs-lookup"><span data-stu-id="7a251-262">extension</span></span> |
| <span data-ttu-id="7a251-263">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-263">**Data type**</span></span> | <span data-ttu-id="7a251-264">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-264">String</span></span> |
| <span data-ttu-id="7a251-265">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-265">**Possible values**</span></span> | <span data-ttu-id="7a251-266">geldige bestandsextensies</span><span class="sxs-lookup"><span data-stu-id="7a251-266">valid file extensions</span></span> |
| <span data-ttu-id="7a251-267">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-267">**Comments**</span></span> | <span data-ttu-id="7a251-268">Alleen van toepassing *als $type* *is uitgeslotenFileExtension*</span><span class="sxs-lookup"><span data-stu-id="7a251-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="7a251-269">Proces uitgesloten van de scan</span><span class="sxs-lookup"><span data-stu-id="7a251-269">Process excluded from the scan</span></span>

<span data-ttu-id="7a251-270">Geef een proces op waarvoor alle bestandsactiviteit is uitgesloten van scannen.</span><span class="sxs-lookup"><span data-stu-id="7a251-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="7a251-271">Het proces kan worden opgegeven door de naam (bijvoorbeeld) of het volledige `cat` pad `/bin/cat` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="7a251-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="7a251-272">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-272">Section</span></span>|<span data-ttu-id="7a251-273">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-274">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-275">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-275">**Key**</span></span> | <span data-ttu-id="7a251-276">naam</span><span class="sxs-lookup"><span data-stu-id="7a251-276">name</span></span> |
| <span data-ttu-id="7a251-277">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-277">**Data type**</span></span> | <span data-ttu-id="7a251-278">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-278">String</span></span> |
| <span data-ttu-id="7a251-279">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-279">**Possible values**</span></span> | <span data-ttu-id="7a251-280">een tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-280">any string</span></span> |
| <span data-ttu-id="7a251-281">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-281">**Comments**</span></span> | <span data-ttu-id="7a251-282">Alleen van toepassing *als $type* *is uitgeslotenFileName*</span><span class="sxs-lookup"><span data-stu-id="7a251-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="7a251-283">Toegestane bedreigingen</span><span class="sxs-lookup"><span data-stu-id="7a251-283">Allowed threats</span></span>

<span data-ttu-id="7a251-284">Geef bedreigingen op op naam die niet worden geblokkeerd door Defender voor Eindpunt op Mac.</span><span class="sxs-lookup"><span data-stu-id="7a251-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="7a251-285">Deze bedreigingen kunnen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="7a251-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="7a251-286">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-286">Section</span></span>|<span data-ttu-id="7a251-287">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-288">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-289">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-289">**Key**</span></span> | <span data-ttu-id="7a251-290">toegestaanThreats</span><span class="sxs-lookup"><span data-stu-id="7a251-290">allowedThreats</span></span> |
| <span data-ttu-id="7a251-291">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-291">**Data type**</span></span> | <span data-ttu-id="7a251-292">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="7a251-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="7a251-293">Niet-toegestaan bedreigingsacties</span><span class="sxs-lookup"><span data-stu-id="7a251-293">Disallowed threat actions</span></span>

<span data-ttu-id="7a251-294">Hiermee beperkt u de acties die de lokale gebruiker van een apparaat kan uitvoeren wanneer bedreigingen worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="7a251-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="7a251-295">De acties in deze lijst worden niet weergegeven in de gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="7a251-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="7a251-296">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-296">Section</span></span>|<span data-ttu-id="7a251-297">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-298">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-299">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-299">**Key**</span></span> | <span data-ttu-id="7a251-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="7a251-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="7a251-301">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-301">**Data type**</span></span> | <span data-ttu-id="7a251-302">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="7a251-302">Array of strings</span></span> |
| <span data-ttu-id="7a251-303">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-303">**Possible values**</span></span> | <span data-ttu-id="7a251-304">toestaan (gebruikers kunnen geen bedreigingen toestaan)</span><span class="sxs-lookup"><span data-stu-id="7a251-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="7a251-305">herstellen (gebruikers kunnen geen bedreigingen herstellen vanuit de quarantaine)</span><span class="sxs-lookup"><span data-stu-id="7a251-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="7a251-306">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-306">**Comments**</span></span> | <span data-ttu-id="7a251-307">Beschikbaar in Microsoft Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="7a251-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="7a251-308">Instellingen voor bedreigingstype</span><span class="sxs-lookup"><span data-stu-id="7a251-308">Threat type settings</span></span>

<span data-ttu-id="7a251-309">Geef op hoe bepaalde bedreigingstypen worden verwerkt door Microsoft Defender voor Eindpunt in macOS.</span><span class="sxs-lookup"><span data-stu-id="7a251-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="7a251-310">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-310">Section</span></span>|<span data-ttu-id="7a251-311">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-312">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-313">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-313">**Key**</span></span> | <span data-ttu-id="7a251-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="7a251-314">threatTypeSettings</span></span> |
| <span data-ttu-id="7a251-315">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-315">**Data type**</span></span> | <span data-ttu-id="7a251-316">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="7a251-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="7a251-317">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-317">**Comments**</span></span> | <span data-ttu-id="7a251-318">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="7a251-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="7a251-319">Type bedreiging</span><span class="sxs-lookup"><span data-stu-id="7a251-319">Threat type</span></span>

<span data-ttu-id="7a251-320">Geef bedreigingstypen op.</span><span class="sxs-lookup"><span data-stu-id="7a251-320">Specify threat types.</span></span>

|<span data-ttu-id="7a251-321">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-321">Section</span></span>|<span data-ttu-id="7a251-322">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-323">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-324">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-324">**Key**</span></span> | <span data-ttu-id="7a251-325">toets</span><span class="sxs-lookup"><span data-stu-id="7a251-325">key</span></span> |
| <span data-ttu-id="7a251-326">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-326">**Data type**</span></span> | <span data-ttu-id="7a251-327">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-327">String</span></span> |
| <span data-ttu-id="7a251-328">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-328">**Possible values**</span></span> | <span data-ttu-id="7a251-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="7a251-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="7a251-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="7a251-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="7a251-331">Actie ondernemen</span><span class="sxs-lookup"><span data-stu-id="7a251-331">Action to take</span></span>

<span data-ttu-id="7a251-332">Geef op welke actie moet worden ondernomen wanneer er een bedreiging wordt gedetecteerd van het type dat is opgegeven in de vorige sectie.</span><span class="sxs-lookup"><span data-stu-id="7a251-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="7a251-333">Kies uit de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="7a251-333">Choose from the following options:</span></span>

- <span data-ttu-id="7a251-334">**Audit:** uw apparaat is niet beveiligd tegen dit type bedreiging, maar er wordt wel een vermelding over de bedreiging geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="7a251-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="7a251-335">**Blokkeren:** uw apparaat is beveiligd tegen dit type bedreiging en u krijgt een melding in de gebruikersinterface en de beveiligingsconsole.</span><span class="sxs-lookup"><span data-stu-id="7a251-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="7a251-336">**Uit:** uw apparaat is niet beveiligd tegen dit type bedreiging en er wordt niets geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="7a251-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="7a251-337">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-337">Section</span></span>|<span data-ttu-id="7a251-338">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-339">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-340">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-340">**Key**</span></span> | <span data-ttu-id="7a251-341">waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-341">value</span></span> |
| <span data-ttu-id="7a251-342">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-342">**Data type**</span></span> | <span data-ttu-id="7a251-343">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-343">String</span></span> |
| <span data-ttu-id="7a251-344">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-344">**Possible values**</span></span> | <span data-ttu-id="7a251-345">audit (standaard)</span><span class="sxs-lookup"><span data-stu-id="7a251-345">audit (default)</span></span> <br/> <span data-ttu-id="7a251-346">blokkering</span><span class="sxs-lookup"><span data-stu-id="7a251-346">block</span></span> <br/> <span data-ttu-id="7a251-347">uit</span><span class="sxs-lookup"><span data-stu-id="7a251-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="7a251-348">Samenvoegbeleid voor instellingen voor bedreigingstype</span><span class="sxs-lookup"><span data-stu-id="7a251-348">Threat type settings merge policy</span></span>

<span data-ttu-id="7a251-349">Geef het samenvoegbeleid op voor instellingen voor bedreigingstype.</span><span class="sxs-lookup"><span data-stu-id="7a251-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="7a251-350">Dit kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde instellingen ( `merge` ) of alleen door beheerders gedefinieerde instellingen ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="7a251-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="7a251-351">Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen instellingen voor verschillende bedreigingstypen definiëren.</span><span class="sxs-lookup"><span data-stu-id="7a251-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="7a251-352">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-352">Section</span></span>|<span data-ttu-id="7a251-353">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-354">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-355">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-355">**Key**</span></span> | <span data-ttu-id="7a251-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="7a251-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="7a251-357">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-357">**Data type**</span></span> | <span data-ttu-id="7a251-358">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-358">String</span></span> |
| <span data-ttu-id="7a251-359">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-359">**Possible values**</span></span> | <span data-ttu-id="7a251-360">samenvoegen (standaard)</span><span class="sxs-lookup"><span data-stu-id="7a251-360">merge (default)</span></span> <br/> <span data-ttu-id="7a251-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="7a251-361">admin_only</span></span> |
| <span data-ttu-id="7a251-362">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-362">**Comments**</span></span> | <span data-ttu-id="7a251-363">Beschikbaar in Microsoft Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="7a251-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="7a251-364">Bewaargeschiedenis van antivirusscans (in dagen)</span><span class="sxs-lookup"><span data-stu-id="7a251-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="7a251-365">Geef het aantal dagen op dat de resultaten worden bewaard in de scangeschiedenis op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="7a251-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="7a251-366">Oude scanresultaten worden uit de geschiedenis verwijderd.</span><span class="sxs-lookup"><span data-stu-id="7a251-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="7a251-367">Oude in quarantaine geplaatste bestanden die ook van de schijf zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="7a251-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="7a251-368">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-368">Section</span></span>|<span data-ttu-id="7a251-369">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-370">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-371">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-371">**Key**</span></span> | <span data-ttu-id="7a251-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="7a251-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="7a251-373">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-373">**Data type**</span></span> | <span data-ttu-id="7a251-374">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-374">String</span></span> |
| <span data-ttu-id="7a251-375">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-375">**Possible values**</span></span> | <span data-ttu-id="7a251-376">90 (standaard).</span><span class="sxs-lookup"><span data-stu-id="7a251-376">90 (default).</span></span> <span data-ttu-id="7a251-377">Toegestane waarden zijn 1 dag tot 180 dagen.</span><span class="sxs-lookup"><span data-stu-id="7a251-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="7a251-378">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-378">**Comments**</span></span> | <span data-ttu-id="7a251-379">Beschikbaar in Microsoft Defender voor Eindpunt versie 101.07.23 of hoger.</span><span class="sxs-lookup"><span data-stu-id="7a251-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="7a251-380">Maximum aantal items in de geschiedenis van de antivirusscan</span><span class="sxs-lookup"><span data-stu-id="7a251-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="7a251-381">Geef het maximum aantal items op dat u wilt behouden in de scangeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="7a251-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="7a251-382">Items zijn alle scans op aanvraag die in het verleden zijn uitgevoerd en alle antivirusdetecties.</span><span class="sxs-lookup"><span data-stu-id="7a251-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="7a251-383">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-383">Section</span></span>|<span data-ttu-id="7a251-384">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-385">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-386">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-386">**Key**</span></span> | <span data-ttu-id="7a251-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="7a251-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="7a251-388">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-388">**Data type**</span></span> | <span data-ttu-id="7a251-389">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-389">String</span></span> |
| <span data-ttu-id="7a251-390">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-390">**Possible values**</span></span> | <span data-ttu-id="7a251-391">10000 (standaard).</span><span class="sxs-lookup"><span data-stu-id="7a251-391">10000 (default).</span></span> <span data-ttu-id="7a251-392">Toegestane waarden zijn van 5000 items tot 15000 items.</span><span class="sxs-lookup"><span data-stu-id="7a251-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="7a251-393">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-393">**Comments**</span></span> | <span data-ttu-id="7a251-394">Beschikbaar in Microsoft Defender voor Eindpunt versie 101.07.23 of hoger.</span><span class="sxs-lookup"><span data-stu-id="7a251-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="7a251-395">Beveiligingsvoorkeuren in de cloud</span><span class="sxs-lookup"><span data-stu-id="7a251-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="7a251-396">Configureer de cloudbeveiligingsfuncties van Microsoft Defender voor Eindpunt op macOS.</span><span class="sxs-lookup"><span data-stu-id="7a251-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="7a251-397">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-397">Section</span></span>|<span data-ttu-id="7a251-398">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-399">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-400">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-400">**Key**</span></span> | <span data-ttu-id="7a251-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="7a251-401">cloudService</span></span> |
| <span data-ttu-id="7a251-402">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-402">**Data type**</span></span> | <span data-ttu-id="7a251-403">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="7a251-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="7a251-404">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-404">**Comments**</span></span> | <span data-ttu-id="7a251-405">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="7a251-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="7a251-406">Beveiliging via de cloud in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="7a251-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="7a251-407">Geef op of u de beveiliging van het apparaat al dan niet wilt inschakelen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="7a251-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="7a251-408">Als u de beveiliging van uw services wilt verbeteren, raden we u aan deze functie ingeschakeld te houden.</span><span class="sxs-lookup"><span data-stu-id="7a251-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="7a251-409">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-409">Section</span></span>|<span data-ttu-id="7a251-410">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-411">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-412">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-412">**Key**</span></span> | <span data-ttu-id="7a251-413">ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="7a251-413">enabled</span></span> |
| <span data-ttu-id="7a251-414">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-414">**Data type**</span></span> | <span data-ttu-id="7a251-415">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-415">Boolean</span></span> |
| <span data-ttu-id="7a251-416">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-416">**Possible values**</span></span> | <span data-ttu-id="7a251-417">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="7a251-417">true (default)</span></span> <br/> <span data-ttu-id="7a251-418">onwaar</span><span class="sxs-lookup"><span data-stu-id="7a251-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="7a251-419">Diagnostisch verzamelingsniveau</span><span class="sxs-lookup"><span data-stu-id="7a251-419">Diagnostic collection level</span></span>

<span data-ttu-id="7a251-420">Diagnostische gegevens worden gebruikt om Microsoft Defender voor Eindpunt veilig en up-to-date te houden, problemen op te sporen, te diagnosticeren en op te lossen, en om productverbeteringen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="7a251-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="7a251-421">Deze instelling bepaalt het niveau van de diagnostische gegevens die door Microsoft Defender voor Eindpunt naar Microsoft worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="7a251-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="7a251-422">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-422">Section</span></span>|<span data-ttu-id="7a251-423">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-424">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-425">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-425">**Key**</span></span> | <span data-ttu-id="7a251-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="7a251-426">diagnosticLevel</span></span> |
| <span data-ttu-id="7a251-427">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-427">**Data type**</span></span> | <span data-ttu-id="7a251-428">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-428">String</span></span> |
| <span data-ttu-id="7a251-429">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-429">**Possible values**</span></span> | <span data-ttu-id="7a251-430">optioneel (standaard)</span><span class="sxs-lookup"><span data-stu-id="7a251-430">optional (default)</span></span> <br/> <span data-ttu-id="7a251-431">Vereist</span><span class="sxs-lookup"><span data-stu-id="7a251-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="7a251-432">Automatische voorbeeldinzendingen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="7a251-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="7a251-433">Hiermee wordt bepaald of verdachte steekproeven (die waarschijnlijk bedreigingen bevatten) naar Microsoft worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="7a251-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="7a251-434">U wordt gevraagd of het ingediende bestand waarschijnlijk persoonlijke gegevens bevat.</span><span class="sxs-lookup"><span data-stu-id="7a251-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="7a251-435">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-435">Section</span></span>|<span data-ttu-id="7a251-436">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-437">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-438">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-438">**Key**</span></span> | <span data-ttu-id="7a251-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="7a251-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="7a251-440">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-440">**Data type**</span></span> | <span data-ttu-id="7a251-441">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-441">Boolean</span></span> |
| <span data-ttu-id="7a251-442">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-442">**Possible values**</span></span> | <span data-ttu-id="7a251-443">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="7a251-443">true (default)</span></span> <br/> <span data-ttu-id="7a251-444">onwaar</span><span class="sxs-lookup"><span data-stu-id="7a251-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="7a251-445">Automatische beveiligingsinformatie-updates in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="7a251-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="7a251-446">Hiermee bepaalt u of beveiligingsinformatieupdates automatisch worden geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="7a251-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="7a251-447">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-447">Section</span></span>|<span data-ttu-id="7a251-448">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-449">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-449">**Key**</span></span> | <span data-ttu-id="7a251-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="7a251-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="7a251-451">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-451">**Data type**</span></span> | <span data-ttu-id="7a251-452">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-452">Boolean</span></span> |
| <span data-ttu-id="7a251-453">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-453">**Possible values**</span></span> | <span data-ttu-id="7a251-454">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="7a251-454">true (default)</span></span> <br/> <span data-ttu-id="7a251-455">onwaar</span><span class="sxs-lookup"><span data-stu-id="7a251-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="7a251-456">Gebruikersinterfacevoorkeuren</span><span class="sxs-lookup"><span data-stu-id="7a251-456">User interface preferences</span></span>

<span data-ttu-id="7a251-457">Beheer de voorkeuren voor de gebruikersinterface van Microsoft Defender voor Eindpunt op macOS.</span><span class="sxs-lookup"><span data-stu-id="7a251-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="7a251-458">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-458">Section</span></span>|<span data-ttu-id="7a251-459">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-460">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-461">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-461">**Key**</span></span> | <span data-ttu-id="7a251-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="7a251-462">userInterface</span></span> |
| <span data-ttu-id="7a251-463">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-463">**Data type**</span></span> | <span data-ttu-id="7a251-464">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="7a251-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="7a251-465">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-465">**Comments**</span></span> | <span data-ttu-id="7a251-466">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="7a251-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="7a251-467">Pictogram statusmenu weergeven/verbergen</span><span class="sxs-lookup"><span data-stu-id="7a251-467">Show / hide status menu icon</span></span>

<span data-ttu-id="7a251-468">Geef op of u het statusmenupictogram wilt weergeven of verbergen in de rechterbovenhoek van het scherm.</span><span class="sxs-lookup"><span data-stu-id="7a251-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="7a251-469">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-469">Section</span></span>|<span data-ttu-id="7a251-470">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-471">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-472">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-472">**Key**</span></span> | <span data-ttu-id="7a251-473">StatusMenuIcon verbergen</span><span class="sxs-lookup"><span data-stu-id="7a251-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="7a251-474">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-474">**Data type**</span></span> | <span data-ttu-id="7a251-475">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-475">Boolean</span></span> |
| <span data-ttu-id="7a251-476">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-476">**Possible values**</span></span> | <span data-ttu-id="7a251-477">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="7a251-477">false (default)</span></span> <br/> <span data-ttu-id="7a251-478">waar</span><span class="sxs-lookup"><span data-stu-id="7a251-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="7a251-479">Optie weergeven/verbergen om feedback te verzenden</span><span class="sxs-lookup"><span data-stu-id="7a251-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="7a251-480">Geef op of gebruikers feedback kunnen verzenden naar Microsoft door naar `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="7a251-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="7a251-481">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-481">Section</span></span>|<span data-ttu-id="7a251-482">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-483">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-484">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-484">**Key**</span></span> | <span data-ttu-id="7a251-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="7a251-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="7a251-486">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-486">**Data type**</span></span> | <span data-ttu-id="7a251-487">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-487">String</span></span> |
| <span data-ttu-id="7a251-488">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-488">**Possible values**</span></span> | <span data-ttu-id="7a251-489">ingeschakeld (standaard)</span><span class="sxs-lookup"><span data-stu-id="7a251-489">enabled (default)</span></span> <br/> <span data-ttu-id="7a251-490">uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="7a251-490">disabled</span></span> |
| <span data-ttu-id="7a251-491">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-491">**Comments**</span></span> | <span data-ttu-id="7a251-492">Beschikbaar in Microsoft Defender voor Eindpunt versie 101.19.61 of hoger.</span><span class="sxs-lookup"><span data-stu-id="7a251-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="7a251-493">Eindpuntdetectie- en antwoordvoorkeuren</span><span class="sxs-lookup"><span data-stu-id="7a251-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="7a251-494">Beheer de voorkeuren van het eindpuntdetectie en -respons (EDR) van Microsoft Defender voor Eindpunt in macOS.</span><span class="sxs-lookup"><span data-stu-id="7a251-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="7a251-495">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-495">Section</span></span>|<span data-ttu-id="7a251-496">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-497">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-498">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-498">**Key**</span></span> | <span data-ttu-id="7a251-499">edr</span><span class="sxs-lookup"><span data-stu-id="7a251-499">edr</span></span> |
| <span data-ttu-id="7a251-500">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-500">**Data type**</span></span> | <span data-ttu-id="7a251-501">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="7a251-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="7a251-502">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-502">**Comments**</span></span> | <span data-ttu-id="7a251-503">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="7a251-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="7a251-504">Apparaatlabels</span><span class="sxs-lookup"><span data-stu-id="7a251-504">Device tags</span></span>

<span data-ttu-id="7a251-505">Geef een tagnaam en de waarde op.</span><span class="sxs-lookup"><span data-stu-id="7a251-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="7a251-506">Met de tag GROEP wordt het apparaat gelabeld met de opgegeven waarde.</span><span class="sxs-lookup"><span data-stu-id="7a251-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="7a251-507">De tag wordt weergegeven in de portal onder de apparaatpagina en kan worden gebruikt voor het filteren en groeperen van apparaten.</span><span class="sxs-lookup"><span data-stu-id="7a251-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="7a251-508">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-508">Section</span></span>|<span data-ttu-id="7a251-509">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-510">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-511">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-511">**Key**</span></span> | <span data-ttu-id="7a251-512">tags</span><span class="sxs-lookup"><span data-stu-id="7a251-512">tags</span></span> |
| <span data-ttu-id="7a251-513">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-513">**Data type**</span></span> | <span data-ttu-id="7a251-514">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="7a251-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="7a251-515">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="7a251-515">**Comments**</span></span> | <span data-ttu-id="7a251-516">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="7a251-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="7a251-517">Type tag</span><span class="sxs-lookup"><span data-stu-id="7a251-517">Type of tag</span></span>

<span data-ttu-id="7a251-518">Geeft het type tag op</span><span class="sxs-lookup"><span data-stu-id="7a251-518">Specifies the type of tag</span></span>

|<span data-ttu-id="7a251-519">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-519">Section</span></span>|<span data-ttu-id="7a251-520">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-521">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-522">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-522">**Key**</span></span> | <span data-ttu-id="7a251-523">toets</span><span class="sxs-lookup"><span data-stu-id="7a251-523">key</span></span> |
| <span data-ttu-id="7a251-524">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-524">**Data type**</span></span> | <span data-ttu-id="7a251-525">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-525">String</span></span> |
| <span data-ttu-id="7a251-526">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="7a251-527">Waarde van tag</span><span class="sxs-lookup"><span data-stu-id="7a251-527">Value of tag</span></span>

<span data-ttu-id="7a251-528">Geeft de waarde van de tag op</span><span class="sxs-lookup"><span data-stu-id="7a251-528">Specifies the value of tag</span></span>

|<span data-ttu-id="7a251-529">Sectie</span><span class="sxs-lookup"><span data-stu-id="7a251-529">Section</span></span>|<span data-ttu-id="7a251-530">Waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="7a251-531">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7a251-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="7a251-532">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="7a251-532">**Key**</span></span> | <span data-ttu-id="7a251-533">waarde</span><span class="sxs-lookup"><span data-stu-id="7a251-533">value</span></span> |
| <span data-ttu-id="7a251-534">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="7a251-534">**Data type**</span></span> | <span data-ttu-id="7a251-535">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-535">String</span></span> |
| <span data-ttu-id="7a251-536">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="7a251-536">**Possible values**</span></span> | <span data-ttu-id="7a251-537">een tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a251-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="7a251-538">Er kan slechts één waarde per tagtype worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="7a251-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="7a251-539">Het type tags is uniek en mag niet worden herhaald in hetzelfde configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="7a251-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="7a251-540">Aanbevolen configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="7a251-540">Recommended configuration profile</span></span>

<span data-ttu-id="7a251-541">Om aan de slag te gaan, wordt u aangeraden de volgende configuratie voor uw bedrijf te gebruiken om te profiteren van alle beveiligingsfuncties die Microsoft Defender voor Eindpunt biedt.</span><span class="sxs-lookup"><span data-stu-id="7a251-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="7a251-542">Het volgende configuratieprofiel (of, in het geval van JAMF, een eigenschappenlijst die kan worden geüpload naar het configuratieprofiel voor aangepaste instellingen) wordt als volgt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="7a251-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="7a251-543">Realtimebeveiliging inschakelen (RTP)</span><span class="sxs-lookup"><span data-stu-id="7a251-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="7a251-544">Geef op hoe de volgende bedreigingstypen worden verwerkt:</span><span class="sxs-lookup"><span data-stu-id="7a251-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="7a251-545">**Potentieel ongewenste toepassingen (PUA)** worden geblokkeerd</span><span class="sxs-lookup"><span data-stu-id="7a251-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="7a251-546">**Archiefbommen** (bestand met een hoge compressiesnelheid) worden gecontroleerd op Microsoft Defender voor eindpuntlogboeken</span><span class="sxs-lookup"><span data-stu-id="7a251-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="7a251-547">Automatische beveiligingsinformatie-updates inschakelen</span><span class="sxs-lookup"><span data-stu-id="7a251-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="7a251-548">Cloudbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="7a251-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="7a251-549">Automatische voorbeeldinzending inschakelen</span><span class="sxs-lookup"><span data-stu-id="7a251-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="7a251-550">Eigenschappenlijst voor HET CONFIGURATIEprofiel VAN JAMF</span><span class="sxs-lookup"><span data-stu-id="7a251-550">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="7a251-551">Intune-profiel</span><span class="sxs-lookup"><span data-stu-id="7a251-551">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="7a251-552">Voorbeeld van volledig configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="7a251-552">Full configuration profile example</span></span>

<span data-ttu-id="7a251-553">De volgende sjablonen bevatten vermeldingen voor alle instellingen die in dit document worden beschreven en kunnen worden gebruikt voor meer geavanceerde scenario's waarin u meer controle wilt over Microsoft Defender voor Eindpunt in macOS.</span><span class="sxs-lookup"><span data-stu-id="7a251-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="7a251-554">Eigenschappenlijst voor HET CONFIGURATIEprofiel VAN JAMF</span><span class="sxs-lookup"><span data-stu-id="7a251-554">Property list for JAMF configuration profile</span></span>

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
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
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

### <a name="intune-profile"></a><span data-ttu-id="7a251-555">Intune-profiel</span><span class="sxs-lookup"><span data-stu-id="7a251-555">Intune profile</span></span>

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
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
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

## <a name="property-list-validation"></a><span data-ttu-id="7a251-556">Validatie van eigenschappenlijst</span><span class="sxs-lookup"><span data-stu-id="7a251-556">Property list validation</span></span>

<span data-ttu-id="7a251-557">De lijst met eigenschappen moet een geldig *PLIST-bestand* zijn.</span><span class="sxs-lookup"><span data-stu-id="7a251-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="7a251-558">U kunt dit controleren door het volgende uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="7a251-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="7a251-559">Als het bestand goed is gevormd, wordt met de bovenstaande opdracht een exitcode van `OK` `0` .</span><span class="sxs-lookup"><span data-stu-id="7a251-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="7a251-560">Anders wordt een fout weergegeven die het probleem beschrijft en retourneert de opdracht een exitcode van `1` .</span><span class="sxs-lookup"><span data-stu-id="7a251-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="7a251-561">Implementatie van configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="7a251-561">Configuration profile deployment</span></span>

<span data-ttu-id="7a251-562">Nadat u het configuratieprofiel voor uw bedrijf hebt gemaakt, kunt u het implementeren via de beheerconsole die uw bedrijf gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7a251-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="7a251-563">In de volgende secties worden instructies gegeven voor het implementeren van dit profiel met BEHULP van JAMF en Intune.</span><span class="sxs-lookup"><span data-stu-id="7a251-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="7a251-564">JAMF-implementatie</span><span class="sxs-lookup"><span data-stu-id="7a251-564">JAMF deployment</span></span>

<span data-ttu-id="7a251-565">Open in de JAMF-console **De configuratieprofielen** van computers, navigeer naar het configuratieprofiel dat u wilt gebruiken en selecteer vervolgens  >   **Aangepaste Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="7a251-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="7a251-566">Maak een item met `com.microsoft.wdav` als voorkeursdomein en upload de *.plist die* eerder is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7a251-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="7a251-567">U moet het juiste voorkeursdomein invoeren ( ); anders worden de voorkeuren niet herkend `com.microsoft.wdav` door Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="7a251-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="7a251-568">Intune-implementatie</span><span class="sxs-lookup"><span data-stu-id="7a251-568">Intune deployment</span></span>

1. <span data-ttu-id="7a251-569">Open   >  **Apparaatconfiguratie beheren.**</span><span class="sxs-lookup"><span data-stu-id="7a251-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="7a251-570">Selecteer **Profielen beheren**  >  **Profiel**  >  **maken.**</span><span class="sxs-lookup"><span data-stu-id="7a251-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="7a251-571">Kies een naam voor het profiel.</span><span class="sxs-lookup"><span data-stu-id="7a251-571">Choose a name for the profile.</span></span> <span data-ttu-id="7a251-572">**Platform=macOS wijzigen** in **Profieltype=Aangepast**.</span><span class="sxs-lookup"><span data-stu-id="7a251-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="7a251-573">Selecteer Configureren.</span><span class="sxs-lookup"><span data-stu-id="7a251-573">Select Configure.</span></span>

3. <span data-ttu-id="7a251-574">Sla de eerder geproduceerde PLIST op als `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="7a251-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="7a251-575">Voer `com.microsoft.wdav` de naam van het aangepaste **configuratieprofiel in.**</span><span class="sxs-lookup"><span data-stu-id="7a251-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="7a251-576">Open het configuratieprofiel en upload het `com.microsoft.wdav.xml` bestand.</span><span class="sxs-lookup"><span data-stu-id="7a251-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="7a251-577">(Dit bestand is gemaakt in stap 3.)</span><span class="sxs-lookup"><span data-stu-id="7a251-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="7a251-578">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a251-578">Select **OK**.</span></span>

7. <span data-ttu-id="7a251-579">Selecteer **Opdrachten**  >  **beheren.**</span><span class="sxs-lookup"><span data-stu-id="7a251-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="7a251-580">Selecteer op **het** tabblad Opnemen de optie Toewijzen aan **alle & alle apparaten.**</span><span class="sxs-lookup"><span data-stu-id="7a251-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="7a251-581">U moet de juiste naam van het aangepaste configuratieprofiel invoeren. Anders worden deze voorkeuren niet herkend door Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="7a251-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="7a251-582">Resources</span><span class="sxs-lookup"><span data-stu-id="7a251-582">Resources</span></span>

- [<span data-ttu-id="7a251-583">Documentatie over configuratieprofielen (documentatie van Apple voor ontwikkelaars, Engelstalig)</span><span class="sxs-lookup"><span data-stu-id="7a251-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
