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
ms.openlocfilehash: 834ce13917237dd822bdfbb7b88967dcac4bc0f8
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929011"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="8bd1f-104">Microsoft Defender voor eindpunt configureren voor iOS-functies</span><span class="sxs-lookup"><span data-stu-id="8bd1f-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8bd1f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8bd1f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8bd1f-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8bd1f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8bd1f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8bd1f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8bd1f-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8bd1f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8bd1f-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="8bd1f-110">Defender voor Eindpunt in iOS zou een VPN gebruiken om de functie Webbeveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="8bd1f-111">Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="8bd1f-112">Voorwaardelijke toegang met Defender voor Eindpunt in iOS</span><span class="sxs-lookup"><span data-stu-id="8bd1f-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="8bd1f-113">Microsoft Defender voor Eindpunt op iOS, samen met Microsoft Intune en Azure Active Directory, maakt het afdwingen van apparaat compliance en beleid voor voorwaardelijke toegang mogelijk op basis van apparaatrisiconiveaus.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="8bd1f-114">Defender for Endpoint is een MTD-oplossing (Mobile Threat Defense) die u kunt implementeren om gebruik te maken van deze mogelijkheid via Intune.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="8bd1f-115">Zie Defender voor Eindpunt en [Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)voor meer informatie over het instellen van Voorwaardelijke toegang met Defender voor Eindpunt in iOS.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="8bd1f-116">Webbeveiliging en VPN</span><span class="sxs-lookup"><span data-stu-id="8bd1f-116">Web Protection and VPN</span></span>

<span data-ttu-id="8bd1f-117">Defender voor Eindpunt in iOS bevat standaard de functie voor webbeveiliging en schakelt deze in.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-117">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="8bd1f-118">[Webbeveiliging helpt](web-protection-overview.md) om apparaten te beveiligen tegen webbedreigingen en gebruikers te beschermen tegen phishingaanvallen.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-118">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="8bd1f-119">Defender voor Endpoint in iOS gebruikt een VPN om deze beveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-119">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="8bd1f-120">Let op: dit is een lokale VPN en in tegenstelling tot traditionele VPN wordt netwerkverkeer niet buiten het apparaat verzonden.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-120">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="8bd1f-121">Hoewel deze standaard is ingeschakeld, zijn er mogelijk bepaalde gevallen waarvoor u VPN moet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-121">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="8bd1f-122">U wilt bijvoorbeeld bepaalde apps uitvoeren die niet werken wanneer een VPN is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-122">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="8bd1f-123">In dergelijke gevallen kunt u ervoor kiezen om VPN uit te schakelen vanuit de app op het apparaat door de onderstaande stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="8bd1f-123">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="8bd1f-124">Open de app Instellingen  op uw iOS-apparaat, klik of tik **op Algemeen** en vervolgens **op VPN.**</span><span class="sxs-lookup"><span data-stu-id="8bd1f-124">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="8bd1f-125">Klik of tik op de knop 'i' voor Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-125">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="8bd1f-126">Schakel Verbinding maken **op aanvraag uit om** VPN uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-126">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8bd1f-127">![VPN config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="8bd1f-127">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="8bd1f-128">Webbeveiliging is niet beschikbaar wanneer VPN is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-128">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="8bd1f-129">Als u Webbeveiliging opnieuw wilt inschakelen, opent u de Microsoft Defender voor Eindpunt-app op het apparaat en klikt of tikt u op **Start VPN**.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-129">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="8bd1f-130">Co-bestaan van meerdere VPN-profielen</span><span class="sxs-lookup"><span data-stu-id="8bd1f-130">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="8bd1f-131">Apple iOS biedt geen ondersteuning voor meerdere VPN's voor het hele apparaat om tegelijk actief te zijn.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-131">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="8bd1f-132">Hoewel er meerdere VPN-profielen op het apparaat kunnen bestaan, kan er slechts één VPN tegelijk actief zijn.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-132">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="8bd1f-133">Compliancebeleid configureren voor jailbroken apparaten</span><span class="sxs-lookup"><span data-stu-id="8bd1f-133">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="8bd1f-134">Om ervoor te zorgen dat bedrijfsgegevens niet worden gebruikt op iOS-apparaten met een jailbroken, raden we u aan het volgende compliancebeleid in te stellen op Intune.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-134">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="8bd1f-135">Op dit moment biedt Microsoft Defender voor Eindpunt in iOS geen bescherming tegen scenario's met een jailbreak.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-135">At this time Microsoft Defender for Endpoint on iOS does not provide protection against jailbreak scenarios.</span></span> <span data-ttu-id="8bd1f-136">Als het apparaat wordt gebruikt op een jailbroken apparaat, kunnen in specifieke scenario's gegevens die door de toepassing worden gebruikt, zoals uw bedrijfs-e-mail-id en bedrijfsprofielafbeelding (indien beschikbaar), lokaal worden getoond.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-136">If used on a jailbroken device, then in specific scenarios data that is used by the application like your corporate email id and corporate profile picture (if available) can be exposed locally</span></span>

