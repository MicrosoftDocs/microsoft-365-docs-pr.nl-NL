---
title: Geavanceerde jagers-query's migreren van Microsoft Defender voor eindpunt
description: Meer informatie over het aanpassen van uw Microsoft Defender voor eindpunt query's, zodat u deze kunt gebruiken in Microsoft 365 Defender
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
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846854"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="c1a4a-104">Geavanceerde jagers-query's migreren van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="c1a4a-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c1a4a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c1a4a-105">**Applies to:**</span></span>
- <span data-ttu-id="c1a4a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1a4a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c1a4a-107">U kunt uw werkstromen voor Geavanceerd zoeken van Microsoft Defender voor het eindpunt verplaatsen naar een meer ervaring met een uitgebreidere set gegevens.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="c1a4a-108">In Microsoft 365 Defender krijgt u toegang tot gegevens vanuit andere beveiligingsoplossingen van Microsoft 365, waaronder:</span><span class="sxs-lookup"><span data-stu-id="c1a4a-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="c1a4a-109">Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="c1a4a-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="c1a4a-110">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c1a4a-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="c1a4a-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c1a4a-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="c1a4a-112">Microsoft Defender voor identiteit</span><span class="sxs-lookup"><span data-stu-id="c1a4a-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="c1a4a-113">De meeste Microsoft Defender voor eindpunten van klanten kunnen [Microsoft 365 Defender gebruiken zonder extra licenties](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="c1a4a-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="c1a4a-114">Als u wilt beginnen met het overstappen van uw Advanced jacht-werkstromen vanuit Defender voor eindpunten, [schakelt u Microsoft 365 Defender in](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="c1a4a-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="c1a4a-115">U kunt overstappen zonder dat dit van invloed is op de bestaande Defender voor eindpunten.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="c1a4a-116">Opgeslagen query's blijven behouden en aangepaste detectieregels blijven doorgaan met het uitvoeren en genereren van waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="c1a4a-117">Deze worden echter wel weergegeven in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="c1a4a-118">Schema tabellen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1a4a-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="c1a4a-119">Het [Microsoft 365 Defender Advanced jacht-schema](advanced-hunting-schema-tables.md) biedt extra tabellen met gegevens van diverse beveiligingsoplossingen van microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="c1a4a-120">De volgende tabellen zijn alleen beschikbaar in Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="c1a4a-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="c1a4a-121">Tabelnaam</span><span class="sxs-lookup"><span data-stu-id="c1a4a-121">Table name</span></span> | <span data-ttu-id="c1a4a-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c1a4a-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="c1a4a-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="c1a4a-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="c1a4a-124">Bestanden, IP-adressen, Url's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="c1a4a-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="c1a4a-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="c1a4a-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="c1a4a-126">Waarschuwingen van Microsoft Defender for endpoints, Microsoft Defender for Office 365, Microsoft Cloud app Security en Microsoft Defender for Identity, waaronder informatie over de ernst en bedreigings Categorieën</span><span class="sxs-lookup"><span data-stu-id="c1a4a-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="c1a4a-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="c1a4a-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="c1a4a-128">Activiteiten met betrekking tot bestanden in Cloud-apps en-services</span><span class="sxs-lookup"><span data-stu-id="c1a4a-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="c1a4a-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="c1a4a-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="c1a4a-130">Informatie over bestanden die zijn gekoppeld aan e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="c1a4a-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="c1a4a-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="c1a4a-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="c1a4a-132">Microsoft 365-e-mail gebeurtenissen, waaronder e-mail bezorging en blokkering van gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="c1a4a-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="c1a4a-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="c1a4a-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="c1a4a-134">Beveiligingsgebeurtenissen die na na ontvangst plaatsvinden, nadat Microsoft 365 de e-mail heeft bezorgd in het postvak van de geadresseerde</span><span class="sxs-lookup"><span data-stu-id="c1a4a-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="c1a4a-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="c1a4a-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="c1a4a-136">Info over Url's voor e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="c1a4a-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="c1a4a-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="c1a4a-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="c1a4a-138">Gebeurtenissen waarbij een on-premises domeincontroller met Active Directory (AD) wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="c1a4a-139">Deze tabel behandelt een bereik van gebeurtenissen die betrekking hebben op de identiteit en de systeemgebeurtenissen op de domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="c1a4a-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="c1a4a-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="c1a4a-141">Account gegevens van diverse bronnen, waaronder Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c1a4a-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="c1a4a-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="c1a4a-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="c1a4a-143">Verificatiegebeurtenissen in Active Directory en Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="c1a4a-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="c1a4a-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="c1a4a-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="c1a4a-145">Query's voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen</span><span class="sxs-lookup"><span data-stu-id="c1a4a-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="c1a4a-146">Kaart DeviceAlertEvents tabel</span><span class="sxs-lookup"><span data-stu-id="c1a4a-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="c1a4a-147">`AlertInfo`Met de `AlertEvidence` tabellen en worden de tabellen `DeviceAlertEvents` in het Microsoft Defender voor eindpunt schema vervangen.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="c1a4a-148">Naast gegevens over waarschuwingen voor apparaten, bevatten deze twee tabellen gegevens over waarschuwingen voor identiteiten, apps en e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="c1a4a-149">Gebruik de volgende tabel om te controleren hoe `DeviceAlertEvents` kolommen zijn toegewezen aan kolommen in de `AlertInfo` `AlertEvidence` tabellen en.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="c1a4a-150">Naast de kolommen de volgende tabel `AlertEvidence` bevat de tabel veel andere kolommen die een meer holistische afbeelding van waarschuwingen van diverse bronnen bieden.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="c1a4a-151">Alle AlertEvidence kolommen weergeven</span><span class="sxs-lookup"><span data-stu-id="c1a4a-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="c1a4a-152">Kolom DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="c1a4a-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="c1a4a-153">Waarnaar u dezelfde gegevens kunt vinden in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1a4a-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="c1a4a-154">`AlertInfo` en  `AlertEvidence` tabellen</span><span class="sxs-lookup"><span data-stu-id="c1a4a-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="c1a4a-155">`AlertInfo` en  `AlertEvidence` tabellen</span><span class="sxs-lookup"><span data-stu-id="c1a4a-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="c1a4a-156">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="c1a4a-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="c1a4a-157">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="c1a4a-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="c1a4a-158">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="c1a4a-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="c1a4a-159">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="c1a4a-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="c1a4a-160">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="c1a4a-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="c1a4a-161">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="c1a4a-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="c1a4a-162">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="c1a4a-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="c1a4a-163">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="c1a4a-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="c1a4a-164">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="c1a4a-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="c1a4a-165">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="c1a4a-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="c1a4a-166">Deze kolom wordt meestal in Microsoft Defender voor eindpunt gebruikt om gerelateerde records in andere tabellen te zoeken.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="c1a4a-167">In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel weergeven `AlertEvidence` .</span><span class="sxs-lookup"><span data-stu-id="c1a4a-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="c1a4a-168">Deze kolom wordt meestal gebruikt in Microsoft Defender voor eindpunt voor aanvullende informatie over gebeurtenissen in andere tabellen.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="c1a4a-169">In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel weergeven `AlertEvidence` .</span><span class="sxs-lookup"><span data-stu-id="c1a4a-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="c1a4a-170">Bestaande Microsoft Defender voor eindpunten query's aanpassen</span><span class="sxs-lookup"><span data-stu-id="c1a4a-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="c1a4a-171">Microsoft Defender voor eindpunt query's werken net zo, tenzij ze naar de `DeviceAlertEvents` tabel verwijzen.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="c1a4a-172">Als u deze query's wilt gebruiken in Microsoft 365 Defender, past u de volgende wijzigingen aan:</span><span class="sxs-lookup"><span data-stu-id="c1a4a-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="c1a4a-173">Vervangen `DeviceAlertEvents` door `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="c1a4a-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="c1a4a-174">Neem deel aan de `AlertInfo` tabellen en de `AlertEvidence` tabellen `AlertId` om equivalente gegevens te vinden.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="c1a4a-175">Oorspronkelijke query</span><span class="sxs-lookup"><span data-stu-id="c1a4a-175">Original query</span></span>
<span data-ttu-id="c1a4a-176">De volgende query wordt `DeviceAlertEvents` in Microsoft Defender voor eindpunt gebruikt om de gewenste waarschuwingen _powershell.exe_ te ontvangen:</span><span class="sxs-lookup"><span data-stu-id="c1a4a-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_ :</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="c1a4a-177">Gewijzigde query</span><span class="sxs-lookup"><span data-stu-id="c1a4a-177">Modified query</span></span>
<span data-ttu-id="c1a4a-178">De volgende query is aangepast voor gebruik in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="c1a4a-179">In plaats van de bestandsnaam rechtstreeks van `DeviceAlertEvents` te controleren, wordt `AlertEvidence` de bestandsnaam in die tabel samengevoegd en gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="c1a4a-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="c1a4a-180">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c1a4a-180">Related topics</span></span>
- [<span data-ttu-id="c1a4a-181">Microsoft 365 Defender inschakelen</span><span class="sxs-lookup"><span data-stu-id="c1a4a-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c1a4a-182">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="c1a4a-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c1a4a-183">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="c1a4a-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c1a4a-184">Geavanceerde jacht in Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="c1a4a-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)