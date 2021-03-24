---
title: DeviceTvmSecureConfigurationAssessment table in the advanced hunting schema
description: Meer informatie over & beveiligingsbeoordelingsgebeurtenissen voor beveiligingsrisico's in de tabel DeviceTvmSecureConfigurationAssessment van het schema Geavanceerd. Deze gebeurtenissen bevatten apparaatgegevens en beveiligingsconfiguratiegegevens, impact- en compliancegegevens.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059766"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="ef662-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="ef662-105">DeviceTvmSecureConfigurationAssessment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ef662-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ef662-106">**Applies to:**</span></span>
- [<span data-ttu-id="ef662-107">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="ef662-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="ef662-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ef662-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ef662-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ef662-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ef662-110">Elke rij in de `DeviceTvmSecureConfigurationAssessment` tabel bevat een beoordelingsgebeurtenis voor een specifieke beveiligingsconfiguratie van [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="ef662-110">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="ef662-111">Gebruik deze verwijzing om de meest recente evaluatieresultaten te controleren en te bepalen of apparaten compatibel zijn.</span><span class="sxs-lookup"><span data-stu-id="ef662-111">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="ef662-112">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)</span><span class="sxs-lookup"><span data-stu-id="ef662-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="ef662-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="ef662-113">Column name</span></span> | <span data-ttu-id="ef662-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="ef662-114">Data type</span></span> | <span data-ttu-id="ef662-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ef662-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="ef662-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef662-116">string</span></span> | <span data-ttu-id="ef662-117">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="ef662-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ef662-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef662-118">string</span></span> | <span data-ttu-id="ef662-119">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="ef662-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="ef662-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef662-120">string</span></span> | <span data-ttu-id="ef662-121">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ef662-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="ef662-122">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="ef662-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="ef662-123">datetime</span><span class="sxs-lookup"><span data-stu-id="ef662-123">datetime</span></span> |<span data-ttu-id="ef662-124">Datum en tijd waarop de record is gegenereerd</span><span class="sxs-lookup"><span data-stu-id="ef662-124">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="ef662-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef662-125">string</span></span> | <span data-ttu-id="ef662-126">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="ef662-126">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="ef662-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef662-127">string</span></span> | <span data-ttu-id="ef662-128">Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="ef662-128">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="ef662-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef662-129">string</span></span> |<span data-ttu-id="ef662-130">Subcategorie of subgroepering waarvan de configuratie deel uitmaken.</span><span class="sxs-lookup"><span data-stu-id="ef662-130">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="ef662-131">In veel gevallen worden hier specifieke mogelijkheden of functies beschreven.</span><span class="sxs-lookup"><span data-stu-id="ef662-131">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="ef662-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef662-132">string</span></span> | <span data-ttu-id="ef662-133">Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10)</span><span class="sxs-lookup"><span data-stu-id="ef662-133">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="ef662-134">booleaanse</span><span class="sxs-lookup"><span data-stu-id="ef662-134">boolean</span></span> | <span data-ttu-id="ef662-135">Geeft aan of de configuratie of het beleid juist is geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="ef662-135">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="ef662-136">booleaanse</span><span class="sxs-lookup"><span data-stu-id="ef662-136">boolean</span></span> | <span data-ttu-id="ef662-137">Geeft aan of de configuratie of het beleid van toepassing is op het apparaat</span><span class="sxs-lookup"><span data-stu-id="ef662-137">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="ef662-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef662-138">string</span></span> | <span data-ttu-id="ef662-139">Aanvullende contextuele informatie over de configuratie of het beleid</span><span class="sxs-lookup"><span data-stu-id="ef662-139">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="ef662-140">booleaanse</span><span class="sxs-lookup"><span data-stu-id="ef662-140">boolean</span></span> | <span data-ttu-id="ef662-141">Geeft aan of er gevolgen voor de gebruiker zijn als de configuratie of het beleid wordt toegepast</span><span class="sxs-lookup"><span data-stu-id="ef662-141">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ef662-142">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ef662-142">Related topics</span></span>

- [<span data-ttu-id="ef662-143">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="ef662-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ef662-144">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="ef662-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ef662-145">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="ef662-145">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="ef662-146">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="ef662-146">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)