---
title: Integratie van Microsoft 365 Defender met Azure Sentinel
description: Gebruik Azure Sentinel als siem voor Microsoft 365 Defender incidenten en gebeurtenissen.
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
ms.openlocfilehash: adb65c82713464da2df4d473d2fd7a055e0dbeb3
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415576"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="6e10f-104">Integratie van Microsoft 365 Defender met Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="6e10f-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6e10f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6e10f-105">**Applies to:**</span></span>
- <span data-ttu-id="6e10f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e10f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6e10f-107">Met Microsoft 365 Defender connector voor Azure Sentinel (preview) worden alle Microsoft 365 Defender meldingen naar Azure Sentinel en worden de incidenten gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="6e10f-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="6e10f-108">Wanneer u de verbindingslijn toevoegt, worden Microsoft 365 Defender-incidenten met alle bijbehorende waarschuwingen, entiteiten en relevante informatie die is ontvangen van Microsoft Defender voor Eindpunt, Microsoft Defender voor identiteit, Microsoft Defender voor Office 365 en Microsoft Cloud App Security gestreamd naar Azure Sentinel als siem-gegevens (Security Information and Event Management), zodat u context hebt om triage- en incidentrespons uit te voeren met &mdash; &mdash; Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="6e10f-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="6e10f-109">Eenmaal in Azure Sentinel blijven incidenten tweerichtingsgesynchroniseerd met Microsoft 365 Defender, zodat u kunt profiteren van de voordelen van zowel de Microsoft 365 Defender-portal als Azure Sentinel in de Azure-portal voor incidentonderzoek en -reactie.</span><span class="sxs-lookup"><span data-stu-id="6e10f-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 Defender portal and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="6e10f-110">Bekijk dit korte overzicht van Azure Sentinel-integratie met Microsoft 365 Defender (4 minuten).</span><span class="sxs-lookup"><span data-stu-id="6e10f-110">Watch this short overview of Azure Sentinel integration with Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


<span data-ttu-id="6e10f-111">Dit doet u als u dit doet.</span><span class="sxs-lookup"><span data-stu-id="6e10f-111">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="De stroom en het delen van incidentgegevens tussen Microsoft 365 Defender en Azure Sentinel":::

## <a name="next-steps"></a><span data-ttu-id="6e10f-113">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="6e10f-113">Next steps</span></span>

1. <span data-ttu-id="6e10f-114">Krijg meer inzicht in Microsoft 365 Defender [integratie met Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)</span><span class="sxs-lookup"><span data-stu-id="6e10f-114">Get a deeper understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="6e10f-115">[Verbinding maken gegevens uit Microsoft 365 Defender Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="6e10f-115">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="6e10f-116">Zie ook</span><span class="sxs-lookup"><span data-stu-id="6e10f-116">See also</span></span>

- [<span data-ttu-id="6e10f-117">Overzicht van incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e10f-117">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="6e10f-118">Incidenten met Azure Sentinel onderzoeken</span><span class="sxs-lookup"><span data-stu-id="6e10f-118">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
