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
ms.openlocfilehash: 2c9638dc7b8c6d095b87cf81114f3812c8362597
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656131"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="8831f-104">Problemen gevonden met het hulpprogramma voor gereedheids beoordeling</span><span class="sxs-lookup"><span data-stu-id="8831f-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="8831f-105">Voor elke controle wordt in het hulpmiddel een van de drie mogelijke resultaten weergegeven:</span><span class="sxs-lookup"><span data-stu-id="8831f-105">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="8831f-106">Resultaat</span><span class="sxs-lookup"><span data-stu-id="8831f-106">Result</span></span>  |<span data-ttu-id="8831f-107">Betekenis</span><span class="sxs-lookup"><span data-stu-id="8831f-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="8831f-108">Gereedgemaakt</span><span class="sxs-lookup"><span data-stu-id="8831f-108">Ready</span></span>     | <span data-ttu-id="8831f-109">U hoeft geen actie te ondernemen voordat u de registratie uitvoert.</span><span class="sxs-lookup"><span data-stu-id="8831f-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="8831f-110">Adviser</span><span class="sxs-lookup"><span data-stu-id="8831f-110">Advisory</span></span>    | <span data-ttu-id="8831f-111">Voer de stappen in het hulpprogramma of dit artikel uit voor de beste ervaring met inschrijving en voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8831f-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="8831f-112">U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.</span><span class="sxs-lookup"><span data-stu-id="8831f-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="8831f-113">Niet gereed</span><span class="sxs-lookup"><span data-stu-id="8831f-113">Not ready</span></span> | <span data-ttu-id="8831f-114">*De registratie mislukt als u deze problemen niet oplost.*</span><span class="sxs-lookup"><span data-stu-id="8831f-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="8831f-115">Voer de stappen in het hulpprogramma of dit artikel uit om ze op te lossen.</span><span class="sxs-lookup"><span data-stu-id="8831f-115">Follow the steps in the tool or this article to resolve them.</span></span>        |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="8831f-116">Microsoft intune-instellingen</span><span class="sxs-lookup"><span data-stu-id="8831f-116">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="8831f-117">Auto Pilot-implementatie profiel</span><span class="sxs-lookup"><span data-stu-id="8831f-117">Autopilot deployment profile</span></span>

<span data-ttu-id="8831f-118">U hebt geen bestaande auto pilot-profielen die door Microsoft beheerde bureaublad worden toegewezen of dynamische groepen die door Microsoft worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="8831f-118">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="8831f-119">Microsoft Managed Desktop gebruikt auto pilot om nieuwe apparaten te creëren.</span><span class="sxs-lookup"><span data-stu-id="8831f-119">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="8831f-120">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-120">**Not ready**</span></span>

