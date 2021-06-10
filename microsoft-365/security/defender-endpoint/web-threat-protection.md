---
title: Uw organisatie beschermen tegen webbedreigingen
description: Meer informatie over webbeveiliging in Microsoft Defender voor Endpoint en hoe het uw organisatie kan beschermen.
keywords: webbeveiliging, bescherming tegen bedreigingen op het web, surfen op het web, beveiliging, phishing, malware, misbruik, websites, netwerkbeveiliging, Edge, Internet Explorer, Chrome, Firefox, webbrowser
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0c42c05e318390741b94b6d7d1b5394fca961714
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688943"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="51aa6-104">Uw organisatie beschermen tegen webbedreigingen</span><span class="sxs-lookup"><span data-stu-id="51aa6-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="51aa6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="51aa6-105">**Applies to:**</span></span>
- [<span data-ttu-id="51aa6-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="51aa6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="51aa6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51aa6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="51aa6-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="51aa6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="51aa6-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="51aa6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="51aa6-110">Webbedreigingsbeveiliging maakt deel uit [van webbeveiliging](web-protection-overview.md) in Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="51aa6-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="51aa6-111">Er wordt [netwerkbeveiliging gebruikt](network-protection.md) om uw apparaten te beveiligen tegen webbedreigingen.</span><span class="sxs-lookup"><span data-stu-id="51aa6-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="51aa6-112">Door te integreren met Microsoft Edge en populaire browsers van derden, zoals Chrome en Firefox, worden webbedreigingen gestopt zonder een webproxy en kunnen apparaten worden beschermd terwijl ze niet of on-premises zijn.</span><span class="sxs-lookup"><span data-stu-id="51aa6-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="51aa6-113">Beveiliging tegen webbedreigingen stopt de toegang tot phishingsites, malwarevectoren, misbruiksites, niet-vertrouwde of slechte reputatiesites, evenals sites die u hebt geblokkeerd in de lijst met aangepaste [indicatoren.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="51aa6-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="51aa6-114">Het kan tot een uur duren voordat apparaten nieuwe aangepaste indicatoren ontvangen.</span><span class="sxs-lookup"><span data-stu-id="51aa6-114">It can take up to an hour for devices to receive new custom indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="51aa6-115">Vereisten</span><span class="sxs-lookup"><span data-stu-id="51aa6-115">Prerequisites</span></span>
<span data-ttu-id="51aa6-116">Webbeveiliging gebruikt netwerkbeveiliging om webbrowserbeveiliging te bieden in Microsoft Edge webbrowsers van derden.</span><span class="sxs-lookup"><span data-stu-id="51aa6-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="51aa6-117">Netwerkbeveiliging op uw apparaten in- en uit te zetten:</span><span class="sxs-lookup"><span data-stu-id="51aa6-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="51aa6-118">Bewerk de beveiligingslijn Defender voor Eindpunt onder **Web & Netwerkbeveiliging** om netwerkbeveiliging in te stellen voordat u deze implementeert of opnieuw implementeert.</span><span class="sxs-lookup"><span data-stu-id="51aa6-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="51aa6-119">Meer informatie over het controleren en toewijzen van de beveiligingslijn defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="51aa6-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="51aa6-120">Schakel netwerkbeveiliging in met de configuratie van Intune-apparaten, SCCM, Groepsbeleid of uw MDM-oplossing.</span><span class="sxs-lookup"><span data-stu-id="51aa6-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="51aa6-121">Meer informatie over het inschakelen van netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="51aa6-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="51aa6-122">Als u netwerkbeveiliging in stelt op **Alleen controleren,** is blokkeren niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="51aa6-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="51aa6-123">U kunt ook pogingen om toegang tot schadelijke en ongewenste websites op Microsoft Edge detecteren en loggen.</span><span class="sxs-lookup"><span data-stu-id="51aa6-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="51aa6-124">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="51aa6-124">Related topics</span></span>

- [<span data-ttu-id="51aa6-125">Overzicht webbeveiliging</span><span class="sxs-lookup"><span data-stu-id="51aa6-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="51aa6-126">Webbedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="51aa6-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="51aa6-127">Webbeveiliging monitoren</span><span class="sxs-lookup"><span data-stu-id="51aa6-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="51aa6-128">Reageren op webbedreigingen</span><span class="sxs-lookup"><span data-stu-id="51aa6-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="51aa6-129">Netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="51aa6-129">Network protection</span></span>](network-protection.md)
