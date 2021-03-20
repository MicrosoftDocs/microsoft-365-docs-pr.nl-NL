---
title: Actie ondernemen voor geavanceerde zoekqueryresultaten in Microsoft 365 Defender
description: Snel bedreigingen en beïnvloede activa in uw geavanceerde resultaten van de zoekquery aan te pakken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, take action
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
ms.technology: m365d
ms.openlocfilehash: fbd49806913b5f01ccc3127d6b596db140d2e2aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904006"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="924e9-104">Actie ondernemen voor geavanceerde resultaten van query's</span><span class="sxs-lookup"><span data-stu-id="924e9-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="924e9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="924e9-105">**Applies to:**</span></span>
- <span data-ttu-id="924e9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="924e9-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="924e9-107">Met krachtige en uitgebreide actieopties kunt u snel bedreigingen bevatten of gecompromitteerde activa die u in [geavanceerde](advanced-hunting-overview.md) zoekactie vindt, bevatten.</span><span class="sxs-lookup"><span data-stu-id="924e9-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="924e9-108">Met deze opties kunt u:</span><span class="sxs-lookup"><span data-stu-id="924e9-108">With these options, you can:</span></span>

- <span data-ttu-id="924e9-109">Verschillende acties uitvoeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="924e9-109">Take various actions on devices</span></span>
- <span data-ttu-id="924e9-110">Quarantainebestanden</span><span class="sxs-lookup"><span data-stu-id="924e9-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="924e9-111">Vereiste machtigingen</span><span class="sxs-lookup"><span data-stu-id="924e9-111">Required permissions</span></span>
<span data-ttu-id="924e9-112">Als u actie wilt kunnen ondernemen via geavanceerde zoekacties, hebt u een rol nodig in Microsoft Defender voor Eindpunt met machtigingen voor het indienen van herstelacties [op apparaten.](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="924e9-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="924e9-113">Als u geen actie kunt ondernemen, neemt u contact op met een globale beheerder over het verkrijgen van de volgende machtigingen:</span><span class="sxs-lookup"><span data-stu-id="924e9-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="924e9-114">*Actieve herstelacties > bedreigings- en kwetsbaarheidsbeheer - Herstelafhandeling*</span><span class="sxs-lookup"><span data-stu-id="924e9-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="924e9-115">Verschillende acties uitvoeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="924e9-115">Take various actions on devices</span></span>
<span data-ttu-id="924e9-116">U kunt de volgende acties uitvoeren op apparaten die zijn geïdentificeerd door de `DeviceId` kolom in de queryresultaten:</span><span class="sxs-lookup"><span data-stu-id="924e9-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="924e9-117">Getroffen apparaten isoleren om een infectie te bevatten of om te voorkomen dat aanvallen lateraal worden verplaatst</span><span class="sxs-lookup"><span data-stu-id="924e9-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="924e9-118">Onderzoekspakket verzamelen om meer gerechtelijke informatie te verkrijgen</span><span class="sxs-lookup"><span data-stu-id="924e9-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="924e9-119">Voer een antivirusscan uit om bedreigingen te zoeken en te verwijderen met de meest recente beveiligingsinformatie-updates</span><span class="sxs-lookup"><span data-stu-id="924e9-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="924e9-120">Een geautomatiseerd onderzoek starten om bedreigingen op het apparaat en mogelijk andere getroffen apparaten te controleren en te corrigeren</span><span class="sxs-lookup"><span data-stu-id="924e9-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="924e9-121">De uitvoering van apps beperken tot alleen door Microsoft ondertekende uitvoerbare bestanden, waardoor verdere bedreigingsactiviteit via malware of andere niet-vertrouwde uitvoerbare bestanden wordt voorkomen</span><span class="sxs-lookup"><span data-stu-id="924e9-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="924e9-122">Lees meer over reactieacties op apparaten voor meer informatie over hoe deze antwoordacties worden uitgevoerd via Microsoft Defender voor [Eindpunt.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)</span><span class="sxs-lookup"><span data-stu-id="924e9-122">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="924e9-123">Quarantainebestanden</span><span class="sxs-lookup"><span data-stu-id="924e9-123">Quarantine files</span></span>
<span data-ttu-id="924e9-124">U kunt de *quarantaineactie voor* bestanden implementeren, zodat ze automatisch in quarantaine worden geplaatst wanneer ze worden aangetroffen.</span><span class="sxs-lookup"><span data-stu-id="924e9-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="924e9-125">Wanneer u deze actie selecteert, kunt u kiezen uit de volgende kolommen om te bepalen welke bestanden in de queryresultaten in quarantaine moeten worden geplaatst:</span><span class="sxs-lookup"><span data-stu-id="924e9-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="924e9-126">`SHA1` — In de meeste geavanceerde zoektabellen is dit de SHA-1 van het bestand dat is beïnvloed door de opgenomen actie.</span><span class="sxs-lookup"><span data-stu-id="924e9-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="924e9-127">Als een bestand bijvoorbeeld is gekopieerd, is dit het gekopieerde bestand.</span><span class="sxs-lookup"><span data-stu-id="924e9-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="924e9-128">`InitiatingProcessSHA1` — In de meest geavanceerde zoektabellen is dit het bestand dat verantwoordelijk is voor het starten van de opgenomen actie.</span><span class="sxs-lookup"><span data-stu-id="924e9-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="924e9-129">Als bijvoorbeeld een onderliggend proces is gestart, is dit het bovenliggende proces.</span><span class="sxs-lookup"><span data-stu-id="924e9-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="924e9-130">`SHA256` — Dit is het SHA-256-equivalent van het bestand dat door de kolom is `SHA1` geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="924e9-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="924e9-131">`InitiatingProcessSHA256` — Dit is het SHA-256-equivalent van het bestand dat door de kolom is `InitiatingProcessSHA1` geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="924e9-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="924e9-132">Voor meer informatie over hoe quarantaineacties worden ondernomen en hoe bestanden kunnen worden hersteld, leest u [meer over reactieacties op bestanden.](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)</span><span class="sxs-lookup"><span data-stu-id="924e9-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="924e9-133">Als u bestanden wilt zoeken en in quarantaine wilt plaatsen, moeten de queryresultaten ook waarden `DeviceId` als apparaataanduidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="924e9-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="924e9-134">Actie ondernemen</span><span class="sxs-lookup"><span data-stu-id="924e9-134">Take action</span></span>
<span data-ttu-id="924e9-135">Als u een van de beschreven acties wilt uitvoeren, selecteert u een of meer records in de queryresultaten en selecteert u **Vervolgens Acties uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="924e9-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="924e9-136">Een wizard begeleidt u bij het proces van het selecteren en vervolgens indienen van uw gewenste acties.</span><span class="sxs-lookup"><span data-stu-id="924e9-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Afbeelding van geselecteerde record met deelvenster voor het controleren van de record](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="924e9-138">Acties bekijken die zijn ondernomen</span><span class="sxs-lookup"><span data-stu-id="924e9-138">Review actions taken</span></span>
<span data-ttu-id="924e9-139">Elke actie wordt afzonderlijk opgenomen in het [actiecentrum](mtp-action-center.md) onder **Actiecentrumgeschiedenis**  >   [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="924e9-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="924e9-140">Ga naar het actiecentrum om de status van elke actie te controleren.</span><span class="sxs-lookup"><span data-stu-id="924e9-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="924e9-141">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="924e9-141">Related topics</span></span>
- [<span data-ttu-id="924e9-142">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="924e9-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="924e9-143">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="924e9-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="924e9-144">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="924e9-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="924e9-145">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="924e9-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="924e9-146">Overzicht van actiecentrum</span><span class="sxs-lookup"><span data-stu-id="924e9-146">Action center overview</span></span>](mtp-action-center.md)