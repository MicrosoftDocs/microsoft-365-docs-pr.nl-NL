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
ms.openlocfilehash: 370048586c5ddfa6fa9ea265e929608357adf5df
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186879"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="86aaf-104">Microsoft Defender voor endpoint preview-functies</span><span class="sxs-lookup"><span data-stu-id="86aaf-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="86aaf-105">De preview-versies worden geleverd zonder serviceovereenkomst en worden niet aanbevolen voor productiebelastingen.</span><span class="sxs-lookup"><span data-stu-id="86aaf-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="86aaf-106">Bepaalde functies worden mogelijk niet ondersteund of hebben mogelijk beperkte mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="86aaf-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="86aaf-107">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="86aaf-107">**Applies to:**</span></span>
- [<span data-ttu-id="86aaf-108">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="86aaf-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="86aaf-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86aaf-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="86aaf-110">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="86aaf-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="86aaf-111">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="86aaf-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="86aaf-112">De Defender voor Eindpunt-service wordt voortdurend bijgewerkt met nieuwe functieverbeteringen en -mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="86aaf-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

> [!TIP]
> <span data-ttu-id="86aaf-113">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="86aaf-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="86aaf-114">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="86aaf-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-abovefoldlink)

<span data-ttu-id="86aaf-115">Lees meer over nieuwe functies in de preview-release van Defender voor Eindpunt en probeer als een van de eersten toekomstige functies door de preview-ervaring in te- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="86aaf-115">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="86aaf-116">Ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in de feedlezer te kopiëren en te kopiëren: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span><span class="sxs-lookup"><span data-stu-id="86aaf-116">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span></span>

<span data-ttu-id="86aaf-117">Zie Nieuw in Defender voor eindpunt voor meer informatie over nieuwe mogelijkheden die algemeen [beschikbaar zijn.](whats-new-in-microsoft-defender-atp.md)</span><span class="sxs-lookup"><span data-stu-id="86aaf-117">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="86aaf-118">Preview-functies inschakelen</span><span class="sxs-lookup"><span data-stu-id="86aaf-118">Turn on preview features</span></span>

<span data-ttu-id="86aaf-119">U hebt toegang tot toekomstige functies waar u feedback over kunt geven om de algehele ervaring te verbeteren voordat functies algemeen beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="86aaf-119">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="86aaf-120">Schakel de preview-ervaringsinstelling in om een van de eersten te zijn om nieuwe functies uit te proberen.</span><span class="sxs-lookup"><span data-stu-id="86aaf-120">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="86aaf-121">Selecteer in het navigatiedeelvenster **Instellingen Geavanceerde**  >  **functies**  >  **Preview-functies.**</span><span class="sxs-lookup"><span data-stu-id="86aaf-121">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="86aaf-122">Schakel de instelling in tussen **Aan** en **Uit** en selecteer **Voorkeuren opslaan.**</span><span class="sxs-lookup"><span data-stu-id="86aaf-122">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="86aaf-123">Preview-functies</span><span class="sxs-lookup"><span data-stu-id="86aaf-123">Preview features</span></span>

<span data-ttu-id="86aaf-124">De volgende functies zijn opgenomen in de preview-release:</span><span class="sxs-lookup"><span data-stu-id="86aaf-124">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="86aaf-125">Filteren op webinhoud</span><span class="sxs-lookup"><span data-stu-id="86aaf-125">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="86aaf-126">Filteren van webinhoud maakt deel uit van de mogelijkheden voor webbeveiliging in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="86aaf-126">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="86aaf-127">Hiermee kan uw organisatie de toegang tot websites bijhouden en reguleren op basis van hun inhoudscategorieën.</span><span class="sxs-lookup"><span data-stu-id="86aaf-127">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="86aaf-128">Veel van deze websites, hoewel niet schadelijk, kunnen problematisch zijn vanwege nalevingsregels, bandbreedtegebruik of andere problemen.</span><span class="sxs-lookup"><span data-stu-id="86aaf-128">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="86aaf-129">Rapport apparaattoestand en naleving</span><span class="sxs-lookup"><span data-stu-id="86aaf-129">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="86aaf-130">Het rapport apparaattoestand en compliance bevat informatie op hoog niveau over de apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="86aaf-130">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

- [<span data-ttu-id="86aaf-131">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="86aaf-131">Information protection</span></span>](information-protection-in-windows-overview.md)<BR>
<span data-ttu-id="86aaf-132">Informatiebeveiliging is een integraal onderdeel van de Microsoft 365 Enterprise-suite en biedt intelligente beveiliging om gevoelige gegevens veilig te houden en productiviteit op de werkplek in te stellen.</span><span class="sxs-lookup"><span data-stu-id="86aaf-132">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span> <span data-ttu-id="86aaf-133">Microsoft Defender voor Eindpunt is naadloos geïntegreerd in Microsoft Threat Protection om een volledige en uitgebreide oplossing voor preventie van gegevensverlies (DLP) te bieden voor Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="86aaf-133">Microsoft Defender for Endpoint is seamlessly integrated in Microsoft Threat Protection to provide a complete and comprehensive data loss prevention (DLP) solution for Windows devices.</span></span>

    >[!NOTE]
    ><span data-ttu-id="86aaf-134">Gedeeltelijk beschikbaar in Windows 10, versie 1809.</span><span class="sxs-lookup"><span data-stu-id="86aaf-134">Partially available from Windows 10, version 1809.</span></span>

- [<span data-ttu-id="86aaf-135">Onboard Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="86aaf-135">Onboard Windows Server 2019</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-version-1803-and-windows-server-2019) <BR> <span data-ttu-id="86aaf-136">Microsoft Defender voor Eindpunt voegt nu ondersteuning toe voor Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="86aaf-136">Microsoft Defender for Endpoint now adds support for Windows Server 2019.</span></span> <span data-ttu-id="86aaf-137">U kunt Windows Server 2019 aan boord nemen volgens dezelfde methode die beschikbaar is voor Windows 10-clientapparaten.</span><span class="sxs-lookup"><span data-stu-id="86aaf-137">You'll be able to onboard Windows Server 2019 in the same method available for Windows 10 client devices.</span></span>


> [!TIP] 
> <span data-ttu-id="86aaf-138">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="86aaf-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="86aaf-139">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="86aaf-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
