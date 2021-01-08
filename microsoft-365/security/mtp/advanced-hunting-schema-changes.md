---
title: Wijzigingen aanbrengen in het Microsoft 365 Defender Advanced jacht schema
description: Naam wijzigen en tabellen en kolommen wijzigen in het geavanceerde jacht schema
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, gegevens, naam wijzigen, naam wijzigen, Microsoft Threat Protection
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780783"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Naamwijzigingen in het schema voor geavanceerde jacht

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Het [schema geavanceerde jacht](advanced-hunting-schema-tables.md) wordt regelmatig bijgewerkt om nieuwe tabellen en kolommen toe te voegen. In sommige gevallen worden namen van bestaande kolommen gewijzigd of vervangen ter verbetering van de gebruikerservaring. Raadpleeg dit artikel om de naamwijzigingen te bekijken die van invloed kunnen zijn op uw query's.

Gewijzigde namen worden automatisch toegepast op query's die zijn opgeslagen in het Beveiligingscentrum, waaronder query's die worden gebruikt door aangepaste detectieregels. U hoeft deze query's niet handmatig bij te werken. U moet echter de volgende query's bijwerken:
- Query's die worden uitgevoerd met de API
- Query's die elders buiten het Beveiligingscentrum worden opgeslagen

## <a name="december-2020"></a>December 2020

| Tabelnaam | Naam van oorspronkelijke kolom | Naam van nieuwe kolom | Reden voor wijziging
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailAction | EmailAction | Feedback van klanten |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicy | EmailActionPolicy | Feedback van klanten |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicyGuid | EmailActionPolicyGuid | Feedback van klanten |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)