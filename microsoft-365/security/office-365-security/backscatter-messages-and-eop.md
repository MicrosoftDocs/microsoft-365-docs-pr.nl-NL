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
ms.openlocfilehash: 3cdc556a8cc193466d150fc82298796779841cca
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165953"
---
# <a name="backscatter-in-eop"></a>Backscatter in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

*Backscatter* is rapporten over niet-bezorging (ook wel NR's of niet-bezorgdberichten genoemd) die u ontvangt voor berichten die u niet hebt verzonden. Spammers vervalsen het Van:-adres van hun berichten en gebruiken vaak echte e-mailadressen om hun berichten geloofwaardig te maken. Wanneer spammers dus onvermijdelijk berichten verzenden naar niet-bestaande geadresseerden (spam is een bewerking met hoog volume), wordt de doel-e-mailserver in feite gedredigd om het onbeslieerde bericht in een NDR te retourneren aan de vervalste afzender in het Van:-adres.

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken doet EOP er alles aan om berichten van bronnen te identificeren en op de rui uit te zetten zonder een NDR te genereren. Maar op basis van de grote hoeveelheid e-mail die door de service wordt verzonden, is het echter altijd mogelijk dat EOP backscatter onbedoeld verzendt.

Backscatterer.org een blokkeringslijst bijhoudt (ook wel een DNS-blokkeringslijst of DNSBL genoemd) van e-mailservers die verantwoordelijk waren voor het verzenden van backscatter en EOP-servers kunnen in deze lijst worden weergegeven. Maar we proberen niet te verwijderen uit de lijst met geblokkeerde Backscatterer.org omdat het geen lijst met spammers is (voor hun eigen toegang).

> [!TIP]
> De Backscatter.org () raadt aan de service te gebruiken voor het controleren van inkomende e-mail in de veilige modus in plaats van de modus Weigeren (in grote e-mailservices wordt vrijwel altijd <http://www.backscatterer.org/?target=usage> backscatter verzonden).
