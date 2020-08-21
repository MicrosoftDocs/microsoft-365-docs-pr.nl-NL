---
title: Rapport over niet-geaccepteerd domein in het dashboard voor de e-mail stroom
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u het niet-geaccepteerde domein rapport gebruikt in het dashboard voor e-mail stromen in de beveiligings & nalevings centrum voor het bewaken van berichten van uw on-premises organisatie waarbij het domein van de afzender niet is geconfigureerd in Microsoft 365.
ms.openlocfilehash: ef5f1c26168347b6696e90292d9c957e63615c0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826939"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Rapport over niet-geaccepteerd domein in de beveiligings & nalevings centrum

Het **niet-geaccepteerde domein** rapport op het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in de beveiligings & nalevings centrum geeft informatie weer over berichten van de on-premises e-mail organisatie waarbij het domein van de afzender niet is geconfigureerd als een geaccepteerd domein in uw Microsoft 365-organisatie.

In Microsoft 365 kunnen deze berichten worden beperkt als we gegevens hebben om te bewijzen dat de intentie van deze berichten schadelijk is. Daarom is het belangrijk om te begrijpen wat er gebeurt en om het probleem te verhelpen.

![Niet-geaccepteerd domein widget in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Rapportweergave voor het niet-geaccepteerde domein rapport

Door te klikken op het diagram in het **niet-geaccepteerde domein** object, gaat u naar het rapport **niet-geaccepteerd domein** .

Standaard wordt de activiteit voor alle desbetreffende verbindingslijnen weergegeven. Als u op **gegevens weergeven**klikt, kunt u een specifieke verbindingslijn selecteren in de vervolgkeuzelijst.

Als u de muisaanwijzer over een gegevenspunt (dag) van de grafiek houdt, ziet u het totale aantal berichten voor de verbindingslijn.

![Rapportweergave in het niet-geaccepteerde domein rapport](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>De tabel weergave Details voor het niet-geaccepteerde domein rapport

Als u in een rapportweergave op **Details tabel weergeven** klikt, wordt de volgende informatie weergegeven:

- **Einddatum**
- **Naam van inkomende connector**
- **Afzenderdomein**
- **Aantal berichten**
- **Voorbeeldberichten**: de bericht-id's van een voorbeeld van de betreffende berichten.

Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.

Als u het rapport voor een specifiek datumbereik naar een of meer geadresseerden wilt verzenden, klikt u op **Download aanvragen**.

Wanneer u een rij in de tabel selecteert, wordt een flyout met de volgende informatie weergegeven:

- **Einddatum**
- **Naam van inkomende connector**
- **Afzenderdomein**
- **Aantal berichten**
- **Voorbeeldberichten**: u kunt op **voorbeeldberichten weergeven** klikken om de resultaten van de [bericht tracering](message-trace-scc.md) te zien voor een voorbeeld van de betreffende berichten.

![Info-flyout na het selecteren van een rij in de weergave Details van een niet-geaccepteerd domein rapport](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Als u terug wilt gaan naar de weergave rapporten, klikt u op **rapport weergeven**.

## <a name="related-topics"></a>Verwante onderwerpen

Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).
