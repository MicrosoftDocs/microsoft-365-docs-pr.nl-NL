---
title: Onderneem actie op geavanceerde jachtqueryresultaten in Microsoft Threat Protection
description: Pak bedreigingen en getroffen assets snel aan in uw geavanceerde jachtqueryresultaten
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, actie ondernemen
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4ebf220472db69d48127b805256e15246bd400cb
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552730"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="3f748-104">Actie ondernemen op geavanceerde jachtqueryresultaten</span><span class="sxs-lookup"><span data-stu-id="3f748-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="3f748-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3f748-105">**Applies to:**</span></span>
- <span data-ttu-id="3f748-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3f748-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="3f748-107">U snel bedreigingen bevatten of gecompromitteerde activa aanpakken die u in [geavanceerde jacht](advanced-hunting-overview.md) vindt met behulp van krachtige en uitgebreide actieopties.</span><span class="sxs-lookup"><span data-stu-id="3f748-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="3f748-108">Met deze opties u:</span><span class="sxs-lookup"><span data-stu-id="3f748-108">With these options, you can:</span></span>

- <span data-ttu-id="3f748-109">Verschillende acties uitvoeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="3f748-109">Take various actions on devices</span></span>
- <span data-ttu-id="3f748-110">Quarantainebestanden</span><span class="sxs-lookup"><span data-stu-id="3f748-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="3f748-111">Vereiste machtigingen</span><span class="sxs-lookup"><span data-stu-id="3f748-111">Required permissions</span></span>
<span data-ttu-id="3f748-112">Om actie te kunnen ondernemen door middel van geavanceerde jacht, heb je een rol nodig in Microsoft Defender ATP met [machtigingen om herstelacties in te dienen op apparaten.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="3f748-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender ATP with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="3f748-113">Als u geen actie ondernemen, neemt u contact op met een globale beheerder over het verkrijgen van de volgende machtiging:</span><span class="sxs-lookup"><span data-stu-id="3f748-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="3f748-114">*Actieve herstelacties > bedreigings- en kwetsbaarheidsbeheer - Herstelafhandeling*</span><span class="sxs-lookup"><span data-stu-id="3f748-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="3f748-115">Verschillende acties uitvoeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="3f748-115">Take various actions on devices</span></span>
<span data-ttu-id="3f748-116">U de volgende acties uitvoeren op apparaten die door de kolom in de queryresultaten zijn `DeviceId` geïdentificeerd:</span><span class="sxs-lookup"><span data-stu-id="3f748-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="3f748-117">Getroffen apparaten isoleren om een infectie te bevatten of te voorkomen dat aanvallen lateraal bewegen</span><span class="sxs-lookup"><span data-stu-id="3f748-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="3f748-118">Verzamel onderzoekspakket om meer forensische informatie te verkrijgen</span><span class="sxs-lookup"><span data-stu-id="3f748-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="3f748-119">Een antivirusscan uitvoeren om bedreigingen te vinden en te verwijderen met behulp van de nieuwste updates van beveiligingsinformatie</span><span class="sxs-lookup"><span data-stu-id="3f748-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="3f748-120">Start een geautomatiseerd onderzoek om bedreigingen op het apparaat en mogelijk andere getroffen apparaten te controleren en te herstellen</span><span class="sxs-lookup"><span data-stu-id="3f748-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="3f748-121">App-uitvoering beperken tot alleen door Microsoft ondertekende uitvoerbare bestanden, waardoor latere bedreigingsactiviteit wordt voorkomen door middel van malware of andere niet-vertrouwde uitvoerbare bestanden</span><span class="sxs-lookup"><span data-stu-id="3f748-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="3f748-122">[Lees meer over de](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)manier waarop deze reactieacties worden uitgevoerd via Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="3f748-122">To learn more about how these response actions are performed through Microsoft Defender ATP, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="3f748-123">Quarantainebestanden</span><span class="sxs-lookup"><span data-stu-id="3f748-123">Quarantine files</span></span>
<span data-ttu-id="3f748-124">U de *quarantaineactie* implementeren op bestanden, zodat ze automatisch in quarantaine worden geplaatst wanneer ze worden aangetroffen.</span><span class="sxs-lookup"><span data-stu-id="3f748-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="3f748-125">Wanneer u deze actie selecteert, u kiezen uit de volgende kolommen om te bepalen welke bestanden in uw queryresultaten in quarantaine moeten worden geplaatst:</span><span class="sxs-lookup"><span data-stu-id="3f748-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="3f748-126">`SHA1`— In de meeste geavanceerde jachttafels is dit de SHA-1 van het bestand dat werd beïnvloed door de geregistreerde actie.</span><span class="sxs-lookup"><span data-stu-id="3f748-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="3f748-127">Als een bestand bijvoorbeeld is gekopieerd, is dit het gekopieerde bestand.</span><span class="sxs-lookup"><span data-stu-id="3f748-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="3f748-128">`InitiatingProcessSHA1`— In de meeste geavanceerde jachttabellen is dit het bestand dat verantwoordelijk is voor het initiëren van de geregistreerde actie.</span><span class="sxs-lookup"><span data-stu-id="3f748-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="3f748-129">Als er bijvoorbeeld een onderliggend proces is gestart, is dit het bovenliggende proces.</span><span class="sxs-lookup"><span data-stu-id="3f748-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="3f748-130">`SHA256`— Dit is het SHA-256-equivalent van het bestand dat door de kolom wordt `SHA1` geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="3f748-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="3f748-131">`InitiatingProcessSHA256`— Dit is het SHA-256-equivalent van het bestand dat door de kolom wordt `InitiatingProcessSHA1` geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="3f748-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="3f748-132">Lees meer over de manier waarop quarantaineacties worden uitgevoerd en hoe bestanden kunnen worden hersteld, [over reactieacties in bestanden](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="3f748-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="3f748-133">Als u bestanden wilt zoeken en in quarantaine wilt plaatsen, moeten de queryresultaten ook `DeviceId` waarden als apparaat-id's bevatten.</span><span class="sxs-lookup"><span data-stu-id="3f748-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="3f748-134">Actie ondernemen</span><span class="sxs-lookup"><span data-stu-id="3f748-134">Take action</span></span>
<span data-ttu-id="3f748-135">Als u een van de beschreven acties wilt uitvoeren, selecteert u een of meer records in uw queryresultaten en selecteert u **Acties uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="3f748-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="3f748-136">Een wizard begeleidt u bij het selecteren en vervolgens indienen van uw gewenste acties.</span><span class="sxs-lookup"><span data-stu-id="3f748-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Afbeelding van geselecteerde record met deelvenster voor het inspecteren van de record](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="3f748-138">Acties bekijken</span><span class="sxs-lookup"><span data-stu-id="3f748-138">Review actions taken</span></span>
<span data-ttu-id="3f748-139">Elke actie wordt individueel geregistreerd in het [actiecentrum](mtp-action-center.md) onder **Geschiedenis van het Actiecentrum**  >  **History** [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="3f748-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="3f748-140">Ga naar het actiecentrum om de status van elke actie te controleren.</span><span class="sxs-lookup"><span data-stu-id="3f748-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="3f748-141">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="3f748-141">Related topics</span></span>
- [<span data-ttu-id="3f748-142">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="3f748-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3f748-143">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="3f748-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3f748-144">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="3f748-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="3f748-145">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="3f748-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3f748-146">Overzicht van het Onderhoudscentrum</span><span class="sxs-lookup"><span data-stu-id="3f748-146">Action center overview</span></span>](mtp-action-center.md)