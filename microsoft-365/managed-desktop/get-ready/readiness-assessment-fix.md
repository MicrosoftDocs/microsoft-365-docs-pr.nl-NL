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
ms.openlocfilehash: ada6bb8ef66e3414a375a151b45d4871e306e825
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841062"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="9c6eb-104">Los problemen op die door het hulpprogramma voor gereedheidsevaluatie worden gevonden</span><span class="sxs-lookup"><span data-stu-id="9c6eb-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="9c6eb-105">Voor elke controle wordt in het hulpmiddel een van de vier mogelijke resultaten weergegeven:</span><span class="sxs-lookup"><span data-stu-id="9c6eb-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="9c6eb-106">Resultaat</span><span class="sxs-lookup"><span data-stu-id="9c6eb-106">Result</span></span>  |<span data-ttu-id="9c6eb-107">Betekenis</span><span class="sxs-lookup"><span data-stu-id="9c6eb-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="9c6eb-108">Gereedgemaakt</span><span class="sxs-lookup"><span data-stu-id="9c6eb-108">Ready</span></span>     | <span data-ttu-id="9c6eb-109">U hoeft geen actie te ondernemen voordat u de registratie uitvoert.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="9c6eb-110">Adviser</span><span class="sxs-lookup"><span data-stu-id="9c6eb-110">Advisory</span></span>    | <span data-ttu-id="9c6eb-111">Voer de stappen in het hulpprogramma of dit artikel uit voor de beste ervaring met inschrijving en voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="9c6eb-112">U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="9c6eb-113">Niet gereed</span><span class="sxs-lookup"><span data-stu-id="9c6eb-113">Not ready</span></span> | <span data-ttu-id="9c6eb-114">*De registratie mislukt als u deze problemen niet oplost.*</span><span class="sxs-lookup"><span data-stu-id="9c6eb-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="9c6eb-115">Voer de stappen in het hulpprogramma of dit artikel uit om ze op te lossen.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="9c6eb-116">Error</span><span class="sxs-lookup"><span data-stu-id="9c6eb-116">Error</span></span> | <span data-ttu-id="9c6eb-117">De rol van Azure Active Director (AD) die u gebruikt, heeft onvoldoende machtigingen om deze controle uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="9c6eb-118">De resultaten van dit hulpmiddel worden weergegeven op de status van uw instellingen op een bepaald moment dat u de bewerking hebt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="9c6eb-119">Als u later wijzigingen aanbrengt in een beleid in Microsoft intune, Azure Active Directory of Microsoft 365, kunnen items die ' klaar ' zijn, ' niet gereed ' worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="9c6eb-120">Als u problemen met Microsoft beheerde bureaublad bewerkingen wilt voorkomen, controleert u de specifieke instellingen die in dit artikel worden beschreven voordat u beleidsregels wijzigt.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="9c6eb-121">Microsoft intune-instellingen</span><span class="sxs-lookup"><span data-stu-id="9c6eb-121">Microsoft Intune settings</span></span>

