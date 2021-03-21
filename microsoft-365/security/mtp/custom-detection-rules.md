---
title: Aangepaste detectieregels maken en beheren in Microsoft 365 Defender
description: Informatie over het maken en beheren van aangepaste detectieregels op basis van geavanceerde zoekquery's
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, rules, schema, kusto, microsoft 365, Microsoft Threat Protection, RBAC, permissions, Microsoft Defender ATP
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
ms.openlocfilehash: ed1eeb29119d477673bb04d9474bd38438db9fd9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928938"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="663e1-104">Aangepaste detectieregels maken en beheren</span><span class="sxs-lookup"><span data-stu-id="663e1-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="663e1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="663e1-105">**Applies to:**</span></span>
- <span data-ttu-id="663e1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="663e1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="663e1-107">Aangepaste detectieregels zijn regels die u kunt ontwerpen en aanpassen met behulp van [geavanceerde zoekquery's.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="663e1-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="663e1-108">Met deze regels kunt u proactief verschillende gebeurtenissen en systeemstaten controleren, waaronder verdachte inbreukactiviteiten en verkeerd geconfigureerde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="663e1-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="663e1-109">U kunt instellen dat ze regelmatig worden uitgevoerd, waarschuwingen genereren en antwoordacties uitvoeren wanneer er overeenkomsten zijn.</span><span class="sxs-lookup"><span data-stu-id="663e1-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="663e1-110">Vereiste machtigingen voor het beheren van aangepaste detecties</span><span class="sxs-lookup"><span data-stu-id="663e1-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="663e1-111">Als u aangepaste detecties wilt beheren, moet u een van de volgende rollen krijgen:</span><span class="sxs-lookup"><span data-stu-id="663e1-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="663e1-112">**Beveiligingsbeheerder:** gebruikers met deze [Azure Active Directory-rol](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kunnen beveiligingsinstellingen beheren in het Microsoft 365-beveiligingscentrum en andere portals en services.</span><span class="sxs-lookup"><span data-stu-id="663e1-112">**Security administrator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="663e1-113">**Beveiligingsoperator:** gebruikers met deze [Azure Active Directory-rol](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kunnen waarschuwingen beheren en hebben globale alleen-lezen toegang tot beveiligingsfuncties, inclusief alle informatie in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="663e1-113">**Security operator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="663e1-114">Deze rol is alleen voldoende voor het beheren van aangepaste detecties als RBAC (Role Based Access Control) is uitgeschakeld in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="663e1-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="663e1-115">Als u RBAC hebt geconfigureerd,  hebt u ook de machtiging beveiligingsinstellingen voor Defender voor Eindpunt nodig.</span><span class="sxs-lookup"><span data-stu-id="663e1-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="663e1-116">Als u vereiste machtigingen wilt beheren, kan een **globale beheerder** het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="663e1-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="663e1-117">Wijs de **rol van de** beveiligingsbeheerder of **beveiligingsoperator** toe in [het Microsoft 365-beheercentrum](https://admin.microsoft.com/) onder   >  **Rollenbeveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="663e1-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="663e1-118">Controleer RBAC-instellingen voor Microsoft Defender voor Eindpunt in [het Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com/) onder **Instellingen**  >  **Machtigingen**  >  **Rollen**.</span><span class="sxs-lookup"><span data-stu-id="663e1-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="663e1-119">Selecteer de bijbehorende rol om de machtiging **beveiligingsinstellingen beheren toe te** wijzen.</span><span class="sxs-lookup"><span data-stu-id="663e1-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="663e1-120">Als u aangepaste detecties wilt  beheren, hebben **beveiligingsoperatoren** de machtiging beveiligingsinstellingen in Microsoft Defender voor Eindpunt nodig als RBAC is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="663e1-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="663e1-121">Een aangepaste detectieregel maken</span><span class="sxs-lookup"><span data-stu-id="663e1-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="663e1-122">1. De query voorbereiden.</span><span class="sxs-lookup"><span data-stu-id="663e1-122">1. Prepare the query.</span></span>

<span data-ttu-id="663e1-123">Ga in het Microsoft 365-beveiligingscentrum naar Geavanceerd **zoeken** en selecteer een bestaande query of maak een nieuwe query.</span><span class="sxs-lookup"><span data-stu-id="663e1-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="663e1-124">Wanneer u een nieuwe query gebruikt, moet u de query uitvoeren om fouten te identificeren en mogelijke resultaten te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="663e1-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="663e1-125">Als u wilt voorkomen dat de service te veel waarschuwingen retourneert, is elke regel beperkt tot het genereren van slechts 100 waarschuwingen wanneer deze wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="663e1-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="663e1-126">Voordat u een regel maakt, kunt u de query aanpassen om te voorkomen dat u een waarschuwing voor normale, dagelijkse activiteiten uitvoert.</span><span class="sxs-lookup"><span data-stu-id="663e1-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="663e1-127">Vereiste kolommen in de queryresultaten</span><span class="sxs-lookup"><span data-stu-id="663e1-127">Required columns in the query results</span></span>
<span data-ttu-id="663e1-128">Als u een aangepaste detectieregel wilt maken, moet de query de volgende kolommen retourneren:</span><span class="sxs-lookup"><span data-stu-id="663e1-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="663e1-129">`Timestamp`—gebruikt om de tijdstempel in te stellen voor gegenereerde waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="663e1-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="663e1-130">`ReportId`—hiermee kunt u opzoekingen voor de oorspronkelijke records in</span><span class="sxs-lookup"><span data-stu-id="663e1-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="663e1-131">Een van de volgende kolommen die specifieke apparaten, gebruikers of postvakken identificeren:</span><span class="sxs-lookup"><span data-stu-id="663e1-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="663e1-132">`SenderFromAddress` (afzender van envelop of Return-Path adres)</span><span class="sxs-lookup"><span data-stu-id="663e1-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="663e1-133">`SenderMailFromAddress` (afzenderadres weergegeven door e-mailclient)</span><span class="sxs-lookup"><span data-stu-id="663e1-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="663e1-134">Ondersteuning voor extra entiteiten wordt toegevoegd als er nieuwe tabellen worden toegevoegd aan het [geavanceerde schema voor de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="663e1-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="663e1-135">Eenvoudige query's, zoals query's die de operator of operator niet gebruiken om resultaten aan te passen of te aggregeren, retourneert meestal `project` `summarize` deze algemene kolommen.</span><span class="sxs-lookup"><span data-stu-id="663e1-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="663e1-136">Er zijn verschillende manieren om ervoor te zorgen dat complexere query's deze kolommen retourneren.</span><span class="sxs-lookup"><span data-stu-id="663e1-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="663e1-137">Als u bijvoorbeeld liever wilt aggregeren en tellen per entiteit onder een kolom zoals , kunt u deze nog steeds retourneren en deze verkrijgen van de meest recente gebeurtenis waarbij elke unieke gebeurtenis `DeviceId` `Timestamp` betrokken `ReportId` `DeviceId` is.</span><span class="sxs-lookup"><span data-stu-id="663e1-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="663e1-138">De voorbeeldquery hieronder telt het aantal unieke apparaten () met antivirusdetecties en gebruikt dit aantal om alleen de apparaten met meer dan `DeviceId` vijf detecties te vinden.</span><span class="sxs-lookup"><span data-stu-id="663e1-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="663e1-139">Als u de meest recente `Timestamp` en de bijbehorende `ReportId` functie wilt retourneren, wordt de `summarize` operator met de functie `arg_max` gebruikt.</span><span class="sxs-lookup"><span data-stu-id="663e1-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="663e1-140">Voor betere queryprestaties stelt u een tijdfilter in dat overeenkomt met de geplande runfrequentie voor de regel.</span><span class="sxs-lookup"><span data-stu-id="663e1-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="663e1-141">Aangezien de minst voorkomende run elke _24 uur_ is, worden alle nieuwe gegevens bestrijken door te filteren op de afgelopen dag.</span><span class="sxs-lookup"><span data-stu-id="663e1-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="663e1-142">2. Maak een nieuwe regel en geef waarschuwingsdetails op.</span><span class="sxs-lookup"><span data-stu-id="663e1-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="663e1-143">Met de query in de queryeditor selecteert u **Detectieregel maken** en geeft u de volgende waarschuwingsdetails op:</span><span class="sxs-lookup"><span data-stu-id="663e1-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="663e1-144">**Detectienaam**:naam van de detectieregel</span><span class="sxs-lookup"><span data-stu-id="663e1-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="663e1-145">**Frequentie:** interval voor het uitvoeren van de query en het uitvoeren van actie.</span><span class="sxs-lookup"><span data-stu-id="663e1-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="663e1-146">Zie aanvullende richtlijnen hieronder</span><span class="sxs-lookup"><span data-stu-id="663e1-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="663e1-147">**Waarschuwingstitel**: titel weergegeven met waarschuwingen die door de regel worden geactiveerd</span><span class="sxs-lookup"><span data-stu-id="663e1-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="663e1-148">**Ernst :** potentieel risico van het onderdeel of de activiteit die door de regel is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="663e1-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="663e1-149">**Categorie**:bedreigingscomponent of activiteit die door de regel is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="663e1-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="663e1-150">**MITRE ATT&CK-technieken**( een of meer aanvalstechnieken die door de regel zijn geïdentificeerd zoals beschreven in het [MITRE ATT-&CK-framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="663e1-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="663e1-151">Deze sectie is verborgen voor bepaalde waarschuwingscategorieën, waaronder malware, ransomware, verdachte activiteiten en ongewenste software</span><span class="sxs-lookup"><span data-stu-id="663e1-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="663e1-152">**Beschrijving**: meer informatie over het onderdeel of de activiteit die door de regel is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="663e1-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="663e1-153">**Aanbevolen acties**: aanvullende acties die reageren op een waarschuwing</span><span class="sxs-lookup"><span data-stu-id="663e1-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="663e1-154">Regelfrequentie</span><span class="sxs-lookup"><span data-stu-id="663e1-154">Rule frequency</span></span>
<span data-ttu-id="663e1-155">Wanneer u een nieuwe regel ops slaan of bewerken, wordt deze uitgevoerd en gecontroleerd op overeenkomsten uit de afgelopen 30 dagen met gegevens.</span><span class="sxs-lookup"><span data-stu-id="663e1-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="663e1-156">De regel wordt vervolgens opnieuw uitgevoerd met vaste intervallen, met een terugslagduur op basis van de frequentie die u kiest:</span><span class="sxs-lookup"><span data-stu-id="663e1-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="663e1-157">**Elke 24 uur :** wordt elke 24 uur uitgevoerd en controleert gegevens uit de afgelopen 30 dagen</span><span class="sxs-lookup"><span data-stu-id="663e1-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="663e1-158">**Elke 12 uur :** wordt elke 12 uur uitgevoerd en controleert gegevens uit de afgelopen 24 uur</span><span class="sxs-lookup"><span data-stu-id="663e1-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="663e1-159">**Elke 3 uur :** wordt elke 3 uur uitgevoerd en controleert gegevens uit de afgelopen 6 uur</span><span class="sxs-lookup"><span data-stu-id="663e1-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="663e1-160">**Elk uur**: wordt elk uur uitgevoerd en de gegevens van de afgelopen 2 uur worden gecontroleerd</span><span class="sxs-lookup"><span data-stu-id="663e1-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="663e1-161">De tijdfilters in de query overeenkomen met de duur van de terugblik.</span><span class="sxs-lookup"><span data-stu-id="663e1-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="663e1-162">Resultaten buiten de terugblikduur worden genegeerd.</span><span class="sxs-lookup"><span data-stu-id="663e1-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="663e1-163">Selecteer de frequentie die overeenkomt met hoe nauw u detecties wilt controleren.</span><span class="sxs-lookup"><span data-stu-id="663e1-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="663e1-164">Houd rekening met de capaciteit van uw organisatie om op de waarschuwingen te reageren.</span><span class="sxs-lookup"><span data-stu-id="663e1-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="663e1-165">3. Kies de beïnvloede entiteiten.</span><span class="sxs-lookup"><span data-stu-id="663e1-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="663e1-166">Identificeer de kolommen in de queryresultaten waar u de belangrijkste beïnvloede of beïnvloede entiteit verwacht te vinden.</span><span class="sxs-lookup"><span data-stu-id="663e1-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="663e1-167">Een query kan bijvoorbeeld adressen van afzender `SenderFromAddress` (of `SenderMailFromAddress` ) en geadresseerde `RecipientEmailAddress` () retourneren.</span><span class="sxs-lookup"><span data-stu-id="663e1-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="663e1-168">Door te bepalen welke van deze kolommen de belangrijkste beïnvloede entiteit vertegenwoordigt, kan de service relevante waarschuwingen, correlerende incidenten en doelreactieacties aggregeren.</span><span class="sxs-lookup"><span data-stu-id="663e1-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="663e1-169">U kunt slechts één kolom selecteren voor elk entiteitstype (postvak, gebruiker of apparaat).</span><span class="sxs-lookup"><span data-stu-id="663e1-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="663e1-170">Kolommen die niet door uw query worden geretourneerd, kunnen niet worden geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="663e1-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="663e1-171">4. Geef acties op.</span><span class="sxs-lookup"><span data-stu-id="663e1-171">4. Specify actions.</span></span>
<span data-ttu-id="663e1-172">Uw aangepaste detectieregel kan automatisch acties uitvoeren op apparaten, bestanden of gebruikers die door de query worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="663e1-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="663e1-173">Acties op apparaten</span><span class="sxs-lookup"><span data-stu-id="663e1-173">Actions on devices</span></span>
<span data-ttu-id="663e1-174">Deze acties worden toegepast op apparaten in de `DeviceId` kolom van de queryresultaten:</span><span class="sxs-lookup"><span data-stu-id="663e1-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="663e1-175">**Apparaat isoleren:** hiermee wordt Microsoft Defender voor Eindpunt gebruikt om volledige netwerkisolatie toe te passen, waardoor het apparaat geen verbinding kan maken met een toepassing of service.</span><span class="sxs-lookup"><span data-stu-id="663e1-175">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="663e1-176">Meer informatie over machineisolatie van Microsoft Defender voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="663e1-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="663e1-177">**Verzamel onderzoekspakket:** verzamelt apparaatgegevens in een ZIP-bestand.</span><span class="sxs-lookup"><span data-stu-id="663e1-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="663e1-178">Meer informatie over het Microsoft Defender for Endpoint-onderzoekspakket</span><span class="sxs-lookup"><span data-stu-id="663e1-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="663e1-179">**Antivirusscan uitvoeren**: voert een volledige Windows Defender Antivirus-scan uit op het apparaat</span><span class="sxs-lookup"><span data-stu-id="663e1-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="663e1-180">**Onderzoek starten**: start een [geautomatiseerd onderzoek](mtp-autoir.md) op het apparaat</span><span class="sxs-lookup"><span data-stu-id="663e1-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="663e1-181">**De uitvoering van apps** beperken: hiermee stelt u beperkingen in op het apparaat om alleen bestanden toe te staan die zijn ondertekend met een door Microsoft uitgegeven certificaat.</span><span class="sxs-lookup"><span data-stu-id="663e1-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="663e1-182">Meer informatie over app-beperkingen met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="663e1-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="663e1-183">Acties op bestanden</span><span class="sxs-lookup"><span data-stu-id="663e1-183">Actions on files</span></span>
<span data-ttu-id="663e1-184">Wanneer geselecteerd, kunt u ervoor kiezen om de actie **Quarantainebestand** toe te passen op bestanden in `SHA1` de , of kolom van de `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` queryresultaten.</span><span class="sxs-lookup"><span data-stu-id="663e1-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="663e1-185">Met deze actie wordt het bestand van de huidige locatie verwijderd en wordt een kopie in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="663e1-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="663e1-186">Acties voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="663e1-186">Actions on users</span></span>
<span data-ttu-id="663e1-187">Wanneer deze optie **is** geselecteerd, wordt de actie Gebruiker markeren als gecompromitteerd uitgevoerd op gebruikers in de , of kolom van de `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` queryresultaten.</span><span class="sxs-lookup"><span data-stu-id="663e1-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="663e1-188">Met deze actie wordt het risiconiveau voor gebruikers in Azure Active Directory op 'hoog' gebracht, wat het [bijbehorende identiteitsbeveiligingsbeleid activeert.](/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="663e1-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="663e1-189">De actie toestaan of blokkeren voor aangepaste detectieregels wordt momenteel niet ondersteund in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="663e1-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="663e1-190">5. Stel het regelbereik in.</span><span class="sxs-lookup"><span data-stu-id="663e1-190">5. Set the rule scope.</span></span>
<span data-ttu-id="663e1-191">Stel het bereik in om op te geven welke apparaten onder de regel vallen.</span><span class="sxs-lookup"><span data-stu-id="663e1-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="663e1-192">Het bereik is van invloed op regels die apparaten controleren en hebben geen invloed op regels die alleen postvakken en gebruikersaccounts of identiteiten controleren.</span><span class="sxs-lookup"><span data-stu-id="663e1-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="663e1-193">Wanneer u het bereik instelt, kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="663e1-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="663e1-194">Alle apparaten</span><span class="sxs-lookup"><span data-stu-id="663e1-194">All devices</span></span>
- <span data-ttu-id="663e1-195">Specifieke apparaatgroepen</span><span class="sxs-lookup"><span data-stu-id="663e1-195">Specific device groups</span></span>

<span data-ttu-id="663e1-196">Alleen gegevens van apparaten in bereik worden opgevraagd.</span><span class="sxs-lookup"><span data-stu-id="663e1-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="663e1-197">Acties worden ook alleen op die apparaten ondernomen.</span><span class="sxs-lookup"><span data-stu-id="663e1-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="663e1-198">6. Controleer de regel en schakel deze in.</span><span class="sxs-lookup"><span data-stu-id="663e1-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="663e1-199">Nadat u de regel heeft beoordeeld, **selecteert u Maken om** deze op te slaan.</span><span class="sxs-lookup"><span data-stu-id="663e1-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="663e1-200">De aangepaste detectieregel wordt onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="663e1-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="663e1-201">Deze wordt opnieuw uitgevoerd op basis van de geconfigureerde frequentie om te controleren op overeenkomsten, waarschuwingen te genereren en antwoordacties uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="663e1-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>


>[!Important] 
><span data-ttu-id="663e1-202">Aangepaste detecties moeten regelmatig worden gecontroleerd op efficiëntie en effectiviteit.</span><span class="sxs-lookup"><span data-stu-id="663e1-202">Custom detections should be regularly reviewed for efficiency and effectiveness.</span></span> <span data-ttu-id="663e1-203">Als u wilt controleren of u detecties maakt die echte waarschuwingen activeren, neemt u de tijd om uw bestaande aangepaste detecties te bekijken door de stappen in Bestaande aangepaste detectieregels [beheren te volgen.](#manage-existing-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="663e1-203">To make sure you are creating detections that trigger true alerts, take time to review your existing custom detections by following the steps in [Manage existing custom detection rules](#manage-existing-custom-detection-rules).</span></span> <br>  
<span data-ttu-id="663e1-204">U behoudt de controle over de breedheid of specificiteit van uw aangepaste detecties, zodat eventuele foutmeldingen die door aangepaste detecties worden gegenereerd, kunnen aangeven dat bepaalde parameters van de regels moeten worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="663e1-204">You maintain control over the broadness or specificity of your custom detections so any false alerts generated by custom detections might indicate a need to modify certain parameters of the rules.</span></span>


## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="663e1-205">Bestaande aangepaste detectieregels beheren</span><span class="sxs-lookup"><span data-stu-id="663e1-205">Manage existing custom detection rules</span></span>
<span data-ttu-id="663e1-206">U kunt de lijst met bestaande aangepaste detectieregels bekijken, de eerdere versies controleren en de waarschuwingen bekijken die ze hebben geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="663e1-206">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="663e1-207">U kunt ook een regel op aanvraag uitvoeren en deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="663e1-207">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="663e1-208">Bestaande regels weergeven</span><span class="sxs-lookup"><span data-stu-id="663e1-208">View existing rules</span></span>

<span data-ttu-id="663e1-209">Als u alle bestaande aangepaste detectieregels wilt weergeven, gaat u naar **Aangepaste**  >  **detecties opzoeken.**</span><span class="sxs-lookup"><span data-stu-id="663e1-209">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="663e1-210">Op de pagina vindt u alle regels met de volgende gegevens:</span><span class="sxs-lookup"><span data-stu-id="663e1-210">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="663e1-211">**Laatst uitgevoerd:** wanneer een regel voor het laatst is uitgevoerd om te controleren op query's en waarschuwingen te genereren</span><span class="sxs-lookup"><span data-stu-id="663e1-211">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="663e1-212">**Status laatst uitgevoerd**: of een regel is uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="663e1-212">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="663e1-213">**Volgende run**: de volgende geplande run</span><span class="sxs-lookup"><span data-stu-id="663e1-213">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="663e1-214">**Status**, ongeacht of een regel is ingeschakeld of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="663e1-214">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="663e1-215">Regeldetails weergeven, regel wijzigen en regel uitvoeren</span><span class="sxs-lookup"><span data-stu-id="663e1-215">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="663e1-216">Als u uitgebreide informatie over een aangepaste detectieregel wilt weergeven, gaat u naar **Op** zoek naar aangepaste  >  **detecties** en selecteert u vervolgens de naam van de regel.</span><span class="sxs-lookup"><span data-stu-id="663e1-216">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="663e1-217">U kunt vervolgens algemene informatie over de regel bekijken, inclusief de status en het bereik van de regel.</span><span class="sxs-lookup"><span data-stu-id="663e1-217">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="663e1-218">De pagina bevat ook de lijst met geactiveerde waarschuwingen en acties.</span><span class="sxs-lookup"><span data-stu-id="663e1-218">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="663e1-219">![Pagina Met details van aangepaste detectieregel](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="663e1-219">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="663e1-220">*Details van aangepaste detectieregel*</span><span class="sxs-lookup"><span data-stu-id="663e1-220">*Custom detection rule details*</span></span>

<span data-ttu-id="663e1-221">U kunt ook de volgende acties uitvoeren op de regel op deze pagina:</span><span class="sxs-lookup"><span data-stu-id="663e1-221">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="663e1-222">**Uitvoeren:** voer de regel onmiddellijk uit.</span><span class="sxs-lookup"><span data-stu-id="663e1-222">**Run**—run the rule immediately.</span></span> <span data-ttu-id="663e1-223">Hiermee wordt ook het interval voor de volgende run opnieuw ingesteld.</span><span class="sxs-lookup"><span data-stu-id="663e1-223">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="663e1-224">**Bewerken**: wijzig de regel zonder de query te wijzigen</span><span class="sxs-lookup"><span data-stu-id="663e1-224">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="663e1-225">**Query wijzigen:** bewerk de query in geavanceerde zoekopdrachten</span><span class="sxs-lookup"><span data-stu-id="663e1-225">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="663e1-226">**In- en uit-**  /  **Uitschakelen :de** regel inschakelen of stoppen met uitvoeren</span><span class="sxs-lookup"><span data-stu-id="663e1-226">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="663e1-227">**Verwijderen**: schakel de regel uit en verwijder deze</span><span class="sxs-lookup"><span data-stu-id="663e1-227">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="663e1-228">Getriggerde waarschuwingen weergeven en beheren</span><span class="sxs-lookup"><span data-stu-id="663e1-228">View and manage triggered alerts</span></span>

<span data-ttu-id="663e1-229">Ga in het scherm Met regeldetails **(Op** zoek naar aangepaste  >  **detecties**  >  **[regelnaam] naar** Geactiveerde waarschuwingen , waarin de waarschuwingen worden weergegeven die worden gegenereerd door overeenkomsten met de regel.</span><span class="sxs-lookup"><span data-stu-id="663e1-229">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="663e1-230">Selecteer een waarschuwing om gedetailleerde informatie over de waarschuwing weer te geven en de volgende acties uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="663e1-230">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="663e1-231">De waarschuwing beheren door de status en classificatie in te stellen (waar of onwaar)</span><span class="sxs-lookup"><span data-stu-id="663e1-231">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="663e1-232">De waarschuwing koppelen aan een incident</span><span class="sxs-lookup"><span data-stu-id="663e1-232">Link the alert to an incident</span></span>
- <span data-ttu-id="663e1-233">Voer de query uit die de waarschuwing bij geavanceerd zoeken heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="663e1-233">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="663e1-234">Acties controleren</span><span class="sxs-lookup"><span data-stu-id="663e1-234">Review actions</span></span>
<span data-ttu-id="663e1-235">Ga in het scherm Met regeldetails **(Op** zoek naar aangepaste  >  **detecties**  >  **[regelnaam] naar** Geactiveerde acties , waarin de acties worden vermeld die zijn gemaakt op basis van overeenkomsten met de regel.</span><span class="sxs-lookup"><span data-stu-id="663e1-235">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="663e1-236">Als u snel informatie wilt weergeven en actie wilt ondernemen voor een item in een tabel, gebruikt u de selectiekolom [&#10003;] links van de tabel.</span><span class="sxs-lookup"><span data-stu-id="663e1-236">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="663e1-237">Zie ook</span><span class="sxs-lookup"><span data-stu-id="663e1-237">See also</span></span>
- [<span data-ttu-id="663e1-238">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="663e1-238">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="663e1-239">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="663e1-239">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="663e1-240">De geavanceerde zoekquerytaal leren</span><span class="sxs-lookup"><span data-stu-id="663e1-240">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="663e1-241">Geavanceerde zoekquery's migreren van Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="663e1-241">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mdatp.md)