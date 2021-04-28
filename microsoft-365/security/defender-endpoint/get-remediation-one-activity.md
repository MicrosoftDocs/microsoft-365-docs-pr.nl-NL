---
title: Eén herstelactiviteit per id
description: Retourneert gegevens voor de opgegeven herstelactiviteit.
keywords: api's, herstel, herstel-api, get, hersteltaken, lijst
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
ms.openlocfilehash: 40a7102a8c7dbf63641daaf47bbd9aa9f2e54649
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061130"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="1791a-104">Eén herstelactiviteit per id</span><span class="sxs-lookup"><span data-stu-id="1791a-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1791a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1791a-105">**Applies to:**</span></span>

- [<span data-ttu-id="1791a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1791a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1791a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1791a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1791a-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="1791a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1791a-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="1791a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="1791a-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="1791a-110">API description</span></span>

<span data-ttu-id="1791a-111">Retourneert gegevens voor de opgegeven herstelactiviteit.</span><span class="sxs-lookup"><span data-stu-id="1791a-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="1791a-112">Geeft dezelfde kolommen weer als [Alle herstelactiviteit](get-remediation-all-activities.md)', maar geeft alleen resultaten als resultaat voor de opgegeven _herstelactiviteit._</span><span class="sxs-lookup"><span data-stu-id="1791a-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="1791a-113">[Meer informatie over herstelactiviteiten.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="1791a-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="1791a-114">Een opgegeven herstelactiviteit voor (id)</span><span class="sxs-lookup"><span data-stu-id="1791a-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="1791a-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="1791a-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

<span data-ttu-id="1791a-116">**Eigenschappendetails**</span><span class="sxs-lookup"><span data-stu-id="1791a-116">**Properties** details</span></span>

<span data-ttu-id="1791a-117">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="1791a-117">Property (id)</span></span> | <span data-ttu-id="1791a-118">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="1791a-118">Data type</span></span> | <span data-ttu-id="1791a-119">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="1791a-119">Description</span></span> | <span data-ttu-id="1791a-120">Voorbeeld van een geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="1791a-120">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="1791a-121">categorie</span><span class="sxs-lookup"><span data-stu-id="1791a-121">category</span></span> | <span data-ttu-id="1791a-122">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-122">String</span></span> | <span data-ttu-id="1791a-123">Categorie van de herstelactiviteit (software-/beveiligingsconfiguratie)</span><span class="sxs-lookup"><span data-stu-id="1791a-123">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="1791a-124">Software</span><span class="sxs-lookup"><span data-stu-id="1791a-124">Software</span></span>
<span data-ttu-id="1791a-125">completerEmail</span><span class="sxs-lookup"><span data-stu-id="1791a-125">completerEmail</span></span> | <span data-ttu-id="1791a-126">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-126">String</span></span> | <span data-ttu-id="1791a-127">Als de herstelactiviteit handmatig is voltooid door iemand, bevat deze kolom zijn of haar e-mail</span><span class="sxs-lookup"><span data-stu-id="1791a-127">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="1791a-128">null</span><span class="sxs-lookup"><span data-stu-id="1791a-128">null</span></span>
<span data-ttu-id="1791a-129">completerId</span><span class="sxs-lookup"><span data-stu-id="1791a-129">completerId</span></span> | <span data-ttu-id="1791a-130">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-130">String</span></span> | <span data-ttu-id="1791a-131">Als de herstelactiviteit handmatig is voltooid door iemand, bevat deze kolom de object-id</span><span class="sxs-lookup"><span data-stu-id="1791a-131">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="1791a-132">null</span><span class="sxs-lookup"><span data-stu-id="1791a-132">null</span></span>
<span data-ttu-id="1791a-133">completionMethod</span><span class="sxs-lookup"><span data-stu-id="1791a-133">completionMethod</span></span> | <span data-ttu-id="1791a-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-134">String</span></span> | <span data-ttu-id="1791a-135">Een herstelactiviteit kan 'automatisch' worden voltooid (als alle apparaten zijn gepatcht) of 'handmatig' door een persoon die 'markeren als voltooid' selecteert.</span><span class="sxs-lookup"><span data-stu-id="1791a-135">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="1791a-136">Automatisch</span><span class="sxs-lookup"><span data-stu-id="1791a-136">Automatic</span></span>
<span data-ttu-id="1791a-137">gemaaktOn</span><span class="sxs-lookup"><span data-stu-id="1791a-137">createdOn</span></span> | <span data-ttu-id="1791a-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="1791a-138">DateTime</span></span> | <span data-ttu-id="1791a-139">Tijd dat deze herstelactiviteit is gemaakt</span><span class="sxs-lookup"><span data-stu-id="1791a-139">Time this remediation activity was created</span></span> | <span data-ttu-id="1791a-140">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="1791a-140">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="1791a-141">beschrijving</span><span class="sxs-lookup"><span data-stu-id="1791a-141">description</span></span> | <span data-ttu-id="1791a-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-142">String</span></span> | <span data-ttu-id="1791a-143">Beschrijving van deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="1791a-143">Description of this remediation activity</span></span> | <span data-ttu-id="1791a-144">Werk Chrome bij naar een nieuwere versie om 1248 bekende beveiligingslekken op uw apparaten te beperken.</span><span class="sxs-lookup"><span data-stu-id="1791a-144">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="1791a-145">dueOn</span><span class="sxs-lookup"><span data-stu-id="1791a-145">dueOn</span></span> | <span data-ttu-id="1791a-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="1791a-146">DateTime</span></span> | <span data-ttu-id="1791a-147">Einddatum die de maker heeft ingesteld voor deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="1791a-147">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="1791a-148">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="1791a-148">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="1791a-149">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="1791a-149">fixedDevices</span></span> |  | <span data-ttu-id="1791a-150">Het aantal apparaten dat is opgelost</span><span class="sxs-lookup"><span data-stu-id="1791a-150">The number of devices that have been fixed</span></span> | <span data-ttu-id="1791a-151">2</span><span class="sxs-lookup"><span data-stu-id="1791a-151">2</span></span>
<span data-ttu-id="1791a-152">id</span><span class="sxs-lookup"><span data-stu-id="1791a-152">id</span></span> | <span data-ttu-id="1791a-153">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-153">String</span></span> | <span data-ttu-id="1791a-154">Id van deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="1791a-154">ID of this remediation activity</span></span> | <span data-ttu-id="1791a-155">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="1791a-155">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="1791a-156">nameId</span><span class="sxs-lookup"><span data-stu-id="1791a-156">nameId</span></span> | <span data-ttu-id="1791a-157">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-157">String</span></span> | <span data-ttu-id="1791a-158">Verwante productnaam</span><span class="sxs-lookup"><span data-stu-id="1791a-158">Related product name</span></span> | <span data-ttu-id="1791a-159">chrome</span><span class="sxs-lookup"><span data-stu-id="1791a-159">chrome</span></span>
<span data-ttu-id="1791a-160">prioriteit</span><span class="sxs-lookup"><span data-stu-id="1791a-160">priority</span></span> | <span data-ttu-id="1791a-161">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-161">String</span></span> | <span data-ttu-id="1791a-162">Prioriteit die de maker heeft ingesteld voor deze herstelactiviteit (Hoog\Gemiddeld\Laag)</span><span class="sxs-lookup"><span data-stu-id="1791a-162">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="1791a-163">Hoog</span><span class="sxs-lookup"><span data-stu-id="1791a-163">High</span></span>
<span data-ttu-id="1791a-164">productId</span><span class="sxs-lookup"><span data-stu-id="1791a-164">productId</span></span> | <span data-ttu-id="1791a-165">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-165">String</span></span> | <span data-ttu-id="1791a-166">Gerelateerde product-id</span><span class="sxs-lookup"><span data-stu-id="1791a-166">Related product ID</span></span> | <span data-ttu-id="1791a-167">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="1791a-167">google-_-chrome</span></span>
<span data-ttu-id="1791a-168">productiviteitImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="1791a-168">productivityImpactRemediationType</span></span> | <span data-ttu-id="1791a-169">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-169">String</span></span> | <span data-ttu-id="1791a-170">Er kunnen alleen enkele configuratiewijzigingen worden aangevraagd voor apparaten zonder dat dit gevolgen heeft voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1791a-170">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="1791a-171">Deze waarde geeft de selectie aan tussen 'alle blootgestelde apparaten' of 'alleen apparaten zonder invloed van de gebruiker'.</span><span class="sxs-lookup"><span data-stu-id="1791a-171">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="1791a-172">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="1791a-172">AllExposedAssets</span></span>
<span data-ttu-id="1791a-173">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="1791a-173">rbacGroupNames</span></span> | <span data-ttu-id="1791a-174">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-174">String</span></span> | <span data-ttu-id="1791a-175">Namen van gerelateerde apparaatgroep</span><span class="sxs-lookup"><span data-stu-id="1791a-175">Related device group names</span></span> | <span data-ttu-id="1791a-176">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="1791a-176">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="1791a-177">aanbevolenProgram</span><span class="sxs-lookup"><span data-stu-id="1791a-177">recommendedProgram</span></span> | <span data-ttu-id="1791a-178">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-178">String</span></span> | <span data-ttu-id="1791a-179">Aanbevolen programma om een upgrade uit te voeren naar</span><span class="sxs-lookup"><span data-stu-id="1791a-179">Recommended program to upgrade to</span></span> | <span data-ttu-id="1791a-180">null</span><span class="sxs-lookup"><span data-stu-id="1791a-180">null</span></span>
<span data-ttu-id="1791a-181">aanbevolenVendor</span><span class="sxs-lookup"><span data-stu-id="1791a-181">recommendedVendor</span></span> | <span data-ttu-id="1791a-182">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-182">String</span></span> | <span data-ttu-id="1791a-183">Aanbevolen leverancier om een upgrade uit te voeren naar</span><span class="sxs-lookup"><span data-stu-id="1791a-183">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="1791a-184">null</span><span class="sxs-lookup"><span data-stu-id="1791a-184">null</span></span>
<span data-ttu-id="1791a-185">aanbevolenVersie</span><span class="sxs-lookup"><span data-stu-id="1791a-185">recommendedVersion</span></span> | <span data-ttu-id="1791a-186">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-186">String</span></span> | <span data-ttu-id="1791a-187">Aanbevolen versie om bij te werken/upgraden naar</span><span class="sxs-lookup"><span data-stu-id="1791a-187">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="1791a-188">null</span><span class="sxs-lookup"><span data-stu-id="1791a-188">null</span></span>
<span data-ttu-id="1791a-189">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="1791a-189">relatedComponent</span></span> | <span data-ttu-id="1791a-190">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-190">String</span></span> | <span data-ttu-id="1791a-191">Gerelateerd onderdeel van deze herstelactiviteit (vergelijkbaar met het gerelateerde onderdeel voor een beveiligingsaanbeveling)</span><span class="sxs-lookup"><span data-stu-id="1791a-191">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="1791a-192">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="1791a-192">Google Chrome</span></span>
<span data-ttu-id="1791a-193">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="1791a-193">requesterEmail</span></span> | <span data-ttu-id="1791a-194">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-194">String</span></span> | <span data-ttu-id="1791a-195">E-mailadres maker</span><span class="sxs-lookup"><span data-stu-id="1791a-195">Creator email address</span></span> | <span data-ttu-id="1791a-196">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1791a-196">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="1791a-197">requesterId</span><span class="sxs-lookup"><span data-stu-id="1791a-197">requesterId</span></span> | <span data-ttu-id="1791a-198">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-198">String</span></span> | <span data-ttu-id="1791a-199">Creator-object-id</span><span class="sxs-lookup"><span data-stu-id="1791a-199">Creator object id</span></span> | <span data-ttu-id="1791a-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="1791a-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="1791a-201">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="1791a-201">requesterNotes</span></span> | <span data-ttu-id="1791a-202">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-202">String</span></span> | <span data-ttu-id="1791a-203">De notities (vrije tekst) die de maker heeft toegevoegd voor deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="1791a-203">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="1791a-204">null</span><span class="sxs-lookup"><span data-stu-id="1791a-204">null</span></span>
<span data-ttu-id="1791a-205">scid</span><span class="sxs-lookup"><span data-stu-id="1791a-205">scid</span></span> | <span data-ttu-id="1791a-206">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-206">String</span></span> | <span data-ttu-id="1791a-207">SCID van de gerelateerde beveiligingsaanbeveling</span><span class="sxs-lookup"><span data-stu-id="1791a-207">SCID of the related security recommendation</span></span> | <span data-ttu-id="1791a-208">null</span><span class="sxs-lookup"><span data-stu-id="1791a-208">null</span></span>
<span data-ttu-id="1791a-209">status</span><span class="sxs-lookup"><span data-stu-id="1791a-209">status</span></span> | <span data-ttu-id="1791a-210">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-210">String</span></span> | <span data-ttu-id="1791a-211">Status van herstelactiviteit (actief/voltooid)</span><span class="sxs-lookup"><span data-stu-id="1791a-211">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="1791a-212">Actief</span><span class="sxs-lookup"><span data-stu-id="1791a-212">Active</span></span>
<span data-ttu-id="1791a-213">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="1791a-213">statusLastModifiedOn</span></span> | <span data-ttu-id="1791a-214">DateTime</span><span class="sxs-lookup"><span data-stu-id="1791a-214">DateTime</span></span> | <span data-ttu-id="1791a-215">Datum waarop het statusveld is bijgewerkt</span><span class="sxs-lookup"><span data-stu-id="1791a-215">Date when the status field was updated</span></span> | <span data-ttu-id="1791a-216">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="1791a-216">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="1791a-217">targetDevices</span><span class="sxs-lookup"><span data-stu-id="1791a-217">targetDevices</span></span> | <span data-ttu-id="1791a-218">Lang</span><span class="sxs-lookup"><span data-stu-id="1791a-218">Long</span></span> | <span data-ttu-id="1791a-219">Het aantal blootgestelde apparaten dat door deze herstel wordt toegepast op</span><span class="sxs-lookup"><span data-stu-id="1791a-219">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="1791a-220">43</span><span class="sxs-lookup"><span data-stu-id="1791a-220">43</span></span>
<span data-ttu-id="1791a-221">titel</span><span class="sxs-lookup"><span data-stu-id="1791a-221">title</span></span> | <span data-ttu-id="1791a-222">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-222">String</span></span> | <span data-ttu-id="1791a-223">Titel van deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="1791a-223">Title of this remediation activity</span></span> | <span data-ttu-id="1791a-224">Google Chrome bijwerken</span><span class="sxs-lookup"><span data-stu-id="1791a-224">Update Google Chrome</span></span>
<span data-ttu-id="1791a-225">type</span><span class="sxs-lookup"><span data-stu-id="1791a-225">type</span></span> | <span data-ttu-id="1791a-226">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-226">String</span></span> | <span data-ttu-id="1791a-227">Hersteltype</span><span class="sxs-lookup"><span data-stu-id="1791a-227">Remediation type</span></span> | <span data-ttu-id="1791a-228">Update</span><span class="sxs-lookup"><span data-stu-id="1791a-228">Update</span></span>
<span data-ttu-id="1791a-229">vendorId</span><span class="sxs-lookup"><span data-stu-id="1791a-229">vendorId</span></span> | <span data-ttu-id="1791a-230">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1791a-230">String</span></span> | <span data-ttu-id="1791a-231">Naam van gerelateerde leverancier</span><span class="sxs-lookup"><span data-stu-id="1791a-231">Related vendor name</span></span> | <span data-ttu-id="1791a-232">google</span><span class="sxs-lookup"><span data-stu-id="1791a-232">google</span></span>

## <a name="example"></a><span data-ttu-id="1791a-233">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="1791a-233">Example</span></span>

<span data-ttu-id="1791a-234">**Voorbeeld aanvragen**</span><span class="sxs-lookup"><span data-stu-id="1791a-234">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

<span data-ttu-id="1791a-235">**Voorbeeld van** antwoord</span><span class="sxs-lookup"><span data-stu-id="1791a-235">**Response** example</span></span>

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
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
```

## <a name="see-also"></a><span data-ttu-id="1791a-236">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1791a-236">See also</span></span>

- [<span data-ttu-id="1791a-237">Herstelmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="1791a-237">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="1791a-238">Alle herstelactiviteiten op een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="1791a-238">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="1791a-239">Belichte apparaten van één herstelactiviteit op de lijst</span><span class="sxs-lookup"><span data-stu-id="1791a-239">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="1791a-240">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="1791a-240">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="1791a-241">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="1791a-241">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
