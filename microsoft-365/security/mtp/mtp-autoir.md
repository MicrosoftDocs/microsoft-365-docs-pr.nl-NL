---
title: Automatisch onderzoek en antwoorden in Microsoft 365 Defender
description: Krijg een overzicht van geautomatiseerde onderzoeks- en antwoordmogelijkheden, ook wel zelf-moeten worden genoemd, in Microsoft 365 Defender
keywords: automated, investigation, alert, trigger, action, remediation, self-in
search.appverid: met150
ms.prod: m365-security
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930328"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Automatisch onderzoek en antwoorden in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

> Wilt u ervaring met Microsoft 365 Defender? U kunt [dit evalueren in een testomgeving](https://aka.ms/mtp-trial-lab) of uw [pilotproject in productie nemen.](https://aka.ms/m365d-pilotplaybook)
>

## <a name="how-automated-investigation-and-self-healing-works"></a>Hoe automatisch onderzoek en zelf-herstel werken

Wanneer beveiligingswaarschuwingen worden geactiveerd, is het aan uw team voor beveiligingsactiviteiten om naar deze waarschuwingen te kijken en stappen te ondernemen om uw organisatie te beschermen. Het geven van prioriteit aan waarschuwingen en het onderzoeken van waarschuwingen kan erg veel tijd in beslag nemen, vooral wanneer er steeds nieuwe waarschuwingen binnen komen terwijl er een onderzoek bezig is. Teams met beveiligingsbewerkingen kunnen overstelpt worden door het grote aantal bedreigingen die ze moeten controleren en beveiligen tegen. Automatische onderzoeks- en antwoordmogelijkheden, met self-moeten, in Microsoft 365 Defender kunnen helpen.

Bekijk de volgende video om te zien hoe uw werk werkt:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

In Microsoft 365 Defender werken geautomatiseerde onderzoeken en antwoorden met self-functionaliteit op uw apparaten, e-mailen & inhoud en identiteiten.
 
> [!TIP]
> In dit artikel wordt beschreven hoe automatisch onderzoek en antwoorden werken. Zie Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren [in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)om deze mogelijkheden te configureren.

## <a name="your-own-virtual-analyst"></a>Uw eigen virtuele analist

Stel dat u een virtuele analist hebt in uw beveiligingsteam voor Laag 1/Laag 2. De virtuele analist nabootst de ideale stappen die beveiligingsbewerkingen moeten uitvoeren om bedreigingen te onderzoeken en te herstellen. De virtuele assistent zou 24x7 kunnen werken, met onbeperkte capaciteit, en een aanzienlijke belasting van onderzoeken en bedreigingen herstellen. Een dergelijke virtuele assistent kan de tijd om te reageren aanzienlijk verminderen, waardoor het team voor beveiligingsactiviteiten vrij komt voor andere belangrijke strategische projecten. Als dit scenario klinkt als sciencefiction, is dat niet het geval. Een dergelijke virtuele analist maakt deel uit van uw Microsoft 365 Defender-suite en de naam is *geautomatiseerd onderzoek en reactie.*

Dankzij automatisch onderzoek en automatisch antwoord kan het team voor beveiligingsactiviteiten de capaciteit van uw organisatie om te gaan met beveiligingswaarschuwingen en -incidenten aanzienlijk verhogen. Met geautomatiseerd onderzoek en automatisch onderzoek kunt u de kosten van onderzoeken en herstelactiviteiten verminderen en het beste uit uw suite voor bedreigingsbeveiliging halen. Geautomatiseerde onderzoeken en antwoorden helpt uw team voor beveiligingsbewerkingen door:

1. Bepalen of actie moet worden ondernomen voor een bedreiging;
2. Eventuele benodigde herstelacties uitvoeren (of aanbevelen);
3. Bepalen welke aanvullende onderzoeken moeten worden uitgevoerd; en
4. Herhaal dit proces indien nodig voor andere waarschuwingen.

## <a name="the-automated-investigation-process"></a>Het proces van automatisch onderzoek

**Waarschuwing**  >  **incident**  >  **geautomatiseerd onderzoek**  >  **één**  >  **herstelactie**

Een geactiveerde waarschuwing maakt een incident, dat een geautomatiseerd onderzoek kan starten. Dit onderzoek kan leiden tot een of meer herstelacties. In Microsoft 365 Defender correleren elk geautomatiseerd onderzoek signalen tussen Microsoft Defender for Identity, Microsoft Defender voor Eindpunt en Defender voor Office 365, zoals samengevat in de volgende tabel: 

|Entiteiten |Bedreigingsbeveiligingsservices  |
|---------|---------|
|Apparaten (ook wel eindpunten genoemd)     |[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-mailinhoud (bestanden en berichten in postvakken)     |[Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Elk onderzoek genereert onderzoek (*Kwaadaardige,* *Verdachte* of Geen bedreigingen *gevonden)* voor elk stukje onderzoek dat wordt onderzocht. Afhankelijk van het type bedreiging en het resulterende resultaat, vinden herstelacties automatisch of na goedkeuring door het beveiligingsteam van uw organisatie plaats. Acties in behandeling en voltooid worden weergegeven in het [Actiecentrum.](mtp-action-center.md)

Wanneer een onderzoek wordt uitgevoerd, worden alle andere gerelateerde waarschuwingen die zich voordoen, toegevoegd aan het onderzoek totdat het is voltooid. Als een belaste entiteit ergens anders wordt gezien, wordt het bereik van het geautomatiseerde onderzoek uitgebreid met die entiteit en wordt er een algemene beveiligings playbook uitgevoerd. 

> [!NOTE]
> Niet elke waarschuwing activeert een geautomatiseerd onderzoek en niet elk onderzoek resulteert in automatische herstelacties. Dit is allemaal afhankelijk van hoe automatisch onderzoek en antwoorden voor uw organisatie zijn geconfigureerd. Zie [Mogelijkheden voor geautomatiseerd onderzoek en antwoorden configureren in Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)


## <a name="next-steps"></a>Volgende stappen

- [Bekijk de vereisten voor geautomatiseerd onderzoek en antwoorden in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Geautomatiseerd onderzoek en automatisch onderzoek voor uw organisatie configureren](mtp-configure-auto-investigation-response.md)
- [Meer informatie over het Actiecentrum](mtp-action-center.md)
