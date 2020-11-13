---
title: Los problemen op die door het hulpprogramma voor gereedheidsevaluatie worden gevonden
description: Gedetailleerde stappen voor elk probleem dat met het hulpprogramma wordt gevonden
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 0459de8974fe6bae98e6984fd7dc65afeb04b4e7
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021083"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="bd888-104">Los problemen op die door het hulpprogramma voor gereedheidsevaluatie worden gevonden</span><span class="sxs-lookup"><span data-stu-id="bd888-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="bd888-105">Voor elke controle wordt in het hulpmiddel een van de vier mogelijke resultaten weergegeven:</span><span class="sxs-lookup"><span data-stu-id="bd888-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="bd888-106">Resultaat</span><span class="sxs-lookup"><span data-stu-id="bd888-106">Result</span></span>  |<span data-ttu-id="bd888-107">Betekenis</span><span class="sxs-lookup"><span data-stu-id="bd888-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="bd888-108">Gereedgemaakt</span><span class="sxs-lookup"><span data-stu-id="bd888-108">Ready</span></span>     | <span data-ttu-id="bd888-109">U hoeft geen actie te ondernemen voordat u de registratie uitvoert.</span><span class="sxs-lookup"><span data-stu-id="bd888-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="bd888-110">Adviser</span><span class="sxs-lookup"><span data-stu-id="bd888-110">Advisory</span></span>    | <span data-ttu-id="bd888-111">Voer de stappen in het hulpprogramma of dit artikel uit voor de beste ervaring met inschrijving en voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="bd888-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="bd888-112">U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.</span><span class="sxs-lookup"><span data-stu-id="bd888-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="bd888-113">Niet gereed</span><span class="sxs-lookup"><span data-stu-id="bd888-113">Not ready</span></span> | <span data-ttu-id="bd888-114">*De registratie mislukt als u deze problemen niet oplost.*</span><span class="sxs-lookup"><span data-stu-id="bd888-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="bd888-115">Voer de stappen in het hulpprogramma of dit artikel uit om ze op te lossen.</span><span class="sxs-lookup"><span data-stu-id="bd888-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="bd888-116">Error</span><span class="sxs-lookup"><span data-stu-id="bd888-116">Error</span></span> | <span data-ttu-id="bd888-117">De rol van Azure Active Director (AD) die u gebruikt, heeft onvoldoende machtigingen om deze controle uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="bd888-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="bd888-118">Microsoft intune-instellingen</span><span class="sxs-lookup"><span data-stu-id="bd888-118">Microsoft Intune settings</span></span>

