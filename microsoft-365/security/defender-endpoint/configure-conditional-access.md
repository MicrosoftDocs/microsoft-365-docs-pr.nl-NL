---
title: Voorwaardelijke toegang configureren in Microsoft Defender voor eindpunt
description: Meer informatie over de stappen die u moet uitvoeren in Intune, Microsoft Defender-beveiligingscentrum azure om voorwaardelijke toegang te implementeren
keywords: voorwaardelijke toegang, voorwaardelijke toegang, toegang, apparaatrisico, risiconiveau, integratie, intune-integratie
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ceb69d59dc5208c0908e33d0880d9352562ec140
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843972"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="f937b-104">Voorwaardelijke toegang configureren in Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="f937b-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f937b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f937b-105">**Applies to:**</span></span>
- [<span data-ttu-id="f937b-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f937b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f937b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f937b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f937b-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f937b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f937b-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f937b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="f937b-110">In deze sectie wordt u begeleid bij alle stappen die u moet uitvoeren om Voorwaardelijke toegang correct te implementeren.</span><span class="sxs-lookup"><span data-stu-id="f937b-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="f937b-111">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="f937b-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="f937b-112">Het is belangrijk om te weten dat geregistreerde Azure AD-apparaten in dit scenario niet worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="f937b-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="f937b-113">Alleen aangemelde Intune-apparaten worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="f937b-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="f937b-114">U moet ervoor zorgen dat al uw apparaten zijn geregistreerd in Intune.</span><span class="sxs-lookup"><span data-stu-id="f937b-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="f937b-115">U kunt een van de volgende opties gebruiken om apparaten in te schrijven in Intune:</span><span class="sxs-lookup"><span data-stu-id="f937b-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="f937b-116">IT-beheerder: Zie Windows [Enrollment](/intune/windows-enroll#enable-windows-10-automatic-enrollment) voor meer informatie over het inschakelen van automatische inschrijving</span><span class="sxs-lookup"><span data-stu-id="f937b-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="f937b-117">Eindgebruiker: Zie Uw Windows 10 in Intune registreren voor meer informatie over het registreren van uw Windows 10 apparaat [in Intune](/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="f937b-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="f937b-118">Alternatief voor eindgebruikers: Zie How to: Plan your Azure AD join implementation (Uw [Azure AD join-implementatie](/azure/active-directory/devices/azureadjoin-plan)plannen) voor meer informatie over het deelnemen aan een Azure AD-domein.</span><span class="sxs-lookup"><span data-stu-id="f937b-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="f937b-119">Er zijn stappen die u moet uitvoeren in Microsoft Defender-beveiligingscentrum, de Intune-portal en de Azure AD-portal.</span><span class="sxs-lookup"><span data-stu-id="f937b-119">There are steps you'll need to take in Microsoft Defender Security Center, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="f937b-120">Het is belangrijk om de vereiste rollen op te merken om toegang te krijgen tot deze portals en Voorwaardelijke toegang te implementeren:</span><span class="sxs-lookup"><span data-stu-id="f937b-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="f937b-121">**Microsoft Defender-beveiligingscentrum:** u moet zich aanmelden bij de portal met een globale beheerdersrol om de integratie in te zetten.</span><span class="sxs-lookup"><span data-stu-id="f937b-121">**Microsoft Defender Security Center** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="f937b-122">**Intune:** u moet zich aanmelden bij de portal met beveiligingsbeheerdersrechten met beheermachtigingen.</span><span class="sxs-lookup"><span data-stu-id="f937b-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="f937b-123">**Azure AD-portal:** u moet zich aanmelden als globale beheerder, beveiligingsbeheerder of beheerder van voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="f937b-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="f937b-124">U hebt een Microsoft Intune nodig, met intune beheerde en Azure AD-Windows 10 apparaten.</span><span class="sxs-lookup"><span data-stu-id="f937b-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="f937b-125">Ga als volgt te werk om Voorwaardelijke toegang in te stellen:</span><span class="sxs-lookup"><span data-stu-id="f937b-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="f937b-126">Stap 1: Schakel de Microsoft Intune verbinding in Microsoft Defender-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="f937b-126">Step 1: Turn on the Microsoft Intune connection from Microsoft Defender Security Center</span></span>
- <span data-ttu-id="f937b-127">Stap 2: De integratie van Defender voor eindpunten in Intune in-</span><span class="sxs-lookup"><span data-stu-id="f937b-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="f937b-128">Stap 3: Het compliancebeleid maken in Intune</span><span class="sxs-lookup"><span data-stu-id="f937b-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="f937b-129">Stap 4: Het beleid toewijzen</span><span class="sxs-lookup"><span data-stu-id="f937b-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="f937b-130">Stap 5: Een Azure AD-beleid voor voorwaardelijke toegang maken</span><span class="sxs-lookup"><span data-stu-id="f937b-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="f937b-131">Stap 1: De Microsoft Intune in</span><span class="sxs-lookup"><span data-stu-id="f937b-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="f937b-132">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Geavanceerde functies Microsoft Intune**  >  **verbinding.**</span><span class="sxs-lookup"><span data-stu-id="f937b-132">In the navigation pane, select **Settings** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="f937b-133">Schakel de instelling Microsoft Intune in op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="f937b-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="f937b-134">Klik **op Voorkeuren opslaan.**</span><span class="sxs-lookup"><span data-stu-id="f937b-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="f937b-135">Stap 2: De integratie van Defender voor eindpunten in Intune in-</span><span class="sxs-lookup"><span data-stu-id="f937b-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="f937b-136">Meld u aan bij [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="f937b-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="f937b-137">Selecteer **Apparaat compliance**  >  **Microsoft Defender ATP.**</span><span class="sxs-lookup"><span data-stu-id="f937b-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="f937b-138">Stel **Verbinding maken Windows 10.0.15063+** apparaten in op Microsoft Defender Advanced Threat Protection op **Aan.**</span><span class="sxs-lookup"><span data-stu-id="f937b-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="f937b-139">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f937b-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="f937b-140">Stap 3: Het compliancebeleid maken in Intune</span><span class="sxs-lookup"><span data-stu-id="f937b-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="f937b-141">Selecteer in [de Azure-portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="f937b-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="f937b-142">Selecteer **Apparaat**  >  **compliancebeleid Beleid**  >  **maken**.</span><span class="sxs-lookup"><span data-stu-id="f937b-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="f937b-143">Voer een **naam en** **beschrijving in.**</span><span class="sxs-lookup"><span data-stu-id="f937b-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="f937b-144">Selecteer **in Platform** de Windows 10 en **hoger.**</span><span class="sxs-lookup"><span data-stu-id="f937b-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="f937b-145">Stel in **de instellingen voor** Apparaattoestand De instelling Vereisen dat het apparaat zich op of onder het **apparaatrisiconiveau** op het gewenste niveau moet hebben ingesteld:</span><span class="sxs-lookup"><span data-stu-id="f937b-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="f937b-146">**Beveiligd:** dit niveau is het veiligst.</span><span class="sxs-lookup"><span data-stu-id="f937b-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="f937b-147">Het apparaat kan geen bestaande bedreigingen hebben en heeft nog steeds toegang tot bedrijfsresources.</span><span class="sxs-lookup"><span data-stu-id="f937b-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="f937b-148">Als er bedreigingen worden gevonden, wordt het apparaat geëvalueerd als niet-compatibel.</span><span class="sxs-lookup"><span data-stu-id="f937b-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="f937b-149">**Laag:** Het apparaat voldoet als er alleen bedreigingen op laag niveau zijn.</span><span class="sxs-lookup"><span data-stu-id="f937b-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="f937b-150">Apparaten met een gemiddeld of hoog bedreigingsniveau voldoen niet.</span><span class="sxs-lookup"><span data-stu-id="f937b-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="f937b-151">**Medium:** Het apparaat voldoet als de bedreigingen op het apparaat laag of gemiddeld zijn.</span><span class="sxs-lookup"><span data-stu-id="f937b-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="f937b-152">Als er bedreigingen op hoog niveau worden gedetecteerd, wordt het apparaat bepaald als niet-compatibel.</span><span class="sxs-lookup"><span data-stu-id="f937b-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="f937b-153">**Hoog:** Dit niveau is het minst veilig en staat alle bedreigingsniveaus toe.</span><span class="sxs-lookup"><span data-stu-id="f937b-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="f937b-154">Apparaten met een hoog, gemiddeld of laag bedreigingsniveau worden dus als compatibel beschouwd.</span><span class="sxs-lookup"><span data-stu-id="f937b-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="f937b-155">Selecteer **OK** en Maken **om** uw wijzigingen op te slaan (en het beleid te maken).</span><span class="sxs-lookup"><span data-stu-id="f937b-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="f937b-156">Stap 4: Het beleid toewijzen</span><span class="sxs-lookup"><span data-stu-id="f937b-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="f937b-157">Selecteer in [de Azure-portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="f937b-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="f937b-158">Selecteer **Apparaat**  >  **compliancebeleid>** microsoft Defender voor endpoint compliancebeleid te selecteren.</span><span class="sxs-lookup"><span data-stu-id="f937b-158">Select **Device compliance** > **Policies**> select your Microsoft Defender for Endpoint compliance policy.</span></span>
3. <span data-ttu-id="f937b-159">Kies **Opdrachten**.</span><span class="sxs-lookup"><span data-stu-id="f937b-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="f937b-160">Neem uw Azure AD-groepen op of sluit deze uit om ze het beleid toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="f937b-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="f937b-161">Als u het beleid wilt implementeren voor de groepen, selecteert u **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="f937b-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="f937b-162">De gebruikersapparaten die het doel zijn van het beleid, worden geëvalueerd op naleving.</span><span class="sxs-lookup"><span data-stu-id="f937b-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="f937b-163">Stap 5: Een Azure AD-beleid voor voorwaardelijke toegang maken</span><span class="sxs-lookup"><span data-stu-id="f937b-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="f937b-164">Open in [de Azure-portal](https://portal.azure.com) **het Azure Active Directory**  >  **Voorwaardelijke toegang** nieuw  >  **beleid**.</span><span class="sxs-lookup"><span data-stu-id="f937b-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="f937b-165">Voer een **beleidsnaam in** en selecteer **Gebruikers en groepen.**</span><span class="sxs-lookup"><span data-stu-id="f937b-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="f937b-166">Gebruik de opties Opnemen of Uitsluiten om uw groepen toe te voegen voor het beleid en selecteer **Klaar.**</span><span class="sxs-lookup"><span data-stu-id="f937b-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="f937b-167">Selecteer **Cloud-apps** en kies welke apps u wilt beveiligen.</span><span class="sxs-lookup"><span data-stu-id="f937b-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="f937b-168">Kies bijvoorbeeld Apps **selecteren** en selecteer Office 365 SharePoint **Online** en **Office 365 Exchange Online.**</span><span class="sxs-lookup"><span data-stu-id="f937b-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="f937b-169">Selecteer **Klaar om** uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="f937b-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="f937b-170">Selecteer **Voorwaarden**  >  **Client-apps om** het beleid toe te passen op apps en browsers.</span><span class="sxs-lookup"><span data-stu-id="f937b-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="f937b-171">Selecteer bijvoorbeeld **Ja** en schakel vervolgens **Browser-** en **Mobiele apps en bureaubladcl clients in.**</span><span class="sxs-lookup"><span data-stu-id="f937b-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="f937b-172">Selecteer **Klaar om** uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="f937b-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="f937b-173">Selecteer **Verlenen om** Voorwaardelijke toegang toe te passen op basis van apparaat compliance.</span><span class="sxs-lookup"><span data-stu-id="f937b-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="f937b-174">Selecteer bijvoorbeeld Toegang verlenen **Apparaat vereisen** dat apparaat moet worden gemarkeerd  >  **als compatibel**.</span><span class="sxs-lookup"><span data-stu-id="f937b-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="f937b-175">Kies **Selecteren om** uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="f937b-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="f937b-176">Selecteer **Beleid inschakelen** en vervolgens **Maken om** uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="f937b-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="f937b-177">Zie Naleving afdwingen voor Microsoft Defender voor Eindpunt met [Voorwaardelijke toegang in Intune](/intune/advanced-threat-protection)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f937b-177">For more information, see [Enforce compliance for Microsoft Defender for Endpoint with Conditional Access in Intune](/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="f937b-178">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f937b-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f937b-179">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f937b-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
