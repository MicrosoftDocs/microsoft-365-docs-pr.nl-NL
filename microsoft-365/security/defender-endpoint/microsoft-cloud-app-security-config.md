---
title: Microsoft Cloud App Security-integratie configureren
ms.reviewer: ''
description: Meer informatie over het inschakelen van de instellingen om de Microsoft Defender for Endpoint-integratie met Microsoft Cloud App Security in te stellen.
keywords: cloud, app, beveiliging, instellingen, integratie, detectie, rapport
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
ms.openlocfilehash: ddf32b26191826ab6ecbad6b9d047ac7bbb6276a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060529"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a1918-104">Microsoft Cloud App-beveiliging configureren in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a1918-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a1918-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a1918-105">**Applies to:**</span></span>
- [<span data-ttu-id="a1918-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="a1918-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="a1918-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1918-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a1918-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a1918-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a1918-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="a1918-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="a1918-110">Als u wilt profiteren van detectiesignalen van Microsoft Defender voor endpoint-cloud-apps, schakelt u Microsoft Cloud App Security-integratie in.</span><span class="sxs-lookup"><span data-stu-id="a1918-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="a1918-111">Deze functie is beschikbaar met een E5-licentie voor [Enterprise Mobility + Beveiliging](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) op apparaten met Windows 10, versie 1709 (os build 16299.1085 met [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, versie 1803 (os build 17134.704 met [KB4493464),](https://support.microsoft.com/help/4493464)Windows 10, versie 1809 (os build 17763.379 met [KB4489899)](https://support.microsoft.com/help/4489899)of hoger Windows 10-versies.</span><span class="sxs-lookup"><span data-stu-id="a1918-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="a1918-112">Zie [Microsoft Defender voor endpoint-integratie met Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) voor gedetailleerde integratie van Microsoft Defender voor Eindpunt met Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="a1918-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a1918-113">Microsoft Cloud App-beveiliging inschakelen in Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="a1918-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="a1918-114">Selecteer in het navigatiedeelvenster **Voorkeuren instellen**  >  **Geavanceerde functies.**</span><span class="sxs-lookup"><span data-stu-id="a1918-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="a1918-115">Selecteer **Microsoft Cloud App-beveiliging** en schakel de wisselknop over naar **Aan.**</span><span class="sxs-lookup"><span data-stu-id="a1918-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="a1918-116">Klik **op Voorkeuren opslaan.**</span><span class="sxs-lookup"><span data-stu-id="a1918-116">Click **Save preferences**.</span></span>

<span data-ttu-id="a1918-117">Wanneer microsoft Defender voor Eindpunt is geactiveerd, worden detectiesignalen onmiddellijk doorgestuurd naar Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="a1918-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="a1918-118">De verzamelde gegevens weergeven</span><span class="sxs-lookup"><span data-stu-id="a1918-118">View the data collected</span></span>

<span data-ttu-id="a1918-119">Zie Apparaten onderzoeken [in Cloud App-beveiliging](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)voor informatie over het weergeven en openen van Microsoft Defender voor eindpuntgegevens in Microsoft Cloud Apps Security.</span><span class="sxs-lookup"><span data-stu-id="a1918-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="a1918-120">Zie Werken met ontdekte [apps](https://docs.microsoft.com/cloud-app-security/discovered-apps)voor meer informatie over clouddetectie.</span><span class="sxs-lookup"><span data-stu-id="a1918-120">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="a1918-121">Zie Microsoft Cloud App Security Trial als u microsoft Cloud App Security [wilt proberen.](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)</span><span class="sxs-lookup"><span data-stu-id="a1918-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="a1918-122">Gerelateerd onderwerp</span><span class="sxs-lookup"><span data-stu-id="a1918-122">Related topic</span></span>
- [<span data-ttu-id="a1918-123">Microsoft Cloud App Security-integratie</span><span class="sxs-lookup"><span data-stu-id="a1918-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
