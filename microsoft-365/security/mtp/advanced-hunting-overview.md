---
title: Overzicht - Geavanceerde jacht
description: Meer informatie over geavanceerde jachtquery's in Microsoft 365 en hoe u deze gebruiken om proactief bedreigingen en zwakke punten in uw netwerk te vinden
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, schema, kusto, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 48850c76176d79e4f90581bfbab804f4649998cc
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049630"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Proactief jagen op bedreigingen met geavanceerde jacht in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Geavanceerde jacht is een op query gebaseerde hulpprogramma voor bedreigingsjacht waarmee u tot 30 dagen ruwe gegevens verkennen. U proactief gebeurtenissen in uw netwerk inspecteren om interessante indicatoren en entiteiten te vinden. De flexibele toegang tot gegevens vergemakkelijkt de ongebreidelde jacht op zowel bekende als potentiële bedreigingen.

U dezelfde query's voor bedreigingsjacht gebruiken om aangepaste detectieregels te maken. Deze regels worden automatisch uitgevoerd om te controleren op en te reageren op verschillende gebeurtenissen en systeemstatussen, waaronder vermoedelijke inbreukactiviteit en verkeerd geconfigureerde machines.

In het Microsoft 365-beveiligingscentrum ondersteunt geavanceerde jachtquery's die gegevens uit verschillende werkruimten bekijken, waaronder gegevens over apparaten, e-mails, apps en identiteiten van Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security en Azure ATP. Als u geavanceerde jacht wilt gebruiken, [schakelt u Microsoft Threat Protection in.](mtp-enable.md)

## <a name="get-started-with-advanced-hunting"></a>Aan de slag met geavanceerde jacht

We raden aan om verschillende stappen te doorlopen om snel aan de slag te gaan met geavanceerde jacht.

| Leerdoel | Beschrijving | Resource |
|--|--|--|
| **Krijg een gevoel voor de taal** | Geavanceerde jacht is gebaseerd op de [Kusto query taal,](https://docs.microsoft.com/azure/kusto/query/)ondersteuning van dezelfde syntaxis en operators. Begin met het leren van de querytaal door uw eerste query uit te voeren. | [Overzicht van querytaal](advanced-hunting-query-language.md) |
| **Meer informatie over het gebruik van de queryresultaten** | Meer informatie over grafieken en verschillende manieren waarop u uw resultaten bekijken of exporteren. Ontdek hoe u query's snel aanpassen en inzoomen om rijkere informatie te krijgen. | [Werken met queryresultaten](advanced-hunting-query-results.md) |
| **Meer informatie over het schema** | Krijg een goed inzicht op hoog niveau in de tabellen in het schema en hun kolommen. Zo u bepalen waar u gegevens moet zoeken en hoe u uw query's construeren. | [Schemaverwijzing](advanced-hunting-schema-tables.md) |
| **Vooraf gedefinieerde query's gebruiken** | Verken verzamelingen van vooraf gedefinieerde query's die verschillende scenario's voor bedreigingsjacht bestrijken. | - [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)<br>- [Ga jagen](advanced-hunting-go-hunt.md) |
| **Query's optimaliseren** | Lees hoe u efficiënte query's en query's maakt die gegevens van e-mails en apparaten combineren. | - [Aanbevolen procedures voor query's](advanced-hunting-shared-queries.md) <br>- [Hunt op verschillende apparaten en e-mails](advanced-hunting-best-practices.md) |
| **Aangepaste detectieregels maken** | Begrijp hoe u geavanceerde jachtquery's gebruiken om waarschuwingen te activeren en reactieacties automatisch toe te passen. | - [Overzicht van aangepaste detecties](custom-detections-overview.md)<br>- [Aangepaste detectieregels](custom-detection-rules.md) |

## <a name="get-access"></a>Toegang krijgen
Als u geavanceerde jacht- of andere [Microsoft Threat Protection-mogelijkheden](microsoft-threat-protection.md) wilt gebruiken, moet u een passende rol krijgen toegewezen in Azure AD. Houd er rekening mee dat uw toegang tot eindpuntgegevens wordt beïnvloed door op rollen gebaseerde toegangscontrole-instellingen in Microsoft Defender ATP. [Lees meer over het beheren van toegang tot Microsoft Threat Protection](mtp-permissions.md)


## <a name="related-topics"></a>Verwante onderwerpen
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)
