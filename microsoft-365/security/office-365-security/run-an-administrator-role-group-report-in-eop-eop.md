---
title: Een rapport over groepen met beheerdersrollen uitvoeren in standalone EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u een beheerdersrolgroeprapport uitvoert in standalone Exchange Online Protection (EOP). Dit rapport logt wanneer een beheerder leden toevoegt aan of leden verwijdert uit beheerdersrolgroepen, EOP registreert elke gebeurtenis.
ms.openlocfilehash: 0c504460657a153aad7d3dd065c81007a68ba916
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587362"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="2b250-104">Een rapport over groepen met beheerdersrollen uitvoeren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="2b250-104">Run an administrator role group report in standalone EOP</span></span>

<span data-ttu-id="2b250-105">In zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, wanneer een beheerder leden toevoegt aan of leden uit beheerdersgroepen verwijdert, registreert de service elke gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="2b250-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="2b250-106">Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md)voor meer informatie over rolgroepen in standalone EOP.</span><span class="sxs-lookup"><span data-stu-id="2b250-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="2b250-107">Wanneer u een beheerdersrolgroeprapport uitvoert in het Exchange-beheercentrum (EAC), worden vermeldingen weergegeven als zoekresultaten en worden de betrokken rolgroepen opgenomen, die het lidmaatschap van de rolgroep hebben gewijzigd en wanneer en welke lidmaatschapsupdates zijn uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="2b250-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="2b250-108">Gebruik dit rapport om wijzigingen in de beheerdersmachtigingen te controleren die zijn toegewezen aan gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2b250-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2b250-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="2b250-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2b250-110">Zie [Exchange-beheercentrum in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum wilt openen.</span><span class="sxs-lookup"><span data-stu-id="2b250-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="2b250-111">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2b250-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="2b250-112">U hebt specifiek de rol Auditlogboeken of Controlelogboeken alleen weergeven nodig, die standaard zijn toegewezen aan de rolgroepen ComplianceManagement, OrganizationManagement (global admins) en SecurityAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2b250-112">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="2b250-113">Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de EAC voor meer informatie [de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2b250-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="2b250-114">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="2b250-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="2b250-115">Heb je problemen?</span><span class="sxs-lookup"><span data-stu-id="2b250-115">Having problems?</span></span> <span data-ttu-id="2b250-116">Vraag om hulp in het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="2b250-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="2b250-117">De EAC gebruiken om een rapport over een beheerdersrolgroep uit te voeren</span><span class="sxs-lookup"><span data-stu-id="2b250-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="2b250-118">Voer het rapport van de beheerdersrolgroep uit om de wijzigingen in beheerrolgroepen in uw organisatie binnen een bepaald tijdsbestek te vinden.</span><span class="sxs-lookup"><span data-stu-id="2b250-118">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="2b250-119">Ga in de EAC naar **Compliance management** \> **Auditing**en kies **vervolgens Een beheerdersrolgroeprapport uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="2b250-119">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="2b250-120">Configureer in de pagina Zoeken naar wijzigingen in de pagina **beheerdersrolgroepen** die wordt geopend de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="2b250-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="2b250-121">**Begindatum** en **einddatum**: Voer een datumbereik in.</span><span class="sxs-lookup"><span data-stu-id="2b250-121">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="2b250-122">Standaard zoekt het rapport naar wijzigingen die in de afgelopen twee weken zijn aangebracht in beheerdersrolgroepen.</span><span class="sxs-lookup"><span data-stu-id="2b250-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="2b250-123">**Rolgroepen selecteren:** Standaard worden alle rolgroepen doorzocht.</span><span class="sxs-lookup"><span data-stu-id="2b250-123">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="2b250-124">Als u de resultaten wilt filteren op specifieke rolgroepen, klikt u op **Rolgroepen selecteren**.</span><span class="sxs-lookup"><span data-stu-id="2b250-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="2b250-125">Selecteer in het dialoogvenster dat wordt weergegeven een rolgroep en klik op **toevoegen ->**.</span><span class="sxs-lookup"><span data-stu-id="2b250-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="2b250-126">Herhaal deze stap zo vaak als nodig is en klik op **OK** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="2b250-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="2b250-127">Klik op **Zoeken**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="2b250-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="2b250-128">Als er wijzigingen worden gevonden met behulp van de criteria die u hebt opgegeven, worden deze weergegeven in het resultatenvenster.</span><span class="sxs-lookup"><span data-stu-id="2b250-128">If any changes are found using the criteria you specified, they will appear in the results pane.</span></span> <span data-ttu-id="2b250-129">Klik op een rolgroep in de zoekresultaten om de wijzigingen in het detailvenster weer te geven.</span><span class="sxs-lookup"><span data-stu-id="2b250-129">Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2b250-130">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="2b250-130">How do you know this worked?</span></span>

