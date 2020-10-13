---
title: Geautomatiseerd onderzoek en antwoord in Microsoft Threat Protection
description: Een overzicht van geautomatiseerde functies voor onderzoek en antwoord, ook wel zelfherstel genoemd, in Microsoft Threat Protection
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
ms.openlocfilehash: 32bf5f1ada91ae67f72bd26c7fe68fe91897be7c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429357"
---
# <a name="automated-investigation-and-response-in-microsoft-threat-protection"></a>Geautomatiseerd onderzoek en antwoord in Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

Wanneer beveiligingswaarschuwingen worden geactiveerd, kunt u het beste uw beveiligingsteam raadplegen met deze waarschuwingen en de stappen ondernemen om uw organisatie te beveiligen. Het kan zeer lang voor het maken van waarschuwingen, met name wanneer nieuwe waarschuwingen worden gehouden wanneer een onderzoek wordt gehouden, zeer veel tijd in beslag nemen en onderzoeken. Beveiligingsactiviteiten teams kunnen overspoeld worden door het doorschijnende volume van de bedreigingen die ze moeten controleren en beschermen. Geautomatiseerd onderzoek-en antwoord vermogen met zelfherstel in Microsoft Threat Protection kan u helpen.

Bekijk de volgende video om te zien hoe u dit doet:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

In Microsoft Threat Protection werkt een geautomatiseerd onderzoek en antwoord met mogelijkheid voor automatisch herstel op uw apparaten, e-mail & inhoud en identiteiten. Microsoft Threat Protection biedt de volgende mogelijkheden: 
- [Automatisch onderzoek en herstel in Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Geautomatiseerd onderzoek en antwoord in Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Detectie van Azure Advanced Threat](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
In dit artikel wordt beschreven hoe automatisch onderzoek en reacties werken. Zie [geautomatiseerde onderzoek-en antwoord mogelijkheden in Microsoft Threat Protection configureren](mtp-configure-auto-investigation-response.md)voor het configureren van deze functies.

## <a name="your-virtual-analyst"></a>Uw virtuele analist

Voorbeeld van een virtuele analist in uw team van 1/laag 2-beveiligingsactiviteiten. De virtuele analist imiteert de ideale stappen die beveiligingsactiviteiten ondernemen om bedreigingen te onderzoeken en te herstellen. De virtuele assistent kan 24x7 werken, met onbeperkte capaciteit, en kan een aanzienlijke belasting van onderzoek en bedreiging doen. Een dergelijke virtuele assistent kon de tijd in beslag nemen om te reageren, het team van uw beveiligingsactiviteiten vrijmaken voor andere belangrijke strategische projecten. Als dit scenario klinkt als Science fictief, dan is het niet! Zo'n virtuele analist maakt deel uit van uw Microsoft Threat Protection Suite en de naam is *geautomatiseerd onderzoek en antwoord*.

Met geautomatiseerd onderzoek en antwoord kan uw bedrijfsvoering de capaciteit van uw organisatie ingrijpend verhogen om te zorgen voor beveiligingsmeldingen en incidenten. Met automatisch onderzoek en antwoord kunt u de kosten van transacties met onderzoek-en herstel activiteiten reduceren en optimaal gebruikmaken van uw Threat Protection-Suite. met geautomatiseerd onderzoek en antwoord zorgt u ervoor dat uw beveiligingsactiviteiten team:

1. Bepalen of een Threat een actie vereist;
2. Het uitvoeren (of aanbevelen) van alle benodigde herstelacties;
3. Bepalen welke aanvullende onderzoeken moeten worden gedaan; en
4. Herhaal het proces zo nodig voor andere meldingen.

## <a name="the-automated-investigation-process"></a>Het proces voor automatisch onderzoek

**Waarschuwing**  >  **incident**  >  **automatisch onderzoek**  >  **verdict**  >  **herstelactie**

Een waarschuwing met een trigger maakt een incident, dat een geautomatiseerd onderzoek kan starten. Dat onderzoek kan resulteren in een of meer herstelacties. In Microsoft Threat Protection vertoont elk automatisch onderzoek alle signalen in azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) en Office 365 Advanced Threat Protection (Office 365 ATP), zoals in de volgende tabel wordt samengevat: 

|Onderzoeksinstellingen |Service voor Threat Protection  |
|---------|---------|
|Apparaten (ook wel eindpunten genoemd)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-mail inhoud (bestanden en berichten in postvakken)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Bij elk onderzoek wordt Verdicts (*kwaadaardige*, *verdachte*of *geen bedreigingen gevonden*) voor elk onderzocht onderzoek. Afhankelijk van het type bedreiging en het resultaat Verdict, worden herstelacties automatisch of na goedkeuring uitgevoerd door het team van uw organisatie. Acties in behandeling en voltooid worden weergegeven in het [Actiecentrum](mtp-action-center.md).

Wanneer een onderzoek wordt uitgevoerd, worden eventuele andere bijbehorende waarschuwingen toegevoegd aan het onderzoek totdat het onderzoek wordt voltooid. Als een incriminated-entiteit elders wordt weergegeven, wordt het bereik van de geautomatiseerd onderzoek uitgebreid met die entiteit, en moet een algemeen beveiligings Playbook worden uitgevoerd. 

> [!NOTE]
> Niet elke melding veroorzaakt een geautomatiseerd onderzoek en niet alle onderzoekresultaten met geautomatiseerde herstelacties; Dit is alles, afhankelijk van de manier waarop automatisch onderzoek en beantwoorden zijn geconfigureerd voor uw organisatie. Zie [geautomatiseerde onderzoek-en antwoord mogelijkheden in Microsoft Threat Protection configureren](mtp-configure-auto-investigation-response.md).


## <a name="next-steps"></a>Volgende stappen

- [Zie de vereisten voor een geautomatiseerd onderzoek en een geautomatiseerd antwoord in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection)
- [Automatisch onderzoek en antwoord configureren voor uw organisatie](mtp-configure-auto-investigation-response.md)
- [Meer informatie over het Actiecentrum](mtp-action-center.md)
