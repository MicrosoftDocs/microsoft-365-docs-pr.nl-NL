---
title: Microsoft Defender voor endpoint ASR-regels rapporteren en oplossen
description: In dit onderwerp wordt beschreven hoe u Microsoft Defender voor Endpoint ASR-regels kunt rapporteren en oplossen
keywords: Attack surface reduction rules, asr, hips, host intrusion prevention system, protection rules, anti-exploit, anti-exploit, exploit, infection prevention, microsoft defender for endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246059"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a><span data-ttu-id="3df45-104">Microsoft Defender voor ATP ASR-regels rapporteren en oplossen</span><span class="sxs-lookup"><span data-stu-id="3df45-104">Report and troubleshoot Microsoft Defender for ATP ASR Rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3df45-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3df45-105">**Applies to:**</span></span>

- [<span data-ttu-id="3df45-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="3df45-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3df45-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3df45-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3df45-108">Het Microsoft 365 beveiligingscentrum is de nieuwe interface voor het bewaken en beheren van beveiliging in uw Microsoft-identiteiten, gegevens, apparaten, apps en infrastructuur.</span><span class="sxs-lookup"><span data-stu-id="3df45-108">The Microsoft 365 security center is the new interface for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> <span data-ttu-id="3df45-109">Hier kunt u eenvoudig de beveiligingstoestand van uw organisatie bekijken, in actie komen om apparaten, gebruikers en apps te configureren en waarschuwingen voor verdachte activiteiten te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="3df45-109">Here you can easily view the security health of your organization, act to configure devices, users, and apps, and get alerts for suspicious activity.</span></span> <span data-ttu-id="3df45-110">Het Microsoft 365 beveiligingscentrum is bedoeld voor beveiligingsbeheerders en beveiligingsbewerkingsteams om hun organisatie beter te beheren en te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="3df45-110">The Microsoft 365 security center is intended for security admins and security operations teams to better manage and protect their organization.</span></span> <span data-ttu-id="3df45-111">Ga naar het Microsoft 365 beveiligingscentrum op https://security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="3df45-111">Visit the Microsoft 365 security center at https://security.microsoft.com.</span></span>
<span data-ttu-id="3df45-112">In Microsoft 365 beveiligingscentrum bieden we u een volledig overzicht van de huidige configuratie en gebeurtenissen van ASR-regels in uw domein.</span><span class="sxs-lookup"><span data-stu-id="3df45-112">In Microsoft 365 security center, we offer you a complete look at the current ASR rules configuration and events in your estate.</span></span> <span data-ttu-id="3df45-113">Houd er rekening mee dat uw apparaten moeten zijn aangesloten bij de Microsoft Defender voor Eindpunt-service om deze rapporten in te vullen.</span><span class="sxs-lookup"><span data-stu-id="3df45-113">Note that your devices must be onboarded into the Microsoft Defender for Endpoint service for these reports to be populated.</span></span>
<span data-ttu-id="3df45-114">Hier is een schermafbeelding van het Microsoft 365 beveiligingscentrum (onder **Reports**  >  **Devices**  >  **Attack surface reduction**).</span><span class="sxs-lookup"><span data-stu-id="3df45-114">Here's a screenshot from the Microsoft 365 security center (under **Reports** > **Devices** > **Attack surface reduction**).</span></span> <span data-ttu-id="3df45-115">Selecteer Configuratie op apparaatniveau **in het** deelvenster Surface Reduction Rules **van Attack.**</span><span class="sxs-lookup"><span data-stu-id="3df45-115">At the device level, select **Configuration** from the **Attack surface reduction rules** pane.</span></span> <span data-ttu-id="3df45-116">Het volgende scherm wordt weergegeven, waarin u een specifiek apparaat kunt selecteren en de afzonderlijke ASR-regelconfiguratie kunt controleren.</span><span class="sxs-lookup"><span data-stu-id="3df45-116">The following screen is displayed, where you can select a specific device and check its individual ASR rule configuration.</span></span>

:::image type="content" source="images/asrrulesnew.png" alt-text="SCHERM ASR-regels":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a><span data-ttu-id="3df45-118">Microsoft Defender for Endpoint – Advanced hunting</span><span class="sxs-lookup"><span data-stu-id="3df45-118">Microsoft Defender for Endpoint – Advanced hunting</span></span>

<span data-ttu-id="3df45-119">Een van de krachtigste functies van Microsoft Defender voor Eindpunt is geavanceerd zoeken.</span><span class="sxs-lookup"><span data-stu-id="3df45-119">One of the most powerful features of Microsoft Defender for Endpoint is advanced hunting.</span></span> <span data-ttu-id="3df45-120">Als u niet bekend bent met geavanceerde jacht, verwijst u proactief [naar bedreigingen met geavanceerde jacht.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3df45-120">If you're unfamiliar with advanced hunting, refer [proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

<span data-ttu-id="3df45-121">Advanced hunting is een op query's gebaseerd (Kusto Query Language) threat-hunting tool waarmee u tot 30 dagen van de vastgelegde (onbewerkte) gegevens kunt verkennen, die MDE Endpoint Detection and Response (EDR) van al uw machines verzamelt.</span><span class="sxs-lookup"><span data-stu-id="3df45-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that MDE Endpoint Detection and Response (EDR) collects from all your machines.</span></span> <span data-ttu-id="3df45-122">Door middel van geavanceerde jacht kunt u gebeurtenissen proactief controleren om interessante indicatoren en entiteiten te vinden.</span><span class="sxs-lookup"><span data-stu-id="3df45-122">Through advanced hunting, you can proactively inspect events to locate interesting indicators and entities.</span></span> <span data-ttu-id="3df45-123">De flexibele toegang tot gegevens helpt ongebreideld zoeken naar bekende en potentiële bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="3df45-123">The flexible access to data helps unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="3df45-124">Door middel van geavanceerd zoeken is het mogelijk om ASR-regelsgegevens op te halen, rapporten te maken en uitgebreide informatie te krijgen over de context van een bepaalde ASR-regelcontrole of -gebeurtenis te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="3df45-124">Through advanced hunting, it's possible to extract ASR rules information, create reports, and get in-depth information on the context of a given ASR rule audit or block event.</span></span>

<span data-ttu-id="3df45-125">Asr-regels kunnen worden opgevraagd in de tabel DeviceEvents in de geavanceerde sectie van de Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="3df45-125">ASR rules events are available to be queried from the DeviceEvents table in the advanced hunting section of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="3df45-126">Een eenvoudige query, zoals de onderstaande, kan bijvoorbeeld alle gebeurtenissen met ASR-regels als gegevensbron rapporteren voor de laatste 30 dagen en deze samenvatten met het aantal ActionType's, dat in dit geval de werkelijke codenaam van de ASR-regel is.</span><span class="sxs-lookup"><span data-stu-id="3df45-126">For example, a simple query such as the one below can report all the events that have ASR rules as data source, for the last 30 days, and will summarize them by the ActionType count, that in this case it will be the actual codename of the ASR rule.</span></span>

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Geavanceerde zoekquery":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="geavanceerd zoekscherm":::

<span data-ttu-id="3df45-129">Met geavanceerd zoeken kunt u de query's naar wens vorm geven, zodat u kunt zien wat er gebeurt, ongeacht of u iets op een afzonderlijke computer wilt aanwijzen of dat u inzichten uit uw hele omgeving wilt halen.</span><span class="sxs-lookup"><span data-stu-id="3df45-129">With advanced hunting you can shape the queries to your liking, so that you can see what is happening, regardless of whether you want to pinpoint something on an individual machine, or you want to extract insights from your entire environment.</span></span>

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a><span data-ttu-id="3df45-130">Tijdlijn van Microsoft Defender voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="3df45-130">Microsoft Defender for Endpoint machine timeline</span></span>

<span data-ttu-id="3df45-131">Een alternatief voor geavanceerd zoeken, maar met een kleiner bereik, is de tijdlijn van microsoft Defender voor eindpunten.</span><span class="sxs-lookup"><span data-stu-id="3df45-131">An alternative to advanced hunting, but with a narrower scope, is the Microsoft Defender for Endpoint machine timeline.</span></span> <span data-ttu-id="3df45-132">U kunt alle verzamelde gebeurtenissen van een apparaat bekijken, de afgelopen zes maanden, in de Microsoft Defender-beveiligingscentrum, door naar de lijst Machines te gaan, een bepaalde computer te selecteren en vervolgens op het tabblad Tijdlijn te klikken.</span><span class="sxs-lookup"><span data-stu-id="3df45-132">You can view all the collected events of a device, for the past six months, in the Microsoft Defender Security Center, by going to the Machines list, select a given machine, and then click on the Timeline tab.</span></span>

<span data-ttu-id="3df45-133">Hieronder ziet u een schermafbeelding van de tijdlijnweergave van deze gebeurtenissen op een bepaald eindpunt.</span><span class="sxs-lookup"><span data-stu-id="3df45-133">Pictured below is a screenshot of the Timeline view of these events on a given endpoint.</span></span>  <span data-ttu-id="3df45-134">In deze weergave kunt u de lijst met gebeurtenissen filteren op basis van een van de gebeurtenisgroepen in het rechterdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="3df45-134">From this view, you can filter the events list based on any of the Event Groups along the right-side pane.</span></span> <span data-ttu-id="3df45-135">U kunt vlaggeveerde en uitgebreide gebeurtenissen ook in- of uitschakelen tijdens het weergeven van waarschuwingen en het scrollen door de historische tijdlijn.</span><span class="sxs-lookup"><span data-stu-id="3df45-135">You can also enable or disable Flagged and Verbose events while viewing alerts and scrolling through the historical timeline.</span></span>

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="tijdlijn van het Microsoft Defender-beveiligingscentrum":::

## <a name="how-to-troubleshoot-asr-rules"></a><span data-ttu-id="3df45-137">Problemen met ASR-regels oplossen?</span><span class="sxs-lookup"><span data-stu-id="3df45-137">How to troubleshoot ASR rules?</span></span>

<span data-ttu-id="3df45-138">De eerste en meest directe manier is om lokaal op een Windows-apparaat te controleren welke ASR-regels zijn ingeschakeld (en de configuratie) met behulp van de PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3df45-138">The first and most immediate way is to check locally, on a Windows device, which ASR rules are enabled (and their configuration) is by using the PowerShell cmdlets.</span></span>

<span data-ttu-id="3df45-139">Hier volgen enkele andere informatiebronnen die Windows bieden, om de gevolgen en werking van ASR-regels op te lossen.</span><span class="sxs-lookup"><span data-stu-id="3df45-139">Here are a few other sources of information that Windows offers, to troubleshoot ASR rules’ impact and operation.</span></span>

### <a name="querying-which-rules-are-active"></a><span data-ttu-id="3df45-140">Query's uitvoeren welke regels actief zijn</span><span class="sxs-lookup"><span data-stu-id="3df45-140">Querying which rules are active</span></span>
<span data-ttu-id="3df45-141">Een van de eenvoudigste manieren om te bepalen of ASR-regels al zijn ingeschakeld, en is via een PowerShell-cmdlet, Get-MpPreference.</span><span class="sxs-lookup"><span data-stu-id="3df45-141">One of the easiest ways to determine if ASR rules are already enabled—and, is through a PowerShell cmdlet, Get-MpPreference.</span></span>
<span data-ttu-id="3df45-142">Hier volgt een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3df45-142">Here's an example:</span></span>

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="mppreference-script krijgen":::

<span data-ttu-id="3df45-144">Er zijn meerdere ASR-regels actief, met verschillende geconfigureerde acties.</span><span class="sxs-lookup"><span data-stu-id="3df45-144">There are multiple ASR rules active, with different configured actions.</span></span>

<span data-ttu-id="3df45-145">Als u de bovenstaande informatie over ASR-regels wilt uitbreiden, kunt u de eigenschappen **AttackSurfaceReductionRules_Ids** en/of **AttackSurfaceReductionRules_Actions.**</span><span class="sxs-lookup"><span data-stu-id="3df45-145">To expand the above information on ASR rules, you can use the properties **AttackSurfaceReductionRules_Ids** and/or **AttackSurfaceReductionRules_Actions**.</span></span>

<span data-ttu-id="3df45-146">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3df45-146">Example:</span></span>

<span data-ttu-id="3df45-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span><span class="sxs-lookup"><span data-stu-id="3df45-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span></span>

:::image type="content" source="images/getmpref-examplenew.png" alt-text="voorbeeld van mpreference krijgen":::

<span data-ttu-id="3df45-149">In het bovenstaande ziet u alle ID's voor ASR-regels die een andere instelling hebben dan 0 (niet geconfigureerd).</span><span class="sxs-lookup"><span data-stu-id="3df45-149">The above shows all the IDs for ASR rules that have a setting different from 0 (Not Configured).</span></span>

<span data-ttu-id="3df45-150">De volgende stap is om de werkelijke acties (Blokkeren of Audit) op te nemen met welke regel elke regel is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="3df45-150">The next step is then to list the actual actions (Block or Audit) that each rule is configured with.</span></span> 

<span data-ttu-id="3df45-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span><span class="sxs-lookup"><span data-stu-id="3df45-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span></span>

:::image type="content" source="images/getmpref-example2new.png" alt-text="voorbeeld van mppreference krijgen2":::

### <a name="querying-blocking-and-auditing-events"></a><span data-ttu-id="3df45-153">Query's blokkeren en controleren</span><span class="sxs-lookup"><span data-stu-id="3df45-153">Querying blocking and auditing events</span></span>
<span data-ttu-id="3df45-154">ASR-regelgebeurtenissen kunnen worden bekeken in het Windows Defender logboek.</span><span class="sxs-lookup"><span data-stu-id="3df45-154">ASR rule events can be viewed within the Windows Defender log.</span></span>

<span data-ttu-id="3df45-155">Als u deze wilt openen, opent u Windows Viewer voor gebeurtenissen en bladert u naar Toepassingen en **serviceslogboeken** van  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operationeel.**</span><span class="sxs-lookup"><span data-stu-id="3df45-155">To access it, open Windows Event Viewer, and browse to **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

:::image type="content" source="images/eventviewerscrnew.png" alt-text="gebeurtenisviewer scr":::

## <a name="microsoft-defender-malware-protection-logs"></a><span data-ttu-id="3df45-157">Microsoft Defender Malware Protection Logs</span><span class="sxs-lookup"><span data-stu-id="3df45-157">Microsoft Defender Malware Protection Logs</span></span>
<span data-ttu-id="3df45-158">U kunt ook regelgebeurtenissen weergeven via het Microsoft Defender Antivirus speciaal opdrachtregelprogramma, dat kan worden gebruikt om taken te beheren en te configureren en te `*mpcmdrun.exe*` automatiseren, indien nodig.</span><span class="sxs-lookup"><span data-stu-id="3df45-158">You can also view rule events through the Microsoft Defender Antivirus dedicated command-line tool, called `*mpcmdrun.exe*`, that can be used to manage and configure, and automate tasks if needed.</span></span>

<span data-ttu-id="3df45-159">U vindt dit hulpprogramma in *%ProgramFiles%\Windows Defender\MpCmdRun.exe.*</span><span class="sxs-lookup"><span data-stu-id="3df45-159">You can find this utility in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span></span> <span data-ttu-id="3df45-160">U moet deze uitvoeren vanuit een opdrachtprompt met verhoogde opdracht (dat wil zeggen uitvoeren als beheerder).</span><span class="sxs-lookup"><span data-stu-id="3df45-160">You must run it from an elevated command prompt (that is, run as Admin).</span></span>

<span data-ttu-id="3df45-161">Als u de ondersteuningsgegevens wilt genereren, *typtMpCmdRun.exe -getfiles*.</span><span class="sxs-lookup"><span data-stu-id="3df45-161">To generate the support information, type *MpCmdRun.exe -getfiles*.</span></span> <span data-ttu-id="3df45-162">Na een tijdje worden verschillende logboeken in een archief (MpSupportFiles.cab) verpakt en beschikbaar gesteld in *C:\ProgramData\Microsoft\Windows Defender\Support.*</span><span class="sxs-lookup"><span data-stu-id="3df45-162">After a while, several logs will be packaged into an archive (MpSupportFiles.cab) and made available in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span></span>

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="malwarebeveiligingslogboeken":::

<span data-ttu-id="3df45-164">Haal dat archief op en u hebt veel bestanden beschikbaar voor probleemoplossingsdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="3df45-164">Extract that archive and you'll have many files available for troubleshooting purposes.</span></span>

<span data-ttu-id="3df45-165">De meest relevante bestanden zijn als volgt:</span><span class="sxs-lookup"><span data-stu-id="3df45-165">The most relevant files are as follows:</span></span>

- <span data-ttu-id="3df45-166">**MPOperationalEvents.txt:** dit bestand bevat hetzelfde informatieniveau dat wordt gevonden in Gebeurtenisviewer voor Windows Defender het operationele logboek van de groep.</span><span class="sxs-lookup"><span data-stu-id="3df45-166">**MPOperationalEvents.txt** - This file contains same level of information found in Event Viewer for Windows Defender’s Operational log.</span></span>
- <span data-ttu-id="3df45-167">**MPRegistry.txt:** in dit bestand kunt u alle huidige Windows Defender analyseren, vanaf het moment dat de ondersteuningslogboeken zijn vastgelegd.</span><span class="sxs-lookup"><span data-stu-id="3df45-167">**MPRegistry.txt** – In this file you will can analyze all the current Windows Defender configurations, from the moment the support logs were captured.</span></span>
- <span data-ttu-id="3df45-168">**MPLog.txt:** dit logboek bevat uitgebreidere informatie over alle acties/bewerkingen van de Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="3df45-168">**MPLog.txt** – This log contains more verbose information about all the actions/operations of the Windows Defender.</span></span>
