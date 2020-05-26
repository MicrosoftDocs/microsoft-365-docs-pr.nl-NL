---
title: Controleer op lekken van persoonlijke gegevens
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Meer informatie over drie hulpprogramma's die u kunt gebruiken om te controleren op lekkage van persoonlijke gegevens.
ms.openlocfilehash: ef6e1b2edecc8ee8318f1b1e6228e9931b8c66c5
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351883"
---
# <a name="monitor-for-leaks-of-personal-data"></a><span data-ttu-id="ee697-103">Controleer op lekken van persoonlijke gegevens</span><span class="sxs-lookup"><span data-stu-id="ee697-103">Monitor for leaks of personal data</span></span>

<span data-ttu-id="ee697-104">Er zijn veel hulpmiddelen die kunnen worden gebruikt om het gebruik en het transport van persoonlijke gegevens te bewaken.</span><span class="sxs-lookup"><span data-stu-id="ee697-104">There are many tools that can be used to monitor the use and transport of personal data.</span></span> <span data-ttu-id="ee697-105">Dit onderwerp beschrijft drie hulpmiddelen die goed werken.</span><span class="sxs-lookup"><span data-stu-id="ee697-105">This topic describes three tools that work well.</span></span>

![Hulpmiddelen voor het controleren van het gebruik en het transport van persoonlijke gegevens](../../media/Monitor-for-leaks-of-personal-data-image1.png)

<span data-ttu-id="ee697-107">In de afbeelding:</span><span class="sxs-lookup"><span data-stu-id="ee697-107">In the illustration:</span></span>

- <span data-ttu-id="ee697-108">Begin met Microsoft 365-rapporten voor preventie van gegevensverlies voor het bewaken van persoonlijke gegevens in SharePoint Online, OneDrive voor Bedrijven en e-mail in transit.</span><span class="sxs-lookup"><span data-stu-id="ee697-108">Start with Microsoft 365 data loss prevention reports for monitoring personal data in SharePoint Online, OneDrive for Business, and email in transit.</span></span> <span data-ttu-id="ee697-109">Dit geeft het grootste detailniveau voor het bewaken van persoonlijke gegevens.</span><span class="sxs-lookup"><span data-stu-id="ee697-109">These provide the greatest level of detail for monitoring personal data.</span></span> <span data-ttu-id="ee697-110">Deze rapporten bevatten echter niet alle services in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee697-110">However, these reports don't include all services in Office 365.</span></span>

- <span data-ttu-id="ee697-111">Gebruik vervolgens waarschuwingsbeleid en het controlelogboek om de activiteit in alle services te controleren.</span><span class="sxs-lookup"><span data-stu-id="ee697-111">Next, use alert policies and the audit log to monitor activity across services.</span></span> <span data-ttu-id="ee697-112">Stel doorlopende bewaking in of doorzoek het auditlogboek om een incident te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="ee697-112">Setup ongoing monitoring or search the audit log to investigate an incident.</span></span> <span data-ttu-id="ee697-113">Het auditlogboek werkt in alle services: Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Beheerdersactiviteit, OneDrive voor Bedrijven, SharePoint Online, mail in transit en postvakken in rust.</span><span class="sxs-lookup"><span data-stu-id="ee697-113">The audit log works across services — Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Admin activity, OneDrive for Business, SharePoint Online, mail in transit, and mailboxes at rest.</span></span> <span data-ttu-id="ee697-114">Skype-gesprekken worden in de mailboxen in rust opgenomen.</span><span class="sxs-lookup"><span data-stu-id="ee697-114">Skype conversations are included in mailboxes at rest.</span></span>

- <span data-ttu-id="ee697-115">Ten slotte kunt u Microsoft Cloud App Security gebruiken om bestanden met gevoelige gegevens in andere SaaS-providers te bewaken.</span><span class="sxs-lookup"><span data-stu-id="ee697-115">Finally, Use Microsoft Cloud App Security to monitor files with sensitive data in other SaaS providers.</span></span> <span data-ttu-id="ee697-116">Binnenkort is het mogelijk om gevoelige informatietypen en geïntegreerde labels te gebruiken voor Azure Information Protection en Office met Cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="ee697-116">Coming soon is the ability to use sensitive information types and unified labels across Azure Information Protection and Office with Cloud App Security.</span></span> <span data-ttu-id="ee697-117">U kunt beleid instellen dat van toepassing is op al uw SaaS-apps of specifieke apps (zoals Box).</span><span class="sxs-lookup"><span data-stu-id="ee697-117">You can setup policies that apply to all of your SaaS apps or specific apps (like Box).</span></span> <span data-ttu-id="ee697-118">Cloud App Security vindt geen bestanden in Exchange Online, inclusief bestanden die zijn bijgevoegd bij e-mail.</span><span class="sxs-lookup"><span data-stu-id="ee697-118">Cloud App Security doesn't discover files in Exchange Online, including files attached to email.</span></span>

