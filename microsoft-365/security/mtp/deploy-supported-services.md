---
title: Services implementeren die worden ondersteund door Microsoft Threat Protection
description: Meer informatie over de Microsoft-beveiligingsservices die kunnen worden geïntegreerd door Microsoft Threat Protection, hun licentievereisten en implementatieprocedures
keywords: implementeren, licenties, ondersteunde services, provisioning, configuratie Microsoft Threat Protection, M365, licentiegeschiktheid, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, geavanceerde bedreigingsbeveiliging, E5, A5, EMS
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
ms.openlocfilehash: c2798238f0e3cb10edab7f98bf096474a80fa006
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857473"
---
# <a name="deploy-supported-services"></a>Ondersteunde services implementeren

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft Threat Protection](microsoft-threat-protection.md) integreert verschillende Microsoft-beveiligingsservices om gecentraliseerde detectie-, preventie- en onderzoeksmogelijkheden te bieden tegen geavanceerde aanvallen. In dit artikel worden de ondersteunde services, hun licentievereisten, de voordelen en beperkingen beschreven die verbonden zijn aan het implementeren van een of meer services en koppelingen naar hoe u ze afzonderlijk volledig implementeren.

## <a name="supported-services"></a>Ondersteunde diensten
Een Microsoft 365 E5-, E5-beveiligings-, A5- of A5-beveiligingslicentie of een geldige combinatie van licenties biedt toegang tot de volgende ondersteunde services en geeft u het recht om Microsoft Threat Protection te gebruiken in microsoft 365-beveiligingscentrum. [Zie licentievereisten](prerequisites.md#licensing-requirements)

| Ondersteunde service | Beschrijving |
| ------ | ------ |
| Microsoft Defender ATP | Endpoint protection suite gebouwd rond krachtige gedragssensoren, cloud analytics en threat intelligence |
| Office 365 ATP | Geavanceerde beveiliging voor uw apps en gegevens in Office 365, inclusief e-mail en andere samenwerkingstools |
| Azure ATP | Beschermen tegen geavanceerde bedreigingen, gecompromitteerde identiteiten en kwaadwillende insiders met gecorreleerde Active Directory-signalen |
| Microsoft Cloud App Beveiliging | Identificeert en bestrijdt cyberdreigingen in uw Microsoft- en externe cloudservices |

## <a name="deployed-services-and-functionality"></a>Geïmplementeerde services en functionaliteit
Microsoft Threat Protection biedt betere zichtbaarheid, correlatie en herstel terwijl u meer ondersteunde services implementeert.

### <a name="benefits-of-full-deployment"></a>Voordelen van volledige implementatie
Om de volledige voordelen van Microsoft Threat Protection te krijgen, raden we u aan alle ondersteunde services te implementeren. Hier volgen enkele van de belangrijkste voordelen van volledige implementatie:
- Incidenten worden geïdentificeerd en gecorreleerd op basis van waarschuwingen en gebeurtenissignalen van alle beschikbare sensoren en servicespecifieke analysemogelijkheden
- Geautomatiseerde luchtspeelboeken (onderzoek en herstel) zijn van toepassing op verschillende entiteitstypen, waaronder apparaten, postvakken en gebruikersaccounts
- Een uitgebreider geavanceerd jachtschema kan worden opgevraagd voor gebeurtenis- en entiteitsgegevens van apparaten, postvakken en andere entiteiten

### <a name="limited-deployment-scenarios"></a>Beperkte implementatiescenario's
Elke ondersteunde service die u implementeert, biedt een extreem rijke set van ruwe signalen en gecorreleerde informatie. Hoewel beperkte implementatie er niet toe zorgt dat de functionaliteit van Microsoft Threat Protection wordt uitgeschakeld, wordt de mogelijkheid om uitgebreide zichtbaarheid te bieden op uw eindpunten, apps, gegevens en identiteiten beïnvloed. Tegelijkertijd zijn alle herstelmogelijkheden alleen van toepassing op entiteiten die kunnen worden beheerd door de services die u hebt geïmplementeerd.

In de onderstaande tabel wordt beschreven hoe elke ondersteunde service aanvullende gegevens biedt, mogelijkheden om extra inzicht te verkrijgen door de gegevens te correleren en betere herstel- en responsmogelijkheden.

| Service | Gegevens (signalen & gecorreleerde informatie) | Herstel & responsbereik |
| ------ | ------ | ------ |
| Microsoft Defender ATP | - Eindpuntstaten en ruwe evenementen<br />- Endpoint detecties en waarschuwingen, waaronder antivirus, EDR, aanval oppervlak reductie<br />- Informatie over bestanden en andere entiteiten die op eindpunten worden waargenomen | Eindpunten |
| Office 365 ATP | - Post- en mailboxstaten en ruwe evenementen<br />- E-mail-, bijlage- en linkdetecties | - Brievenbussen<br />- Office 365-accounts |
| Azure ATP | - Active Directory-signalen, inclusief verificatiegebeurtenissen<br />- Identiteitsgerelateerde gedragsdetecties | Identiteiten |
| Microsoft Cloud App Beveiliging | - Detectie van niet-gesanctioneerde cloud-apps & services (schaduw IT)<br />- Blootstelling van gegevens aan cloud-apps<br />- In verband met de activiteit geassocieerde cloud-apps voor bedreigingsactiviteit | Cloud-apps |

## <a name="deploy-the-services"></a>De services implementeren
Het implementeren van elke service vereist meestal inrichten aan uw tenant en een initiële configuratie. Zie de volgende tabel om te begrijpen hoe elk van deze services wordt geïmplementeerd.

| Service | Voorzieningsinstructies | Eerste configuratie |
| ------ | ------ | ------ |
| Microsoft Defender ATP | [Microsoft Defender ATP-implementatiehandleiding](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Zie insinerinstructies* |
| Office 365 ATP | *None* | [ATP-beleid configureren](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [Snelstart: uw Azure ATP-exemplaar maken](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Zie insinerinstructies* |
| Microsoft Cloud App Beveiliging | *Geen* | [Snelstart: aan de slag met Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Zodra u de ondersteunde services hebt geïmplementeerd, [schakelt u Microsoft Threat Protection](mtp-enable.md)in.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van Microsoft Threat Protection](microsoft-threat-protection.md)
- [Microsoft-bedreigingsbeveiliging inschakelen](mtp-enable.md)
- [Microsoft Defender ATP-overzicht](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP-overzicht](../office-365-security/office-365-atp.md)
- [Overzicht van Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP-overzicht](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
