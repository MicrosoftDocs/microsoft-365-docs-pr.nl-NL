---
title: Saneringsacties na geautomatiseerde onderzoeken in Microsoft Threat Protection
description: Een overzicht krijgen van herstelacties die volgen op geautomatiseerde onderzoeken in Microsoft Threat Protection
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
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502935"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Saneringsacties na geautomatiseerde onderzoeken in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft Threat Protection


## <a name="remediation-actions"></a>Herstelacties

Tijdens en na een geautomatiseerd onderzoek in Microsoft Threat Protection worden herstelacties geïdentificeerd voor schadelijke of verdachte items. Sommige soorten herstelacties worden uitgevoerd op apparaten, ook wel eindpunten genoemd. Andere herstelacties worden uitgevoerd op e-mailinhoud. Geautomatiseerde onderzoeken die worden voltooid nadat herstelmaatregelen zijn uitgevoerd, goedgekeurd of afgewezen.

In de volgende tabel worden herstelacties samengevat die momenteel worden ondersteund in Microsoft Threat Protection: 

|Herstelacties voor apparaten (eindpunt)  |Acties voor het herstellen van e-mail  |
|---------|---------|
|- Verzamel onderzoekspakket <br/>- Isoleren apparaat (deze actie kan ongedaan worden gemaakt)<br/>- Buitenboordmachine <br/>- Release code uitvoering <br/>- Loslaten uit quarantaine <br/>- Voorbeeld aanvragen <br/>- Code-uitvoering beperken (deze actie kan ongedaan worden gemaakt) <br/>- Antivirusscan uitvoeren <br/>- Stoppen en in quarantaine      |- URL blokkeren (tijd-van-klik)<br/>- Soft verwijderen van e-mailberichten of clusters<br/>- Quarantaine e-mail<br/>- Een e-mailbijlage in quarantaine plaatsen<br/>- Externe e-maildoorschakeling uitschakelen          |

Herstelacties, of ze nu goedgekeurd zijn of al zijn voltooid, kunnen worden weergegeven in het [Onderhoudscentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-follow-automated-investigations"></a>Saneringsacties volgen op geautomatiseerde onderzoeken

Wanneer een geautomatiseerd onderzoek is voltooid, wordt een oordeel geveld voor elk betrokken bewijsstuk en worden saneringsacties geïdentificeerd. In sommige gevallen worden herstelmaatregelen automatisch ondernomen; in andere gevallen wachten saneringsacties op goedkeuring. In de volgende tabel worden mogelijke uitspraken en uitkomsten weergegeven:

|Oordeel    |Gebied    |Resultaten|
|------|------|------|
|Kwaadaardige    |Apparaten (eindpunten)    |Herstelacties worden automatisch uitgevoerd|
|Kwaadaardige    |E-mailinhoud (URL's of bijlagen) | Aanbevolen herstelacties zijn in afwachting van goedkeuring|
|Verdachte    |Apparaten of e-mailinhoud |Aanbevolen herstelacties zijn in afwachting van goedkeuring|
|Geen bedreigingen gevonden    |Apparaten of e-mailinhoud    |Er zijn geen saneringsacties nodig|

[Een lopende actie in het Actiecentrum bekijken](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> Als u denkt dat er iets is gemist of ten onrechte is gedetecteerd door geautomatiseerde onderzoeks- en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten! [Valse positieven/negatieven melden](mtp-autoir-report-false-positives-negatives.md).

## <a name="next-steps"></a>Volgende stappen

- [Acties goedkeuren of afwijzen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [Meer informatie over het Actiecentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
