---
title: Geavanceerde zoekquery's migreren van Microsoft Defender for Endpoint
description: Informatie over het aanpassen van uw query's van Microsoft Defender voor eindpunten, zodat u deze kunt gebruiken in Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, microsoft defender atp, mdatp, search, query, telemetry, custom detections, schema, kusto, microsoft 365, mapping
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094805"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="b04e6-104">Geavanceerde zoekquery's migreren van Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b04e6-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b04e6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b04e6-105">**Applies to:**</span></span>
- <span data-ttu-id="b04e6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b04e6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b04e6-107">Verplaats uw geavanceerde zoekwerkstromen van Microsoft Defender for Endpoint om proactief te zoeken naar bedreigingen met behulp van een bredere set gegevens.</span><span class="sxs-lookup"><span data-stu-id="b04e6-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="b04e6-108">In Microsoft 365 Defender krijgt u toegang tot gegevens van andere beveiligingsoplossingen van Microsoft 365, waaronder:</span><span class="sxs-lookup"><span data-stu-id="b04e6-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="b04e6-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b04e6-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="b04e6-110">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b04e6-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="b04e6-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b04e6-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="b04e6-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="b04e6-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="b04e6-113">De meeste klanten van Microsoft Defender voor eindpunten kunnen [Microsoft 365 Defender](prerequisites.md#licensing-requirements)zonder extra licenties gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b04e6-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="b04e6-114">Schakel [Microsoft 365 Defender](mtp-enable.md)in om te beginnen met de overgang van geavanceerde zoekwerkstromen van Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b04e6-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="b04e6-115">U kunt overstappen zonder dat dit van invloed is op uw bestaande Defender voor eindpunt-werkstromen.</span><span class="sxs-lookup"><span data-stu-id="b04e6-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="b04e6-116">Opgeslagen query's blijven intact en aangepaste detectieregels blijven worden uitgevoerd en waarschuwingen worden gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="b04e6-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="b04e6-117">Ze zijn echter wel zichtbaar in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b04e6-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="b04e6-118">Alleen schematabellen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b04e6-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="b04e6-119">Het [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) biedt aanvullende tabellen met gegevens uit diverse Microsoft 365-beveiligingsoplossingen.</span><span class="sxs-lookup"><span data-stu-id="b04e6-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="b04e6-120">De volgende tabellen zijn alleen beschikbaar in Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="b04e6-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="b04e6-121">Tabelnaam</span><span class="sxs-lookup"><span data-stu-id="b04e6-121">Table name</span></span> | <span data-ttu-id="b04e6-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b04e6-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="b04e6-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="b04e6-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="b04e6-124">Bestanden, IP-adressen, URL's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="b04e6-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="b04e6-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="b04e6-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="b04e6-126">Waarschuwingen van Microsoft Defender voor eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App-beveiliging en Microsoft Defender voor identiteit, inclusief ernstgegevens en bedreigingscategorieën</span><span class="sxs-lookup"><span data-stu-id="b04e6-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="b04e6-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="b04e6-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="b04e6-128">Activiteiten in verband met bestanden in cloud-apps en -services</span><span class="sxs-lookup"><span data-stu-id="b04e6-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="b04e6-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="b04e6-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="b04e6-130">Informatie over bestanden die zijn bijgevoegd bij e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="b04e6-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="b04e6-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="b04e6-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="b04e6-132">E-mailgebeurtenissen van Microsoft 365, inclusief bezorging van e-mail en blokkeren van gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="b04e6-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="b04e6-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="b04e6-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="b04e6-134">Beveiligingsgebeurtenissen na bezorging, nadat Microsoft 365 de e-mailberichten heeft bezorgd bij het postvak van de geadresseerde</span><span class="sxs-lookup"><span data-stu-id="b04e6-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="b04e6-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="b04e6-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="b04e6-136">Informatie over URL's in e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="b04e6-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="b04e6-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="b04e6-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="b04e6-138">Gebeurtenissen waarbij een on-premises domeincontroller Active Directory (AD) wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b04e6-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="b04e6-139">Deze tabel beslaat een bereik van identiteitsgerelateerde gebeurtenissen en systeemgebeurtenissen op de domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="b04e6-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="b04e6-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="b04e6-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="b04e6-141">Accountgegevens uit verschillende bronnen, waaronder Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b04e6-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="b04e6-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="b04e6-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="b04e6-143">Verificatiegebeurtenissen in Active Directory en Microsoft-onlineservices</span><span class="sxs-lookup"><span data-stu-id="b04e6-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="b04e6-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="b04e6-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="b04e6-145">Query's voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen</span><span class="sxs-lookup"><span data-stu-id="b04e6-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="b04e6-146">Map DeviceAlertEvents table</span><span class="sxs-lookup"><span data-stu-id="b04e6-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="b04e6-147">De tabel in het schema Microsoft Defender for Endpoint wordt vervangen door de `AlertInfo` `AlertEvidence` `DeviceAlertEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="b04e6-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="b04e6-148">Naast gegevens over apparaatwaarschuwingen bevatten deze twee tabellen gegevens over waarschuwingen voor identiteiten, apps en e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="b04e6-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="b04e6-149">Gebruik de volgende tabel om te controleren hoe `DeviceAlertEvents` kolommen worden toe te staan aan kolommen in de `AlertInfo` `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="b04e6-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="b04e6-150">Naast de kolommen uit de volgende tabel bevat de tabel vele andere kolommen die een beter beeld geven van `AlertEvidence` waarschuwingen uit verschillende bronnen.</span><span class="sxs-lookup"><span data-stu-id="b04e6-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="b04e6-151">Alle kolommen voor AlertEvidence bekijken</span><span class="sxs-lookup"><span data-stu-id="b04e6-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="b04e6-152">DeviceAlertEvents column</span><span class="sxs-lookup"><span data-stu-id="b04e6-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="b04e6-153">Waar vind ik dezelfde gegevens in Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="b04e6-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="b04e6-154">`AlertInfo` en  `AlertEvidence` tabellen</span><span class="sxs-lookup"><span data-stu-id="b04e6-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="b04e6-155">`AlertInfo` en  `AlertEvidence` tabellen</span><span class="sxs-lookup"><span data-stu-id="b04e6-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="b04e6-156">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b04e6-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="b04e6-157">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b04e6-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="b04e6-158">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="b04e6-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="b04e6-159">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="b04e6-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="b04e6-160">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="b04e6-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="b04e6-161">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b04e6-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="b04e6-162">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b04e6-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="b04e6-163">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b04e6-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="b04e6-164">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b04e6-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="b04e6-165">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="b04e6-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="b04e6-166">Deze kolom wordt meestal gebruikt in Microsoft Defender voor eindpunt om gerelateerde records in andere tabellen te zoeken.</span><span class="sxs-lookup"><span data-stu-id="b04e6-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="b04e6-167">In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel `AlertEvidence` halen.</span><span class="sxs-lookup"><span data-stu-id="b04e6-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="b04e6-168">Deze kolom wordt meestal gebruikt in Microsoft Defender voor het eindpunt voor aanvullende gebeurtenisgegevens in andere tabellen.</span><span class="sxs-lookup"><span data-stu-id="b04e6-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="b04e6-169">In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel `AlertEvidence` halen.</span><span class="sxs-lookup"><span data-stu-id="b04e6-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="b04e6-170">Bestaande Microsoft Defender voor eindpuntquery's aanpassen</span><span class="sxs-lookup"><span data-stu-id="b04e6-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="b04e6-171">Microsoft Defender voor eindpuntquery's werkt zoals ze zijn, tenzij ze naar de tabel `DeviceAlertEvents` verwijzen.</span><span class="sxs-lookup"><span data-stu-id="b04e6-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="b04e6-172">Als u deze query's wilt gebruiken in Microsoft 365 Defender, moet u deze wijzigingen toepassen:</span><span class="sxs-lookup"><span data-stu-id="b04e6-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="b04e6-173">Vervangen `DeviceAlertEvents` door `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="b04e6-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="b04e6-174">Join the `AlertInfo` and the tables on to get equivalent `AlertEvidence` `AlertId` data.</span><span class="sxs-lookup"><span data-stu-id="b04e6-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="b04e6-175">Oorspronkelijke query</span><span class="sxs-lookup"><span data-stu-id="b04e6-175">Original query</span></span>
<span data-ttu-id="b04e6-176">De volgende query gebruikt `DeviceAlertEvents` Microsoft Defender for Endpoint __ om de waarschuwingen te ontvangen die betrekking hebben oppowershell.exe:</span><span class="sxs-lookup"><span data-stu-id="b04e6-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="b04e6-177">Aangepaste query</span><span class="sxs-lookup"><span data-stu-id="b04e6-177">Modified query</span></span>
<span data-ttu-id="b04e6-178">De volgende query is aangepast voor gebruik in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b04e6-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="b04e6-179">In plaats van de bestandsnaam rechtstreeks te controleren, wordt de naam van het bestand in de tabel toegevoegd en `DeviceAlertEvents` `AlertEvidence` gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="b04e6-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```



## <a name="see-also"></a><span data-ttu-id="b04e6-180">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b04e6-180">See also</span></span>
- [<span data-ttu-id="b04e6-181">Microsoft 365 Defender in te zetten</span><span class="sxs-lookup"><span data-stu-id="b04e6-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b04e6-182">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b04e6-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b04e6-183">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b04e6-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b04e6-184">Geavanceerd zoeken in Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="b04e6-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)