<span data-ttu-id="2b250-131">Als u een rapport van de beheerdersrolgroep hebt uitgevoerd, worden rolgroepen die binnen het datumbereik zijn gewijzigd, weergegeven in het deelvenster zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="2b250-131">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane.</span></span> <span data-ttu-id="2b250-132">Als er geen resultaten zijn, hebben er geen wijzigingen plaatsgevonden in rolgroepen binnen het opgegeven datumbereik.</span><span class="sxs-lookup"><span data-stu-id="2b250-132">If there are no results, then no changes to role groups have taken place within the specified date range.</span></span> <span data-ttu-id="2b250-133">Als u denkt dat er resultaten moeten zijn, wijzigt u het datumbereik en voert u het rapport opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="2b250-133">If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="2b250-134">Wijzigingen in het lidmaatschap van de rolgroep controleren</span><span class="sxs-lookup"><span data-stu-id="2b250-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="2b250-135">Wanneer leden worden toegevoegd aan of verwijderd uit een rolgroep, geven de zoekresultaten die in het detailvenster worden weergegeven aan dat het lidmaatschap van de rolgroep is bijgewerkt en worden de huidige leden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2b250-135">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members.</span></span> <span data-ttu-id="2b250-136">In de resultaten wordt niet expliciet vermeld welke gebruiker is toegevoegd of verwijderd.</span><span class="sxs-lookup"><span data-stu-id="2b250-136">The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="2b250-137">Als u wilt bepalen of een gebruiker is toegevoegd of verwijderd, moet u twee afzonderlijke vermeldingen in het rapport vergelijken.</span><span class="sxs-lookup"><span data-stu-id="2b250-137">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="2b250-138">Laten we bijvoorbeeld eens kijken naar de volgende logboekvermeldingen voor de **rolgroep HelpDesk:**</span><span class="sxs-lookup"><span data-stu-id="2b250-138">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="2b250-139">1/27/2018 16:43</span><span class="sxs-lookup"><span data-stu-id="2b250-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="2b250-140">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="2b250-140">Administrator</span></span> <br> <span data-ttu-id="2b250-141">Bijgewerkte leden: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="2b250-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="2b250-142">2/06/2018 10:09</span><span class="sxs-lookup"><span data-stu-id="2b250-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="2b250-143">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="2b250-143">Administrator</span></span> <br> <span data-ttu-id="2b250-144">Bijgewerkte leden: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="2b250-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="2b250-145">19-19-2018 14:12 uur</span><span class="sxs-lookup"><span data-stu-id="2b250-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="2b250-146">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="2b250-146">Administrator</span></span> <br> <span data-ttu-id="2b250-147">Bijgewerkte leden: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="2b250-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="2b250-148">In dit voorbeeld heeft het gebruikersaccount van de beheerder de volgende wijzigingen aangebracht:</span><span class="sxs-lookup"><span data-stu-id="2b250-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="2b250-149">Op 2/06/2018 voegden ze de gebruiker tonip toe.</span><span class="sxs-lookup"><span data-stu-id="2b250-149">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="2b250-150">Op 2/19/2018 verwijderden ze de gebruiker pilarp.</span><span class="sxs-lookup"><span data-stu-id="2b250-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="2b250-151">Zelfstandige Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen</span><span class="sxs-lookup"><span data-stu-id="2b250-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="2b250-152">U Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen die voldoen aan de criteria die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="2b250-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="2b250-153">Zie [Zoek-AdminAuditLog-zoekcriteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)voor een lijst met zoekcriteria.</span><span class="sxs-lookup"><span data-stu-id="2b250-153">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="2b250-154">Deze procedure maakt gebruik van de cmdlet **Search-AdminAuditLog** en geeft zoekresultaten weer in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b250-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="2b250-155">U deze cmdlet gebruiken wanneer u een set resultaten moet retourneren die de limieten overschrijdt die zijn gedefinieerd in de cmdlet **New-AdminAuditLogSearch** of in de EAC Audit Reporting-rapporten.</span><span class="sxs-lookup"><span data-stu-id="2b250-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="2b250-156">Als u in het controlelogboek wilt zoeken naar criteria die u opgeeft, gebruikt u de volgende syntaxis.</span><span class="sxs-lookup"><span data-stu-id="2b250-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="2b250-157">De cmdlet **Search-AdminAuditLog** retourneert standaard maximaal 1.000 logboekvermeldingen.</span><span class="sxs-lookup"><span data-stu-id="2b250-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="2b250-158">Gebruik de parameter _ResultSize_ om maximaal 250.000 logboekvermeldingen op te geven.</span><span class="sxs-lookup"><span data-stu-id="2b250-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="2b250-159">Of gebruik de waarde `Unlimited` om alle vermeldingen terug te sturen.</span><span class="sxs-lookup"><span data-stu-id="2b250-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="2b250-160">In dit voorbeeld wordt gezocht naar alle controlelogboekvermeldingen met de volgende criteria:</span><span class="sxs-lookup"><span data-stu-id="2b250-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="2b250-161">**Startdatum**: 08/04/2018</span><span class="sxs-lookup"><span data-stu-id="2b250-161">**Start date**: 08/04/2018</span></span>

