---
title: Herstelacties na geautomatiseerde onderzoeken in Microsoft Threat Protection
description: Een overzicht krijgen van herstelacties die volgen op geautomatiseerde onderzoeken in Microsoft Threat Protection
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel
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
ms.openlocfilehash: ca0c557de24320692d903a1136fc434d635f0507
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955589"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Herstelacties na geautomatiseerde onderzoeken in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging


## <a name="remediation-actions"></a>Herstelacties

Tijdens en na een geautomatiseerd onderzoek in Microsoft Threat Protection worden herstelacties geïdentificeerd voor schadelijke of verdachte items. Sommige soorten herstelacties worden uitgevoerd op apparaten, ook wel eindpunten genoemd. Andere herstelacties worden uitgevoerd op e-mailinhoud. Geautomatiseerde onderzoeken worden voltooid nadat herstelacties zijn uitgevoerd, goedgekeurd of afgewezen.

In de volgende tabel worden herstelacties samengevat die momenteel worden ondersteund in Microsoft-bedreigingsbeveiliging: 

|Apparaatherstelacties (eindpunt)  |Acties voor e-mailherstel  |
|---------|---------|
|Quarantainebestand<br/>Registersleutel verwijderen<br/>Kill proces <br/>Service stoppen <br/>Stuurprogramma uitschakelen <br/>Geplande taak verwijderen      |E-mailberichten of clusters verwijderen van soft<br/>URL blokkeren (kliktijd)<br/>Extern doorsturen van e-mail uitschakelen          |

Herstelacties, ongeacht of ze in behandeling zijn of al voltooid zijn, kunnen worden weergegeven in het [Onderhoudscentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-follow-automated-investigations"></a>Herstelacties volgen geautomatiseerde onderzoeken

Wanneer een geautomatiseerd onderzoek is voltooid, wordt een oordeel bereikt voor elk bewijsstuk betrokken, en saneringacties worden geïdentificeerd. In sommige gevallen worden herstelacties automatisch uitgevoerd; in andere gevallen wachten saneringsacties op goedkeuring. De volgende tabel bevat mogelijke uitspraken en uitkomsten:

|Oordeel    |Gebied    |Resultaten|
|------|------|------|
|Kwaadaardige    |Apparaten (eindpunten)    |Herstelacties worden automatisch uitgevoerd|
|Kwaadaardige    |E-mailinhoud (URL's of bijlagen) | Aanbevolen herstelacties zijn in afwachting van goedkeuring|
|Verdachte    |Apparaten of e-mailinhoud |Aanbevolen herstelacties zijn in afwachting van goedkeuring|
|Geen bedreigingen gevonden    |Apparaten of e-mailinhoud    |Er zijn geen herstelacties nodig|

[Een actie in behandeling controleren in het actiecentrum](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> Als u denkt dat er iets is gemist of verkeerd is gedetecteerd door geautomatiseerde onderzoeks- en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten! [Valse positieven/negatieven melden](mtp-autoir-report-false-positives-negatives.md).

## <a name="next-steps"></a>Volgende stappen

- [Acties goedkeuren of afwijzen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [Meer informatie over het actiecentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