<span data-ttu-id="8831f-121">U hebt een auto pilot-profiel dat is toegewezen aan alle apparaten.</span><span class="sxs-lookup"><span data-stu-id="8831f-121">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="8831f-122">Zie [Windows-apparaten in intune registreren met behulp van Windows auto pilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="8831f-122">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="8831f-123">Wanneer de Microsoft-bureaublad registratie voor het bureaublad is ingeschakeld, stelt u uw auto pilot-beleid in om de **moderne werkplekken te uitsluiten: alle** Azure AD-groep.</span><span class="sxs-lookup"><span data-stu-id="8831f-123">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="8831f-124">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-124">**Advisory**</span></span>

<span data-ttu-id="8831f-125">Zorg ervoor dat uw auto pilot-profielen een toegewezen of dynamische Azure AD-groep betreffen die geen door Microsoft beheerde bureaublad apparaten bevat die worden gemaakt bij het registreren.</span><span class="sxs-lookup"><span data-stu-id="8831f-125">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="8831f-126">Zie [Windows-apparaten in intune registreren met behulp van Windows auto pilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="8831f-126">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="8831f-127">Wanneer de Microsoft-bureaublad registratie voor het bureaublad is ingeschakeld, stelt u uw auto pilot-beleid in om de **moderne werkplekken te uitsluiten: alle** Azure AD-groep.</span><span class="sxs-lookup"><span data-stu-id="8831f-127">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="8831f-128">Certificaat verbindingslijnen</span><span class="sxs-lookup"><span data-stu-id="8831f-128">Certificate connectors</span></span>

<span data-ttu-id="8831f-129">Als u certificaat verbindingslijnen hebt die worden gebruikt door de apparaten die u wilt registreren op Microsoft Managed Desktop, zijn de connectors geen fouten.</span><span class="sxs-lookup"><span data-stu-id="8831f-129">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="8831f-130">Slechts één van de volgende adviseurs is op uw situatie van toepassing, dus controleer ze aandachtig.</span><span class="sxs-lookup"><span data-stu-id="8831f-130">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="8831f-131">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-131">**Advisory**</span></span>

<span data-ttu-id="8831f-132">Er zijn geen certificaat connectors aanwezig.</span><span class="sxs-lookup"><span data-stu-id="8831f-132">No certificate connectors are present.</span></span> <span data-ttu-id="8831f-133">Het is mogelijk dat u geen connectors nodig hebt, maar u moet eerst beoordelen of u een netwerkverbinding met Microsoft beheerde bureaublad apparaten nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="8831f-133">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8831f-134">Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-134">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="8831f-135">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-135">**Advisory**</span></span>

<span data-ttu-id="8831f-136">Minstens één certificaatconnector bevat een fout.</span><span class="sxs-lookup"><span data-stu-id="8831f-136">At least one certificate connector has an error.</span></span> <span data-ttu-id="8831f-137">Als u deze connector nodig hebt voor connectiviteit met Microsoft Managed Desktop-apparaten, moet u de fout oplossen.</span><span class="sxs-lookup"><span data-stu-id="8831f-137">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="8831f-138">Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-138">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="8831f-139">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-139">**Advisory**</span></span>

<span data-ttu-id="8831f-140">U moet minimaal één certificaatconnector en geen fouten rapporteren.</span><span class="sxs-lookup"><span data-stu-id="8831f-140">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="8831f-141">U kunt echter wel een profiel maken om de connector voor Microsoft beheerde bureaublad apparaten opnieuw te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8831f-141">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8831f-142">Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-142">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="8831f-143">Beleidsregels voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="8831f-143">Conditional access policies</span></span>

<span data-ttu-id="8831f-144">Het beleid voor voorwaardelijke toegang in uw Azure AD-organisatie mag geen Microsoft-bureaubladgebruikers bedoelen.</span><span class="sxs-lookup"><span data-stu-id="8831f-144">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="8831f-145">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-145">**Not ready**</span></span>

<span data-ttu-id="8831f-146">U hebt ten minste één beleid voor voorwaardelijke toegang voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8831f-146">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="8831f-147">Stel het beleid opnieuw in om een specifieke Azure AD-groep met de Azure AD-groep met Microsoft Managed Desktop service-accounts die worden gemaakt bij het registreren, niet te omvatten.</span><span class="sxs-lookup"><span data-stu-id="8831f-147">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="8831f-148">Zie voor de stappen [voorwaardelijke toegang: gebruikers en groepen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="8831f-148">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="8831f-149">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-149">**Advisory**</span></span>

<span data-ttu-id="8831f-150">Zorg ervoor dat u een beleidsregels voor voorwaardelijke toegang hebt uitgesloten met de Azure AD-groep voor de **moderne service accounts** .</span><span class="sxs-lookup"><span data-stu-id="8831f-150">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="8831f-151">Zie [voorwaardelijke toegang aanpassen](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)voor de stappen.</span><span class="sxs-lookup"><span data-stu-id="8831f-151">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="8831f-152">De **modern Workplace service accounts** Azure Ad Group is een dynamische groep die we voor de service maken wanneer u zich registreert.</span><span class="sxs-lookup"><span data-stu-id="8831f-152">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="8831f-153">U dient na de inschrijving weer de groep uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="8831f-153">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="8831f-154">Zie voor meer informatie over deze serviceaccounts [standaardprocedures](../service-description/operations-and-monitoring.md#standard-operating-procedures)voor het werk.</span><span class="sxs-lookup"><span data-stu-id="8831f-154">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="8831f-155">Nalevingsbeleid voor apparaten</span><span class="sxs-lookup"><span data-stu-id="8831f-155">Device Compliance policies</span></span>

<span data-ttu-id="8831f-156">Het beleid voor naleving van intune-apparaten in de Azure AD-organisatie mag geen door Microsoft beheerde bureaubladgebruikers afstemmen.</span><span class="sxs-lookup"><span data-stu-id="8831f-156">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="8831f-157">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-157">**Not ready**</span></span>

<span data-ttu-id="8831f-158">U hebt ten minste één nalevingsbeleid voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8831f-158">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="8831f-159">Stel het beleid opnieuw in om een specifieke Azure AD-groep te richten die geen Microsoft-beheerde bureaubladgebruikers omvat.</span><span class="sxs-lookup"><span data-stu-id="8831f-159">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="8831f-160">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="8831f-160">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="8831f-161">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-161">**Advisory**</span></span>

<span data-ttu-id="8831f-162">Zorg ervoor dat het nalevingsbeleid van Microsoft beheerde bureaubladgebruikers niet omvat.</span><span class="sxs-lookup"><span data-stu-id="8831f-162">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="8831f-163">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="8831f-163">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="8831f-164">Beleidsregels voor apparaatconfiguratie</span><span class="sxs-lookup"><span data-stu-id="8831f-164">Device Configuration policies</span></span>

<span data-ttu-id="8831f-165">Het beleid voor het configureren van intune-apparaten in de Azure AD-organisatie mag geen Microsoft-bureaublad apparaten of-gebruikers beheren.</span><span class="sxs-lookup"><span data-stu-id="8831f-165">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="8831f-166">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-166">**Not ready**</span></span>

<span data-ttu-id="8831f-167">U hebt minimaal één configuratiebeleid voor alle gebruikers, alle apparaten of beide.</span><span class="sxs-lookup"><span data-stu-id="8831f-167">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="8831f-168">Stel het beleid opnieuw in om een specifieke Azure AD-groep te richten die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="8831f-168">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8831f-169">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="8831f-169">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="8831f-170">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-170">**Advisory**</span></span>

<span data-ttu-id="8831f-171">Zorg ervoor dat het nalevingsbeleid van Microsoft beheerde bureaublad apparaten of gebruikers niet omvat.</span><span class="sxs-lookup"><span data-stu-id="8831f-171">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="8831f-172">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="8831f-172">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="8831f-173">Beperkingen voor apparaattype</span><span class="sxs-lookup"><span data-stu-id="8831f-173">Device type restrictions</span></span>

<span data-ttu-id="8831f-174">Door Microsoft beheerde bureaublad apparaten moet u zich kunnen registreren bij intune.</span><span class="sxs-lookup"><span data-stu-id="8831f-174">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="8831f-175">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-175">**Not ready**</span></span>

<span data-ttu-id="8831f-176">Voer de stappen uit in de optie voor het [instellen van inschrijving](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) om de **instelling toe te passen.**</span><span class="sxs-lookup"><span data-stu-id="8831f-176">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="8831f-177">Pagina met inschrijvings status</span><span class="sxs-lookup"><span data-stu-id="8831f-177">Enrollment Status Page</span></span>

<span data-ttu-id="8831f-178">U hebt momenteel de pagina met de inschrijvings status (ESP) ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8831f-178">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="8831f-179">Als u deelneemt aan de openbare preview van deze functie, kunt u dit item negeren.</span><span class="sxs-lookup"><span data-stu-id="8831f-179">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="8831f-180">Zie [First Run-ervaring met auto pilot en de pagina inschrijvings status](../get-started/esp-first-run.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-180">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="8831f-181">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-181">**Not ready**</span></span>

<span data-ttu-id="8831f-182">Voor het weergeven van de voortgang van de **apps en profielen**moet u de standaard-ESP-profielset opgeven.</span><span class="sxs-lookup"><span data-stu-id="8831f-182">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="8831f-183">Schakel deze instelling uit door de stappen te volgen in [de pagina inschrijvings status instellen](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="8831f-183">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="8831f-184">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-184">**Advisory**</span></span>

<span data-ttu-id="8831f-185">Zorg ervoor dat profielen met de instelling **voortgang van app en profielconfiguratie weergeven** niet zijn toegewezen aan een Azure AD-groep die Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="8831f-185">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8831f-186">Zie [de pagina inschrijvings status instellen](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-186">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="8831f-187">InTune-registratie</span><span class="sxs-lookup"><span data-stu-id="8831f-187">Intune enrollment</span></span>

<span data-ttu-id="8831f-188">Windows 10-apparaten in uw Azure AD-organisatie moeten automatisch worden geregistreerd in intune.</span><span class="sxs-lookup"><span data-stu-id="8831f-188">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="8831f-189">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-189">**Not ready**</span></span>

<span data-ttu-id="8831f-190">Gebruikers in uw Azure AD-organisatie worden niet automatisch ingeschreven in Microsoft intune.</span><span class="sxs-lookup"><span data-stu-id="8831f-190">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="8831f-191">Het MDM-gebruikers bereik wijzigen **in** **Alles of alles**.</span><span class="sxs-lookup"><span data-stu-id="8831f-191">Change the MDM User scope to **Some** or **All**.</span></span> <span data-ttu-id="8831f-192">Als u dit kiest.</span><span class="sxs-lookup"><span data-stu-id="8831f-192">If you choose.</span></span> <span data-ttu-id="8831f-193">Sommige \* \*, komen na de inschrijving en selecteert u de groep **modern werk, alle** Azure AD-groep voor **groepen**.</span><span class="sxs-lookup"><span data-stu-id="8831f-193">Some\*\*, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="8831f-194">Microsoft Store voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="8831f-194">Microsoft Store for Business</span></span>

<span data-ttu-id="8831f-195">We gebruiken Microsoft Store voor bedrijven, zodat u de bedrijfs portal kunt downloaden om bepaalde apps te implementeren, zoals Microsoft Project en Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="8831f-195">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="8831f-196">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-196">**Not ready**</span></span>

<span data-ttu-id="8831f-197">Microsoft Store voor bedrijven is niet ingeschakeld of wordt niet gesynchroniseerd met intune.</span><span class="sxs-lookup"><span data-stu-id="8831f-197">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="8831f-198">Zie voor meer informatie het artikel [apps gekochte apps in Microsoft Store voor bedrijven beheren met Microsoft intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) en de [intune-bedrijfs portal installeren op een apparaat](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="8831f-198">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="8831f-199">Meervoudige verificatie</span><span class="sxs-lookup"><span data-stu-id="8831f-199">Multi-factor authentication</span></span>

<span data-ttu-id="8831f-200">Meervoudige verificatie mag niet per ongeluk worden toegepast op Microsoft beheerde bureaublad serviceaccounts.</span><span class="sxs-lookup"><span data-stu-id="8831f-200">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="8831f-201">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-201">**Not ready**</span></span>

<span data-ttu-id="8831f-202">U hebt een aantal opties voor het instellen van multi-factor Authentication (MFA) ingesteld voor het beleid voor voorwaardelijke toegang dat aan alle gebruikers wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="8831f-202">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="8831f-203">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="8831f-203">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8831f-204">Zie voor meer informatie [beleidsregels voor voorwaardelijke toegang](#conditional-access-policies) en [voorwaardelijke toegang: MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="8831f-204">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="8831f-205">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-205">**Advisory**</span></span>

<span data-ttu-id="8831f-206">Zorg ervoor dat voor beleidsregels voor voorwaardelijke toegang de optie MFA moet **zijn opgenomen:** de groep alle Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8831f-206">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="8831f-207">Zie voor meer informatie [beleidsregels voor voorwaardelijke toegang](#conditional-access-policies) en [voorwaardelijke toegang: MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="8831f-207">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="8831f-208">De **modern Workplace-all** Azure AD-groep is een dynamische groep die we maken wanneer u zich registreert bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.</span><span class="sxs-lookup"><span data-stu-id="8831f-208">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>



### <a name="powershell-scripts"></a><span data-ttu-id="8831f-209">PowerShell-scripts</span><span class="sxs-lookup"><span data-stu-id="8831f-209">PowerShell scripts</span></span>

<span data-ttu-id="8831f-210">Windows PowerShell-scripts kunnen niet worden toegewezen in de manier waarop Microsoft beheerde bureaublad apparaten kunnen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="8831f-210">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="8831f-211">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-211">**Advisory**</span></span>

<span data-ttu-id="8831f-212">Zorg ervoor dat Windows PowerShell-scripts in uw Azure AD-organisatie geen Microsoft-bureaublad apparaten of-gebruikers beheren.</span><span class="sxs-lookup"><span data-stu-id="8831f-212">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="8831f-213">Zie [PowerShell-scripts op Windows 10-apparaten gebruiken in intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-213">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="8831f-214">Regio</span><span class="sxs-lookup"><span data-stu-id="8831f-214">Region</span></span>

<span data-ttu-id="8831f-215">Uw regio moet worden ondersteund door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="8831f-215">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="8831f-216">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-216">**Not ready**</span></span>

<span data-ttu-id="8831f-217">Uw regio van Azure AD organisatie wordt momenteel niet ondersteund door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="8831f-217">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="8831f-218">Zie [ondersteunde regio's en talen door Microsoft worden beheerd op het bureaublad](../service-description/regions-languages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-218">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="8831f-219">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-219">**Advisory**</span></span>

<span data-ttu-id="8831f-220">Een of meer van de landen waar uw Azure AD organisatie zich bevindt, wordt niet ondersteund door het door Microsoft beheerde bureaublad.</span><span class="sxs-lookup"><span data-stu-id="8831f-220">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="8831f-221">Zie [ondersteunde regio's en talen door Microsoft worden beheerd op het bureaublad](../service-description/regions-languages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-221">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="8831f-222">Basislijnen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="8831f-222">Security baselines</span></span>

<span data-ttu-id="8831f-223">Beleidsregels voor beveiliging van basislijn dienen niet te worden beheerd door Microsoft beheerde bureaublad apparaten.</span><span class="sxs-lookup"><span data-stu-id="8831f-223">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="8831f-224">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-224">**Not ready**</span></span>

<span data-ttu-id="8831f-225">U hebt een profiel voor beveiligings basislijn voor alle gebruikers, alle apparaten of beide.</span><span class="sxs-lookup"><span data-stu-id="8831f-225">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="8831f-226">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="8831f-226">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8831f-227">Zie [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="8831f-227">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="8831f-228">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-228">**Advisory**</span></span>

<span data-ttu-id="8831f-229">Zorg dat beleidsregels voor beveiliging op basis van Microsoft beheerde bureaublad apparaten zijn uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="8831f-229">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8831f-230">Zie [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="8831f-230">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="8831f-231">De **moderne werkplekken-** de groep Azure AD is een dynamische groep die we maken wanneer u zich aanmeldt bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.</span><span class="sxs-lookup"><span data-stu-id="8831f-231">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="8831f-232">Windows-apps</span><span class="sxs-lookup"><span data-stu-id="8831f-232">Windows apps</span></span>

<span data-ttu-id="8831f-233">Bekijk de apps waarover u Microsoft beheerde bureaubladgebruikers wilt hebben.</span><span class="sxs-lookup"><span data-stu-id="8831f-233">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="8831f-234">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-234">**Advisory**</span></span>

<span data-ttu-id="8831f-235">U moet een inventarisatie voorbereiden van de apps die u wilt laten door Microsoft beheerde bureaubladgebruikers.</span><span class="sxs-lookup"><span data-stu-id="8831f-235">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="8831f-236">Zorg ervoor dat deze apps kunnen worden geïmplementeerd door intune.</span><span class="sxs-lookup"><span data-stu-id="8831f-236">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="8831f-237">Zie [apps in Microsoft Managed Desktop](apps.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-237">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="8831f-238">U kunt de vertegenwoordiger van uw Microsoft-account vragen om te bepalen welke apps gereed zijn om te worden gemigreerd naar intune of een correctie.</span><span class="sxs-lookup"><span data-stu-id="8831f-238">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="8831f-239">Windows Hello voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="8831f-239">Windows Hello for Business</span></span>

<span data-ttu-id="8831f-240">Voor Microsoft Managed Desktop is Windows hello voor bedrijven ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8831f-240">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="8831f-241">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-241">**Not ready**</span></span>

<span data-ttu-id="8831f-242">Windows hello voor bedrijven is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8831f-242">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="8831f-243">Activeren door de stappen te volgen in [een beleid voor Windows hello voor bedrijven maken](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="8831f-243">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="8831f-244">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-244">**Advisory**</span></span>

<span data-ttu-id="8831f-245">Windows hello voor bedrijven is niet ingesteld.</span><span class="sxs-lookup"><span data-stu-id="8831f-245">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="8831f-246">Schakel deze optie in door de stappen te volgen in [een beleid voor Windows hello voor bedrijven maken](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="8831f-246">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="8831f-247">Windows 10-update ringen</span><span class="sxs-lookup"><span data-stu-id="8831f-247">Windows 10 update rings</span></span>

<span data-ttu-id="8831f-248">Het beleid Windows 10-update ring in intune mag geen Microsoft-bureaublad apparaten met Microsoft worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="8831f-248">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="8831f-249">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-249">**Not ready**</span></span>

<span data-ttu-id="8831f-250">U hebt een beleid voor het bijwerken van een update voor alle apparaten, alle gebruikers of beide.</span><span class="sxs-lookup"><span data-stu-id="8831f-250">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="8831f-251">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="8831f-251">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8831f-252">Zie [updates voor Windows 10-software beheren in intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="8831f-252">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="8831f-253">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-253">**Advisory**</span></span>

<span data-ttu-id="8831f-254">Zorg ervoor dat bij een update ring beleid u de **moderne werkplek, alle** Azure AD-groep, hebt uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="8831f-254">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="8831f-255">Zie [updates voor Windows 10-software beheren in intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="8831f-255">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="8831f-256">De **moderne werkplekken-** de groep Azure AD is een dynamische groep die we maken wanneer u zich aanmeldt bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.</span><span class="sxs-lookup"><span data-stu-id="8831f-256">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="8831f-257">Azure Active Directory-instellingen</span><span class="sxs-lookup"><span data-stu-id="8831f-257">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="8831f-258">Ad hoc-abonnementen</span><span class="sxs-lookup"><span data-stu-id="8831f-258">Ad hoc subscriptions</span></span>

<span data-ttu-id="8831f-259">Adviseert het controleren van een instelling die (indien ingesteld op ' onwaar ') kan voorkomen dat roaming via Enterprise niet goed werkt.</span><span class="sxs-lookup"><span data-stu-id="8831f-259">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="8831f-260">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-260">**Advisory**</span></span>

<span data-ttu-id="8831f-261">Zorg ervoor dat **AllowAdHocSubscriptions** is ingesteld op **waar**.</span><span class="sxs-lookup"><span data-stu-id="8831f-261">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="8831f-262">Anders werkt Enterprise State roaming mogelijk niet.</span><span class="sxs-lookup"><span data-stu-id="8831f-262">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="8831f-263">Zie [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-263">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="8831f-264">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="8831f-264">Enterprise State Roaming</span></span>

<span data-ttu-id="8831f-265">Enterprise State roaming moet zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8831f-265">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="8831f-266">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-266">**Advisory**</span></span>

<span data-ttu-id="8831f-267">Zorg ervoor dat roaming voor bedrijven is ingeschakeld voor **alle** of voor **geselecteerde** groepen.</span><span class="sxs-lookup"><span data-stu-id="8831f-267">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="8831f-268">Zie [Enterprise State roaming inschakelen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-268">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="8831f-269">Licenties</span><span class="sxs-lookup"><span data-stu-id="8831f-269">Licenses</span></span>

<span data-ttu-id="8831f-270">U moet een aantal licenties gebruiken om Microsoft Managed Desktop te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8831f-270">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="8831f-271">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-271">**Not Ready**</span></span>

<span data-ttu-id="8831f-272">U hebt niet alle licenties die u nodig hebt om Microsoft Managed Desktop te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8831f-272">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="8831f-273">Zie [Microsoft Managed Desktop Technologies](../intro/technologies.md) en meer informatie [over licenties](prerequisites.md#more-about-licenses)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-273">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="8831f-274">Namen van beveiligingsaccounts</span><span class="sxs-lookup"><span data-stu-id="8831f-274">Security account names</span></span>

<span data-ttu-id="8831f-275">Het is mogelijk dat de namen van bepaalde beveiligingsaccounts conflicteren met die van Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="8831f-275">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="8831f-276">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-276">**Not ready**</span></span>

<span data-ttu-id="8831f-277">U hebt minimaal één accountnaam waarvan de naam afwijkt van de naam die wordt gemaakt door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="8831f-277">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="8831f-278">Met de vertegenwoordiger van uw Microsoft-account kunt u deze accountnamen uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="8831f-278">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="8831f-279">Rollen van beveiligingsbeheerders</span><span class="sxs-lookup"><span data-stu-id="8831f-279">Security administrator roles</span></span>

<span data-ttu-id="8831f-280">Gebruikers met bepaalde beveiligingsrollen moeten de toewijzingen in Microsoft Defender voor eindpunten hebben.</span><span class="sxs-lookup"><span data-stu-id="8831f-280">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="8831f-281">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-281">**Advisory**</span></span>

<span data-ttu-id="8831f-282">Als u een van deze rollen hebt toegewezen aan uw Azure AD-organisatie, moet u ervoor zorgen dat deze rollen ook zijn toegewezen in Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="8831f-282">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8831f-283">Anders hebben beheerders met deze rollen geen toegang tot de beheerportal.</span><span class="sxs-lookup"><span data-stu-id="8831f-283">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="8831f-284">Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="8831f-284">Security Reader</span></span>
- <span data-ttu-id="8831f-285">Beveiligings operator</span><span class="sxs-lookup"><span data-stu-id="8831f-285">Security Operator</span></span>
- <span data-ttu-id="8831f-286">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="8831f-286">Global Reader</span></span>

<span data-ttu-id="8831f-287">Zie [rollen voor toegangsbeheer op basis van rollen maken en beheren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8831f-287">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="8831f-288">Beveiligingsstandaard</span><span class="sxs-lookup"><span data-stu-id="8831f-288">Security default</span></span>

<span data-ttu-id="8831f-289">Met behulp van de beveiligingsinstellingen in azure Active Directory wordt voorkomen dat Microsoft beheerd bureaublad uw apparaten beheert.</span><span class="sxs-lookup"><span data-stu-id="8831f-289">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="8831f-290">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-290">**Not ready**</span></span>

<span data-ttu-id="8831f-291">U hebt beveiligingsstandaarden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8831f-291">You have Security defaults turned on.</span></span> <span data-ttu-id="8831f-292">Schakel beveiligingsstandaarden uit en stel beleidsregels voor voorwaardelijke toegang in.</span><span class="sxs-lookup"><span data-stu-id="8831f-292">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="8831f-293">Zie voor meer informatie [veelgebruikte beleidsregels voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="8831f-293">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="8831f-294">Selfservice voor wachtwoordherstel</span><span class="sxs-lookup"><span data-stu-id="8831f-294">Self-service Password Reset</span></span>

<span data-ttu-id="8831f-295">Selfservice voor wachtwoordherstel (SSPR) moet zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8831f-295">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="8831f-296">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="8831f-296">**Not ready**</span></span>

<span data-ttu-id="8831f-297">SSPR moet zijn ingeschakeld voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8831f-297">SSPR must be enabled for all users.</span></span> <span data-ttu-id="8831f-298">Als dat niet het geval is, kunnen de Microsoft-services voor beheerde bureaublad accounts niet werken.</span><span class="sxs-lookup"><span data-stu-id="8831f-298">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="8831f-299">Zie [Zelfstudie: gebruikers toestaan hun account te ontgrendelen of wachtwoorden opnieuw in te stellen met behulp van Azure Active Directory-wachtwoordherstel](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="8831f-299">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="8831f-300">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-300">**Advisory**</span></span>

<span data-ttu-id="8831f-301">Zorg ervoor dat de **geselecteerde** instelling voor SSPR Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="8831f-301">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

### <a name="standard-user-role"></a><span data-ttu-id="8831f-302">Standaard gebruikersrol</span><span class="sxs-lookup"><span data-stu-id="8831f-302">Standard user role</span></span>

<span data-ttu-id="8831f-303">Microsoft beheerde bureaubladgebruikers moeten standaardgebruikers zijn zonder lokale beheerdersbevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="8831f-303">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="8831f-304">Er wordt een standaard gebruikersrol toegewezen wanneer het Microsoft-beheerapparaat wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="8831f-304">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="8831f-305">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-305">**Advisory**</span></span>

<span data-ttu-id="8831f-306">Microsoft beheerde bureaubladgebruikers moeten geen lokale beheerdersbevoegdheden hebben voordat ze zich kunnen registreren.</span><span class="sxs-lookup"><span data-stu-id="8831f-306">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="8831f-307">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="8831f-307">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="8831f-308">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="8831f-308">OneDrive for Business</span></span>

<span data-ttu-id="8831f-309">De instelling voor **synchronisatie alleen toestaan op pc's die lid zijn van een specifieke domein** instelling, conflicteert met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="8831f-309">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="8831f-310">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="8831f-310">**Advisory**</span></span>

<span data-ttu-id="8831f-311">U gebruikt de instelling **synchronisatie alleen toestaan op pc's die lid zijn van bepaalde domeinen** .</span><span class="sxs-lookup"><span data-stu-id="8831f-311">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="8831f-312">Deze instelling werkt niet met beheerde Microsoft-bureaublad.</span><span class="sxs-lookup"><span data-stu-id="8831f-312">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="8831f-313">Schakel deze instelling uit en zet OneDrive voor bedrijven zodanig op dat deze gebruikmaakt van een voorwaardelijk toegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="8831f-313">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="8831f-314">Zie [voorwaardelijke toegang plannen](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="8831f-314">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

