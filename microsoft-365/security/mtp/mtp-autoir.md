---
title: Automatisch onderzoek en antwoord in Microsoft 365 Defender
description: Een overzicht van geautomatiseerde functies voor onderzoek en antwoord, ook wel zelfherstel genoemd, in Microsoft 365 Defender
keywords: automatisch, onderzoek, waarschuwing, trigger, actie, herstel, zelfherstel
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2b8872288291adc0b9fc5e1c1541f885711df230
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356701"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Automatisch onderzoek en antwoord in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

> Wilt u Microsoft 365 Defender ervaren? U kunt [deze beoordelen in een testomgeving](https://aka.ms/mtp-trial-lab) of een [proefproject uitvoeren op de productie](https://aka.ms/m365d-pilotplaybook).
>

Wanneer beveiligingswaarschuwingen worden geactiveerd, kunt u het beste uw beveiligingsteam raadplegen met deze waarschuwingen en de stappen ondernemen om uw organisatie te beveiligen. Het kan zeer lang voor het maken van waarschuwingen, met name wanneer nieuwe waarschuwingen worden gehouden wanneer een onderzoek wordt gehouden, zeer veel tijd in beslag nemen en onderzoeken. Beveiligingsactiviteiten teams kunnen overspoeld worden door het doorschijnende volume van de bedreigingen die ze moeten controleren en beschermen. Geautomatiseerd onderzoek en antwoord functies met zelfherstel in Microsoft 365 Defender kan u helpen.

Bekijk de volgende video om te zien hoe u dit doet:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

In Microsoft 365 Defender werken geautomatiseerde onderzoek en antwoord met mogelijkheden voor automatisch herstel op uw apparaten, e-mail & inhoud en identiteiten. Microsoft 365 Defender biedt de volgende mogelijkheden: 
- [Automatisch onderzoek en herstel in Microsoft Defender voor eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Automatisch onderzoek en antwoord in Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Detectie van Azure Advanced Threat](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
In dit artikel wordt beschreven hoe automatisch onderzoek en reacties werken. Zie [geautomatiseerde onderzoek-en antwoord mogelijkheden in Microsoft 365 Defender configureren](mtp-configure-auto-investigation-response.md)voor het configureren van deze functies.

## <a name="your-virtual-analyst"></a>Uw virtuele analist

Voorbeeld van een virtuele analist in uw team van 1/laag 2-beveiligingsactiviteiten. De virtuele analist imiteert de ideale stappen die beveiligingsactiviteiten ondernemen om bedreigingen te onderzoeken en te herstellen. De virtuele assistent kan 24x7 werken, met onbeperkte capaciteit, en kan een aanzienlijke belasting van onderzoek en bedreiging doen. Een dergelijke virtuele assistent kon de tijd in beslag nemen om te reageren, het team van uw beveiligingsactiviteiten vrijmaken voor andere belangrijke strategische projecten. Als dit scenario klinkt als Science fictief, dan is het niet! Zo'n virtuele analist maakt deel uit van uw Microsoft 365-Suite en de naam is *geautomatiseerd onderzoek en antwoord*.

Met geautomatiseerd onderzoek en antwoord kan uw bedrijfsvoering de capaciteit van uw organisatie ingrijpend verhogen om te zorgen voor beveiligingsmeldingen en incidenten. Met automatisch onderzoek en antwoord kunt u de kosten van transacties met onderzoek-en herstel activiteiten reduceren en optimaal gebruikmaken van uw Threat Protection-Suite. met geautomatiseerd onderzoek en antwoord zorgt u ervoor dat uw beveiligingsactiviteiten team:

1. Bepalen of een Threat een actie vereist;
2. Het uitvoeren (of aanbevelen) van alle benodigde herstelacties;
3. Bepalen welke aanvullende onderzoeken moeten worden gedaan; en
4. Herhaal het proces zo nodig voor andere meldingen.

## <a name="the-automated-investigation-process"></a>Het proces voor automatisch onderzoek

**Waarschuwing**  >  **incident**  >  **automatisch onderzoek**  >  **verdict**  >  **herstelactie**

Een waarschuwing met een trigger maakt een incident, dat een geautomatiseerd onderzoek kan starten. Dat onderzoek kan resulteren in een of meer herstelacties. In Microsoft 365 Defender verbindt elk automatisch onderzoek alle signalen in Microsoft Defender voor de identiteit, Microsoft Defender voor eindpunt en Defender voor Office 365, zoals in de volgende tabel wordt samengevat: 

|Onderzoeksinstellingen |Service voor Threat Protection  |
|---------|---------|
|Apparaten (ook wel eindpunten genoemd)     |[Microsoft Defender voor Eindpunt ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-mail inhoud (bestanden en berichten in postvakken)     |[Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Bij elk onderzoek wordt Verdicts (*kwaadaardige*, *verdachte* of *geen bedreigingen gevonden*) voor elk onderzocht onderzoek. Afhankelijk van het type bedreiging en het resultaat Verdict, worden herstelacties automatisch of na goedkeuring uitgevoerd door het team van uw organisatie. Acties in behandeling en voltooid worden weergegeven in het [Actiecentrum](mtp-action-center.md).

Wanneer een onderzoek wordt uitgevoerd, worden eventuele andere bijbehorende waarschuwingen toegevoegd aan het onderzoek totdat het onderzoek wordt voltooid. Als een incriminated-entiteit elders wordt weergegeven, wordt het bereik van de geautomatiseerd onderzoek uitgebreid met die entiteit, en moet een algemeen beveiligings Playbook worden uitgevoerd. 

> [!NOTE]
> Niet elke melding veroorzaakt een geautomatiseerd onderzoek en niet alle onderzoekresultaten met geautomatiseerde herstelacties; Dit is alles, afhankelijk van de manier waarop automatisch onderzoek en beantwoorden zijn geconfigureerd voor uw organisatie. Zie [geautomatiseerde onderzoek-en antwoord mogelijkheden in Microsoft 365 Defender configureren](mtp-configure-auto-investigation-response.md).


## <a name="next-steps"></a>Volgende stappen

- [Zie de vereisten voor automatisch onderzoek en antwoord in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Automatisch onderzoek en antwoord configureren voor uw organisatie](mtp-configure-auto-investigation-response.md)
- [Meer informatie over het Actiecentrum](mtp-action-center.md)
