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
ms.openlocfilehash: d32d40ac8ce086caedd53e0a69aac2a3025dc702
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842252"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="18d41-104">Microsoft Defender voor eindpunt configureren voor iOS-functies</span><span class="sxs-lookup"><span data-stu-id="18d41-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="18d41-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="18d41-105">**Applies to:**</span></span>
- [<span data-ttu-id="18d41-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="18d41-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="18d41-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18d41-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="18d41-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="18d41-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="18d41-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="18d41-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="18d41-110">Defender voor Eindpunt in iOS zou een VPN gebruiken om de functie Webbeveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="18d41-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="18d41-111">Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.</span><span class="sxs-lookup"><span data-stu-id="18d41-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="18d41-112">Voorwaardelijke toegang met Defender voor Eindpunt in iOS</span><span class="sxs-lookup"><span data-stu-id="18d41-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="18d41-113">Microsoft Defender voor Eindpunt op iOS, samen met Microsoft Intune en Azure Active Directory, maakt het afdwingen van apparaat compliance en beleid voor Voorwaardelijke toegang mogelijk op basis van apparaatrisicoscore.</span><span class="sxs-lookup"><span data-stu-id="18d41-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="18d41-114">Defender for Endpoint is een MTD-oplossing (Mobile Threat Defense) die u kunt implementeren om gebruik te maken van deze mogelijkheid via Intune.</span><span class="sxs-lookup"><span data-stu-id="18d41-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="18d41-115">Zie Defender voor Eindpunt en [Intune](/mem/intune/protect/advanced-threat-protection)voor meer informatie over het instellen van Voorwaardelijke toegang met Defender voor Eindpunt in iOS.</span><span class="sxs-lookup"><span data-stu-id="18d41-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a><span data-ttu-id="18d41-116">Jailbreakdetectie door Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="18d41-116">Jailbreak detection by Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="18d41-117">Microsoft Defender voor Eindpunt heeft de mogelijkheid om niet-beheerde en beheerde apparaten te detecteren die in de bajes staan.</span><span class="sxs-lookup"><span data-stu-id="18d41-117">Microsoft Defender for Endpoint has the capability of detecting unmanaged and managed devices that are jailbroken.</span></span> <span data-ttu-id="18d41-118">Als wordt vastgesteld dat een apparaat een jailbroken is, wordt een waarschuwing met hoog risico gerapporteerd aan het Beveiligingscentrum en als Voorwaardelijke toegang is ingesteld op basis van de apparaatrisicoscore, wordt het apparaat geblokkeerd voor toegang tot bedrijfsgegevens.</span><span class="sxs-lookup"><span data-stu-id="18d41-118">If a device is detected to be jailbroken, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="18d41-119">Webbeveiliging en VPN</span><span class="sxs-lookup"><span data-stu-id="18d41-119">Web Protection and VPN</span></span>

<span data-ttu-id="18d41-120">Defender voor Eindpunt in iOS bevat standaard de functie voor webbeveiliging en schakelt deze in.</span><span class="sxs-lookup"><span data-stu-id="18d41-120">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="18d41-121">[Webbeveiliging helpt](web-protection-overview.md) om apparaten te beveiligen tegen webbedreigingen en gebruikers te beschermen tegen phishingaanvallen.</span><span class="sxs-lookup"><span data-stu-id="18d41-121">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="18d41-122">Defender voor Endpoint in iOS gebruikt een VPN om deze beveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="18d41-122">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="18d41-123">Let op: dit is een lokale VPN en in tegenstelling tot traditionele VPN wordt netwerkverkeer niet buiten het apparaat verzonden.</span><span class="sxs-lookup"><span data-stu-id="18d41-123">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="18d41-124">Hoewel deze standaard is ingeschakeld, zijn er mogelijk bepaalde gevallen waarvoor u VPN moet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="18d41-124">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="18d41-125">U wilt bijvoorbeeld bepaalde apps uitvoeren die niet werken wanneer een VPN is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="18d41-125">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="18d41-126">In dergelijke gevallen kunt u ervoor kiezen om VPN uit te schakelen vanuit de app op het apparaat door de onderstaande stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="18d41-126">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="18d41-127">Open op uw iOS-apparaat de **Instellingen** app, klik of tik **op Algemeen** en vervolgens **op VPN.**</span><span class="sxs-lookup"><span data-stu-id="18d41-127">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="18d41-128">Klik of tik op de knop 'i' voor Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="18d41-128">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="18d41-129">Schakel de optie **Verbinding maken op aanvraag uit om** VPN uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="18d41-129">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="18d41-130">![VPN config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="18d41-130">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="18d41-131">Webbeveiliging is niet beschikbaar wanneer VPN is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="18d41-131">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="18d41-132">Als u Webbeveiliging opnieuw wilt inschakelen, opent u de Microsoft Defender voor Eindpunt-app op het apparaat en klikt of tikt u op **Start VPN**.</span><span class="sxs-lookup"><span data-stu-id="18d41-132">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="18d41-133">Co-bestaan van meerdere VPN-profielen</span><span class="sxs-lookup"><span data-stu-id="18d41-133">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="18d41-134">Apple iOS biedt geen ondersteuning voor meerdere VPN's voor het hele apparaat om tegelijk actief te zijn.</span><span class="sxs-lookup"><span data-stu-id="18d41-134">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="18d41-135">Hoewel er meerdere VPN-profielen op het apparaat kunnen bestaan, kan er slechts één VPN tegelijk actief zijn.</span><span class="sxs-lookup"><span data-stu-id="18d41-135">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="18d41-136">Compliancebeleid configureren voor jailbroken apparaten</span><span class="sxs-lookup"><span data-stu-id="18d41-136">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="18d41-137">Om ervoor te zorgen dat bedrijfsgegevens niet worden gebruikt op iOS-apparaten met een jailbroken, raden we u aan het volgende compliancebeleid in te stellen op Intune.</span><span class="sxs-lookup"><span data-stu-id="18d41-137">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="18d41-138">Jailbreakdetectie is een mogelijkheid die wordt geleverd door Microsoft Defender voor Eindpunt in iOS.</span><span class="sxs-lookup"><span data-stu-id="18d41-138">Jailbreak detection is a capability provided by Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="18d41-139">U wordt echter aangeraden dit beleid in te stellen als een extra verdedigingslaag tegen scenario's met een jailbreak.</span><span class="sxs-lookup"><span data-stu-id="18d41-139">However, we recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="18d41-140">Volg de onderstaande stappen om een compliancebeleid te maken tegen jailbroken apparaten.</span><span class="sxs-lookup"><span data-stu-id="18d41-140">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="18d41-141">Ga [Microsoft Endpoint Manager beheercentrum naar](https://go.microsoft.com/fwlink/?linkid=2109431)Beleid voor naleving van **apparaten**  ->    ->  **Beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="18d41-141">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="18d41-142">Selecteer 'iOS/iPadOS' als platform en klik op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="18d41-142">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="18d41-143">![Beleid maken](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="18d41-143">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="18d41-144">Geef een naam op van het beleid, bijvoorbeeld 'Compliancebeleid voor jailbreak'.</span><span class="sxs-lookup"><span data-stu-id="18d41-144">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="18d41-145">Klik op de pagina nalevingsinstellingen op om de sectie **Apparaattoestand** uit te vouwen en klik **op Blokkeren** voor **jailbroken apparaten.**</span><span class="sxs-lookup"><span data-stu-id="18d41-145">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="18d41-146">![Beleid Instellingen](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="18d41-146">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="18d41-147">Selecteer in *de sectie Actie voor niet-naleving* de acties volgens uw vereisten en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="18d41-147">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="18d41-148">![Beleidsacties](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="18d41-148">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="18d41-149">Selecteer in *de sectie* Opdrachten de gebruikersgroepen die u wilt opnemen voor dit beleid en selecteer **vervolgens Volgende**.</span><span class="sxs-lookup"><span data-stu-id="18d41-149">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="18d41-150">Controleer in **de sectie Controleren+Maken** of alle ingevoerde gegevens juist zijn en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="18d41-150">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="18d41-151">Aangepaste indicatoren configureren</span><span class="sxs-lookup"><span data-stu-id="18d41-151">Configure custom indicators</span></span>

<span data-ttu-id="18d41-152">Met Defender voor Eindpunt in iOS kunnen beheerders ook aangepaste indicatoren configureren op iOS-apparaten.</span><span class="sxs-lookup"><span data-stu-id="18d41-152">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="18d41-153">Zie Indicatoren beheren voor meer informatie over het configureren van aangepaste [indicatoren.](/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="18d41-153">For more information on how to configure custom indicators, see [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="18d41-154">Defender voor Eindpunt in iOS ondersteunt het maken van aangepaste indicatoren alleen voor IP-adressen en URL's/domeinen.</span><span class="sxs-lookup"><span data-stu-id="18d41-154">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="18d41-155">Onveilige site rapporteren</span><span class="sxs-lookup"><span data-stu-id="18d41-155">Report unsafe site</span></span>

<span data-ttu-id="18d41-156">Phishingwebsites doen zich voor als betrouwbare websites om uw persoonlijke of financiële gegevens te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="18d41-156">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="18d41-157">Ga naar [de pagina Feedback geven over netwerkbeveiliging](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) als u een website wilt rapporteren die een phishingsite kan zijn.</span><span class="sxs-lookup"><span data-stu-id="18d41-157">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

