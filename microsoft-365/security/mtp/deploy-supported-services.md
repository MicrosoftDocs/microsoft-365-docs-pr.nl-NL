---
title: Services implementeren die worden ondersteund door Microsoft 365 Defender
description: Meer informatie over de Microsoft-beveiligingsservices die kunnen worden geïntegreerd door Microsoft 365 Defender, hun licentievereisten en implementatieprocedures
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
ms.openlocfilehash: 3dce310dbfd8bd8debe9b6eb3015790073002bee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928890"
---
# <a name="deploy-supported-services"></a>Ondersteunde services implementeren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-threat-protection.md) integreert verschillende Microsoft-beveiligingsservices om gecentraliseerde detectie-, preventie- en onderzoeksmogelijkheden te bieden tegen geavanceerde aanvallen. In dit artikel worden de ondersteunde services, hun licentievereisten, de voordelen en beperkingen beschreven die samenhangen met het implementeren van een of meer services, en worden koppelingen beschreven over hoe u deze volledig afzonderlijk kunt implementeren.

## <a name="supported-services"></a>Ondersteunde services
Een Microsoft 365 E5-, E5-beveiligings-, A5- of A5-beveiligingslicentie of een geldige combinatie van licenties biedt toegang tot de volgende ondersteunde services en geeft u het recht Microsoft 365 Defender te gebruiken in het Microsoft 365-beveiligingscentrum. [Licentievereisten bekijken](prerequisites.md#licensing-requirements)

| Ondersteunde service | Beschrijving |
| ------ | ------ |
| Microsoft Defender for Endpoint | Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence |
|Microsoft Defender voor Office 365 | Geavanceerde beveiliging voor uw apps en gegevens in Office 365, inclusief e-mail en andere samenwerkingshulpmiddelen |
| Microsoft Defender for Identity | Verdediging tegen geavanceerde bedreigingen, gecompromitteerde identiteiten en kwaadwillende insiders met behulp van gecorreleerde Active Directory-signalen |
| Microsoft Cloud App Security | Cyberthreats identificeren en bestrijden in uw Microsoft- en externe cloudservices |

## <a name="deployed-services-and-functionality"></a>Geïmplementeerde services en functionaliteit
Microsoft 365 Defender biedt een betere zichtbaarheid, correlatie en herstel wanneer u meer ondersteunde services implementeert.

### <a name="benefits-of-full-deployment"></a>Voordelen van volledige implementatie
Om de volledige voordelen van Microsoft 365 Defender te krijgen, raden we u aan alle ondersteunde services te implementeren. Hier zijn enkele belangrijke voordelen van volledige implementatie:
- Incidenten worden geïdentificeerd en gecorreleerd op basis van waarschuwingen en gebeurtenissignalen van alle beschikbare sensoren en servicespecifieke analysemogelijkheden
- Air-playbooks (Automated Investigation and Remediation) zijn van toepassing op verschillende entiteitstypen, waaronder apparaten, postvakken en gebruikersaccounts
- Er kan een uitgebreider geavanceerd schema worden opgevraagd voor gebeurtenis- en entiteitsgegevens van apparaten, postvakken en andere entiteiten

### <a name="limited-deployment-scenarios"></a>Beperkte implementatiescenario's
Elke ondersteunde service die u implementeert, biedt een zeer uitgebreide set onbewerkte signalen en gecorreleerde informatie. Hoewel beperkte implementatie er niet toe kan leiden dat de functionaliteit van Microsoft 365 Defender wordt uitgeschakeld, is de mogelijkheid om uitgebreide zichtbaarheid te bieden voor uw eindpunten, apps, gegevens en identiteiten van invloed. Tegelijkertijd zijn herstelmogelijkheden alleen van toepassing op entiteiten die kunnen worden beheerd door de services die u hebt geïmplementeerd.

In de onderstaande tabel ziet u hoe elke ondersteunde service aanvullende gegevens biedt, mogelijkheden om extra inzicht te verkrijgen door de gegevens te correveren en betere herstel- en antwoordmogelijkheden te bieden.

| Service | Gegevens (signalen & gecorreleerde informatie) | Herstel van & antwoordbereik |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | - Eindpunten en onbewerkte gebeurtenissen<br />- Eindpuntdetecties en -waarschuwingen, waaronder antivirussoftware, EDR, beperking van het oppervlak van de aanval<br />- Informatie over bestanden en andere entiteiten die zijn waargenomen op eindpunten | Eindpunten |
|Microsoft Defender voor Office 365 | - E-mail- en postvakstaten en onbewerkte gebeurtenissen<br />- Detecties van e-mail, bijlagen en koppeling | - Postvakken<br />- Microsoft 365-accounts |
| Microsoft Defender for Identity | - Active Directory-signalen, inclusief verificatiegebeurtenissen<br />- Identiteitsgerelateerde gedragsdetecties | Identiteiten |
| Microsoft Cloud App Security | - Detectie van niet-geanctioneerde cloud-apps en -services (schaduw-IT)<br />- Blootstelling van gegevens aan cloud-apps<br />- Bedreigingsactiviteit die is gekoppeld aan cloud-apps | Cloud-apps |

## <a name="deploy-the-services"></a>De services implementeren
Voor het implementeren van elke service is meestal inrichting voor uw tenant en een eerste configuratie vereist. Zie de volgende tabel om te begrijpen hoe elk van deze services worden geïmplementeerd.

| Service | Inrichtingsinstructies | Eerste configuratie |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | [Implementatiehandleiding voor Microsoft Defender voor eindpunten](/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Zie inrichtingsinstructies* |
|Microsoft Defender voor Office 365 | *Geen, ingericht met Office 365* | [Beleid in Microsoft Defender voor Office 365 instellen](../office-365-security/office-365-atp.md#configure-atp-policies) |
| Microsoft Defender for Identity | [Snelstart: Uw Exemplaar van Microsoft Defender voor identiteit maken](/azure-advanced-threat-protection/install-atp-step1) | *Zie inrichtingsinstructies* |
| Microsoft Cloud App Security | *Geen* | [Snelstart: Aan de slag met Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security) |

Nadat u de ondersteunde services hebt geïmplementeerd, [schakelt u Microsoft 365 Defender in.](mtp-enable.md)

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van Microsoft 365 Defender](microsoft-threat-protection.md)
- [Microsoft 365 Defender in-](mtp-enable.md)
- [Overzicht van Microsoft Defender voor eindpunt](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Overzicht van Microsoft Defender voor Office 365](../office-365-security/office-365-atp.md)
- [Overzicht van Microsoft Cloud App-beveiliging](/cloud-app-security/what-is-cloud-app-security)
- [Overzicht van Microsoft Defender voor identiteit](/azure-advanced-threat-protection/what-is-atp)