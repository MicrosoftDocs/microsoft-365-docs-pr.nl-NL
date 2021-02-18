---
title: Waarden voor bulksgelaagden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over BCL-waarden (Bulk Compliance Level) die worden gebruikt in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c68314cf992d39a105293955b6fade7b1a2bec56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289891"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Bulksgewijs klachtniveau (BCL) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken wijst EOP een bulksgewijs compatibel niveau (BCL) toe aan inkomende berichten van bulkmailers. De BCL wordt toegevoegd aan het bericht in een X-koptekst en is vergelijkbaar met het spamniveau [dat](spam-confidence-levels.md) wordt gebruikt om berichten als spam te identificeren. Een hogere BCL geeft aan dat de kans groter is dat een bulkbericht klachten genereert (en daardoor waarschijnlijk spam is). Microsoft gebruikt zowel interne als externe bronnen om bulkmail te identificeren en de juiste BCL te bepalen.

Bulkmailers variëren in hun verzendingspatronen, het maken van inhoud en het verkrijgen van geadresseerden. Goede bulkmailers verzenden gewenste berichten met relevante inhoud naar hun abonnees. Deze berichten genereren weinig klachten van geadresseerden. Andere bulkmailers verzenden ongevraagde berichten die sterk lijken op spam en genereren veel klachten van geadresseerden. Berichten van bulkmail worden ook wel bulkmail of grijze e-mail genoemd.

 Met spamfilters  worden berichten gemarkeerd als bulk-e-mail op basis van de drempelwaarde voor BCL (de standaardwaarde of een waarde die u opgeeft) en wordt de opgegeven actie ondernomen op het bericht (de standaardactie is het bericht bezorgen bij de map Ongewenste e-mail van de geadresseerde). Zie Antispambeleid configureren en wat is het verschil tussen ongewenste [e-mail](configure-your-spam-filter-policies.md) en [bulk-e-mail voor meer informatie.](what-s-the-difference-between-junk-email-and-bulk-email.md)

De drempelwaarden voor BCL worden in de volgende tabel beschreven.

****

|BCL|Beschrijving|
|:---:|---|
|0|Het bericht is niet afkomstig van een bulksge keer.|
|1, 2, 3|Het bericht is afkomstig van een afzender die bulksgewijs maar weinig klachten genereert.|
|4, 5, 6, 7<sup>\*</sup>|Het bericht is afkomstig van een afzender die bulksgewijs een gemengd aantal klachten genereert.|
|8, 9|Het bericht is afkomstig van een afzender die bulksgewijs veel klachten genereert.|
|

<sup>\*</sup> Dit is de standaard drempelwaarde die wordt gebruikt in antispambeleid.
