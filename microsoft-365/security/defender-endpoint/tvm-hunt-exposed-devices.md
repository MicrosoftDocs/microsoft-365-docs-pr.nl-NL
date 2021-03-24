---
title: Zoeken naar blootgestelde apparaten
description: Lees hoe bedreigings- en kwetsbaarheidsbeheer kan worden gebruikt om beveiligingsbeheerders, IT-beheerders en SecOps te helpen samenwerken.
keywords: mdatp-tvm-scenario's, mdatp, tvm, tvm-scenario's, risico's beperken & blootstelling aan kwetsbaarheid, bedreiging en kwetsbaarheid verminderen, beveiligingsconfiguratie verbeteren, Microsoft Secure Score voor apparaten verhogen, bedreiging verhogen & kwetsbaarheid Microsoft Secure Score for Devices, Microsoft Secure Score for Devices, exposure score, security controls
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9af7464d9cae06dc53abb019aa0b189d6e72e749
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056680"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>Zoeken naar blootgestelde apparaten - bedreigings- en kwetsbaarheidsbeheer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>Geavanceerde zoeking gebruiken om apparaten met beveiligingsproblemen te vinden

Geavanceerd zoeken is een op query's gebaseerd hulpprogramma voor bedreigingsjacht waarmee u tot 30 dagen onbewerkte gegevens kunt verkennen. U kunt gebeurtenissen in uw netwerk proactief controleren om bedreigingsindicatoren en entiteiten te zoeken. De flexibele toegang tot gegevens maakt ongeconseld zoeken naar bekende en potentiële bedreigingen mogelijk. [Meer informatie over geavanceerd jagen](advanced-hunting-overview.md)

### <a name="schema-tables"></a>Schematabellen

- [DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventaris van software die op apparaten is geïnstalleerd, inclusief de versiegegevens en de status van de end-of-support

- [DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Softwareproblemen gevonden op apparaten en de lijst met beschikbare beveiligingsupdates die elk beveiligingsprobleem verhelpen

- [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available

- [DeviceTvmSecureConfigurationAssessment - Evaluatiegebeurtenissen voor bedreigings-](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) en kwetsbaarheidsbeheer, waarmee de status van verschillende beveiligingsconfiguraties op apparaten wordt aangegeven

- [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; bevat toewijzingen aan verschillende standaarden en benchmarks

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>Controleren welke apparaten betrokken zijn bij waarschuwingen met hoge ernst

1. Ga naar **Geavanceerd zoeken** vanuit het linkernavigatiedeelvenster van het Microsoft Defender-beveiligingscentrum.

2. Schuif omlaag naar de geavanceerde schema's van tvm om vertrouwd te raken met de kolomnamen.

3. Voer de volgende query's in:

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Beveiligingsaanbevelingen](tvm-security-recommendation.md)
- [API‘s](next-gen-threat-and-vuln-mgt.md#apis)
- [Gegevenstoegang configureren voor rollen voor bedreigings- en kwetsbaarheidsbeheer](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [Overzicht van geavanceerd opsporen](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Alle geavanceerde zoektabellen](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
