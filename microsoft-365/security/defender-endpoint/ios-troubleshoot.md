---
title: Problemen met Microsoft Defender voor Eindpunt oplossen in iOS
description: Probleemoplossing en veelgestelde vragen - Microsoft Defender voor Eindpunt op iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, troubleshoot, faq, how to
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
ms.openlocfilehash: 82a3fcc58b97f53f584befae77c86e8a18952a23
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539302"
---
# <a name="troubleshoot-issues-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="0c253-104">Problemen met Microsoft Defender voor Eindpunt oplossen in iOS</span><span class="sxs-lookup"><span data-stu-id="0c253-104">Troubleshoot issues on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0c253-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0c253-105">**Applies to:**</span></span>
- [<span data-ttu-id="0c253-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="0c253-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0c253-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c253-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0c253-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="0c253-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0c253-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="0c253-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="0c253-110">In dit onderwerp vindt u informatie over het oplossen van problemen die kunnen optreden wanneer u Microsoft Defender voor Eindpunt in iOS gebruikt.</span><span class="sxs-lookup"><span data-stu-id="0c253-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="0c253-111">Defender voor Eindpunt in iOS zou een VPN gebruiken om de functie Webbeveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="0c253-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="0c253-112">Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.</span><span class="sxs-lookup"><span data-stu-id="0c253-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="0c253-113">Apps werken niet wanneer VPN is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="0c253-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="0c253-114">Er zijn enkele apps die niet meer werken wanneer er een actieve VPN wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="0c253-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="0c253-115">U kunt de VPN uitschakelen tijdens het gebruik van dergelijke apps.</span><span class="sxs-lookup"><span data-stu-id="0c253-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="0c253-116">Defender voor Eindpunt in iOS bevat standaard de functie voor webbeveiliging en schakelt deze in.</span><span class="sxs-lookup"><span data-stu-id="0c253-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="0c253-117">[Webbeveiliging helpt](web-protection-overview.md) om apparaten te beveiligen tegen webbedreigingen en gebruikers te beschermen tegen phishingaanvallen.</span><span class="sxs-lookup"><span data-stu-id="0c253-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="0c253-118">Defender voor Endpoint in iOS gebruikt een VPN om deze beveiliging te bieden.</span><span class="sxs-lookup"><span data-stu-id="0c253-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="0c253-119">Let op: dit is een lokale VPN en in tegenstelling tot traditionele VPN wordt netwerkverkeer niet buiten het apparaat verzonden.</span><span class="sxs-lookup"><span data-stu-id="0c253-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="0c253-120">Hoewel deze standaard is ingeschakeld, zijn er mogelijk bepaalde gevallen waarvoor u VPN moet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="0c253-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="0c253-121">U wilt bijvoorbeeld bepaalde apps uitvoeren die niet werken wanneer een VPN is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="0c253-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="0c253-122">In dergelijke gevallen kunt u ervoor kiezen om VPN uit te schakelen vanuit de app op het apparaat door de onderstaande stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="0c253-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="0c253-123">Open op uw iOS-apparaat de **Instellingen** app, klik of tik **op Algemeen** en vervolgens **op VPN.**</span><span class="sxs-lookup"><span data-stu-id="0c253-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="0c253-124">Klik of tik op de knop 'i' voor Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="0c253-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="0c253-125">Schakel de optie **Verbinding maken op aanvraag uit om** VPN uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="0c253-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0c253-126">![VPN config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="0c253-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="0c253-127">Webbeveiliging is niet beschikbaar wanneer VPN is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0c253-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="0c253-128">Als u Webbeveiliging opnieuw wilt inschakelen, opent u de Microsoft Defender voor Eindpunt-app op het apparaat en klikt of tikt u op **Start VPN**.</span><span class="sxs-lookup"><span data-stu-id="0c253-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="0c253-129">Problemen met meerdere VPN-profielen</span><span class="sxs-lookup"><span data-stu-id="0c253-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="0c253-130">Apple iOS biedt geen ondersteuning voor meerdere VPN's voor het hele apparaat om tegelijk actief te zijn.</span><span class="sxs-lookup"><span data-stu-id="0c253-130">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="0c253-131">Hoewel er meerdere VPN-profielen op het apparaat kunnen bestaan, kan er slechts één VPN tegelijk actief zijn.</span><span class="sxs-lookup"><span data-stu-id="0c253-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="battery-consumption"></a><span data-ttu-id="0c253-132">Batterijverbruik</span><span class="sxs-lookup"><span data-stu-id="0c253-132">Battery consumption</span></span>

<span data-ttu-id="0c253-133">Het batterijgebruik door een app wordt door Apple berekend op basis van een groot aantal factoren, waaronder cpu- en netwerkgebruik.</span><span class="sxs-lookup"><span data-stu-id="0c253-133">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="0c253-134">Microsoft Defender voor Eindpunt gebruikt een lokale/lus-back VPN op de achtergrond om het webverkeer te controleren op schadelijke websites of verbindingen.</span><span class="sxs-lookup"><span data-stu-id="0c253-134">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="0c253-135">Netwerkpakketten van een app worden door deze controle heen en daardoor wordt het batterijgebruik van Microsoft Defender voor Eindpunt onjuist berekend.</span><span class="sxs-lookup"><span data-stu-id="0c253-135">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="0c253-136">Dit geeft een onjuiste indruk voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0c253-136">This gives a false impression to the user.</span></span> <span data-ttu-id="0c253-137">Het werkelijke batterijverbruik van Microsoft Defender voor Eindpunt is lager dan wat wordt weergegeven op de pagina Batterij Instellingen op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="0c253-137">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="0c253-138">Dit is gebaseerd op tests die zijn uitgevoerd in de Microsoft Defender voor Eindpunt-app om het batterijverbruik te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="0c253-138">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="0c253-139">Ook de gebruikte VPN is een lokale VPN en in tegenstelling tot een traditionele VPN wordt netwerkverkeer niet buiten het apparaat verzonden.</span><span class="sxs-lookup"><span data-stu-id="0c253-139">Also the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="0c253-140">Gegevensgebruik</span><span class="sxs-lookup"><span data-stu-id="0c253-140">Data usage</span></span>

<span data-ttu-id="0c253-141">Microsoft Defender for Endpoint gebruikt een lokale/lusback VPN om het webverkeer te controleren op schadelijke websites of verbindingen.</span><span class="sxs-lookup"><span data-stu-id="0c253-141">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="0c253-142">Om deze reden worden gegevensgebruik door Apple onjuist door Apple bij Microsoft Defender voor Eindpunt verwerkt.</span><span class="sxs-lookup"><span data-stu-id="0c253-142">Due to this reason Apple accounts data usage to Microsoft Defender for Endpoint inaccurately.</span></span> <span data-ttu-id="0c253-143">Het werkelijke gegevensgebruik door Microsoft Defender voor Eindpunt is niet significant en veel kleiner dan wat wordt weergegeven op het gegevensgebruik Instellingen op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="0c253-143">The actual data usage by Microsoft Defender for Endpoint is not significant and much less than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="0c253-144">Onveilige site rapporteren</span><span class="sxs-lookup"><span data-stu-id="0c253-144">Report unsafe site</span></span>

<span data-ttu-id="0c253-145">Phishingwebsites doen zich voor als betrouwbare websites om uw persoonlijke of financiële gegevens te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="0c253-145">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="0c253-146">Ga naar [de pagina Feedback geven over netwerkbeveiliging](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) om een website te rapporteren die een phishingsite kan zijn.</span><span class="sxs-lookup"><span data-stu-id="0c253-146">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="0c253-147">Schadelijke site gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="0c253-147">Malicious site detected</span></span>

<span data-ttu-id="0c253-148">Microsoft Defender voor Eindpunt beschermt u tegen phishing of andere webaanvallen.</span><span class="sxs-lookup"><span data-stu-id="0c253-148">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="0c253-149">Als er een schadelijke site wordt gedetecteerd, wordt de verbinding geblokkeerd en wordt er een waarschuwing verzonden naar de portal van het beveiligingscentrum van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="0c253-149">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="0c253-150">De waarschuwing bevat de domeinnaam van de verbinding, het externe IP-adres en de apparaatgegevens.</span><span class="sxs-lookup"><span data-stu-id="0c253-150">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="0c253-151">Daarnaast wordt er een melding weergegeven op het iOS-apparaat.</span><span class="sxs-lookup"><span data-stu-id="0c253-151">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="0c253-152">Als u op de melding tikt, wordt het volgende scherm geopend voor de gebruiker om de details te bekijken.</span><span class="sxs-lookup"><span data-stu-id="0c253-152">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0c253-153">![Afbeelding van site gerapporteerd als onveilige melding](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="0c253-153">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="0c253-154">Gegevens en privacy</span><span class="sxs-lookup"><span data-stu-id="0c253-154">Data and Privacy</span></span>

<span data-ttu-id="0c253-155">Zie Privacygegevens - Microsoft [Defender voor eindpunt in iOS](ios-privacy.md)voor meer informatie over verzamelde gegevens en privacy.</span><span class="sxs-lookup"><span data-stu-id="0c253-155">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