## <a name="data-loss-prevention-reports"></a><span data-ttu-id="ee697-119">Rapporten voor preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="ee697-119">Data loss prevention reports</span></span>

<span data-ttu-id="ee697-120">Nadat u uw DLP-beleid (Data Loss Prevention) heeft gemaakt, moet u controleren of het werkt zoals u het bedoeld heeft en of het u helpt om aan de regels te blijven voldoen.</span><span class="sxs-lookup"><span data-stu-id="ee697-120">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="ee697-121">Met de DLP-rapporten in Office 365 kunt u snel het aantal DLP-beleidsovereenkomsten, onderdrukkingen of foutieve positieven bekijken. Zie of ze in de loop van de tijd omhoog of omlaag gaan, filter het rapport op verschillende manieren en bekijk aanvullende details door een punt op een lijn in de grafiek te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ee697-121">With the DLP reports in Office 365, you can quickly view the number of DLP policy matches, overrides, or false positives; see whether they're trending up or down over time; filter the report in different ways; and view additional details by selecting a point on a line on the graph.</span></span>

<span data-ttu-id="ee697-122">Met de DLP-rapporten kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="ee697-122">You can use the DLP reports to:</span></span>

- <span data-ttu-id="ee697-123">Focus op specifieke tijdsperiodes en begrijp de redenen voor pieken en trends.</span><span class="sxs-lookup"><span data-stu-id="ee697-123">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>

- <span data-ttu-id="ee697-124">Ontdek bedrijfsprocessen die strijdig zijn met het DLP-beleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ee697-124">Discover business processes that violate your organization's DLP policies.</span></span>

- <span data-ttu-id="ee697-125">Begrijp de zakelijke impact van het DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="ee697-125">Understand any business impact of the DLP policies.</span></span>

- <span data-ttu-id="ee697-126">Bekijk de redenen die door gebruikers zijn ingediend bij het oplossen van een beleidstip door het beleid te negeren of een fout-positief te melden.</span><span class="sxs-lookup"><span data-stu-id="ee697-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy or reporting a false positive.</span></span>

- <span data-ttu-id="ee697-127">Controleer de naleving van een specifiek DLP-beleid door alle overeenkomsten voor dat beleid weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ee697-127">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>

- <span data-ttu-id="ee697-128">Bekijk een lijst met bestanden met gevoelige gegevens die overeenkomen met uw DLP-beleid in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="ee697-128">View a list of files with sensitive data that matches your DLP policies in the details pane.</span></span>

<span data-ttu-id="ee697-129">Daarnaast kunt u met de DLP-rapporten uw DLP-beleid nauwkeurig afstemmen terwijl u ze in de testmodus uitvoert.</span><span class="sxs-lookup"><span data-stu-id="ee697-129">In addition, you can use the DLP reports to fine tune your DLP policies as you run them in test mode.</span></span>

<span data-ttu-id="ee697-130">DLP-rapporten zijn te vinden in het beveiligingscentrum en het compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="ee697-130">DLP reports are in the security center and the compliance center.</span></span> <span data-ttu-id="ee697-131">Navigeer naar rapporten \> Rapporten weergeven.</span><span class="sxs-lookup"><span data-stu-id="ee697-131">Navigate to Reports \> View reports.</span></span> <span data-ttu-id="ee697-132">Ga onder preventie van gegevensverlies (DLP) naar DLP-beleid en regelovereenkomsten of DLP foute positieven en overschrijvingen.</span><span class="sxs-lookup"><span data-stu-id="ee697-132">Under Data loss prevention (DLP), go to either DLP policy and rule matches or DLP false positives and overrides.</span></span>

