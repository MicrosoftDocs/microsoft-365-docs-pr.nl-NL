---
title: Services implementeren die worden ondersteund door Microsoft 365 Defender
description: Meer informatie over de Microsoft-beveiligingsservices die kunnen worden geïntegreerd met Microsoft 365 Defender, de licentievereisten en implementatie procedures
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
ms.openlocfilehash: 4a1bed4d6c6688c266b9df8ce36e4b25a0632d68
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843922"
---
# <a name="deploy-supported-services"></a>Ondersteunde services implementeren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-threat-protection.md) integreert diverse Microsoft-beveiligingsservices om gecentraliseerde detectie, preventie en onderzoek mogelijkheden te bieden tegen geavanceerde aanvallen. In dit artikel worden de ondersteunde services, de licentievereisten en de voordelen van een of meer services beschreven, en koppelingen naar de manier waarop u ze geheel afzonderlijk kunt implementeren.

## <a name="supported-services"></a>Ondersteunde services
Een Microsoft 365 E5-, E5-beveiligings licentie, A5-of A5-beveiligings licentie, of een geldige combinatie van licenties, biedt toegang tot de volgende ondersteunde services en geeft u een recht om Microsoft 365 Defender te gebruiken in Microsoft 365 Beveiligingscentrum. [Zie licentievereisten](prerequisites.md#licensing-requirements)

| Ondersteunde service | Beschrijving |
| ------ | ------ |
| Microsoft Defender voor eindpunt | Endpoint Protection Suite gebouwd rond krachtige sensoren, Cloud analyses en bedreigings informatie |
|Microsoft Defender voor Office 365 | Geavanceerde beveiliging voor uw apps en gegevens in Office 365, waaronder e-mail en andere samenwerkingsprogramma's |
| Microsoft Defender voor identiteit | Verdedigen tegen geavanceerde bedreigingen, compromisloze identiteiten, en kwaadaardige insiders die gebruikmaken van gecorreleerde Active Directory-signalen |
| Microsoft Cloud App Security | Identificeer en Combat cyberthreats in de cloudservices van Microsoft en van derden |

## <a name="deployed-services-and-functionality"></a>Geïmplementeerde Services en functionaliteit
Microsoft 365 Defender biedt betere zichtbaarheid, correlatie en herstel wanneer u meer ondersteunde services implementeert.

### <a name="benefits-of-full-deployment"></a>Voordelen van volledige implementatie
U wordt aangeraden alle ondersteunde services te implementeren voor de volledige voordelen van Microsoft 365 Defender. Hier volgen enkele van de belangrijkste voordelen van een volledige implementatie:
- Incidenten worden geïdentificeerd en gecorreleerd op basis van waarschuwingen en gebeurtenis signalen van alle beschikbare sensoren en servicespecifieke analysemogelijkheden
- Automatisch onderzoek en herstel (lucht) playbooks zijn van toepassing op diverse typen entiteit, waaronder apparaten, postvakken en gebruikersaccounts.
- Een uitgebreid uitgebreid jacht-schema kan worden geraadpleegd voor gebeurtenissen en entiteitsgegevens van apparaten, postvakken en andere entiteiten.

### <a name="limited-deployment-scenarios"></a>Scenario's met beperkte implementatie
Elke ondersteunde service die u implementeert, biedt een zeer uitgebreide set van onbewerkte signalen en gerelateerde informatie. Hoewel de functionaliteit van Microsoft 365 Defender niet wordt uitgeschakeld door beperkte implementatie, heeft dit invloed op de mogelijkheid om volledig inzicht te geven in de eindpunten, apps, gegevens en identiteiten. Op hetzelfde moment gelden alle herstelmogelijkheden alleen voor entiteiten die kunnen worden beheerd door de services die u hebt geïmplementeerd.

De onderstaande tabel bevat een overzicht van de manier waarop elke ondersteunde service extra gegevens levert, verkoopkansen voor een betere inzichten door de gegevens te correleren en betere herstel-en antwoord mogelijkheden te krijgen.

| Service | Gegevens (signalen & gerelateerde informatie) | Herstel & antwoord bereik |
| ------ | ------ | ------ |
| Microsoft Defender voor eindpunt | -Staten van eindpunten en RAW-gebeurtenissen<br />-Detectie van eindpunten en waarschuwingen, waaronder antivirus, EDR, oppervlakte van aanval<br />-Info over bestanden en andere entiteiten op eindpunten | Eindpunten |
|Microsoft Defender voor Office 365 | E-mail en Postvak Staten en RAW-gebeurtenissen<br />-Detectie van e-mail, bijlage en link | -Postvakken<br />-Microsoft 365-accounts |
| Microsoft Defender voor identiteit | Active Directory-signalen, waaronder verificatiegebeurtenissen<br />-Gerelateerde gedrags detectie | Stemmen |
| Microsoft Cloud App Security | -Detectie van niet-goedgekeurde Cloud-apps en-services (schaduw)<br />-Blootstelling van gegevens aan Cloud-apps<br />-Bedreigings activiteit van Cloud-apps | Cloud-apps |

## <a name="deploy-the-services"></a>De services implementeren
Als u een service implementeert, is de implementatie van uw Tenant en enige initiële configuratie meestal vereist. Raadpleeg de volgende tabel voor meer informatie over de manier waarop elk van deze services wordt geïmplementeerd.

| Service | Instructies voor inrichten | Eerste configuratie |
| ------ | ------ | ------ |
| Microsoft Defender voor eindpunt | [Implementatiehandleiding voor Microsoft Defender voor eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Zie instructies voor het inrichten* |
|Microsoft Defender voor Office 365 | *Geen, ingericht met Office 365* | [Beleidsregels voor Microsoft Defender voor Office 365 configureren](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Microsoft Defender voor identiteit | [Snelstartgids: uw Microsoft Defender maken voor een identiteits exemplaar](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Zie instructies voor het inrichten* |
| Microsoft Cloud App Security | *Geen* | [Snelstartgids: aan de slag met Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Wanneer u de ondersteunde services hebt geïmplementeerd, [schakelt u Microsoft 365 Defender in](mtp-enable.md).

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van Microsoft 365 Defender](microsoft-threat-protection.md)
- [Microsoft 365 Defender inschakelen](mtp-enable.md)
- [Overzicht van Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Overzicht van Microsoft Defender voor Office 365](../office-365-security/office-365-atp.md)
- [Overzicht van de beveiliging van Microsoft Cloud-app](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Overzicht van Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
