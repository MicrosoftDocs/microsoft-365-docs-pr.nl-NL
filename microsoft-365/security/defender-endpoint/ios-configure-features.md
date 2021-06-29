---
title: Microsoft Defender voor eindpunt configureren voor iOS-functies
description: Beschrijft hoe u Microsoft Defender voor Eindpunt implementeert voor iOS-functies
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, configure, features, ios
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 07905cc3f1b3bd4445199d7bddcdf3b45500bd5f
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194947"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="287e5-104">Microsoft Defender voor eindpunt configureren voor iOS-functies</span><span class="sxs-lookup"><span data-stu-id="287e5-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="287e5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="287e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="287e5-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="287e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="287e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="287e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="287e5-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="287e5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="287e5-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="287e5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="287e5-110">Defender voor Eindpunt in iOS zou een VPN gebruiken om de functie Webbeveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="287e5-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="287e5-111">Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.</span><span class="sxs-lookup"><span data-stu-id="287e5-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="287e5-112">Voorwaardelijke toegang met Defender voor Eindpunt in iOS</span><span class="sxs-lookup"><span data-stu-id="287e5-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="287e5-113">Microsoft Defender voor Eindpunt op iOS, samen met Microsoft Intune en Azure Active Directory, maakt het afdwingen van apparaat compliance en beleid voor Voorwaardelijke toegang mogelijk op basis van apparaatrisicoscore.</span><span class="sxs-lookup"><span data-stu-id="287e5-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="287e5-114">Defender for Endpoint is een MTD-oplossing (Mobile Threat Defense) die u kunt implementeren om gebruik te maken van deze mogelijkheid via Intune.</span><span class="sxs-lookup"><span data-stu-id="287e5-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="287e5-115">Zie Defender voor Eindpunt en [Intune](/mem/intune/protect/advanced-threat-protection)voor meer informatie over het instellen van Voorwaardelijke toegang met Defender voor Eindpunt in iOS.</span><span class="sxs-lookup"><span data-stu-id="287e5-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a><span data-ttu-id="287e5-116">Jailbreakdetectie door Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="287e5-116">Jailbreak detection by Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="287e5-117">Microsoft Defender voor Eindpunt heeft de mogelijkheid om niet-beheerde en beheerde apparaten te detecteren die in de bajes staan.</span><span class="sxs-lookup"><span data-stu-id="287e5-117">Microsoft Defender for Endpoint has the capability of detecting unmanaged and managed devices that are jailbroken.</span></span> <span data-ttu-id="287e5-118">Als wordt vastgesteld dat een apparaat een jailbroken is, wordt een waarschuwing met hoog risico gerapporteerd aan het Beveiligingscentrum en als Voorwaardelijke toegang is ingesteld op basis van de apparaatrisicoscore, wordt het apparaat geblokkeerd voor toegang tot bedrijfsgegevens.</span><span class="sxs-lookup"><span data-stu-id="287e5-118">If a device is detected to be jailbroken, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="287e5-119">Webbeveiliging en VPN</span><span class="sxs-lookup"><span data-stu-id="287e5-119">Web Protection and VPN</span></span>

