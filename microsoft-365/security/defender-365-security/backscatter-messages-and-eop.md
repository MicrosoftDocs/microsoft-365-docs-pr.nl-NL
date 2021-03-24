---
title: Backscatter in EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over Backscatter en Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058989"
---
# <a name="backscatter-in-eop"></a>Backscatter in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* is niet-bezorgingsrapporten (ook wel NDR's of niet-bezorgde berichten genoemd) die u ontvangt voor berichten die u niet hebt verzonden. Spammers vervalsen (spoof) het Van:-adres van hun berichten en ze gebruiken vaak echte e-mailadressen om hun berichten geloofwaardig te maken. Dus wanneer spammers onvermijdelijk berichten verzenden naar niet-bestaande geadresseerden (spam is een groot volumebewerking), wordt de doel-e-mailserver in feite misleid om het niet-beleverbare bericht in een NDR terug te sturen naar de vervalste afzender in het Van:-adres.

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, doet EOP er alles aan om berichten uit dubieuze bronnen te identificeren en in stilte neer te zetten zonder een NDR te genereren. Maar op basis van het grote volume dat via de service wordt verzonden, is er altijd de mogelijkheid dat EOP per ongeluk backscatter verzendt.

Backscatterer.org een blokkeringslijst (ook wel een DNS-bloklijst of DNSBL genoemd) van e-mailservers die verantwoordelijk waren voor het verzenden van backscatter, en EOP-servers worden mogelijk weergegeven in deze lijst. Maar we proberen ons niet uit de lijst met blokkeringen Backscatterer.org verwijderen omdat het geen lijst met spammers is (naar eigen zeggen).

> [!TIP]
> De Backscatter.org website () raadt aan de service te gebruiken om binnenkomende e-mail te controleren in de veilige modus in plaats van de modus Weigeren (grote e-mailservices sturen vrijwel altijd wat <http://www.backscatterer.org/?target=usage> backscatter).
