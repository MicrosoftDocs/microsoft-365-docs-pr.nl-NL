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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060709"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="ccfbe-104">Voorkeuren instellen voor Microsoft Defender voor Eindpunt voor Mac</span><span class="sxs-lookup"><span data-stu-id="ccfbe-104">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ccfbe-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-105">**Applies to:**</span></span>

- [<span data-ttu-id="ccfbe-106">Microsoft Defender voor Eindpunt voor Mac</span><span class="sxs-lookup"><span data-stu-id="ccfbe-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="ccfbe-107">Dit artikel bevat instructies voor het instellen van voorkeuren voor Microsoft Defender voor Eindpunt voor Mac in bedrijfsorganisaties.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint for Mac in enterprise organizations.</span></span> <span data-ttu-id="ccfbe-108">Zie Resources als u Microsoft Defender voor Eindpunt voor Mac wilt configureren met behulp van de [opdrachtregelinterface.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-108">To configure Microsoft Defender for Endpoint for Mac using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="ccfbe-109">Samenvatting</span><span class="sxs-lookup"><span data-stu-id="ccfbe-109">Summary</span></span>

<span data-ttu-id="ccfbe-110">In ondernemingsorganisaties kan Microsoft Defender voor Eindpunt voor Mac worden beheerd via een configuratieprofiel dat wordt geïmplementeerd met behulp van een van de verschillende beheerhulpmiddelen.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-110">In enterprise organizations, Microsoft Defender for Endpoint for Mac can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="ccfbe-111">Voorkeuren die worden beheerd door uw beveiligingsbewerkingsteam, hebben voorrang op voorkeuren die lokaal op het apparaat zijn ingesteld.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="ccfbe-112">Het wijzigen van de voorkeuren die zijn ingesteld via het configuratieprofiel vereist geëscaleerde bevoegdheden en is niet beschikbaar voor gebruikers zonder beheerdersmachtigingen.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="ccfbe-113">In dit artikel wordt de structuur van het configuratieprofiel beschreven, wordt een aanbevolen profiel beschreven dat u kunt gebruiken om aan de slag te gaan en worden instructies gegeven over het implementeren van het profiel.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="ccfbe-114">Configuratieprofielstructuur</span><span class="sxs-lookup"><span data-stu-id="ccfbe-114">Configuration profile structure</span></span>

<span data-ttu-id="ccfbe-115">Het configuratieprofiel is een *PLIST-bestand* dat bestaat uit items die zijn geïdentificeerd met een sleutel (die de naam van de voorkeur aan duidt), gevolgd door een waarde, die afhankelijk is van de aard van de voorkeur.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="ccfbe-116">Waarden kunnen eenvoudig zijn (zoals een numerieke waarde) of complex, zoals een geneste lijst met voorkeuren.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="ccfbe-117">De indeling van het configuratieprofiel is afhankelijk van de beheerconsole die u gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="ccfbe-118">De volgende secties bevatten voorbeelden van configuratieprofielen voor JAMF en Intune.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="ccfbe-119">Het bovenste niveau van het configuratieprofiel bevat productvoorkeuren en vermeldingen voor subareas van Microsoft Defender voor Eindpunt, die in de volgende secties in meer detail worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="ccfbe-120">Voorkeuren voor antivirusprogramma's</span><span class="sxs-lookup"><span data-stu-id="ccfbe-120">Antivirus engine preferences</span></span>

<span data-ttu-id="ccfbe-121">De *antivirusEngine-sectie* van het configuratieprofiel wordt gebruikt om de voorkeuren van het antivirusonderdeel van Microsoft Defender voor Eindpunt te beheren.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-122">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-123">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-123">**Key**</span></span> | <span data-ttu-id="ccfbe-124">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="ccfbe-124">antivirusEngine</span></span> |
| <span data-ttu-id="ccfbe-125">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-125">**Data type**</span></span> | <span data-ttu-id="ccfbe-126">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ccfbe-127">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-127">**Comments**</span></span> | <span data-ttu-id="ccfbe-128">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-128">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="ccfbe-129">Realtime beveiliging in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-129">Enable / disable real-time protection</span></span>

<span data-ttu-id="ccfbe-130">Geef op of u realtimebeveiliging wilt inschakelen, waarmee bestanden worden gescand wanneer ze worden toegankelijk.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-130">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-131">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-132">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-132">**Key**</span></span> | <span data-ttu-id="ccfbe-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="ccfbe-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="ccfbe-134">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-134">**Data type**</span></span> | <span data-ttu-id="ccfbe-135">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="ccfbe-135">Boolean</span></span> |
| <span data-ttu-id="ccfbe-136">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-136">**Possible values**</span></span> | <span data-ttu-id="ccfbe-137">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-137">true (default)</span></span> <br/> <span data-ttu-id="ccfbe-138">onwaar</span><span class="sxs-lookup"><span data-stu-id="ccfbe-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="ccfbe-139">Passieve modus in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-139">Enable / disable passive mode</span></span>

<span data-ttu-id="ccfbe-140">Geef op of de antivirusprogramma's in de passieve modus worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-140">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="ccfbe-141">De passieve modus heeft de volgende gevolgen:</span><span class="sxs-lookup"><span data-stu-id="ccfbe-141">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="ccfbe-142">Realtimebeveiliging is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="ccfbe-142">Real-time protection is turned off</span></span>
- <span data-ttu-id="ccfbe-143">Scannen op aanvraag is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="ccfbe-143">On-demand scanning is turned on</span></span>
- <span data-ttu-id="ccfbe-144">Automatische herstel van bedreigingen is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="ccfbe-144">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="ccfbe-145">Beveiligingsinformatie-updates zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="ccfbe-145">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="ccfbe-146">Pictogram statusmenu is verborgen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-146">Status menu icon is hidden</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-147">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-147">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-148">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-148">**Key**</span></span> | <span data-ttu-id="ccfbe-149">passiveMode</span><span class="sxs-lookup"><span data-stu-id="ccfbe-149">passiveMode</span></span> |
| <span data-ttu-id="ccfbe-150">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-150">**Data type**</span></span> | <span data-ttu-id="ccfbe-151">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="ccfbe-151">Boolean</span></span> |
| <span data-ttu-id="ccfbe-152">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-152">**Possible values**</span></span> | <span data-ttu-id="ccfbe-153">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-153">false (default)</span></span> <br/> <span data-ttu-id="ccfbe-154">waar</span><span class="sxs-lookup"><span data-stu-id="ccfbe-154">true</span></span> |
| <span data-ttu-id="ccfbe-155">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-155">**Comments**</span></span> | <span data-ttu-id="ccfbe-156">Beschikbaar in Microsoft Defender voor Eindpunt versie 100.67.60 of hoger.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-156">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="ccfbe-157">Beleid voor samenvoeging van uitsluiting</span><span class="sxs-lookup"><span data-stu-id="ccfbe-157">Exclusion merge policy</span></span>

<span data-ttu-id="ccfbe-158">Geef het samenvoegbeleid op voor uitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-158">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="ccfbe-159">Dit kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde uitsluitingen ( ) of alleen `merge` door beheerders gedefinieerde uitsluitingen ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="ccfbe-159">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="ccfbe-160">Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen uitsluitingen definiëren.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-160">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-161">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-161">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-162">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-162">**Key**</span></span> | <span data-ttu-id="ccfbe-163">uitsluitingenMergePolicy</span><span class="sxs-lookup"><span data-stu-id="ccfbe-163">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="ccfbe-164">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-164">**Data type**</span></span> | <span data-ttu-id="ccfbe-165">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-165">String</span></span> |
| <span data-ttu-id="ccfbe-166">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-166">**Possible values**</span></span> | <span data-ttu-id="ccfbe-167">samenvoegen (standaard)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-167">merge (default)</span></span> <br/> <span data-ttu-id="ccfbe-168">admin_only</span><span class="sxs-lookup"><span data-stu-id="ccfbe-168">admin_only</span></span> |
| <span data-ttu-id="ccfbe-169">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-169">**Comments**</span></span> | <span data-ttu-id="ccfbe-170">Beschikbaar in Microsoft Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-170">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="ccfbe-171">Uitsluitingen scannen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-171">Scan exclusions</span></span>

<span data-ttu-id="ccfbe-172">Geef entiteiten op die niet mogen worden gescand.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-172">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="ccfbe-173">Uitsluitingen kunnen worden opgegeven door volledige paden, extensies of bestandsnamen.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-173">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-174">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-174">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-175">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-175">**Key**</span></span> | <span data-ttu-id="ccfbe-176">uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-176">exclusions</span></span> |
| <span data-ttu-id="ccfbe-177">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-177">**Data type**</span></span> | <span data-ttu-id="ccfbe-178">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-178">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ccfbe-179">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-179">**Comments**</span></span> | <span data-ttu-id="ccfbe-180">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-180">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="ccfbe-181">Type uitsluiting</span><span class="sxs-lookup"><span data-stu-id="ccfbe-181">Type of exclusion</span></span>

<span data-ttu-id="ccfbe-182">Geef inhoud op die niet per type kan worden gescand.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-182">Specify content excluded from being scanned by type.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-183">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-184">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-184">**Key**</span></span> | <span data-ttu-id="ccfbe-185">$type</span><span class="sxs-lookup"><span data-stu-id="ccfbe-185">$type</span></span> |
| <span data-ttu-id="ccfbe-186">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-186">**Data type**</span></span> | <span data-ttu-id="ccfbe-187">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-187">String</span></span> |
| <span data-ttu-id="ccfbe-188">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-188">**Possible values**</span></span> | <span data-ttu-id="ccfbe-189">excludedPath</span><span class="sxs-lookup"><span data-stu-id="ccfbe-189">excludedPath</span></span> <br/> <span data-ttu-id="ccfbe-190">uitgeslotenFileExtension</span><span class="sxs-lookup"><span data-stu-id="ccfbe-190">excludedFileExtension</span></span> <br/> <span data-ttu-id="ccfbe-191">uitgeslotenFileName</span><span class="sxs-lookup"><span data-stu-id="ccfbe-191">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="ccfbe-192">Pad naar uitgesloten inhoud</span><span class="sxs-lookup"><span data-stu-id="ccfbe-192">Path to excluded content</span></span>

<span data-ttu-id="ccfbe-193">Geef inhoud op die niet kan worden gescand via een volledig bestandspad.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-193">Specify content excluded from being scanned by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-194">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-195">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-195">**Key**</span></span> | <span data-ttu-id="ccfbe-196">pad</span><span class="sxs-lookup"><span data-stu-id="ccfbe-196">path</span></span> |
| <span data-ttu-id="ccfbe-197">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-197">**Data type**</span></span> | <span data-ttu-id="ccfbe-198">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-198">String</span></span> |
| <span data-ttu-id="ccfbe-199">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-199">**Possible values**</span></span> | <span data-ttu-id="ccfbe-200">geldige paden</span><span class="sxs-lookup"><span data-stu-id="ccfbe-200">valid paths</span></span> |
| <span data-ttu-id="ccfbe-201">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-201">**Comments**</span></span> | <span data-ttu-id="ccfbe-202">Alleen van toepassing *als $type* *is uitgeslotenPath*</span><span class="sxs-lookup"><span data-stu-id="ccfbe-202">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="ccfbe-203">Padtype (bestand /adreslijst)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-203">Path type (file / directory)</span></span>

<span data-ttu-id="ccfbe-204">Geef aan of *de eigenschap pad* verwijst naar een bestand of adreslijst.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-204">Indicate if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="ccfbe-205">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-205">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-206">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-206">**Key**</span></span> | <span data-ttu-id="ccfbe-207">isDirectory</span><span class="sxs-lookup"><span data-stu-id="ccfbe-207">isDirectory</span></span> |
| <span data-ttu-id="ccfbe-208">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-208">**Data type**</span></span> | <span data-ttu-id="ccfbe-209">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="ccfbe-209">Boolean</span></span> |
| <span data-ttu-id="ccfbe-210">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-210">**Possible values**</span></span> | <span data-ttu-id="ccfbe-211">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-211">false (default)</span></span> <br/> <span data-ttu-id="ccfbe-212">waar</span><span class="sxs-lookup"><span data-stu-id="ccfbe-212">true</span></span> |
| <span data-ttu-id="ccfbe-213">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-213">**Comments**</span></span> | <span data-ttu-id="ccfbe-214">Alleen van toepassing *als $type* *is uitgeslotenPath*</span><span class="sxs-lookup"><span data-stu-id="ccfbe-214">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="ccfbe-215">Bestandsextensie uitgesloten van de scan</span><span class="sxs-lookup"><span data-stu-id="ccfbe-215">File extension excluded from the scan</span></span>

<span data-ttu-id="ccfbe-216">Geef inhoud op die niet kan worden gescand door bestandsextensie.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-216">Specify content excluded from being scanned by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-217">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-217">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-218">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-218">**Key**</span></span> | <span data-ttu-id="ccfbe-219">extensie</span><span class="sxs-lookup"><span data-stu-id="ccfbe-219">extension</span></span> |
| <span data-ttu-id="ccfbe-220">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-220">**Data type**</span></span> | <span data-ttu-id="ccfbe-221">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-221">String</span></span> |
| <span data-ttu-id="ccfbe-222">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-222">**Possible values**</span></span> | <span data-ttu-id="ccfbe-223">geldige bestandsextensies</span><span class="sxs-lookup"><span data-stu-id="ccfbe-223">valid file extensions</span></span> |
| <span data-ttu-id="ccfbe-224">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-224">**Comments**</span></span> | <span data-ttu-id="ccfbe-225">Alleen van toepassing *als $type* *is uitgeslotenFileExtension*</span><span class="sxs-lookup"><span data-stu-id="ccfbe-225">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="ccfbe-226">Proces uitgesloten van de scan</span><span class="sxs-lookup"><span data-stu-id="ccfbe-226">Process excluded from the scan</span></span>

<span data-ttu-id="ccfbe-227">Geef een proces op waarvoor alle bestandsactiviteit is uitgesloten van scannen.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-227">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="ccfbe-228">Het proces kan worden opgegeven door de naam (bijvoorbeeld) of het volledige `cat` pad `/bin/cat` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="ccfbe-228">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-229">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-230">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-230">**Key**</span></span> | <span data-ttu-id="ccfbe-231">naam</span><span class="sxs-lookup"><span data-stu-id="ccfbe-231">name</span></span> |
| <span data-ttu-id="ccfbe-232">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-232">**Data type**</span></span> | <span data-ttu-id="ccfbe-233">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-233">String</span></span> |
| <span data-ttu-id="ccfbe-234">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-234">**Possible values**</span></span> | <span data-ttu-id="ccfbe-235">een tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-235">any string</span></span> |
| <span data-ttu-id="ccfbe-236">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-236">**Comments**</span></span> | <span data-ttu-id="ccfbe-237">Alleen van toepassing *als $type* *is uitgeslotenFileName*</span><span class="sxs-lookup"><span data-stu-id="ccfbe-237">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="ccfbe-238">Toegestane bedreigingen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-238">Allowed threats</span></span>

<span data-ttu-id="ccfbe-239">Geef bedreigingen op op naam die niet worden geblokkeerd door Defender voor Eindpunt voor Mac.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-239">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="ccfbe-240">Deze bedreigingen kunnen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-240">These threats will be allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-241">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-241">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-242">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-242">**Key**</span></span> | <span data-ttu-id="ccfbe-243">toegestaanThreats</span><span class="sxs-lookup"><span data-stu-id="ccfbe-243">allowedThreats</span></span> |
| <span data-ttu-id="ccfbe-244">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-244">**Data type**</span></span> | <span data-ttu-id="ccfbe-245">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-245">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="ccfbe-246">Niet-toegestaan bedreigingsacties</span><span class="sxs-lookup"><span data-stu-id="ccfbe-246">Disallowed threat actions</span></span>

<span data-ttu-id="ccfbe-247">Hiermee beperkt u de acties die de lokale gebruiker van een apparaat kan uitvoeren wanneer bedreigingen worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-247">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="ccfbe-248">De acties in deze lijst worden niet weergegeven in de gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-248">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-249">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-250">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-250">**Key**</span></span> | <span data-ttu-id="ccfbe-251">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="ccfbe-251">disallowedThreatActions</span></span> |
| <span data-ttu-id="ccfbe-252">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-252">**Data type**</span></span> | <span data-ttu-id="ccfbe-253">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-253">Array of strings</span></span> |
| <span data-ttu-id="ccfbe-254">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-254">**Possible values**</span></span> | <span data-ttu-id="ccfbe-255">toestaan (gebruikers kunnen geen bedreigingen toestaan)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-255">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="ccfbe-256">herstellen (gebruikers kunnen geen bedreigingen herstellen vanuit de quarantaine)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-256">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="ccfbe-257">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-257">**Comments**</span></span> | <span data-ttu-id="ccfbe-258">Beschikbaar in Microsoft Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-258">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="ccfbe-259">Instellingen voor bedreigingstype</span><span class="sxs-lookup"><span data-stu-id="ccfbe-259">Threat type settings</span></span>

<span data-ttu-id="ccfbe-260">Geef op hoe bepaalde bedreigingstypen worden verwerkt door Microsoft Defender voor Eindpunt voor Mac.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-260">Specify how certain threat types are handled by Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-261">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-261">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-262">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-262">**Key**</span></span> | <span data-ttu-id="ccfbe-263">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="ccfbe-263">threatTypeSettings</span></span> |
| <span data-ttu-id="ccfbe-264">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-264">**Data type**</span></span> | <span data-ttu-id="ccfbe-265">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-265">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ccfbe-266">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-266">**Comments**</span></span> | <span data-ttu-id="ccfbe-267">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-267">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="ccfbe-268">Type bedreiging</span><span class="sxs-lookup"><span data-stu-id="ccfbe-268">Threat type</span></span>

<span data-ttu-id="ccfbe-269">Geef bedreigingstypen op.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-269">Specify threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-270">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-270">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-271">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-271">**Key**</span></span> | <span data-ttu-id="ccfbe-272">toets</span><span class="sxs-lookup"><span data-stu-id="ccfbe-272">key</span></span> |
| <span data-ttu-id="ccfbe-273">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-273">**Data type**</span></span> | <span data-ttu-id="ccfbe-274">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-274">String</span></span> |
| <span data-ttu-id="ccfbe-275">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-275">**Possible values**</span></span> | <span data-ttu-id="ccfbe-276">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="ccfbe-276">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="ccfbe-277">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="ccfbe-277">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="ccfbe-278">Actie ondernemen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-278">Action to take</span></span>

<span data-ttu-id="ccfbe-279">Geef op welke actie moet worden ondernomen wanneer er een bedreiging wordt gedetecteerd van het type dat is opgegeven in de vorige sectie.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-279">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="ccfbe-280">Kies uit de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="ccfbe-280">Choose from the following options:</span></span>

- <span data-ttu-id="ccfbe-281">**Audit:** uw apparaat is niet beveiligd tegen dit type bedreiging, maar er wordt wel een vermelding over de bedreiging geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-281">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="ccfbe-282">**Blokkeren:** uw apparaat is beveiligd tegen dit type bedreiging en u krijgt een melding in de gebruikersinterface en de beveiligingsconsole.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-282">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="ccfbe-283">**Uit:** uw apparaat is niet beveiligd tegen dit type bedreiging en er wordt niets geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-283">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-284">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-284">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-285">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-285">**Key**</span></span> | <span data-ttu-id="ccfbe-286">waarde</span><span class="sxs-lookup"><span data-stu-id="ccfbe-286">value</span></span> |
| <span data-ttu-id="ccfbe-287">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-287">**Data type**</span></span> | <span data-ttu-id="ccfbe-288">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-288">String</span></span> |
| <span data-ttu-id="ccfbe-289">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-289">**Possible values**</span></span> | <span data-ttu-id="ccfbe-290">audit (standaard)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-290">audit (default)</span></span> <br/> <span data-ttu-id="ccfbe-291">blokkering</span><span class="sxs-lookup"><span data-stu-id="ccfbe-291">block</span></span> <br/> <span data-ttu-id="ccfbe-292">uit</span><span class="sxs-lookup"><span data-stu-id="ccfbe-292">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="ccfbe-293">Samenvoegbeleid voor instellingen voor bedreigingstype</span><span class="sxs-lookup"><span data-stu-id="ccfbe-293">Threat type settings merge policy</span></span>

<span data-ttu-id="ccfbe-294">Geef het samenvoegbeleid op voor instellingen voor bedreigingstype.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-294">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="ccfbe-295">Dit kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde instellingen ( `merge` ) of alleen door beheerders gedefinieerde instellingen ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="ccfbe-295">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="ccfbe-296">Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen instellingen voor verschillende bedreigingstypen definiëren.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-296">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-297">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-297">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-298">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-298">**Key**</span></span> | <span data-ttu-id="ccfbe-299">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="ccfbe-299">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="ccfbe-300">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-300">**Data type**</span></span> | <span data-ttu-id="ccfbe-301">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-301">String</span></span> |
| <span data-ttu-id="ccfbe-302">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-302">**Possible values**</span></span> | <span data-ttu-id="ccfbe-303">samenvoegen (standaard)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-303">merge (default)</span></span> <br/> <span data-ttu-id="ccfbe-304">admin_only</span><span class="sxs-lookup"><span data-stu-id="ccfbe-304">admin_only</span></span> |
| <span data-ttu-id="ccfbe-305">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-305">**Comments**</span></span> | <span data-ttu-id="ccfbe-306">Beschikbaar in Microsoft Defender voor Eindpunt versie 100.83.73 of hoger.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-306">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="ccfbe-307">Bewaargeschiedenis van antivirusscans (in dagen)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-307">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="ccfbe-308">Geef het aantal dagen op dat de resultaten worden bewaard in de scangeschiedenis op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-308">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="ccfbe-309">Oude scanresultaten worden uit de geschiedenis verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-309">Old scan results are removed from the history.</span></span> <span data-ttu-id="ccfbe-310">Oude in quarantaine geplaatste bestanden die ook van de schijf zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-310">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-311">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-311">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-312">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-312">**Key**</span></span> | <span data-ttu-id="ccfbe-313">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="ccfbe-313">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="ccfbe-314">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-314">**Data type**</span></span> | <span data-ttu-id="ccfbe-315">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-315">String</span></span> |
| <span data-ttu-id="ccfbe-316">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-316">**Possible values**</span></span> | <span data-ttu-id="ccfbe-317">90 (standaard).</span><span class="sxs-lookup"><span data-stu-id="ccfbe-317">90 (default).</span></span> <span data-ttu-id="ccfbe-318">Toegestane waarden zijn 1 dag tot 180 dagen.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-318">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="ccfbe-319">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-319">**Comments**</span></span> | <span data-ttu-id="ccfbe-320">Beschikbaar in Microsoft Defender voor Eindpunt versie 101.07.23 of hoger.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-320">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="ccfbe-321">Maximum aantal items in de geschiedenis van de antivirusscan</span><span class="sxs-lookup"><span data-stu-id="ccfbe-321">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="ccfbe-322">Geef het maximum aantal items op dat u wilt behouden in de scangeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-322">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="ccfbe-323">Items zijn alle scans op aanvraag die in het verleden zijn uitgevoerd en alle antivirusdetecties.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-323">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-324">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-324">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-325">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-325">**Key**</span></span> | <span data-ttu-id="ccfbe-326">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="ccfbe-326">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="ccfbe-327">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-327">**Data type**</span></span> | <span data-ttu-id="ccfbe-328">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-328">String</span></span> |
| <span data-ttu-id="ccfbe-329">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-329">**Possible values**</span></span> | <span data-ttu-id="ccfbe-330">10000 (standaard).</span><span class="sxs-lookup"><span data-stu-id="ccfbe-330">10000 (default).</span></span> <span data-ttu-id="ccfbe-331">Toegestane waarden zijn van 5000 items tot 15000 items.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-331">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="ccfbe-332">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-332">**Comments**</span></span> | <span data-ttu-id="ccfbe-333">Beschikbaar in Microsoft Defender voor Eindpunt versie 101.07.23 of hoger.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-333">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="ccfbe-334">Beveiligingsvoorkeuren in de cloud</span><span class="sxs-lookup"><span data-stu-id="ccfbe-334">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="ccfbe-335">Configureer de beveiligingsfuncties in de cloud van Microsoft Defender voor Endpoint voor Mac.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-335">Configure the cloud-driven protection features of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-336">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-336">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-337">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-337">**Key**</span></span> | <span data-ttu-id="ccfbe-338">cloudService</span><span class="sxs-lookup"><span data-stu-id="ccfbe-338">cloudService</span></span> |
| <span data-ttu-id="ccfbe-339">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-339">**Data type**</span></span> | <span data-ttu-id="ccfbe-340">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-340">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ccfbe-341">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-341">**Comments**</span></span> | <span data-ttu-id="ccfbe-342">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-342">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="ccfbe-343">Beveiliging via de cloud in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-343">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="ccfbe-344">Geef op of u de beveiliging van het apparaat al dan niet wilt inschakelen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-344">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="ccfbe-345">Als u de beveiliging van uw services wilt verbeteren, raden we u aan deze functie ingeschakeld te houden.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-345">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-346">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-346">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-347">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-347">**Key**</span></span> | <span data-ttu-id="ccfbe-348">ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="ccfbe-348">enabled</span></span> |
| <span data-ttu-id="ccfbe-349">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-349">**Data type**</span></span> | <span data-ttu-id="ccfbe-350">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="ccfbe-350">Boolean</span></span> |
| <span data-ttu-id="ccfbe-351">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-351">**Possible values**</span></span> | <span data-ttu-id="ccfbe-352">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-352">true (default)</span></span> <br/> <span data-ttu-id="ccfbe-353">onwaar</span><span class="sxs-lookup"><span data-stu-id="ccfbe-353">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="ccfbe-354">Diagnostisch verzamelingsniveau</span><span class="sxs-lookup"><span data-stu-id="ccfbe-354">Diagnostic collection level</span></span>

<span data-ttu-id="ccfbe-355">Diagnostische gegevens worden gebruikt om Microsoft Defender voor Eindpunt veilig en up-to-date te houden, problemen op te sporen, te diagnosticeren en op te lossen, en om productverbeteringen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-355">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="ccfbe-356">Deze instelling bepaalt het niveau van de diagnostische gegevens die door Microsoft Defender voor Eindpunt naar Microsoft worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-356">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-357">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-357">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-358">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-358">**Key**</span></span> | <span data-ttu-id="ccfbe-359">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="ccfbe-359">diagnosticLevel</span></span> |
| <span data-ttu-id="ccfbe-360">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-360">**Data type**</span></span> | <span data-ttu-id="ccfbe-361">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-361">String</span></span> |
| <span data-ttu-id="ccfbe-362">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-362">**Possible values**</span></span> | <span data-ttu-id="ccfbe-363">optioneel (standaard)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-363">optional (default)</span></span> <br/> <span data-ttu-id="ccfbe-364">Vereist</span><span class="sxs-lookup"><span data-stu-id="ccfbe-364">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="ccfbe-365">Automatische voorbeeldinzendingen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-365">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="ccfbe-366">Hiermee wordt bepaald of verdachte steekproeven (die waarschijnlijk bedreigingen bevatten) naar Microsoft worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-366">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="ccfbe-367">U wordt gevraagd of het ingediende bestand waarschijnlijk persoonlijke gegevens bevat.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-367">You are prompted if the submitted file is likely to contain personal information.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-368">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-368">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-369">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-369">**Key**</span></span> | <span data-ttu-id="ccfbe-370">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="ccfbe-370">automaticSampleSubmission</span></span> |
| <span data-ttu-id="ccfbe-371">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-371">**Data type**</span></span> | <span data-ttu-id="ccfbe-372">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="ccfbe-372">Boolean</span></span> |
| <span data-ttu-id="ccfbe-373">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-373">**Possible values**</span></span> | <span data-ttu-id="ccfbe-374">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-374">true (default)</span></span> <br/> <span data-ttu-id="ccfbe-375">onwaar</span><span class="sxs-lookup"><span data-stu-id="ccfbe-375">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="ccfbe-376">Automatische beveiligingsinformatie-updates in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-376">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="ccfbe-377">Hiermee bepaalt u of beveiligingsinformatieupdates automatisch worden geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="ccfbe-377">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-378">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-378">**Key**</span></span> | <span data-ttu-id="ccfbe-379">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="ccfbe-379">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="ccfbe-380">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-380">**Data type**</span></span> | <span data-ttu-id="ccfbe-381">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="ccfbe-381">Boolean</span></span> |
| <span data-ttu-id="ccfbe-382">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-382">**Possible values**</span></span> | <span data-ttu-id="ccfbe-383">true (standaard)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-383">true (default)</span></span> <br/> <span data-ttu-id="ccfbe-384">onwaar</span><span class="sxs-lookup"><span data-stu-id="ccfbe-384">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="ccfbe-385">Gebruikersinterfacevoorkeuren</span><span class="sxs-lookup"><span data-stu-id="ccfbe-385">User interface preferences</span></span>

<span data-ttu-id="ccfbe-386">Beheer de voorkeuren voor de gebruikersinterface van Microsoft Defender voor Eindpunt voor Mac.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-386">Manage the preferences for the user interface of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-387">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-387">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-388">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-388">**Key**</span></span> | <span data-ttu-id="ccfbe-389">userInterface</span><span class="sxs-lookup"><span data-stu-id="ccfbe-389">userInterface</span></span> |
| <span data-ttu-id="ccfbe-390">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-390">**Data type**</span></span> | <span data-ttu-id="ccfbe-391">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-391">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ccfbe-392">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-392">**Comments**</span></span> | <span data-ttu-id="ccfbe-393">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-393">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="ccfbe-394">Pictogram statusmenu weergeven/verbergen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-394">Show / hide status menu icon</span></span>

<span data-ttu-id="ccfbe-395">Geef op of u het statusmenupictogram wilt weergeven of verbergen in de rechterbovenhoek van het scherm.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-395">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-396">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-396">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-397">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-397">**Key**</span></span> | <span data-ttu-id="ccfbe-398">StatusMenuIcon verbergen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-398">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="ccfbe-399">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-399">**Data type**</span></span> | <span data-ttu-id="ccfbe-400">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="ccfbe-400">Boolean</span></span> |
| <span data-ttu-id="ccfbe-401">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-401">**Possible values**</span></span> | <span data-ttu-id="ccfbe-402">onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-402">false (default)</span></span> <br/> <span data-ttu-id="ccfbe-403">waar</span><span class="sxs-lookup"><span data-stu-id="ccfbe-403">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="ccfbe-404">Optie weergeven/verbergen om feedback te verzenden</span><span class="sxs-lookup"><span data-stu-id="ccfbe-404">Show / hide option to send feedback</span></span>

<span data-ttu-id="ccfbe-405">Geef op of gebruikers feedback kunnen verzenden naar Microsoft door naar `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="ccfbe-405">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-406">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-406">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-407">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-407">**Key**</span></span> | <span data-ttu-id="ccfbe-408">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="ccfbe-408">userInitiatedFeedback</span></span> |
| <span data-ttu-id="ccfbe-409">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-409">**Data type**</span></span> | <span data-ttu-id="ccfbe-410">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-410">String</span></span> |
| <span data-ttu-id="ccfbe-411">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-411">**Possible values**</span></span> | <span data-ttu-id="ccfbe-412">ingeschakeld (standaard)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-412">enabled (default)</span></span> <br/> <span data-ttu-id="ccfbe-413">uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="ccfbe-413">disabled</span></span> |
| <span data-ttu-id="ccfbe-414">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-414">**Comments**</span></span> | <span data-ttu-id="ccfbe-415">Beschikbaar in Microsoft Defender voor Eindpunt versie 101.19.61 of hoger.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-415">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="ccfbe-416">Eindpuntdetectie- en antwoordvoorkeuren</span><span class="sxs-lookup"><span data-stu-id="ccfbe-416">Endpoint detection and response preferences</span></span>

<span data-ttu-id="ccfbe-417">Beheer de voorkeuren van het onderdeel eindpuntdetectie en -antwoord (EDR) van Microsoft Defender voor Eindpunt voor Mac.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-417">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-418">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-418">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-419">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-419">**Key**</span></span> | <span data-ttu-id="ccfbe-420">edr</span><span class="sxs-lookup"><span data-stu-id="ccfbe-420">edr</span></span> |
| <span data-ttu-id="ccfbe-421">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-421">**Data type**</span></span> | <span data-ttu-id="ccfbe-422">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-422">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ccfbe-423">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-423">**Comments**</span></span> | <span data-ttu-id="ccfbe-424">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-424">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="ccfbe-425">Apparaatlabels</span><span class="sxs-lookup"><span data-stu-id="ccfbe-425">Device tags</span></span>

<span data-ttu-id="ccfbe-426">Geef een tagnaam en de waarde op.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-426">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="ccfbe-427">Met de tag GROEP wordt het apparaat gelabeld met de opgegeven waarde.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-427">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="ccfbe-428">De tag wordt weergegeven in de portal onder de apparaatpagina en kan worden gebruikt voor het filteren en groeperen van apparaten.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-428">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-429">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-429">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-430">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-430">**Key**</span></span> | <span data-ttu-id="ccfbe-431">tags</span><span class="sxs-lookup"><span data-stu-id="ccfbe-431">tags</span></span> |
| <span data-ttu-id="ccfbe-432">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-432">**Data type**</span></span> | <span data-ttu-id="ccfbe-433">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-433">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ccfbe-434">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-434">**Comments**</span></span> | <span data-ttu-id="ccfbe-435">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-435">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="ccfbe-436">Type tag</span><span class="sxs-lookup"><span data-stu-id="ccfbe-436">Type of tag</span></span>

<span data-ttu-id="ccfbe-437">Geeft het type tag op</span><span class="sxs-lookup"><span data-stu-id="ccfbe-437">Specifies the type of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-438">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-438">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-439">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-439">**Key**</span></span> | <span data-ttu-id="ccfbe-440">toets</span><span class="sxs-lookup"><span data-stu-id="ccfbe-440">key</span></span> |
| <span data-ttu-id="ccfbe-441">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-441">**Data type**</span></span> | <span data-ttu-id="ccfbe-442">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-442">String</span></span> |
| <span data-ttu-id="ccfbe-443">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-443">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="ccfbe-444">Waarde van tag</span><span class="sxs-lookup"><span data-stu-id="ccfbe-444">Value of tag</span></span>

<span data-ttu-id="ccfbe-445">Geeft de waarde van de tag op</span><span class="sxs-lookup"><span data-stu-id="ccfbe-445">Specifies the value of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccfbe-446">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccfbe-447">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-447">**Key**</span></span> | <span data-ttu-id="ccfbe-448">waarde</span><span class="sxs-lookup"><span data-stu-id="ccfbe-448">value</span></span> |
| <span data-ttu-id="ccfbe-449">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-449">**Data type**</span></span> | <span data-ttu-id="ccfbe-450">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-450">String</span></span> |
| <span data-ttu-id="ccfbe-451">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-451">**Possible values**</span></span> | <span data-ttu-id="ccfbe-452">een tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ccfbe-452">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="ccfbe-453">Er kan slechts één waarde per tagtype worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-453">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="ccfbe-454">Het type tags is uniek en mag niet worden herhaald in hetzelfde configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-454">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="ccfbe-455">Aanbevolen configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="ccfbe-455">Recommended configuration profile</span></span>

<span data-ttu-id="ccfbe-456">Om aan de slag te gaan, wordt u aangeraden de volgende configuratie voor uw bedrijf te gebruiken om te profiteren van alle beveiligingsfuncties die Microsoft Defender voor Eindpunt biedt.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-456">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="ccfbe-457">Het volgende configuratieprofiel (of, in het geval van JAMF, een eigenschappenlijst die kan worden geüpload naar het configuratieprofiel voor aangepaste instellingen) wordt als volgt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ccfbe-457">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="ccfbe-458">Realtimebeveiliging inschakelen (RTP)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-458">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="ccfbe-459">Geef op hoe de volgende bedreigingstypen worden verwerkt:</span><span class="sxs-lookup"><span data-stu-id="ccfbe-459">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="ccfbe-460">**Potentieel ongewenste toepassingen (PUA)** worden geblokkeerd</span><span class="sxs-lookup"><span data-stu-id="ccfbe-460">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="ccfbe-461">**Archiefbommen** (bestand met een hoge compressiesnelheid) worden gecontroleerd op Microsoft Defender voor eindpuntlogboeken</span><span class="sxs-lookup"><span data-stu-id="ccfbe-461">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="ccfbe-462">Automatische beveiligingsinformatie-updates inschakelen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-462">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="ccfbe-463">Beveiliging via de cloud inschakelen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-463">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="ccfbe-464">Automatische voorbeeldinzending inschakelen</span><span class="sxs-lookup"><span data-stu-id="ccfbe-464">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="ccfbe-465">Eigenschappenlijst voor HET CONFIGURATIEprofiel VAN JAMF</span><span class="sxs-lookup"><span data-stu-id="ccfbe-465">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="ccfbe-466">Intune-profiel</span><span class="sxs-lookup"><span data-stu-id="ccfbe-466">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="ccfbe-467">Voorbeeld van volledig configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="ccfbe-467">Full configuration profile example</span></span>

<span data-ttu-id="ccfbe-468">De volgende sjablonen bevatten vermeldingen voor alle instellingen die in dit document worden beschreven en kunnen worden gebruikt voor meer geavanceerde scenario's waarin u meer controle wilt over Microsoft Defender voor Eindpunt voor Mac.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-468">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="ccfbe-469">Eigenschappenlijst voor HET CONFIGURATIEprofiel VAN JAMF</span><span class="sxs-lookup"><span data-stu-id="ccfbe-469">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="ccfbe-470">Intune-profiel</span><span class="sxs-lookup"><span data-stu-id="ccfbe-470">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="ccfbe-471">Validatie van eigenschappenlijst</span><span class="sxs-lookup"><span data-stu-id="ccfbe-471">Property list validation</span></span>

<span data-ttu-id="ccfbe-472">De lijst met eigenschappen moet een geldig *PLIST-bestand* zijn.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-472">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="ccfbe-473">U kunt dit controleren door het volgende uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="ccfbe-473">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="ccfbe-474">Als het bestand goed is gevormd, wordt met de bovenstaande opdracht een exitcode van `OK` `0` .</span><span class="sxs-lookup"><span data-stu-id="ccfbe-474">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="ccfbe-475">Anders wordt een fout weergegeven die het probleem beschrijft en retourneert de opdracht een exitcode van `1` .</span><span class="sxs-lookup"><span data-stu-id="ccfbe-475">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="ccfbe-476">Implementatie van configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="ccfbe-476">Configuration profile deployment</span></span>

<span data-ttu-id="ccfbe-477">Nadat u het configuratieprofiel voor uw bedrijf hebt gemaakt, kunt u het implementeren via de beheerconsole die uw bedrijf gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-477">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="ccfbe-478">In de volgende secties worden instructies gegeven voor het implementeren van dit profiel met BEHULP van JAMF en Intune.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-478">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="ccfbe-479">JAMF-implementatie</span><span class="sxs-lookup"><span data-stu-id="ccfbe-479">JAMF deployment</span></span>

<span data-ttu-id="ccfbe-480">Open in de JAMF-console **De configuratieprofielen van computers,** ga naar het configuratieprofiel dat u wilt gebruiken  >  en selecteer vervolgens **Aangepaste instellingen.**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-480">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="ccfbe-481">Maak een item met `com.microsoft.wdav` als voorkeursdomein en upload de *.plist die* eerder is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-481">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="ccfbe-482">U moet het juiste voorkeursdomein invoeren ( ); anders worden de voorkeuren niet herkend `com.microsoft.wdav` door Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-482">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="ccfbe-483">Intune-implementatie</span><span class="sxs-lookup"><span data-stu-id="ccfbe-483">Intune deployment</span></span>

1. <span data-ttu-id="ccfbe-484">Open   >  **Apparaatconfiguratie beheren.**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-484">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="ccfbe-485">Selecteer **Profielen beheren**  >  **Profiel**  >  **maken.**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-485">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="ccfbe-486">Kies een naam voor het profiel.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-486">Choose a name for the profile.</span></span> <span data-ttu-id="ccfbe-487">**Platform=macOS wijzigen** in **Profieltype=Aangepast**.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-487">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="ccfbe-488">Selecteer Configureren.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-488">Select Configure.</span></span>

3. <span data-ttu-id="ccfbe-489">Sla de eerder geproduceerde PLIST op als `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="ccfbe-489">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="ccfbe-490">Voer `com.microsoft.wdav` de naam van het aangepaste **configuratieprofiel in.**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-490">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="ccfbe-491">Open het configuratieprofiel en upload het `com.microsoft.wdav.xml` bestand.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-491">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="ccfbe-492">(Dit bestand is gemaakt in stap 3.)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-492">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="ccfbe-493">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-493">Select **OK**.</span></span>

7. <span data-ttu-id="ccfbe-494">Selecteer **Opdrachten**  >  **beheren.**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-494">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="ccfbe-495">Selecteer op **het** tabblad Opnemen de optie Toewijzen aan **alle & alle apparaten.**</span><span class="sxs-lookup"><span data-stu-id="ccfbe-495">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="ccfbe-496">U moet de juiste naam van het aangepaste configuratieprofiel invoeren. Anders worden deze voorkeuren niet herkend door Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-496">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="ccfbe-497">Resources</span><span class="sxs-lookup"><span data-stu-id="ccfbe-497">Resources</span></span>

- [<span data-ttu-id="ccfbe-498">Documentatie over configuratieprofielen (documentatie van Apple voor ontwikkelaars, Engelstalig)</span><span class="sxs-lookup"><span data-stu-id="ccfbe-498">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
