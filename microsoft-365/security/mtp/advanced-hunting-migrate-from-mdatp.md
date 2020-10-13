---
title: Geavanceerde jagers-query's migreren vanuit Microsoft Defender ATP
description: Meer informatie over het aanpassen van uw Microsoft Defender ATP-query's, zodat u deze kunt gebruiken in Microsoft Threat Protection
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Microsoft Defender ATP, mdatp, Search, query, telemetrie, aangepaste detectie, schema, kusto, Microsoft 365, toewijzen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f56360b28a9fe9de4198d97954a64a429d1d99a5
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429693"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a><span data-ttu-id="b992d-104">Geavanceerde jagers-query's migreren vanuit Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b992d-104">Migrate advanced hunting queries from Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b992d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b992d-105">**Applies to:**</span></span>
- <span data-ttu-id="b992d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b992d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b992d-107">Verplaats uw werkstromen voor gevorderden in Microsoft Defender ATP om te zoeken naar bedreigingen met een bredere set gegevens.</span><span class="sxs-lookup"><span data-stu-id="b992d-107">Move your advanced hunting workflows from Microsoft Defender ATP to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="b992d-108">In Microsoft Threat Protection krijgt u toegang tot gegevens vanuit andere Microsoft 365-beveiligingsoplossingen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="b992d-108">In Microsoft Threat Protection, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="b992d-109">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b992d-109">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="b992d-110">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b992d-110">Office 365 Advanced Threat Protection</span></span>
- <span data-ttu-id="b992d-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b992d-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="b992d-112">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b992d-112">Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="b992d-113">De meeste Microsoft Defender ATP-klanten kunnen [Microsoft Threat Protection gebruiken zonder extra licenties](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="b992d-113">Most Microsoft Defender ATP customers can [use Microsoft Threat Protection without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="b992d-114">[Schakel Microsoft Threat Protection](mtp-enable.md)in om te beginnen met het overstappen van uw werkstromen voor gevorderden in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="b992d-114">To start transitioning your advanced hunting workflows from Microsoft Defender ATP, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

<span data-ttu-id="b992d-115">U kunt overstappen zonder dat dit invloed heeft op uw bestaande Microsoft Defender ATP-werkstromen.</span><span class="sxs-lookup"><span data-stu-id="b992d-115">You can transition without affecting your existing Microsoft Defender ATP workflows.</span></span> <span data-ttu-id="b992d-116">Opgeslagen query's blijven behouden en aangepaste detectieregels blijven doorgaan met het uitvoeren en genereren van waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="b992d-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="b992d-117">Ze zijn echter ook zichtbaar in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="b992d-117">They will, however, be visible in Microsoft Threat Protection.</span></span> 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a><span data-ttu-id="b992d-118">Schema tabellen in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b992d-118">Schema tables in Microsoft Threat Protection only</span></span>
<span data-ttu-id="b992d-119">Het [geavanceerde Microsoft Threat Protection-schema](advanced-hunting-schema-tables.md) bevat extra tabellen met gegevens van diverse microsoft 365-beveiligingsoplossingen.</span><span class="sxs-lookup"><span data-stu-id="b992d-119">The [Microsoft Threat Protection advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="b992d-120">De volgende tabellen zijn alleen beschikbaar in Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="b992d-120">The following tables are available only in Microsoft Threat Protection:</span></span>

| <span data-ttu-id="b992d-121">Tabelnaam</span><span class="sxs-lookup"><span data-stu-id="b992d-121">Table name</span></span> | <span data-ttu-id="b992d-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b992d-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="b992d-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="b992d-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="b992d-124">Bestanden, IP-adressen, Url's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="b992d-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="b992d-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="b992d-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="b992d-126">Waarschuwingen uit Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud app Security en Azure ATP, waaronder informatie over de ernst en bedreigings Categorieën</span><span class="sxs-lookup"><span data-stu-id="b992d-126">Alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="b992d-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="b992d-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="b992d-128">Activiteiten met betrekking tot bestanden in Cloud-apps en-services</span><span class="sxs-lookup"><span data-stu-id="b992d-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="b992d-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="b992d-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="b992d-130">Informatie over bestanden die zijn gekoppeld aan e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="b992d-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="b992d-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="b992d-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="b992d-132">Microsoft 365-e-mail gebeurtenissen, waaronder e-mail bezorging en blokkering van gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="b992d-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="b992d-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="b992d-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="b992d-134">Beveiligingsgebeurtenissen die na na ontvangst plaatsvinden, nadat Microsoft 365 de e-mail heeft bezorgd in het postvak van de geadresseerde</span><span class="sxs-lookup"><span data-stu-id="b992d-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="b992d-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="b992d-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="b992d-136">Info over Url's voor e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="b992d-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="b992d-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="b992d-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="b992d-138">Gebeurtenissen waarbij een on-premises domeincontroller met Active Directory (AD) wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b992d-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="b992d-139">Deze tabel behandelt een bereik van gebeurtenissen die betrekking hebben op de identiteit en de systeemgebeurtenissen op de domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="b992d-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="b992d-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="b992d-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="b992d-141">Account gegevens van diverse bronnen, waaronder Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b992d-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="b992d-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="b992d-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="b992d-143">Verificatiegebeurtenissen in Active Directory en Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="b992d-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="b992d-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="b992d-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="b992d-145">Query's voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen</span><span class="sxs-lookup"><span data-stu-id="b992d-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="b992d-146">Kaart DeviceAlertEvents tabel</span><span class="sxs-lookup"><span data-stu-id="b992d-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="b992d-147">`AlertInfo`Met de `AlertEvidence` tabellen en worden de tabellen `DeviceAlertEvents` in het MICROsoft Defender ATP-schema vervangen.</span><span class="sxs-lookup"><span data-stu-id="b992d-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender ATP schema.</span></span> <span data-ttu-id="b992d-148">Naast gegevens over waarschuwingen voor apparaten, bevatten deze twee tabellen gegevens over waarschuwingen voor identiteiten, apps en e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="b992d-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="b992d-149">Gebruik de volgende tabel om te controleren hoe `DeviceAlertEvents` kolommen zijn toegewezen aan kolommen in de `AlertInfo` `AlertEvidence` tabellen en.</span><span class="sxs-lookup"><span data-stu-id="b992d-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="b992d-150">Naast de kolommen de volgende tabel `AlertEvidence` bevat de tabel veel andere kolommen die een meer holistische afbeelding van waarschuwingen van diverse bronnen bieden.</span><span class="sxs-lookup"><span data-stu-id="b992d-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="b992d-151">Alle AlertEvidence kolommen weergeven</span><span class="sxs-lookup"><span data-stu-id="b992d-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="b992d-152">Kolom DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="b992d-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="b992d-153">Waarnaar u dezelfde gegevens kunt vinden in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b992d-153">Where to find the same data in Microsoft Threat Protection</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="b992d-154">`AlertInfo` en  `AlertEvidence` tabellen</span><span class="sxs-lookup"><span data-stu-id="b992d-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="b992d-155">`AlertInfo` en  `AlertEvidence` tabellen</span><span class="sxs-lookup"><span data-stu-id="b992d-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="b992d-156">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b992d-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="b992d-157">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b992d-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="b992d-158">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="b992d-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="b992d-159">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="b992d-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="b992d-160">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="b992d-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="b992d-161">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b992d-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="b992d-162">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b992d-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="b992d-163">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b992d-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="b992d-164">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b992d-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="b992d-165">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="b992d-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="b992d-166">Deze kolom wordt meestal gebruikt in Microsoft Defender ATP om gerelateerde records in andere tabellen te zoeken.</span><span class="sxs-lookup"><span data-stu-id="b992d-166">This column is typically used in Microsoft Defender ATP to locate related records in other tables.</span></span> <span data-ttu-id="b992d-167">In Microsoft Threat Protection kunt u gerelateerde gegevens rechtstreeks uit de tabel weergeven `AlertEvidence` .</span><span class="sxs-lookup"><span data-stu-id="b992d-167">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="b992d-168">Deze kolom wordt meestal gebruikt in Microsoft Defender ATP voor aanvullende informatie over gebeurtenissen in andere tabellen.</span><span class="sxs-lookup"><span data-stu-id="b992d-168">This column is typically used in Microsoft Defender ATP for additional event information in other tables.</span></span> <span data-ttu-id="b992d-169">In Microsoft Threat Protection kunt u gerelateerde gegevens rechtstreeks uit de tabel weergeven `AlertEvidence` .</span><span class="sxs-lookup"><span data-stu-id="b992d-169">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a><span data-ttu-id="b992d-170">Bestaande Microsoft Defender ATP-query's aanpassen</span><span class="sxs-lookup"><span data-stu-id="b992d-170">Adjust existing Microsoft Defender ATP queries</span></span>
<span data-ttu-id="b992d-171">Microsoft Defender ATP-query's werken net zo, tenzij ze naar de `DeviceAlertEvents` tabel verwijzen.</span><span class="sxs-lookup"><span data-stu-id="b992d-171">Microsoft Defender ATP queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="b992d-172">Als u deze query's wilt gebruiken in Microsoft Threat Protection, past u de volgende wijzigingen aan:</span><span class="sxs-lookup"><span data-stu-id="b992d-172">To use these queries in Microsoft Threat Protection, apply these changes:</span></span>

- <span data-ttu-id="b992d-173">Vervangen `DeviceAlertEvents` door `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="b992d-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="b992d-174">Neem deel aan de `AlertInfo` tabellen en de `AlertEvidence` tabellen `AlertId` om equivalente gegevens te vinden.</span><span class="sxs-lookup"><span data-stu-id="b992d-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="b992d-175">Oorspronkelijke query</span><span class="sxs-lookup"><span data-stu-id="b992d-175">Original query</span></span>
<span data-ttu-id="b992d-176">De volgende query wordt `DeviceAlertEvents` in Microsoft Defender ATP gebruikt om de gewenste waarschuwingen _powershell.exe_te ontvangen:</span><span class="sxs-lookup"><span data-stu-id="b992d-176">The following query uses `DeviceAlertEvents` in Microsoft Defender ATP to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="b992d-177">Gewijzigde query</span><span class="sxs-lookup"><span data-stu-id="b992d-177">Modified query</span></span>
<span data-ttu-id="b992d-178">De volgende query is aangepast voor gebruik in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="b992d-178">The following query has been adjusted for use in Microsoft Threat Protection.</span></span> <span data-ttu-id="b992d-179">In plaats van de bestandsnaam rechtstreeks van `DeviceAlertEvents` te controleren, wordt `AlertEvidence` de bestandsnaam in die tabel samengevoegd en gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="b992d-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="b992d-180">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b992d-180">Related topics</span></span>
- [<span data-ttu-id="b992d-181">Microsoft Threat Protection inschakelen</span><span class="sxs-lookup"><span data-stu-id="b992d-181">Turn on Microsoft Threat Protection</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b992d-182">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b992d-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b992d-183">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b992d-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b992d-184">Geavanceerde jacht in Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b992d-184">Advanced hunting in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)