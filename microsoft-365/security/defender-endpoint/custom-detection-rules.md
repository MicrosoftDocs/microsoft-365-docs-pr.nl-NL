---
title: Aangepaste detectieregels maken in Microsoft Defender ATP
ms.reviewer: ''
description: Meer informatie over het maken van aangepaste detectieregels op basis van geavanceerde zoekquery's
keywords: aangepaste detecties, maken, beheren, waarschuwingen, bewerken, uitvoeren op aanvraag, frequentie, interval, detectieregels, geavanceerd zoeken, jagen, query, antwoordacties, mdatp, microsoft defender atp
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
ms.openlocfilehash: fc4c15d2e391176ed0b4420c13fb865674da0361
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163585"
---
# <a name="create-custom-detection-rules"></a><span data-ttu-id="88d70-104">Aangepaste detectieregels maken</span><span class="sxs-lookup"><span data-stu-id="88d70-104">Create custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="88d70-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="88d70-105">**Applies to:**</span></span>
- [<span data-ttu-id="88d70-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="88d70-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="88d70-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88d70-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="88d70-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="88d70-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="88d70-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="88d70-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="88d70-110">Met aangepaste detectieregels die zijn gebaseerd op geavanceerde zoekquery's, kunt u proactief verschillende gebeurtenissen en systeemstaten controleren, waaronder vermoedelijke inbreukactiviteit en verkeerd geconfigureerde apparaten. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="88d70-110">Custom detection rules built from [advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="88d70-111">U kunt instellen dat ze regelmatig worden uitgevoerd, waarschuwingen genereren en antwoordacties uitvoeren wanneer er overeenkomsten zijn.</span><span class="sxs-lookup"><span data-stu-id="88d70-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="88d70-112">Lees dit artikel voor meer informatie over het maken van nieuwe aangepaste detectieregels.</span><span class="sxs-lookup"><span data-stu-id="88d70-112">Read this article to learn how to create new custom detection rules.</span></span> <span data-ttu-id="88d70-113">Of [bekijk bestaande regels weergeven en beheren.](custom-detections-manage.md)</span><span class="sxs-lookup"><span data-stu-id="88d70-113">Or [see viewing and managing existing rules](custom-detections-manage.md).</span></span>

> [!NOTE]
> <span data-ttu-id="88d70-114">Als u aangepaste detecties wilt maken of beheren, [moet uw](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) rol de machtiging **beveiligingsinstellingen** beheren hebben.</span><span class="sxs-lookup"><span data-stu-id="88d70-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="1-prepare-the-query"></a><span data-ttu-id="88d70-115">1. De query voorbereiden.</span><span class="sxs-lookup"><span data-stu-id="88d70-115">1. Prepare the query.</span></span>

<span data-ttu-id="88d70-116">Ga in het Microsoft Defender-beveiligingscentrum naar **Geavanceerd zoeken** en selecteer een bestaande query of maak een nieuwe query.</span><span class="sxs-lookup"><span data-stu-id="88d70-116">In Microsoft Defender Security Center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="88d70-117">Wanneer u een nieuwe query gebruikt, moet u de query uitvoeren om fouten te identificeren en mogelijke resultaten te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="88d70-117">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="88d70-118">Als u wilt voorkomen dat de service te veel waarschuwingen retourneert, is elke regel beperkt tot het genereren van slechts 100 waarschuwingen wanneer deze wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="88d70-118">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="88d70-119">Voordat u een regel maakt, kunt u de query aanpassen om te voorkomen dat u een waarschuwing voor normale, dagelijkse activiteiten uitvoert.</span><span class="sxs-lookup"><span data-stu-id="88d70-119">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>

### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="88d70-120">Vereiste kolommen in de queryresultaten</span><span class="sxs-lookup"><span data-stu-id="88d70-120">Required columns in the query results</span></span>

<span data-ttu-id="88d70-121">Als u een query wilt gebruiken voor een aangepaste detectieregel, moet de query de volgende kolommen retourneren:</span><span class="sxs-lookup"><span data-stu-id="88d70-121">To use a query for a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- `DeviceId`
- `ReportId`

<span data-ttu-id="88d70-122">Eenvoudige query's, zoals query's die de operator of operator niet gebruiken om resultaten aan te passen of te aggregeren, retourneert meestal `project` `summarize` deze algemene kolommen.</span><span class="sxs-lookup"><span data-stu-id="88d70-122">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="88d70-123">Er zijn verschillende manieren om ervoor te zorgen dat complexere query's deze kolommen retourneren.</span><span class="sxs-lookup"><span data-stu-id="88d70-123">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="88d70-124">Als u bijvoorbeeld de voorkeur geeft aan aggregeren en tellen op , kunt u ze nog steeds retourneren en deze verkrijgen van de meest recente gebeurtenis waarbij elk `DeviceId` `Timestamp` apparaat is `ReportId` betrokken.</span><span class="sxs-lookup"><span data-stu-id="88d70-124">For example, if you prefer to aggregate and count by `DeviceId`, you can still return `Timestamp` and `ReportId` by getting them from the most recent event involving each device.</span></span>

<span data-ttu-id="88d70-125">De voorbeeldquery hieronder telt het aantal unieke apparaten () met antivirusdetecties en gebruikt deze om alleen die apparaten met meer dan `DeviceId` vijf detecties te vinden.</span><span class="sxs-lookup"><span data-stu-id="88d70-125">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this to find only those devices with more than five detections.</span></span> <span data-ttu-id="88d70-126">Als u de meest recente `Timestamp` en de bijbehorende `ReportId` functie wilt retourneren, wordt de `summarize` operator met de functie `arg_max` gebruikt.</span><span class="sxs-lookup"><span data-stu-id="88d70-126">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="88d70-127">Voor betere queryprestaties stelt u een tijdfilter in dat overeenkomt met de geplande runfrequentie voor de regel.</span><span class="sxs-lookup"><span data-stu-id="88d70-127">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="88d70-128">Aangezien de minst voorkomende run elke 24 uur is, worden alle nieuwe gegevens bestrijken door te filteren op de afgelopen dag.</span><span class="sxs-lookup"><span data-stu-id="88d70-128">Since the least frequent run is every 24 hours, filtering for the past day will cover all new data.</span></span>

## <a name="2-create-a-new-rule-and-provide-alert-details"></a><span data-ttu-id="88d70-129">2. Maak een nieuwe regel en geef waarschuwingsdetails op.</span><span class="sxs-lookup"><span data-stu-id="88d70-129">2. Create a new rule and provide alert details.</span></span>

<span data-ttu-id="88d70-130">Met de query in de queryeditor selecteert u **Detectieregel maken** en geeft u de volgende waarschuwingsdetails op:</span><span class="sxs-lookup"><span data-stu-id="88d70-130">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="88d70-131">**Detectienaam**:naam van de detectieregel</span><span class="sxs-lookup"><span data-stu-id="88d70-131">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="88d70-132">**Frequentie:** interval voor het uitvoeren van de query en het uitvoeren van actie.</span><span class="sxs-lookup"><span data-stu-id="88d70-132">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="88d70-133">Zie aanvullende richtlijnen hieronder</span><span class="sxs-lookup"><span data-stu-id="88d70-133">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="88d70-134">**Waarschuwingstitel**: titel weergegeven met waarschuwingen die door de regel worden geactiveerd</span><span class="sxs-lookup"><span data-stu-id="88d70-134">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="88d70-135">**Ernst : potentieel** risico van het onderdeel of de activiteit die door de regel is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="88d70-135">**Severity**—potential risk of the component or activity identified by the rule.</span></span> [<span data-ttu-id="88d70-136">Lees meer over ernst van waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="88d70-136">Read about alert severities</span></span>](alerts-queue.md#severity)
- <span data-ttu-id="88d70-137">**Categorie**(type bedreigingsonderdeel of -activiteit, indien van het type).</span><span class="sxs-lookup"><span data-stu-id="88d70-137">**Category**—type of threat component or activity, if any.</span></span> [<span data-ttu-id="88d70-138">Meer informatie over waarschuwingscategorieën</span><span class="sxs-lookup"><span data-stu-id="88d70-138">Read about alert categories</span></span>](alerts-queue.md#understanding-alert-categories)
- <span data-ttu-id="88d70-139">**MITRE ATT&CK-technieken**: een of meer aanvalstechnieken die door de regel zijn geïdentificeerd, zoals beschreven in het MITRE ATT-&CK-framework.</span><span class="sxs-lookup"><span data-stu-id="88d70-139">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the MITRE ATT&CK framework.</span></span> <span data-ttu-id="88d70-140">Deze sectie is niet beschikbaar met bepaalde waarschuwingscategorieën, zoals malware, ransomware, verdachte activiteiten en ongewenste software</span><span class="sxs-lookup"><span data-stu-id="88d70-140">This section is not available with certain alert categories, such as malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="88d70-141">**Beschrijving**: meer informatie over het onderdeel of de activiteit die door de regel is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="88d70-141">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="88d70-142">**Aanbevolen acties**: aanvullende acties die reageren op een waarschuwing</span><span class="sxs-lookup"><span data-stu-id="88d70-142">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

<span data-ttu-id="88d70-143">Lees meer over de waarschuwingswachtrij voor meer informatie over hoe waarschuwingsgegevens [worden weergegeven.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="88d70-143">For more information about how alert details are displayed, [read about the alert queue](alerts-queue.md).</span></span>

### <a name="rule-frequency"></a><span data-ttu-id="88d70-144">Regelfrequentie</span><span class="sxs-lookup"><span data-stu-id="88d70-144">Rule frequency</span></span>

<span data-ttu-id="88d70-145">Wanneer u deze opgeslagen hebt, wordt er onmiddellijk een nieuwe aangepaste detectieregel uitgevoerd en wordt gecontroleerd op overeenkomsten uit de afgelopen 30 dagen met gegevens.</span><span class="sxs-lookup"><span data-stu-id="88d70-145">When saved, a new custom detection rule immediately runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="88d70-146">De regel wordt vervolgens opnieuw uitgevoerd met vaste intervallen en duur van terugkijken op basis van de frequentie die u kiest:</span><span class="sxs-lookup"><span data-stu-id="88d70-146">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="88d70-147">**Elke 24 uur :** wordt elke 24 uur uitgevoerd en controleert gegevens uit de afgelopen 30 dagen</span><span class="sxs-lookup"><span data-stu-id="88d70-147">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="88d70-148">**Elke 12 uur :** wordt elke 12 uur uitgevoerd en controleert gegevens uit de afgelopen 24 uur</span><span class="sxs-lookup"><span data-stu-id="88d70-148">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="88d70-149">**Elke 3 uur :** wordt elke 3 uur uitgevoerd en controleert gegevens uit de afgelopen 6 uur</span><span class="sxs-lookup"><span data-stu-id="88d70-149">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="88d70-150">**Elk uur**: wordt elk uur uitgevoerd en de gegevens van de afgelopen 2 uur worden gecontroleerd</span><span class="sxs-lookup"><span data-stu-id="88d70-150">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88d70-151">Bij het wijzigen van een query die al is gepland als aangepaste detectie, heeft de volgende onmiddellijke uitvoering een terugblikvenster van 30 dagen, precies alsof er een nieuwe query wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="88d70-151">When changing a query that is already scheduled as a Custom Detection, it's next immediate execution will have a lookback window of 30 days, exactly as if a new query was being created.</span></span> <span data-ttu-id="88d70-152">Wijzigingen in een groot aantal query's en met tijdfilters die hoger zijn dan de standaardterugslagduur voor de geselecteerde frequentie, kan dit van invloed zijn op het totale quotumverbruik van Advanced Hunting, waardoor het dagelijkse quotum wordt uitputtend.</span><span class="sxs-lookup"><span data-stu-id="88d70-152">Changes to a large number of queries, and with time filters higher than the default lookback duration for the selected frequency, might have an impact in the overall quota consumption of Advanced Hunting and resulting in exhausting the daily quota.</span></span>

> [!TIP]
> <span data-ttu-id="88d70-153">De tijdfilters in de query overeenkomen met de duur van de terugblik.</span><span class="sxs-lookup"><span data-stu-id="88d70-153">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="88d70-154">Resultaten buiten de terugblikduur worden genegeerd.</span><span class="sxs-lookup"><span data-stu-id="88d70-154">Results outside of the lookback duration are ignored.</span></span>

<span data-ttu-id="88d70-155">Selecteer de frequentie die overeenkomt met de manier waarop u detecties wilt controleren en houd rekening met de capaciteit van uw organisatie om op de waarschuwingen te reageren.</span><span class="sxs-lookup"><span data-stu-id="88d70-155">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

## <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="88d70-156">3. Kies de beïnvloede entiteiten.</span><span class="sxs-lookup"><span data-stu-id="88d70-156">3. Choose the impacted entities.</span></span>

<span data-ttu-id="88d70-157">Identificeer de kolommen in de queryresultaten waar u de belangrijkste beïnvloede of beïnvloede entiteit verwacht te vinden.</span><span class="sxs-lookup"><span data-stu-id="88d70-157">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="88d70-158">Een query kan bijvoorbeeld zowel apparaat- als gebruikers-ID's retourneren.</span><span class="sxs-lookup"><span data-stu-id="88d70-158">For example, a query might return both device and user IDs.</span></span> <span data-ttu-id="88d70-159">Door te bepalen welke van deze kolommen de belangrijkste beïnvloede entiteit vertegenwoordigt, kan de service relevante waarschuwingen, correlerende incidenten en doelreactieacties aggregeren.</span><span class="sxs-lookup"><span data-stu-id="88d70-159">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="88d70-160">U kunt slechts één kolom selecteren voor elk entiteitstype.</span><span class="sxs-lookup"><span data-stu-id="88d70-160">You can select only one column for each entity type.</span></span> <span data-ttu-id="88d70-161">Kolommen die niet door uw query worden geretourneerd, kunnen niet worden geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="88d70-161">Columns that are not returned by your query can't be selected.</span></span>

## <a name="4-specify-actions"></a><span data-ttu-id="88d70-162">4. Geef acties op.</span><span class="sxs-lookup"><span data-stu-id="88d70-162">4. Specify actions.</span></span>

<span data-ttu-id="88d70-163">Uw aangepaste detectieregel kan automatisch acties uitvoeren op bestanden of apparaten die door de query worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="88d70-163">Your custom detection rule can automatically take actions on files or devices that are returned by the query.</span></span>

### <a name="actions-on-devices"></a><span data-ttu-id="88d70-164">Acties op apparaten</span><span class="sxs-lookup"><span data-stu-id="88d70-164">Actions on devices</span></span>

<span data-ttu-id="88d70-165">Deze acties worden toegepast op apparaten in de `DeviceId` kolom van de queryresultaten:</span><span class="sxs-lookup"><span data-stu-id="88d70-165">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>

- <span data-ttu-id="88d70-166">**Isolatieapparaat:** hiermee wordt volledige netwerkisolatie toegepast, waardoor het apparaat geen verbinding kan maken met een toepassing of service, met uitzondering van de Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="88d70-166">**Isolate device**—applies full network isolation, preventing the device from connecting to any application or service, except for the Defender for Endpoint service.</span></span> [<span data-ttu-id="88d70-167">Meer informatie over apparaatisolatie</span><span class="sxs-lookup"><span data-stu-id="88d70-167">Learn more about device isolation</span></span>](respond-machine-alerts.md#isolate-devices-from-the-network)
- <span data-ttu-id="88d70-168">**Verzamel onderzoekspakket:** verzamelt apparaatgegevens in een ZIP-bestand.</span><span class="sxs-lookup"><span data-stu-id="88d70-168">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="88d70-169">Meer informatie over het onderzoekspakket</span><span class="sxs-lookup"><span data-stu-id="88d70-169">Learn more about the investigation package</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- <span data-ttu-id="88d70-170">**Antivirusscan uitvoeren**: voert een volledige Microsoft Defender Antivirus-scan uit op het apparaat</span><span class="sxs-lookup"><span data-stu-id="88d70-170">**Run antivirus scan**—performs a full Microsoft Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="88d70-171">**Onderzoek starten**: start een [geautomatiseerd onderzoek](automated-investigations.md) op het apparaat</span><span class="sxs-lookup"><span data-stu-id="88d70-171">**Initiate investigation**—starts an [automated investigation](automated-investigations.md) on the device</span></span>
- <span data-ttu-id="88d70-172">**De uitvoering van apps** beperken: stelt beperkingen in op het apparaat om alleen bestanden toe te staan die zijn ondertekend met een door Microsoft uitgegeven certificaat.</span><span class="sxs-lookup"><span data-stu-id="88d70-172">**Restrict app execution**—sets restrictions on the device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="88d70-173">Meer informatie over het beperken van het uitvoeren van apps</span><span class="sxs-lookup"><span data-stu-id="88d70-173">Learn more about restricting app execution</span></span>](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a><span data-ttu-id="88d70-174">Acties op bestanden</span><span class="sxs-lookup"><span data-stu-id="88d70-174">Actions on files</span></span>

<span data-ttu-id="88d70-175">Deze acties worden toegepast op bestanden in de `SHA1` of de kolom van de `InitiatingProcessSHA1` queryresultaten:</span><span class="sxs-lookup"><span data-stu-id="88d70-175">These actions are applied to files in the `SHA1` or the `InitiatingProcessSHA1` column of the query results:</span></span>

- <span data-ttu-id="88d70-176">**Toestaan/blokkeren:** hiermee wordt het bestand automatisch toegevoegd aan de lijst met aangepaste [indicators,](manage-indicators.md) zodat het bestand altijd kan worden uitgevoerd of geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="88d70-176">**Allow/Block**—automatically adds the file to your [custom indicator list](manage-indicators.md) so that it is always allowed to run or blocked from running.</span></span> <span data-ttu-id="88d70-177">U kunt het bereik van deze actie zo instellen dat deze alleen wordt genomen voor geselecteerde apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="88d70-177">You can set the scope of this action so that it is taken only on selected device groups.</span></span> <span data-ttu-id="88d70-178">Dit bereik is onafhankelijk van het bereik van de regel.</span><span class="sxs-lookup"><span data-stu-id="88d70-178">This scope is independent of the scope of the rule.</span></span>
- <span data-ttu-id="88d70-179">**Quarantainebestand**: verwijdert het bestand van de huidige locatie en plaatst een kopie in quarantaine</span><span class="sxs-lookup"><span data-stu-id="88d70-179">**Quarantine file**—deletes the file from its current location and places a copy in quarantine</span></span>

### <a name="actions-on-users"></a><span data-ttu-id="88d70-180">Acties voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="88d70-180">Actions on users</span></span>

- <span data-ttu-id="88d70-181">**Als gebruiker markeren als gecompromitteerd:** hiermee wordt het risiconiveau van de gebruiker in Azure Active Directory op 'hoog' gebracht, wat het bijbehorende [identiteitsbeveiligingsbeleid activeert.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)</span><span class="sxs-lookup"><span data-stu-id="88d70-181">**Mark user as compromised**—sets the user's risk level to "high" in Azure Active Directory, triggering the corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels).</span></span>

## <a name="5-set-the-rule-scope"></a><span data-ttu-id="88d70-182">5. Stel het regelbereik in.</span><span class="sxs-lookup"><span data-stu-id="88d70-182">5. Set the rule scope.</span></span>

<span data-ttu-id="88d70-183">Stel het bereik in om op te geven welke apparaten onder de regel vallen:</span><span class="sxs-lookup"><span data-stu-id="88d70-183">Set the scope to specify which devices are covered by the rule:</span></span>

- <span data-ttu-id="88d70-184">Alle apparaten</span><span class="sxs-lookup"><span data-stu-id="88d70-184">All devices</span></span>
- <span data-ttu-id="88d70-185">Specifieke apparaatgroepen</span><span class="sxs-lookup"><span data-stu-id="88d70-185">Specific device groups</span></span>

<span data-ttu-id="88d70-186">Alleen gegevens van apparaten in bereik worden opgevraagd.</span><span class="sxs-lookup"><span data-stu-id="88d70-186">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="88d70-187">Acties worden ook alleen op die apparaten ondernomen.</span><span class="sxs-lookup"><span data-stu-id="88d70-187">Also, actions will be taken only on those devices.</span></span>

## <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="88d70-188">6. Controleer de regel en schakel deze in.</span><span class="sxs-lookup"><span data-stu-id="88d70-188">6. Review and turn on the rule.</span></span>

<span data-ttu-id="88d70-189">Nadat u de regel heeft beoordeeld, **selecteert u Maken om** deze op te slaan.</span><span class="sxs-lookup"><span data-stu-id="88d70-189">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="88d70-190">De aangepaste detectieregel wordt onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="88d70-190">The custom detection rule immediately runs.</span></span> <span data-ttu-id="88d70-191">Deze wordt opnieuw uitgevoerd op basis van de geconfigureerde frequentie om te controleren op overeenkomsten, waarschuwingen te genereren en antwoordacties uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="88d70-191">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

<span data-ttu-id="88d70-192">U kunt [aangepaste detectieregels weergeven en beheren,](custom-detections-manage.md)de vorige runs controleren en de waarschuwingen controleren die ze hebben geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="88d70-192">You can [view and manage custom detection rules](custom-detections-manage.md), check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="88d70-193">U kunt ook een regel op aanvraag uitvoeren en deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="88d70-193">You can also run a rule on demand and modify it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="88d70-194">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="88d70-194">Related topics</span></span>

- [<span data-ttu-id="88d70-195">Aangepaste detectieregels weergeven en beheren</span><span class="sxs-lookup"><span data-stu-id="88d70-195">View and manage custom detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="88d70-196">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="88d70-196">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="88d70-197">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="88d70-197">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="88d70-198">De geavanceerde zoekquerytaal leren</span><span class="sxs-lookup"><span data-stu-id="88d70-198">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="88d70-199">Waarschuwingen weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="88d70-199">View and organize alerts</span></span>](alerts-queue.md)
