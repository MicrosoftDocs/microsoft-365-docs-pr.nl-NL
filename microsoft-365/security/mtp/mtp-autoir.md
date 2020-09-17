---
title: Geautomatiseerd onderzoek en antwoord mogelijkheden in Microsoft Threat Protection
description: Een overzicht van geautomatiseerde functies voor onderzoek en antwoorden in Microsoft Threat Protection
keywords: automatisch, onderzoek, waarschuwing, trigger, actie, herstel
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 9fc4c99254f4f27b476930a555b237be093bff24
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950722"
---
# <a name="automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Geautomatiseerd onderzoek en antwoord mogelijkheden in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft Threat Protection

Wanneer beveiligingswaarschuwingen worden geactiveerd, kunt u het beste uw beveiligingsteam raadplegen met deze waarschuwingen en de stappen ondernemen om uw organisatie te beveiligen. Het kan zeer lang voor het maken van waarschuwingen, met name wanneer nieuwe waarschuwingen worden gehouden wanneer een onderzoek wordt gehouden, zeer veel tijd in beslag nemen en onderzoeken. Beveiligingsactiviteiten teams kunnen overspoeld worden door het doorschijnende volume van de bedreigingen die ze moeten controleren en beschermen. Geautomatiseerd onderzoek-en antwoord vermogen (ook wel *zelfherstel* mogelijkheden genoemd) in Microsoft Threat Protection kan u helpen. 

Bekijk de volgende video om te zien hoe geautomatiseerde mogelijkheden voor automatisch herstel werken:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Geautomatiseerd onderzoek en antwoord is vergelijkbaar met een virtuele analist in uw Beveiligingscentrum.

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

> [!TIP]
> Laat het ons weten als u denkt dat er een fout is opgetreden met een automatisch onderzoek en antwoord functies in Microsoft Threat Protection. Lees [hoe u onjuiste positief en negatief kunt melden bij een geautomatiseerd onderzoek en antwoord mogelijkheden in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

Wanneer een onderzoek wordt uitgevoerd, worden eventuele andere bijbehorende waarschuwingen toegevoegd aan het onderzoek totdat het onderzoek wordt voltooid. Als een incriminated-entiteit elders wordt weergegeven, wordt het bereik van de geautomatiseerd onderzoek uitgebreid met die entiteit, en moet een algemeen beveiligings Playbook worden uitgevoerd. 

> [!NOTE]
> Niet elke melding veroorzaakt een geautomatiseerd onderzoek en niet alle onderzoekresultaten met geautomatiseerde herstelacties; Dit is alles, afhankelijk van de manier waarop automatisch onderzoek en beantwoorden zijn geconfigureerd voor uw organisatie. 

## <a name="requirements-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Vereisten voor automatisch onderzoek en reacties op Microsoft Threat Protection

|Vereiste |Details |
|--|--|
|Vereisten voor het abonnement |Een van de volgende opties: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5-beveiliging<br/>-Microsoft 365 A5 beveiliging<br/>-Office 365 E5 Plus Enterprise Mobility + Security E5 Plus Windows E5<br/><br/>Zie [licentievereisten voor Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Netwerkvereisten |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ingeschakeld<br/>- [Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) is geconfigureerd<br/>- [MCAS geïntegreerd met Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Systeemvereisten voor Windows |-Windows 10, versie 1709 of hoger is geïnstalleerd (Zie [informatie over de release van Windows 10](https://docs.microsoft.com/windows/release-information/)) met de volgende instellingen voor de Threat Protection-Service:<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Bescherming voor e-mail inhoud en Office-bestanden |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) is geconfigureerd |
|Machtigingen |-Om geautomatiseerde onderzoek en antwoorden te configureren, moet u beschikken over de rol van globale beheerder of beveiligingsbeheerder in azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) of in het Microsoft 365-Beheercentrum [https://admin.microsoft.com](https://admin.microsoft.com) .<br/><br/>Als u geautomatiseerde onderzoek-en antwoord mogelijkheden wilt gebruiken, raadpleegt u de [vereiste machtigingen voor taken in het Actiecentrum](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Volgende stappen

- [Acties met betrekking tot een automatisch onderzoek en antwoord goedkeuren of afwijzen](mtp-autoir-actions.md)
- [Meer informatie over het Actiecentrum](mtp-action-center.md)
