---
title: Backscatter messages and EOP(Backscatter-berichten en EOP)
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
description: Backscatter-berichten zijn automatische bounceberichten die naar vervalste e-mailadressen worden verzonden. De Backscatterer DNSBL identificeert servers die backscatter-berichten verzenden (waaronder veel legitieme e-mailbronnen). Aangezien het geen spammerlijst is, proberen wij niet om van De DNSBL van Backscatterer te verwijderen.
ms.openlocfilehash: 20ed828680dd20e82819730e6dcd509b896d8616
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/27/2020
ms.locfileid: "42810934"
---
# <a name="backscatter-messages-and-eop"></a>Backscatter messages and EOP(Backscatter-berichten en EOP)

*Backscatter-berichten* zijn niet-leveringsrapporten (ook wel NDR's of bounceberichten genoemd) die u ontvangt voor berichten die u niet hebt verzonden. Spammers smeden (spoof) de Van: adres van hun berichten, en ze gebruiken vaak echte e-mailadressen om geloofwaardigheid te verlenen aan hun berichten. Dus, wanneer een spammer onvermijdelijk berichten te sturen naar niet-bestaande ontvangers (spam is een high-volume operatie), zal de bestemming e-mailserver waarschijnlijk terug de onbestelbare bericht in een NDR, die wordt verzonden naar de vervalste afzender in de Van: adres.

Exchange Online Protection (EOP) stelt alles in het werk om berichten van dubieuze bronnen te identificeren en in stilte te droppen zonder een NDR te genereren. Maar, op basis van het enorme volume e-mail stroomt door de dienst, is er altijd de mogelijkheid dat EOP onbedoeld backscatter berichten zal sturen.

Backscatterer.org een bloklijst (ook wel DNS-bloklijst of DNSBL) bijhoudt van e-mailservers die verantwoordelijk waren voor het verzenden van backscatter-berichten, en EOP-servers kunnen in deze lijst worden weergegeven. Maar, we proberen niet om onszelf te verwijderen uit de Backscatterer.org blok lijst, want het is niet een lijst van spammers (door hun eigen toelating).

> [!TIP]
> De Backscatter.org<http://www.backscatterer.org/?target=usage>website ( ) raadt het gebruik van hun service om inkomende e-mail te controleren in de veilige modus in plaats van Reject-modus (grote e-maildiensten bijna altijd een aantal backscatter berichten).
