---
title: Problemen gevonden met het hulpprogramma voor gereedheids beoordeling
description: Gedetailleerde stappen voor elk probleem dat met het hulpprogramma wordt gevonden
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 642de80e1a133f212b7afb6774d9aab2eeaabdbf
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941407"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="584b8-104">Problemen gevonden met het hulpprogramma voor gereedheids beoordeling</span><span class="sxs-lookup"><span data-stu-id="584b8-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="584b8-105">Voor elke controle wordt in het hulpmiddel een van de vier mogelijke resultaten weergegeven:</span><span class="sxs-lookup"><span data-stu-id="584b8-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="584b8-106">Resultaat</span><span class="sxs-lookup"><span data-stu-id="584b8-106">Result</span></span>  |<span data-ttu-id="584b8-107">Betekenis</span><span class="sxs-lookup"><span data-stu-id="584b8-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="584b8-108">Gereedgemaakt</span><span class="sxs-lookup"><span data-stu-id="584b8-108">Ready</span></span>     | <span data-ttu-id="584b8-109">U hoeft geen actie te ondernemen voordat u de registratie uitvoert.</span><span class="sxs-lookup"><span data-stu-id="584b8-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="584b8-110">Adviser</span><span class="sxs-lookup"><span data-stu-id="584b8-110">Advisory</span></span>    | <span data-ttu-id="584b8-111">Voer de stappen in het hulpprogramma of dit artikel uit voor de beste ervaring met inschrijving en voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="584b8-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="584b8-112">U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.</span><span class="sxs-lookup"><span data-stu-id="584b8-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="584b8-113">Niet gereed</span><span class="sxs-lookup"><span data-stu-id="584b8-113">Not ready</span></span> | <span data-ttu-id="584b8-114">*De registratie mislukt als u deze problemen niet oplost.*</span><span class="sxs-lookup"><span data-stu-id="584b8-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="584b8-115">Voer de stappen in het hulpprogramma of dit artikel uit om ze op te lossen.</span><span class="sxs-lookup"><span data-stu-id="584b8-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="584b8-116">Error</span><span class="sxs-lookup"><span data-stu-id="584b8-116">Error</span></span> | <span data-ttu-id="584b8-117">De rol van Azure Active Director (AD) die u gebruikt, heeft onvoldoende machtigingen om deze controle uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="584b8-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="584b8-118">Microsoft intune-instellingen</span><span class="sxs-lookup"><span data-stu-id="584b8-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="584b8-119">Auto Pilot-implementatie profiel</span><span class="sxs-lookup"><span data-stu-id="584b8-119">Autopilot deployment profile</span></span>

<span data-ttu-id="584b8-120">U hebt geen bestaande auto pilot-profielen die door Microsoft beheerde bureaublad worden toegewezen of dynamische groepen die door Microsoft worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="584b8-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="584b8-121">Microsoft Managed Desktop gebruikt auto pilot om nieuwe apparaten te creëren.</span><span class="sxs-lookup"><span data-stu-id="584b8-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="584b8-122">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-122">**Not ready**</span></span>

<span data-ttu-id="584b8-123">U hebt een auto pilot-profiel dat is toegewezen aan alle apparaten.</span><span class="sxs-lookup"><span data-stu-id="584b8-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="584b8-124">Zie [Windows-apparaten in intune registreren met behulp van Windows auto pilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="584b8-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="584b8-125">Wanneer de Microsoft-bureaublad registratie voor het bureaublad is ingeschakeld, stelt u uw auto pilot-beleid in om de **moderne werkplekken te uitsluiten: alle** Azure AD-groep.</span><span class="sxs-lookup"><span data-stu-id="584b8-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="584b8-126">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-126">**Advisory**</span></span>

