---
title: Actie ondernemen op het gebied van geavanceerde resultaten van query's in Microsoft Threat Protection
description: Snel bedreigingen en beïnvloede activa in uw geavanceerde resultaten van de zoekquery aan te pakken
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, avoid timeout, command lines, process id
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 79d720a8b996f826548b79834e5d5c2048e28c2b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059969"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="589b3-104">Actie ondernemen voor geavanceerde resultaten van query's</span><span class="sxs-lookup"><span data-stu-id="589b3-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="589b3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="589b3-105">**Applies to:**</span></span>
- [<span data-ttu-id="589b3-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="589b3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="589b3-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="589b3-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="589b3-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="589b3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="589b3-109">Met krachtige en uitgebreide actieopties kunt u snel bedreigingen bevatten of gecompromitteerde activa die u in [geavanceerde](advanced-hunting-overview.md) zoekactie vindt, bevatten.</span><span class="sxs-lookup"><span data-stu-id="589b3-109">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="589b3-110">Met deze opties kunt u:</span><span class="sxs-lookup"><span data-stu-id="589b3-110">With these options, you can:</span></span>

- <span data-ttu-id="589b3-111">Verschillende acties uitvoeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="589b3-111">Take various actions on devices</span></span>
- <span data-ttu-id="589b3-112">Quarantainebestanden</span><span class="sxs-lookup"><span data-stu-id="589b3-112">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="589b3-113">Vereiste machtigingen</span><span class="sxs-lookup"><span data-stu-id="589b3-113">Required permissions</span></span>

<span data-ttu-id="589b3-114">Als u actie wilt kunnen ondernemen via geavanceerde zoekacties, hebt u een rol nodig in Defender for Endpoint met machtigingen voor het indienen van herstelacties [op apparaten.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="589b3-114">To be able to take action through advanced hunting, you need a role in Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span></span> <span data-ttu-id="589b3-115">Als u geen actie kunt ondernemen, neemt u contact op met een globale beheerder over het verkrijgen van de volgende machtigingen:</span><span class="sxs-lookup"><span data-stu-id="589b3-115">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="589b3-116">*Actieve herstelacties > bedreigings- en kwetsbaarheidsbeheer - Herstelafhandeling*</span><span class="sxs-lookup"><span data-stu-id="589b3-116">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="589b3-117">Verschillende acties uitvoeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="589b3-117">Take various actions on devices</span></span>

<span data-ttu-id="589b3-118">U kunt de volgende acties uitvoeren op apparaten die zijn geïdentificeerd door de `DeviceId` kolom in de queryresultaten:</span><span class="sxs-lookup"><span data-stu-id="589b3-118">You can take the following actions on devices identified by the `DeviceId` column in your query results:</span></span>

- <span data-ttu-id="589b3-119">Getroffen apparaten isoleren om een infectie te bevatten of om te voorkomen dat aanvallen lateraal worden verplaatst</span><span class="sxs-lookup"><span data-stu-id="589b3-119">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="589b3-120">Onderzoekspakket verzamelen om meer gerechtelijke informatie te verkrijgen</span><span class="sxs-lookup"><span data-stu-id="589b3-120">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="589b3-121">Voer een antivirusscan uit om bedreigingen te zoeken en te verwijderen met de meest recente beveiligingsinformatie-updates</span><span class="sxs-lookup"><span data-stu-id="589b3-121">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="589b3-122">Een geautomatiseerd onderzoek starten om bedreigingen op het apparaat en mogelijk andere getroffen apparaten te controleren en te corrigeren</span><span class="sxs-lookup"><span data-stu-id="589b3-122">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="589b3-123">De uitvoering van apps beperken tot alleen door Microsoft ondertekende uitvoerbare bestanden, waardoor verdere bedreigingsactiviteit via malware of andere niet-vertrouwde uitvoerbare bestanden wordt voorkomen</span><span class="sxs-lookup"><span data-stu-id="589b3-123">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="589b3-124">Voor meer informatie over hoe deze antwoordacties worden uitgevoerd via Defender voor Eindpunt, leest u [meer over antwoordacties op apparaten.](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="589b3-124">To learn more about how these response actions are performed through Defender for Endpoint, [read about response actions on devices](respond-machine-alerts.md).</span></span>

## <a name="quarantine-files"></a><span data-ttu-id="589b3-125">Quarantainebestanden</span><span class="sxs-lookup"><span data-stu-id="589b3-125">Quarantine files</span></span>

<span data-ttu-id="589b3-126">U kunt de *quarantaineactie voor* bestanden implementeren, zodat ze automatisch in quarantaine worden geplaatst wanneer ze worden aangetroffen.</span><span class="sxs-lookup"><span data-stu-id="589b3-126">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="589b3-127">Wanneer u deze actie selecteert, kunt u kiezen uit de volgende kolommen om te bepalen welke bestanden in de queryresultaten in quarantaine moeten worden geplaatst:</span><span class="sxs-lookup"><span data-stu-id="589b3-127">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="589b3-128">`SHA1` — In de meeste geavanceerde zoektabellen is dit de SHA-1 van het bestand dat is beïnvloed door de opgenomen actie.</span><span class="sxs-lookup"><span data-stu-id="589b3-128">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="589b3-129">Als een bestand bijvoorbeeld is gekopieerd, is dit het gekopieerde bestand.</span><span class="sxs-lookup"><span data-stu-id="589b3-129">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="589b3-130">`InitiatingProcessSHA1` — In de meest geavanceerde zoektabellen is dit het bestand dat verantwoordelijk is voor het starten van de opgenomen actie.</span><span class="sxs-lookup"><span data-stu-id="589b3-130">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="589b3-131">Als bijvoorbeeld een onderliggend proces is gestart, is dit het bovenliggende proces.</span><span class="sxs-lookup"><span data-stu-id="589b3-131">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="589b3-132">`SHA256` — Dit is het SHA-256-equivalent van het bestand dat door de kolom is `SHA1` geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="589b3-132">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="589b3-133">`InitiatingProcessSHA256` — Dit is het SHA-256-equivalent van het bestand dat door de kolom is `InitiatingProcessSHA1` geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="589b3-133">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="589b3-134">Voor meer informatie over hoe quarantaineacties worden ondernomen en hoe bestanden kunnen worden hersteld, leest u [meer over reactieacties op bestanden.](respond-file-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="589b3-134">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](respond-file-alerts.md).</span></span>

>[!NOTE]
><span data-ttu-id="589b3-135">Als u bestanden wilt zoeken en in quarantaine wilt plaatsen, moeten de queryresultaten ook waarden `DeviceId` als apparaataanduidingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="589b3-135">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="589b3-136">Actie ondernemen</span><span class="sxs-lookup"><span data-stu-id="589b3-136">Take action</span></span>

<span data-ttu-id="589b3-137">Als u een van de beschreven acties wilt uitvoeren, selecteert u een of meer records in de queryresultaten en selecteert u **Vervolgens Acties uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="589b3-137">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="589b3-138">Een wizard begeleidt u bij het proces van het selecteren en vervolgens indienen van uw gewenste acties.</span><span class="sxs-lookup"><span data-stu-id="589b3-138">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Afbeelding van geselecteerde record met deelvenster voor het controleren van de record](images/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="589b3-140">Acties bekijken die zijn ondernomen</span><span class="sxs-lookup"><span data-stu-id="589b3-140">Review actions taken</span></span>

<span data-ttu-id="589b3-141">Elke actie wordt afzonderlijk opgenomen in het actiecentrum, onder **Actiecentrumgeschiedenis**  >   [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="589b3-141">Each action is individually recorded in the action center, under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="589b3-142">Ga naar het actiecentrum om de status van elke actie te controleren.</span><span class="sxs-lookup"><span data-stu-id="589b3-142">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="589b3-143">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="589b3-143">Related topics</span></span>

- [<span data-ttu-id="589b3-144">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="589b3-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="589b3-145">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="589b3-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="589b3-146">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="589b3-146">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="589b3-147">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="589b3-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="589b3-148">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="589b3-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="589b3-149">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="589b3-149">Custom detections overview</span></span>](overview-custom-detections.md)
