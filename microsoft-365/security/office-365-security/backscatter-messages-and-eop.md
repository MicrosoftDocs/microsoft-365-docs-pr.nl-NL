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
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286967"
---
# <a name="backscatter-in-eop"></a>Backscatter in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*Backscatter* is rapporten over niet-bezorging (ook wel NR's of niet-bezorgdberichten genoemd) die u ontvangt voor berichten die u niet hebt verzonden. Spammers vervalsen het Van:-adres van hun berichten en gebruiken vaak echte e-mailadressen om hun berichten geloofwaardig te maken. Wanneer spammers dus onvermijdelijk berichten verzenden naar niet-bestaande geadresseerden (spam is een bewerking met hoog volume), wordt de doel-e-mailserver in feite gedredigd om het onbeslieerde bericht in een NDR te retourneren aan de vervalste afzender in het Van:-adres.

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken doet EOP er alles aan om berichten van bronnen te identificeren en op de rui uit te zetten zonder een NDR te genereren. Maar op basis van de grote hoeveelheid e-mail die door de service wordt verzonden, is het echter altijd mogelijk dat EOP backscatter onbedoeld verzendt.

Backscatterer.org een blokkeringslijst bijhoudt (ook wel een DNS-blokkeringslijst of DNSBL genoemd) van e-mailservers die verantwoordelijk waren voor het verzenden van backscatter en EOP-servers kunnen in deze lijst worden weergegeven. Maar we proberen niet te verwijderen uit de lijst met geblokkeerde Backscatterer.org omdat het geen lijst met spammers is (voor hun eigen toegang).

> [!TIP]
> De Backscatter.org website ( ) raadt aan de service te gebruiken voor het controleren van inkomende e-mail in de veilige modus in plaats van de modus Weigeren (grote e-mailservices verzenden vrijwel altijd <http://www.backscatterer.org/?target=usage> backscatter).
