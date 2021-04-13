---
title: Microsoft Defender ATP preview-functies
description: Meer informatie over het openen van de preview-functies van Microsoft Defender voor eindpunten.
keywords: preview, preview-ervaring, Microsoft Defender voor Eindpunt, functies, updates
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
ms.openlocfilehash: 4a91fa3c8ff55f46619c7b49eaf973ad94f60bfe
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698184"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="aefc0-104">Microsoft Defender voor endpoint preview-functies</span><span class="sxs-lookup"><span data-stu-id="aefc0-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="aefc0-105">De preview-versies worden geleverd zonder serviceovereenkomst en worden niet aanbevolen voor productiebelastingen.</span><span class="sxs-lookup"><span data-stu-id="aefc0-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="aefc0-106">Bepaalde functies worden mogelijk niet ondersteund of hebben mogelijk beperkte mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="aefc0-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="aefc0-107">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="aefc0-107">**Applies to:**</span></span>
- [<span data-ttu-id="aefc0-108">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="aefc0-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aefc0-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aefc0-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aefc0-110">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="aefc0-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aefc0-111">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="aefc0-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="aefc0-112">De Defender voor Eindpunt-service wordt voortdurend bijgewerkt met nieuwe functieverbeteringen en -mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="aefc0-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="aefc0-113">Lees meer over nieuwe functies in de preview-release van Defender voor Eindpunt en probeer als een van de eersten toekomstige functies door de preview-ervaring in te- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="aefc0-113">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="aefc0-114">Ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in de feedlezer te kopiëren en te kopiëren: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span><span class="sxs-lookup"><span data-stu-id="aefc0-114">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span></span>

<span data-ttu-id="aefc0-115">Zie Nieuw in Defender voor eindpunt voor meer informatie over nieuwe mogelijkheden die algemeen [beschikbaar zijn.](whats-new-in-microsoft-defender-atp.md)</span><span class="sxs-lookup"><span data-stu-id="aefc0-115">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="aefc0-116">Preview-functies inschakelen</span><span class="sxs-lookup"><span data-stu-id="aefc0-116">Turn on preview features</span></span>

<span data-ttu-id="aefc0-117">U hebt toegang tot toekomstige functies waar u feedback over kunt geven om de algehele ervaring te verbeteren voordat functies algemeen beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="aefc0-117">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="aefc0-118">Schakel de preview-ervaringsinstelling in om een van de eersten te zijn om nieuwe functies uit te proberen.</span><span class="sxs-lookup"><span data-stu-id="aefc0-118">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="aefc0-119">Selecteer in het navigatiedeelvenster **Instellingen Geavanceerde**  >  **functies**  >  **Preview-functies.**</span><span class="sxs-lookup"><span data-stu-id="aefc0-119">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="aefc0-120">Schakel de instelling in tussen **Aan** en **Uit** en selecteer **Voorkeuren opslaan.**</span><span class="sxs-lookup"><span data-stu-id="aefc0-120">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="aefc0-121">Preview-functies</span><span class="sxs-lookup"><span data-stu-id="aefc0-121">Preview features</span></span>

<span data-ttu-id="aefc0-122">De volgende functies zijn opgenomen in de preview-release:</span><span class="sxs-lookup"><span data-stu-id="aefc0-122">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="aefc0-123">Apparaatdetectie</span><span class="sxs-lookup"><span data-stu-id="aefc0-123">Device discovery</span></span>](device-discovery.md) <br> <span data-ttu-id="aefc0-124">Helpt u bij het vinden van niet-beheerbare apparaten die zijn verbonden met uw bedrijfsnetwerk zonder dat u extra apparaten of lastige proceswijzigingen nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="aefc0-124">Helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span> <span data-ttu-id="aefc0-125">Met onboarded-apparaten kunt u onaangemande apparaten in uw netwerk vinden en beveiligingslekken en risico's beoordelen.</span><span class="sxs-lookup"><span data-stu-id="aefc0-125">Using onboarded devices, you can find unmanaged devices in your network and assess vulnerabilities and risks.</span></span> <span data-ttu-id="aefc0-126">U kunt vervolgens ontdekte apparaten aan boord nemen om de risico's te beperken die verbonden zijn aan het hebben van niet-gebouwde eindpunten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="aefc0-126">You can then onboard discovered devices to reduce risks associated with having unmanaged endpoints in your network.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="aefc0-127">Standaarddetectie is de standaardmodus voor alle preview-klanten vanaf 10 mei 2021.</span><span class="sxs-lookup"><span data-stu-id="aefc0-127">Standard discovery will be the default mode for all preview customers starting May 10, 2021.</span></span> <span data-ttu-id="aefc0-128">U kunt ervoor kiezen om de basismodus te behouden via de pagina Instellingen.</span><span class="sxs-lookup"><span data-stu-id="aefc0-128">You can choose to retain the basic mode through the settings page.</span></span> 


- [<span data-ttu-id="aefc0-129">Filteren op webinhoud</span><span class="sxs-lookup"><span data-stu-id="aefc0-129">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="aefc0-130">Filteren van webinhoud maakt deel uit van de mogelijkheden voor webbeveiliging in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="aefc0-130">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="aefc0-131">Hiermee kan uw organisatie de toegang tot websites bijhouden en reguleren op basis van hun inhoudscategorieën.</span><span class="sxs-lookup"><span data-stu-id="aefc0-131">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="aefc0-132">Veel van deze websites, hoewel niet schadelijk, kunnen problematisch zijn vanwege nalevingsregels, bandbreedtegebruik of andere problemen.</span><span class="sxs-lookup"><span data-stu-id="aefc0-132">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="aefc0-133">Rapport apparaattoestand en naleving</span><span class="sxs-lookup"><span data-stu-id="aefc0-133">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="aefc0-134">Het rapport apparaattoestand en compliance bevat informatie op hoog niveau over de apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="aefc0-134">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="aefc0-135">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="aefc0-135">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aefc0-136">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="aefc0-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
