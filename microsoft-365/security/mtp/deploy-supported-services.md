---
title: Services implementeren die worden ondersteund door Microsoft Threat Protection
description: Meer informatie over de Microsoft-beveiligingsservices die kunnen worden geïntegreerd met Microsoft Threat Protection, de licentievereisten en implementatie procedures
keywords: implementeren, licenties, ondersteunde services, inrichting, configuratie van Microsoft Threat Protection, M365, licentie in aanmerking, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud app Security, MCAS, Advanced Threat Protection, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4e4036e1a1ee0ccf807dc5299b9842911f140478
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430809"
---
# <a name="deploy-supported-services"></a>Ondersteunde services implementeren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft Threat Protection](microsoft-threat-protection.md) integreert diverse Microsoft-beveiligingsservices om gecentraliseerde detectie, preventie en onderzoek mogelijkheden te bieden tegen geavanceerde aanvallen. In dit artikel worden de ondersteunde services, de licentievereisten en de voordelen van een of meer services beschreven, en koppelingen naar de manier waarop u ze geheel afzonderlijk kunt implementeren.

## <a name="supported-services"></a>Ondersteunde services
Een Microsoft 365 E5-, E5-beveiligings licentie, A5-of A5-beveiligings licentie of een geldige combinatie van licenties biedt toegang tot de volgende ondersteunde services en geeft u een recht om Microsoft Threat Protection in Microsoft 365 Beveiligingscentrum te gebruiken. [Zie licentievereisten](prerequisites.md#licensing-requirements)

| Ondersteunde service | Beschrijving |
| ------ | ------ |
| Microsoft Defender ATP | Endpoint Protection Suite gebouwd rond krachtige sensoren, Cloud analyses en bedreigings informatie |
| Office 365 ATP | Geavanceerde beveiliging voor uw apps en gegevens in Office 365, waaronder e-mail en andere samenwerkingsprogramma's |
| Azure ATP | Verdedigen tegen geavanceerde bedreigingen, compromisloze identiteiten, en kwaadaardige insiders die gebruikmaken van gecorreleerde Active Directory-signalen |
| Microsoft Cloud App Security | Identificeer en Combat cyberthreats in de cloudservices van Microsoft en van derden |

## <a name="deployed-services-and-functionality"></a>Geïmplementeerde Services en functionaliteit
Microsoft Threat Protection biedt een betere zichtbaarheid, correlatie en herstel wanneer u meer ondersteunde services implementeert.

### <a name="benefits-of-full-deployment"></a>Voordelen van volledige implementatie
Voor de volledige voordelen van Microsoft Threat Protection wordt u aangeraden alle ondersteunde services te implementeren. Hier volgen enkele van de belangrijkste voordelen van een volledige implementatie:
- Incidenten worden geïdentificeerd en gecorreleerd op basis van waarschuwingen en gebeurtenis signalen van alle beschikbare sensoren en servicespecifieke analysemogelijkheden
- Automatisch onderzoek en herstel (lucht) playbooks zijn van toepassing op diverse typen entiteit, waaronder apparaten, postvakken en gebruikersaccounts.
- Een uitgebreid uitgebreid jacht-schema kan worden geraadpleegd voor gebeurtenissen en entiteitsgegevens van apparaten, postvakken en andere entiteiten.

### <a name="limited-deployment-scenarios"></a>Scenario's met beperkte implementatie
Elke ondersteunde service die u implementeert, biedt een zeer uitgebreide set van onbewerkte signalen en gerelateerde informatie. Hoewel de functionaliteit van Microsoft Threat Protection niet wordt uitgeschakeld door beperkte implementatie, is het mogelijk dat de functionaliteit van de eindpunten, apps, gegevens en identiteiten volledig wordt weergeven. Op hetzelfde moment gelden alle herstelmogelijkheden alleen voor entiteiten die kunnen worden beheerd door de services die u hebt geïmplementeerd.

De onderstaande tabel bevat een overzicht van de manier waarop elke ondersteunde service extra gegevens levert, verkoopkansen voor een betere inzichten door de gegevens te correleren en betere herstel-en antwoord mogelijkheden te krijgen.

| Service | Gegevens (signalen & gerelateerde informatie) | Herstel & antwoord bereik |
| ------ | ------ | ------ |
| Microsoft Defender ATP | -Staten van eindpunten en RAW-gebeurtenissen<br />-Detectie van eindpunten en waarschuwingen, waaronder antivirus, EDR, oppervlakte van aanval<br />-Info over bestanden en andere entiteiten op eindpunten | Eindpunten |
| Office 365 ATP | E-mail en Postvak Staten en RAW-gebeurtenissen<br />-Detectie van e-mail, bijlage en link | -Postvakken<br />-Microsoft 365-accounts |
| Azure ATP | Active Directory-signalen, waaronder verificatiegebeurtenissen<br />-Gerelateerde gedrags detectie | Stemmen |
| Microsoft Cloud App Security | -Detectie van niet-goedgekeurde Cloud-apps en-services (schaduw)<br />-Blootstelling van gegevens aan Cloud-apps<br />-Bedreigings activiteit van Cloud-apps | Cloud-apps |

## <a name="deploy-the-services"></a>De services implementeren
Als u een service implementeert, is de implementatie van uw Tenant en enige initiële configuratie meestal vereist. Raadpleeg de volgende tabel voor meer informatie over de manier waarop elk van deze services wordt geïmplementeerd.

| Service | Instructies voor inrichten | Eerste configuratie |
| ------ | ------ | ------ |
| Microsoft Defender ATP | [Implementatiehandleiding voor Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Zie instructies voor het inrichten* |
| Office 365 ATP | *Geen, ingericht met Office 365* | [ATP-beleid configureren](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [Snelstartgids: uw exemplaar van Azure ATP maken](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Zie instructies voor het inrichten* |
| Microsoft Cloud App Security | *Geen* | [Snelstartgids: aan de slag met Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Wanneer u de ondersteunde services hebt geïmplementeerd, [schakelt u Microsoft Threat Protection in](mtp-enable.md).

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van Microsoft Threat Protection](microsoft-threat-protection.md)
- [Microsoft Threat Protection inschakelen](mtp-enable.md)
- [Overzicht van Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Overzicht van Office 365 ATP](../office-365-security/office-365-atp.md)
- [Overzicht van de beveiliging van Microsoft Cloud-app](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Overzicht van Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
