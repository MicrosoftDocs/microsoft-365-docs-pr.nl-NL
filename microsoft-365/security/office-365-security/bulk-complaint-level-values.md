---
title: Waarden voor bulksgewijs klachtenniveau
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
description: Beheerders kunnen meer informatie krijgen over BCL-waarden (Bulk Complaint Level) die worden gebruikt in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08924a7db0a5c4588ed70bc41e4caf46afb35b53
ms.sourcegitcommit: a46532bb422ee51331f478ff50cc5444586bf6a9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2021
ms.locfileid: "51650252"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Bulkklachtsniveau (BCL) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, wijst EOP een bulkklachtsniveau (BCL) toe aan binnenkomende berichten van bulkmailers. De BCL wordt toegevoegd aan het bericht in een X-header en is vergelijkbaar met het betrouwbaarheidsniveau voor [spam (SCL)](spam-confidence-levels.md) dat wordt gebruikt om berichten te identificeren als spam. Een hogere BCL geeft aan dat een bulkbericht meer kans heeft op het genereren van klachten (en dus waarschijnlijk spam is). Microsoft gebruikt interne en externe bronnen om bulkmail te identificeren en de juiste BCL te bepalen.

Bulkmailers variëren in hun verzendingspatronen, het maken van inhoud en het verkrijgen van geadresseerden. Goede bulkmailers verzenden gewenste berichten met relevante inhoud naar hun abonnees. Deze berichten genereren weinig klachten van geadresseerden. Andere bulkmailers verzenden ongevraagde berichten die sterk lijken op spam en veel klachten van geadresseerden genereren. Berichten van een bulkmailer worden bulkmail of grijze e-mail genoemd.

 Met spamfilters  worden berichten gemarkeerd als Bulk-e-mail op basis van de BCL-drempelwaarde (de standaardwaarde of een waarde die u opgeeft) en voert u de opgegeven actie uit voor het bericht (de standaardactie is om het bericht naar de map Ongewenste e-mail van de geadresseerde te sturen). Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) en Wat is het verschil tussen ongewenste e-mail en [bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) voor meer informatie.

De BCL-drempelwaarden worden beschreven in de volgende tabel.

****

|BCL|Omschrijving|
|:---:|---|
|0|Het bericht is niet afkomstig van een bulksgewijs afzender.|
|1, 2, 3|Het bericht is afkomstig van een bulksgewijs afzender die weinig klachten genereert.|
|4, 5, 6, 7<sup>\*</sup>|Het bericht is afkomstig van een bulksgewijs afzender die een gemengd aantal klachten genereert.|
|8, 9|Het bericht is afkomstig van een bulksgewijs afzender die een groot aantal klachten genereert.|
|

<sup>\*</sup> Dit is de standaard drempelwaarde die wordt gebruikt in antispambeleid.
