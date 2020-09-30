---
title: Waarden voor bulk klachten niveau
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie lezen over de BCL-waarden (bulk compliance niveau) die worden gebruikt in Exchange Online Protection (EOP).
ms.openlocfilehash: 53d0ae5fb23fb68ef970a07b2b5d8c4220775de7
ms.sourcegitcommit: 61ef32f802a1fb6d1e3a3aa005764ead32a7951e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2020
ms.locfileid: "48318212"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Bulk klachten niveau (BCL) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken wordt in EOP een BCL (bulk compliant niveau) toegewezen aan inkomende berichten van grote Mailers. De BCL wordt aan het bericht toegevoegd in een X-header en is vergelijkbaar met het [spam betrouwbaarheidsniveau (SCL)](spam-confidence-levels.md) dat wordt gebruikt om berichten als spam op te sporen. Een hogere BCL geeft aan dat een bulk bericht waarschijnlijk klachten genereert (en dat waarschijnlijk spam is). Microsoft gebruikt interne en externe bronnen voor het identificeren van bulk berichten en het bepalen van de juiste BCL.

Grote Mailers verschillen in hun verzend patronen, het maken van inhoud en de overname van geadresseerden. Goede bulk berichten sturen de gewenste berichten met relevante inhoud naar hun abonnees. Deze berichten genereren enkele klachten van geadresseerden. Andere grote Mailers verzenden ongevraagde berichten die sterk lijken op spam en Genereer veel klachten van geadresseerden. Berichten van een grootschalige e-mail band worden ook wel grote hoeveelheden e-mail of grijze e-mail genoemd.

 Met filters voor ongewenste e-mail worden berichten als **bulk e-mail** gemarkeerd op basis van de BCL-drempelwaarde (de standaardwaarde of een waarde die u opgeeft) en wordt de opgegeven actie op het bericht uitgevoerd (de standaardactie zorgt voor het verzenden van het bericht naar de map Ongewenste e-mail van de geadresseerde). Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) en [Wat is het verschil tussen ongewenste e-mail en bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) voor meer informatie.

In de volgende tabel vindt u een beschrijving van de BCL-drempelwaarden.

****

|BCL|Beschrijving|
|:---:|---|
|0|Het bericht is niet afkomstig van een bulk verzender.|
|1, 2, 3|Het bericht is afkomstig uit een bulk verzender waarmee een aantal klachten wordt gegenereerd.|
|4, 5, 6, 7<sup>\*</sup>|Het bericht is afkomstig uit een bulk verzender waarmee een gemengde soort klachten wordt gegenereerd.|
|8, 9|Het bericht is afkomstig van een bulk verzender waarmee een groot aantal klachten wordt gegenereerd.|
|

<sup>\*</sup> Dit is de standaard drempelwaarde die wordt gebruikt in antispambeleid.
