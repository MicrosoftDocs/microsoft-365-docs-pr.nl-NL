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
ms.openlocfilehash: 4d29f4f3df3d65ad72a19f059763523d7f7cba31
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597001"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="31fc8-104">Geavanceerde zoekquery's migreren van Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="31fc8-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="31fc8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="31fc8-105">**Applies to:**</span></span>
- <span data-ttu-id="31fc8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31fc8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="31fc8-107">Verplaats uw geavanceerde zoekwerkstromen van Microsoft Defender for Endpoint om proactief te zoeken naar bedreigingen met behulp van een bredere set gegevens.</span><span class="sxs-lookup"><span data-stu-id="31fc8-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="31fc8-108">In Microsoft 365 Defender krijgt u toegang tot gegevens van andere beveiligingsoplossingen van Microsoft 365, waaronder:</span><span class="sxs-lookup"><span data-stu-id="31fc8-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="31fc8-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="31fc8-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="31fc8-110">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="31fc8-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="31fc8-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="31fc8-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="31fc8-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="31fc8-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="31fc8-113">De meeste klanten van Microsoft Defender voor eindpunten kunnen [Microsoft 365 Defender](prerequisites.md#licensing-requirements)zonder extra licenties gebruiken.</span><span class="sxs-lookup"><span data-stu-id="31fc8-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="31fc8-114">Schakel [Microsoft 365 Defender](mtp-enable.md)in om te beginnen met de overgang van geavanceerde zoekwerkstromen van Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="31fc8-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="31fc8-115">U kunt overstappen zonder dat dit van invloed is op uw bestaande Defender voor eindpunt-werkstromen.</span><span class="sxs-lookup"><span data-stu-id="31fc8-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="31fc8-116">Opgeslagen query's blijven intact en aangepaste detectieregels blijven worden uitgevoerd en waarschuwingen worden gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="31fc8-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="31fc8-117">Ze zijn echter wel zichtbaar in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="31fc8-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="31fc8-118">Alleen schematabellen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31fc8-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="31fc8-119">Het [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) biedt aanvullende tabellen met gegevens uit diverse Microsoft 365-beveiligingsoplossingen.</span><span class="sxs-lookup"><span data-stu-id="31fc8-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="31fc8-120">De volgende tabellen zijn alleen beschikbaar in Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="31fc8-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="31fc8-121">Tabelnaam</span><span class="sxs-lookup"><span data-stu-id="31fc8-121">Table name</span></span> | <span data-ttu-id="31fc8-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="31fc8-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="31fc8-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="31fc8-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="31fc8-124">Bestanden, IP-adressen, URL's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="31fc8-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="31fc8-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="31fc8-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="31fc8-126">Waarschuwingen van Microsoft Defender voor eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App-beveiliging en Microsoft Defender voor identiteit, inclusief ernstgegevens en bedreigingscategorieën</span><span class="sxs-lookup"><span data-stu-id="31fc8-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="31fc8-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="31fc8-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="31fc8-128">Activiteiten in verband met bestanden in cloud-apps en -services</span><span class="sxs-lookup"><span data-stu-id="31fc8-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="31fc8-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="31fc8-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="31fc8-130">Informatie over bestanden die zijn bijgevoegd bij e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="31fc8-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="31fc8-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="31fc8-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="31fc8-132">E-mailgebeurtenissen van Microsoft 365, inclusief bezorging van e-mail en blokkeren van gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="31fc8-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="31fc8-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="31fc8-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="31fc8-134">Beveiligingsgebeurtenissen na bezorging, nadat Microsoft 365 de e-mailberichten heeft bezorgd bij het postvak van de geadresseerde</span><span class="sxs-lookup"><span data-stu-id="31fc8-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="31fc8-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="31fc8-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="31fc8-136">Informatie over URL's in e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="31fc8-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="31fc8-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="31fc8-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="31fc8-138">Gebeurtenissen waarbij een on-premises domeincontroller Active Directory (AD) wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="31fc8-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="31fc8-139">Deze tabel beslaat een bereik van identiteitsgerelateerde gebeurtenissen en systeemgebeurtenissen op de domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="31fc8-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="31fc8-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="31fc8-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="31fc8-141">Accountgegevens uit verschillende bronnen, waaronder Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="31fc8-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="31fc8-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="31fc8-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="31fc8-143">Verificatiegebeurtenissen in Active Directory en Microsoft-onlineservices</span><span class="sxs-lookup"><span data-stu-id="31fc8-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="31fc8-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="31fc8-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="31fc8-145">Query's voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen</span><span class="sxs-lookup"><span data-stu-id="31fc8-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="31fc8-146">Query's en aangepaste detecties waarin schematabellen worden gebruikt die alleen beschikbaar zijn in Microsoft 365 Defender, kunnen alleen worden weergegeven in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="31fc8-146">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="31fc8-147">Map DeviceAlertEvents table</span><span class="sxs-lookup"><span data-stu-id="31fc8-147">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="31fc8-148">De `AlertInfo` tabel en tabellen vervangen de tabel in het schema van Microsoft Defender for `AlertEvidence` `DeviceAlertEvents` Endpoint.</span><span class="sxs-lookup"><span data-stu-id="31fc8-148">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="31fc8-149">Naast gegevens over apparaatwaarschuwingen bevatten deze twee tabellen gegevens over waarschuwingen voor identiteiten, apps en e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="31fc8-149">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="31fc8-150">Gebruik de volgende tabel om te controleren hoe `DeviceAlertEvents` kolommen worden toe te staan aan kolommen in de `AlertInfo` `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="31fc8-150">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="31fc8-151">Naast de kolommen uit de volgende tabel bevat de tabel vele andere kolommen die een beter beeld geven van `AlertEvidence` waarschuwingen uit verschillende bronnen.</span><span class="sxs-lookup"><span data-stu-id="31fc8-151">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="31fc8-152">Alle kolommen voor AlertEvidence bekijken</span><span class="sxs-lookup"><span data-stu-id="31fc8-152">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="31fc8-153">DeviceAlertEvents column</span><span class="sxs-lookup"><span data-stu-id="31fc8-153">DeviceAlertEvents column</span></span> | <span data-ttu-id="31fc8-154">Waar vind ik dezelfde gegevens in Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="31fc8-154">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="31fc8-155">`AlertInfo` en  `AlertEvidence` tabellen</span><span class="sxs-lookup"><span data-stu-id="31fc8-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="31fc8-156">`AlertInfo` en  `AlertEvidence` tabellen</span><span class="sxs-lookup"><span data-stu-id="31fc8-156">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="31fc8-157">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="31fc8-157">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="31fc8-158">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="31fc8-158">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="31fc8-159">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="31fc8-159">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="31fc8-160">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="31fc8-160">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="31fc8-161">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="31fc8-161">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="31fc8-162">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="31fc8-162">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="31fc8-163">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="31fc8-163">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="31fc8-164">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="31fc8-164">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="31fc8-165">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="31fc8-165">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="31fc8-166">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="31fc8-166">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="31fc8-167">Deze kolom wordt meestal gebruikt in Microsoft Defender voor eindpunt om gerelateerde records te zoeken in andere tabellen.</span><span class="sxs-lookup"><span data-stu-id="31fc8-167">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="31fc8-168">In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel `AlertEvidence` halen.</span><span class="sxs-lookup"><span data-stu-id="31fc8-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="31fc8-169">Deze kolom wordt meestal gebruikt in Microsoft Defender voor het eindpunt voor aanvullende gebeurtenisgegevens in andere tabellen.</span><span class="sxs-lookup"><span data-stu-id="31fc8-169">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="31fc8-170">In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel `AlertEvidence` halen.</span><span class="sxs-lookup"><span data-stu-id="31fc8-170">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="31fc8-171">Bestaande Microsoft Defender voor eindpuntquery's aanpassen</span><span class="sxs-lookup"><span data-stu-id="31fc8-171">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="31fc8-172">Microsoft Defender voor eindpuntquery's werkt zoals ze zijn, tenzij ze naar de tabel `DeviceAlertEvents` verwijzen.</span><span class="sxs-lookup"><span data-stu-id="31fc8-172">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="31fc8-173">Als u deze query's wilt gebruiken in Microsoft 365 Defender, moet u deze wijzigingen toepassen:</span><span class="sxs-lookup"><span data-stu-id="31fc8-173">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="31fc8-174">Vervangen `DeviceAlertEvents` door `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="31fc8-174">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="31fc8-175">Join the `AlertInfo` and the tables on to get equivalent `AlertEvidence` `AlertId` data.</span><span class="sxs-lookup"><span data-stu-id="31fc8-175">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="31fc8-176">Oorspronkelijke query</span><span class="sxs-lookup"><span data-stu-id="31fc8-176">Original query</span></span>
<span data-ttu-id="31fc8-177">De volgende query gebruikt microsoft Defender for Endpoint om de `DeviceAlertEvents` waarschuwingen te ontvangen die betrekking hebben oppowershell.exe: __</span><span class="sxs-lookup"><span data-stu-id="31fc8-177">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="31fc8-178">Aangepaste query</span><span class="sxs-lookup"><span data-stu-id="31fc8-178">Modified query</span></span>
<span data-ttu-id="31fc8-179">De volgende query is aangepast voor gebruik in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="31fc8-179">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="31fc8-180">In plaats van de bestandsnaam rechtstreeks te controleren, wordt de naam van het bestand in de tabel toegevoegd en `DeviceAlertEvents` `AlertEvidence` gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="31fc8-180">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="31fc8-181">Aangepaste detectieregels migreren</span><span class="sxs-lookup"><span data-stu-id="31fc8-181">Migrate custom detection rules</span></span>

<span data-ttu-id="31fc8-182">Wanneer regels van Microsoft Defender voor eindpunt worden bewerkt op Microsoft 365 Defender, blijven ze werken alsof de resulterende query alleen naar apparaattabellen kijkt.</span><span class="sxs-lookup"><span data-stu-id="31fc8-182">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="31fc8-183">Waarschuwingen die worden gegenereerd door aangepaste detectieregels die query's uitvoeren op alleen apparaattabellen, worden bijvoorbeeld nog steeds bezorgd in uw SIEM en genereren e-mailmeldingen, afhankelijk van hoe u deze hebt geconfigureerd in Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="31fc8-183">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="31fc8-184">Bestaande onderdrukkende regels in Defender voor eindpunt blijven ook van toepassing.</span><span class="sxs-lookup"><span data-stu-id="31fc8-184">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="31fc8-185">Zodra u een regel van Defender voor eindpunt bewerkt zodat identiteits- en e-mailtabellen worden opgevraagd, die alleen beschikbaar zijn in Microsoft 365 Defender, wordt de regel automatisch verplaatst naar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="31fc8-185">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="31fc8-186">Waarschuwingen die worden gegenereerd door de gemigreerde regel:</span><span class="sxs-lookup"><span data-stu-id="31fc8-186">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="31fc8-187">Zijn niet meer zichtbaar in de portal Defender for Endpoint (Microsoft Defender-beveiligingscentrum)</span><span class="sxs-lookup"><span data-stu-id="31fc8-187">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="31fc8-188">Stop met afgeleverd te worden in uw SIEM of genereer e-mailmeldingen.</span><span class="sxs-lookup"><span data-stu-id="31fc8-188">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="31fc8-189">U kunt deze wijziging omsdraaien door meldingen via Microsoft 365 Defender zo te configureren dat de waarschuwingen worden ontvangen.</span><span class="sxs-lookup"><span data-stu-id="31fc8-189">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="31fc8-190">U kunt de [Microsoft 365 Defender-API](api-incident.md) gebruiken om meldingen te ontvangen voor waarschuwingen van klantendetectie of verwante incidenten.</span><span class="sxs-lookup"><span data-stu-id="31fc8-190">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="31fc8-191">Wordt niet onderdrukken door de regels voor het onderdrukken van eindpunten van Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="31fc8-191">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="31fc8-192">Als u wilt voorkomen dat waarschuwingen worden gegenereerd voor bepaalde gebruikers, apparaten of postvakken, wijzigt u de bijbehorende query's om deze entiteiten expliciet uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="31fc8-192">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="31fc8-193">Als u een regel op deze manier bewerkt, wordt u om bevestiging gevraagd voordat dergelijke wijzigingen worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="31fc8-193">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="31fc8-194">Nieuwe waarschuwingen die worden gegenereerd door aangepaste detectieregels in de Microsoft 365 Defender-portal, worden weergegeven op een waarschuwingspagina met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="31fc8-194">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="31fc8-195">Naam en beschrijving van waarschuwing</span><span class="sxs-lookup"><span data-stu-id="31fc8-195">Alert title and description</span></span> 
- <span data-ttu-id="31fc8-196">Beïnvloede activa</span><span class="sxs-lookup"><span data-stu-id="31fc8-196">Impacted assets</span></span>
- <span data-ttu-id="31fc8-197">Acties die zijn ondernomen in reactie op de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="31fc8-197">Actions taken in response to the alert</span></span>
- <span data-ttu-id="31fc8-198">Queryresultaten die de waarschuwing hebben geactiveerd</span><span class="sxs-lookup"><span data-stu-id="31fc8-198">Query results that triggered the alert</span></span> 
- <span data-ttu-id="31fc8-199">Informatie over de aangepaste detectieregel</span><span class="sxs-lookup"><span data-stu-id="31fc8-199">Information on the custom detection rule</span></span> 
 
![Afbeelding van de pagina Nieuwe waarschuwing](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="31fc8-201">Query's schrijven zonder DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="31fc8-201">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="31fc8-202">In het Microsoft 365 Defender-schema worden de tabellen en de tabellen verstrekt voor de diverse reeks informatie die bij waarschuwingen `AlertInfo` `AlertEvidence` van verschillende bronnen past.</span><span class="sxs-lookup"><span data-stu-id="31fc8-202">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="31fc8-203">Als u dezelfde waarschuwingsgegevens uit de tabel in het schema Microsoft Defender for Endpoint hebt ontvangen, filtert u de tabel op en voegt u elke unieke id toe aan de tabel, die gedetailleerde informatie over gebeurtenissen en entiteiten `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` biedt.</span><span class="sxs-lookup"><span data-stu-id="31fc8-203">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="31fc8-204">Zie de voorbeeldquery hieronder:</span><span class="sxs-lookup"><span data-stu-id="31fc8-204">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="31fc8-205">Deze query levert veel meer kolommen op dan `DeviceAlertEvents` in het schema van Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="31fc8-205">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="31fc8-206">Gebruik alleen kolommen waarin u geïnteresseerd bent om de resultaten `project` beheersbaar te houden.</span><span class="sxs-lookup"><span data-stu-id="31fc8-206">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="31fc8-207">In het onderstaande voorbeeld ziet u de kolommen waarin u mogelijk geïnteresseerd bent wanneer door het onderzoek PowerShell-activiteit is gedetecteerd:</span><span class="sxs-lookup"><span data-stu-id="31fc8-207">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="31fc8-208">Als u wilt filteren op specifieke entiteiten die betrokken zijn bij de waarschuwingen, kunt u dit doen door het entiteitstype op te geven en de waarde die u wilt `EntityType` filteren.</span><span class="sxs-lookup"><span data-stu-id="31fc8-208">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="31fc8-209">In het volgende voorbeeld wordt naar een specifiek IP-adres zoekt:</span><span class="sxs-lookup"><span data-stu-id="31fc8-209">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="31fc8-210">Zie ook</span><span class="sxs-lookup"><span data-stu-id="31fc8-210">See also</span></span>
- [<span data-ttu-id="31fc8-211">Microsoft 365 Defender in te zetten</span><span class="sxs-lookup"><span data-stu-id="31fc8-211">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="31fc8-212">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="31fc8-212">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="31fc8-213">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="31fc8-213">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="31fc8-214">Geavanceerd zoeken in Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="31fc8-214">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)