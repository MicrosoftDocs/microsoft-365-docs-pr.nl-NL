---
title: Microsoft Defender voor Eindpunt in Android-functies configureren
description: Hier wordt beschreven hoe u Microsoft Defender voor Eindpunt configureert op Android
keywords: microsoft, defender, Microsoft Defender voor Eindpunt, mde, android, configuratie
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935315"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a><span data-ttu-id="5f67a-104">Defender voor eindpunt configureren op Android-functies</span><span class="sxs-lookup"><span data-stu-id="5f67a-104">Configure Defender for Endpoint on Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5f67a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5f67a-105">**Applies to:**</span></span>
- [<span data-ttu-id="5f67a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5f67a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5f67a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f67a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a><span data-ttu-id="5f67a-108">Voorwaardelijke toegang met Defender voor Eindpunt op Android</span><span class="sxs-lookup"><span data-stu-id="5f67a-108">Conditional Access with Defender for Endpoint on Android</span></span>  
<span data-ttu-id="5f67a-109">Microsoft Defender voor Eindpunt op Android, samen met Microsoft Intune en Azure Active Directory, maakt het afdwingen van apparaat compliance en beleid voor voorwaardelijke toegang mogelijk op basis van apparaatrisiconiveaus.</span><span class="sxs-lookup"><span data-stu-id="5f67a-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="5f67a-110">Defender for Endpoint is een MTD-oplossing (Mobile Threat Defense) die u kunt implementeren om gebruik te maken van deze mogelijkheid via Intune.</span><span class="sxs-lookup"><span data-stu-id="5f67a-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="5f67a-111">Zie Defender voor Eindpunt en [Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)voor meer informatie over het instellen van Defender voor eindpunten op Android en Voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="5f67a-111">For more information about how to set up Defender for Endpoint on Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="5f67a-112">Aangepaste indicatoren configureren</span><span class="sxs-lookup"><span data-stu-id="5f67a-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="5f67a-113">Defender voor Eindpunt op Android ondersteunt alleen het maken van aangepaste indicatoren voor IP-adressen en URL's/domeinen.</span><span class="sxs-lookup"><span data-stu-id="5f67a-113">Defender for Endpoint on Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="5f67a-114">Met Defender voor Eindpunt op Android kunnen beheerders aangepaste indicatoren configureren voor ondersteuning van Android-apparaten.</span><span class="sxs-lookup"><span data-stu-id="5f67a-114">Defender for Endpoint on Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="5f67a-115">Zie Indicatoren beheren voor meer informatie over het configureren van aangepaste [indicatoren.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="5f67a-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="5f67a-116">Webbeveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="5f67a-116">Configure web protection</span></span>
<span data-ttu-id="5f67a-117">Met Defender voor Eindpunt op Android kunnen IT-beheerders de webbeveiligingsfunctie configureren.</span><span class="sxs-lookup"><span data-stu-id="5f67a-117">Defender for Endpoint on Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="5f67a-118">Deze mogelijkheid is beschikbaar in het Microsoft Endpoint Manager-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="5f67a-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="5f67a-119">Defender voor Eindpunt op Android zou een VPN gebruiken om de webbeveiligingsfunctie te bieden.</span><span class="sxs-lookup"><span data-stu-id="5f67a-119">Defender for Endpoint on Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="5f67a-120">Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.</span><span class="sxs-lookup"><span data-stu-id="5f67a-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="5f67a-121">Zie Webbeveiliging configureren op apparaten [met Android voor meer informatie.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)</span><span class="sxs-lookup"><span data-stu-id="5f67a-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5f67a-122">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="5f67a-122">Related topics</span></span>
- [<span data-ttu-id="5f67a-123">Overzicht van Microsoft Defender voor Eindpunt op Android</span><span class="sxs-lookup"><span data-stu-id="5f67a-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="5f67a-124">Microsoft Defender voor Eindpunt op Android implementeren via Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5f67a-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
