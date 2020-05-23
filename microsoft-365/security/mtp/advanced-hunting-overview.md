---
title: Overzicht - Geavanceerde jacht
description: Meer informatie over geavanceerde jachtquery's in Microsoft 365 en hoe u deze gebruiken om bedreigingen en zwakke punten in uw netwerk proactief te vinden
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, schema, kusto, microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 3e8f83b943e83c37ecf13af1221c043d413bd6b5
ms.sourcegitcommit: 8d9509e617ede7cc5ba933c54fb9300d2d1c6344
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/22/2020
ms.locfileid: "44347829"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Proactief op zoek naar bedreigingen met geavanceerde jacht in Microsoft Threat Protection

**Geldt voor:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Geavanceerde jacht is een query-gebaseerde bedreiging-jacht tool waarmee u verkennen tot 30 dagen van ruwe gegevens. U gebeurtenissen in uw netwerk proactief inspecteren om interessante indicatoren en entiteiten te vinden. De flexibele toegang tot gegevens vergemakkelijkt de ongedwongen jacht op zowel bekende als potentiële bedreigingen.

U dezelfde detectiequery's gebruiken om aangepaste detectieregels te maken. Deze regels worden automatisch uitgevoerd om te controleren op en te reageren op verschillende gebeurtenissen en systeemtoestanden, waaronder vermoedelijke inbreukactiviteiten en verkeerd geconfigureerde machines.

In het Microsoft 365-beveiligingscentrum ondersteunt advanced hunting query's die gegevens uit verschillende werkruimten bekijken, waaronder gegevens over apparaten, e-mails, apps en identiteiten van Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security en Azure ATP. Als u geavanceerde jacht wilt gebruiken, [schakelt u Microsoft Threat Protection in.](mtp-enable.md)

## <a name="get-started-with-advanced-hunting"></a>Aan de slag met geavanceerde jacht

We raden aan om verschillende stappen te doorlopen om snel aan de slag te gaan met geavanceerde jacht.

| Leerdoel | Beschrijving | Resource |
|--|--|--|
| **Krijg een gevoel voor de taal** | Geavanceerde jacht is gebaseerd op de [Kusto-querytaal,](https://docs.microsoft.com/azure/kusto/query/)die dezelfde syntaxis en operatoren ondersteunt. Begin met het leren van de querytaal door uw eerste query uit te voeren. | [Overzicht van querytalen](advanced-hunting-query-language.md) |
| **Meer informatie over het gebruik van de queryresultaten** | Meer informatie over grafieken en verschillende manieren waarop u uw resultaten bekijken of exporteren. Ontdek hoe u snel query's aanpassen en inzoomen om rijkere informatie te krijgen. | [Werken met queryresultaten](advanced-hunting-query-results.md) |
| **Meer informatie over het schema** | Krijg een goed, hoog niveau inzicht in de tabellen in het schema en hun kolommen. Zo u bepalen waar u naar gegevens moet zoeken en hoe u uw query's samenstellen. | [Schemaverwijzing](advanced-hunting-schema-tables.md) |
| **Vooraf gedefinieerde query's gebruiken** | Bekijk verzamelingen van vooraf gedefinieerde query's die verschillende scenario's voor bedreigingsjacht behandelen. | [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md) |
| **Query's optimaliseren** | Meer informatie over het maken van efficiënte query's en query's die gegevens van e-mails en apparaten combineren. | - [Aanbevolen procedures voor query's](advanced-hunting-shared-queries.md) <br>- [Jaag op apparaten en e-mails](advanced-hunting-best-practices.md) |
| **Aangepaste detectieregels maken** | Ontdek hoe u geavanceerde jachtquery's gebruiken om waarschuwingen te activeren en automatisch reactieacties toe te passen. | - [Overzicht van aangepaste detecties](custom-detections-overview.md)<br>- [Aangepaste detectieregels](custom-detection-rules.md) |

## <a name="get-access"></a>Krijg toegang
Als u geavanceerde jacht- of andere [Microsoft Threat Protection-mogelijkheden](microsoft-threat-protection.md) wilt gebruiken, moet u een geschikte rol in Azure AD krijgen toegewezen. Houd er rekening mee dat uw toegang tot eindpuntgegevens wordt beïnvloed door op rollen gebaseerde toegangscontrole-instellingen in Microsoft Defender ATP. [Lees meer over het beheren van toegang tot Microsoft Threat Protection](mtp-permissions.md)

## <a name="get-help-as-you-write-queries"></a>Hulp krijgen bij het schrijven van query's
Profiteer van de volgende functionaliteit om sneller query's te schrijven:
- **Automatisch voorstellen** - terwijl u query's schrijft, biedt geavanceerde jacht suggesties van IntelliSense. 
- **Schemaverwijzing** : naast uw werkgebied wordt een schemaverwijzing weergegeven met de lijst met tabellen en hun kolommen. Voor meer informatie, zweven over een item. Dubbelklik op een item om het in te voegen in de queryeditor.

## <a name="related-topics"></a>Verwante onderwerpen
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)
