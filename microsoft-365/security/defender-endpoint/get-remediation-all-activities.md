---
title: Alle herstelactiviteiten weergeven
description: Retourneert informatie over alle herstelactiviteiten.
keywords: api's, herstel, herstel-api, get, hersteltaken, alle hersteltaken,
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 60f80e78a5f5c7da44a218c30f4b0173d4ecc829
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845128"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="b5113-104">Alle herstelactiviteiten weergeven</span><span class="sxs-lookup"><span data-stu-id="b5113-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b5113-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b5113-105">**Applies to:**</span></span>

- [<span data-ttu-id="b5113-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b5113-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b5113-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5113-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b5113-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b5113-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b5113-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="b5113-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b5113-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="b5113-110">API description</span></span>

<span data-ttu-id="b5113-111">Retourneert informatie over alle herstelactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="b5113-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="b5113-112">[Meer informatie over herstelactiviteiten.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="b5113-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="b5113-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="b5113-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="b5113-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="b5113-114">Permissions</span></span>

<span data-ttu-id="b5113-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="b5113-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b5113-116">Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b5113-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="b5113-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="b5113-117">Permission type</span></span> | <span data-ttu-id="b5113-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="b5113-118">Permission</span></span> | <span data-ttu-id="b5113-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="b5113-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b5113-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="b5113-120">Application</span></span> | <span data-ttu-id="b5113-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="b5113-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="b5113-122">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="b5113-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="b5113-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="b5113-123">Delegated (work or school account)</span></span> | <span data-ttu-id="b5113-124">RemediationTask.Read</span><span class="sxs-lookup"><span data-stu-id="b5113-124">RemediationTask.Read</span></span> | <span data-ttu-id="b5113-125">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="b5113-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="b5113-126">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="b5113-126">Properties</span></span>

<span data-ttu-id="b5113-127">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="b5113-127">Property (id)</span></span> | <span data-ttu-id="b5113-128">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="b5113-128">Data type</span></span> | <span data-ttu-id="b5113-129">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b5113-129">Description</span></span> | <span data-ttu-id="b5113-130">Voorbeeld van een geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="b5113-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="b5113-131">categorie</span><span class="sxs-lookup"><span data-stu-id="b5113-131">category</span></span> | <span data-ttu-id="b5113-132">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-132">String</span></span> | <span data-ttu-id="b5113-133">Categorie van de herstelactiviteit (software-/beveiligingsconfiguratie)</span><span class="sxs-lookup"><span data-stu-id="b5113-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="b5113-134">Software</span><span class="sxs-lookup"><span data-stu-id="b5113-134">Software</span></span>
<span data-ttu-id="b5113-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="b5113-135">completerEmail</span></span> | <span data-ttu-id="b5113-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-136">String</span></span> | <span data-ttu-id="b5113-137">Als de herstelactiviteit handmatig is voltooid door iemand, bevat deze kolom zijn of haar e-mail</span><span class="sxs-lookup"><span data-stu-id="b5113-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="b5113-138">null</span><span class="sxs-lookup"><span data-stu-id="b5113-138">null</span></span>
<span data-ttu-id="b5113-139">completerId</span><span class="sxs-lookup"><span data-stu-id="b5113-139">completerId</span></span> | <span data-ttu-id="b5113-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-140">String</span></span> | <span data-ttu-id="b5113-141">Als de herstelactiviteit handmatig is voltooid door iemand, bevat deze kolom de object-id</span><span class="sxs-lookup"><span data-stu-id="b5113-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="b5113-142">null</span><span class="sxs-lookup"><span data-stu-id="b5113-142">null</span></span>
<span data-ttu-id="b5113-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="b5113-143">completionMethod</span></span> | <span data-ttu-id="b5113-144">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-144">String</span></span> | <span data-ttu-id="b5113-145">Een herstelactiviteit kan 'automatisch' worden voltooid (als alle apparaten zijn gepatcht) of 'handmatig' door een persoon die 'markeren als voltooid' selecteert.</span><span class="sxs-lookup"><span data-stu-id="b5113-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="b5113-146">Automatisch</span><span class="sxs-lookup"><span data-stu-id="b5113-146">Automatic</span></span>
<span data-ttu-id="b5113-147">gemaaktOn</span><span class="sxs-lookup"><span data-stu-id="b5113-147">createdOn</span></span> | <span data-ttu-id="b5113-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="b5113-148">DateTime</span></span> | <span data-ttu-id="b5113-149">Tijd dat deze herstelactiviteit is gemaakt</span><span class="sxs-lookup"><span data-stu-id="b5113-149">Time this remediation activity was created</span></span> | <span data-ttu-id="b5113-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="b5113-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="b5113-151">beschrijving</span><span class="sxs-lookup"><span data-stu-id="b5113-151">description</span></span> | <span data-ttu-id="b5113-152">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-152">String</span></span> | <span data-ttu-id="b5113-153">Beschrijving van deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="b5113-153">Description of this remediation activity</span></span> | <span data-ttu-id="b5113-154">Werk Microsoft Silverlight bij naar een latere versie om bekende beveiligingsproblemen op uw apparaten te beperken.</span><span class="sxs-lookup"><span data-stu-id="b5113-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="b5113-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="b5113-155">dueOn</span></span> | <span data-ttu-id="b5113-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="b5113-156">DateTime</span></span> | <span data-ttu-id="b5113-157">Einddatum die de maker heeft ingesteld voor deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="b5113-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="b5113-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="b5113-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="b5113-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="b5113-159">fixedDevices</span></span> | <span data-ttu-id="b5113-160">.</span><span class="sxs-lookup"><span data-stu-id="b5113-160">.</span></span> | <span data-ttu-id="b5113-161">Het aantal apparaten dat is opgelost</span><span class="sxs-lookup"><span data-stu-id="b5113-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="b5113-162">2</span><span class="sxs-lookup"><span data-stu-id="b5113-162">2</span></span>
<span data-ttu-id="b5113-163">id</span><span class="sxs-lookup"><span data-stu-id="b5113-163">id</span></span> | <span data-ttu-id="b5113-164">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-164">String</span></span> | <span data-ttu-id="b5113-165">Id van deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="b5113-165">ID of this remediation activity</span></span> | <span data-ttu-id="b5113-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="b5113-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="b5113-167">nameId</span><span class="sxs-lookup"><span data-stu-id="b5113-167">nameId</span></span> | <span data-ttu-id="b5113-168">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-168">String</span></span> | <span data-ttu-id="b5113-169">Verwante productnaam</span><span class="sxs-lookup"><span data-stu-id="b5113-169">Related product name</span></span> | <span data-ttu-id="b5113-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="b5113-170">Microsoft Silverlight</span></span>
<span data-ttu-id="b5113-171">prioriteit</span><span class="sxs-lookup"><span data-stu-id="b5113-171">priority</span></span> | <span data-ttu-id="b5113-172">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-172">String</span></span> | <span data-ttu-id="b5113-173">Prioriteit die de maker heeft ingesteld voor deze herstelactiviteit (Hoog\Gemiddeld\Laag)</span><span class="sxs-lookup"><span data-stu-id="b5113-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="b5113-174">Hoog</span><span class="sxs-lookup"><span data-stu-id="b5113-174">High</span></span>
<span data-ttu-id="b5113-175">productId</span><span class="sxs-lookup"><span data-stu-id="b5113-175">productId</span></span> | <span data-ttu-id="b5113-176">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-176">String</span></span> | <span data-ttu-id="b5113-177">Gerelateerde product-id</span><span class="sxs-lookup"><span data-stu-id="b5113-177">Related product ID</span></span> | <span data-ttu-id="b5113-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="b5113-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="b5113-179">productiviteitImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="b5113-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="b5113-180">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-180">String</span></span> | <span data-ttu-id="b5113-181">Er kunnen alleen enkele configuratiewijzigingen worden aangevraagd voor apparaten zonder dat dit gevolgen heeft voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="b5113-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="b5113-182">Deze waarde geeft de selectie aan tussen 'alle blootgestelde apparaten' of 'alleen apparaten zonder gebruikerseffect'.</span><span class="sxs-lookup"><span data-stu-id="b5113-182">This value indicates the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="b5113-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="b5113-183">AllExposedAssets</span></span>
<span data-ttu-id="b5113-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="b5113-184">rbacGroupNames</span></span> | <span data-ttu-id="b5113-185">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-185">String</span></span> | <span data-ttu-id="b5113-186">Namen van gerelateerde apparaatgroep</span><span class="sxs-lookup"><span data-stu-id="b5113-186">Related device group names</span></span> | <span data-ttu-id="b5113-187">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="b5113-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="b5113-188">aanbevolenProgram</span><span class="sxs-lookup"><span data-stu-id="b5113-188">recommendedProgram</span></span> | <span data-ttu-id="b5113-189">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-189">String</span></span> | <span data-ttu-id="b5113-190">Aanbevolen programma om een upgrade uit te voeren naar</span><span class="sxs-lookup"><span data-stu-id="b5113-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="b5113-191">null</span><span class="sxs-lookup"><span data-stu-id="b5113-191">null</span></span>
<span data-ttu-id="b5113-192">aanbevolenVendor</span><span class="sxs-lookup"><span data-stu-id="b5113-192">recommendedVendor</span></span> | <span data-ttu-id="b5113-193">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-193">String</span></span> | <span data-ttu-id="b5113-194">Aanbevolen leverancier om een upgrade uit te voeren naar</span><span class="sxs-lookup"><span data-stu-id="b5113-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="b5113-195">null</span><span class="sxs-lookup"><span data-stu-id="b5113-195">null</span></span>
<span data-ttu-id="b5113-196">aanbevolenVersie</span><span class="sxs-lookup"><span data-stu-id="b5113-196">recommendedVersion</span></span> | <span data-ttu-id="b5113-197">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-197">String</span></span> | <span data-ttu-id="b5113-198">Aanbevolen versie om bij te werken/upgraden naar</span><span class="sxs-lookup"><span data-stu-id="b5113-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="b5113-199">null</span><span class="sxs-lookup"><span data-stu-id="b5113-199">null</span></span>
<span data-ttu-id="b5113-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="b5113-200">relatedComponent</span></span> | <span data-ttu-id="b5113-201">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-201">String</span></span> | <span data-ttu-id="b5113-202">Gerelateerd onderdeel van deze herstelactiviteit (vergelijkbaar met het gerelateerde onderdeel voor een beveiligingsaanbeveling)</span><span class="sxs-lookup"><span data-stu-id="b5113-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="b5113-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="b5113-203">Microsoft Silverlight</span></span>
<span data-ttu-id="b5113-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="b5113-204">requesterEmail</span></span> | <span data-ttu-id="b5113-205">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-205">String</span></span> | <span data-ttu-id="b5113-206">E-mailadres maker</span><span class="sxs-lookup"><span data-stu-id="b5113-206">Creator email address</span></span> | <span data-ttu-id="b5113-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5113-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="b5113-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="b5113-208">requesterId</span></span> | <span data-ttu-id="b5113-209">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-209">String</span></span> | <span data-ttu-id="b5113-210">Creator-object-id</span><span class="sxs-lookup"><span data-stu-id="b5113-210">Creator object id</span></span> | <span data-ttu-id="b5113-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="b5113-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="b5113-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="b5113-212">requesterNotes</span></span> | <span data-ttu-id="b5113-213">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-213">String</span></span> | <span data-ttu-id="b5113-214">De notities (vrije tekst) die de maker heeft toegevoegd voor deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="b5113-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="b5113-215">null</span><span class="sxs-lookup"><span data-stu-id="b5113-215">null</span></span>
<span data-ttu-id="b5113-216">scid</span><span class="sxs-lookup"><span data-stu-id="b5113-216">scid</span></span> | <span data-ttu-id="b5113-217">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-217">String</span></span> | <span data-ttu-id="b5113-218">SCID van de gerelateerde beveiligingsaanbeveling</span><span class="sxs-lookup"><span data-stu-id="b5113-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="b5113-219">null</span><span class="sxs-lookup"><span data-stu-id="b5113-219">null</span></span>
<span data-ttu-id="b5113-220">status</span><span class="sxs-lookup"><span data-stu-id="b5113-220">status</span></span> | <span data-ttu-id="b5113-221">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-221">String</span></span> | <span data-ttu-id="b5113-222">Status van herstelactiviteit (actief/voltooid)</span><span class="sxs-lookup"><span data-stu-id="b5113-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="b5113-223">Actief</span><span class="sxs-lookup"><span data-stu-id="b5113-223">Active</span></span>
<span data-ttu-id="b5113-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="b5113-224">statusLastModifiedOn</span></span> | <span data-ttu-id="b5113-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="b5113-225">DateTime</span></span> | <span data-ttu-id="b5113-226">Datum waarop het statusveld is bijgewerkt</span><span class="sxs-lookup"><span data-stu-id="b5113-226">Date when the status field was updated</span></span> | <span data-ttu-id="b5113-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="b5113-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="b5113-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="b5113-228">targetDevices</span></span> | <span data-ttu-id="b5113-229">Lang</span><span class="sxs-lookup"><span data-stu-id="b5113-229">Long</span></span> | <span data-ttu-id="b5113-230">Het aantal blootgestelde apparaten dat door deze herstel wordt toegepast op</span><span class="sxs-lookup"><span data-stu-id="b5113-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="b5113-231">43</span><span class="sxs-lookup"><span data-stu-id="b5113-231">43</span></span>
<span data-ttu-id="b5113-232">titel</span><span class="sxs-lookup"><span data-stu-id="b5113-232">title</span></span> | <span data-ttu-id="b5113-233">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-233">String</span></span> | <span data-ttu-id="b5113-234">Titel van deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="b5113-234">Title of this remediation activity</span></span> | <span data-ttu-id="b5113-235">Microsoft Silverlight bijwerken</span><span class="sxs-lookup"><span data-stu-id="b5113-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="b5113-236">type</span><span class="sxs-lookup"><span data-stu-id="b5113-236">type</span></span> | <span data-ttu-id="b5113-237">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-237">String</span></span> | <span data-ttu-id="b5113-238">Hersteltype</span><span class="sxs-lookup"><span data-stu-id="b5113-238">Remediation type</span></span> | <span data-ttu-id="b5113-239">Update</span><span class="sxs-lookup"><span data-stu-id="b5113-239">Update</span></span>
<span data-ttu-id="b5113-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="b5113-240">vendorId</span></span> | <span data-ttu-id="b5113-241">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b5113-241">String</span></span> | <span data-ttu-id="b5113-242">Naam van gerelateerde leverancier</span><span class="sxs-lookup"><span data-stu-id="b5113-242">Related vendor name</span></span> | <span data-ttu-id="b5113-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5113-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="b5113-244">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="b5113-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="b5113-245">Voorbeeld aanvragen</span><span class="sxs-lookup"><span data-stu-id="b5113-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="b5113-246">Voorbeeld van antwoord</span><span class="sxs-lookup"><span data-stu-id="b5113-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b5113-247">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b5113-247">See also</span></span>

- [<span data-ttu-id="b5113-248">Herstelmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="b5113-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="b5113-249">Eén herstelactiviteit krijgen op id</span><span class="sxs-lookup"><span data-stu-id="b5113-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="b5113-250">Weergegeven apparaten van één herstelactiviteit weergeven</span><span class="sxs-lookup"><span data-stu-id="b5113-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="b5113-251">Risicogebaseerd & vulnerability management</span><span class="sxs-lookup"><span data-stu-id="b5113-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="b5113-252">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="b5113-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
