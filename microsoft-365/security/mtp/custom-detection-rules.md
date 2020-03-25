---
title: Aangepaste detectieregels maken en beheren in Microsoft Threat Protection
description: Meer informatie over het maken en beheren van aangepaste detectieregels op basis van geavanceerde jachtquery's
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, regels, schema, kusto, microsoft 365, Microsoft Threat Protection, RBAC, machtigingen, Microsoft Verdediger ATP
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
ms.openlocfilehash: adb8c7dfa0050ef2eb0d59e1e55d07da7aaa3f39
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42931742"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="a2d08-104">Aangepaste detectieregels maken en beheren</span><span class="sxs-lookup"><span data-stu-id="a2d08-104">Create and manage custom detections rules</span></span>

<span data-ttu-id="a2d08-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a2d08-105">**Applies to:**</span></span>
- <span data-ttu-id="a2d08-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="a2d08-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a2d08-107">Met aangepaste detectieregels die zijn gebaseerd op geavanceerde jachtquery's, u proactief verschillende gebeurtenissen en systeemstatussen controleren, waaronder vermoedelijke inbreukactiviteiten en verkeerd geconfigureerde eindpunten. [Advanced hunting](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a2d08-107">Custom detection rules built from [Advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="a2d08-108">U instellen dat ze op regelmatige tijdstippen worden uitgevoerd, waarschuwingen genereren en responsacties uitvoeren wanneer er overeenkomsten zijn.</span><span class="sxs-lookup"><span data-stu-id="a2d08-108">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="a2d08-109">Vereiste machtigingen voor het beheren van aangepaste detecties</span><span class="sxs-lookup"><span data-stu-id="a2d08-109">Required permissions for managing custom detections</span></span>

<span data-ttu-id="a2d08-110">Als u aangepaste detecties wilt beheren, moet u een van deze rollen toegewezen krijgen:</span><span class="sxs-lookup"><span data-stu-id="a2d08-110">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="a2d08-111">**Beveiligingsbeheerder** : de beveiligingsbeheerder of beveiligingsbeheerrol is een [Azure Active Directory-rol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) voor het beheren van verschillende beveiligingsinstellingen in het Microsoft 365-beveiligingscentrum en verschillende portals en services.</span><span class="sxs-lookup"><span data-stu-id="a2d08-111">**Security administrator** — the security administrator or security admin role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing various security settings in Microsoft 365 security center and various portals and services.</span></span>

- <span data-ttu-id="a2d08-112">**Beveiligingsoperator** : de rol van de beveiligingsoperator is een [Azure Active Directory-rol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) voor het beheren van waarschuwingen en heeft wereldwijde alleen-lezen toegang voor beveiligingsfuncties, inclusief alle informatie in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="a2d08-112">**Security operator** —  the security operator role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing alerts and has global read-only access on security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="a2d08-113">Deze rol is voldoende voor het beheren van aangepaste detecties alleen als role-based access control (RBAC) is uitgeschakeld in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a2d08-113">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="a2d08-114">Als u RBAC hebt geconfigureerd, hebt u ook de machtiging **voor beveiligingsinstellingen voor** Microsoft Defender ATP nodig.</span><span class="sxs-lookup"><span data-stu-id="a2d08-114">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="a2d08-115">Als u vereiste machtigingen wilt beheren, kan een **globale beheerder** het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="a2d08-115">To manage required permissions, a **global administrator** can do the following:</span></span>

- <span data-ttu-id="a2d08-116">Wijs de rol **van beveiligingsbeheerder** of **beveiligingsoperator** toe in [het Microsoft 365-beheercentrum](https://admin.microsoft.com/) onder**Debeveiligingsbeheerder** **rollen** > .</span><span class="sxs-lookup"><span data-stu-id="a2d08-116">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="a2d08-117">Schakel RBAC-instellingen voor Microsoft Defender ATP in Microsoft Defender Security Center in microsoft [Defender-beveiligingscentrum](https://securitycenter.windows.com/) onder**Rollen\*\*\*\*voor machtigingen voor** >  **instellingen** > .</span><span class="sxs-lookup"><span data-stu-id="a2d08-117">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="a2d08-118">Selecteer de bijbehorende rol om de machtigingen **voor beveiligingsinstellingen beheren** toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="a2d08-118">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="a2d08-119">Om aangepaste detecties te beheren, hebben **beveiligingsoperators** de machtigingen **voor beveiligingsinstellingen beheren** in Microsoft Defender ATP nodig als RBAC is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a2d08-119">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="a2d08-120">Een aangepaste detectieregel maken</span><span class="sxs-lookup"><span data-stu-id="a2d08-120">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="a2d08-121">1. Bereid de query voor.</span><span class="sxs-lookup"><span data-stu-id="a2d08-121">1. Prepare the query.</span></span>

<span data-ttu-id="a2d08-122">Ga in het beveiligingscentrum van Microsoft 365 naar **Geavanceerd zoeken** en selecteer een bestaande query of maak een nieuwe query.</span><span class="sxs-lookup"><span data-stu-id="a2d08-122">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="a2d08-123">Wanneer u een nieuwe query gebruikt, voert u de query uit om fouten te identificeren en mogelijke resultaten te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="a2d08-123">When using a new query, run the query to identify errors and understand possible results.</span></span>

#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="a2d08-124">Vereiste kolommen in de queryresultaten</span><span class="sxs-lookup"><span data-stu-id="a2d08-124">Required columns in the query results</span></span>
<span data-ttu-id="a2d08-125">Als u een aangepaste detectieregel wilt maken, moet de query de volgende kolommen retourneren:</span><span class="sxs-lookup"><span data-stu-id="a2d08-125">To create a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- <span data-ttu-id="a2d08-126">Een van de volgende kolommen voor apparaat, gebruiker of postvak:</span><span class="sxs-lookup"><span data-stu-id="a2d08-126">One of the following device, user, or mailbox columns:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="a2d08-127">`SenderFromAddress`(afzender envelop of retourpadadres)</span><span class="sxs-lookup"><span data-stu-id="a2d08-127">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="a2d08-128">`SenderMailFromAddress`(afzenderadres weergegeven per e-mailclient)</span><span class="sxs-lookup"><span data-stu-id="a2d08-128">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountSid`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
><span data-ttu-id="a2d08-129">Ondersteuning voor extra entiteiten wordt toegevoegd als er nieuwe tabellen worden toegevoegd aan het [geavanceerde jachtschema](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a2d08-129">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="a2d08-130">Eenvoudige query's, zoals query's `project` die `summarize` de operator niet gebruiken om resultaten aan te passen of samen te voegen, retourneren doorgaans deze algemene kolommen.</span><span class="sxs-lookup"><span data-stu-id="a2d08-130">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="a2d08-131">Er zijn verschillende manieren om ervoor te zorgen dat complexere query's deze kolommen retourneren.</span><span class="sxs-lookup"><span data-stu-id="a2d08-131">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="a2d08-132">Als u bijvoorbeeld de voorkeur geeft aan aggregaat `DeviceId`en telt `Timestamp` op entiteit onder een kolom zoals `DeviceId`, u nog steeds terugkeren door deze te verkrijgen van de meest recente gebeurtenis waarbij elke unieke.</span><span class="sxs-lookup"><span data-stu-id="a2d08-132">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="a2d08-133">De onderstaande voorbeeldquery telt het`DeviceId`aantal unieke machines ( ) met antivirusdetecties en gebruikt dit aantal om alleen de machines met meer dan vijf detecties te vinden.</span><span class="sxs-lookup"><span data-stu-id="a2d08-133">The sample query below counts the number of unique machines (`DeviceId`) with antivirus detections and uses this count to find only the machines with more than five detections.</span></span> <span data-ttu-id="a2d08-134">Om de `Timestamp`laatste keer `summarize` terug te `arg_max` keren, gebruikt het de operator met de functie.</span><span class="sxs-lookup"><span data-stu-id="a2d08-134">To return the latest `Timestamp`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="a2d08-135">2. Maak een nieuwe regel en geef waarschuwingsgegevens op.</span><span class="sxs-lookup"><span data-stu-id="a2d08-135">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="a2d08-136">Selecteer met de query in de queryeditor **de detectieregel maken** en geef de volgende waarschuwingsdetails op:</span><span class="sxs-lookup"><span data-stu-id="a2d08-136">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="a2d08-137">**Detectienaam** — naam van de detectieregel</span><span class="sxs-lookup"><span data-stu-id="a2d08-137">**Detection name** — name of the detection rule</span></span>
- <span data-ttu-id="a2d08-138">**Frequentie** : interval voor het uitvoeren van de query en het uitvoeren van actie.</span><span class="sxs-lookup"><span data-stu-id="a2d08-138">**Frequency** — interval for running the query and taking action.</span></span> [<span data-ttu-id="a2d08-139">Zie aanvullende richtlijnen hieronder</span><span class="sxs-lookup"><span data-stu-id="a2d08-139">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="a2d08-140">**Waarschuwingstitel** — titel weergegeven met waarschuwingen die door de regel worden geactiveerd</span><span class="sxs-lookup"><span data-stu-id="a2d08-140">**Alert title** — title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="a2d08-141">**Ernst** — potentieel risico van de component of activiteit die door de regel is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="a2d08-141">**Severity** — potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="a2d08-142">**Categorie** — bedreigingscomponent of activiteit die door de regel is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="a2d08-142">**Category** — threat component or activity identified by the rule</span></span>
- <span data-ttu-id="a2d08-143">**MITRE ATT&CK technieken** - een of meer aanvalstechnieken geïdentificeerd door de regel zoals gedocumenteerd in de [MITRE ATT&CK kader](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="a2d08-143">**MITRE ATT&CK techniques** — one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/)</span></span>
- <span data-ttu-id="a2d08-144">**Beschrijving** — meer informatie over de component of activiteit die door de regel is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="a2d08-144">**Description** — more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="a2d08-145">**Aanbevolen acties** : extra acties die responders kunnen uitvoeren als reactie op een waarschuwing</span><span class="sxs-lookup"><span data-stu-id="a2d08-145">**Recommended actions** — additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="a2d08-146">Regelfrequentie</span><span class="sxs-lookup"><span data-stu-id="a2d08-146">Rule frequency</span></span>
<span data-ttu-id="a2d08-147">Wanneer deze wordt opgeslagen, wordt een nieuwe of bewerkte aangepaste detectieregel onmiddellijk uitgevoerd en gecontroleerd op overeenkomsten van de afgelopen 30 dagen aan gegevens.</span><span class="sxs-lookup"><span data-stu-id="a2d08-147">When saved, a new or edited custom detection rule immediately runs and checks for matches from  the past 30 days of data.</span></span> <span data-ttu-id="a2d08-148">De regel wordt vervolgens opnieuw uitgevoerd met vaste intervallen en terugkijkduur op basis van de frequentie die u kiest:</span><span class="sxs-lookup"><span data-stu-id="a2d08-148">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="a2d08-149">**Elke 24 uur** - loopt elke 24 uur, het controleren van gegevens van de afgelopen 30 dagen</span><span class="sxs-lookup"><span data-stu-id="a2d08-149">**Every 24 hours** — runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="a2d08-150">**Elke 12 uur** - loopt elke 12 uur, het controleren van gegevens van de afgelopen 24 uur</span><span class="sxs-lookup"><span data-stu-id="a2d08-150">**Every 12 hours** — runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="a2d08-151">**Elke 3 uur** - loopt elke 3 uur, het controleren van gegevens van de afgelopen 6 uur</span><span class="sxs-lookup"><span data-stu-id="a2d08-151">**Every 3 hours** — runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="a2d08-152">**Elk uur** - loopt per uur, het controleren van gegevens van de afgelopen 2 uur</span><span class="sxs-lookup"><span data-stu-id="a2d08-152">**Every hour** — runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="a2d08-153">Selecteer de frequentie die overeenkomt met hoe nauw u detecties wilt controleren en houd rekening met het vermogen van uw organisatie om op de waarschuwingen te reageren.</span><span class="sxs-lookup"><span data-stu-id="a2d08-153">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="a2d08-154">3. Kies de getroffen entiteiten.</span><span class="sxs-lookup"><span data-stu-id="a2d08-154">3. Choose the impacted entities.</span></span>
<span data-ttu-id="a2d08-155">Identificeer de kolommen in uw queryresultaten waar u verwacht de belangrijkste of getroffen entiteit te vinden.</span><span class="sxs-lookup"><span data-stu-id="a2d08-155">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="a2d08-156">Een query kan bijvoorbeeld afzender`SenderFromAddress` `SenderMailFromAddress`- of`RecipientEmailAddress`geadresseerde () adressen retourneren.</span><span class="sxs-lookup"><span data-stu-id="a2d08-156">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="a2d08-157">Als u identificeert welke van deze kolommen de belangrijkste getroffen entiteit zijn, kan de service relevante waarschuwingen samenvoegen, incidenten correleren en acties voor doelrespons uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="a2d08-157">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="a2d08-158">U slechts één kolom selecteren voor elk entiteitstype (postvak, gebruiker of apparaat).</span><span class="sxs-lookup"><span data-stu-id="a2d08-158">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="a2d08-159">Kolommen die niet door uw query worden geretourneerd, kunnen niet worden geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a2d08-159">Columns that are not returned by your query can't be selected.</span></span>

### <a name="3-specify-actions-on-files-or-machines"></a><span data-ttu-id="a2d08-160">3. Geef acties op bestanden of machines op.</span><span class="sxs-lookup"><span data-stu-id="a2d08-160">3. Specify actions on files or machines.</span></span>
<span data-ttu-id="a2d08-161">Uw aangepaste detectieregel kan automatisch acties uitvoeren op bestanden of machines die door de query worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="a2d08-161">Your custom detection rule can automatically take actions on files or machines that are returned by the query.</span></span>

#### <a name="actions-on-machines"></a><span data-ttu-id="a2d08-162">Acties op machines</span><span class="sxs-lookup"><span data-stu-id="a2d08-162">Actions on machines</span></span>
<span data-ttu-id="a2d08-163">Deze acties worden toegepast `DeviceId` op machines in de kolom van de queryresultaten:</span><span class="sxs-lookup"><span data-stu-id="a2d08-163">These actions are applied to machines in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="a2d08-164">**Machine isoleren** — gebruikt Microsoft Defender ATP om volledige netwerkisolatie toe te passen, waardoor de machine geen verbinding kan maken met een toepassing of service.</span><span class="sxs-lookup"><span data-stu-id="a2d08-164">**Isolate machine** — uses Microsoft Defender ATP to apply full network isolation, preventing the machine from connecting to any application or service.</span></span> [<span data-ttu-id="a2d08-165">Meer informatie over Microsoft Defender ATP-machineisolatie</span><span class="sxs-lookup"><span data-stu-id="a2d08-165">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- <span data-ttu-id="a2d08-166">**Onderzoekspakket verzamelen** — verzamelt machinegegevens in een ZIP-bestand.</span><span class="sxs-lookup"><span data-stu-id="a2d08-166">**Collect investigation package** — collects machine information in a ZIP file.</span></span> [<span data-ttu-id="a2d08-167">Meer informatie over het Microsoft Defender ATP-onderzoekspakket</span><span class="sxs-lookup"><span data-stu-id="a2d08-167">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- <span data-ttu-id="a2d08-168">**Antivirusscan uitvoeren** — voert een volledige Windows Defender Antivirus-scan uit op de machine</span><span class="sxs-lookup"><span data-stu-id="a2d08-168">**Run antivirus scan** — performs a full Windows Defender Antivirus scan on the machine</span></span>
- <span data-ttu-id="a2d08-169">**Start onderzoek** — start een [geautomatiseerd onderzoek](mtp-autoir.md) naar de machine</span><span class="sxs-lookup"><span data-stu-id="a2d08-169">**Initiate investigation** — initiates an [automated investigation](mtp-autoir.md) on the machine</span></span>

#### <a name="actions-on-files"></a><span data-ttu-id="a2d08-170">Acties op bestanden</span><span class="sxs-lookup"><span data-stu-id="a2d08-170">Actions on files</span></span>
<span data-ttu-id="a2d08-171">Wanneer deze optie is geselecteerd, wordt de `InitiatingProcessSHA1` `SHA256`actie `InitiatingProcessSHA256` **Quarantainebestand** uitgevoerd op bestanden in de `SHA1`kolom , of kolom van de queryresultaten.</span><span class="sxs-lookup"><span data-stu-id="a2d08-171">When selected, the **Quarantine file** action is taken on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="a2d08-172">Met deze actie wordt het bestand van de huidige locatie verwijderd en wordt een kopie in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="a2d08-172">This action deletes the file from its current location and places a copy in quarantine.</span></span>

> [!NOTE]
> <span data-ttu-id="a2d08-173">De actie voor aangepaste detectieregels toestaan of blokkeren, wordt momenteel niet ondersteund op Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="a2d08-173">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="4-set-the-rule-scope"></a><span data-ttu-id="a2d08-174">4. Stel de regelscope in.</span><span class="sxs-lookup"><span data-stu-id="a2d08-174">4. Set the rule scope.</span></span>
<span data-ttu-id="a2d08-175">Stel het bereik in om op te geven welke apparaten onder de regel vallen.</span><span class="sxs-lookup"><span data-stu-id="a2d08-175">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="a2d08-176">Het bereik beïnvloedt regels die apparaten controleren en heeft geen invloed op regels die alleen postvakken en gebruikersaccounts of identiteiten controleren.</span><span class="sxs-lookup"><span data-stu-id="a2d08-176">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="a2d08-177">Wanneer u het bereik instelt, u het beste selecteren:</span><span class="sxs-lookup"><span data-stu-id="a2d08-177">When setting the scope, you can select:</span></span>

- <span data-ttu-id="a2d08-178">Alle apparaten</span><span class="sxs-lookup"><span data-stu-id="a2d08-178">All devices</span></span>
- <span data-ttu-id="a2d08-179">Specifieke apparaatgroepen</span><span class="sxs-lookup"><span data-stu-id="a2d08-179">Specific device groups</span></span>

<span data-ttu-id="a2d08-180">Alleen gegevens van apparaten in het bereik worden opgevraagd.</span><span class="sxs-lookup"><span data-stu-id="a2d08-180">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="a2d08-181">Ook zullen acties alleen worden uitgevoerd op deze apparaten.</span><span class="sxs-lookup"><span data-stu-id="a2d08-181">Also, actions will be taken only on those devices.</span></span>

### <a name="5-review-and-turn-on-the-rule"></a><span data-ttu-id="a2d08-182">5. De regel controleren en inschakelen.</span><span class="sxs-lookup"><span data-stu-id="a2d08-182">5. Review and turn on the rule.</span></span>
<span data-ttu-id="a2d08-183">Nadat u de regel hebt gecontroleerd, klikt u op **Maken** om deze op te slaan.</span><span class="sxs-lookup"><span data-stu-id="a2d08-183">After reviewing the rule, click **Create** to save it.</span></span> <span data-ttu-id="a2d08-184">De aangepaste detectieregel wordt onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a2d08-184">The custom detection rule immediately runs.</span></span> <span data-ttu-id="a2d08-185">Het wordt opnieuw uitgevoerd op basis van geconfigureerde frequentie om te controleren op overeenkomsten, waarschuwingen te genereren en reactieacties uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="a2d08-185">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="a2d08-186">Bestaande aangepaste detectieregels beheren</span><span class="sxs-lookup"><span data-stu-id="a2d08-186">Manage existing custom detection rules</span></span>
<span data-ttu-id="a2d08-187">U de lijst met bestaande aangepaste detectieregels bekijken, de eerdere uitvoeringen controleren en de waarschuwingen bekijken die ze hebben geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="a2d08-187">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="a2d08-188">U ook een regel op aanvraag uitvoeren en deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a2d08-188">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="a2d08-189">Bestaande regels weergeven</span><span class="sxs-lookup"><span data-stu-id="a2d08-189">View existing rules</span></span>

<span data-ttu-id="a2d08-190">Als u alle bestaande aangepaste detectieregels wilt weergeven, navigeert u naar**Detecties voor aangepaste** **jacht** > .</span><span class="sxs-lookup"><span data-stu-id="a2d08-190">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="a2d08-191">De pagina bevat alle regels met de volgende run informatie:</span><span class="sxs-lookup"><span data-stu-id="a2d08-191">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="a2d08-192">**Laatste run** : wanneer een regel voor het laatst is uitgevoerd om te controleren op queryovereenkomsten en waarschuwingen te genereren</span><span class="sxs-lookup"><span data-stu-id="a2d08-192">**Last run** — when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="a2d08-193">**Status van laatste run** : of een regel is uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="a2d08-193">**Last run status** — whether a rule ran successfully</span></span>
- <span data-ttu-id="a2d08-194">**Volgende run** — de volgende geplande run</span><span class="sxs-lookup"><span data-stu-id="a2d08-194">**Next run** — the next scheduled run</span></span>
- <span data-ttu-id="a2d08-195">**Status** — of een regel is in- of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="a2d08-195">**Status** — whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="a2d08-196">Regeldetails weergeven, regel wijzigen en regel uitvoeren</span><span class="sxs-lookup"><span data-stu-id="a2d08-196">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="a2d08-197">Als u uitgebreide informatie over een aangepaste detectieregel wilt weergeven, selecteert u de naam van de regel in de lijst met regels in **Detecties voor aangepaste** > **jacht**.</span><span class="sxs-lookup"><span data-stu-id="a2d08-197">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="a2d08-198">Hiermee wordt een pagina geopend over de aangepaste detectieregel met algemene informatie over de regel, inclusief de details van de waarschuwing, de status van de uitvoeren en het bereik.</span><span class="sxs-lookup"><span data-stu-id="a2d08-198">This opens a page about the custom detection rule with general information about the rule, including the details of the alert, run status, and scope.</span></span> <span data-ttu-id="a2d08-199">Het biedt ook de lijst met geactiveerde waarschuwingen en geactiveerde acties.</span><span class="sxs-lookup"><span data-stu-id="a2d08-199">It also provides the list of triggered alerts and triggered actions.</span></span>

<span data-ttu-id="a2d08-200">![Pagina Met aangepaste detectieregeldetails](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="a2d08-200">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="a2d08-201">*Aangepaste detectieregeldetails*</span><span class="sxs-lookup"><span data-stu-id="a2d08-201">*Custom detection rule details*</span></span>

<span data-ttu-id="a2d08-202">Op deze pagina u ook de volgende acties op de regel uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="a2d08-202">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="a2d08-203">**Uitvoeren** : voer de regel onmiddellijk uit.</span><span class="sxs-lookup"><span data-stu-id="a2d08-203">**Run** — run the rule immediately.</span></span> <span data-ttu-id="a2d08-204">Hiermee wordt ook het interval voor de volgende run gereset.</span><span class="sxs-lookup"><span data-stu-id="a2d08-204">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="a2d08-205">**Bewerken** : de regel wijzigen zonder de query te wijzigen</span><span class="sxs-lookup"><span data-stu-id="a2d08-205">**Edit** — modify the rule without changing the query</span></span>
- <span data-ttu-id="a2d08-206">**Query wijzigen** — de query bewerken in geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="a2d08-206">**Modify query** — edit the query in advanced hunting</span></span>
- <span data-ttu-id="a2d08-207">**Uitschakelen inschakelen** / **Turn off** — de regel inschakelen of stoppen met werken</span><span class="sxs-lookup"><span data-stu-id="a2d08-207">**Turn on** / **Turn off** — enable the rule or stop it from running</span></span>
- <span data-ttu-id="a2d08-208">**Verwijderen** — de regel uitschakelen en verwijderen</span><span class="sxs-lookup"><span data-stu-id="a2d08-208">**Delete** — turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="a2d08-209">Geactiveerde waarschuwingen weergeven en beheren</span><span class="sxs-lookup"><span data-stu-id="a2d08-209">View and manage triggered alerts</span></span>

<span data-ttu-id="a2d08-210">Ga in het scherm regeldetails **(Aangepaste** > **detecties** > **zoeken [Regelnaam]** naar **Geactiveerde waarschuwingen** om de lijst met waarschuwingen te bekijken die worden gegenereerd door overeenkomsten met de regel.</span><span class="sxs-lookup"><span data-stu-id="a2d08-210">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered alerts** to view the list of alerts generated by matches to the rule.</span></span> <span data-ttu-id="a2d08-211">Selecteer een waarschuwing om gedetailleerde informatie over die waarschuwing weer te geven en de volgende acties uit te voeren op die waarschuwing:</span><span class="sxs-lookup"><span data-stu-id="a2d08-211">Select an alert to view detailed information about that alert and take the following actions on that alert:</span></span>

- <span data-ttu-id="a2d08-212">De waarschuwing beheren door de status en classificatie in te stellen (true of false alert)</span><span class="sxs-lookup"><span data-stu-id="a2d08-212">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="a2d08-213">De waarschuwing koppelen aan een incident</span><span class="sxs-lookup"><span data-stu-id="a2d08-213">Link the alert to an incident</span></span>
- <span data-ttu-id="a2d08-214">Voer de query uit die de waarschuwing heeft geactiveerd bij geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="a2d08-214">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="a2d08-215">Acties bekijken</span><span class="sxs-lookup"><span data-stu-id="a2d08-215">Review actions</span></span>
<span data-ttu-id="a2d08-216">Ga in het scherm regeldetails **(Aangepaste** > **detecties** > **zoeken [Regelnaam]** naar **Geactiveerde acties** om de lijst met acties te bekijken die zijn uitgevoerd op basis van overeenkomsten met de regel.</span><span class="sxs-lookup"><span data-stu-id="a2d08-216">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions** to view the list of actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="a2d08-217">Als u snel informatie wilt weergeven en actie wilt ondernemen voor een item in een tabel, gebruikt u de selectiekolom [&#10003;] links van de tabel.</span><span class="sxs-lookup"><span data-stu-id="a2d08-217">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="a2d08-218">Gerelateerd onderwerp</span><span class="sxs-lookup"><span data-stu-id="a2d08-218">Related topic</span></span>
- [<span data-ttu-id="a2d08-219">Overzicht van aangepaste detecties</span><span class="sxs-lookup"><span data-stu-id="a2d08-219">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="a2d08-220">Geavanceerd jachtoverzicht</span><span class="sxs-lookup"><span data-stu-id="a2d08-220">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a2d08-221">Leer de geavanceerde jachtquerytaal</span><span class="sxs-lookup"><span data-stu-id="a2d08-221">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
