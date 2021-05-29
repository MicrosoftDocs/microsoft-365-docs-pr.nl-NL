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
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365 Defender-integratie met Azure Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

De Microsoft 365 Defender-connector voor Azure Sentinel (preview) verzendt alle Microsoft 365 Defender-incidenten en waarschuwt informatie naar Azure Sentinel en houdt de incidenten gesynchroniseerd. 

Wanneer u de verbindingslijn toevoegt, worden Microsoft 365 Defender-incidenten die alle bijbehorende waarschuwingen, entiteiten en relevante informatie bevatten die zijn ontvangen van Microsoft Defender voor Eindpunt, Microsoft Defender voor identiteit, Microsoft Defender voor Office 365 en Microsoft Cloud App Security gestreamd naar Azure Sentinel als gegevens over beveiligingsgegevens en gebeurtenisbeheer (SIEM), zodat u context hebt om triage- en incidentrespons uit te voeren met &mdash; &mdash; Azure Sentinel. 

Eenmaal in Azure Sentinel blijven incidenten tweerichtingsgesynchroniseerd met Microsoft 365 Defender, zodat u kunt profiteren van de voordelen van zowel het Microsoft 365-beveiligingscentrum als Azure Sentinel in de Azure-portal voor incidentonderzoek en -reactie.

Dit doet u als u dit doet.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="De stroom en het delen van incidentgegevens tussen Microsoft 365 Defender en Azure Sentinel":::

## <a name="next-steps"></a>Volgende stappen

1. Krijg meer inzicht in de [Microsoft 365 Defender-integratie met Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).
2. [Verbinding maken gegevens van Microsoft 365 Defender naar Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).

## <a name="see-also"></a>Zie ook

- [Overzicht van incidenten in Microsoft 365 Defender](incidents-overview.md)
- [Incidenten met Azure Sentinel onderzoeken](/azure/sentinel/tutorial-investigate-cases)
