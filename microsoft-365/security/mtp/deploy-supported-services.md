---
title: Services implementeren die worden ondersteund door Microsoft Threat Protection
description: Meer informatie over de Microsoft-beveiligingsservices die kunnen worden geïntegreerd door Microsoft Threat Protection, hun licentievereisten en implementatieprocedures
keywords: implementeren, licenties, ondersteunde services, inrichting, configuratie Microsoft Threat Protection, M365, licentiegeschiktheid, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, geavanceerde bescherming tegen bedreigingen, E5, A5, EMS
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c29027bb641530ba2d3c7a22c578770c098f53ba
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633469"
---
# <a name="deploy-supported-services"></a>Ondersteunde services implementeren

**Geldt voor:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft Threat Protection](microsoft-threat-protection.md) integreert verschillende Microsoft-beveiligingsservices om gecentraliseerde detectie-, preventie- en onderzoeksmogelijkheden te bieden tegen geavanceerde aanvallen. In dit artikel worden de ondersteunde services, hun licentievereisten, de voordelen en beperkingen van het implementeren van een of meer services beschreven en worden koppelingen naar de manier waarop u ze afzonderlijk implementeren.

## <a name="supported-services"></a>Ondersteunde diensten
Een Microsoft 365 E5-, E5 Security-, A5- of A5-beveiligingslicentie of een geldige combinatie van licenties biedt toegang tot de volgende ondersteunde services en geeft u het recht microsoft threat protection te gebruiken in het Microsoft 365-beveiligingscentrum. [Zie licentievereisten](prerequisites.md#licensing-requirements)

| Ondersteunde service | Beschrijving |
| ------ | ------ |
| Microsoft Defender ATP | Endpoint protection suite gebouwd rond krachtige gedragssensoren, cloud analytics en threat intelligence |
| Office 365 ATP | Geavanceerde beveiliging voor uw apps en gegevens in Office 365, inclusief e-mail en andere samenwerkingstools |
| Azure ATP | Verdedigen tegen geavanceerde bedreigingen, gecompromitteerde identiteiten en kwaadwillende insiders met behulp van gecorreleerde Active Directory-signalen |
| Microsoft Cloud App Security | Cyberbedreigingen identificeren en bestrijden in uw Microsoft- en externe cloudservices |

## <a name="deployed-services-and-functionality"></a>Geïmplementeerde services en functionaliteit
Microsoft Threat Protection biedt betere zichtbaarheid, correlatie en herstel terwijl u meer ondersteunde services implementeert.

### <a name="benefits-of-full-deployment"></a>Voordelen van volledige implementatie
Om de volledige voordelen van Microsoft Threat Protection te krijgen, raden we u aan alle ondersteunde services te implementeren. Hier volgen enkele van de belangrijkste voordelen van volledige implementatie:
- Incidenten worden geïdentificeerd en gecorreleerd op basis van waarschuwingen en gebeurtenissignalen van alle beschikbare sensoren en servicespecifieke analysemogelijkheden
- Playbooks (Automated Investigation and Remediation) zijn van toepassing op verschillende entiteitstypen, waaronder apparaten, postvakken en gebruikersaccounts
- Een uitgebreider geavanceerd jachtschema kan worden opgevraagd voor gebeurtenis- en entiteitsgegevens van apparaten, postvakken en andere entiteiten

### <a name="limited-deployment-scenarios"></a>Beperkte implementatiescenario's
Elke ondersteunde service die u implementeert, biedt een extreem rijke set ruwe signalen en gecorreleerde informatie. Hoewel de beperkte implementatie er niet toe voor zorgt dat de microsoft-beveiligingsfunctionaliteit wordt uitgeschakeld, wordt de mogelijkheid om uitgebreide zichtbaarheid te bieden op uw eindpunten, apps, gegevens en identiteiten beïnvloed. Tegelijkertijd zijn eventuele herstelmogelijkheden alleen van toepassing op entiteiten die kunnen worden beheerd door de services die u hebt geïmplementeerd.

In de onderstaande tabel wordt beschreven hoe elke ondersteunde service aanvullende gegevens biedt, mogelijkheden om extra inzicht te verkrijgen door de gegevens te correleren en betere herstel- en reactiemogelijkheden.

| Service | Gegevens (signalen & gecorreleerde informatie) | Herstel & reactiebereik |
| ------ | ------ | ------ |
| Microsoft Defender ATP | - Eindpuntstaten en ruwe gebeurtenissen<br />- Endpoint detecties en waarschuwingen, waaronder antivirus, EDR, aanval oppervlakte reductie<br />- Informatie over bestanden en andere entiteiten waargenomen op eindpunten | Eindpunten |
| Office 365 ATP | - Post- en postvakstatuss en onbewerkte gebeurtenissen<br />- Detecties via e-mail, bijlage en koppeling | - Brievenbussen<br />- Microsoft 365-accounts |
| Azure ATP | - Active Directory-signalen, inclusief verificatiegebeurtenissen<br />- Identiteitsgerelateerde gedragsdetecties | Identiteiten |
| Microsoft Cloud App Security | - Detectie van niet-goedgekeurde cloud-apps en -services (schaduw-IT)<br />- Blootstelling van gegevens aan cloud-apps<br />- Bedreigingsactiviteit in verband met cloud-apps | Cloud-apps |

## <a name="deploy-the-services"></a>De services implementeren
Voor het implementeren van elke service is meestal een inlevering nodig voor uw tenant en een eerste configuratie. Zie de volgende tabel om te begrijpen hoe elk van deze services wordt geïmplementeerd.

| Service | Indvoorziensinstructies | Initiële configuratie |
| ------ | ------ | ------ |
| Microsoft Defender ATP | [Microsoft Defender ATP-implementatiehandleiding](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Zie ingerichte instructies* |
| Office 365 ATP | *None* | [ATP-beleid configureren](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [Snelstart: uw Azure ATP-exemplaar maken](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Zie ingerichte instructies* |
| Microsoft Cloud App Security | *Geen* | [Snel aan de slag met Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Zodra u de ondersteunde services hebt geïmplementeerd, [schakelt u Microsoft Threat Protection in.](mtp-enable.md)

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van Microsoft Threat Protection](microsoft-threat-protection.md)
- [Microsoft Threat Protection inschakelen](mtp-enable.md)
- [Overzicht van Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Overzicht van Office 365 ATP](../office-365-security/office-365-atp.md)
- [Overzicht van Microsoft Cloud App-beveiliging](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Overzicht van Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
