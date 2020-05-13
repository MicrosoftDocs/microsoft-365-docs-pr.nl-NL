---
title: Backscatter in EOP
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
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over Backscatter en Microsoft Exchange Online Protection (EOP)
ms.openlocfilehash: e30fa27ac359ad28e042b2d4bd446d34a2e4f1e9
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209629"
---
# <a name="backscatter-in-eop"></a>Backscatter in EOP

*Backscatter* is niet-levering rapporten (ook wel bekend als NDR's of bounce berichten) die u ontvangt voor berichten die u niet hebt verzonden. Spammers smeden (spoof) de Van: adres van hun berichten, en ze gebruiken vaak echte e-mailadressen om geloofwaardigheid te verlenen aan hun berichten. Dus, wanneer spammers onvermijdelijk berichten sturen naar niet-bestaande ontvangers (spam is een high-volume operatie), de bestemming e-mailserver is in wezen misleid in het retourneren van de niet-leverbare bericht in een NDR naar de vervalste afzender in de Van: adres.

In Microsoft 365-organisaties met postvakken in Exchange Online- of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, doet EOP er alles aan om berichten van dubieuze bronnen te identificeren en in stilte te droppen zonder een NDR te genereren. Maar, op basis van het enorme volume e-mail stroomt door de dienst, is er altijd de mogelijkheid dat EOP onbedoeld backscatter zal sturen.

Backscatterer.org een bloklijst (ook wel DNS-bloklijst of DNSBL) bijhoudt van e-mailservers die verantwoordelijk waren voor het verzenden van backscatter, en EOP-servers kunnen in deze lijst worden weergegeven. Maar, we proberen niet om onszelf te verwijderen uit de Backscatterer.org blok lijst, want het is niet een lijst van spammers (door hun eigen toelating).

> [!TIP]
> De Backscatter.org website ( <http://www.backscatterer.org/?target=usage> ) raadt het gebruik van hun service om inkomende e-mail te controleren in de veilige modus in plaats van Reject-modus (grote e-maildiensten bijna altijd een aantal backscatter).
