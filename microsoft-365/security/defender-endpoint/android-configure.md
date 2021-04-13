---
title: Microsoft Defender configureren voor endpoint op Android-functies
description: Hier wordt beschreven hoe u Microsoft Defender voor Eindpunt configureert op Android
keywords: microsoft, defender, atp, mde, android, configuratie
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
ms.openlocfilehash: 8ec4a19bdd641c721bfcd7be2ceb59de1de92963
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688031"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a><span data-ttu-id="b182f-104">Defender voor endpoint voor Android-functies configureren</span><span class="sxs-lookup"><span data-stu-id="b182f-104">Configure Defender for Endpoint for Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b182f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b182f-105">**Applies to:**</span></span>
- [<span data-ttu-id="b182f-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b182f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b182f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b182f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a><span data-ttu-id="b182f-108">Voorwaardelijke toegang met Defender voor Eindpunt voor Android</span><span class="sxs-lookup"><span data-stu-id="b182f-108">Conditional Access with Defender for Endpoint for Android</span></span>  
<span data-ttu-id="b182f-109">Microsoft Defender voor Eindpunt op Android, samen met Microsoft Intune en Azure Active Directory, maakt het afdwingen van apparaat compliance en beleid voor voorwaardelijke toegang mogelijk op basis van apparaatrisiconiveaus.</span><span class="sxs-lookup"><span data-stu-id="b182f-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="b182f-110">Defender for Endpoint is een MTD-oplossing (Mobile Threat Defense) die u kunt implementeren om gebruik te maken van deze mogelijkheid via Intune.</span><span class="sxs-lookup"><span data-stu-id="b182f-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="b182f-111">Zie Defender voor Eindpunt en [Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)voor meer informatie over het instellen van Defender voor Eindpunt voor Android en Voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="b182f-111">For more information about how to set up Defender for Endpoint for Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="b182f-112">Aangepaste indicatoren configureren</span><span class="sxs-lookup"><span data-stu-id="b182f-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="b182f-113">Defender voor Eindpunt voor Android ondersteunt alleen het maken van aangepaste indicatoren voor IP-adressen en URL's/domeinen.</span><span class="sxs-lookup"><span data-stu-id="b182f-113">Defender for Endpoint for Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="b182f-114">Met Defender voor Eindpunt voor Android kunnen beheerders aangepaste indicatoren configureren voor ondersteuning van Android-apparaten.</span><span class="sxs-lookup"><span data-stu-id="b182f-114">Defender for Endpoint for Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="b182f-115">Zie Indicatoren beheren voor meer informatie over het configureren van aangepaste [indicatoren.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="b182f-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="b182f-116">Webbeveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="b182f-116">Configure web protection</span></span>
<span data-ttu-id="b182f-117">Met Defender voor Eindpunt voor Android kunnen IT-beheerders de webbeveiligingsfunctie configureren.</span><span class="sxs-lookup"><span data-stu-id="b182f-117">Defender for Endpoint for Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="b182f-118">Deze mogelijkheid is beschikbaar in het Microsoft Endpoint Manager-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b182f-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="b182f-119">Defender voor Eindpunt voor Android zou een VPN gebruiken om de webbeveiligingsfunctie te bieden.</span><span class="sxs-lookup"><span data-stu-id="b182f-119">Defender for Endpoint for Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="b182f-120">Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.</span><span class="sxs-lookup"><span data-stu-id="b182f-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="b182f-121">Zie Webbeveiliging configureren op apparaten [met Android voor meer informatie.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)</span><span class="sxs-lookup"><span data-stu-id="b182f-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b182f-122">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b182f-122">Related topics</span></span>
- [<span data-ttu-id="b182f-123">Overzicht van Microsoft Defender voor Eindpunt voor Android</span><span class="sxs-lookup"><span data-stu-id="b182f-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="b182f-124">Microsoft Defender voor eindpunt implementeren op Android met Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b182f-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