<span data-ttu-id="bd888-119">U kunt de intune-instellingen openen via het [Beheercentrum](https://endpoint.microsoft.com)van Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="bd888-119">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="bd888-120">Auto Pilot-implementatie profiel</span><span class="sxs-lookup"><span data-stu-id="bd888-120">Autopilot deployment profile</span></span>

<span data-ttu-id="bd888-121">U hebt geen bestaande auto pilot-profielen die door Microsoft beheerde bureaublad worden toegewezen of dynamische groepen die door Microsoft worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="bd888-121">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="bd888-122">Microsoft Managed Desktop gebruikt auto pilot om nieuwe apparaten te creëren.</span><span class="sxs-lookup"><span data-stu-id="bd888-122">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="bd888-123">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-123">**Not ready**</span></span>

<span data-ttu-id="bd888-124">U hebt een auto pilot-profiel dat is toegewezen aan alle apparaten.</span><span class="sxs-lookup"><span data-stu-id="bd888-124">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="bd888-125">Zie [Windows-apparaten in intune registreren met behulp van Windows auto pilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="bd888-125">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="bd888-126">Wanneer de Microsoft-bureaublad registratie voor het bureaublad is ingeschakeld, stelt u uw auto pilot-beleid in om de **moderne werkplekken te uitsluiten: alle** Azure AD-groep.</span><span class="sxs-lookup"><span data-stu-id="bd888-126">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="bd888-127">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-127">**Advisory**</span></span>

<span data-ttu-id="bd888-128">Zorg ervoor dat uw auto pilot-profielen een toegewezen of dynamische Azure AD-groep betreffen die geen door Microsoft beheerde bureaublad apparaten bevat die worden gemaakt bij het registreren.</span><span class="sxs-lookup"><span data-stu-id="bd888-128">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="bd888-129">Zie [Windows-apparaten in intune registreren met behulp van Windows auto pilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="bd888-129">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="bd888-130">Wanneer de Microsoft-bureaublad registratie voor het bureaublad is ingeschakeld, stelt u uw auto pilot-beleid in om de **moderne werkplekken te uitsluiten: alle** Azure AD-groep.</span><span class="sxs-lookup"><span data-stu-id="bd888-130">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="bd888-131">Certificaat verbindingslijnen</span><span class="sxs-lookup"><span data-stu-id="bd888-131">Certificate connectors</span></span>

<span data-ttu-id="bd888-132">Als u certificaat verbindingslijnen hebt die worden gebruikt door de apparaten die u wilt registreren op Microsoft Managed Desktop, zijn de connectors geen fouten.</span><span class="sxs-lookup"><span data-stu-id="bd888-132">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="bd888-133">Slechts één van de volgende adviseurs is op uw situatie van toepassing, dus controleer ze aandachtig.</span><span class="sxs-lookup"><span data-stu-id="bd888-133">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="bd888-134">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-134">**Advisory**</span></span>

<span data-ttu-id="bd888-135">Er zijn geen certificaat connectors aanwezig.</span><span class="sxs-lookup"><span data-stu-id="bd888-135">No certificate connectors are present.</span></span> <span data-ttu-id="bd888-136">Het is mogelijk dat u geen connectors nodig hebt, maar u moet eerst beoordelen of u een netwerkverbinding met Microsoft beheerde bureaublad apparaten nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="bd888-136">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bd888-137">Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-137">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="bd888-138">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-138">**Advisory**</span></span>

<span data-ttu-id="bd888-139">Minstens één certificaatconnector bevat een fout.</span><span class="sxs-lookup"><span data-stu-id="bd888-139">At least one certificate connector has an error.</span></span> <span data-ttu-id="bd888-140">Als u deze connector nodig hebt voor connectiviteit met Microsoft Managed Desktop-apparaten, moet u de fout oplossen.</span><span class="sxs-lookup"><span data-stu-id="bd888-140">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="bd888-141">Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-141">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="bd888-142">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-142">**Advisory**</span></span>

<span data-ttu-id="bd888-143">U moet minimaal één certificaatconnector en geen fouten rapporteren.</span><span class="sxs-lookup"><span data-stu-id="bd888-143">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="bd888-144">U kunt echter wel een profiel maken om de connector voor Microsoft beheerde bureaublad apparaten opnieuw te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="bd888-144">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bd888-145">Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-145">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="bd888-146">Beleidsregels voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="bd888-146">Conditional access policies</span></span>

<span data-ttu-id="bd888-147">Het beleid voor voorwaardelijke toegang in uw Azure AD-organisatie mag geen Microsoft-bureaubladgebruikers bedoelen.</span><span class="sxs-lookup"><span data-stu-id="bd888-147">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="bd888-148">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-148">**Not ready**</span></span>

<span data-ttu-id="bd888-149">U hebt ten minste één beleid voor voorwaardelijke toegang voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="bd888-149">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="bd888-150">Stel het beleid opnieuw in om een specifieke Azure AD-groep met de Azure AD-groep met Microsoft Managed Desktop service-accounts die worden gemaakt bij het registreren, niet te omvatten.</span><span class="sxs-lookup"><span data-stu-id="bd888-150">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="bd888-151">Zie voor de stappen [voorwaardelijke toegang: gebruikers en groepen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="bd888-151">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="bd888-152">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-152">**Advisory**</span></span>

<span data-ttu-id="bd888-153">Zorg ervoor dat u een beleidsregels voor voorwaardelijke toegang hebt uitgesloten met de Azure AD-groep voor de **moderne service accounts** .</span><span class="sxs-lookup"><span data-stu-id="bd888-153">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="bd888-154">Zie [voorwaardelijke toegang aanpassen](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)voor de stappen.</span><span class="sxs-lookup"><span data-stu-id="bd888-154">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="bd888-155">De **modern Workplace service accounts** Azure Ad Group is een dynamische groep die we voor de service maken wanneer u zich registreert.</span><span class="sxs-lookup"><span data-stu-id="bd888-155">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="bd888-156">U dient na de inschrijving weer de groep uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="bd888-156">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="bd888-157">Zie voor meer informatie over deze serviceaccounts [standaardprocedures](../service-description/operations-and-monitoring.md#standard-operating-procedures)voor het werk.</span><span class="sxs-lookup"><span data-stu-id="bd888-157">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="bd888-158">**Fout**</span><span class="sxs-lookup"><span data-stu-id="bd888-158">**Error**</span></span>

<span data-ttu-id="bd888-159">De rol intune-beheerder heeft onvoldoende machtigingen voor deze controle.</span><span class="sxs-lookup"><span data-stu-id="bd888-159">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="bd888-160">U hebt ook een van de volgende Azure AD-rollen nodig die zijn toegewezen om deze controle uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="bd888-160">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="bd888-161">Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="bd888-161">Security Reader</span></span>
- <span data-ttu-id="bd888-162">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="bd888-162">Security Administrator</span></span>
- <span data-ttu-id="bd888-163">Beheerder van voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="bd888-163">Conditional Access Administrator</span></span>
- <span data-ttu-id="bd888-164">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="bd888-164">Global Reader</span></span>
- <span data-ttu-id="bd888-165">Apparaten beheerder</span><span class="sxs-lookup"><span data-stu-id="bd888-165">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="bd888-166">Nalevingsbeleid voor apparaten</span><span class="sxs-lookup"><span data-stu-id="bd888-166">Device Compliance policies</span></span>

<span data-ttu-id="bd888-167">Het beleid voor naleving van intune-apparaten in de Azure AD-organisatie mag geen door Microsoft beheerde bureaubladgebruikers afstemmen.</span><span class="sxs-lookup"><span data-stu-id="bd888-167">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="bd888-168">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-168">**Not ready**</span></span>

<span data-ttu-id="bd888-169">U hebt ten minste één nalevingsbeleid voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="bd888-169">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="bd888-170">Stel het beleid opnieuw in om een specifieke Azure AD-groep te richten die geen Microsoft-beheerde bureaubladgebruikers omvat.</span><span class="sxs-lookup"><span data-stu-id="bd888-170">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="bd888-171">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="bd888-171">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="bd888-172">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-172">**Advisory**</span></span>

<span data-ttu-id="bd888-173">Zorg ervoor dat het nalevingsbeleid van Microsoft beheerde bureaubladgebruikers niet omvat.</span><span class="sxs-lookup"><span data-stu-id="bd888-173">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="bd888-174">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="bd888-174">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="bd888-175">Beleidsregels voor apparaatconfiguratie</span><span class="sxs-lookup"><span data-stu-id="bd888-175">Device Configuration policies</span></span>

<span data-ttu-id="bd888-176">Het beleid voor het configureren van intune-apparaten in de Azure AD-organisatie mag geen Microsoft-bureaublad apparaten of-gebruikers beheren.</span><span class="sxs-lookup"><span data-stu-id="bd888-176">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="bd888-177">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-177">**Not ready**</span></span>

<span data-ttu-id="bd888-178">U hebt minimaal één configuratiebeleid voor alle gebruikers, alle apparaten of beide.</span><span class="sxs-lookup"><span data-stu-id="bd888-178">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="bd888-179">Stel het beleid opnieuw in om een specifieke Azure AD-groep te richten die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="bd888-179">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bd888-180">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="bd888-180">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="bd888-181">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-181">**Advisory**</span></span>

<span data-ttu-id="bd888-182">Zorg ervoor dat het nalevingsbeleid van Microsoft beheerde bureaublad apparaten of gebruikers niet omvat.</span><span class="sxs-lookup"><span data-stu-id="bd888-182">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="bd888-183">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="bd888-183">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="bd888-184">Beperkingen voor apparaattype</span><span class="sxs-lookup"><span data-stu-id="bd888-184">Device type restrictions</span></span>

<span data-ttu-id="bd888-185">Door Microsoft beheerde bureaublad apparaten moet u zich kunnen registreren bij intune.</span><span class="sxs-lookup"><span data-stu-id="bd888-185">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="bd888-186">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-186">**Not ready**</span></span>

<span data-ttu-id="bd888-187">Voer de stappen uit in de optie voor het [instellen van inschrijving](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) om de **instelling toe te passen.**</span><span class="sxs-lookup"><span data-stu-id="bd888-187">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="bd888-188">Pagina met inschrijvings status</span><span class="sxs-lookup"><span data-stu-id="bd888-188">Enrollment Status Page</span></span>

<span data-ttu-id="bd888-189">U hebt momenteel de pagina met de inschrijvings status (ESP) ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="bd888-189">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="bd888-190">Als u deelneemt aan de openbare preview van deze functie, kunt u dit item negeren.</span><span class="sxs-lookup"><span data-stu-id="bd888-190">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="bd888-191">Zie [First Run-ervaring met auto pilot en de pagina inschrijvings status](../get-started/esp-first-run.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-191">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="bd888-192">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-192">**Not ready**</span></span>

<span data-ttu-id="bd888-193">Voor het weergeven van de voortgang van de **apps en profielen** moet u de standaard-ESP-profielset opgeven.</span><span class="sxs-lookup"><span data-stu-id="bd888-193">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="bd888-194">Schakel deze instelling uit of zorg ervoor dat toewijzingen aan een Azure AD-groep geen door Microsoft beheerde bureaublad apparaten bevatten door de stappen te volgen in [de pagina inschrijvings status instellen](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="bd888-194">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="bd888-195">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-195">**Advisory**</span></span>

<span data-ttu-id="bd888-196">Zorg ervoor dat profielen met de instelling **voortgang van app en profielconfiguratie weergeven** niet zijn toegewezen aan een Azure AD-groep die Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="bd888-196">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bd888-197">Zie [de pagina inschrijvings status instellen](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-197">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="bd888-198">InTune-registratie</span><span class="sxs-lookup"><span data-stu-id="bd888-198">Intune enrollment</span></span>

<span data-ttu-id="bd888-199">Windows 10-apparaten in uw Azure AD-organisatie moeten automatisch worden geregistreerd in intune.</span><span class="sxs-lookup"><span data-stu-id="bd888-199">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="bd888-200">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-200">**Advisory**</span></span>

<span data-ttu-id="bd888-201">Zorg ervoor dat het bereik van MDM-gebruikers is **ingesteld op** **Alles of alles** , niet **none**.</span><span class="sxs-lookup"><span data-stu-id="bd888-201">Make sure the MDM User scope is set to **Some** or **All** , not **None**.</span></span> <span data-ttu-id="bd888-202">Als u **een aantal** kiest, meldt u zich weer na de inschrijving en selecteert u de groep **modern Workplace-all** Azure AD voor **groepen**.</span><span class="sxs-lookup"><span data-stu-id="bd888-202">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="bd888-203">Microsoft Store voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="bd888-203">Microsoft Store for Business</span></span>

<span data-ttu-id="bd888-204">We gebruiken Microsoft Store voor bedrijven, zodat u de bedrijfs portal kunt downloaden om bepaalde apps te implementeren, zoals Microsoft Project en Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="bd888-204">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="bd888-205">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-205">**Not ready**</span></span>

<span data-ttu-id="bd888-206">Microsoft Store voor bedrijven is niet ingeschakeld of wordt niet gesynchroniseerd met intune.</span><span class="sxs-lookup"><span data-stu-id="bd888-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="bd888-207">Zie voor meer informatie het artikel [apps gekochte apps in Microsoft Store voor bedrijven beheren met Microsoft intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) en de [intune-bedrijfs portal installeren op een apparaat](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="bd888-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="bd888-208">Meervoudige verificatie</span><span class="sxs-lookup"><span data-stu-id="bd888-208">Multi-factor authentication</span></span>

<span data-ttu-id="bd888-209">Meervoudige verificatie mag niet per ongeluk worden toegepast op Microsoft beheerde bureaublad serviceaccounts.</span><span class="sxs-lookup"><span data-stu-id="bd888-209">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="bd888-210">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-210">**Not ready**</span></span>

<span data-ttu-id="bd888-211">U hebt een aantal opties voor het instellen van multi-factor Authentication (MFA) ingesteld voor het beleid voor voorwaardelijke toegang dat aan alle gebruikers wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="bd888-211">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="bd888-212">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="bd888-212">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bd888-213">Zie voor meer informatie [beleidsregels voor voorwaardelijke toegang](#conditional-access-policies) en [voorwaardelijke toegang: MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="bd888-213">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="bd888-214">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-214">**Advisory**</span></span>

<span data-ttu-id="bd888-215">Zorg ervoor dat voor beleidsregels voor voorwaardelijke toegang de optie MFA moet **zijn opgenomen:** de groep alle Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bd888-215">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="bd888-216">Zie voor meer informatie [beleidsregels voor voorwaardelijke toegang](#conditional-access-policies) en [voorwaardelijke toegang: MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="bd888-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="bd888-217">De **modern Workplace-all** Azure AD-groep is een dynamische groep die we maken wanneer u zich registreert bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.</span><span class="sxs-lookup"><span data-stu-id="bd888-217">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="bd888-218">**Fout**</span><span class="sxs-lookup"><span data-stu-id="bd888-218">**Error**</span></span>

<span data-ttu-id="bd888-219">De rol intune-beheerder heeft onvoldoende machtigingen voor deze controle.</span><span class="sxs-lookup"><span data-stu-id="bd888-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="bd888-220">U hebt ook een van de volgende Azure AD-rollen nodig die zijn toegewezen om deze controle uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="bd888-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="bd888-221">Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="bd888-221">Security Reader</span></span>
- <span data-ttu-id="bd888-222">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="bd888-222">Security Administrator</span></span>
- <span data-ttu-id="bd888-223">Beheerder van voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="bd888-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="bd888-224">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="bd888-224">Global Reader</span></span>
- <span data-ttu-id="bd888-225">Apparaten beheerder</span><span class="sxs-lookup"><span data-stu-id="bd888-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="bd888-226">PowerShell-scripts</span><span class="sxs-lookup"><span data-stu-id="bd888-226">PowerShell scripts</span></span>

<span data-ttu-id="bd888-227">Windows PowerShell-scripts kunnen niet worden toegewezen in de manier waarop Microsoft beheerde bureaublad apparaten kunnen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="bd888-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="bd888-228">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-228">**Advisory**</span></span>

<span data-ttu-id="bd888-229">Zorg ervoor dat Windows PowerShell-scripts in uw Azure AD-organisatie geen Microsoft-bureaublad apparaten of-gebruikers beheren.</span><span class="sxs-lookup"><span data-stu-id="bd888-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="bd888-230">Wijs geen PowerShell-script toe om alle gebruikers, alle apparaten of beide te bereiken.</span><span class="sxs-lookup"><span data-stu-id="bd888-230">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="bd888-231">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="bd888-231">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bd888-232">Zie [PowerShell-scripts op Windows 10-apparaten gebruiken in intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-232">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="bd888-233">Regio</span><span class="sxs-lookup"><span data-stu-id="bd888-233">Region</span></span>

<span data-ttu-id="bd888-234">Uw regio moet worden ondersteund door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bd888-234">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="bd888-235">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-235">**Not ready**</span></span>

<span data-ttu-id="bd888-236">Uw regio van Azure AD organisatie wordt momenteel niet ondersteund door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bd888-236">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="bd888-237">Zie [ondersteunde regio's en talen door Microsoft worden beheerd op het bureaublad](../service-description/regions-languages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-237">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="bd888-238">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-238">**Advisory**</span></span>

<span data-ttu-id="bd888-239">Een of meer van de landen waar uw Azure AD organisatie zich bevindt, wordt niet ondersteund door het door Microsoft beheerde bureaublad.</span><span class="sxs-lookup"><span data-stu-id="bd888-239">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="bd888-240">Zie [ondersteunde regio's en talen door Microsoft worden beheerd op het bureaublad](../service-description/regions-languages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="bd888-241">Basislijnen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="bd888-241">Security baselines</span></span>

<span data-ttu-id="bd888-242">Beleidsregels voor beveiliging van basislijn dienen niet te worden beheerd door Microsoft beheerde bureaublad apparaten.</span><span class="sxs-lookup"><span data-stu-id="bd888-242">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="bd888-243">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-243">**Not ready**</span></span>

<span data-ttu-id="bd888-244">U hebt een profiel voor beveiligings basislijn voor alle gebruikers, alle apparaten of beide.</span><span class="sxs-lookup"><span data-stu-id="bd888-244">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="bd888-245">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="bd888-245">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bd888-246">Zie [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="bd888-246">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="bd888-247">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-247">**Advisory**</span></span>

<span data-ttu-id="bd888-248">Zorg dat beleidsregels voor beveiliging op basis van Microsoft beheerde bureaublad apparaten zijn uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="bd888-248">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bd888-249">Zie [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="bd888-249">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="bd888-250">De **moderne werkplekken-** de groep Azure AD is een dynamische groep die we maken wanneer u zich aanmeldt bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.</span><span class="sxs-lookup"><span data-stu-id="bd888-250">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="bd888-251">Windows-apps</span><span class="sxs-lookup"><span data-stu-id="bd888-251">Windows apps</span></span>

<span data-ttu-id="bd888-252">Bekijk de apps waarover u Microsoft beheerde bureaubladgebruikers wilt hebben.</span><span class="sxs-lookup"><span data-stu-id="bd888-252">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="bd888-253">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-253">**Advisory**</span></span>

<span data-ttu-id="bd888-254">U moet een inventarisatie voorbereiden van de apps die u wilt laten door Microsoft beheerde bureaubladgebruikers.</span><span class="sxs-lookup"><span data-stu-id="bd888-254">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="bd888-255">Aangezien deze apps moeten worden geïmplementeerd door intune, evalueert u de bestaande intune-apps opnieuw.</span><span class="sxs-lookup"><span data-stu-id="bd888-255">Since these apps must be deployed by Intune, evaluate re-using existing Intune apps.</span></span> <span data-ttu-id="bd888-256">Overweeg om bedrijfsportal te gebruiken (Zie [intune-bedrijfsportal installeren op apparaten](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) en de pagina inschrijvings status (ESP) om apps te distribueren voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="bd888-256">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="bd888-257">Zie [apps in Microsoft Managed Desktop](apps.md) en [First-Run met auto pilot en de pagina met de inschrijvings status](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-257">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="bd888-258">U kunt de vertegenwoordiger van uw Microsoft-account vragen om te bepalen welke apps gereed zijn om te worden gemigreerd naar intune of een correctie.</span><span class="sxs-lookup"><span data-stu-id="bd888-258">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="bd888-259">Windows Hello voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="bd888-259">Windows Hello for Business</span></span>

<span data-ttu-id="bd888-260">Voor Microsoft Managed Desktop is Windows hello voor bedrijven ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="bd888-260">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="bd888-261">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-261">**Not ready**</span></span>

<span data-ttu-id="bd888-262">Windows hello voor bedrijven is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="bd888-262">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="bd888-263">Activeren door de stappen te volgen in [een beleid voor Windows hello voor bedrijven maken](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="bd888-263">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="bd888-264">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-264">**Advisory**</span></span>

<span data-ttu-id="bd888-265">Windows hello voor bedrijven is niet ingesteld.</span><span class="sxs-lookup"><span data-stu-id="bd888-265">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="bd888-266">Schakel deze optie in door de stappen te volgen in [een beleid voor Windows hello voor bedrijven maken](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="bd888-266">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="bd888-267">Windows 10-update ringen</span><span class="sxs-lookup"><span data-stu-id="bd888-267">Windows 10 update rings</span></span>

<span data-ttu-id="bd888-268">Het beleid Windows 10-update ring in intune mag geen Microsoft-bureaublad apparaten met Microsoft worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="bd888-268">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="bd888-269">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-269">**Not ready**</span></span>

<span data-ttu-id="bd888-270">U hebt een beleid voor het bijwerken van een update voor alle apparaten, alle gebruikers of beide.</span><span class="sxs-lookup"><span data-stu-id="bd888-270">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="bd888-271">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="bd888-271">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bd888-272">Zie [updates voor Windows 10-software beheren in intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="bd888-272">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="bd888-273">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-273">**Advisory**</span></span>

<span data-ttu-id="bd888-274">Zorg ervoor dat bij een update ring beleid u de **moderne Werkplaatsings apparaten-alle** Azure AD-groep uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="bd888-274">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="bd888-275">Als u een Azure AD-gebruikersgroep aan deze beleidsregels hebt toegewezen, moet u ervoor zorgen dat u ook de **moderne werkplek,** exclusief de Azure AD-groep, die uw door Microsoft beheerde bureaubladgebruikers omvat.</span><span class="sxs-lookup"><span data-stu-id="bd888-275">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group which includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="bd888-276">Zie [updates voor Windows 10-software beheren in intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="bd888-276">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="bd888-277">Zowel de **moderne werkplekken-** alle en de **moderne werkplek: alle** Azure ad-groepen zijn toegewezen groepen die we maken wanneer u zich aanmeldt bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.</span><span class="sxs-lookup"><span data-stu-id="bd888-277">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="bd888-278">Azure Active Directory-instellingen</span><span class="sxs-lookup"><span data-stu-id="bd888-278">Azure Active Directory settings</span></span>

<span data-ttu-id="bd888-279">U kunt toegang krijgen tot Azure Active Directory-instellingen op de [Azure-Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="bd888-279">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="bd888-280">Ad hoc-abonnementen</span><span class="sxs-lookup"><span data-stu-id="bd888-280">Ad hoc subscriptions</span></span>

<span data-ttu-id="bd888-281">Adviseert het controleren van een instelling die (indien ingesteld op ' onwaar ') kan voorkomen dat roaming via Enterprise niet goed werkt.</span><span class="sxs-lookup"><span data-stu-id="bd888-281">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="bd888-282">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-282">**Advisory**</span></span>

<span data-ttu-id="bd888-283">Zorg ervoor dat **AllowAdHocSubscriptions** is ingesteld op **waar**.</span><span class="sxs-lookup"><span data-stu-id="bd888-283">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="bd888-284">Anders werkt Enterprise State roaming mogelijk niet.</span><span class="sxs-lookup"><span data-stu-id="bd888-284">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="bd888-285">Zie [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-285">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="bd888-286">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="bd888-286">Enterprise State Roaming</span></span>

<span data-ttu-id="bd888-287">Enterprise State roaming moet zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="bd888-287">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="bd888-288">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-288">**Advisory**</span></span>

<span data-ttu-id="bd888-289">Zorg ervoor dat roaming voor bedrijven is ingeschakeld voor **alle** of voor **geselecteerde** groepen.</span><span class="sxs-lookup"><span data-stu-id="bd888-289">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="bd888-290">Zie [Enterprise State roaming inschakelen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-290">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="bd888-291">Licenties</span><span class="sxs-lookup"><span data-stu-id="bd888-291">Licenses</span></span>

<span data-ttu-id="bd888-292">U moet een aantal licenties gebruiken om Microsoft Managed Desktop te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="bd888-292">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="bd888-293">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-293">**Not Ready**</span></span>

<span data-ttu-id="bd888-294">U hebt niet alle licenties die u nodig hebt om Microsoft Managed Desktop te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="bd888-294">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="bd888-295">Zie [Microsoft Managed Desktop Technologies](../intro/technologies.md) en meer informatie [over licenties](prerequisites.md#more-about-licenses)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-295">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="bd888-296">Namen van beveiligingsaccounts</span><span class="sxs-lookup"><span data-stu-id="bd888-296">Security account names</span></span>

<span data-ttu-id="bd888-297">Het is mogelijk dat de namen van bepaalde beveiligingsaccounts conflicteren met die van Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bd888-297">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="bd888-298">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-298">**Not ready**</span></span>

<span data-ttu-id="bd888-299">U hebt minimaal één accountnaam waarvan de naam afwijkt van de naam die wordt gemaakt door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bd888-299">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="bd888-300">Met de vertegenwoordiger van uw Microsoft-account kunt u deze accountnamen uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="bd888-300">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="bd888-301">Rollen van beveiligingsbeheerders</span><span class="sxs-lookup"><span data-stu-id="bd888-301">Security administrator roles</span></span>

<span data-ttu-id="bd888-302">Gebruikers met bepaalde beveiligingsrollen moeten de toewijzingen in Microsoft Defender voor eindpunten hebben.</span><span class="sxs-lookup"><span data-stu-id="bd888-302">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="bd888-303">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-303">**Advisory**</span></span>

<span data-ttu-id="bd888-304">Als u gebruikers hebt toegewezen aan een van deze rollen in uw Azure AD-organisatie, moet u ervoor zorgen dat deze rollen ook zijn toegewezen in Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="bd888-304">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bd888-305">Anders hebben beheerders met deze rollen geen toegang tot de beheerportal.</span><span class="sxs-lookup"><span data-stu-id="bd888-305">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="bd888-306">Beveiligings operator</span><span class="sxs-lookup"><span data-stu-id="bd888-306">Security Operator</span></span>
- <span data-ttu-id="bd888-307">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="bd888-307">Global Reader</span></span>

<span data-ttu-id="bd888-308">Zie [rollen voor toegangsbeheer op basis van rollen maken en beheren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd888-308">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="bd888-309">Beveiligingsstandaard</span><span class="sxs-lookup"><span data-stu-id="bd888-309">Security default</span></span>

<span data-ttu-id="bd888-310">Met behulp van de beveiligingsinstellingen in azure Active Directory wordt voorkomen dat Microsoft beheerd bureaublad uw apparaten beheert.</span><span class="sxs-lookup"><span data-stu-id="bd888-310">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="bd888-311">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="bd888-311">**Not ready**</span></span>

<span data-ttu-id="bd888-312">U hebt beveiligingsstandaarden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="bd888-312">You have Security defaults turned on.</span></span> <span data-ttu-id="bd888-313">Schakel beveiligingsstandaarden uit en stel beleidsregels voor voorwaardelijke toegang in.</span><span class="sxs-lookup"><span data-stu-id="bd888-313">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="bd888-314">Zie voor meer informatie [veelgebruikte beleidsregels voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="bd888-314">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="bd888-315">Selfservice voor wachtwoordherstel</span><span class="sxs-lookup"><span data-stu-id="bd888-315">Self-service Password Reset</span></span>

<span data-ttu-id="bd888-316">U moet selfservice voor wachtwoordherstel (SSPR) inschakelen voor alle Microsoft beheerde bureaubladgebruikers, met uitzondering van Microsoft beheerde bureaublad serviceaccounts.</span><span class="sxs-lookup"><span data-stu-id="bd888-316">Self-service Password Reset (SSPR) should be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="bd888-317">Zie [Zelfstudie: gebruikers toestaan hun account te ontgrendelen of wachtwoorden opnieuw in te stellen met behulp van Azure Active Directory-wachtwoordherstel](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="bd888-317">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="bd888-318">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-318">**Advisory**</span></span>

<span data-ttu-id="bd888-319">Zorg ervoor dat de **geselecteerde** instelling voor SSPR Microsoft beheerde bureaublad apparaten bevat, maar dat Microsoft beheerde bureaublad-serviceaccounts niet is opgenomen.</span><span class="sxs-lookup"><span data-stu-id="bd888-319">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="bd888-320">Accounts van Microsoft beheerde bureaubladservices werken niet zoals verwacht wanneer SSPR is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="bd888-320">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="bd888-321">Standaard gebruikersrol</span><span class="sxs-lookup"><span data-stu-id="bd888-321">Standard user role</span></span>

<span data-ttu-id="bd888-322">Behalve de gebruikers die een Azure AD-rol van globale beheerder en een andere netwerkbeheerder toegewezen, zijn Microsoft-beheerde bureaubladgebruikers standaardgebruikers zonder lokale beheerdersbevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="bd888-322">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="bd888-323">Voor alle andere gebruikers wordt een standaard gebruikersrol toegewezen wanneer ze hun Microsoft-beheerde bureaublad apparaat starten.</span><span class="sxs-lookup"><span data-stu-id="bd888-323">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="bd888-324">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-324">**Advisory**</span></span>

<span data-ttu-id="bd888-325">Microsoft beheerde bureaubladgebruikers hebben geen lokale beheerdersbevoegdheden op hun Microsoft beheerde bureaublad apparaten na registratie.</span><span class="sxs-lookup"><span data-stu-id="bd888-325">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="bd888-326">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="bd888-326">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="bd888-327">OneDrive</span><span class="sxs-lookup"><span data-stu-id="bd888-327">OneDrive</span></span>

<span data-ttu-id="bd888-328">De instelling voor **synchronisatie alleen toestaan op pc's die lid zijn van een specifieke domein** instelling, conflicteert met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bd888-328">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="bd888-329">U kunt toegang krijgen tot OneDrive-instellingen in het OneDrive- [Beheercentrum](https://admin.onedrive.com).</span><span class="sxs-lookup"><span data-stu-id="bd888-329">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="bd888-330">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="bd888-330">**Advisory**</span></span>

<span data-ttu-id="bd888-331">U gebruikt de instelling **synchronisatie alleen toestaan op pc's die lid zijn van bepaalde domeinen** .</span><span class="sxs-lookup"><span data-stu-id="bd888-331">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="bd888-332">Deze instelling werkt niet met beheerde Microsoft-bureaublad.</span><span class="sxs-lookup"><span data-stu-id="bd888-332">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="bd888-333">Schakel deze instelling uit en zet OneDrive zodanig in dat deze gebruikmaakt van een voorwaardelijk toegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="bd888-333">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="bd888-334">Zie [voorwaardelijke toegang plannen](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="bd888-334">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

