---
title: Geavanceerde zoekquery's migreren van Microsoft Defender voor Eindpunt
description: Meer informatie over het aanpassen van uw Microsoft Defender voor eindpuntquery's, zodat u deze kunt gebruiken in Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, Microsoft Defender for Endpoint, search, query, telemetry, custom detections, schema, kusto, mapping
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ba6f84f9f08d0635dab6ac65eaa697b8e0e73df7
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470686"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="1106f-104">Geavanceerde zoekquery's migreren van Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1106f-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1106f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1106f-105">**Applies to:**</span></span>
- <span data-ttu-id="1106f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1106f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1106f-107">Verplaats uw geavanceerde zoekwerkstromen van Microsoft Defender voor Eindpunt om proactief te zoeken naar bedreigingen met een bredere set gegevens.</span><span class="sxs-lookup"><span data-stu-id="1106f-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="1106f-108">In Microsoft 365 Defender krijgt u toegang tot gegevens van andere Microsoft 365 beveiligingsoplossingen, zoals:</span><span class="sxs-lookup"><span data-stu-id="1106f-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="1106f-109">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1106f-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="1106f-110">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1106f-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="1106f-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1106f-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="1106f-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="1106f-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="1106f-113">De meeste Klanten van Microsoft Defender voor Eindpunten kunnen [Microsoft 365 Defender gebruiken zonder extra licenties.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="1106f-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="1106f-114">Als u wilt beginnen met het overstappen van uw geavanceerde werkstromen voor jagen vanuit Defender voor eindpunt, [schakelt](m365d-enable.md)u Microsoft 365 Defender in.</span><span class="sxs-lookup"><span data-stu-id="1106f-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="1106f-115">U kunt overstappen zonder dat dit van invloed is op uw bestaande Defender voor Eindpunt-werkstromen.</span><span class="sxs-lookup"><span data-stu-id="1106f-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="1106f-116">Opgeslagen query's blijven intact en aangepaste detectieregels blijven worden uitgevoerd en waarschuwingen worden gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="1106f-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="1106f-117">Ze zijn echter zichtbaar in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1106f-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="1106f-118">Alleen tabellen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1106f-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="1106f-119">Het [geavanceerde Microsoft 365 Defender biedt](advanced-hunting-schema-tables.md) extra tabellen met gegevens uit verschillende Microsoft 365 beveiligingsoplossingen.</span><span class="sxs-lookup"><span data-stu-id="1106f-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="1106f-120">De volgende tabellen zijn alleen beschikbaar in Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="1106f-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="1106f-121">Tabelnaam</span><span class="sxs-lookup"><span data-stu-id="1106f-121">Table name</span></span> | <span data-ttu-id="1106f-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="1106f-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="1106f-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="1106f-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="1106f-124">Bestanden, IP-adressen, URL's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="1106f-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="1106f-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="1106f-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="1106f-126">Waarschuwingen van Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App Security en Microsoft Defender voor identiteit, inclusief ernstsinformatie en bedreigingscategorieën</span><span class="sxs-lookup"><span data-stu-id="1106f-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="1106f-127">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="1106f-127">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="1106f-128">Informatie over bestanden die zijn gekoppeld aan e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="1106f-128">Information about files attached to emails</span></span> |
| [<span data-ttu-id="1106f-129">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="1106f-129">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="1106f-130">Microsoft 365 e-mailgebeurtenissen, waaronder e-mailbezorging en het blokkeren van gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="1106f-130">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="1106f-131">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="1106f-131">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="1106f-132">Beveiligingsgebeurtenissen die zich voordoen na de bezorging, nadat Microsoft 365 de e-mailberichten heeft bezorgd bij het postvak van de geadresseerde</span><span class="sxs-lookup"><span data-stu-id="1106f-132">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="1106f-133">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="1106f-133">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="1106f-134">Informatie over URL's in e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="1106f-134">Information about URLs on emails</span></span> |
| [<span data-ttu-id="1106f-135">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="1106f-135">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="1106f-136">Gebeurtenissen met een on-premises domeincontroller met Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="1106f-136">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="1106f-137">Deze tabel bestrijkt een reeks identiteitsgerelateerde gebeurtenissen en systeemgebeurtenissen op de domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="1106f-137">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="1106f-138">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="1106f-138">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="1106f-139">Accountgegevens uit verschillende bronnen, waaronder Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1106f-139">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="1106f-140">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="1106f-140">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="1106f-141">Verificatiegebeurtenissen in Active Directory- en Microsoft-onlineservices</span><span class="sxs-lookup"><span data-stu-id="1106f-141">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="1106f-142">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="1106f-142">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="1106f-143">Query's voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen</span><span class="sxs-lookup"><span data-stu-id="1106f-143">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="1106f-144">Query's en aangepaste detecties die schematabellen gebruiken die alleen beschikbaar zijn in Microsoft 365 Defender kunnen alleen worden weergegeven in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1106f-144">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="1106f-145">Map DeviceAlertEvents table</span><span class="sxs-lookup"><span data-stu-id="1106f-145">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="1106f-146">De `AlertInfo` en tabellen vervangen de tabel in het Microsoft Defender for `AlertEvidence` `DeviceAlertEvents` Endpoint-schema.</span><span class="sxs-lookup"><span data-stu-id="1106f-146">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="1106f-147">Naast gegevens over apparaatwaarschuwingen bevatten deze twee tabellen gegevens over waarschuwingen voor identiteiten, apps en e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="1106f-147">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="1106f-148">Gebruik de volgende tabel om te controleren hoe `DeviceAlertEvents` kolommen worden toe te schrijven aan kolommen in de en `AlertInfo` `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="1106f-148">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="1106f-149">Naast de kolommen in de volgende tabel bevat de tabel veel andere kolommen die een meer holistisch beeld geven van `AlertEvidence` waarschuwingen uit verschillende bronnen.</span><span class="sxs-lookup"><span data-stu-id="1106f-149">In addition to the columns in the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="1106f-150">Alle kolommen van AlertEvidence bekijken</span><span class="sxs-lookup"><span data-stu-id="1106f-150">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="1106f-151">Kolom DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="1106f-151">DeviceAlertEvents column</span></span> | <span data-ttu-id="1106f-152">Waar vindt u dezelfde gegevens in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1106f-152">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="1106f-153">`AlertInfo` en  `AlertEvidence` tabellen</span><span class="sxs-lookup"><span data-stu-id="1106f-153">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="1106f-154">`AlertInfo` en  `AlertEvidence` tabellen</span><span class="sxs-lookup"><span data-stu-id="1106f-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="1106f-155">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="1106f-155">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="1106f-156">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="1106f-156">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="1106f-157">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="1106f-157">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="1106f-158">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="1106f-158">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="1106f-159">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="1106f-159">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="1106f-160">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="1106f-160">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="1106f-161">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="1106f-161">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="1106f-162">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="1106f-162">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="1106f-163">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="1106f-163">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="1106f-164">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="1106f-164">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="1106f-165">Deze kolom wordt meestal gebruikt in Microsoft Defender voor Eindpunt om gerelateerde records in andere tabellen te zoeken.</span><span class="sxs-lookup"><span data-stu-id="1106f-165">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="1106f-166">In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel `AlertEvidence` halen.</span><span class="sxs-lookup"><span data-stu-id="1106f-166">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="1106f-167">Deze kolom wordt meestal gebruikt in Microsoft Defender voor Eindpunt voor aanvullende gebeurtenisgegevens in andere tabellen.</span><span class="sxs-lookup"><span data-stu-id="1106f-167">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="1106f-168">In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel `AlertEvidence` halen.</span><span class="sxs-lookup"><span data-stu-id="1106f-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="1106f-169">Bestaande Microsoft Defender voor eindpuntquery's aanpassen</span><span class="sxs-lookup"><span data-stu-id="1106f-169">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="1106f-170">Microsoft Defender voor eindpuntquery's werken zoals ze zijn, tenzij ze verwijzen naar de `DeviceAlertEvents` tabel.</span><span class="sxs-lookup"><span data-stu-id="1106f-170">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="1106f-171">Als u deze query's wilt gebruiken in Microsoft 365 Defender, moet u de volgende wijzigingen toepassen:</span><span class="sxs-lookup"><span data-stu-id="1106f-171">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="1106f-172">Vervangen `DeviceAlertEvents` door `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="1106f-172">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="1106f-173">Sluit u `AlertInfo` aan bij de tabellen en voeg deze toe om `AlertEvidence` `AlertId` equivalente gegevens te krijgen.</span><span class="sxs-lookup"><span data-stu-id="1106f-173">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="1106f-174">Oorspronkelijke query</span><span class="sxs-lookup"><span data-stu-id="1106f-174">Original query</span></span>
<span data-ttu-id="1106f-175">De volgende query wordt gebruikt in Microsoft Defender voor Eindpunt om de waarschuwingen te `DeviceAlertEvents` krijgen die betrekking hebben op _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="1106f-175">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="1106f-176">Gewijzigde query</span><span class="sxs-lookup"><span data-stu-id="1106f-176">Modified query</span></span>
<span data-ttu-id="1106f-177">De volgende query is aangepast voor gebruik in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1106f-177">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="1106f-178">In plaats van de bestandsnaam rechtstreeks vandaan te controleren, wordt de bestandsnaam in die tabel toegevoegd en gecontroleerd `DeviceAlertEvents` `AlertEvidence` op de bestandsnaam.</span><span class="sxs-lookup"><span data-stu-id="1106f-178">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="1106f-179">Aangepaste detectieregels migreren</span><span class="sxs-lookup"><span data-stu-id="1106f-179">Migrate custom detection rules</span></span>

<span data-ttu-id="1106f-180">Wanneer microsoft Defender voor eindpuntregels worden bewerkt op Microsoft 365 Defender, blijven ze werken zoals voorheen als de resulterende query alleen naar apparaattabellen kijkt.</span><span class="sxs-lookup"><span data-stu-id="1106f-180">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="1106f-181">Waarschuwingen die worden gegenereerd door aangepaste detectieregels die alleen apparaattabellen bevragen, blijven bijvoorbeeld bezorgd bij uw SIEM en genereren e-mailmeldingen, afhankelijk van hoe u deze hebt geconfigureerd in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="1106f-181">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="1106f-182">Bestaande onderdrukkingsregels in Defender voor Eindpunt blijven ook van toepassing.</span><span class="sxs-lookup"><span data-stu-id="1106f-182">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="1106f-183">Nadat u een Defender voor Eindpunt-regel hebt bewerkt, zodat identiteits- en e-mailtabellen worden opgevraagd, die alleen beschikbaar zijn in Microsoft 365 Defender, wordt de regel automatisch verplaatst naar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1106f-183">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="1106f-184">Waarschuwingen gegenereerd door de gemigreerde regel:</span><span class="sxs-lookup"><span data-stu-id="1106f-184">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="1106f-185">Zijn niet meer zichtbaar in de Defender for Endpoint-portal (Microsoft Defender-beveiligingscentrum)</span><span class="sxs-lookup"><span data-stu-id="1106f-185">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="1106f-186">Stop met leveren aan uw SIEM of genereer e-mailmeldingen.</span><span class="sxs-lookup"><span data-stu-id="1106f-186">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="1106f-187">Als u deze wijziging wilt aanpassen, configureert u meldingen via Microsoft 365 Defender om de waarschuwingen te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="1106f-187">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="1106f-188">U kunt de Defender [MICROSOFT 365 gebruiken om](api-incident.md) meldingen te ontvangen voor waarschuwingen voor klantdetectie of gerelateerde incidenten.</span><span class="sxs-lookup"><span data-stu-id="1106f-188">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="1106f-189">Wordt niet onderdrukt door microsoft Defender voor endpoint-onderdrukkingsregels.</span><span class="sxs-lookup"><span data-stu-id="1106f-189">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="1106f-190">Als u wilt voorkomen dat waarschuwingen worden gegenereerd voor bepaalde gebruikers, apparaten of postvakken, wijzigt u de bijbehorende query's om deze entiteiten expliciet uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="1106f-190">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="1106f-191">Als u een regel op deze manier bewerkt, wordt u gevraagd om bevestiging voordat dergelijke wijzigingen worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="1106f-191">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="1106f-192">Nieuwe waarschuwingen die worden gegenereerd door aangepaste detectieregels in Microsoft 365 Defender-portal, worden weergegeven op een waarschuwingspagina met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="1106f-192">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="1106f-193">Waarschuwingstitel en beschrijving</span><span class="sxs-lookup"><span data-stu-id="1106f-193">Alert title and description</span></span> 
- <span data-ttu-id="1106f-194">Beïnvloede activa</span><span class="sxs-lookup"><span data-stu-id="1106f-194">Impacted assets</span></span>
- <span data-ttu-id="1106f-195">Acties die zijn ondernomen in reactie op de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="1106f-195">Actions taken in response to the alert</span></span>
- <span data-ttu-id="1106f-196">Queryresultaten die de waarschuwing hebben geactiveerd</span><span class="sxs-lookup"><span data-stu-id="1106f-196">Query results that triggered the alert</span></span> 
- <span data-ttu-id="1106f-197">Informatie over de aangepaste detectieregel</span><span class="sxs-lookup"><span data-stu-id="1106f-197">Information on the custom detection rule</span></span> 
 
> [!div class="mx-imgBorder"]
> <span data-ttu-id="1106f-198">![Afbeelding van nieuwe waarschuwingspagina](../../media/new-alert-page.png)</span><span class="sxs-lookup"><span data-stu-id="1106f-198">![Image of new alert page](../../media/new-alert-page.png)</span></span>

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="1106f-199">Query's schrijven zonder DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="1106f-199">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="1106f-200">In het Microsoft 365 Defender-schema worden de tabellen en tabellen verstrekt voor de diverse set informatie die bij `AlertInfo` waarschuwingen van verschillende bronnen `AlertEvidence` past.</span><span class="sxs-lookup"><span data-stu-id="1106f-200">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="1106f-201">Als u dezelfde waarschuwingsgegevens wilt ontvangen die u hebt gebruikt om uit de tabel in het Schema van Microsoft Defender voor eindpunten te komen, filtert u de tabel op en voegt u vervolgens elke unieke id toe aan de tabel, die gedetailleerde gebeurtenis- en entiteitsgegevens `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` bevat.</span><span class="sxs-lookup"><span data-stu-id="1106f-201">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="1106f-202">Zie de voorbeeldquery hieronder:</span><span class="sxs-lookup"><span data-stu-id="1106f-202">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="1106f-203">Deze query levert veel meer kolommen op dan `DeviceAlertEvents` in het Schema van Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="1106f-203">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="1106f-204">Als u de resultaten beheersbaar wilt houden, `project` gebruikt u alleen de kolommen waarin u geïnteresseerd bent.</span><span class="sxs-lookup"><span data-stu-id="1106f-204">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="1106f-205">In het onderstaande voorbeeld ziet u kolommen waarin u mogelijk geïnteresseerd bent wanneer tijdens het onderzoek PowerShell-activiteit is gedetecteerd:</span><span class="sxs-lookup"><span data-stu-id="1106f-205">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="1106f-206">Als u wilt filteren op specifieke entiteiten die betrokken zijn bij de waarschuwingen, kunt u dit doen door het entiteitstype in op te geven en de waarde op te geven die u `EntityType` wilt filteren.</span><span class="sxs-lookup"><span data-stu-id="1106f-206">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="1106f-207">In het volgende voorbeeld wordt naar een specifiek IP-adres op zoek:</span><span class="sxs-lookup"><span data-stu-id="1106f-207">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="1106f-208">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1106f-208">See also</span></span>
- [<span data-ttu-id="1106f-209">Microsoft 365 Defender inschakelen</span><span class="sxs-lookup"><span data-stu-id="1106f-209">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1106f-210">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="1106f-210">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1106f-211">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="1106f-211">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1106f-212">Advanced hunting in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1106f-212">Advanced hunting in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)