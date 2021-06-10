---
title: Ransomware zoeken met geavanceerde jacht
description: Gebruik geavanceerde zoekmogelijkheden om apparaten te vinden die mogelijk door ransomware zijn beïnvloed.
keywords: advanced hunting, ransomware, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft 365, Microsoft 365 Defender
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
ms.technology: m365d
ms.openlocfilehash: b6d88f5383cef052ac1b0871b4f0556ba3ba160e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934811"
---
# <a name="hunt-for-ransomware"></a><span data-ttu-id="51332-104">Ransomware opsporen</span><span class="sxs-lookup"><span data-stu-id="51332-104">Hunt for ransomware</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="51332-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="51332-105">**Applies to:**</span></span>
- <span data-ttu-id="51332-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51332-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="51332-107">Ransomware heeft zich snel ontwikkeld van eenvoudige malware op basis van goederen die van invloed is op afzonderlijke computergebruikers tot een ondernemingsdreiging die ernstige gevolgen heeft voor bedrijfstakken en overheidsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="51332-107">Ransomware has rapidly evolved from being simple commodity malware affecting individual computer users to an enterprise threat that is severely impacting industries and government institutions.</span></span> <span data-ttu-id="51332-108">Hoewel [Microsoft 365 Defender](microsoft-365-defender.md) vele mogelijkheden biedt die ransomware en bijbehorende inbraakactiviteiten detecteren en blokkeren, kan het uitvoeren van proactieve controles op tekenen van compromissen uw netwerk beschermen.</span><span class="sxs-lookup"><span data-stu-id="51332-108">While [Microsoft 365 Defender](microsoft-365-defender.md) provides many capabilities that detect and block ransomware and associated intrusion activities, performing proactive checks for signs of compromise can help keep your network protected.</span></span>

