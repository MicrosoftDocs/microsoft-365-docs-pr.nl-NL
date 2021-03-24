---
title: Geavanceerde zoekquery's migreren van Microsoft Defender voor Eindpunt
description: Meer informatie over het aanpassen van uw Microsoft Defender voor eindpuntquery's, zodat u ze kunt gebruiken in Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: c0575b5eaf5a4683f86d4a48dd1076fa2c423acf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060418"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="b6d60-104">Geavanceerde zoekquery's migreren van Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b6d60-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b6d60-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b6d60-105">**Applies to:**</span></span>
- <span data-ttu-id="b6d60-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6d60-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b6d60-107">Verplaats uw geavanceerde zoekwerkstromen van Microsoft Defender voor Eindpunt om proactief te zoeken naar bedreigingen met een bredere set gegevens.</span><span class="sxs-lookup"><span data-stu-id="b6d60-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="b6d60-108">In Microsoft 365 Defender krijgt u toegang tot gegevens van andere beveiligingsoplossingen van Microsoft 365, waaronder:</span><span class="sxs-lookup"><span data-stu-id="b6d60-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="b6d60-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b6d60-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="b6d60-110">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b6d60-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="b6d60-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b6d60-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="b6d60-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="b6d60-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="b6d60-113">De meeste Klanten van Microsoft Defender voor eindpunten kunnen [Microsoft 365 Defender gebruiken zonder extra licenties.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="b6d60-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="b6d60-114">Schakel [Microsoft 365 Defender](m365d-enable.md)in om te beginnen met het overstappen van uw geavanceerde werkstromen voor jagen vanuit Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b6d60-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="b6d60-115">U kunt overstappen zonder dat dit van invloed is op uw bestaande Defender voor Eindpunt-werkstromen.</span><span class="sxs-lookup"><span data-stu-id="b6d60-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="b6d60-116">Opgeslagen query's blijven intact en aangepaste detectieregels blijven worden uitgevoerd en waarschuwingen worden gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="b6d60-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="b6d60-117">Ze zijn echter zichtbaar in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b6d60-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="b6d60-118">Alleen schematabellen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6d60-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="b6d60-119">Het geavanceerde zoekschema van [Microsoft 365 Defender](advanced-hunting-schema-tables.md) bevat aanvullende tabellen met gegevens uit verschillende beveiligingsoplossingen van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6d60-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="b6d60-120">De volgende tabellen zijn alleen beschikbaar in Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="b6d60-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="b6d60-121">Tabelnaam</span><span class="sxs-lookup"><span data-stu-id="b6d60-121">Table name</span></span> | <span data-ttu-id="b6d60-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b6d60-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="b6d60-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="b6d60-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="b6d60-124">Bestanden, IP-adressen, URL's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="b6d60-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="b6d60-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="b6d60-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="b6d60-126">Waarschuwingen van Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App Security en Microsoft Defender voor identiteit, inclusief ernstsinformatie en bedreigingscategorieën</span><span class="sxs-lookup"><span data-stu-id="b6d60-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="b6d60-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="b6d60-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="b6d60-128">Bestandsgerelateerde activiteiten in cloud-apps en -services</span><span class="sxs-lookup"><span data-stu-id="b6d60-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="b6d60-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="b6d60-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="b6d60-130">Informatie over bestanden die zijn gekoppeld aan e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="b6d60-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="b6d60-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="b6d60-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="b6d60-132">E-mailgebeurtenissen van Microsoft 365, inclusief e-mailbezorging en het blokkeren van gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="b6d60-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="b6d60-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="b6d60-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="b6d60-134">Beveiligingsgebeurtenissen die zich voordoen na de bezorging, nadat Microsoft 365 de e-mailberichten heeft bezorgd bij het postvak van de geadresseerde</span><span class="sxs-lookup"><span data-stu-id="b6d60-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="b6d60-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="b6d60-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="b6d60-136">Informatie over URL's in e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="b6d60-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="b6d60-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="b6d60-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="b6d60-138">Gebeurtenissen met een on-premises domeincontroller met Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="b6d60-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="b6d60-139">Deze tabel bestrijkt een reeks identiteitsgerelateerde gebeurtenissen en systeemgebeurtenissen op de domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="b6d60-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="b6d60-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="b6d60-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="b6d60-141">Accountgegevens uit verschillende bronnen, waaronder Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b6d60-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="b6d60-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="b6d60-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="b6d60-143">Verificatiegebeurtenissen in Active Directory- en Microsoft-onlineservices</span><span class="sxs-lookup"><span data-stu-id="b6d60-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="b6d60-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="b6d60-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="b6d60-145">Query's voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen</span><span class="sxs-lookup"><span data-stu-id="b6d60-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="b6d60-146">Query's en aangepaste detecties die schematabellen gebruiken die alleen beschikbaar zijn in Microsoft 365 Defender, kunnen alleen worden weergegeven in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b6d60-146">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="b6d60-147">Map DeviceAlertEvents table</span><span class="sxs-lookup"><span data-stu-id="b6d60-147">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="b6d60-148">De `AlertInfo` en tabellen vervangen de tabel in het Microsoft Defender for `AlertEvidence` `DeviceAlertEvents` Endpoint-schema.</span><span class="sxs-lookup"><span data-stu-id="b6d60-148">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="b6d60-149">Naast gegevens over apparaatwaarschuwingen bevatten deze twee tabellen gegevens over waarschuwingen voor identiteiten, apps en e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="b6d60-149">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="b6d60-150">Gebruik de volgende tabel om te controleren hoe `DeviceAlertEvents` kolommen worden toe te schrijven aan kolommen in de en `AlertInfo` `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="b6d60-150">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="b6d60-151">Naast de kolommen in de volgende tabel bevat de tabel veel andere kolommen die een meer holistisch beeld geven van `AlertEvidence` waarschuwingen uit verschillende bronnen.</span><span class="sxs-lookup"><span data-stu-id="b6d60-151">In addition to the columns in the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="b6d60-152">Alle kolommen van AlertEvidence bekijken</span><span class="sxs-lookup"><span data-stu-id="b6d60-152">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="b6d60-153">Kolom DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="b6d60-153">DeviceAlertEvents column</span></span> | <span data-ttu-id="b6d60-154">Waar vindt u dezelfde gegevens in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6d60-154">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="b6d60-155">`AlertInfo` en  `AlertEvidence` tabellen</span><span class="sxs-lookup"><span data-stu-id="b6d60-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="b6d60-156">`AlertInfo` en  `AlertEvidence` tabellen</span><span class="sxs-lookup"><span data-stu-id="b6d60-156">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="b6d60-157">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b6d60-157">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="b6d60-158">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b6d60-158">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="b6d60-159">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="b6d60-159">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="b6d60-160">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="b6d60-160">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="b6d60-161">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="b6d60-161">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="b6d60-162">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b6d60-162">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="b6d60-163">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b6d60-163">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="b6d60-164">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b6d60-164">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="b6d60-165">`AlertEvidence` tabel</span><span class="sxs-lookup"><span data-stu-id="b6d60-165">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="b6d60-166">`AlertInfo` tabel</span><span class="sxs-lookup"><span data-stu-id="b6d60-166">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="b6d60-167">Deze kolom wordt meestal gebruikt in Microsoft Defender voor Eindpunt om gerelateerde records in andere tabellen te zoeken.</span><span class="sxs-lookup"><span data-stu-id="b6d60-167">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="b6d60-168">In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de `AlertEvidence` tabel halen.</span><span class="sxs-lookup"><span data-stu-id="b6d60-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="b6d60-169">Deze kolom wordt meestal gebruikt in Microsoft Defender voor Eindpunt voor aanvullende gebeurtenisgegevens in andere tabellen.</span><span class="sxs-lookup"><span data-stu-id="b6d60-169">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="b6d60-170">In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de `AlertEvidence` tabel halen.</span><span class="sxs-lookup"><span data-stu-id="b6d60-170">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="b6d60-171">Bestaande Microsoft Defender voor eindpuntquery's aanpassen</span><span class="sxs-lookup"><span data-stu-id="b6d60-171">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="b6d60-172">Microsoft Defender voor eindpuntquery's werken zoals ze zijn, tenzij ze verwijzen naar de `DeviceAlertEvents` tabel.</span><span class="sxs-lookup"><span data-stu-id="b6d60-172">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="b6d60-173">Als u deze query's wilt gebruiken in Microsoft 365 Defender, moet u de volgende wijzigingen toepassen:</span><span class="sxs-lookup"><span data-stu-id="b6d60-173">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="b6d60-174">Vervangen `DeviceAlertEvents` door `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="b6d60-174">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="b6d60-175">Sluit u `AlertInfo` aan bij de tabellen en voeg deze toe om `AlertEvidence` `AlertId` equivalente gegevens te krijgen.</span><span class="sxs-lookup"><span data-stu-id="b6d60-175">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="b6d60-176">Oorspronkelijke query</span><span class="sxs-lookup"><span data-stu-id="b6d60-176">Original query</span></span>
<span data-ttu-id="b6d60-177">De volgende query wordt gebruikt in Microsoft Defender voor Eindpunt om de waarschuwingen te `DeviceAlertEvents` krijgen die betrekking hebben op _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="b6d60-177">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="b6d60-178">Gewijzigde query</span><span class="sxs-lookup"><span data-stu-id="b6d60-178">Modified query</span></span>
<span data-ttu-id="b6d60-179">De volgende query is aangepast voor gebruik in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b6d60-179">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="b6d60-180">In plaats van de bestandsnaam rechtstreeks vandaan te controleren, wordt de bestandsnaam in die tabel toegevoegd en gecontroleerd `DeviceAlertEvents` `AlertEvidence` op de bestandsnaam.</span><span class="sxs-lookup"><span data-stu-id="b6d60-180">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="b6d60-181">Aangepaste detectieregels migreren</span><span class="sxs-lookup"><span data-stu-id="b6d60-181">Migrate custom detection rules</span></span>

<span data-ttu-id="b6d60-182">Wanneer microsoft Defender voor eindpuntregels worden bewerkt op Microsoft 365 Defender, blijven ze werken zoals voorheen als de resulterende query alleen naar apparaattabellen kijkt.</span><span class="sxs-lookup"><span data-stu-id="b6d60-182">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="b6d60-183">Waarschuwingen die worden gegenereerd door aangepaste detectieregels die alleen apparaattabellen bevragen, blijven bijvoorbeeld bezorgd bij uw SIEM en genereren e-mailmeldingen, afhankelijk van hoe u deze hebt geconfigureerd in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b6d60-183">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b6d60-184">Bestaande onderdrukkingsregels in Defender voor Eindpunt blijven ook van toepassing.</span><span class="sxs-lookup"><span data-stu-id="b6d60-184">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="b6d60-185">Nadat u een Defender voor Eindpunt-regel hebt bewerkt, zodat identiteits- en e-mailtabellen worden opgevraagd, die alleen beschikbaar zijn in Microsoft 365 Defender, wordt de regel automatisch verplaatst naar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b6d60-185">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="b6d60-186">Waarschuwingen gegenereerd door de gemigreerde regel:</span><span class="sxs-lookup"><span data-stu-id="b6d60-186">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="b6d60-187">Zijn niet meer zichtbaar in de Defender for Endpoint-portal (Microsoft Defender Security Center)</span><span class="sxs-lookup"><span data-stu-id="b6d60-187">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="b6d60-188">Stop met leveren aan uw SIEM of genereer e-mailmeldingen.</span><span class="sxs-lookup"><span data-stu-id="b6d60-188">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="b6d60-189">Als u deze wijziging wilt aanpassen, configureert u meldingen via Microsoft 365 Defender om de waarschuwingen te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="b6d60-189">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="b6d60-190">U kunt de [Microsoft 365 Defender-API gebruiken](api-incident.md) om meldingen te ontvangen voor waarschuwingen voor klantdetectie of verwante incidenten.</span><span class="sxs-lookup"><span data-stu-id="b6d60-190">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="b6d60-191">Wordt niet onderdrukt door microsoft Defender voor endpoint-onderdrukkingsregels.</span><span class="sxs-lookup"><span data-stu-id="b6d60-191">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="b6d60-192">Als u wilt voorkomen dat waarschuwingen worden gegenereerd voor bepaalde gebruikers, apparaten of postvakken, wijzigt u de bijbehorende query's om deze entiteiten expliciet uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="b6d60-192">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="b6d60-193">Als u een regel op deze manier bewerkt, wordt u gevraagd om bevestiging voordat dergelijke wijzigingen worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="b6d60-193">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="b6d60-194">Nieuwe waarschuwingen die worden gegenereerd door aangepaste detectieregels in de Microsoft 365 Defender-portal, worden weergegeven op een waarschuwingspagina met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="b6d60-194">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="b6d60-195">Waarschuwingstitel en beschrijving</span><span class="sxs-lookup"><span data-stu-id="b6d60-195">Alert title and description</span></span> 
- <span data-ttu-id="b6d60-196">Beïnvloede activa</span><span class="sxs-lookup"><span data-stu-id="b6d60-196">Impacted assets</span></span>
- <span data-ttu-id="b6d60-197">Acties die zijn ondernomen in reactie op de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="b6d60-197">Actions taken in response to the alert</span></span>
- <span data-ttu-id="b6d60-198">Queryresultaten die de waarschuwing hebben geactiveerd</span><span class="sxs-lookup"><span data-stu-id="b6d60-198">Query results that triggered the alert</span></span> 
- <span data-ttu-id="b6d60-199">Informatie over de aangepaste detectieregel</span><span class="sxs-lookup"><span data-stu-id="b6d60-199">Information on the custom detection rule</span></span> 
 
![Afbeelding van nieuwe waarschuwingspagina](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="b6d60-201">Query's schrijven zonder DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="b6d60-201">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="b6d60-202">In het Microsoft 365 Defender-schema worden de tabellen en tabellen geleverd voor de diverse set informatie die bij `AlertInfo` waarschuwingen van verschillende bronnen `AlertEvidence` past.</span><span class="sxs-lookup"><span data-stu-id="b6d60-202">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="b6d60-203">Als u dezelfde waarschuwingsgegevens wilt ontvangen die u hebt gebruikt om uit de tabel in het Schema van Microsoft Defender voor eindpunten te komen, filtert u de tabel op en voegt u vervolgens elke unieke id toe aan de tabel, die gedetailleerde gebeurtenis- en entiteitsgegevens `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` bevat.</span><span class="sxs-lookup"><span data-stu-id="b6d60-203">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="b6d60-204">Zie de voorbeeldquery hieronder:</span><span class="sxs-lookup"><span data-stu-id="b6d60-204">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="b6d60-205">Deze query levert veel meer kolommen op dan `DeviceAlertEvents` in het Schema van Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b6d60-205">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="b6d60-206">Als u de resultaten beheersbaar wilt houden, `project` gebruikt u alleen de kolommen waarin u geïnteresseerd bent.</span><span class="sxs-lookup"><span data-stu-id="b6d60-206">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="b6d60-207">In het onderstaande voorbeeld ziet u kolommen waarin u mogelijk geïnteresseerd bent wanneer tijdens het onderzoek PowerShell-activiteit is gedetecteerd:</span><span class="sxs-lookup"><span data-stu-id="b6d60-207">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="b6d60-208">Als u wilt filteren op specifieke entiteiten die betrokken zijn bij de waarschuwingen, kunt u dit doen door het entiteitstype in op te geven en de waarde op te geven die u `EntityType` wilt filteren.</span><span class="sxs-lookup"><span data-stu-id="b6d60-208">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="b6d60-209">In het volgende voorbeeld wordt naar een specifiek IP-adres op zoek:</span><span class="sxs-lookup"><span data-stu-id="b6d60-209">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="b6d60-210">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b6d60-210">See also</span></span>
- [<span data-ttu-id="b6d60-211">Microsoft 365 Defender in-</span><span class="sxs-lookup"><span data-stu-id="b6d60-211">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b6d60-212">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b6d60-212">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b6d60-213">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b6d60-213">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b6d60-214">Advanced hunting in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b6d60-214">Advanced hunting in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)