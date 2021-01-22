---
title: Services implementeren die worden ondersteund door Microsoft 365 Defender
description: Meer informatie over de Microsoft-beveiligingsservices die kunnen worden geïntegreerd met Microsoft 365 Defender, hun licentievereisten en implementatieprocedures
keywords: deploy, licenses, supported services, provisioning, configuration Microsoft Threat Protection, M365, license eligibility, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, advanced threat protection, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 5af58a1c6850619ca08960997a30fe4a81158446
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928960"
---
# <a name="deploy-supported-services"></a>Ondersteunde services implementeren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-threat-protection.md) integreert verschillende microsoft-beveiligingsservices om gecentraliseerde detectie, preventie en onderzoek te bieden tegen geavanceerde aanvallen. In dit artikel worden de ondersteunde services, de licentievereisten, de voordelen en beperkingen van de implementatie van een of meer services beschreven en vindt u koppelingen naar hoe u deze volledig afzonderlijk kunt implementeren.

## <a name="supported-services"></a>Ondersteunde services
Een microsoft 365 E5-, E5-, A5- of A5-beveiligingslicentie of een geldige combinatie van licenties biedt toegang tot de volgende ondersteunde services en geeft u een recht om Microsoft 365 Defender te gebruiken in het Microsoft 365-beveiligingscentrum. [Licentievereisten bekijken](prerequisites.md#licensing-requirements)

| Ondersteunde service | Beschrijving |
| ------ | ------ |
| Microsoft Defender for Endpoint | Eindpuntbeveiligingssuite gebouwd op krachtige sensoren, cloudanalyses en bedreigingsinformatie |
|Microsoft Defender voor Office 365 | Geavanceerde beveiliging voor uw apps en gegevens in Office 365, inclusief e-mail en andere samenwerkingshulpmiddelen |
| Microsoft Defender for Identity | Bescherming tegen geavanceerde bedreigingen, gekromde identiteiten en kwaadwillende insiders met behulp van correleren Active Directory-signalen |
| Microsoft Cloud App Security | Cyberaanvallen identificeren en bestrijden in uw cloudservices van Microsoft en derden |

## <a name="deployed-services-and-functionality"></a>Geïmplementeerde services en functionaliteit
Microsoft 365 Defender biedt betere zichtbaarheid, correlatie en herstel wanneer u meer ondersteunde services implementeert.

### <a name="benefits-of-full-deployment"></a>Voordelen van volledige implementatie
Om de volledige voordelen van Microsoft 365 Defender te krijgen, raden we u aan alle ondersteunde services te implementeren. Hier zijn enkele van de belangrijkste voordelen van een volledige implementatie:
- Incidenten worden geïdentificeerd en gerelateerd op basis van waarschuwingen en gebeurtenissignaal van alle beschikbare sensoren en servicespecifieke analysemogelijkheden
- Playbooks voor automatisch onderzoek en herstel (AIR) zijn van toepassing op verschillende entiteitstypen, waaronder apparaten, postvakken en gebruikersaccounts.
- Een uitgebreider geavanceerd schema voor zoeken kan worden opgevraagd naar gebeurtenis- en entiteitsgegevens van apparaten, postvakken en andere entiteiten

### <a name="limited-deployment-scenarios"></a>Scenario's voor beperkte implementatie
Elke ondersteunde service die u implementeert, biedt een zeer uitgebreide set onbewerkte signalen en correlatiede informatie. Hoewel beperkte implementatie niet tot gevolgen heeft dat de functionaliteit van Microsoft 365 Defender wordt uitgeschakeld, heeft dit invloed op de mogelijkheid om uitgebreide zichtbaarheid te bieden voor uw eindpunten, apps, gegevens en identiteiten. Tegelijkertijd zijn herstelmogelijkheden alleen van toepassing op entiteiten die kunnen worden beheerd door de services die u hebt geïmplementeerd.

In de onderstaande tabel wordt beschreven hoe elke ondersteunde service aanvullende gegevens biedt, mogelijkheden om extra inzicht te krijgen door de gegevens te correleren, en betere herstel- en antwoordmogelijkheden.

| Service | Gegevens (signalen van & info) | Remediation & response scope |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | - Eindpunten en onbewerkte gebeurtenissen<br />- Eindpuntdetecties en -waarschuwingen, waaronder antivirussoftware, EDR, aanvallen verminderen<br />- Informatie over bestanden en andere entiteiten die op eindpunten worden waargenomen | Eindpunten |
|Microsoft Defender voor Office 365 | - E-mail- en postvak staat en onbewerkte gebeurtenissen<br />- Detectie van e-mail, bijlagen en koppeling | - Postvakken<br />- Microsoft 365-accounts |
| Microsoft Defender for Identity | - Active Directory-signalen, inclusief verificatiegebeurtenissen<br />- Identity-gerelateerde detecties van gezichtsherkenning | Identities |
| Microsoft Cloud App Security | - Detectie van niet-geanctioneerde cloud-apps en -services (SCHADUW IT)<br />- Blootstelling van gegevens aan cloud-apps<br />- Bedreigingsactiviteit gekoppeld aan cloud-apps | Cloud-apps |

## <a name="deploy-the-services"></a>De services implementeren
Voor het implementeren van elke service moet meestal de tenant worden ingericht en moet er een eerste configuratie worden geïmplementeerd. Zie de volgende tabel als u wilt weten hoe elk van deze services wordt geïmplementeerd.

| Service | Inrichtingsinstructies | Eerste configuratie |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | [Implementatiehandleiding voor Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Zie inrichtingsinstructies* |
|Microsoft Defender voor Office 365 | *Geen, ingericht met Office 365* | [Beleid in Microsoft Defender voor Office 365 instellen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Microsoft Defender for Identity | [Snelstart: uw Exemplaar van Microsoft Defender voor identiteit maken](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Zie inrichtingsinstructies* |
| Microsoft Cloud App Security | *Geen* | [Snelstart: Aan de slag met Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Als u de ondersteunde services hebt geïmplementeerd, kunt u [Microsoft 365 Defender in dienst zetten.](mtp-enable.md)

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van Microsoft 365 Defender](microsoft-threat-protection.md)
- [Microsoft 365 Defender in te zetten](mtp-enable.md)
- [Overzicht van Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Overzicht van Microsoft Defender voor Office 365](../office-365-security/office-365-atp.md)
- [Overzicht van beveiliging van Microsoft Cloud-apps](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Overzicht van Microsoft Defender voor identiteit](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
