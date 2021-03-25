---
title: Microsoft Defender ATP voor Android-functies configureren
description: Beschrijft hoe u MICROSOFT Defender ATP voor Android configureert
keywords: microsoft, defender, atp, android, configuratie
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4325020e653f14898ece4192e03cbf8b90131136
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163445"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a><span data-ttu-id="b8ba2-104">Defender voor endpoint voor Android-functies configureren</span><span class="sxs-lookup"><span data-stu-id="b8ba2-104">Configure Defender for Endpoint for Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b8ba2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b8ba2-105">**Applies to:**</span></span>
- [<span data-ttu-id="b8ba2-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="b8ba2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b8ba2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8ba2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a><span data-ttu-id="b8ba2-108">Voorwaardelijke toegang met Defender voor Eindpunt voor Android</span><span class="sxs-lookup"><span data-stu-id="b8ba2-108">Conditional Access with Defender for Endpoint for Android</span></span>  
<span data-ttu-id="b8ba2-109">Microsoft Defender voor Eindpunt voor Android, samen met Microsoft Intune en Azure Active Directory, maakt het afdwingen van apparaat compliance en beleid voor voorwaardelijke toegang mogelijk op basis van apparaatrisiconiveaus.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-109">Microsoft Defender for Endpoint for Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="b8ba2-110">Defender for Endpoint is een MTD-oplossing (Mobile Threat Defense) die u kunt implementeren om gebruik te maken van deze mogelijkheid via Intune.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="b8ba2-111">Zie Defender voor Eindpunt en [Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)voor meer informatie over het instellen van Defender voor Eindpunt voor Android en Voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-111">For more information about how to set up Defender for Endpoint for Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="b8ba2-112">Aangepaste indicatoren configureren</span><span class="sxs-lookup"><span data-stu-id="b8ba2-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="b8ba2-113">Defender voor Eindpunt voor Android ondersteunt alleen het maken van aangepaste indicatoren voor IP-adressen en URL's/domeinen.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-113">Defender for Endpoint for Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="b8ba2-114">Met Defender voor Eindpunt voor Android kunnen beheerders aangepaste indicatoren configureren voor ondersteuning van Android-apparaten.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-114">Defender for Endpoint for Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="b8ba2-115">Zie Indicatoren beheren voor meer informatie over het configureren van aangepaste [indicatoren.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="b8ba2-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="b8ba2-116">Webbeveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="b8ba2-116">Configure web protection</span></span>
<span data-ttu-id="b8ba2-117">Met Defender voor Eindpunt voor Android kunnen IT-beheerders de webbeveiligingsfunctie configureren.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-117">Defender for Endpoint for Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="b8ba2-118">Deze mogelijkheid is beschikbaar in het Microsoft Endpoint Manager-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="b8ba2-119">Defender voor Eindpunt voor Android zou een VPN gebruiken om de webbeveiligingsfunctie te bieden.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-119">Defender for Endpoint for Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="b8ba2-120">Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.</span><span class="sxs-lookup"><span data-stu-id="b8ba2-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="b8ba2-121">Zie Webbeveiliging configureren op apparaten [met Android voor meer informatie.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)</span><span class="sxs-lookup"><span data-stu-id="b8ba2-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b8ba2-122">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b8ba2-122">Related topics</span></span>
- [<span data-ttu-id="b8ba2-123">Overzicht van Microsoft Defender voor Eindpunt voor Android</span><span class="sxs-lookup"><span data-stu-id="b8ba2-123">Overview of Microsoft Defender for Endpoint for Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="b8ba2-124">Microsoft Defender voor Eindpunt voor Android implementeren met Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b8ba2-124">Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune</span></span>](android-intune.md)
