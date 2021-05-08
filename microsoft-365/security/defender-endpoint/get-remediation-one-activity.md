---
title: Eén herstelactiviteit krijgen op id
description: Retourneert gegevens voor de opgegeven herstelactiviteit.
keywords: api's, herstel, herstel-api, get, hersteltaken, herstel per id,
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
ms.openlocfilehash: e0f68e8a28b302f0ae1ca06a2f892fea38a219b2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244441"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="761eb-104">Eén herstelactiviteit krijgen op id</span><span class="sxs-lookup"><span data-stu-id="761eb-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="761eb-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="761eb-105">**Applies to:**</span></span>

- [<span data-ttu-id="761eb-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="761eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="761eb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="761eb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="761eb-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="761eb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="761eb-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="761eb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="761eb-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="761eb-110">API description</span></span>

<span data-ttu-id="761eb-111">Retourneert gegevens voor de opgegeven herstelactiviteit.</span><span class="sxs-lookup"><span data-stu-id="761eb-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="761eb-112">Geeft dezelfde kolommen weer als [Alle herstelactiviteit](get-remediation-all-activities.md)', maar geeft alleen resultaten als resultaat voor de opgegeven _herstelactiviteit._</span><span class="sxs-lookup"><span data-stu-id="761eb-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="761eb-113">[Meer informatie over herstelactiviteiten.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="761eb-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="761eb-114">Een opgegeven herstelactiviteit voor (id)</span><span class="sxs-lookup"><span data-stu-id="761eb-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="761eb-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="761eb-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

## <a name="permissions"></a><span data-ttu-id="761eb-116">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="761eb-116">Permissions</span></span>

<span data-ttu-id="761eb-117">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="761eb-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="761eb-118">Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="761eb-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="761eb-119">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="761eb-119">Permission type</span></span> | <span data-ttu-id="761eb-120">Machtiging</span><span class="sxs-lookup"><span data-stu-id="761eb-120">Permission</span></span> | <span data-ttu-id="761eb-121">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="761eb-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="761eb-122">Toepassing</span><span class="sxs-lookup"><span data-stu-id="761eb-122">Application</span></span> | <span data-ttu-id="761eb-123">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="761eb-123">RemediationTask.Read.All</span></span> | <span data-ttu-id="761eb-124">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="761eb-124">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="761eb-125">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="761eb-125">Delegated (work or school account)</span></span> | <span data-ttu-id="761eb-126">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="761eb-126">RemediationTask.Read.Read</span></span> | <span data-ttu-id="761eb-127">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="761eb-127">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="761eb-128">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="761eb-128">Properties</span></span>

<span data-ttu-id="761eb-129">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="761eb-129">Property (id)</span></span> | <span data-ttu-id="761eb-130">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="761eb-130">Data type</span></span> | <span data-ttu-id="761eb-131">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="761eb-131">Description</span></span> | <span data-ttu-id="761eb-132">Voorbeeld van een geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="761eb-132">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="761eb-133">categorie</span><span class="sxs-lookup"><span data-stu-id="761eb-133">category</span></span> | <span data-ttu-id="761eb-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-134">String</span></span> | <span data-ttu-id="761eb-135">Categorie van de herstelactiviteit (software-/beveiligingsconfiguratie)</span><span class="sxs-lookup"><span data-stu-id="761eb-135">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="761eb-136">Software</span><span class="sxs-lookup"><span data-stu-id="761eb-136">Software</span></span>
<span data-ttu-id="761eb-137">completerEmail</span><span class="sxs-lookup"><span data-stu-id="761eb-137">completerEmail</span></span> | <span data-ttu-id="761eb-138">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-138">String</span></span> | <span data-ttu-id="761eb-139">Als de herstelactiviteit handmatig is voltooid door iemand, bevat deze kolom zijn of haar e-mail</span><span class="sxs-lookup"><span data-stu-id="761eb-139">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="761eb-140">null</span><span class="sxs-lookup"><span data-stu-id="761eb-140">null</span></span>
<span data-ttu-id="761eb-141">completerId</span><span class="sxs-lookup"><span data-stu-id="761eb-141">completerId</span></span> | <span data-ttu-id="761eb-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-142">String</span></span> | <span data-ttu-id="761eb-143">Als de herstelactiviteit handmatig is voltooid door iemand, bevat deze kolom de object-id</span><span class="sxs-lookup"><span data-stu-id="761eb-143">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="761eb-144">null</span><span class="sxs-lookup"><span data-stu-id="761eb-144">null</span></span>
<span data-ttu-id="761eb-145">completionMethod</span><span class="sxs-lookup"><span data-stu-id="761eb-145">completionMethod</span></span> | <span data-ttu-id="761eb-146">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-146">String</span></span> | <span data-ttu-id="761eb-147">Een herstelactiviteit kan 'automatisch' worden voltooid (als alle apparaten zijn gepatcht) of 'handmatig' door een persoon die 'markeren als voltooid' selecteert.</span><span class="sxs-lookup"><span data-stu-id="761eb-147">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="761eb-148">Automatisch</span><span class="sxs-lookup"><span data-stu-id="761eb-148">Automatic</span></span>
<span data-ttu-id="761eb-149">gemaaktOn</span><span class="sxs-lookup"><span data-stu-id="761eb-149">createdOn</span></span> | <span data-ttu-id="761eb-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="761eb-150">DateTime</span></span> | <span data-ttu-id="761eb-151">Tijd dat deze herstelactiviteit is gemaakt</span><span class="sxs-lookup"><span data-stu-id="761eb-151">Time this remediation activity was created</span></span> | <span data-ttu-id="761eb-152">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="761eb-152">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="761eb-153">beschrijving</span><span class="sxs-lookup"><span data-stu-id="761eb-153">description</span></span> | <span data-ttu-id="761eb-154">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-154">String</span></span> | <span data-ttu-id="761eb-155">Beschrijving van deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="761eb-155">Description of this remediation activity</span></span> | <span data-ttu-id="761eb-156">Werk Microsoft Silverlight bij naar een latere versie om bekende beveiligingsproblemen op uw apparaten te beperken.</span><span class="sxs-lookup"><span data-stu-id="761eb-156">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="761eb-157">dueOn</span><span class="sxs-lookup"><span data-stu-id="761eb-157">dueOn</span></span> | <span data-ttu-id="761eb-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="761eb-158">DateTime</span></span> | <span data-ttu-id="761eb-159">Einddatum die de maker heeft ingesteld voor deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="761eb-159">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="761eb-160">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="761eb-160">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="761eb-161">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="761eb-161">fixedDevices</span></span> |  | <span data-ttu-id="761eb-162">Het aantal apparaten dat is opgelost</span><span class="sxs-lookup"><span data-stu-id="761eb-162">The number of devices that have been fixed</span></span> | <span data-ttu-id="761eb-163">2</span><span class="sxs-lookup"><span data-stu-id="761eb-163">2</span></span>
<span data-ttu-id="761eb-164">id</span><span class="sxs-lookup"><span data-stu-id="761eb-164">id</span></span> | <span data-ttu-id="761eb-165">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-165">String</span></span> | <span data-ttu-id="761eb-166">Id van deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="761eb-166">ID of this remediation activity</span></span> | <span data-ttu-id="761eb-167">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="761eb-167">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="761eb-168">nameId</span><span class="sxs-lookup"><span data-stu-id="761eb-168">nameId</span></span> | <span data-ttu-id="761eb-169">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-169">String</span></span> | <span data-ttu-id="761eb-170">Verwante productnaam</span><span class="sxs-lookup"><span data-stu-id="761eb-170">Related product name</span></span> | <span data-ttu-id="761eb-171">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="761eb-171">Microsoft Silverlight</span></span>
<span data-ttu-id="761eb-172">prioriteit</span><span class="sxs-lookup"><span data-stu-id="761eb-172">priority</span></span> | <span data-ttu-id="761eb-173">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-173">String</span></span> | <span data-ttu-id="761eb-174">Prioriteit die de maker heeft ingesteld voor deze herstelactiviteit (Hoog\Gemiddeld\Laag)</span><span class="sxs-lookup"><span data-stu-id="761eb-174">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="761eb-175">Hoog</span><span class="sxs-lookup"><span data-stu-id="761eb-175">High</span></span>
<span data-ttu-id="761eb-176">productId</span><span class="sxs-lookup"><span data-stu-id="761eb-176">productId</span></span> | <span data-ttu-id="761eb-177">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-177">String</span></span> | <span data-ttu-id="761eb-178">Gerelateerde product-id</span><span class="sxs-lookup"><span data-stu-id="761eb-178">Related product ID</span></span> | <span data-ttu-id="761eb-179">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="761eb-179">microsoft-_-silverlight</span></span>
<span data-ttu-id="761eb-180">productiviteitImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="761eb-180">productivityImpactRemediationType</span></span> | <span data-ttu-id="761eb-181">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-181">String</span></span> | <span data-ttu-id="761eb-182">Er kunnen alleen enkele configuratiewijzigingen worden aangevraagd voor apparaten zonder dat dit gevolgen heeft voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="761eb-182">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="761eb-183">Deze waarde geeft de selectie aan tussen 'alle blootgestelde apparaten' of 'alleen apparaten zonder invloed van de gebruiker'.</span><span class="sxs-lookup"><span data-stu-id="761eb-183">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="761eb-184">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="761eb-184">AllExposedAssets</span></span>
<span data-ttu-id="761eb-185">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="761eb-185">rbacGroupNames</span></span> | <span data-ttu-id="761eb-186">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-186">String</span></span> | <span data-ttu-id="761eb-187">Namen van gerelateerde apparaatgroep</span><span class="sxs-lookup"><span data-stu-id="761eb-187">Related device group names</span></span> | <span data-ttu-id="761eb-188">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="761eb-188">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="761eb-189">aanbevolenProgram</span><span class="sxs-lookup"><span data-stu-id="761eb-189">recommendedProgram</span></span> | <span data-ttu-id="761eb-190">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-190">String</span></span> | <span data-ttu-id="761eb-191">Aanbevolen programma om een upgrade uit te voeren naar</span><span class="sxs-lookup"><span data-stu-id="761eb-191">Recommended program to upgrade to</span></span> | <span data-ttu-id="761eb-192">null</span><span class="sxs-lookup"><span data-stu-id="761eb-192">null</span></span>
<span data-ttu-id="761eb-193">aanbevolenVendor</span><span class="sxs-lookup"><span data-stu-id="761eb-193">recommendedVendor</span></span> | <span data-ttu-id="761eb-194">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-194">String</span></span> | <span data-ttu-id="761eb-195">Aanbevolen leverancier om een upgrade uit te voeren naar</span><span class="sxs-lookup"><span data-stu-id="761eb-195">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="761eb-196">null</span><span class="sxs-lookup"><span data-stu-id="761eb-196">null</span></span>
<span data-ttu-id="761eb-197">aanbevolenVersie</span><span class="sxs-lookup"><span data-stu-id="761eb-197">recommendedVersion</span></span> | <span data-ttu-id="761eb-198">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-198">String</span></span> | <span data-ttu-id="761eb-199">Aanbevolen versie om bij te werken/upgraden naar</span><span class="sxs-lookup"><span data-stu-id="761eb-199">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="761eb-200">null</span><span class="sxs-lookup"><span data-stu-id="761eb-200">null</span></span>
<span data-ttu-id="761eb-201">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="761eb-201">relatedComponent</span></span> | <span data-ttu-id="761eb-202">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-202">String</span></span> | <span data-ttu-id="761eb-203">Gerelateerd onderdeel van deze herstelactiviteit (vergelijkbaar met het gerelateerde onderdeel voor een beveiligingsaanbeveling)</span><span class="sxs-lookup"><span data-stu-id="761eb-203">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="761eb-204">Microsoft Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="761eb-204">Microsoft Microsoft Silverlight</span></span>
<span data-ttu-id="761eb-205">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="761eb-205">requesterEmail</span></span> | <span data-ttu-id="761eb-206">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-206">String</span></span> | <span data-ttu-id="761eb-207">E-mailadres maker</span><span class="sxs-lookup"><span data-stu-id="761eb-207">Creator email address</span></span> | <span data-ttu-id="761eb-208">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="761eb-208">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="761eb-209">requesterId</span><span class="sxs-lookup"><span data-stu-id="761eb-209">requesterId</span></span> | <span data-ttu-id="761eb-210">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-210">String</span></span> | <span data-ttu-id="761eb-211">Creator-object-id</span><span class="sxs-lookup"><span data-stu-id="761eb-211">Creator object id</span></span> | <span data-ttu-id="761eb-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="761eb-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="761eb-213">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="761eb-213">requesterNotes</span></span> | <span data-ttu-id="761eb-214">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-214">String</span></span> | <span data-ttu-id="761eb-215">De notities (vrije tekst) die de maker heeft toegevoegd voor deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="761eb-215">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="761eb-216">null</span><span class="sxs-lookup"><span data-stu-id="761eb-216">null</span></span>
<span data-ttu-id="761eb-217">scid</span><span class="sxs-lookup"><span data-stu-id="761eb-217">scid</span></span> | <span data-ttu-id="761eb-218">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-218">String</span></span> | <span data-ttu-id="761eb-219">SCID van de gerelateerde beveiligingsaanbeveling</span><span class="sxs-lookup"><span data-stu-id="761eb-219">SCID of the related security recommendation</span></span> | <span data-ttu-id="761eb-220">null</span><span class="sxs-lookup"><span data-stu-id="761eb-220">null</span></span>
<span data-ttu-id="761eb-221">status</span><span class="sxs-lookup"><span data-stu-id="761eb-221">status</span></span> | <span data-ttu-id="761eb-222">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-222">String</span></span> | <span data-ttu-id="761eb-223">Status van herstelactiviteit (actief/voltooid)</span><span class="sxs-lookup"><span data-stu-id="761eb-223">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="761eb-224">Actief</span><span class="sxs-lookup"><span data-stu-id="761eb-224">Active</span></span>
<span data-ttu-id="761eb-225">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="761eb-225">statusLastModifiedOn</span></span> | <span data-ttu-id="761eb-226">DateTime</span><span class="sxs-lookup"><span data-stu-id="761eb-226">DateTime</span></span> | <span data-ttu-id="761eb-227">Datum waarop het statusveld is bijgewerkt</span><span class="sxs-lookup"><span data-stu-id="761eb-227">Date when the status field was updated</span></span> | <span data-ttu-id="761eb-228">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="761eb-228">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="761eb-229">targetDevices</span><span class="sxs-lookup"><span data-stu-id="761eb-229">targetDevices</span></span> | <span data-ttu-id="761eb-230">Lang</span><span class="sxs-lookup"><span data-stu-id="761eb-230">Long</span></span> | <span data-ttu-id="761eb-231">Het aantal blootgestelde apparaten dat door deze herstel wordt toegepast op</span><span class="sxs-lookup"><span data-stu-id="761eb-231">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="761eb-232">43</span><span class="sxs-lookup"><span data-stu-id="761eb-232">43</span></span>
<span data-ttu-id="761eb-233">titel</span><span class="sxs-lookup"><span data-stu-id="761eb-233">title</span></span> | <span data-ttu-id="761eb-234">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-234">String</span></span> | <span data-ttu-id="761eb-235">Titel van deze herstelactiviteit</span><span class="sxs-lookup"><span data-stu-id="761eb-235">Title of this remediation activity</span></span> | <span data-ttu-id="761eb-236">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="761eb-236">Microsoft Silverlight</span></span>
<span data-ttu-id="761eb-237">type</span><span class="sxs-lookup"><span data-stu-id="761eb-237">type</span></span> | <span data-ttu-id="761eb-238">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-238">String</span></span> | <span data-ttu-id="761eb-239">Hersteltype</span><span class="sxs-lookup"><span data-stu-id="761eb-239">Remediation type</span></span> | <span data-ttu-id="761eb-240">Update</span><span class="sxs-lookup"><span data-stu-id="761eb-240">Update</span></span>
<span data-ttu-id="761eb-241">vendorId</span><span class="sxs-lookup"><span data-stu-id="761eb-241">vendorId</span></span> | <span data-ttu-id="761eb-242">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="761eb-242">String</span></span> | <span data-ttu-id="761eb-243">Naam van gerelateerde leverancier</span><span class="sxs-lookup"><span data-stu-id="761eb-243">Related vendor name</span></span> | <span data-ttu-id="761eb-244">Microsoft</span><span class="sxs-lookup"><span data-stu-id="761eb-244">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="761eb-245">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="761eb-245">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="761eb-246">Voorbeeld aanvragen</span><span class="sxs-lookup"><span data-stu-id="761eb-246">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a><span data-ttu-id="761eb-247">Voorbeeld van antwoord</span><span class="sxs-lookup"><span data-stu-id="761eb-247">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="761eb-248">Zie ook</span><span class="sxs-lookup"><span data-stu-id="761eb-248">See also</span></span>

- [<span data-ttu-id="761eb-249">Herstelmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="761eb-249">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="761eb-250">Alle herstelactiviteiten weergeven</span><span class="sxs-lookup"><span data-stu-id="761eb-250">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="761eb-251">Weergegeven apparaten van één herstelactiviteit weergeven</span><span class="sxs-lookup"><span data-stu-id="761eb-251">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="761eb-252">Risicogebaseerd & vulnerability management</span><span class="sxs-lookup"><span data-stu-id="761eb-252">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="761eb-253">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="761eb-253">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
