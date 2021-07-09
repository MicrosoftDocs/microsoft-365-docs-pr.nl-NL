---
title: Microsoft Defender voor endpoint preview-functies
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
ms.openlocfilehash: 0b6edbdcda61eaf402275ae0b6dc9a38c5fe19f7
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339488"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="f5c0b-104">Microsoft Defender voor endpoint preview-functies</span><span class="sxs-lookup"><span data-stu-id="f5c0b-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f5c0b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f5c0b-105">**Applies to:**</span></span>
- [<span data-ttu-id="f5c0b-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f5c0b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f5c0b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5c0b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f5c0b-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f5c0b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f5c0b-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="f5c0b-110">De Defender voor Eindpunt-service wordt voortdurend bijgewerkt met nieuwe functieverbeteringen en -mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-110">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="f5c0b-111">Lees meer over nieuwe functies in de preview-release van Defender voor Eindpunt en probeer als een van de eersten toekomstige functies door de preview-ervaring in te- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-111">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="f5c0b-112">Ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in de feedlezer te kopiëren en te kopiëren: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="f5c0b-112">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="f5c0b-113">Zie Nieuw in Defender voor eindpunt voor meer informatie over nieuwe mogelijkheden die algemeen [beschikbaar zijn.](whats-new-in-microsoft-defender-atp.md)</span><span class="sxs-lookup"><span data-stu-id="f5c0b-113">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="f5c0b-114">Wat u moet weten</span><span class="sxs-lookup"><span data-stu-id="f5c0b-114">What you need to know</span></span>

<span data-ttu-id="f5c0b-115">Als u werkt met functies in een openbaar voorbeeld, zijn deze functies:</span><span class="sxs-lookup"><span data-stu-id="f5c0b-115">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="f5c0b-116">Kan beperkte of beperkte functionaliteit hebben.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-116">May have restricted or limited functionality.</span></span> <span data-ttu-id="f5c0b-117">De functie kan bijvoorbeeld slechts op één platform van toepassing zijn.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-117">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="f5c0b-118">Meestal worden functiewijzigingen doorgevoerd voordat ze algemeen beschikbaar zijn (GA).</span><span class="sxs-lookup"><span data-stu-id="f5c0b-118">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="f5c0b-119">Worden volledig ondersteund door Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-119">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="f5c0b-120">Is mogelijk alleen beschikbaar in geselecteerde geografische regio's of cloudomgevingen.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-120">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="f5c0b-121">De functie bestaat bijvoorbeeld mogelijk niet in de cloud van de overheid.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-121">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="f5c0b-122">Afzonderlijke functies in de preview-versie hebben mogelijk meer gebruiks- en ondersteuningsbeperkingen.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-122">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="f5c0b-123">Als dat zo is, wordt deze informatie meestal vermeld in de documentatie van de functie.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-123">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="f5c0b-124">De preview-versies worden geleverd met een standaardondersteuningsniveau en kunnen worden gebruikt voor productieomgevingen.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-124">The preview versions are provided with a standard support level, and can be used for production environments.</span></span> 



## <a name="turn-on-preview-features"></a><span data-ttu-id="f5c0b-125">Preview-functies inschakelen</span><span class="sxs-lookup"><span data-stu-id="f5c0b-125">Turn on preview features</span></span>

<span data-ttu-id="f5c0b-126">U hebt toegang tot toekomstige functies waar u feedback over kunt geven om de algehele ervaring te verbeteren voordat functies algemeen beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-126">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="f5c0b-127">Schakel de preview-ervaringsinstelling in om een van de eersten te zijn om nieuwe functies uit te proberen.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-127">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="f5c0b-128">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Geavanceerde functies**  >  **Preview-functies.**</span><span class="sxs-lookup"><span data-stu-id="f5c0b-128">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="f5c0b-129">Schakel de instelling in tussen **Aan** en **Uit** en selecteer **Voorkeuren opslaan.**</span><span class="sxs-lookup"><span data-stu-id="f5c0b-129">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="f5c0b-130">Preview-functies</span><span class="sxs-lookup"><span data-stu-id="f5c0b-130">Preview features</span></span>

<span data-ttu-id="f5c0b-131">De volgende functies zijn opgenomen in de preview-release:</span><span class="sxs-lookup"><span data-stu-id="f5c0b-131">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="f5c0b-132">Filteren op webinhoud</span><span class="sxs-lookup"><span data-stu-id="f5c0b-132">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="f5c0b-133">Filteren van webinhoud maakt deel uit van de mogelijkheden voor webbeveiliging in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-133">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f5c0b-134">Hiermee kan uw organisatie de toegang tot websites bijhouden en reguleren op basis van hun inhoudscategorieën.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-134">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="f5c0b-135">Veel van deze websites, hoewel niet schadelijk, kunnen problematisch zijn vanwege nalevingsregels, bandbreedtegebruik of andere problemen.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-135">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="f5c0b-136">Rapport apparaattoestand en naleving</span><span class="sxs-lookup"><span data-stu-id="f5c0b-136">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="f5c0b-137">Het rapport apparaattoestand en compliance bevat informatie op hoog niveau over de apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-137">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="f5c0b-138">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f5c0b-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f5c0b-139">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="f5c0b-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
