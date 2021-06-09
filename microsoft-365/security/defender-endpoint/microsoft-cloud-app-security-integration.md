---
title: Overzicht van integratie van Microsoft Cloud App Security
ms.reviewer: ''
description: Microsoft Defender for Endpoint is geïntegreerd met Cloud App Security door alle netwerkactiviteiten voor cloud-apps door testuren.
keywords: cloud, app, netwerken, zichtbaarheid, gebruik
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844740"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="5371d-104">Microsoft Cloud App Security in Overzicht van Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5371d-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="5371d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5371d-105">**Applies to:**</span></span>
- [<span data-ttu-id="5371d-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5371d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5371d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5371d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="5371d-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="5371d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5371d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="5371d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5371d-110">Microsoft Cloud App Security (Cloud App Security) is een uitgebreide oplossing waarmee u inzicht krijgt in cloud-apps en -services doordat u de toegang tot cloud-apps kunt beheren en beperken, terwijl u nalevingsvereisten afdwingt voor gegevens die zijn opgeslagen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="5371d-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="5371d-111">Zie voor meer informatie [Cloud App Security.](/cloud-app-security/what-is-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="5371d-111">For more information, see [Cloud App Security](/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="5371d-112">Deze functie is beschikbaar met een E5-licentie [voor](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) Enterprise Mobility + Security apparaten met Windows 10 versie 1809 of hoger.</span><span class="sxs-lookup"><span data-stu-id="5371d-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="5371d-113">Microsoft Defender voor endpoint- en Cloud App Security-integratie</span><span class="sxs-lookup"><span data-stu-id="5371d-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="5371d-114">Cloud App Security discovery is afhankelijk van cloudverkeerslogboeken die worden doorgestuurd vanuit bedrijfsfirewall- en proxyservers.</span><span class="sxs-lookup"><span data-stu-id="5371d-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="5371d-115">Microsoft Defender voor Eindpunt is geïntegreerd met Cloud App Security door alle netwerkactiviteiten voor cloud-apps te verzamelen en door testuren, waardoor het gebruik van cloud-apps ongeëvenaard zichtbaar is.</span><span class="sxs-lookup"><span data-stu-id="5371d-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="5371d-116">De monitoringfunctionaliteit is ingebouwd in het apparaat, wat volledige dekking biedt voor netwerkactiviteit.</span><span class="sxs-lookup"><span data-stu-id="5371d-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="5371d-117">De integratie biedt de volgende belangrijke verbeteringen in de bestaande Cloud App Security detectie:</span><span class="sxs-lookup"><span data-stu-id="5371d-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="5371d-118">Overal beschikbaar: aangezien de netwerkactiviteit rechtstreeks vanuit het eindpunt wordt verzameld, is het beschikbaar op elke plaats waar het apparaat zich, in of buiten het bedrijfsnetwerk, bevinden, omdat deze niet meer afhankelijk is van verkeer dat wordt gerouteerd via de bedrijfsfirewall of proxyservers.</span><span class="sxs-lookup"><span data-stu-id="5371d-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="5371d-119">Werkt out of the box, geen configuratie vereist: het doorsturen van cloudverkeerlogboeken naar Cloud App Security vereist firewall- en proxyserverconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="5371d-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="5371d-120">Met de Defender voor Eindpunt en Cloud App Security is er geen configuratie vereist.</span><span class="sxs-lookup"><span data-stu-id="5371d-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="5371d-121">Schakel deze in in Microsoft Defender-beveiligingscentrum instellingen en u bent klaar om te gaan.</span><span class="sxs-lookup"><span data-stu-id="5371d-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="5371d-122">Apparaatcontext: cloudverkeerslogboeken hebben geen apparaatcontext.</span><span class="sxs-lookup"><span data-stu-id="5371d-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="5371d-123">Defender voor Endpoint-netwerkactiviteit wordt gerapporteerd met de apparaatcontext (welk apparaat toegang heeft tot de cloud-app), zodat u precies kunt begrijpen waar (apparaat) de netwerkactiviteit heeft plaatsgevonden, naast wie (gebruiker) de activiteit heeft uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="5371d-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="5371d-124">Zie Werken met ontdekte [apps](/cloud-app-security/discovered-apps)voor meer informatie over clouddetectie.</span><span class="sxs-lookup"><span data-stu-id="5371d-124">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="5371d-125">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="5371d-125">Related topic</span></span>

- [<span data-ttu-id="5371d-126">Integratie van Microsoft Cloud App Security configureren</span><span class="sxs-lookup"><span data-stu-id="5371d-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