<span data-ttu-id="584b8-127">Zorg ervoor dat uw auto pilot-profielen een toegewezen of dynamische Azure AD-groep betreffen die geen door Microsoft beheerde bureaublad apparaten bevat die worden gemaakt bij het registreren.</span><span class="sxs-lookup"><span data-stu-id="584b8-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="584b8-128">Zie [Windows-apparaten in intune registreren met behulp van Windows auto pilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="584b8-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="584b8-129">Wanneer de Microsoft-bureaublad registratie voor het bureaublad is ingeschakeld, stelt u uw auto pilot-beleid in om de **moderne werkplekken te uitsluiten: alle** Azure AD-groep.</span><span class="sxs-lookup"><span data-stu-id="584b8-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="584b8-130">Certificaat verbindingslijnen</span><span class="sxs-lookup"><span data-stu-id="584b8-130">Certificate connectors</span></span>

<span data-ttu-id="584b8-131">Als u certificaat verbindingslijnen hebt die worden gebruikt door de apparaten die u wilt registreren op Microsoft Managed Desktop, zijn de connectors geen fouten.</span><span class="sxs-lookup"><span data-stu-id="584b8-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="584b8-132">Slechts één van de volgende adviseurs is op uw situatie van toepassing, dus controleer ze aandachtig.</span><span class="sxs-lookup"><span data-stu-id="584b8-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="584b8-133">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-133">**Advisory**</span></span>

<span data-ttu-id="584b8-134">Er zijn geen certificaat connectors aanwezig.</span><span class="sxs-lookup"><span data-stu-id="584b8-134">No certificate connectors are present.</span></span> <span data-ttu-id="584b8-135">Het is mogelijk dat u geen connectors nodig hebt, maar u moet eerst beoordelen of u een netwerkverbinding met Microsoft beheerde bureaublad apparaten nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="584b8-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="584b8-136">Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="584b8-137">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-137">**Advisory**</span></span>

<span data-ttu-id="584b8-138">Minstens één certificaatconnector bevat een fout.</span><span class="sxs-lookup"><span data-stu-id="584b8-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="584b8-139">Als u deze connector nodig hebt voor connectiviteit met Microsoft Managed Desktop-apparaten, moet u de fout oplossen.</span><span class="sxs-lookup"><span data-stu-id="584b8-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="584b8-140">Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="584b8-141">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-141">**Advisory**</span></span>

<span data-ttu-id="584b8-142">U moet minimaal één certificaatconnector en geen fouten rapporteren.</span><span class="sxs-lookup"><span data-stu-id="584b8-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="584b8-143">U kunt echter wel een profiel maken om de connector voor Microsoft beheerde bureaublad apparaten opnieuw te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="584b8-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="584b8-144">Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="584b8-145">Beleidsregels voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="584b8-145">Conditional access policies</span></span>

<span data-ttu-id="584b8-146">Het beleid voor voorwaardelijke toegang in uw Azure AD-organisatie mag geen Microsoft-bureaubladgebruikers bedoelen.</span><span class="sxs-lookup"><span data-stu-id="584b8-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="584b8-147">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-147">**Not ready**</span></span>