<span data-ttu-id="8bd1f-137">Volg de onderstaande stappen om een compliancebeleid te maken tegen jailbroken apparaten.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-137">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="8bd1f-138">Ga [in het Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)naar Beleid voor naleving van   ->  **apparaten**  ->  **Beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="8bd1f-138">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="8bd1f-139">Selecteer 'iOS/iPadOS' als platform en klik op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="8bd1f-139">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8bd1f-140">![Beleid maken](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="8bd1f-140">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="8bd1f-141">Geef een naam op van het beleid, bijvoorbeeld 'Compliancebeleid voor jailbreak'.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-141">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="8bd1f-142">Klik op de pagina nalevingsinstellingen op om de sectie **Apparaattoestand** uit te vouwen en klik **op Blokkeren** voor **jailbroken apparaten.**</span><span class="sxs-lookup"><span data-stu-id="8bd1f-142">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8bd1f-143">![Beleidsinstellingen](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="8bd1f-143">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="8bd1f-144">Selecteer in *de sectie Actie voor niet-naleving* de acties volgens uw vereisten en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="8bd1f-144">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8bd1f-145">![Beleidsacties](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="8bd1f-145">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="8bd1f-146">Selecteer in *de sectie* Opdrachten de gebruikersgroepen die u wilt opnemen voor dit beleid en selecteer **vervolgens Volgende**.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-146">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="8bd1f-147">Controleer in **de sectie Controleren+Maken** of alle ingevoerde gegevens juist zijn en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="8bd1f-147">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="8bd1f-148">Aangepaste indicatoren configureren</span><span class="sxs-lookup"><span data-stu-id="8bd1f-148">Configure custom indicators</span></span>

<span data-ttu-id="8bd1f-149">Met Defender voor Eindpunt in iOS kunnen beheerders ook aangepaste indicatoren configureren op iOS-apparaten.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-149">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="8bd1f-150">Zie Indicatoren beheren voor meer informatie over het configureren van aangepaste [indicatoren.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="8bd1f-150">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="8bd1f-151">Defender voor Eindpunt in iOS ondersteunt het maken van aangepaste indicatoren alleen voor IP-adressen en URL's/domeinen.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-151">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="8bd1f-152">Onveilige site rapporteren</span><span class="sxs-lookup"><span data-stu-id="8bd1f-152">Report unsafe site</span></span>

<span data-ttu-id="8bd1f-153">Phishingwebsites doen zich voor als betrouwbare websites om uw persoonlijke of financiële gegevens te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-153">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="8bd1f-154">Ga naar [de pagina Feedback geven over netwerkbeveiliging](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) als u een website wilt rapporteren die een phishingsite kan zijn.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-154">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a><span data-ttu-id="8bd1f-155">Problemen met batterijverbruik in iOS wanneer Microsoft Defender voor Eindpunt is geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="8bd1f-155">Battery Consumption issues on iOS when Microsoft Defender for Endpoint is installed</span></span>

<span data-ttu-id="8bd1f-156">Het batterijgebruik door een app wordt door Apple berekend op basis van een groot aantal factoren, waaronder cpu- en netwerkgebruik.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-156">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="8bd1f-157">Microsoft Defender voor Eindpunt gebruikt een lokale/lus-back VPN op de achtergrond om het webverkeer te controleren op schadelijke websites of verbindingen.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-157">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="8bd1f-158">Netwerkpakketten van een app worden door deze controle heen en daardoor wordt het batterijgebruik van Microsoft Defender voor Eindpunt onjuist berekend.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-158">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="8bd1f-159">Dit geeft een onjuiste indruk voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-159">This gives a false impression to the user.</span></span> <span data-ttu-id="8bd1f-160">Het werkelijke batterijverbruik van Microsoft Defender voor Eindpunt is lager dan wat wordt weergegeven op de pagina Batterijinstellingen op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-160">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="8bd1f-161">Dit is gebaseerd op tests die zijn uitgevoerd in de Microsoft Defender voor Eindpunt-app om het batterijverbruik te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-161">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="8bd1f-162">Ook de GEBRUIKTE VPN is een lokale VPN en in tegenstelling tot traditionele VPN's wordt netwerkverkeer niet buiten het apparaat verzonden.</span><span class="sxs-lookup"><span data-stu-id="8bd1f-162">Also the VPN used is a local VPN and unlike traditional VPNs, network traffic is not sent outside the device.</span></span>
