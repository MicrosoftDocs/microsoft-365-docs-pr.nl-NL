---
title: Herstelacties naar aanleiding van geautomatiseerde onderzoeken in Microsoft Threat Protection
description: Krijg een overzicht van herstelacties die geautomatiseerde onderzoeken volgen in Microsoft Threat Protection
keywords: geautomatiseerd, onderzoek, alert, trigger, actie, sanering
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/25/2020
ms.locfileid: "42811370"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Herstelacties naar aanleiding van geautomatiseerde onderzoeken in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging


## <a name="remediation-actions"></a>Saneringsacties

Tijdens en na een geautomatiseerd onderzoek in Microsoft Threat Protection worden herstelacties geïdentificeerd voor schadelijke of verdachte items. Sommige soorten van sanering acties worden genomen op apparaten, ook wel aangeduid als eindpunten. Andere herstelacties worden uitgevoerd op e-mailinhoud. Geautomatiseerde onderzoeken worden voltooid nadat herstelacties zijn genomen, goedgekeurd of afgewezen.

In de volgende tabel worden herstelacties samengevat die momenteel worden ondersteund in Microsoft Threat Protection: 

|Herstelacties voor apparaat (eindpunt)  |Acties voor e-mailherstel  |
|---------|---------|
|Quarantainebestand<br/>Registersleutel verwijderen<br/>Dodenproces <br/>Service stoppen <br/>Stuurprogramma uitschakelen <br/>Geplande taak verwijderen      |E-mailberichten of clusters voor soft delete<br/>URL blokkeren (tijd van klikken)<br/>Externe e-mail doorsturen uitschakelen          |

Herstelacties, of ze nu in behandeling zijn met goedkeuring of al voltooid zijn, kunnen worden weergegeven in het [Actiecentrum.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)

## <a name="verdicts-and-outcomes-following-automated-investigations"></a>Vonnissen en resultaten na geautomatiseerde onderzoeken

Wanneer een geautomatiseerd onderzoek is voltooid, wordt een oordeel bereikt voor elk bewijsstuk dat betrokken is, en worden saneringsacties geïdentificeerd. In sommige gevallen worden saneringsacties automatisch uitgevoerd; in andere gevallen wachten saneringsacties op goedkeuring. In de volgende tabel worden mogelijke vonnissen en resultaten opgesomd:

|Oordeel    |Gebied   |Resultaten|
|------|------|------|
|Kwaadaardige  |Apparaten (eindpunten)    |Herstelacties worden automatisch uitgevoerd|
|Kwaadaardige  |E-mailinhoud (URL's of bijlagen) | Aanbevolen herstelacties zijn in afwachting van goedkeuring|
|Verdachte |Apparaten of e-mailinhoud |Aanbevolen herstelacties zijn in afwachting van goedkeuring|
|Schoon  |Apparaten of e-mailinhoud   |Er zijn geen saneringsacties nodig|

[Een lopende actie in het actiecentrum bekijken](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> Als u denkt dat er iets is gemist of ten onrechte is gedetecteerd door geautomatiseerd onderzoek en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten! [Valse positieven/negatieven melden](mtp-autoir-report-false-positives-negatives.md).

## <a name="next-steps"></a>Volgende stappen

- [Acties goedkeuren of afwijzen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [Meer informatie over het actiecentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