<span data-ttu-id="9c6eb-122">U kunt de intune-instellingen openen via het [Beheercentrum](https://endpoint.microsoft.com)van Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="9c6eb-123">Auto Pilot-implementatie profiel</span><span class="sxs-lookup"><span data-stu-id="9c6eb-123">Autopilot deployment profile</span></span>

<span data-ttu-id="9c6eb-124">U hebt geen bestaande auto pilot-profielen die door Microsoft beheerde bureaublad worden toegewezen of dynamische groepen die door Microsoft worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="9c6eb-125">Microsoft Managed Desktop gebruikt auto pilot om nieuwe apparaten te creëren.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="9c6eb-126">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-126">**Not ready**</span></span>

<span data-ttu-id="9c6eb-127">U hebt een auto pilot-profiel dat is toegewezen aan alle apparaten.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="9c6eb-128">Zie [Windows-apparaten in intune registreren met behulp van Windows auto pilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="9c6eb-129">Wanneer de Microsoft-bureaublad registratie voor het bureaublad is ingeschakeld, stelt u uw auto pilot-beleid in om de **moderne werkplekken te uitsluiten: alle** Azure AD-groep.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="9c6eb-130">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-130">**Advisory**</span></span>

<span data-ttu-id="9c6eb-131">Zorg ervoor dat uw auto pilot-profielen een toegewezen of dynamische Azure AD-groep betreffen die geen door Microsoft beheerde bureaublad apparaten bevat die worden gemaakt bij het registreren.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="9c6eb-132">Zie [Windows-apparaten in intune registreren met behulp van Windows auto pilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="9c6eb-133">Wanneer de Microsoft-bureaublad registratie voor het bureaublad is ingeschakeld, stelt u uw auto pilot-beleid in om de **moderne werkplekken te uitsluiten: alle** Azure AD-groep.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-133">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="9c6eb-134">Certificaat verbindingslijnen</span><span class="sxs-lookup"><span data-stu-id="9c6eb-134">Certificate connectors</span></span>

<span data-ttu-id="9c6eb-135">Als u certificaat verbindingslijnen hebt die worden gebruikt door de apparaten die u wilt registreren op Microsoft Managed Desktop, zijn de connectors geen fouten.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-135">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="9c6eb-136">Slechts één van de volgende adviseurs is op uw situatie van toepassing, dus controleer ze aandachtig.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="9c6eb-137">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-137">**Advisory**</span></span>

<span data-ttu-id="9c6eb-138">Er zijn geen certificaat connectors aanwezig.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-138">No certificate connectors are present.</span></span> <span data-ttu-id="9c6eb-139">Het is mogelijk dat u geen connectors nodig hebt, maar u moet eerst beoordelen of u een netwerkverbinding met Microsoft beheerde bureaublad apparaten nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9c6eb-140">Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="9c6eb-141">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-141">**Advisory**</span></span>

<span data-ttu-id="9c6eb-142">Minstens één certificaatconnector bevat een fout.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="9c6eb-143">Als u deze connector nodig hebt voor connectiviteit met Microsoft Managed Desktop-apparaten, moet u de fout oplossen.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-143">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="9c6eb-144">Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="9c6eb-145">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-145">**Advisory**</span></span>

<span data-ttu-id="9c6eb-146">U moet minimaal één certificaatconnector en geen fouten rapporteren.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="9c6eb-147">U kunt echter wel een profiel maken om de connector voor Microsoft beheerde bureaublad apparaten opnieuw te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-147">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9c6eb-148">Zie [certificaten en netwerkprofielen voor Microsoft Managed Desktop voorbereiden](certs-wifi-lan.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="9c6eb-149">Beleidsregels voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="9c6eb-149">Conditional access policies</span></span>

<span data-ttu-id="9c6eb-150">Het beleid voor voorwaardelijke toegang in uw Azure AD-organisatie mag geen Microsoft-bureaubladgebruikers bedoelen.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-150">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="9c6eb-151">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-151">**Not ready**</span></span>

<span data-ttu-id="9c6eb-152">U hebt ten minste één beleid voor voorwaardelijke toegang voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="9c6eb-153">Stel het beleid opnieuw in om een specifieke Azure AD-groep met de Azure AD-groep met Microsoft Managed Desktop service-accounts die worden gemaakt bij het registreren, niet te omvatten.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-153">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="9c6eb-154">Zie voor de stappen [voorwaardelijke toegang: gebruikers en groepen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="9c6eb-154">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="9c6eb-155">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-155">**Advisory**</span></span>

<span data-ttu-id="9c6eb-156">Zorg ervoor dat u een beleidsregels voor voorwaardelijke toegang hebt uitgesloten met de Azure AD-groep voor de **moderne service accounts** .</span><span class="sxs-lookup"><span data-stu-id="9c6eb-156">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="9c6eb-157">Zie [voorwaardelijke toegang aanpassen](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)voor de stappen.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-157">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="9c6eb-158">De **modern Workplace service accounts** Azure Ad Group is een dynamische groep die we voor de service maken wanneer u zich registreert.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-158">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="9c6eb-159">U dient na de inschrijving weer de groep uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-159">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="9c6eb-160">Zie voor meer informatie over deze serviceaccounts [standaardprocedures](../service-description/operations-and-monitoring.md#standard-operating-procedures)voor het werk.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-160">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="9c6eb-161">**Fout**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-161">**Error**</span></span>

<span data-ttu-id="9c6eb-162">De rol intune-beheerder heeft onvoldoende machtigingen voor deze controle.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-162">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="9c6eb-163">U hebt ook een van de volgende Azure AD-rollen nodig die zijn toegewezen om deze controle uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="9c6eb-163">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="9c6eb-164">Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="9c6eb-164">Security Reader</span></span>
- <span data-ttu-id="9c6eb-165">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="9c6eb-165">Security Administrator</span></span>
- <span data-ttu-id="9c6eb-166">Beheerder van voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="9c6eb-166">Conditional Access Administrator</span></span>
- <span data-ttu-id="9c6eb-167">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="9c6eb-167">Global Reader</span></span>
- <span data-ttu-id="9c6eb-168">Apparaten beheerder</span><span class="sxs-lookup"><span data-stu-id="9c6eb-168">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="9c6eb-169">Nalevingsbeleid voor apparaten</span><span class="sxs-lookup"><span data-stu-id="9c6eb-169">Device Compliance policies</span></span>

<span data-ttu-id="9c6eb-170">Het beleid voor naleving van intune-apparaten in de Azure AD-organisatie mag geen door Microsoft beheerde bureaubladgebruikers afstemmen.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-170">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="9c6eb-171">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-171">**Not ready**</span></span>

<span data-ttu-id="9c6eb-172">U hebt ten minste één nalevingsbeleid voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-172">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="9c6eb-173">Stel het beleid opnieuw in om een specifieke Azure AD-groep te richten die geen Microsoft-beheerde bureaubladgebruikers omvat.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-173">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="9c6eb-174">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-174">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="9c6eb-175">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-175">**Advisory**</span></span>

<span data-ttu-id="9c6eb-176">Zorg ervoor dat het nalevingsbeleid van Microsoft beheerde bureaubladgebruikers niet omvat.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-176">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="9c6eb-177">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-177">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="9c6eb-178">Beleidsregels voor apparaatconfiguratie</span><span class="sxs-lookup"><span data-stu-id="9c6eb-178">Device Configuration policies</span></span>

<span data-ttu-id="9c6eb-179">Het beleid voor het configureren van intune-apparaten in de Azure AD-organisatie mag geen Microsoft-bureaublad apparaten of-gebruikers beheren.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-179">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="9c6eb-180">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-180">**Not ready**</span></span>

<span data-ttu-id="9c6eb-181">U hebt minimaal één configuratiebeleid voor alle gebruikers, alle apparaten of beide.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-181">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="9c6eb-182">Stel het beleid opnieuw in om een specifieke Azure AD-groep te richten die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-182">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9c6eb-183">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-183">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="9c6eb-184">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-184">**Advisory**</span></span>

<span data-ttu-id="9c6eb-185">Zorg ervoor dat het nalevingsbeleid van Microsoft beheerde bureaublad apparaten of gebruikers niet omvat.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-185">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="9c6eb-186">Zie [een nalevingsbeleid maken in Microsoft intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-186">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="9c6eb-187">Beperkingen voor apparaattype</span><span class="sxs-lookup"><span data-stu-id="9c6eb-187">Device type restrictions</span></span>

<span data-ttu-id="9c6eb-188">Door Microsoft beheerde bureaublad apparaten moet u zich kunnen registreren bij intune.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-188">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="9c6eb-189">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-189">**Not ready**</span></span>

<span data-ttu-id="9c6eb-190">Voer de stappen uit in de optie voor het [instellen van inschrijving](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) om de **instelling toe te passen.**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-190">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="9c6eb-191">Pagina met inschrijvings status</span><span class="sxs-lookup"><span data-stu-id="9c6eb-191">Enrollment Status Page</span></span>

<span data-ttu-id="9c6eb-192">U hebt momenteel de pagina met de inschrijvings status (ESP) ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-192">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="9c6eb-193">Als u deelneemt aan de openbare preview van deze functie, kunt u dit item negeren.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-193">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="9c6eb-194">Zie [First Run-ervaring met auto pilot en de pagina inschrijvings status](../get-started/esp-first-run.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-194">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="9c6eb-195">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-195">**Not ready**</span></span>

<span data-ttu-id="9c6eb-196">Voor het weergeven van de voortgang van de **apps en profielen** moet u de standaard-ESP-profielset opgeven.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-196">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="9c6eb-197">Schakel deze instelling uit of zorg ervoor dat toewijzingen aan een Azure AD-groep geen door Microsoft beheerde bureaublad apparaten bevatten door de stappen te volgen in [de pagina inschrijvings status instellen](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="9c6eb-197">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="9c6eb-198">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-198">**Advisory**</span></span>

<span data-ttu-id="9c6eb-199">Zorg ervoor dat profielen met de instelling **voortgang van app en profielconfiguratie weergeven** niet zijn toegewezen aan een Azure AD-groep die Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-199">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9c6eb-200">Zie [de pagina inschrijvings status instellen](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-200">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="9c6eb-201">InTune-registratie</span><span class="sxs-lookup"><span data-stu-id="9c6eb-201">Intune enrollment</span></span>

<span data-ttu-id="9c6eb-202">Windows 10-apparaten in uw Azure AD-organisatie moeten automatisch worden geregistreerd in intune.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-202">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="9c6eb-203">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-203">**Advisory**</span></span>

<span data-ttu-id="9c6eb-204">Zorg ervoor dat het bereik van MDM-gebruikers is **ingesteld op** **Alles of alles**, niet **none**.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-204">Make sure the MDM User scope is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="9c6eb-205">Als u **een aantal** kiest, meldt u zich weer na de inschrijving en selecteert u de groep **modern Workplace-all** Azure AD voor **groepen**.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-205">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="9c6eb-206">Microsoft Store voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="9c6eb-206">Microsoft Store for Business</span></span>

<span data-ttu-id="9c6eb-207">We gebruiken Microsoft Store voor bedrijven, zodat u de bedrijfs portal kunt downloaden om bepaalde apps te implementeren, zoals Microsoft Project en Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-207">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="9c6eb-208">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-208">**Not ready**</span></span>

<span data-ttu-id="9c6eb-209">Microsoft Store voor bedrijven is niet ingeschakeld of wordt niet gesynchroniseerd met intune.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-209">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="9c6eb-210">Zie voor meer informatie het artikel [apps gekochte apps in Microsoft Store voor bedrijven beheren met Microsoft intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) en de [intune-bedrijfs portal installeren op een apparaat](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="9c6eb-210">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="9c6eb-211">Meervoudige verificatie</span><span class="sxs-lookup"><span data-stu-id="9c6eb-211">Multifactor authentication</span></span>

<span data-ttu-id="9c6eb-212">Meervoudige verificatie mag niet per ongeluk worden toegepast op accounts van Microsoft Managed Desktop service.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-212">Multifactor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="9c6eb-213">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-213">**Not ready**</span></span>

<span data-ttu-id="9c6eb-214">U hebt een MFA-beleid (multi-factor Authentication) ingesteld als vereist voor regels voor voorwaardelijke toegang die zijn toegewezen aan alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-214">You have some multifactor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="9c6eb-215">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-215">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9c6eb-216">Zie voor meer informatie [beleidsregels voor voorwaardelijke toegang](#conditional-access-policies) en [voorwaardelijke toegang: MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="9c6eb-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="9c6eb-217">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-217">**Advisory**</span></span>

<span data-ttu-id="9c6eb-218">Zorg ervoor dat voor beleidsregels voor voorwaardelijke toegang de optie MFA moet **zijn opgenomen:** de groep alle Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-218">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="9c6eb-219">Zie voor meer informatie [beleidsregels voor voorwaardelijke toegang](#conditional-access-policies) en [voorwaardelijke toegang: MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="9c6eb-219">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="9c6eb-220">De **modern Workplace-all** Azure AD-groep is een dynamische groep die we maken wanneer u zich registreert bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-220">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="9c6eb-221">**Fout**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-221">**Error**</span></span>

<span data-ttu-id="9c6eb-222">De rol intune-beheerder heeft onvoldoende machtigingen voor deze controle.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-222">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="9c6eb-223">U hebt ook een van de volgende Azure AD-rollen nodig die zijn toegewezen om deze controle uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="9c6eb-223">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="9c6eb-224">Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="9c6eb-224">Security Reader</span></span>
- <span data-ttu-id="9c6eb-225">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="9c6eb-225">Security Administrator</span></span>
- <span data-ttu-id="9c6eb-226">Beheerder van voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="9c6eb-226">Conditional Access Administrator</span></span>
- <span data-ttu-id="9c6eb-227">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="9c6eb-227">Global Reader</span></span>
- <span data-ttu-id="9c6eb-228">Apparaten beheerder</span><span class="sxs-lookup"><span data-stu-id="9c6eb-228">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="9c6eb-229">PowerShell-scripts</span><span class="sxs-lookup"><span data-stu-id="9c6eb-229">PowerShell scripts</span></span>

<span data-ttu-id="9c6eb-230">Windows PowerShell-scripts kunnen niet worden toegewezen in de manier waarop Microsoft beheerde bureaublad apparaten kunnen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-230">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="9c6eb-231">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-231">**Advisory**</span></span>

<span data-ttu-id="9c6eb-232">Zorg ervoor dat Windows PowerShell-scripts in uw Azure AD-organisatie geen Microsoft-bureaublad apparaten of-gebruikers beheren.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-232">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="9c6eb-233">Wijs geen PowerShell-script toe om alle gebruikers, alle apparaten of beide te bereiken.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-233">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="9c6eb-234">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-234">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9c6eb-235">Zie [PowerShell-scripts op Windows 10-apparaten gebruiken in intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-235">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="9c6eb-236">Regio</span><span class="sxs-lookup"><span data-stu-id="9c6eb-236">Region</span></span>

<span data-ttu-id="9c6eb-237">Uw regio moet worden ondersteund door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-237">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="9c6eb-238">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-238">**Not ready**</span></span>

<span data-ttu-id="9c6eb-239">Uw regio van Azure AD organisatie wordt momenteel niet ondersteund door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-239">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="9c6eb-240">Zie [ondersteunde regio's en talen door Microsoft worden beheerd op het bureaublad](../service-description/regions-languages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="9c6eb-241">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-241">**Advisory**</span></span>

<span data-ttu-id="9c6eb-242">Een of meer van de landen waar uw Azure AD organisatie zich bevindt, wordt niet ondersteund door het door Microsoft beheerde bureaublad.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-242">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="9c6eb-243">Zie [ondersteunde regio's en talen door Microsoft worden beheerd op het bureaublad](../service-description/regions-languages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-243">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="9c6eb-244">Basislijnen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="9c6eb-244">Security baselines</span></span>

<span data-ttu-id="9c6eb-245">Beleidsregels voor beveiliging van basislijn dienen niet te worden beheerd door Microsoft beheerde bureaublad apparaten.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-245">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="9c6eb-246">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-246">**Not ready**</span></span>

<span data-ttu-id="9c6eb-247">U hebt een profiel voor beveiligings basislijn voor alle gebruikers, alle apparaten of beide.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-247">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="9c6eb-248">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-248">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9c6eb-249">Zie [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-249">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="9c6eb-250">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-250">**Advisory**</span></span>

<span data-ttu-id="9c6eb-251">Zorg dat beleidsregels voor beveiliging op basis van Microsoft beheerde bureaublad apparaten zijn uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-251">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9c6eb-252">Zie [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-252">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="9c6eb-253">De **moderne werkplekken-** de groep Azure AD is een dynamische groep die we maken wanneer u zich aanmeldt bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-253">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="9c6eb-254">Windows-apps</span><span class="sxs-lookup"><span data-stu-id="9c6eb-254">Windows apps</span></span>

<span data-ttu-id="9c6eb-255">Bekijk de apps waarover u Microsoft beheerde bureaubladgebruikers wilt hebben.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-255">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="9c6eb-256">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-256">**Advisory**</span></span>

<span data-ttu-id="9c6eb-257">U moet een inventarisatie voorbereiden van de apps die u wilt laten door Microsoft beheerde bureaubladgebruikers.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-257">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="9c6eb-258">Aangezien deze apps moeten worden geïmplementeerd door intune, moet u bestaande intune-apps hergebruiken.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-258">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="9c6eb-259">Overweeg om bedrijfsportal te gebruiken (Zie [intune-bedrijfsportal installeren op apparaten](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) en de pagina inschrijvings status (ESP) om apps te distribueren voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-259">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="9c6eb-260">Zie [apps in Microsoft Managed Desktop](apps.md) en [First-Run met auto pilot en de pagina met de inschrijvings status](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-260">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="9c6eb-261">U kunt de vertegenwoordiger van uw Microsoft-account vragen om te bepalen welke apps gereed zijn om te worden gemigreerd naar intune of een correctie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-261">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="9c6eb-262">Windows Hello voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="9c6eb-262">Windows Hello for Business</span></span>

<span data-ttu-id="9c6eb-263">Voor Microsoft Managed Desktop is Windows hello voor bedrijven ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-263">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="9c6eb-264">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-264">**Not ready**</span></span>

<span data-ttu-id="9c6eb-265">Windows hello voor bedrijven is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-265">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="9c6eb-266">Activeren door de stappen te volgen in [een beleid voor Windows hello voor bedrijven maken](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="9c6eb-266">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="9c6eb-267">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-267">**Advisory**</span></span>

<span data-ttu-id="9c6eb-268">Windows hello voor bedrijven is niet ingesteld.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-268">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="9c6eb-269">Schakel deze optie in door de stappen te volgen in [een beleid voor Windows hello voor bedrijven maken](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="9c6eb-269">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="9c6eb-270">Windows 10-update ringen</span><span class="sxs-lookup"><span data-stu-id="9c6eb-270">Windows 10 update rings</span></span>

<span data-ttu-id="9c6eb-271">Het beleid Windows 10-update ring in intune mag geen Microsoft-bureaublad apparaten met Microsoft worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-271">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="9c6eb-272">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-272">**Not ready**</span></span>

<span data-ttu-id="9c6eb-273">U hebt een beleid voor het bijwerken van een update voor alle apparaten, alle gebruikers of beide.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-273">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="9c6eb-274">Wijzig het beleid voor het gebruik van een opdracht die een specifieke Azure AD-groep bedoelt die geen door Microsoft beheerde bureaublad apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-274">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9c6eb-275">Zie [updates voor Windows 10-software beheren in intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-275">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="9c6eb-276">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-276">**Advisory**</span></span>

<span data-ttu-id="9c6eb-277">Zorg ervoor dat bij een update ring beleid u de **moderne Werkplaatsings apparaten-alle** Azure AD-groep uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-277">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="9c6eb-278">Als u een Azure AD-gebruikersgroep aan deze beleidsregels hebt toegewezen, moet u ervoor zorgen dat u ook de **moderne werkplek,** exclusief de Azure AD-groep, die uw door Microsoft beheerde bureaubladgebruikers bevat.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-278">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="9c6eb-279">Zie [updates voor Windows 10-software beheren in intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-279">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="9c6eb-280">Zowel de **moderne werkplekken-** alle en de **moderne werkplek: alle** Azure ad-groepen zijn toegewezen groepen die we maken wanneer u zich aanmeldt bij Microsoft Managed Desktop, zodat u deze groep moet uitsluiten na inschrijving.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-280">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="9c6eb-281">Azure Active Directory-instellingen</span><span class="sxs-lookup"><span data-stu-id="9c6eb-281">Azure Active Directory settings</span></span>

<span data-ttu-id="9c6eb-282">U kunt toegang krijgen tot Azure Active Directory-instellingen op de [Azure-Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="9c6eb-282">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="9c6eb-283">Ad hoc-abonnementen</span><span class="sxs-lookup"><span data-stu-id="9c6eb-283">Ad hoc subscriptions</span></span>

<span data-ttu-id="9c6eb-284">Adviseert het controleren van een instelling die (indien ingesteld op ' onwaar ') kan voorkomen dat roaming via Enterprise niet goed werkt.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-284">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="9c6eb-285">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-285">**Advisory**</span></span>

<span data-ttu-id="9c6eb-286">Zorg ervoor dat **AllowAdHocSubscriptions** is ingesteld op **waar**.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-286">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="9c6eb-287">Anders werkt Enterprise State roaming mogelijk niet.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-287">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="9c6eb-288">Zie [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-288">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="9c6eb-289">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="9c6eb-289">Enterprise State Roaming</span></span>

<span data-ttu-id="9c6eb-290">Enterprise State roaming moet zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-290">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="9c6eb-291">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-291">**Advisory**</span></span>

<span data-ttu-id="9c6eb-292">Zorg ervoor dat roaming voor bedrijven is ingeschakeld voor **alle** of voor **geselecteerde** groepen.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-292">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="9c6eb-293">Zie [Enterprise State roaming inschakelen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-293">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="9c6eb-294">Licenties</span><span class="sxs-lookup"><span data-stu-id="9c6eb-294">Licenses</span></span>

<span data-ttu-id="9c6eb-295">U moet een aantal licenties gebruiken om Microsoft Managed Desktop te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-295">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="9c6eb-296">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-296">**Not Ready**</span></span>

<span data-ttu-id="9c6eb-297">U hebt niet alle licenties die u nodig hebt om Microsoft Managed Desktop te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-297">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="9c6eb-298">Zie [Microsoft Managed Desktop Technologies](../intro/technologies.md) en meer informatie [over licenties](prerequisites.md#more-about-licenses)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-298">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="9c6eb-299">Namen van beveiligingsaccounts</span><span class="sxs-lookup"><span data-stu-id="9c6eb-299">Security account names</span></span>

<span data-ttu-id="9c6eb-300">Het is mogelijk dat de namen van bepaalde beveiligingsaccounts conflicteren met die van Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-300">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="9c6eb-301">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-301">**Not ready**</span></span>

<span data-ttu-id="9c6eb-302">U hebt minimaal één accountnaam waarvan de naam afwijkt van de naam die wordt gemaakt door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-302">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="9c6eb-303">Met de vertegenwoordiger van uw Microsoft-account kunt u deze accountnamen uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-303">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="9c6eb-304">Rollen van beveiligingsbeheerders</span><span class="sxs-lookup"><span data-stu-id="9c6eb-304">Security administrator roles</span></span>

<span data-ttu-id="9c6eb-305">Gebruikers met bepaalde beveiligingsrollen moeten deze rollen hebben toegewezen in Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-305">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="9c6eb-306">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-306">**Advisory**</span></span>

<span data-ttu-id="9c6eb-307">Als u gebruikers hebt toegewezen aan een van deze rollen in uw Azure AD-organisatie, moet u ervoor zorgen dat deze rollen ook zijn toegewezen in Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-307">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9c6eb-308">Anders hebben beheerders met deze rollen geen toegang tot de beheerportal.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-308">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="9c6eb-309">Beveiligings operator</span><span class="sxs-lookup"><span data-stu-id="9c6eb-309">Security Operator</span></span>
- <span data-ttu-id="9c6eb-310">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="9c6eb-310">Global Reader</span></span>

<span data-ttu-id="9c6eb-311">Zie [rollen voor toegangsbeheer op basis van rollen maken en beheren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-311">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="9c6eb-312">Beveiligingsstandaard</span><span class="sxs-lookup"><span data-stu-id="9c6eb-312">Security default</span></span>

<span data-ttu-id="9c6eb-313">Met behulp van de beveiligingsinstellingen in azure Active Directory wordt voorkomen dat Microsoft beheerd bureaublad uw apparaten beheert.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-313">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="9c6eb-314">**Niet gereed**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-314">**Not ready**</span></span>

<span data-ttu-id="9c6eb-315">U hebt beveiligingsstandaarden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-315">You have Security defaults turned on.</span></span> <span data-ttu-id="9c6eb-316">Schakel beveiligingsstandaarden uit en stel beleidsregels voor voorwaardelijke toegang in.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-316">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="9c6eb-317">Zie voor meer informatie [veelgebruikte beleidsregels voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="9c6eb-317">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="9c6eb-318">Selfservice voor wachtwoordherstel</span><span class="sxs-lookup"><span data-stu-id="9c6eb-318">Self-service Password Reset</span></span>

<span data-ttu-id="9c6eb-319">U moet selfservice voor wachtwoordherstel (SSPR) inschakelen voor alle Microsoft beheerde bureaubladgebruikers, met uitzondering van Microsoft beheerde bureaublad serviceaccounts.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-319">Self-service Password Reset (SSPR) should be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="9c6eb-320">Zie [Zelfstudie: gebruikers toestaan hun account te ontgrendelen of wachtwoorden opnieuw in te stellen met behulp van Azure Active Directory-wachtwoordherstel](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="9c6eb-320">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="9c6eb-321">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-321">**Advisory**</span></span>

<span data-ttu-id="9c6eb-322">Zorg ervoor dat de **geselecteerde** instelling voor SSPR Microsoft beheerde bureaublad apparaten bevat, maar dat Microsoft beheerde bureaublad-serviceaccounts niet is opgenomen.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-322">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="9c6eb-323">Accounts van Microsoft beheerde bureaubladservices werken niet zoals verwacht wanneer SSPR is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-323">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="9c6eb-324">Standaard gebruikersrol</span><span class="sxs-lookup"><span data-stu-id="9c6eb-324">Standard user role</span></span>

<span data-ttu-id="9c6eb-325">Behalve de gebruikers die een Azure AD-rol van globale beheerder en een andere netwerkbeheerder toegewezen, zijn Microsoft-beheerde bureaubladgebruikers standaardgebruikers zonder lokale beheerdersbevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-325">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="9c6eb-326">Voor alle andere gebruikers wordt een standaard gebruikersrol toegewezen wanneer ze hun Microsoft-beheerde bureaublad apparaat starten.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-326">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="9c6eb-327">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-327">**Advisory**</span></span>

<span data-ttu-id="9c6eb-328">Microsoft beheerde bureaubladgebruikers hebben geen lokale beheerdersbevoegdheden op hun Microsoft beheerde bureaublad apparaten na registratie.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-328">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="9c6eb-329">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="9c6eb-329">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="9c6eb-330">OneDrive</span><span class="sxs-lookup"><span data-stu-id="9c6eb-330">OneDrive</span></span>

<span data-ttu-id="9c6eb-331">De instelling voor **synchronisatie alleen toestaan op pc's die lid zijn van een specifieke domein** instelling, conflicteert met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-331">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="9c6eb-332">U kunt toegang krijgen tot OneDrive-instellingen in het OneDrive- [Beheercentrum](https://admin.onedrive.com).</span><span class="sxs-lookup"><span data-stu-id="9c6eb-332">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="9c6eb-333">**Adviser**</span><span class="sxs-lookup"><span data-stu-id="9c6eb-333">**Advisory**</span></span>

<span data-ttu-id="9c6eb-334">U gebruikt de instelling **synchronisatie alleen toestaan op pc's die lid zijn van bepaalde domeinen** .</span><span class="sxs-lookup"><span data-stu-id="9c6eb-334">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="9c6eb-335">Deze instelling werkt niet met beheerde Microsoft-bureaublad.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-335">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="9c6eb-336">Schakel deze instelling uit en zet OneDrive zodanig in dat deze gebruikmaakt van een voorwaardelijk toegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-336">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="9c6eb-337">Zie [voorwaardelijke toegang plannen](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) voor hulp.</span><span class="sxs-lookup"><span data-stu-id="9c6eb-337">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

