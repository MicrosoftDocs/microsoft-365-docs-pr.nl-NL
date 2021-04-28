---
title: Alle herstelactiviteiten op een lijst zetten
description: Retourneert informatie over alle herstelactiviteiten.
keywords: api's, herstel, herstel-api, get, hersteltaken,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061129"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="4ea22-104">Alle herstelactiviteiten op een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="4ea22-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4ea22-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4ea22-105">**Applies to:**</span></span>

- [<span data-ttu-id="4ea22-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4ea22-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4ea22-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ea22-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4ea22-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4ea22-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4ea22-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4ea22-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="4ea22-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="4ea22-110">API description</span></span>

<span data-ttu-id="4ea22-111">Retourneert informatie over alle herstelactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="4ea22-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="4ea22-112">[Meer informatie over herstelactiviteiten.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="4ea22-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="4ea22-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="4ea22-113">**URL:** GET: /api/remediationTasks</span></span>

<span data-ttu-id="4ea22-114">**Eigenschappendetails**</span><span class="sxs-lookup"><span data-stu-id="4ea22-114">**Properties** details</span></span>

<span data-ttu-id="4ea22-115">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="4ea22-115">Property (id)</span></span> | <span data-ttu-id="4ea22-116">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="4ea22-116">Data type</span></span> | <span data-ttu-id="4ea22-117">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="4ea22-117">Description</span></span> | <span data-ttu-id="4ea22-118">Voorbeeld van een geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="4ea22-118">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="4ea22-119">categorie</span><span class="sxs-lookup"><span data-stu-id="4ea22-119">category</span></span> | <span data-ttu-id="4ea22-120">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-120">String</span></span> | <span data-ttu-id="4ea22-121">Categorie van de herstelactiviteit (software-/beveiligingsconfiguratie)</span><span class="sxs-lookup"><span data-stu-id="4ea22-121">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="4ea22-122">Software</span><span class="sxs-lookup"><span data-stu-id="4ea22-122">Software</span></span>
<span data-ttu-id="4ea22-123">completerEmail</span><span class="sxs-lookup"><span data-stu-id="4ea22-123">completerEmail</span></span> | <span data-ttu-id="4ea22-124">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-124">String</span></span> | <span data-ttu-id="4ea22-125">Als de herstelactiviteit handmatig is voltooid door iemand, bevat deze kolom zijn of haar e-mail</span><span class="sxs-lookup"><span data-stu-id="4ea22-125">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="4ea22-126">null</span><span class="sxs-lookup"><span data-stu-id="4ea22-126">null</span></span>
<span data-ttu-id="4ea22-127">completerId</span><span class="sxs-lookup"><span data-stu-id="4ea22-127">completerId</span></span> | <span data-ttu-id="4ea22-128">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-128">String</span></span> | <span data-ttu-id="4ea22-129">Als de herstelactiviteit handmatig is voltooid door iemand, bevat deze kolom de object-id</span><span class="sxs-lookup"><span data-stu-id="4ea22-129">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="4ea22-130">null</span><span class="sxs-lookup"><span data-stu-id="4ea22-130">null</span></span>
<span data-ttu-id="4ea22-131">completionMethod</span><span class="sxs-lookup"><span data-stu-id="4ea22-131">completionMethod</span></span> | <span data-ttu-id="4ea22-132">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-132">String</span></span> | <span data-ttu-id="4ea22-133">Een herstelactiviteit kan 'automatisch' worden voltooid (als alle apparaten zijn gepatcht) of 'handmatig' door een persoon die 'markeren als voltooid' selecteert.</span><span class="sxs-lookup"><span data-stu-id="4ea22-133">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="4ea22-134">Automatisch</span><span class="sxs-lookup"><span data-stu-id="4ea22-134">Automatic</span></span>
<span data-ttu-id="4ea22-135">gemaaktOn</span><span class="sxs-lookup"><span data-stu-id="4ea22-135">createdOn</span></span> | <span data-ttu-id="4ea22-136">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ea22-136">DateTime</span></span> | <span data-ttu-id="4ea22-137">Tijd dat deze herstelactiviteit is gemaakt</span><span class="sxs-lookup"><span data-stu-id="4ea22-137">Time this remediation activity was created</span></span> | <span data-ttu-id="4ea22-138">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="4ea22-138">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="4ea22-139">beschrijving</span><span class="sxs-lookup"><span data-stu-id="4ea22-139">description</span></span> | <span data-ttu-id="4ea22-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-140">String</span></span> | <span data-ttu-id="4ea22-141">Beschrijving van deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="4ea22-141">Description of this remediation activity</span></span> | <span data-ttu-id="4ea22-142">Werk Chrome bij naar een nieuwere versie om 1248 bekende beveiligingslekken op uw apparaten te beperken.</span><span class="sxs-lookup"><span data-stu-id="4ea22-142">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="4ea22-143">dueOn</span><span class="sxs-lookup"><span data-stu-id="4ea22-143">dueOn</span></span> | <span data-ttu-id="4ea22-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ea22-144">DateTime</span></span> | <span data-ttu-id="4ea22-145">Einddatum die de maker heeft ingesteld voor deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="4ea22-145">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="4ea22-146">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="4ea22-146">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="4ea22-147">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="4ea22-147">fixedDevices</span></span> | <span data-ttu-id="4ea22-148">.</span><span class="sxs-lookup"><span data-stu-id="4ea22-148">.</span></span> | <span data-ttu-id="4ea22-149">Het aantal apparaten dat is opgelost</span><span class="sxs-lookup"><span data-stu-id="4ea22-149">The number of devices that have been fixed</span></span> | <span data-ttu-id="4ea22-150">2</span><span class="sxs-lookup"><span data-stu-id="4ea22-150">2</span></span>
<span data-ttu-id="4ea22-151">id</span><span class="sxs-lookup"><span data-stu-id="4ea22-151">id</span></span> | <span data-ttu-id="4ea22-152">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-152">String</span></span> | <span data-ttu-id="4ea22-153">Id van deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="4ea22-153">ID of this remediation activity</span></span> | <span data-ttu-id="4ea22-154">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="4ea22-154">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="4ea22-155">nameId</span><span class="sxs-lookup"><span data-stu-id="4ea22-155">nameId</span></span> | <span data-ttu-id="4ea22-156">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-156">String</span></span> | <span data-ttu-id="4ea22-157">Verwante productnaam</span><span class="sxs-lookup"><span data-stu-id="4ea22-157">Related product name</span></span> | <span data-ttu-id="4ea22-158">chrome</span><span class="sxs-lookup"><span data-stu-id="4ea22-158">chrome</span></span>
<span data-ttu-id="4ea22-159">prioriteit</span><span class="sxs-lookup"><span data-stu-id="4ea22-159">priority</span></span> | <span data-ttu-id="4ea22-160">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-160">String</span></span> | <span data-ttu-id="4ea22-161">Prioriteit die de maker heeft ingesteld voor deze herstelactiviteit (Hoog\Gemiddeld\Laag)</span><span class="sxs-lookup"><span data-stu-id="4ea22-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="4ea22-162">Hoog</span><span class="sxs-lookup"><span data-stu-id="4ea22-162">High</span></span>
<span data-ttu-id="4ea22-163">productId</span><span class="sxs-lookup"><span data-stu-id="4ea22-163">productId</span></span> | <span data-ttu-id="4ea22-164">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-164">String</span></span> | <span data-ttu-id="4ea22-165">Gerelateerde product-id</span><span class="sxs-lookup"><span data-stu-id="4ea22-165">Related product ID</span></span> | <span data-ttu-id="4ea22-166">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="4ea22-166">google-_-chrome</span></span>
<span data-ttu-id="4ea22-167">productiviteitImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="4ea22-167">productivityImpactRemediationType</span></span> | <span data-ttu-id="4ea22-168">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-168">String</span></span> | <span data-ttu-id="4ea22-169">Er kunnen alleen enkele configuratiewijzigingen worden aangevraagd voor apparaten zonder dat dit gevolgen heeft voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="4ea22-169">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="4ea22-170">Deze waarde geeft de selectie aan tussen 'alle blootgestelde apparaten' of 'alleen apparaten zonder invloed van de gebruiker'.</span><span class="sxs-lookup"><span data-stu-id="4ea22-170">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="4ea22-171">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="4ea22-171">AllExposedAssets</span></span>
<span data-ttu-id="4ea22-172">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="4ea22-172">rbacGroupNames</span></span> | <span data-ttu-id="4ea22-173">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-173">String</span></span> | <span data-ttu-id="4ea22-174">Namen van gerelateerde apparaatgroep</span><span class="sxs-lookup"><span data-stu-id="4ea22-174">Related device group names</span></span> | <span data-ttu-id="4ea22-175">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="4ea22-175">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="4ea22-176">aanbevolenProgram</span><span class="sxs-lookup"><span data-stu-id="4ea22-176">recommendedProgram</span></span> | <span data-ttu-id="4ea22-177">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-177">String</span></span> | <span data-ttu-id="4ea22-178">Aanbevolen programma om een upgrade uit te voeren naar</span><span class="sxs-lookup"><span data-stu-id="4ea22-178">Recommended program to upgrade to</span></span> | <span data-ttu-id="4ea22-179">null</span><span class="sxs-lookup"><span data-stu-id="4ea22-179">null</span></span>
<span data-ttu-id="4ea22-180">aanbevolenVendor</span><span class="sxs-lookup"><span data-stu-id="4ea22-180">recommendedVendor</span></span> | <span data-ttu-id="4ea22-181">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-181">String</span></span> | <span data-ttu-id="4ea22-182">Aanbevolen leverancier om een upgrade uit te voeren naar</span><span class="sxs-lookup"><span data-stu-id="4ea22-182">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="4ea22-183">null</span><span class="sxs-lookup"><span data-stu-id="4ea22-183">null</span></span>
<span data-ttu-id="4ea22-184">aanbevolenVersie</span><span class="sxs-lookup"><span data-stu-id="4ea22-184">recommendedVersion</span></span> | <span data-ttu-id="4ea22-185">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-185">String</span></span> | <span data-ttu-id="4ea22-186">Aanbevolen versie om bij te werken/upgraden naar</span><span class="sxs-lookup"><span data-stu-id="4ea22-186">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="4ea22-187">null</span><span class="sxs-lookup"><span data-stu-id="4ea22-187">null</span></span>
<span data-ttu-id="4ea22-188">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="4ea22-188">relatedComponent</span></span> | <span data-ttu-id="4ea22-189">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-189">String</span></span> | <span data-ttu-id="4ea22-190">Gerelateerd onderdeel van deze herstelactiviteit (vergelijkbaar met het gerelateerde onderdeel voor een beveiligingsaanbeveling)</span><span class="sxs-lookup"><span data-stu-id="4ea22-190">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="4ea22-191">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="4ea22-191">Google Chrome</span></span>
<span data-ttu-id="4ea22-192">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="4ea22-192">requesterEmail</span></span> | <span data-ttu-id="4ea22-193">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-193">String</span></span> | <span data-ttu-id="4ea22-194">E-mailadres maker</span><span class="sxs-lookup"><span data-stu-id="4ea22-194">Creator email address</span></span> | <span data-ttu-id="4ea22-195">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4ea22-195">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="4ea22-196">requesterId</span><span class="sxs-lookup"><span data-stu-id="4ea22-196">requesterId</span></span> | <span data-ttu-id="4ea22-197">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-197">String</span></span> | <span data-ttu-id="4ea22-198">Creator-object-id</span><span class="sxs-lookup"><span data-stu-id="4ea22-198">Creator object id</span></span> | <span data-ttu-id="4ea22-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="4ea22-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="4ea22-200">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="4ea22-200">requesterNotes</span></span> | <span data-ttu-id="4ea22-201">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-201">String</span></span> | <span data-ttu-id="4ea22-202">De notities (vrije tekst) die de maker heeft toegevoegd voor deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="4ea22-202">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="4ea22-203">null</span><span class="sxs-lookup"><span data-stu-id="4ea22-203">null</span></span>
<span data-ttu-id="4ea22-204">scid</span><span class="sxs-lookup"><span data-stu-id="4ea22-204">scid</span></span> | <span data-ttu-id="4ea22-205">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-205">String</span></span> | <span data-ttu-id="4ea22-206">SCID van de gerelateerde beveiligingsaanbeveling</span><span class="sxs-lookup"><span data-stu-id="4ea22-206">SCID of the related security recommendation</span></span> | <span data-ttu-id="4ea22-207">null</span><span class="sxs-lookup"><span data-stu-id="4ea22-207">null</span></span>
<span data-ttu-id="4ea22-208">status</span><span class="sxs-lookup"><span data-stu-id="4ea22-208">status</span></span> | <span data-ttu-id="4ea22-209">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-209">String</span></span> | <span data-ttu-id="4ea22-210">Status van herstelactiviteit (actief/voltooid)</span><span class="sxs-lookup"><span data-stu-id="4ea22-210">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="4ea22-211">Actief</span><span class="sxs-lookup"><span data-stu-id="4ea22-211">Active</span></span>
<span data-ttu-id="4ea22-212">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="4ea22-212">statusLastModifiedOn</span></span> | <span data-ttu-id="4ea22-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ea22-213">DateTime</span></span> | <span data-ttu-id="4ea22-214">Datum waarop het statusveld is bijgewerkt</span><span class="sxs-lookup"><span data-stu-id="4ea22-214">Date when the status field was updated</span></span> | <span data-ttu-id="4ea22-215">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="4ea22-215">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="4ea22-216">targetDevices</span><span class="sxs-lookup"><span data-stu-id="4ea22-216">targetDevices</span></span> | <span data-ttu-id="4ea22-217">Lang</span><span class="sxs-lookup"><span data-stu-id="4ea22-217">Long</span></span> | <span data-ttu-id="4ea22-218">Het aantal blootgestelde apparaten dat door deze herstel wordt toegepast op</span><span class="sxs-lookup"><span data-stu-id="4ea22-218">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="4ea22-219">43</span><span class="sxs-lookup"><span data-stu-id="4ea22-219">43</span></span>
<span data-ttu-id="4ea22-220">titel</span><span class="sxs-lookup"><span data-stu-id="4ea22-220">title</span></span> | <span data-ttu-id="4ea22-221">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-221">String</span></span> | <span data-ttu-id="4ea22-222">Titel van deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="4ea22-222">Title of this remediation activity</span></span> | <span data-ttu-id="4ea22-223">Google Chrome bijwerken</span><span class="sxs-lookup"><span data-stu-id="4ea22-223">Update Google Chrome</span></span>
<span data-ttu-id="4ea22-224">type</span><span class="sxs-lookup"><span data-stu-id="4ea22-224">type</span></span> | <span data-ttu-id="4ea22-225">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-225">String</span></span> | <span data-ttu-id="4ea22-226">Hersteltype</span><span class="sxs-lookup"><span data-stu-id="4ea22-226">Remediation type</span></span> | <span data-ttu-id="4ea22-227">Update</span><span class="sxs-lookup"><span data-stu-id="4ea22-227">Update</span></span>
<span data-ttu-id="4ea22-228">vendorId</span><span class="sxs-lookup"><span data-stu-id="4ea22-228">vendorId</span></span> | <span data-ttu-id="4ea22-229">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ea22-229">String</span></span> | <span data-ttu-id="4ea22-230">Naam van gerelateerde leverancier</span><span class="sxs-lookup"><span data-stu-id="4ea22-230">Related vendor name</span></span> | <span data-ttu-id="4ea22-231">google</span><span class="sxs-lookup"><span data-stu-id="4ea22-231">google</span></span>

## <a name="example"></a><span data-ttu-id="4ea22-232">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="4ea22-232">Example</span></span>

<span data-ttu-id="4ea22-233">**Voorbeeld aanvragen**</span><span class="sxs-lookup"><span data-stu-id="4ea22-233">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

<span data-ttu-id="4ea22-234">**Voorbeeld van** antwoord</span><span class="sxs-lookup"><span data-stu-id="4ea22-234">**Response** example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="4ea22-235">Zie ook</span><span class="sxs-lookup"><span data-stu-id="4ea22-235">See also</span></span>

- [<span data-ttu-id="4ea22-236">Herstelmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="4ea22-236">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="4ea22-237">Eén herstelactiviteit per id</span><span class="sxs-lookup"><span data-stu-id="4ea22-237">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="4ea22-238">Belichte apparaten van één herstelactiviteit op de lijst</span><span class="sxs-lookup"><span data-stu-id="4ea22-238">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="4ea22-239">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="4ea22-239">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="4ea22-240">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="4ea22-240">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