> [<span data-ttu-id="51332-109">Meer informatie over door mensen beheerde ransomware</span><span class="sxs-lookup"><span data-stu-id="51332-109">Read about human-operated ransomware</span></span>](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

<span data-ttu-id="51332-110">Met [geavanceerde zoekactiviteiten](advanced-hunting-overview.md) in Microsoft 365 Defender kunt u query's maken waarin afzonderlijke artefacten worden gevonden die zijn gekoppeld aan ransomware-activiteit.</span><span class="sxs-lookup"><span data-stu-id="51332-110">With [advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender, you can create queries that locate individual artifacts associated with ransomware activity.</span></span> <span data-ttu-id="51332-111">U kunt ook geavanceerdere query's uitvoeren die tekenen van activiteit kunnen zoeken en deze borden kunnen wegen om apparaten te vinden die direct aandacht vereisen.</span><span class="sxs-lookup"><span data-stu-id="51332-111">You can also run more sophisticated queries that can look for signs of activity and weigh those signs to find devices that require immediate attention.</span></span>

## <a name="signs-of-ransomware-activity"></a><span data-ttu-id="51332-112">Tekenen van ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="51332-112">Signs of ransomware activity</span></span>
<span data-ttu-id="51332-113">Beveiligingsonderzoekers van Microsoft hebben verschillende veelvoorkomende maar subtiele artefacten waargenomen in veel ransomware-campagnes die zijn gestart door geavanceerde indringers.</span><span class="sxs-lookup"><span data-stu-id="51332-113">Microsoft security researchers have observed various common yet subtle artifacts in many ransomware campaigns launched by sophisticated intruders.</span></span> <span data-ttu-id="51332-114">Deze tekens bestaan voornamelijk uit het gebruik van systeemhulpmiddelen voor het voorbereiden van versleuteling, het voorkomen van detectie en het vrijmaken van bewijsmateriaal.</span><span class="sxs-lookup"><span data-stu-id="51332-114">These signs mostly involve use of system tools to prepare for encryption, prevent detection, and clear forensic evidence.</span></span>

| <span data-ttu-id="51332-115">Ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="51332-115">Ransomware activity</span></span> | <span data-ttu-id="51332-116">Veelgebruikte hulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="51332-116">Common tools</span></span> | <span data-ttu-id="51332-117">Bedoeling</span><span class="sxs-lookup"><span data-stu-id="51332-117">Intent</span></span> |
|--|--|--|
| <span data-ttu-id="51332-118">Processen stoppen</span><span class="sxs-lookup"><span data-stu-id="51332-118">Stop processes</span></span> | <span data-ttu-id="51332-119">_taskkill.exe_, _netto-stop_</span><span class="sxs-lookup"><span data-stu-id="51332-119">_taskkill.exe_, _net stop_</span></span> | <span data-ttu-id="51332-120">Zorg ervoor dat bestanden die zijn bedoeld voor versleuteling, niet worden vergrendeld door verschillende toepassingen.</span><span class="sxs-lookup"><span data-stu-id="51332-120">Ensure files targeted for encryption are not locked by various applications.</span></span> |
| <span data-ttu-id="51332-121">Services uitschakelen</span><span class="sxs-lookup"><span data-stu-id="51332-121">Turn off services</span></span> | <span data-ttu-id="51332-122">_sc.exe_</span><span class="sxs-lookup"><span data-stu-id="51332-122">_sc.exe_</span></span> | <span data-ttu-id="51332-123">- Zorg ervoor dat bestanden die zijn bedoeld voor versleuteling, niet worden vergrendeld door verschillende toepassingen.</span><span class="sxs-lookup"><span data-stu-id="51332-123">- Ensure files targeted for encryption are not locked by various applications.</span></span><br><span data-ttu-id="51332-124">- Voorkom dat beveiligingssoftware versleuteling en andere ransomware-activiteiten verstoort.</span><span class="sxs-lookup"><span data-stu-id="51332-124">- Prevent security software from disrupting encryption and other ransomware activity.</span></span><br><span data-ttu-id="51332-125">- Stop back-upsoftware om herstelbare kopieën te maken.</span><span class="sxs-lookup"><span data-stu-id="51332-125">- Stop backup software from creating recoverable copies.</span></span>  |
| <span data-ttu-id="51332-126">Logboeken en bestanden verwijderen</span><span class="sxs-lookup"><span data-stu-id="51332-126">Delete logs and files</span></span> | <span data-ttu-id="51332-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span><span class="sxs-lookup"><span data-stu-id="51332-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span></span> | <span data-ttu-id="51332-128">Verwijder het bewijs van de recherche.</span><span class="sxs-lookup"><span data-stu-id="51332-128">Remove forensic evidence.</span></span> |
| <span data-ttu-id="51332-129">Schaduwkopieen verwijderen</span><span class="sxs-lookup"><span data-stu-id="51332-129">Delete shadow copies</span></span>  | <span data-ttu-id="51332-130">_vsadmin.exe_, _wmic.exe_</span><span class="sxs-lookup"><span data-stu-id="51332-130">_vsadmin.exe_, _wmic.exe_</span></span> | <span data-ttu-id="51332-131">Verwijder schijfschaduwkopieën die kunnen worden gebruikt om versleutelde bestanden te herstellen.</span><span class="sxs-lookup"><span data-stu-id="51332-131">Remove drive shadow copies that can be used to recover encrypted files.</span></span> |
| <span data-ttu-id="51332-132">Back-ups verwijderen en stoppen</span><span class="sxs-lookup"><span data-stu-id="51332-132">Delete and stop backups</span></span> | <span data-ttu-id="51332-133">_wbadmin.exe_</span><span class="sxs-lookup"><span data-stu-id="51332-133">_wbadmin.exe_</span></span> | <span data-ttu-id="51332-134">Verwijder bestaande back-ups en stop geplande back-uptaken, waardoor herstel na versleuteling wordt voorkomen.</span><span class="sxs-lookup"><span data-stu-id="51332-134">Delete existing backups and stop scheduled backup tasks, preventing recovery after encryption.</span></span> |
| <span data-ttu-id="51332-135">Opstartinstellingen wijzigen</span><span class="sxs-lookup"><span data-stu-id="51332-135">Modify boot settings</span></span> | <span data-ttu-id="51332-136">_bcdedit.exe_</span><span class="sxs-lookup"><span data-stu-id="51332-136">_bcdedit.exe_</span></span> | <span data-ttu-id="51332-137">Schakel waarschuwingen en automatische reparaties uit na opstartfouten die kunnen worden veroorzaakt door het versleutelingsproces.</span><span class="sxs-lookup"><span data-stu-id="51332-137">Turn off warnings and automatic repairs after boot failures that can be caused by the encryption process.</span></span> |
| <span data-ttu-id="51332-138">Herstelprogramma's uitschakelen</span><span class="sxs-lookup"><span data-stu-id="51332-138">Turn off recovery tools</span></span> | <span data-ttu-id="51332-139">_schtasks.exe_, _regedit.exe_,</span><span class="sxs-lookup"><span data-stu-id="51332-139">_schtasks.exe_, _regedit.exe_,</span></span> | <span data-ttu-id="51332-140">Schakel Systeemherstel en andere systeemherstelopties uit.</span><span class="sxs-lookup"><span data-stu-id="51332-140">Turn off System Restore and other system recovery options.</span></span> |

## <a name="check-for-individual-signs-of-ransomware-activity"></a><span data-ttu-id="51332-141">Controleren op afzonderlijke tekenen van ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="51332-141">Check for individual signs of ransomware activity</span></span>
<span data-ttu-id="51332-142">Veel activiteiten die ransomwaregedrag vormen, inclusief de activiteiten die in de vorige sectie worden beschreven, kunnen goedaardig zijn.</span><span class="sxs-lookup"><span data-stu-id="51332-142">Many activities that constitute ransomware behavior, including the activities described in the preceding section, can be benign.</span></span> <span data-ttu-id="51332-143">Wanneer u de volgende query's gebruikt om ransomware te zoeken, kunt u meerdere query's uitvoeren om te controleren of dezelfde apparaten verschillende tekenen van mogelijke ransomware-activiteit vertonen.</span><span class="sxs-lookup"><span data-stu-id="51332-143">When using the following queries to locate ransomware, run more than one query to check whether the same devices are exhibiting various signs of possible ransomware activity.</span></span>

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a><span data-ttu-id="51332-144">Meerdere processen stoppen _met_ taskkill.exe</span><span class="sxs-lookup"><span data-stu-id="51332-144">Stopping multiple processes using _taskkill.exe_</span></span>
<span data-ttu-id="51332-145">Met deze query wordt gecontroleerd op pogingen om ten minste 10 afzonderlijke processen te stoppen mettaskkill.exe _hulpprogramma._</span><span class="sxs-lookup"><span data-stu-id="51332-145">This query checks for attempts to stop at least 10 separate processes using the _taskkill.exe_ utility.</span></span> [<span data-ttu-id="51332-146">Query uitvoeren</span><span class="sxs-lookup"><span data-stu-id="51332-146">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a><span data-ttu-id="51332-147">Processen stoppen met _behulp van nettostop_</span><span class="sxs-lookup"><span data-stu-id="51332-147">Stopping processes using _net stop_</span></span>
<span data-ttu-id="51332-148">Met deze query wordt gecontroleerd op pogingen om ten minste 10 afzonderlijke processen te stoppen met de _opdracht Netstop._</span><span class="sxs-lookup"><span data-stu-id="51332-148">This query checks for attempts to stop at least 10 separate processes using the _net stop_ command.</span></span> [<span data-ttu-id="51332-149">Query uitvoeren</span><span class="sxs-lookup"><span data-stu-id="51332-149">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a><span data-ttu-id="51332-150">Gegevens verwijderen op meerdere stations met _cipher.exe_</span><span class="sxs-lookup"><span data-stu-id="51332-150">Deletion of data on multiple drives using _cipher.exe_</span></span>
<span data-ttu-id="51332-151">Met deze query wordt gecontroleerd op pogingen om gegevens op meerdere stations te verwijderen met _cipher.exe._</span><span class="sxs-lookup"><span data-stu-id="51332-151">This query checks for attempts to delete data on multiple drives using _cipher.exe_.</span></span> <span data-ttu-id="51332-152">Deze activiteit wordt meestal uitgevoerd door ransomware om herstel van gegevens na versleuteling te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="51332-152">This activity is typically done by ransomware to prevent recovery of data after encryption.</span></span> [<span data-ttu-id="51332-153">Query uitvoeren</span><span class="sxs-lookup"><span data-stu-id="51332-153">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for cipher.exe deleting data from multiple drives
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine),
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1
```

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a><span data-ttu-id="51332-154">Wissen van sporenonderzoek uit gebeurtenislogboeken met _wevtutil_</span><span class="sxs-lookup"><span data-stu-id="51332-154">Clearing of forensic evidence from event logs using _wevtutil_</span></span>
<span data-ttu-id="51332-155">Met deze query wordt gecontroleerd op pogingen om ten minste 10 logboekgegevens uit gebeurtenislogboeken te verwijderen met _wevtutil._</span><span class="sxs-lookup"><span data-stu-id="51332-155">This query checks for attempts to clear at least 10 log entries from event logs using _wevtutil_.</span></span> [<span data-ttu-id="51332-156">Query uitvoeren</span><span class="sxs-lookup"><span data-stu-id="51332-156">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a><span data-ttu-id="51332-157">Services uitschakelen _met_ sc.exe</span><span class="sxs-lookup"><span data-stu-id="51332-157">Turning off services using _sc.exe_</span></span>
<span data-ttu-id="51332-158">Met deze query wordt gecontroleerd op pogingen om ten minste 10 bestaande services uit te schakelen met _sc.exe._</span><span class="sxs-lookup"><span data-stu-id="51332-158">This query checks for attempts to turn off at least 10 existing services using _sc.exe_.</span></span> [<span data-ttu-id="51332-159">Query uitvoeren</span><span class="sxs-lookup"><span data-stu-id="51332-159">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a><span data-ttu-id="51332-160">Systeemherstel uitschakelen</span><span class="sxs-lookup"><span data-stu-id="51332-160">Turning off System Restore</span></span>
<span data-ttu-id="51332-161">Deze query identificeert pogingen om systeemherstel te stoppen en te voorkomen dat het systeem herstelpunten maakt, die kunnen worden gebruikt om gegevens te herstellen die zijn versleuteld door ransomware.</span><span class="sxs-lookup"><span data-stu-id="51332-161">This query identifies attempts to stop System Restore and prevent the system from creating restore points, which can be used to recover data encrypted by ransomware.</span></span> [<span data-ttu-id="51332-162">Query uitvoeren</span><span class="sxs-lookup"><span data-stu-id="51332-162">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
//Pivoting for rundll32  
| where InitiatingProcessFileName =~ 'rundll32.exe'   
//Looking for empty command line   
and InitiatingProcessCommandLine !contains " " and InitiatingProcessCommandLine != ""  
//Looking for schtasks.exe as the created process  
and FileName in~ ('schtasks.exe')  
//Disabling system restore   
and ProcessCommandLine has 'Change' and ProcessCommandLine has 'SystemRestore' 
and ProcessCommandLine has 'disable'
```

### <a name="backup-deletion"></a><span data-ttu-id="51332-163">Back-up verwijderen</span><span class="sxs-lookup"><span data-stu-id="51332-163">Backup deletion</span></span>
<span data-ttu-id="51332-164">Deze query identificeert het gebruik _vanwmic.exe_ om momentopnamen van schaduwkopieen te verwijderen vóór versleuteling.</span><span class="sxs-lookup"><span data-stu-id="51332-164">This query identifies use of _wmic.exe_ to delete shadow copy snapshots prior to encryption.</span></span> [<span data-ttu-id="51332-165">Query uitvoeren</span><span class="sxs-lookup"><span data-stu-id="51332-165">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a><span data-ttu-id="51332-166">Controleer op meerdere tekenen van ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="51332-166">Check for multiple signs of ransomware activity</span></span>
<span data-ttu-id="51332-167">In plaats van meerdere query's afzonderlijk uit te voeren, kunt u ook een uitgebreide query gebruiken die controleert op meerdere tekenen van ransomware-activiteit om getroffen apparaten te identificeren.</span><span class="sxs-lookup"><span data-stu-id="51332-167">Instead of running several queries separately, you can also use a comprehensive query that checks for multiple signs of ransomware activity to identify affected devices.</span></span> <span data-ttu-id="51332-168">De volgende samengevoegde query:</span><span class="sxs-lookup"><span data-stu-id="51332-168">The following consolidated  query:</span></span>
- <span data-ttu-id="51332-169">Zoekt naar zowel relatief concrete als subtiele tekenen van ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="51332-169">Looks for both relatively concrete and subtle signs of ransomware activity</span></span>
- <span data-ttu-id="51332-170">Weegt de aanwezigheid van deze tekens</span><span class="sxs-lookup"><span data-stu-id="51332-170">Weighs the presence of these signs</span></span>
- <span data-ttu-id="51332-171">Identificeert apparaten met een hogere kans om het doel van ransomware te worden</span><span class="sxs-lookup"><span data-stu-id="51332-171">Identifies devices with a higher chance of being targets of ransomware</span></span> 

<span data-ttu-id="51332-172">Wanneer deze query wordt uitgevoerd, retourneert deze samengevoegde query een lijst met apparaten met meerdere aanvallen.</span><span class="sxs-lookup"><span data-stu-id="51332-172">When run, this consolidated query returns a list of devices that have exhibited multiple signs of attack.</span></span> <span data-ttu-id="51332-173">Het aantal van elk type ransomware-activiteit wordt ook weergegeven.</span><span class="sxs-lookup"><span data-stu-id="51332-173">The count of each type of ransomware activity is also shown.</span></span> <span data-ttu-id="51332-174">Als u deze samengevoegde query wilt uitvoeren, kopieert u deze rechtstreeks naar de [geavanceerde queryeditor.](https://security.microsoft.com/advanced-hunting)</span><span class="sxs-lookup"><span data-stu-id="51332-174">To run this consolidated query, copy it directly to the [advanced hunting query editor](https://security.microsoft.com/advanced-hunting).</span></span> 

```kusto
// Find attempts to stop processes using taskkill.exe
let taskKill = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10;
// Find attempts to stop processes using net stop
let netStop = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10;
// Look for cipher.exe deleting data from multiple drives
let cipher = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine), 
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1;
// Look for use of wevtutil to clear multiple logs
let wevtutilClear = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10;
// Look for sc.exe disabling services
let scDisable = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10;
// Main query for counting and aggregating evidence
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "vssadmin.exe" and ProcessCommandLine has_any("list shadows", "delete shadows")
or FileName =~ "fsutil.exe" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal"
or ProcessCommandLine has("bcdedit") and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures")
or ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup")
or (ProcessCommandLine has "wevtutil" and ProcessCommandLine has "cl") 
or (ProcessCommandLine has "wmic" and ProcessCommandLine has "shadowcopy delete")
or (ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled")
| extend Bcdedit = iff(ProcessCommandLine has "bcdedit" and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures"), 1, 0)
| extend ShadowCopyDelete = iff (ProcessCommandLine has "shadowcopy delete", 1, 0)
| extend VssAdminShadows = iff(ProcessCommandLine has "vssadmin" and ProcessCommandLine has_any("list shadows", "delete shadows"), 1, 0)
| extend Wbadmin = iff(ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup"), 1,0)
| extend Fsutil = iff(ProcessCommandLine has "fsutil" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal", 1, 0)
| summarize FirstActivity = min(Timestamp), ReportId = any(ReportId), Commands = make_set(ProcessCommandLine) by DeviceId, Fsutil, Wbadmin, ShadowCopyDelete, Bcdedit, VssAdminShadows, bin(Timestamp, 6h)
// Joining extra evidence
| join kind=leftouter (wevtutilClear) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (cipher) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (netStop) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (taskKill) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (scDisable) on $left.DeviceId == $right.DeviceId
| extend WevtutilUse = iff(LogClearCount > 10, 1, 0)
| extend CipherUse = iff(CipherCount > 1, 1, 0)
| extend NetStopUse = iff(netStopCount > 10, 1, 0)
| extend TaskkillUse = iff(taskKillCount > 10, 1, 0)
| extend ScDisableUse = iff(ScDisableCount > 10, 1, 0)
// Adding up all evidence
| mv-expand CommandList = NetStopList, TaskKillList, ClearedLogList, CipherList, Commands, ScDisableList
// Format results
| summarize BcdEdit = iff(make_set(Bcdedit) contains "1" , 1, 0), NetStop10PlusCommands = iff(make_set(NetStopUse) contains "1", 1, 0), Wevtutil10PlusLogsCleared = iff(make_set(WevtutilUse) contains "1", 1, 0),
CipherMultipleDrives = iff(make_set(CipherUse) contains "1", 1, 0), Fsutil = iff(make_set(Fsutil) contains "1", 1, 0), ShadowCopyDelete = iff(make_set(ShadowCopyDelete) contains "1", 1, 0),
Wbadmin = iff(make_set(Wbadmin) contains "1", 1, 0), TaskKill10PlusCommand = iff(make_set(TaskkillUse) contains "1", 1, 0), VssAdminShadow = iff(make_set(VssAdminShadows) contains "1", 1, 0), 
ScDisable = iff(make_set(ScDisableUse) contains "1", 1, 0), TotalEvidenceCount = count(CommandList), EvidenceList = make_set(Commands), StartofBehavior = min(FirstActivity) by DeviceId, bin(Timestamp, 1d)
| extend UniqueEvidenceCount = BcdEdit + NetStop10PlusCommands + Wevtutil10PlusLogsCleared + CipherMultipleDrives + Wbadmin + Fsutil + TaskKill10PlusCommand + VssAdminShadow + ScDisable + ShadowCopyDelete
| where UniqueEvidenceCount > 2
```
### <a name="understand-and-tweak-the-query-results"></a><span data-ttu-id="51332-175">De queryresultaten begrijpen en aanpassen</span><span class="sxs-lookup"><span data-stu-id="51332-175">Understand and tweak the query results</span></span>
<span data-ttu-id="51332-176">De samengevoegde query retourneert de volgende resultaten:</span><span class="sxs-lookup"><span data-stu-id="51332-176">The consolidated query returns the following results:</span></span>

- <span data-ttu-id="51332-177">**DeviceId**: identificeert het betreffende apparaat</span><span class="sxs-lookup"><span data-stu-id="51332-177">**DeviceId**—identifies the affected device</span></span> 
- <span data-ttu-id="51332-178">**TimeStamp**: de eerste keer dat een teken van ransomware-activiteit werd waargenomen op het apparaat</span><span class="sxs-lookup"><span data-stu-id="51332-178">**TimeStamp**—first time any sign of ransomware activity was observed on the device</span></span>
- <span data-ttu-id="51332-179">**Specifieke tekenen van activiteit:** het aantal voor elk teken dat wordt weergegeven in meerdere kolommen, zoals _BcdEdit_ of _FsUtil_</span><span class="sxs-lookup"><span data-stu-id="51332-179">**Specific signs of activity**—the count for each sign shown in multiple columns, such as _BcdEdit_ or _FsUtil_</span></span>
- <span data-ttu-id="51332-180">**TotalEvidenceCount**(aantal waargenomen tekens)</span><span class="sxs-lookup"><span data-stu-id="51332-180">**TotalEvidenceCount**—number of observed signs</span></span>
- <span data-ttu-id="51332-181">**UniqueEvidenceCount**(aantal typen waargenomen tekens)</span><span class="sxs-lookup"><span data-stu-id="51332-181">**UniqueEvidenceCount**—number of types of observed signs</span></span>

![Afbeelding van de queryresultaten voor ransomware-activiteit](../../media/advanced-hunting-ransomware-query.png)

<span data-ttu-id="51332-183">*Queryresultaten met beïnvloede apparaten en tellingen van verschillende tekenen van ransomware-activiteit*</span><span class="sxs-lookup"><span data-stu-id="51332-183">*Query results showing affected devices and counts of various signs of ransomware activity*</span></span>

<span data-ttu-id="51332-184">Standaard bevat het queryresultaat alleen apparaten met meer dan twee soorten ransomware-activiteiten.</span><span class="sxs-lookup"><span data-stu-id="51332-184">By default, the query result lists only devices that have more than two types of ransomware activity.</span></span> <span data-ttu-id="51332-185">Als u alle apparaten met een teken van ransomware-activiteit wilt zien, wijzigt u de volgende operator en stelt u het getal in `where` op nul (0).</span><span class="sxs-lookup"><span data-stu-id="51332-185">To see all devices with any sign of ransomware activity, modify the following `where` operator and set the number to zero (0).</span></span> <span data-ttu-id="51332-186">Als u minder apparaten wilt zien, stelt u een hoger getal in.</span><span class="sxs-lookup"><span data-stu-id="51332-186">To see fewer devices, set a higher number.</span></span> 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a><span data-ttu-id="51332-187">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="51332-187">Related topics</span></span>
- [<span data-ttu-id="51332-188">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="51332-188">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="51332-189">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="51332-189">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="51332-190">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="51332-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="51332-191">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="51332-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="51332-192">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="51332-192">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="51332-193">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="51332-193">Apply query best practices</span></span>](advanced-hunting-best-practices.md)