- <span data-ttu-id="2b250-162">**Einddatum**: 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="2b250-162">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="2b250-163">**Gebruikers-id's**: davids, chrisd, kima</span><span class="sxs-lookup"><span data-stu-id="2b250-163">**User IDs**: davids, chrisd, kima</span></span>

- <span data-ttu-id="2b250-164">**Cmdlets**: **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="2b250-164">**Cmdlets**: **Set-Mailbox**</span></span>

- <span data-ttu-id="2b250-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="2b250-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="2b250-166">In dit voorbeeld wordt gezocht naar wijzigingen in een specifiek postvak.</span><span class="sxs-lookup"><span data-stu-id="2b250-166">This example searches for changes made to a specific mailbox.</span></span> <span data-ttu-id="2b250-167">Dit is handig als u problemen opgaat of als u informatie moet verstrekken voor een onderzoek.</span><span class="sxs-lookup"><span data-stu-id="2b250-167">This is useful if you're troubleshooting or you need to provide information for an investigation.</span></span> <span data-ttu-id="2b250-168">De volgende criteria worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="2b250-168">The following criteria are used:</span></span>

- <span data-ttu-id="2b250-169">**Startdatum**: 05/01/2018</span><span class="sxs-lookup"><span data-stu-id="2b250-169">**Start date**: 05/01/2018</span></span>

- <span data-ttu-id="2b250-170">**Einddatum**: 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="2b250-170">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="2b250-171">**Object-id**: contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="2b250-171">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="2b250-172">Als uw zoekopdrachten veel logboekvermeldingen retourneren, raden we u aan de procedure in Exchange Online PowerShell te gebruiken **om te zoeken naar controlelogboekvermeldingen en** resultaten later in dit onderwerp naar een ontvanger te sturen.</span><span class="sxs-lookup"><span data-stu-id="2b250-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic.</span></span> <span data-ttu-id="2b250-173">De procedure in die sectie stuurt een XML-bestand als e-mailbijlage naar de ontvangers die u opgeeft, zodat u gemakkelijker de gegevens extraheren waarin u geïnteresseerd bent.</span><span class="sxs-lookup"><span data-stu-id="2b250-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="2b250-174">Zie [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="2b250-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="2b250-175">Details van controlelogboekvermeldingen weergeven</span><span class="sxs-lookup"><span data-stu-id="2b250-175">View details of audit log entries</span></span>

<span data-ttu-id="2b250-176">De cmdlet **ZoekadminLog** retourneert de velden die zijn beschreven in [de inhoud van het controlelogboek](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span><span class="sxs-lookup"><span data-stu-id="2b250-176">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="2b250-177">Van de velden die door de cmdlet worden geretourneerd, bevatten twee velden, **CmdletParameters** en **ModifiedProperties,** aanvullende informatie die standaard niet zichtbaar is.</span><span class="sxs-lookup"><span data-stu-id="2b250-177">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="2b250-178">Als u de inhoud van de velden **CmdletParameters** en **ModifiedProperties wilt weergeven,** gebruikt u de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="2b250-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="2b250-179">U de procedure in Exchange Online PowerShell gebruiken gebruiken **om te zoeken naar controlelogboekvermeldingen en resultaten later** in dit onderwerp naar een ontvanger te sturen om een XML-bestand te maken.</span><span class="sxs-lookup"><span data-stu-id="2b250-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic to create an XML file.</span></span>

<span data-ttu-id="2b250-180">Bij deze procedure worden de volgende begrippen gebruikt:</span><span class="sxs-lookup"><span data-stu-id="2b250-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="2b250-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="2b250-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="2b250-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="2b250-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="2b250-183">Bepaal de criteria waar u naar wilt zoeken, voer de cmdlet **Search-AdminAuditLog** uit en sla de resultaten op in een variabele met de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="2b250-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="2b250-184">Elke controlelogboekvermelding wordt opgeslagen als een arrayelement in de variabele `$Results` .</span><span class="sxs-lookup"><span data-stu-id="2b250-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="2b250-185">U een matrixelement selecteren door de matrixelementindex op te geven.</span><span class="sxs-lookup"><span data-stu-id="2b250-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="2b250-186">Matrixelementenindexen beginnen bij nul (0) voor het eerste matrixelement.</span><span class="sxs-lookup"><span data-stu-id="2b250-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="2b250-187">Als u bijvoorbeeld het vijfde matrixelement, dat een index van 4 heeft, wilt ophalen, gebruikt u de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="2b250-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="2b250-188">De vorige opdracht retourneert de logboekvermelding die is opgeslagen in matrixelement 4.</span><span class="sxs-lookup"><span data-stu-id="2b250-188">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="2b250-189">Als u de inhoud van de velden **CmdletParameters** en **ModifiedProperties** voor dit logboek wilt bekijken, gebruikt u de volgende opdrachten.</span><span class="sxs-lookup"><span data-stu-id="2b250-189">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="2b250-190">Als u de inhoud van de velden **CmdletParameters** of **ModifiedParameters** in een ander logboek wilt weergeven, wijzigt u de matrixelementindex.</span><span class="sxs-lookup"><span data-stu-id="2b250-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>