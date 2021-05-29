---
title: Microsoft 365 Defender-integratie met Azure Sentinel
description: Gebruik Azure Sentinel als siem voor Microsoft 365 defender-incidenten en -gebeurtenissen.
keywords: incidenten, waarschuwingen, onderzoeken, analyseren, reactie, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b5a53131733d1c7c539676c1d45abe7eabbe2de7
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707330"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="e6e7f-104">Microsoft 365 Defender-integratie met Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="e6e7f-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e6e7f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e6e7f-105">**Applies to:**</span></span>
- <span data-ttu-id="e6e7f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6e7f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e6e7f-107">De Microsoft 365 Defender-connector voor Azure Sentinel (preview) verzendt alle Microsoft 365 Defender-incidenten en waarschuwt informatie naar Azure Sentinel en houdt de incidenten gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="e6e7f-108">Wanneer u de verbindingslijn toevoegt, worden Microsoft 365 Defender-incidenten die alle bijbehorende waarschuwingen, entiteiten en relevante informatie bevatten die zijn ontvangen van Microsoft Defender voor Eindpunt, Microsoft Defender voor identiteit, Microsoft Defender voor Office 365 en Microsoft Cloud App Security gestreamd naar Azure Sentinel als gegevens over beveiligingsgegevens en gebeurtenisbeheer (SIEM), zodat u context hebt om triage- en incidentrespons uit te voeren met &mdash; &mdash; Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="e6e7f-109">Eenmaal in Azure Sentinel blijven incidenten tweerichtingsgesynchroniseerd met Microsoft 365 Defender, zodat u kunt profiteren van de voordelen van zowel het Microsoft 365-beveiligingscentrum als Azure Sentinel in de Azure-portal voor incidentonderzoek en -reactie.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 security center and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="e6e7f-110">Dit doet u als u dit doet.</span><span class="sxs-lookup"><span data-stu-id="e6e7f-110">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="De stroom en het delen van incidentgegevens tussen Microsoft 365 Defender en Azure Sentinel":::

## <a name="next-steps"></a><span data-ttu-id="e6e7f-112">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="e6e7f-112">Next steps</span></span>

1. <span data-ttu-id="e6e7f-113">Krijg meer inzicht in de [Microsoft 365 Defender-integratie met Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span><span class="sxs-lookup"><span data-stu-id="e6e7f-113">Get a better understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="e6e7f-114">[Verbinding maken gegevens van Microsoft 365 Defender naar Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="e6e7f-114">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="e6e7f-115">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e6e7f-115">See also</span></span>

- [<span data-ttu-id="e6e7f-116">Overzicht van incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6e7f-116">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="e6e7f-117">Incidenten met Azure Sentinel onderzoeken</span><span class="sxs-lookup"><span data-stu-id="e6e7f-117">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
