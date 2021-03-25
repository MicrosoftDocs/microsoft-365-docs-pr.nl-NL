---
title: Microsoft Defender ATP configureren voor iOS-functies
description: Beschrijft hoe u MICROSOFT Defender ATP voor iOS-functies implementeert
keywords: microsoft, defender, atp, ios, configureren, functies, ios
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 90e65c57321fa05a62bc94f4f56d92062d0826a1
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186699"
---
# <a name="configure-microsoft-defender-for-endpoint-for-ios-features"></a><span data-ttu-id="dc9f2-104">Microsoft Defender configureren voor endpoint voor iOS-functies</span><span class="sxs-lookup"><span data-stu-id="dc9f2-104">Configure Microsoft Defender for Endpoint for iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dc9f2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="dc9f2-105">**Applies to:**</span></span>
- [<span data-ttu-id="dc9f2-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="dc9f2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dc9f2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc9f2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dc9f2-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="dc9f2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dc9f2-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="dc9f2-110">Defender voor Eindpunt voor iOS zou een VPN gebruiken om de functie Webbeveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-110">Defender for Endpoint for iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="dc9f2-111">Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a><span data-ttu-id="dc9f2-112">Voorwaardelijke toegang met Defender voor eindpunt voor iOS</span><span class="sxs-lookup"><span data-stu-id="dc9f2-112">Conditional Access with Defender for Endpoint for iOS</span></span>  
<span data-ttu-id="dc9f2-113">Microsoft Defender voor Eindpunt voor iOS, samen met Microsoft Intune en Azure Active Directory, maakt het afdwingen van apparaat compliance en beleid voor voorwaardelijke toegang mogelijk op basis van apparaatrisiconiveaus.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-113">Microsoft Defender for Endpoint for iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="dc9f2-114">Defender for Endpoint is een MTD-oplossing (Mobile Threat Defense) die u kunt implementeren om gebruik te maken van deze mogelijkheid via Intune.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="dc9f2-115">Zie Defender voor Eindpunt en [Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)voor meer informatie over het instellen van Voorwaardelijke toegang met Defender voor eindpunt voor iOS.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-115">For more information about how to set up Conditional Access with Defender for Endpoint for iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="dc9f2-116">Webbeveiliging en VPN</span><span class="sxs-lookup"><span data-stu-id="dc9f2-116">Web Protection and VPN</span></span>

<span data-ttu-id="dc9f2-117">Defender voor Eindpunt voor iOS bevat standaard de functie voor webbeveiliging en schakelt deze in.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-117">By default, Defender for Endpoint for iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="dc9f2-118">[Webbeveiliging helpt](web-protection-overview.md) om apparaten te beveiligen tegen webbedreigingen en gebruikers te beschermen tegen phishingaanvallen.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-118">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="dc9f2-119">Defender voor Endpoint voor iOS gebruikt een VPN om deze beveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-119">Defender for Endpoint for iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="dc9f2-120">Let op: dit is een lokale VPN en in tegenstelling tot traditionele VPN wordt netwerkverkeer niet buiten het apparaat verzonden.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-120">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="dc9f2-121">Hoewel deze standaard is ingeschakeld, zijn er mogelijk bepaalde gevallen waarvoor u VPN moet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-121">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="dc9f2-122">U wilt bijvoorbeeld bepaalde apps uitvoeren die niet werken wanneer een VPN is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-122">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="dc9f2-123">In dergelijke gevallen kunt u ervoor kiezen om VPN uit te schakelen vanuit de app op het apparaat door de onderstaande stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="dc9f2-123">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="dc9f2-124">Open de app Instellingen  op uw iOS-apparaat, klik of tik **op Algemeen** en vervolgens **op VPN.**</span><span class="sxs-lookup"><span data-stu-id="dc9f2-124">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="dc9f2-125">Klik of tik op de knop 'i' voor Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-125">Click or tap the "i" button for Microsoft Defender ATP.</span></span>
1. <span data-ttu-id="dc9f2-126">Schakel Verbinding maken **op aanvraag uit om** VPN uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-126">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dc9f2-127">![VPN config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="dc9f2-127">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="dc9f2-128">Webbeveiliging is niet beschikbaar wanneer VPN is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-128">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="dc9f2-129">Als u Webbeveiliging opnieuw wilt inschakelen, opent u de Microsoft Defender voor Eindpunt-app op het apparaat en klikt of tikt u op **Start VPN**.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-129">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="dc9f2-130">Co-bestaan van meerdere VPN-profielen</span><span class="sxs-lookup"><span data-stu-id="dc9f2-130">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="dc9f2-131">Apple iOS biedt geen ondersteuning voor meerdere VPN's voor het hele apparaat om tegelijk actief te zijn.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-131">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="dc9f2-132">Hoewel er meerdere VPN-profielen op het apparaat kunnen bestaan, kan er slechts één VPN tegelijk actief zijn.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-132">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="dc9f2-133">Compliancebeleid configureren voor jailbroken apparaten</span><span class="sxs-lookup"><span data-stu-id="dc9f2-133">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="dc9f2-134">Om ervoor te zorgen dat bedrijfsgegevens niet worden gebruikt op iOS-apparaten met een jailbroken, raden we u aan het volgende compliancebeleid in te stellen op Intune.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-134">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="dc9f2-135">Op dit moment biedt Microsoft Defender voor Endpoint voor iOS geen bescherming tegen jailbreakscenario's.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-135">At this time Microsoft Defender for Endpoint for iOS does not provide protection against jailbreak scenarios.</span></span> <span data-ttu-id="dc9f2-136">Als het apparaat wordt gebruikt op een jailbroken apparaat, kunnen in specifieke scenario's gegevens die door de toepassing worden gebruikt, zoals uw bedrijfs-e-mail-id en bedrijfsprofielafbeelding (indien beschikbaar), lokaal worden getoond.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-136">If used on a jailbroken device, then in specific scenarios data that is used by the application like your corporate email id and corporate profile picture (if available) can be exposed locally</span></span>

<span data-ttu-id="dc9f2-137">Volg de onderstaande stappen om een compliancebeleid te maken tegen jailbroken apparaten.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-137">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="dc9f2-138">Ga [in het Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)naar Beleid voor naleving van   ->  **apparaten**  ->  **Beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="dc9f2-138">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="dc9f2-139">Selecteer 'iOS/iPadOS' als platform en klik op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="dc9f2-139">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dc9f2-140">![Beleid maken](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="dc9f2-140">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="dc9f2-141">Geef een naam op van het beleid, bijvoorbeeld 'Compliancebeleid voor jailbreak'.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-141">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="dc9f2-142">Klik op de pagina nalevingsinstellingen op om de sectie **Apparaattoestand** uit te vouwen en klik **op Blokkeren** voor **jailbroken apparaten.**</span><span class="sxs-lookup"><span data-stu-id="dc9f2-142">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dc9f2-143">![Beleidsinstellingen](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="dc9f2-143">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="dc9f2-144">Selecteer in *de sectie Actie voor niet-naleving* de acties volgens uw vereisten en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="dc9f2-144">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dc9f2-145">![Beleidsacties](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="dc9f2-145">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="dc9f2-146">Selecteer in *de sectie* Opdrachten de gebruikersgroepen die u wilt opnemen voor dit beleid en selecteer **vervolgens Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-146">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="dc9f2-147">Controleer in **de sectie Controleren+Maken** of alle ingevoerde gegevens juist zijn en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="dc9f2-147">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="dc9f2-148">Aangepaste indicatoren configureren</span><span class="sxs-lookup"><span data-stu-id="dc9f2-148">Configure custom indicators</span></span>

<span data-ttu-id="dc9f2-149">Met Defender voor Eindpunt voor iOS kunnen beheerders ook aangepaste indicatoren configureren op iOS-apparaten.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-149">Defender for Endpoint for iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="dc9f2-150">Zie Indicatoren beheren voor meer informatie over het configureren van aangepaste [indicatoren.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="dc9f2-150">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="dc9f2-151">Defender voor Eindpunt voor iOS ondersteunt het maken van aangepaste indicatoren alleen voor IP-adressen en URL's/domeinen.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-151">Defender for Endpoint for iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="dc9f2-152">Onveilige site rapporteren</span><span class="sxs-lookup"><span data-stu-id="dc9f2-152">Report unsafe site</span></span>

<span data-ttu-id="dc9f2-153">Phishingwebsites doen zich voor als betrouwbare websites om uw persoonlijke of financiële gegevens te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-153">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="dc9f2-154">Ga naar [de pagina Feedback geven over netwerkbeveiliging](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) als u een website wilt rapporteren die een phishingsite kan zijn.</span><span class="sxs-lookup"><span data-stu-id="dc9f2-154">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>