<span data-ttu-id="ee697-133">Zie [de rapporten weergeven voor preventie van gegevensverlies](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ee697-133">For more information, see [View the reports for data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).</span></span>

![Rapport met DLP-beleidsovereenkomsten](../../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="audit-log-and-alert-policies"></a><span data-ttu-id="ee697-135">controlelogboek en waarschuwingsbeleid</span><span class="sxs-lookup"><span data-stu-id="ee697-135">audit log and alert policies</span></span>

<span data-ttu-id="ee697-136">Het auditlogboek bevat gebeurtenissen van Exchange Online, SharePoint Online, OneDrive voor Bedrijven, Azure Active Directory, Microsoft Teams, Power BI, Sway en andere services.</span><span class="sxs-lookup"><span data-stu-id="ee697-136">The audit log contains events from Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway, and other services.</span></span>

<span data-ttu-id="ee697-137">Het beveiligingscentrum en het compliancecentrum bieden twee manieren om het auditlogboek te controleren en erover te rapporteren:</span><span class="sxs-lookup"><span data-stu-id="ee697-137">The security center and compliance center provide two ways to monitor and report against the audit log:</span></span>

- <span data-ttu-id="ee697-138">Waarschuwingsbeleid instellen, waarschuwingen bekijken en trends volgen. Gebruik het waarschuwingsbeleid en de dashboardinstrumenten in het beveiligingscentrum of het compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="ee697-138">Setup alert policies, view alerts, and monitor trends — Use the alert policy and alert dashboard tools in either the security center or compliance center.</span></span>

- <span data-ttu-id="ee697-139">Direct in het auditlogboek zoeken. Zoek naar alle gebeurtenissen in een gespecificeerd datumbereik.</span><span class="sxs-lookup"><span data-stu-id="ee697-139">Search the audit log directly — Search for all events in a specified date rage.</span></span> <span data-ttu-id="ee697-140">U kunt de resultaten ook filteren op basis van specifieke criteria, zoals de gebruiker die de actie heeft uitgevoerd, de actie of het doelobject.</span><span class="sxs-lookup"><span data-stu-id="ee697-140">Or you can filter the results based on specific criteria, such as the user who performed the action, the action, or the target object.</span></span>

<span data-ttu-id="ee697-141">Teams voor informatiebeveiliging en compliance kunnen deze hulpmiddelen gebruiken om proactief activiteiten te bekijken die worden uitgevoerd door zowel eindgebruikers als beheerders in services.</span><span class="sxs-lookup"><span data-stu-id="ee697-141">Information security and compliance teams can use these tools to proactively review activities performed by both end users and administrators across services.</span></span> <span data-ttu-id="ee697-142">Automatische waarschuwingen kunnen worden geconfigureerd om e-mailmeldingen te verzenden wanneer bepaalde activiteiten plaatsvinden op specifieke siteverzamelingen. Bijvoorbeeld wanneer inhoud wordt gedeeld van sites waarvan bekend is dat ze AVG-gerelateerde informatie bevatten.</span><span class="sxs-lookup"><span data-stu-id="ee697-142">Automatic alerts can be configured to send email notifications when certain activities occur on specific site collections - for example when content is shared from sites known to contain GDPR related information.</span></span> <span data-ttu-id="ee697-143">Hierdoor kunnen deze teams gebruikers opvolgen om ervoor te zorgen dat het beveiligingsbeleid van het bedrijf wordt gevolgd of om aanvullende training te geven.</span><span class="sxs-lookup"><span data-stu-id="ee697-143">This allows those teams to follow up with users to ensure that corporate security policies are followed, or to provide additional training.</span></span>

<span data-ttu-id="ee697-144">Informatiebeveiligingsteams kunnen ook in het auditlogboek zoeken om vermoedelijke datalekken te onderzoeken en zowel de oorzaak als de omvang van de inbreuk te bepalen.</span><span class="sxs-lookup"><span data-stu-id="ee697-144">Information security teams can also search the audit log to investigate suspected data breaches and determine both root cause and the extent of the breach.</span></span> <span data-ttu-id="ee697-145">Deze ingebouwde mogelijkheid vergemakkelijkt de naleving van artikel 33 en 34 van de AVG, die vereisen dat binnen een bepaalde periode meldingen worden gedaan aan de toezichthoudende autoriteit en aan de betrokkenen zelf van een datalek.</span><span class="sxs-lookup"><span data-stu-id="ee697-145">This built in capability facilitates compliance with article 33 and 34 of the GDPR, which require notifications be provided to the GDPR supervisory authority and to the data subjects themselves of a data breach within a specific time period.</span></span> <span data-ttu-id="ee697-146">Vermeldingen in het auditlogboek worden binnen de service slechts 90 dagen bewaard. Het wordt vaak aanbevolen en veel organisaties vereisen dat deze logboeken voor langere tijd worden bewaard.</span><span class="sxs-lookup"><span data-stu-id="ee697-146">Audit log entries are only retained for 90 days within the service - it is often recommended and many organizations required that these logs be retained for longer periods of time.</span></span>

<span data-ttu-id="ee697-147">Er zijn oplossingen beschikbaar die zich via de Microsoft Management Activity API abonneren op de Unified Audit Logs en die zowel logboekvermeldingen kunnen opslaan als geavanceerde dashboards en waarschuwingen kunnen bieden.</span><span class="sxs-lookup"><span data-stu-id="ee697-147">Solutions are available which subscribe to the Unified Audit Logs through the Microsoft Management Activity API and can both store log entries as needed, and provide advanced dashboards and alerts.</span></span> <span data-ttu-id="ee697-148">Een voorbeeld is [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).</span><span class="sxs-lookup"><span data-stu-id="ee697-148">One example is [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).</span></span>

<span data-ttu-id="ee697-149">Meer informatie over het waarschuwingsbeleid en het doorzoeken van het auditlogboek:</span><span class="sxs-lookup"><span data-stu-id="ee697-149">More information about alert policies and searching the audit log:</span></span>

- [<span data-ttu-id="ee697-150">Waarschuwingsbeleid in de beveiligings- en compliancecentra van Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ee697-150">Alert policies in the Microsoft 365 security and compliance centers</span></span>](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)

- <span data-ttu-id="ee697-151">[Zoeken in het auditlogboek naar gebruikers- en beheerdersactiviteit in Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log) (Inleiding)</span><span class="sxs-lookup"><span data-stu-id="ee697-151">[Search the audit log for user and admin activity in Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log) (introduction)</span></span>

- <span data-ttu-id="ee697-152">[Auditlogboeken zoeken in- of uitschakelen](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="ee697-152">[Turn audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)</span></span>

- [<span data-ttu-id="ee697-153">Zoeken in het auditlogboek</span><span class="sxs-lookup"><span data-stu-id="ee697-153">Search the audit log</span></span>](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

- <span data-ttu-id="ee697-154">[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) (cmdlet)</span><span class="sxs-lookup"><span data-stu-id="ee697-154">[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) (cmdlet)</span></span>

- [<span data-ttu-id="ee697-155">Gedetailleerde eigenschappen in het auditlogboek</span><span class="sxs-lookup"><span data-stu-id="ee697-155">Detailed properties in the audit log</span></span>](https://docs.microsoft.com/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log)

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="ee697-156">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ee697-156">Microsoft Cloud App Security</span></span>

<span data-ttu-id="ee697-157">Met Microsoft Cloud App Security kunt u andere SaaS-apps ontdekken die worden gebruikt in uw netwerken en gevoelige gegevens die van en naar deze apps zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="ee697-157">Microsoft Cloud App Security helps you discover other SaaS apps in use across your networks and sensitive data that is sent to and from these apps.</span></span>

<span data-ttu-id="ee697-158">Microsoft Cloud App Security is een uitgebreide service die uitgebreide zichtbaarheid, gedetailleerde controle en verbeterde bescherming tegen bedreigingen biedt voor uw cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="ee697-158">Microsoft Cloud App Security is a comprehensive service providing deep visibility, granular controls and enhanced threat protection for your cloud apps.</span></span> <span data-ttu-id="ee697-159">Het identificeert meer dan 15.000 cloudtoepassingen in uw netwerk, vanaf alle apparaten, en biedt risicoanalyse en doorlopende risicobeoordeling en-analyse.</span><span class="sxs-lookup"><span data-stu-id="ee697-159">It identifies more than 15,000 cloud applications in your network-from all devices-and provides risk scoring and ongoing risk assessment and analytics.</span></span> <span data-ttu-id="ee697-160">Geen agents vereist: informatie verzameld uit uw firewalls en proxy's geeft u volledige zichtbaarheid en context voor het cloudgebruik en schaduw-IT.</span><span class="sxs-lookup"><span data-stu-id="ee697-160">No agents required: information is collected from your firewalls and proxies to give you complete visibility and context for cloud usage and shadow IT.</span></span>

<span data-ttu-id="ee697-161">Om uw cloudomgeving beter te begrijpen, biedt de Cloud App Security-onderzoeksfunctie uitgebreid inzicht in alle activiteiten, bestanden en accounts voor goedgekeurde en beheerde apps.</span><span class="sxs-lookup"><span data-stu-id="ee697-161">To better understand your cloud environment, Cloud App Security investigate feature provides deep visibility into all activities, files and accounts for sanctioned and managed apps.</span></span> <span data-ttu-id="ee697-162">U kunt gedetailleerde informatie op bestandsniveau verkrijgen en ontdekken waar gegevens naartoe gaan in de cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="ee697-162">You can gain detailed information on a file level and discover where data travels in the cloud apps.</span></span>

<span data-ttu-id="ee697-163">De volgende illustratie toont bijvoorbeeld twee Cloud App Security-beleidsregels die kunnen helpen bij AVG.</span><span class="sxs-lookup"><span data-stu-id="ee697-163">For examples, the following illustration demonstrates two Cloud App Security policies that can help with GDPR.</span></span>

![Voorbeeld van Cloud App Security-beleid](../../media/Monitor-for-leaks-of-personal-data-image3.png)

<span data-ttu-id="ee697-165">Het eerste beleid waarschuwt wanneer bestanden met een vooraf gedefinieerd PII-kenmerk of aangepaste expressie die u kiest, buiten de organisatie worden gedeeld vanuit de SaaS-apps die u kiest.</span><span class="sxs-lookup"><span data-stu-id="ee697-165">The first policy alerts when files with a predefined PII attribute or custom expression that you choose is shared outside the organization from the SaaS apps that you choose.</span></span>

<span data-ttu-id="ee697-166">Het tweede beleid blokkeert het downloaden van bestanden naar een onbeheerd apparaat.</span><span class="sxs-lookup"><span data-stu-id="ee697-166">The second policy blocks downloads of files to any unmanaged device.</span></span> <span data-ttu-id="ee697-167">U kiest de kenmerken in de bestanden waarnaar u wilt zoeken en de SaaS-apps waarop u het beleid wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="ee697-167">You choose the attributes within the files to look for and the SaaS apps you want the policy to apply to.</span></span>

<span data-ttu-id="ee697-168">Deze kenmerktypen komen binnenkort beschikbaar in Cloud App Security:</span><span class="sxs-lookup"><span data-stu-id="ee697-168">These attribute types are coming soon to Cloud App Security:</span></span>

- <span data-ttu-id="ee697-169">Gevoelige informatietypen</span><span class="sxs-lookup"><span data-stu-id="ee697-169">Sensitive information types</span></span>

- <span data-ttu-id="ee697-170">Geïntegreerde labels in Microsoft 365 en Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="ee697-170">Unified labels across Microsoft 365 and Azure Information Protection</span></span>

### <a name="cloud-app-security-dashboard"></a><span data-ttu-id="ee697-171">Cloud App Security-dashboard</span><span class="sxs-lookup"><span data-stu-id="ee697-171">Cloud App Security dashboard</span></span>

<span data-ttu-id="ee697-172">Als u de Cloud App Security nog niet gebruikt, begint u met het starten van de app.</span><span class="sxs-lookup"><span data-stu-id="ee697-172">If you haven't yet started to use Cloud App Security, begin by starting it up.</span></span> <span data-ttu-id="ee697-173">Voor toegang tot Cloud App Security: <https://portal.cloudappsecurity.com>.</span><span class="sxs-lookup"><span data-stu-id="ee697-173">To access Cloud App Security: <https://portal.cloudappsecurity.com>.</span></span>

<span data-ttu-id="ee697-174">Opmerking: zorg ervoor dat u 'Bestanden automatisch scannen naar classificatielabels van Azure Information Protection' (in Algemene instellingen) inschakelt wanneer u aan de slag gaat met Cloud App Security of voordat u labels toewijst.</span><span class="sxs-lookup"><span data-stu-id="ee697-174">Note: Be sure to enable 'Automatically scan files for Azure Information Protection classification labels' (in General settings) when getting started with Cloud App Security or before you assign labels.</span></span> <span data-ttu-id="ee697-175">Na de installatie worden bestaande bestanden niet opnieuw gescand door Cloud App Security totdat ze worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ee697-175">After setup, Cloud App Security does not scan existing files again until they are modified.</span></span>

![Dashboard met informatie over waarschuwingen](../../media/Monitor-for-leaks-of-personal-data-image4.png)

<span data-ttu-id="ee697-177">Meer informatie:</span><span class="sxs-lookup"><span data-stu-id="ee697-177">More information:</span></span>

- [<span data-ttu-id="ee697-178">Cloud App Security implementeren</span><span class="sxs-lookup"><span data-stu-id="ee697-178">Deploy Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [<span data-ttu-id="ee697-179">Meer informatie over Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ee697-179">More information about Microsoft Cloud App Security</span></span>](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [<span data-ttu-id="ee697-180">Blokkeer downloads van gevoelige informatie met behulp van de Microsoft Cloud App Security-proxy</span><span class="sxs-lookup"><span data-stu-id="ee697-180">Block downloads of sensitive information using the Microsoft Cloud App Security proxy</span></span>](https://docs.microsoft.com/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a><span data-ttu-id="ee697-181">Voorbeeld van bestands- en activiteitenbeleid om het delen van persoonlijke gegevens te detecteren</span><span class="sxs-lookup"><span data-stu-id="ee697-181">Example file and activity policies to detect sharing of personal data</span></span>

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a><span data-ttu-id="ee697-182">Het delen van bestanden met PII opsporen: creditcardnummer</span><span class="sxs-lookup"><span data-stu-id="ee697-182">Detect sharing of files containing PII — Credit card number</span></span>

<span data-ttu-id="ee697-183">Waarschuwen wanneer een bestand met een creditcardnummer wordt gedeeld vanuit een goedgekeurde cloud-app.</span><span class="sxs-lookup"><span data-stu-id="ee697-183">Alert when a file containing a credit card number is shared from an approved cloud app.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ee697-184"><strong>Besturingselement</strong></span><span class="sxs-lookup"><span data-stu-id="ee697-184"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="ee697-185"><strong>Instellingen</strong></span><span class="sxs-lookup"><span data-stu-id="ee697-185"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ee697-186">Beleidstype</span><span class="sxs-lookup"><span data-stu-id="ee697-186">Policy type</span></span></td>
<td align="left"><span data-ttu-id="ee697-187">Bestandsbeleid</span><span class="sxs-lookup"><span data-stu-id="ee697-187">File policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ee697-188">Beleidssjabloon</span><span class="sxs-lookup"><span data-stu-id="ee697-188">Policy template</span></span></td>
<td align="left"><span data-ttu-id="ee697-189">Geen sjabloon</span><span class="sxs-lookup"><span data-stu-id="ee697-189">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ee697-190">Ernst van beleid</span><span class="sxs-lookup"><span data-stu-id="ee697-190">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="ee697-191">Hoog</span><span class="sxs-lookup"><span data-stu-id="ee697-191">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ee697-192">Categorie</span><span class="sxs-lookup"><span data-stu-id="ee697-192">Category</span></span></td>
<td align="left"><span data-ttu-id="ee697-193">DLP</span><span class="sxs-lookup"><span data-stu-id="ee697-193">DLP</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ee697-194">Filterinstellingen</span><span class="sxs-lookup"><span data-stu-id="ee697-194">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="ee697-195">Toegangsniveau = openbaar (internet), openbaar, extern</span><span class="sxs-lookup"><span data-stu-id="ee697-195">Access level = Public (Internet), Public, External</span></span></p>
<p><span data-ttu-id="ee697-196">App = &lt;selecteer apps&gt; (gebruik deze instelling als u de bewaking wilt beperken tot specifieke SaaS-apps)</span><span class="sxs-lookup"><span data-stu-id="ee697-196">App = &lt;select apps&gt; (use this setting if you want to limit monitoring to specific SaaS apps)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ee697-197">Toepassen op</span><span class="sxs-lookup"><span data-stu-id="ee697-197">Apply to</span></span></td>
<td align="left"><span data-ttu-id="ee697-198">Alle bestanden, alle eigenaren</span><span class="sxs-lookup"><span data-stu-id="ee697-198">All files, all owners</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ee697-199">Inhoudsinspectie</span><span class="sxs-lookup"><span data-stu-id="ee697-199">Content inspection</span></span></td>
<td align="left"><p><span data-ttu-id="ee697-200">Bevat bestanden die voldoen aan een huidige expressie: alle landen: financiën: creditcardnummer</span><span class="sxs-lookup"><span data-stu-id="ee697-200">Includes files that match a present expression: All countries: Finance: Credit card number</span></span></p>
<p><span data-ttu-id="ee697-201">Vereis geen relevante context: niet aangevinkt (dit komt zowel overeen met trefwoorden als met regex)</span><span class="sxs-lookup"><span data-stu-id="ee697-201">Don't require relevant context: unchecked (this will match keywords as well as regex)</span></span></p>
<p><span data-ttu-id="ee697-202">Bevat bestanden met ten minste 1 overeenkomst</span><span class="sxs-lookup"><span data-stu-id="ee697-202">Includes files with at least 1 match</span></span></p>
<p><span data-ttu-id="ee697-203">De laatste vier tekens van de fout opsporen: ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="ee697-203">Unmask the last 4 characters of the violation: checked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ee697-204">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="ee697-204">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="ee697-205">Een waarschuwing maken voor elk overeenkomend bestand: ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="ee697-205">Create an alert for each matching file: checked</span></span></p>
<p><span data-ttu-id="ee697-206">Dagelijkse waarschuwingslimiet: 1000</span><span class="sxs-lookup"><span data-stu-id="ee697-206">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="ee697-207">Een waarschuwing als e-mail selecteren: ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="ee697-207">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="ee697-208">Aan: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee697-208">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ee697-209">Beheermodel</span><span class="sxs-lookup"><span data-stu-id="ee697-209">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="ee697-210">Microsoft OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="ee697-210">Microsoft OneDrive for Business</span></span></p>
<p><span data-ttu-id="ee697-211">Privé maken: vink Externe gebruikers verwijderen aan.</span><span class="sxs-lookup"><span data-stu-id="ee697-211">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="ee697-212">Alle andere instellingen: uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="ee697-212">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="ee697-213">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ee697-213">Microsoft SharePoint Online</span></span></p>
<p><span data-ttu-id="ee697-214">Privé maken: vink Externe gebruikers verwijderen aan.</span><span class="sxs-lookup"><span data-stu-id="ee697-214">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="ee697-215">Alle andere instellingen: uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="ee697-215">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee697-216">Vergelijkbare beleidsregels:</span><span class="sxs-lookup"><span data-stu-id="ee697-216">Similar policies:</span></span>

- <span data-ttu-id="ee697-217">Het delen van bestanden met PII-e-mailadres opsporen</span><span class="sxs-lookup"><span data-stu-id="ee697-217">Detect sharing of Files containing PII - Email Address</span></span>

- <span data-ttu-id="ee697-218">Het delen van bestanden met PII-paspoortnummer opsporen</span><span class="sxs-lookup"><span data-stu-id="ee697-218">Detect sharing of Files containing PII - Passport Number</span></span>

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a><span data-ttu-id="ee697-219">Detecteer klant- of HR-gegevens in Box of OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="ee697-219">Detect Customer or HR Data in Box or OneDrive for Business</span></span>

<span data-ttu-id="ee697-220">Waarschuwen wanneer een bestand met het label Klantgegevens of HR-gegevens wordt geüpload naar OneDrive voor Bedrijven of Box.</span><span class="sxs-lookup"><span data-stu-id="ee697-220">Alert when a file labeled as Customer Data or HR Data is uploaded to OneDrive for Business or Box.</span></span>

<span data-ttu-id="ee697-221">Opmerkingen:</span><span class="sxs-lookup"><span data-stu-id="ee697-221">Notes:</span></span>

- <span data-ttu-id="ee697-222">Voor het bewaken van Box moet een connector worden geconfigureerd met de API-connector SDK.</span><span class="sxs-lookup"><span data-stu-id="ee697-222">Box monitoring requires a connector be configured using the API Connector SDK.</span></span>

- <span data-ttu-id="ee697-223">Dit beleid vereist functies die momenteel in de preview-versie privé zijn.</span><span class="sxs-lookup"><span data-stu-id="ee697-223">This policy requires capabilities that are currently in private preview.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ee697-224"><strong>Besturingselement</strong></span><span class="sxs-lookup"><span data-stu-id="ee697-224"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="ee697-225"><strong>Instellingen</strong></span><span class="sxs-lookup"><span data-stu-id="ee697-225"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ee697-226">Beleidstype</span><span class="sxs-lookup"><span data-stu-id="ee697-226">Policy type</span></span></td>
<td align="left"><span data-ttu-id="ee697-227">Activiteitenbeleid</span><span class="sxs-lookup"><span data-stu-id="ee697-227">Activity policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ee697-228">Beleidssjabloon</span><span class="sxs-lookup"><span data-stu-id="ee697-228">Policy template</span></span></td>
<td align="left"><span data-ttu-id="ee697-229">Geen sjabloon</span><span class="sxs-lookup"><span data-stu-id="ee697-229">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ee697-230">Ernst van beleid</span><span class="sxs-lookup"><span data-stu-id="ee697-230">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="ee697-231">Hoog</span><span class="sxs-lookup"><span data-stu-id="ee697-231">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ee697-232">Categorie</span><span class="sxs-lookup"><span data-stu-id="ee697-232">Category</span></span></td>
<td align="left"><span data-ttu-id="ee697-233">Besturingselement delen</span><span class="sxs-lookup"><span data-stu-id="ee697-233">Sharing Control</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ee697-234">Reageren op</span><span class="sxs-lookup"><span data-stu-id="ee697-234">Act on</span></span></td>
<td align="left"><span data-ttu-id="ee697-235">Afzonderlijke activiteit</span><span class="sxs-lookup"><span data-stu-id="ee697-235">Single activity</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ee697-236">Filterinstellingen</span><span class="sxs-lookup"><span data-stu-id="ee697-236">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="ee697-237">Activiteitstype = bestand uploaden</span><span class="sxs-lookup"><span data-stu-id="ee697-237">Activity type = Upload File</span></span></p>
<p><span data-ttu-id="ee697-238">App = Microsoft OneDrive voor Bedrijven en Box</span><span class="sxs-lookup"><span data-stu-id="ee697-238">App = Microsoft OneDrive for Business and Box</span></span></p>
<p><span data-ttu-id="ee697-239">Classificatielabel (momenteel in privépreview): Azure Information Protection = klantgegevens, personeelszaken (salarisgegevens, personeelszaken), werknemersgegevens</span><span class="sxs-lookup"><span data-stu-id="ee697-239">Classification Label (currently in private preview): Azure Information Protection = Customer Data, Human Resources—Salary Data, Human Resources—Employee Data</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ee697-240">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="ee697-240">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="ee697-241">Een waarschuwing maken: ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="ee697-241">Create an alert: checked</span></span></p>
<p><span data-ttu-id="ee697-242">Dagelijkse waarschuwingslimiet: 1000</span><span class="sxs-lookup"><span data-stu-id="ee697-242">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="ee697-243">Een waarschuwing als e-mail selecteren: ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="ee697-243">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="ee697-244">Aan: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee697-244">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ee697-245">Beheermodel</span><span class="sxs-lookup"><span data-stu-id="ee697-245">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="ee697-246">Alle apps</span><span class="sxs-lookup"><span data-stu-id="ee697-246">All apps</span></span></p>
<p><span data-ttu-id="ee697-247">Gebruiker in quarantaine plaatsen: ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="ee697-247">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="ee697-248">Alle andere instellingen: uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="ee697-248">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="ee697-249">Office 365</span><span class="sxs-lookup"><span data-stu-id="ee697-249">Office 365</span></span></p>
<p><span data-ttu-id="ee697-250">Gebruiker in quarantaine plaatsen: ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="ee697-250">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="ee697-251">Alle andere instellingen: uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="ee697-251">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee697-252">Vergelijkbare beleidsregels:</span><span class="sxs-lookup"><span data-stu-id="ee697-252">Similar policies:</span></span>

- <span data-ttu-id="ee697-253">Detecteer grote downloads van klantgegevens of HR-gegevens. Waarschuw wanneer een groot aantal bestanden met klantgegevens of HR-gegevens in een korte periode wordt gedownload door een enkele gebruiker.</span><span class="sxs-lookup"><span data-stu-id="ee697-253">Detect large downloads of Customer data or HR Data — Alert when a large number of files containing customer data or HR data have been detected being downloaded by a single user within a short period of time.</span></span>

- <span data-ttu-id="ee697-254">Detecteer het delen van klant- en HR-gegevens. Waarschuw wanneer bestanden met klant- of HR-gegevens worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="ee697-254">Detect Sharing of Customer and HR Data — Alert when files containing Customer or HR Data are shared.</span></span>
