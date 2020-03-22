---
title: Backscatter en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Backscatter is geautomatiseerde bounceberichten die naar vervalste e-mailadressen worden verzonden. De Backscatterer DNSBL identificeert servers die backscatter-berichten verzenden (waaronder veel legitieme e-mailbronnen). Aangezien het geen spammerlijst is, proberen wij niet om van De DNSBL van Backscatterer te verwijderen.
ms.openlocfilehash: 22eeec29722cf1742e096234aad95b9f6ee407e2
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895403"
---
# <a name="backscatter-and-eop"></a>Backscatter en EOP

*Backscatter* is niet-levering rapporten (ook wel bekend als NDR's of bounce berichten) die u ontvangt voor berichten die u niet hebt verzonden. Spammers smeden (spoof) de Van: adres van hun berichten, en ze gebruiken vaak echte e-mailadressen om geloofwaardigheid te verlenen aan hun berichten. Dus, wanneer spammers onvermijdelijk berichten sturen naar niet-bestaande ontvangers (spam is een high-volume operatie), de bestemming e-mailserver is in wezen misleid in het retourneren van de niet-leverbare bericht in een NDR naar de vervalste afzender in de Van: adres.

Exchange Online Protection (EOP) stelt alles in het werk om berichten van dubieuze bronnen te identificeren en in stilte te droppen zonder een NDR te genereren. Maar, op basis van het enorme volume e-mail stroomt door de dienst, is er altijd de mogelijkheid dat EOP onbedoeld backscatter zal sturen.

Backscatterer.org een bloklijst (ook wel DNS-bloklijst of DNSBL) bijhoudt van e-mailservers die verantwoordelijk waren voor het verzenden van backscatter, en EOP-servers kunnen in deze lijst worden weergegeven. Maar, we proberen niet om onszelf te verwijderen uit de Backscatterer.org blok lijst, want het is niet een lijst van spammers (door hun eigen toelating).

> [!TIP]
> De Backscatter.org<http://www.backscatterer.org/?target=usage>website ( ) raadt het gebruik van hun service om inkomende e-mail te controleren in de veilige modus in plaats van Reject-modus (grote e-maildiensten bijna altijd een aantal backscatter).
