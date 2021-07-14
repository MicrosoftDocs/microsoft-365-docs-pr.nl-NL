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
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Integratie van Microsoft 365 Defender met Azure Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Met Microsoft 365 Defender connector voor Azure Sentinel (preview) worden alle Microsoft 365 Defender meldingen naar Azure Sentinel en worden de incidenten gesynchroniseerd. 

Wanneer u de verbindingslijn toevoegt, worden Microsoft 365 Defender-incidenten met alle bijbehorende waarschuwingen, entiteiten en relevante informatie die is ontvangen van Microsoft Defender voor Eindpunt, Microsoft Defender voor identiteit, Microsoft Defender voor Office 365 en Microsoft Cloud App Security gestreamd naar Azure Sentinel als siem-gegevens (Security Information and Event Management), zodat u context hebt om triage- en incidentrespons uit te voeren met &mdash; &mdash; Azure Sentinel. 

Eenmaal in Azure Sentinel blijven incidenten tweerichtingsgesynchroniseerd met Microsoft 365 Defender, zodat u kunt profiteren van de voordelen van zowel de Microsoft 365 Defender-portal als Azure Sentinel in de Azure-portal voor incidentonderzoek en -reactie.

Bekijk dit korte overzicht van Azure Sentinel-integratie met Microsoft 365 Defender (4 minuten).

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


Dit doet u als u dit doet.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="De stroom en het delen van incidentgegevens tussen Microsoft 365 Defender en Azure Sentinel":::

## <a name="next-steps"></a>Volgende stappen

1. Krijg meer inzicht in Microsoft 365 Defender [integratie met Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)
2. [Verbinding maken gegevens uit Microsoft 365 Defender Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).

## <a name="see-also"></a>Zie ook

- [Overzicht van incidenten in Microsoft 365 Defender](incidents-overview.md)
- [Incidenten met Azure Sentinel onderzoeken](/azure/sentinel/tutorial-investigate-cases)