<span data-ttu-id="287e5-120">Defender voor Eindpunt in iOS bevat standaard de functie voor webbeveiliging en schakelt deze in.</span><span class="sxs-lookup"><span data-stu-id="287e5-120">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="287e5-121">[Webbeveiliging helpt](web-protection-overview.md) om apparaten te beveiligen tegen webbedreigingen en gebruikers te beschermen tegen phishingaanvallen.</span><span class="sxs-lookup"><span data-stu-id="287e5-121">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="287e5-122">Defender voor Endpoint in iOS gebruikt een VPN om deze beveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="287e5-122">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="287e5-123">Let op: dit is een lokale VPN en in tegenstelling tot traditionele VPN wordt netwerkverkeer niet buiten het apparaat verzonden.</span><span class="sxs-lookup"><span data-stu-id="287e5-123">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="287e5-124">Hoewel deze standaard is ingeschakeld, zijn er mogelijk bepaalde gevallen waarvoor u VPN moet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="287e5-124">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="287e5-125">U wilt bijvoorbeeld bepaalde apps uitvoeren die niet werken wanneer een VPN is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="287e5-125">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="287e5-126">In dergelijke gevallen kunt u ervoor kiezen om VPN uit te schakelen vanuit de app op het apparaat door de onderstaande stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="287e5-126">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="287e5-127">Open op uw iOS-apparaat de **Instellingen** app, klik of tik **op Algemeen** en vervolgens **op VPN.**</span><span class="sxs-lookup"><span data-stu-id="287e5-127">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="287e5-128">Klik of tik op de knop 'i' voor Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="287e5-128">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="287e5-129">Schakel de optie **Verbinding maken op aanvraag uit om** VPN uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="287e5-129">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="287e5-130">![VPN config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="287e5-130">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="287e5-131">Webbeveiliging is niet beschikbaar wanneer VPN is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="287e5-131">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="287e5-132">Als u Webbeveiliging opnieuw wilt inschakelen, opent u de Microsoft Defender voor Eindpunt-app op het apparaat en klikt of tikt u op **Start VPN**.</span><span class="sxs-lookup"><span data-stu-id="287e5-132">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="287e5-133">Co-bestaan van meerdere VPN-profielen</span><span class="sxs-lookup"><span data-stu-id="287e5-133">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="287e5-134">Apple iOS biedt geen ondersteuning voor meerdere VPN's voor het hele apparaat om tegelijk actief te zijn.</span><span class="sxs-lookup"><span data-stu-id="287e5-134">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="287e5-135">Hoewel er meerdere VPN-profielen op het apparaat kunnen bestaan, kan er slechts één VPN tegelijk actief zijn.</span><span class="sxs-lookup"><span data-stu-id="287e5-135">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a><span data-ttu-id="287e5-136">Microsoft Defender configureren voor eindpuntrisicosignaal in app-beveiligingsbeleid (MAM)</span><span class="sxs-lookup"><span data-stu-id="287e5-136">Configure Microsoft Defender for Endpoint risk signal in app protection policy (MAM)</span></span>

<span data-ttu-id="287e5-137">Microsoft Defender voor Eindpunt kan worden geconfigureerd voor het verzenden van bedreigingssignalen die moeten worden gebruikt in app-beveiligingsbeleid (APP, ook wel MAM genoemd) op iOS/iPadOS.</span><span class="sxs-lookup"><span data-stu-id="287e5-137">Microsoft Defender for Endpoint can be configured to send threat signals to be used in App Protection Policies (APP, also known as MAM) on iOS/iPadOS.</span></span> <span data-ttu-id="287e5-138">Met deze mogelijkheid kunt u Microsoft Defender voor Eindpunt gebruiken om de toegang tot bedrijfsgegevens te beschermen tegen niet-geregistreerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="287e5-138">With this capability, you can use Microsoft Defender for Endpoint to protect access to corporate data from unenrolled devices as well.</span></span>

<span data-ttu-id="287e5-139">Stappen voor het instellen van app-beveiligingsbeleid met Microsoft Defender voor Eindpunt zijn als hieronder:</span><span class="sxs-lookup"><span data-stu-id="287e5-139">Steps to setup app protection policies with Microsoft Defender for Endpoint are as below:</span></span>

1. <span data-ttu-id="287e5-140">Stel de verbinding in van uw Microsoft Endpoint Manager tenant met Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="287e5-140">Set up the connection from your Microsoft Endpoint Manager tenant to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="287e5-141">Ga in [het Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)naar **Tenant Administration** Connectors en tokens Microsoft Defender voor Eindpunt (onder Platform kruis) of Endpoint Security Microsoft Defender voor Eindpunt (onder Setup) en schakel de schakelaars in onder  >    >   App Protection   >   Policy Instellingen **voor iOS.**</span><span class="sxs-lookup"><span data-stu-id="287e5-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Tenant Administration** > **Connectors and tokens** > **Microsoft Defender for Endpoint** (under Cross platform) or **Endpoint Security** > **Microsoft Defender for Endpoint** (under Setup) and turn on the toggles under **App Protection Policy Settings for iOS**.</span></span>
1. <span data-ttu-id="287e5-142">Kies Opslaan.</span><span class="sxs-lookup"><span data-stu-id="287e5-142">Select Save.</span></span> <span data-ttu-id="287e5-143">De **verbindingsstatus** is nu ingesteld op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="287e5-143">You should see **Connection status** is now set to **Enabled**.</span></span>
1. <span data-ttu-id="287e5-144">Beleid voor app-beveiliging maken: Nadat de installatie van de Microsoft Defender voor eindpuntconnector is voltooid, gaat u naar **Apps** App-beveiligingsbeleid (onder Beleid) om een nieuw beleid te maken of een bestaand beleid  >   bij te werken.</span><span class="sxs-lookup"><span data-stu-id="287e5-144">Create app protection policy: After your Microsoft Defender for Endpoint connector setup is complete, navigate to **Apps** > **App protection policies** (under Policy) to create a new policy or update an existing one.</span></span>
1. <span data-ttu-id="287e5-145">Selecteer het platform, **apps, gegevensbescherming, Instellingen** voor Toegangsvereisten die uw organisatie voor uw beleid vereist.</span><span class="sxs-lookup"><span data-stu-id="287e5-145">Select the platform, **Apps, Data protection, Access requirements** settings that your organization requires for your policy.</span></span>
1. <span data-ttu-id="287e5-146">Onder **Voorwaarden voor voorwaardelijke** start Apparaat vindt u de instelling Max  >   **toegestaan apparaatbedreigingsniveau.**</span><span class="sxs-lookup"><span data-stu-id="287e5-146">Under **Conditional launch** > **Device conditions**, you will find the setting **Max allowed device threat level**.</span></span> <span data-ttu-id="287e5-147">Dit moet zijn geconfigureerd op Laag, Gemiddeld, Hoog of Beveiligd.</span><span class="sxs-lookup"><span data-stu-id="287e5-147">This will need to be configured to either Low, Medium, High, or Secured.</span></span> <span data-ttu-id="287e5-148">De acties die voor u beschikbaar zijn, zijn **Toegang blokkeren** of **Gegevens wissen.**</span><span class="sxs-lookup"><span data-stu-id="287e5-148">The actions available to you will be **Block access** or **Wipe data**.</span></span> <span data-ttu-id="287e5-149">Mogelijk ziet u een informatief dialoogvenster om ervoor te zorgen dat uw verbindingslijn is ingesteld voordat deze instelling van kracht wordt.</span><span class="sxs-lookup"><span data-stu-id="287e5-149">You may see an informational dialog to make sure you have your connector set up prior to this setting take effect.</span></span> <span data-ttu-id="287e5-150">Als de verbindingslijn al is ingesteld, kunt u dit dialoogvenster negeren.</span><span class="sxs-lookup"><span data-stu-id="287e5-150">If your connector is already set up, you may ignore this dialog.</span></span>
1. <span data-ttu-id="287e5-151">Werk af met Opdrachten en sla uw beleid op.</span><span class="sxs-lookup"><span data-stu-id="287e5-151">Finish with Assignments and save your policy.</span></span>

<span data-ttu-id="287e5-152">Zie beleidsinstellingen voor [iOS-appbeveiliging](https://docs.microsoft.com/mem/intune/apps/app-protection-policy-settings-ios)voor meer informatie over mam- of appbeveiligingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="287e5-152">For more details on MAM or app protection policy, see [iOS app protection policy settings](https://docs.microsoft.com/mem/intune/apps/app-protection-policy-settings-ios).</span></span>

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a><span data-ttu-id="287e5-153">Microsoft Defender voor Eindpunt implementeren voor MAM of op niet-geregistreerde apparaten</span><span class="sxs-lookup"><span data-stu-id="287e5-153">Deploying Microsoft Defender for Endpoint for MAM or on unenrolled devices</span></span>

<span data-ttu-id="287e5-154">Microsoft Defender voor Eindpunt op iOS maakt het scenario Voor app-beveiliging mogelijk en is beschikbaar in de Apple App Store.</span><span class="sxs-lookup"><span data-stu-id="287e5-154">Microsoft Defender for Endpoint on iOS enables the App Protection Policy scenario and is available in the Apple app store.</span></span>

<span data-ttu-id="287e5-155">Eindgebruikers moeten de nieuwste versie van de app rechtstreeks vanuit de Apple App Store installeren.</span><span class="sxs-lookup"><span data-stu-id="287e5-155">End-users should install the latest version of the app directly from the Apple app store.</span></span>

## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="287e5-156">Compliancebeleid configureren voor jailbroken apparaten</span><span class="sxs-lookup"><span data-stu-id="287e5-156">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="287e5-157">Om ervoor te zorgen dat bedrijfsgegevens niet worden gebruikt op iOS-apparaten met een jailbroken, raden we u aan het volgende compliancebeleid in te stellen op Intune.</span><span class="sxs-lookup"><span data-stu-id="287e5-157">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="287e5-158">Jailbreakdetectie is een mogelijkheid die wordt geleverd door Microsoft Defender voor Eindpunt in iOS.</span><span class="sxs-lookup"><span data-stu-id="287e5-158">Jailbreak detection is a capability provided by Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="287e5-159">U wordt echter aangeraden dit beleid in te stellen als een extra verdedigingslaag tegen scenario's met een jailbreak.</span><span class="sxs-lookup"><span data-stu-id="287e5-159">However, we recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="287e5-160">Volg de onderstaande stappen om een compliancebeleid te maken tegen jailbroken apparaten.</span><span class="sxs-lookup"><span data-stu-id="287e5-160">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="287e5-161">Ga [Microsoft Endpoint Manager beheercentrum naar](https://go.microsoft.com/fwlink/?linkid=2109431)Beleid voor naleving van **apparaten**  ->    ->  **Beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="287e5-161">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="287e5-162">Selecteer 'iOS/iPadOS' als platform en klik op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="287e5-162">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="287e5-163">![Beleid maken](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="287e5-163">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="287e5-164">Geef een naam op van het beleid, bijvoorbeeld 'Compliancebeleid voor jailbreak'.</span><span class="sxs-lookup"><span data-stu-id="287e5-164">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="287e5-165">Klik op de pagina nalevingsinstellingen op om de sectie **Apparaattoestand** uit te vouwen en klik **op Blokkeren** voor **jailbroken apparaten.**</span><span class="sxs-lookup"><span data-stu-id="287e5-165">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="287e5-166">![Beleid Instellingen](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="287e5-166">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="287e5-167">Selecteer in **de sectie Actie voor niet-naleving** de acties volgens uw vereisten en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="287e5-167">In the **Action for noncompliance** section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="287e5-168">![Beleidsacties](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="287e5-168">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="287e5-169">Selecteer in **de sectie** Opdrachten de gebruikersgroepen die u wilt opnemen voor dit beleid en selecteer **vervolgens Volgende**.</span><span class="sxs-lookup"><span data-stu-id="287e5-169">In the **Assignments** section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="287e5-170">Controleer in **de sectie Controleren+Maken** of alle ingevoerde gegevens juist zijn en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="287e5-170">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="287e5-171">Aangepaste indicatoren configureren</span><span class="sxs-lookup"><span data-stu-id="287e5-171">Configure custom indicators</span></span>

<span data-ttu-id="287e5-172">Met Defender voor Eindpunt in iOS kunnen beheerders ook aangepaste indicatoren configureren op iOS-apparaten.</span><span class="sxs-lookup"><span data-stu-id="287e5-172">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="287e5-173">Zie Indicatoren beheren voor meer informatie over het configureren van aangepaste [indicatoren.](/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="287e5-173">For more information on how to configure custom indicators, see [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="287e5-174">Defender voor Eindpunt in iOS ondersteunt het maken van aangepaste indicatoren alleen voor IP-adressen en URL's/domeinen.</span><span class="sxs-lookup"><span data-stu-id="287e5-174">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="287e5-175">Onveilige site rapporteren</span><span class="sxs-lookup"><span data-stu-id="287e5-175">Report unsafe site</span></span>

<span data-ttu-id="287e5-176">Phishingwebsites doen zich voor als betrouwbare websites om uw persoonlijke of financiële gegevens te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="287e5-176">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="287e5-177">Ga naar [de pagina Feedback geven over netwerkbeveiliging](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) als u een website wilt rapporteren die een phishingsite kan zijn.</span><span class="sxs-lookup"><span data-stu-id="287e5-177">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

