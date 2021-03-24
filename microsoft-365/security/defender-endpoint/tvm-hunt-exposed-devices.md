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
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a><span data-ttu-id="16d4c-104">Zoeken naar blootgestelde apparaten - bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="16d4c-104">Hunt for exposed devices - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="16d4c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="16d4c-105">**Applies to:**</span></span>

- [<span data-ttu-id="16d4c-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="16d4c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="16d4c-107">Bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="16d4c-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="16d4c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16d4c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="16d4c-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="16d4c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="16d4c-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="16d4c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a><span data-ttu-id="16d4c-111">Geavanceerde zoeking gebruiken om apparaten met beveiligingsproblemen te vinden</span><span class="sxs-lookup"><span data-stu-id="16d4c-111">Use advanced hunting to find devices with vulnerabilities</span></span>

<span data-ttu-id="16d4c-112">Geavanceerd zoeken is een op query's gebaseerd hulpprogramma voor bedreigingsjacht waarmee u tot 30 dagen onbewerkte gegevens kunt verkennen.</span><span class="sxs-lookup"><span data-stu-id="16d4c-112">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="16d4c-113">U kunt gebeurtenissen in uw netwerk proactief controleren om bedreigingsindicatoren en entiteiten te zoeken.</span><span class="sxs-lookup"><span data-stu-id="16d4c-113">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="16d4c-114">De flexibele toegang tot gegevens maakt ongeconseld zoeken naar bekende en potentiële bedreigingen mogelijk.</span><span class="sxs-lookup"><span data-stu-id="16d4c-114">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span> [<span data-ttu-id="16d4c-115">Meer informatie over geavanceerd jagen</span><span class="sxs-lookup"><span data-stu-id="16d4c-115">Learn more about advanced hunting</span></span>](advanced-hunting-overview.md)

### <a name="schema-tables"></a><span data-ttu-id="16d4c-116">Schematabellen</span><span class="sxs-lookup"><span data-stu-id="16d4c-116">Schema tables</span></span>

- <span data-ttu-id="16d4c-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventaris van software die op apparaten is geïnstalleerd, inclusief de versiegegevens en de status van de end-of-support</span><span class="sxs-lookup"><span data-stu-id="16d4c-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventory of software installed on devices, including their version information and end-of-support status</span></span>

- <span data-ttu-id="16d4c-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Softwareproblemen gevonden op apparaten en de lijst met beschikbare beveiligingsupdates die elk beveiligingsprobleem verhelpen</span><span class="sxs-lookup"><span data-stu-id="16d4c-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Software vulnerabilities found on devices and the list of available security updates that address each vulnerability</span></span>

- <span data-ttu-id="16d4c-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span><span class="sxs-lookup"><span data-stu-id="16d4c-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span>

- <span data-ttu-id="16d4c-120">[DeviceTvmSecureConfigurationAssessment - Evaluatiegebeurtenissen voor bedreigings-](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) en kwetsbaarheidsbeheer, waarmee de status van verschillende beveiligingsconfiguraties op apparaten wordt aangegeven</span><span class="sxs-lookup"><span data-stu-id="16d4c-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Threat and vulnerability management assessment events, indicating the status of various security configurations on devices</span></span>

- <span data-ttu-id="16d4c-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; bevat toewijzingen aan verschillende standaarden en benchmarks</span><span class="sxs-lookup"><span data-stu-id="16d4c-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a><span data-ttu-id="16d4c-122">Controleren welke apparaten betrokken zijn bij waarschuwingen met hoge ernst</span><span class="sxs-lookup"><span data-stu-id="16d4c-122">Check which devices are involved in high severity alerts</span></span>

1. <span data-ttu-id="16d4c-123">Ga naar **Geavanceerd zoeken** vanuit het linkernavigatiedeelvenster van het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="16d4c-123">Go to **Advanced hunting** from the left-hand navigation pane of the Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="16d4c-124">Schuif omlaag naar de geavanceerde schema's van tvm om vertrouwd te raken met de kolomnamen.</span><span class="sxs-lookup"><span data-stu-id="16d4c-124">Scroll down to the TVM advanced hunting schemas to familiarize yourself with the column names.</span></span>

3. <span data-ttu-id="16d4c-125">Voer de volgende query's in:</span><span class="sxs-lookup"><span data-stu-id="16d4c-125">Enter the following queries:</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="16d4c-126">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="16d4c-126">Related topics</span></span>

- [<span data-ttu-id="16d4c-127">Overzicht van bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="16d4c-127">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="16d4c-128">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="16d4c-128">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="16d4c-129">API‘s</span><span class="sxs-lookup"><span data-stu-id="16d4c-129">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)
- [<span data-ttu-id="16d4c-130">Gegevenstoegang configureren voor rollen voor bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="16d4c-130">Configure data access for threat and vulnerability management roles</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [<span data-ttu-id="16d4c-131">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="16d4c-131">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [<span data-ttu-id="16d4c-132">Alle geavanceerde zoektabellen</span><span class="sxs-lookup"><span data-stu-id="16d4c-132">All advanced hunting tables</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
