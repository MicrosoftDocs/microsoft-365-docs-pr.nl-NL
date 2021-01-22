---
title: Naamgevingswijzigingen in het Geavanceerde schema voor zoeken van Microsoft 365 Defender
description: Wijzigingen in tabellen en kolommen in het geavanceerde schema voor zoeken bijhouden en bekijken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, data, naming changes, rename, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932200"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Geavanceerd schema voor zoeken : naamgevingswijzigingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Het [geavanceerde schema voor zoeken](advanced-hunting-schema-tables.md) wordt regelmatig bijgewerkt om nieuwe tabellen en kolommen toe te voegen. In sommige gevallen worden bestaande kolomnamen gewijzigd of vervangen om de gebruikerservaring te verbeteren. Raadpleeg dit artikel voor meer informatie over naamgevingswijzigingen die van invloed kunnen zijn op uw query's.

Naamwijzigingen worden automatisch toegepast op query's die worden opgeslagen in het beveiligingscentrum, inclusief query's die worden gebruikt door aangepaste detectieregels. U hoeft deze query's niet handmatig bij te werken. U moet echter de volgende query's bijwerken:
- Query's die worden uitgevoerd met de API
- Query's die ergens anders buiten het beveiligingscentrum worden opgeslagen

## <a name="december-2020"></a>December 2020

| Tabelnaam | Oorspronkelijke kolomnaam | Nieuwe kolomnaam | Reden voor wijziging
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailAction | EmailAction | Feedback van klanten |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicy | EmailActionPolicy | Feedback van klanten |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicyGuid | EmailActionPolicyGuid | Feedback van klanten |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)