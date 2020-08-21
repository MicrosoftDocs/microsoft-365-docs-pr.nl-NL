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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over Backscatter en Microsoft Exchange Online Protection (EOP)
ms.openlocfilehash: f1705fd7fc30c9a8cde5f6acfaf145861de3af08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827783"
---
# <a name="backscatter-in-eop"></a>Backscatter in EOP

*Backscatter* is rapporten over niet-uitgevoerde bezorging (ook wel ndr's genoemd of berichten verzenden) die u ontvangt voor berichten die u niet heb verzonden. Spammers smeden (spoof) The from: adres van hun berichten, en ze gebruiken vaak realtime e-mailadressen om geloofwaardigheid te lenen aan hun berichten. Wanneer spammers via een zeer grote transactie geen berichten naar niet-bestaande geadresseerden sturen (spam is een high-volume-actie), wordt de doel-e-mailserver in feite omgezet in een NDR naar de vervalste afzender in het adres van:.

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, zorgt EOP ervoor dat elke inspanning berichten van dubious-bronnen identificeert en ongestilled verwijdert zonder een NDR te genereren. Op basis van het e-mailadres van doorschijnende, kunt u altijd Backscatter de mogelijkheid bieden om te verzenden.

Backscatterer.org onderhoudt een blokkeringslijst (ook wel bekend als DNS-bloklijst of DNSBL) van e-mailservers die verantwoordelijk zijn voor het verzenden van Backscatter en EOP servers mogelijk in deze lijst worden weergegeven. Maar we proberen onszelf niet te verwijderen uit de lijst met Backscatterer.org-blokken omdat dit geen lijst is met spammers (op basis van eigen invoer).

> [!TIP]
> De Backscatter.org-website ( <http://www.backscatterer.org/?target=usage> ) adviseert hun service te gebruiken voor het controleren van inkomende e-mail in de veilige modus in plaats van de reject-modus (grootschalige e-mailservices verzenden bijna altijd een aantal Backscatter).