<span data-ttu-id="584b8-148">U hebt ten minste één beleid voor voorwaardelijke toegang voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="584b8-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="584b8-149">Stel het beleid opnieuw in om een specifieke Azure AD-groep met de Azure AD-groep met Microsoft Managed Desktop service-accounts die worden gemaakt bij het registreren, niet te omvatten.</span><span class="sxs-lookup"><span data-stu-id="584b8-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="584b8-150">Zie voor de stappen [voorwaardelijke toegang: gebruikers en groepen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="584b8-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="584b8-151">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-151">**Advisory**</span></span>

<span data-ttu-id="584b8-152">Zorg ervoor dat u een beleidsregels voor voorwaardelijke toegang hebt uitgesloten met de Azure AD-groep voor de **moderne service accounts** .</span><span class="sxs-lookup"><span data-stu-id="584b8-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="584b8-153">Zie [voorwaardelijke toegang aanpassen](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)voor de stappen.</span><span class="sxs-lookup"><span data-stu-id="584b8-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="584b8-154">De **modern Workplace service accounts** Azure Ad Group is een dynamische groep die we voor de service maken wanneer u zich registreert.</span><span class="sxs-lookup"><span data-stu-id="584b8-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="584b8-155">U dient na de inschrijving weer de groep uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="584b8-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="584b8-156">Zie voor meer informatie over deze serviceaccounts [standaardprocedures](../service-description/operations-and-monitoring.md#standard-operating-procedures)voor het werk.</span><span class="sxs-lookup"><span data-stu-id="584b8-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="584b8-157">**Fout**</span><span class="sxs-lookup"><span data-stu-id="584b8-157">**Error**</span></span>

<span data-ttu-id="584b8-158">De rol intune-beheerder heeft onvoldoende machtigingen voor deze controle.</span><span class="sxs-lookup"><span data-stu-id="584b8-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="584b8-159">U hebt ook een van de volgende Azure AD-rollen nodig die zijn toegewezen om deze controle uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="584b8-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="584b8-160">Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="584b8-160">Security Reader</span></span>
- <span data-ttu-id="584b8-161">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="584b8-161">Security Administrator</span></span>
- <span data-ttu-id="584b8-162">Beheerder van voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="584b8-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="584b8-163">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="584b8-163">Global Reader</span></span>
- <span data-ttu-id="584b8-164">Apparaten beheerder</span><span class="sxs-lookup"><span data-stu-id="584b8-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="584b8-165">Nalevingsbeleid voor apparaten</span><span class="sxs-lookup"><span data-stu-id="584b8-165">Device Compliance policies</span></span>

<span data-ttu-id="584b8-166">Het beleid voor naleving van intune-apparaten in de Azure AD-organisatie mag geen door Microsoft beheerde bureaubladgebruikers afstemmen.</span><span class="sxs-lookup"><span data-stu-id="584b8-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="584b8-167">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-167">**Not ready**</span></span>

<span data-ttu-id="584b8-168">U hebt ten minste één nalevingsbeleid voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="584b8-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="584b8-169">Stel het beleid opnieuw in om een specifieke Azure AD-groep te richten die geen Microsoft-beheerde bureaubladgebruikers omvat.</span><span class="sxs-lookup"><span data-stu-id="584b8-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="584b8-170">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="584b8-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="584b8-171">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-171">**Advisory**</span></span>

<span data-ttu-id="584b8-172">Zorg ervoor dat het nalevingsbeleid van Microsoft beheerde bureaubladgebruikers niet omvat.</span><span class="sxs-lookup"><span data-stu-id="584b8-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="584b8-173">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="584b8-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="584b8-174">Beleidsregels voor apparaatconfiguratie</span><span class="sxs-lookup"><span data-stu-id="584b8-174">Device Configuration policies</span></span>

<span data-ttu-id="584b8-175">Het beleid voor het configureren van intune-apparaten in de Azure AD-organisatie mag geen Microsoft-bureaublad apparaten of-gebruikers beheren.</span><span class="sxs-lookup"><span data-stu-id="584b8-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="584b8-176">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-176">**Not ready**</span></span>

<span data-ttu-id="584b8-177">U hebt minimaal één configuratiebeleid voor alle gebruikers, alle apparaten of beide.</span><span class="sxs-lookup"><span data-stu-id="584b8-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="584b8-178">Stel het beleid opnieuw in om een specifieke Azure AD-groep te richten die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="584b8-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="584b8-179">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="584b8-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="584b8-180">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-180">**Advisory**</span></span>

<span data-ttu-id="584b8-181">Zorg ervoor dat het nalevingsbeleid van Microsoft beheerde bureaublad apparaten of gebruikers niet omvat.</span><span class="sxs-lookup"><span data-stu-id="584b8-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="584b8-182">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="584b8-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="584b8-183">Beperkingen voor apparaattype</span><span class="sxs-lookup"><span data-stu-id="584b8-183">Device type restrictions</span></span>

<span data-ttu-id="584b8-184">Door Microsoft beheerde bureaublad apparaten moet u zich kunnen registreren bij intune.</span><span class="sxs-lookup"><span data-stu-id="584b8-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="584b8-185">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-185">**Not ready**</span></span>

<span data-ttu-id="584b8-186">Voer de stappen uit in de optie voor het [instellen van inschrijving](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) om de **instelling toe te passen.**</span><span class="sxs-lookup"><span data-stu-id="584b8-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="584b8-187">Pagina met inschrijvings status</span><span class="sxs-lookup"><span data-stu-id="584b8-187">Enrollment Status Page</span></span>

<span data-ttu-id="584b8-188">U hebt momenteel de pagina met de inschrijvings status (ESP) ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="584b8-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="584b8-189">Als u deelneemt aan de openbare preview van deze functie, kunt u dit item negeren.</span><span class="sxs-lookup"><span data-stu-id="584b8-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="584b8-190">Zie [First Run-ervaring met auto pilot en de pagina inschrijvings status](../get-started/esp-first-run.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="584b8-191">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-191">**Not ready**</span></span>

<span data-ttu-id="584b8-192">Voor het weergeven van de voortgang van de **apps en profielen** moet u de standaard-ESP-profielset opgeven.</span><span class="sxs-lookup"><span data-stu-id="584b8-192">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="584b8-193">Schakel deze instelling uit of zorg ervoor dat toewijzingen aan een Azure AD-groep geen door Microsoft beheerde bureaublad apparaten bevatten door de stappen te volgen in [de pagina inschrijvings status instellen](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="584b8-193">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="584b8-194">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-194">**Advisory**</span></span>

<span data-ttu-id="584b8-195">Zorg ervoor dat profielen met de instelling **voortgang van app en profielconfiguratie weergeven** niet zijn toegewezen aan een Azure AD-groep die Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="584b8-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="584b8-196">Zie [de pagina inschrijvings status instellen](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="584b8-197">InTune-registratie</span><span class="sxs-lookup"><span data-stu-id="584b8-197">Intune enrollment</span></span>

<span data-ttu-id="584b8-198">Windows 10-apparaten in uw Azure AD-organisatie moeten automatisch worden geregistreerd in intune.</span><span class="sxs-lookup"><span data-stu-id="584b8-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="584b8-199">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-199">**Advisory**</span></span>

<span data-ttu-id="584b8-200">Zorg ervoor dat het bereik van MDM-gebruikers is **ingesteld op** **Alles of alles** , niet **none**.</span><span class="sxs-lookup"><span data-stu-id="584b8-200">Make sure the MDM User scope is set to **Some** or **All** , not **None**.</span></span> <span data-ttu-id="584b8-201">Als u **een aantal** kiest, meldt u zich weer na de inschrijving en selecteert u de groep **modern Workplace-all** Azure AD voor **groepen**.</span><span class="sxs-lookup"><span data-stu-id="584b8-201">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="584b8-202">Microsoft Store voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="584b8-202">Microsoft Store for Business</span></span>

<span data-ttu-id="584b8-203">We gebruiken Microsoft Store voor bedrijven, zodat u de bedrijfs portal kunt downloaden om bepaalde apps te implementeren, zoals Microsoft Project en Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="584b8-203">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="584b8-204">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-204">**Not ready**</span></span>

<span data-ttu-id="584b8-205">Microsoft Store voor bedrijven is niet ingeschakeld of wordt niet gesynchroniseerd met intune.</span><span class="sxs-lookup"><span data-stu-id="584b8-205">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="584b8-206">Zie voor meer informatie het artikel [apps gekochte apps in Microsoft Store voor bedrijven beheren met Microsoft intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) en de [intune-bedrijfs portal installeren op een apparaat](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="584b8-206">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="584b8-207">Meervoudige verificatie</span><span class="sxs-lookup"><span data-stu-id="584b8-207">Multi-factor authentication</span></span>

<span data-ttu-id="584b8-208">Meervoudige verificatie mag niet per ongeluk worden toegepast op Microsoft beheerde bureaublad serviceaccounts.</span><span class="sxs-lookup"><span data-stu-id="584b8-208">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="584b8-209">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-209">**Not ready**</span></span>

<span data-ttu-id="584b8-210">U hebt een aantal opties voor het instellen van multi-factor Authentication (MFA) ingesteld voor het beleid voor voorwaardelijke toegang dat aan alle gebruikers wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="584b8-210">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="584b8-211">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="584b8-211">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="584b8-212">Zie voor meer informatie [beleidsregels voor voorwaardelijke toegang](#conditional-access-policies) en [voorwaardelijke toegang: MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="584b8-212">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="584b8-213">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-213">**Advisory**</span></span>

<span data-ttu-id="584b8-214">Zorg ervoor dat voor beleidsregels voor voorwaardelijke toegang de optie MFA moet **zijn opgenomen:** de groep alle Azure AD.</span><span class="sxs-lookup"><span data-stu-id="584b8-214">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="584b8-215">Zie voor meer informatie [beleidsregels voor voorwaardelijke toegang](#conditional-access-policies) en [voorwaardelijke toegang: MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="584b8-215">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="584b8-216">De **modern Workplace-all** Azure AD-groep is een dynamische groep die we maken wanneer u zich registreert bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.</span><span class="sxs-lookup"><span data-stu-id="584b8-216">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="584b8-217">**Fout**</span><span class="sxs-lookup"><span data-stu-id="584b8-217">**Error**</span></span>

<span data-ttu-id="584b8-218">De rol intune-beheerder heeft onvoldoende machtigingen voor deze controle.</span><span class="sxs-lookup"><span data-stu-id="584b8-218">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="584b8-219">U hebt ook een van de volgende Azure AD-rollen nodig die zijn toegewezen om deze controle uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="584b8-219">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="584b8-220">Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="584b8-220">Security Reader</span></span>
- <span data-ttu-id="584b8-221">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="584b8-221">Security Administrator</span></span>
- <span data-ttu-id="584b8-222">Beheerder van voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="584b8-222">Conditional Access Administrator</span></span>
- <span data-ttu-id="584b8-223">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="584b8-223">Global Reader</span></span>
- <span data-ttu-id="584b8-224">Apparaten beheerder</span><span class="sxs-lookup"><span data-stu-id="584b8-224">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="584b8-225">PowerShell-scripts</span><span class="sxs-lookup"><span data-stu-id="584b8-225">PowerShell scripts</span></span>

<span data-ttu-id="584b8-226">Windows PowerShell-scripts kunnen niet worden toegewezen in de manier waarop Microsoft beheerde bureaublad apparaten kunnen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="584b8-226">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="584b8-227">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-227">**Advisory**</span></span>

<span data-ttu-id="584b8-228">Zorg ervoor dat Windows PowerShell-scripts in uw Azure AD-organisatie geen Microsoft-bureaublad apparaten of-gebruikers beheren.</span><span class="sxs-lookup"><span data-stu-id="584b8-228">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="584b8-229">Wijs geen PowerShell-script toe om alle gebruikers, alle apparaten of beide te bereiken.</span><span class="sxs-lookup"><span data-stu-id="584b8-229">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="584b8-230">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="584b8-230">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="584b8-231">Zie [PowerShell-scripts op Windows 10-apparaten gebruiken in intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-231">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="584b8-232">Regio</span><span class="sxs-lookup"><span data-stu-id="584b8-232">Region</span></span>

<span data-ttu-id="584b8-233">Uw regio moet worden ondersteund door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="584b8-233">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="584b8-234">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-234">**Not ready**</span></span>

<span data-ttu-id="584b8-235">Uw regio van Azure AD organisatie wordt momenteel niet ondersteund door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="584b8-235">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="584b8-236">Zie [ondersteunde regio's en talen door Microsoft worden beheerd op het bureaublad](../service-description/regions-languages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-236">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="584b8-237">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-237">**Advisory**</span></span>

<span data-ttu-id="584b8-238">Een of meer van de landen waar uw Azure AD organisatie zich bevindt, wordt niet ondersteund door het door Microsoft beheerde bureaublad.</span><span class="sxs-lookup"><span data-stu-id="584b8-238">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="584b8-239">Zie [ondersteunde regio's en talen door Microsoft worden beheerd op het bureaublad](../service-description/regions-languages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-239">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="584b8-240">Basislijnen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="584b8-240">Security baselines</span></span>

<span data-ttu-id="584b8-241">Beleidsregels voor beveiliging van basislijn dienen niet te worden beheerd door Microsoft beheerde bureaublad apparaten.</span><span class="sxs-lookup"><span data-stu-id="584b8-241">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="584b8-242">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-242">**Not ready**</span></span>

<span data-ttu-id="584b8-243">U hebt een profiel voor beveiligings basislijn voor alle gebruikers, alle apparaten of beide.</span><span class="sxs-lookup"><span data-stu-id="584b8-243">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="584b8-244">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="584b8-244">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="584b8-245">Zie [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="584b8-245">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="584b8-246">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-246">**Advisory**</span></span>

<span data-ttu-id="584b8-247">Zorg dat beleidsregels voor beveiliging op basis van Microsoft beheerde bureaublad apparaten zijn uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="584b8-247">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="584b8-248">Zie [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="584b8-248">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="584b8-249">De **moderne werkplekken-** de groep Azure AD is een dynamische groep die we maken wanneer u zich aanmeldt bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.</span><span class="sxs-lookup"><span data-stu-id="584b8-249">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="584b8-250">Windows-apps</span><span class="sxs-lookup"><span data-stu-id="584b8-250">Windows apps</span></span>

<span data-ttu-id="584b8-251">Bekijk de apps waarover u Microsoft beheerde bureaubladgebruikers wilt hebben.</span><span class="sxs-lookup"><span data-stu-id="584b8-251">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="584b8-252">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-252">**Advisory**</span></span>

<span data-ttu-id="584b8-253">U moet een inventarisatie voorbereiden van de apps die u wilt laten door Microsoft beheerde bureaubladgebruikers.</span><span class="sxs-lookup"><span data-stu-id="584b8-253">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="584b8-254">Zorg ervoor dat deze apps kunnen worden geïmplementeerd door intune.</span><span class="sxs-lookup"><span data-stu-id="584b8-254">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="584b8-255">Zie [apps in Microsoft Managed Desktop](apps.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-255">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="584b8-256">U kunt de vertegenwoordiger van uw Microsoft-account vragen om te bepalen welke apps gereed zijn om te worden gemigreerd naar intune of een correctie.</span><span class="sxs-lookup"><span data-stu-id="584b8-256">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="584b8-257">Windows Hello voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="584b8-257">Windows Hello for Business</span></span>

<span data-ttu-id="584b8-258">Voor Microsoft Managed Desktop is Windows hello voor bedrijven ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="584b8-258">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="584b8-259">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-259">**Not ready**</span></span>

<span data-ttu-id="584b8-260">Windows hello voor bedrijven is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="584b8-260">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="584b8-261">Activeren door de stappen te volgen in [een beleid voor Windows hello voor bedrijven maken](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="584b8-261">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="584b8-262">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-262">**Advisory**</span></span>

<span data-ttu-id="584b8-263">Windows hello voor bedrijven is niet ingesteld.</span><span class="sxs-lookup"><span data-stu-id="584b8-263">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="584b8-264">Schakel deze optie in door de stappen te volgen in [een beleid voor Windows hello voor bedrijven maken](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="584b8-264">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="584b8-265">Windows 10-update ringen</span><span class="sxs-lookup"><span data-stu-id="584b8-265">Windows 10 update rings</span></span>

<span data-ttu-id="584b8-266">Het beleid Windows 10-update ring in intune mag geen Microsoft-bureaublad apparaten met Microsoft worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="584b8-266">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="584b8-267">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-267">**Not ready**</span></span>

<span data-ttu-id="584b8-268">U hebt een beleid voor het bijwerken van een update voor alle apparaten, alle gebruikers of beide.</span><span class="sxs-lookup"><span data-stu-id="584b8-268">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="584b8-269">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="584b8-269">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="584b8-270">Zie [updates voor Windows 10-software beheren in intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="584b8-270">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="584b8-271">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-271">**Advisory**</span></span>

<span data-ttu-id="584b8-272">Zorg ervoor dat bij een update ring beleid u de **moderne werkplek, alle** Azure AD-groep, hebt uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="584b8-272">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="584b8-273">Zie [updates voor Windows 10-software beheren in intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="584b8-273">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="584b8-274">De **moderne werkplekken-** de groep Azure AD is een dynamische groep die we maken wanneer u zich aanmeldt bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.</span><span class="sxs-lookup"><span data-stu-id="584b8-274">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="584b8-275">Azure Active Directory-instellingen</span><span class="sxs-lookup"><span data-stu-id="584b8-275">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="584b8-276">Ad hoc-abonnementen</span><span class="sxs-lookup"><span data-stu-id="584b8-276">Ad hoc subscriptions</span></span>

<span data-ttu-id="584b8-277">Adviseert het controleren van een instelling die (indien ingesteld op ' onwaar ') kan voorkomen dat roaming via Enterprise niet goed werkt.</span><span class="sxs-lookup"><span data-stu-id="584b8-277">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="584b8-278">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-278">**Advisory**</span></span>

<span data-ttu-id="584b8-279">Zorg ervoor dat **AllowAdHocSubscriptions** is ingesteld op **waar**.</span><span class="sxs-lookup"><span data-stu-id="584b8-279">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="584b8-280">Anders werkt Enterprise State roaming mogelijk niet.</span><span class="sxs-lookup"><span data-stu-id="584b8-280">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="584b8-281">Zie [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-281">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="584b8-282">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="584b8-282">Enterprise State Roaming</span></span>

<span data-ttu-id="584b8-283">Enterprise State roaming moet zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="584b8-283">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="584b8-284">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-284">**Advisory**</span></span>

<span data-ttu-id="584b8-285">Zorg ervoor dat roaming voor bedrijven is ingeschakeld voor **alle** of voor **geselecteerde** groepen.</span><span class="sxs-lookup"><span data-stu-id="584b8-285">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="584b8-286">Zie [Enterprise State roaming inschakelen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-286">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="584b8-287">Licenties</span><span class="sxs-lookup"><span data-stu-id="584b8-287">Licenses</span></span>

<span data-ttu-id="584b8-288">U moet een aantal licenties gebruiken om Microsoft Managed Desktop te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="584b8-288">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="584b8-289">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-289">**Not Ready**</span></span>

<span data-ttu-id="584b8-290">U hebt niet alle licenties die u nodig hebt om Microsoft Managed Desktop te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="584b8-290">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="584b8-291">Zie [Microsoft Managed Desktop Technologies](../intro/technologies.md) en meer informatie [over licenties](prerequisites.md#more-about-licenses)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-291">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="584b8-292">Namen van beveiligingsaccounts</span><span class="sxs-lookup"><span data-stu-id="584b8-292">Security account names</span></span>

<span data-ttu-id="584b8-293">Het is mogelijk dat de namen van bepaalde beveiligingsaccounts conflicteren met die van Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="584b8-293">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="584b8-294">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-294">**Not ready**</span></span>

<span data-ttu-id="584b8-295">U hebt minimaal één accountnaam waarvan de naam afwijkt van de naam die wordt gemaakt door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="584b8-295">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="584b8-296">Met de vertegenwoordiger van uw Microsoft-account kunt u deze accountnamen uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="584b8-296">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="584b8-297">Rollen van beveiligingsbeheerders</span><span class="sxs-lookup"><span data-stu-id="584b8-297">Security administrator roles</span></span>

<span data-ttu-id="584b8-298">Gebruikers met bepaalde beveiligingsrollen moeten de toewijzingen in Microsoft Defender voor eindpunten hebben.</span><span class="sxs-lookup"><span data-stu-id="584b8-298">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="584b8-299">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-299">**Advisory**</span></span>

<span data-ttu-id="584b8-300">Als u een van deze rollen hebt toegewezen aan uw Azure AD-organisatie, moet u ervoor zorgen dat deze rollen ook zijn toegewezen in Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="584b8-300">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="584b8-301">Anders hebben beheerders met deze rollen geen toegang tot de beheerportal.</span><span class="sxs-lookup"><span data-stu-id="584b8-301">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="584b8-302">Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="584b8-302">Security Reader</span></span>
- <span data-ttu-id="584b8-303">Beveiligings operator</span><span class="sxs-lookup"><span data-stu-id="584b8-303">Security Operator</span></span>
- <span data-ttu-id="584b8-304">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="584b8-304">Global Reader</span></span>

<span data-ttu-id="584b8-305">Zie [rollen voor toegangsbeheer op basis van rollen maken en beheren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584b8-305">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="584b8-306">Beveiligingsstandaard</span><span class="sxs-lookup"><span data-stu-id="584b8-306">Security default</span></span>

<span data-ttu-id="584b8-307">Met behulp van de beveiligingsinstellingen in azure Active Directory wordt voorkomen dat Microsoft beheerd bureaublad uw apparaten beheert.</span><span class="sxs-lookup"><span data-stu-id="584b8-307">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="584b8-308">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="584b8-308">**Not ready**</span></span>

<span data-ttu-id="584b8-309">U hebt beveiligingsstandaarden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="584b8-309">You have Security defaults turned on.</span></span> <span data-ttu-id="584b8-310">Schakel beveiligingsstandaarden uit en stel beleidsregels voor voorwaardelijke toegang in.</span><span class="sxs-lookup"><span data-stu-id="584b8-310">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="584b8-311">Zie voor meer informatie [veelgebruikte beleidsregels voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="584b8-311">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="584b8-312">Selfservice voor wachtwoordherstel</span><span class="sxs-lookup"><span data-stu-id="584b8-312">Self-service Password Reset</span></span>

<span data-ttu-id="584b8-313">U moet selfservice voor wachtwoordherstel (SSPR) inschakelen voor alle gebruikers, met uitzondering van Microsoft Managed Desktop service-accounts.</span><span class="sxs-lookup"><span data-stu-id="584b8-313">Self-service Password Reset (SSPR) should be enabled for all users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="584b8-314">Zie [Zelfstudie: gebruikers toestaan hun account te ontgrendelen of wachtwoorden opnieuw in te stellen met behulp van Azure Active Directory-wachtwoordherstel](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="584b8-314">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="584b8-315">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-315">**Advisory**</span></span>

<span data-ttu-id="584b8-316">Zorg ervoor dat de **geselecteerde** instelling voor SSPR Microsoft beheerde bureaublad apparaten bevat, maar dat Microsoft beheerde bureaublad-serviceaccounts niet is opgenomen.</span><span class="sxs-lookup"><span data-stu-id="584b8-316">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="584b8-317">Accounts van Microsoft beheerde bureaubladservices werken niet zoals verwacht wanneer SSPR is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="584b8-317">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="584b8-318">Standaard gebruikersrol</span><span class="sxs-lookup"><span data-stu-id="584b8-318">Standard user role</span></span>

<span data-ttu-id="584b8-319">Behalve de gebruikers die een Azure AD-rol van globale beheerder en een andere netwerkbeheerder toegewezen, zijn Microsoft-beheerde bureaubladgebruikers standaardgebruikers zonder lokale beheerdersbevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="584b8-319">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="584b8-320">Voor alle andere gebruikers wordt een standaard gebruikersrol toegewezen wanneer ze hun Microsoft-beheerde bureaublad apparaat starten.</span><span class="sxs-lookup"><span data-stu-id="584b8-320">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="584b8-321">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-321">**Advisory**</span></span>

<span data-ttu-id="584b8-322">Microsoft beheerde bureaubladgebruikers hebben geen lokale beheerdersbevoegdheden op hun Microsoft beheerde bureaublad apparaten na registratie.</span><span class="sxs-lookup"><span data-stu-id="584b8-322">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="584b8-323">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="584b8-323">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="584b8-324">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="584b8-324">OneDrive for Business</span></span>

<span data-ttu-id="584b8-325">De instelling voor **synchronisatie alleen toestaan op pc's die lid zijn van een specifieke domein** instelling, conflicteert met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="584b8-325">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="584b8-326">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="584b8-326">**Advisory**</span></span>

<span data-ttu-id="584b8-327">U gebruikt de instelling **synchronisatie alleen toestaan op pc's die lid zijn van bepaalde domeinen** .</span><span class="sxs-lookup"><span data-stu-id="584b8-327">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="584b8-328">Deze instelling werkt niet met beheerde Microsoft-bureaublad.</span><span class="sxs-lookup"><span data-stu-id="584b8-328">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="584b8-329">Schakel deze instelling uit en zet OneDrive voor bedrijven zodanig op dat deze gebruikmaakt van een voorwaardelijk toegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="584b8-329">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="584b8-330">Zie [voorwaardelijke toegang plannen](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="584b8-330">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

