---
title: Een rapport over groepen met beheerdersrollen uitvoeren in standalone EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u een groepsrapport met beheerdersrollen uitvoert in zelfstandige Exchange Online Protection (EOP). Dit rapport meldt wanneer een beheerder leden toevoegt aan of verwijdert uit groepen beheerdersrollen.
ms.openlocfilehash: cd7ca13a3d863240a0f2608ed13321cbe3d50ad2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659259"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="916fc-104">Een rapport over groepen met beheerdersrollen uitvoeren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="916fc-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="916fc-105">Bij zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, wanneer een beheerder leden toevoegt aan of verwijdert uit groepen met administratieve rollen, wordt elk exemplaar in de service geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="916fc-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="916fc-106">Zie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md)voor meer informatie over rollen groepen in zelfstandige EOP.</span><span class="sxs-lookup"><span data-stu-id="916fc-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="916fc-107">Wanneer u een rapport in het rollencentrum van de beheerder uitvoert in het Exchange-Beheercentrum, worden vermeldingen weergegeven als zoekresultaten en worden de betreffende Rolgroepen opgenomen, die het lidmaatschap van rollen groepen en wanneer ze zijn gewijzigd en welke lidmaatschaps updates zijn aangebracht.</span><span class="sxs-lookup"><span data-stu-id="916fc-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="916fc-108">Gebruik dit rapport om wijzigingen aan te brengen in de beheerdersmachtigingen die zijn toegewezen aan gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="916fc-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="916fc-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="916fc-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="916fc-110">Om het Exchange-Beheercentrum te openen, raadpleegt u het [Exchange-Beheercentrum in zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="916fc-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="916fc-111">U moet machtigingen zijn toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="916fc-111">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="916fc-112">Specifiek hebt u de rol **audit** Logboeken of **alleen-lezen** rollen nodig die zijn toegewezen aan de rollen groepen **Organisatiebeheer**, **Compliance Management** en **beveiligingsbeheerder** .</span><span class="sxs-lookup"><span data-stu-id="916fc-112">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="916fc-113">Zie voor meer informatie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en [Gebruik de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="916fc-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="916fc-114">Zie toetscombinaties [voor het Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)voor informatie over toetscombinaties die van toepassing kunnen zijn op de procedures in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="916fc-114">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="916fc-115">Problemen?</span><span class="sxs-lookup"><span data-stu-id="916fc-115">Having problems?</span></span> <span data-ttu-id="916fc-116">Vraag om hulp op het forum van [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="916fc-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="916fc-117">Het rapport van de rollen groep in de lijst met beheerders uitvoeren</span><span class="sxs-lookup"><span data-stu-id="916fc-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="916fc-118">Voer het rapport rollen groep van beheerder uit om de wijzigingen in rollen groepen binnen een bepaald tijdsbestek te vinden.</span><span class="sxs-lookup"><span data-stu-id="916fc-118">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="916fc-119">Ga in het Exchange-Beheercentrum naar **nalevings beheer** \> en kies vervolgens **een beheerrapport** van de beheerderrol.</span><span class="sxs-lookup"><span data-stu-id="916fc-119">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="916fc-120">Configureer de volgende instellingen op de pagina **rollen groepen zoeken naar beheerders** die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="916fc-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="916fc-121">**Begindatum** en **einddatum**: Voer een datumbereik in.</span><span class="sxs-lookup"><span data-stu-id="916fc-121">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="916fc-122">Standaard wordt in de lijst in de afgelopen twee weken gezocht naar wijzigingen in rollen groepen met beheerders.</span><span class="sxs-lookup"><span data-stu-id="916fc-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="916fc-123">**Rollen groepen selecteren**: standaard worden alle rollen groepen gezocht.</span><span class="sxs-lookup"><span data-stu-id="916fc-123">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="916fc-124">Als u de resultaten wilt filteren op specifieke rollen groepen, klikt u op **rollen groepen selecteren**.</span><span class="sxs-lookup"><span data-stu-id="916fc-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="916fc-125">Selecteer in het dialoogvenster dat wordt weergegeven een rolgroep en klik op **add->**.</span><span class="sxs-lookup"><span data-stu-id="916fc-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="916fc-126">Herhaal deze stap zo vaak als nodig is en klik op **OK** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="916fc-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="916fc-127">Wanneer u klaar bent, klikt u op **zoeken**.</span><span class="sxs-lookup"><span data-stu-id="916fc-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="916fc-128">Als er wijzigingen zijn gevonden met de criteria die u hebt opgegeven, worden deze weergegeven in het deelvenster resultaten.</span><span class="sxs-lookup"><span data-stu-id="916fc-128">If any changes are found using the criteria you specified, they will appear in the results pane.</span></span> <span data-ttu-id="916fc-129">Klik in de zoekresultaten op een rolgroep om de wijzigingen weer te geven in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="916fc-129">Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="916fc-130">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="916fc-130">How do you know this worked?</span></span>

<span data-ttu-id="916fc-131">Als u het rapport rollen groep van beheerder hebt uitgevoerd, worden rollen groepen die zijn gewijzigd in het datumbereik weergegeven in het deelvenster Zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="916fc-131">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane.</span></span> <span data-ttu-id="916fc-132">Als er geen resultaten zijn, zijn er geen wijzigingen in rollen groepen binnen het opgegeven datumbereik.</span><span class="sxs-lookup"><span data-stu-id="916fc-132">If there are no results, then no changes to role groups have taken place within the specified date range.</span></span> <span data-ttu-id="916fc-133">Als u denkt dat er resultaten moeten zijn, wijzigt u het datumbereik en voert u het rapport opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="916fc-133">If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="916fc-134">Wijzigingen in lidmaatschap van rollen groepen controleren</span><span class="sxs-lookup"><span data-stu-id="916fc-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="916fc-135">Wanneer leden worden toegevoegd aan of verwijderd uit een rollen groep, wordt in de zoekresultaten die in het detailvenster worden weergegeven, aangegeven dat het lidmaatschap van de rollen groep is bijgewerkt en worden de huidige leden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="916fc-135">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members.</span></span> <span data-ttu-id="916fc-136">De resultaten hebben geen expliciete gevolgen voor het toevoegen of verwijderen van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="916fc-136">The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="916fc-137">Als u wilt bepalen of een gebruiker is toegevoegd of verwijderd, moet u twee afzonderlijke items in het rapport vergelijken.</span><span class="sxs-lookup"><span data-stu-id="916fc-137">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="916fc-138">Laten we bijvoorbeeld kijken naar de volgende logboekvermeldingen voor de rollen groep **helpdesk** :</span><span class="sxs-lookup"><span data-stu-id="916fc-138">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="916fc-139">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="916fc-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="916fc-140">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="916fc-140">Administrator</span></span> <br> <span data-ttu-id="916fc-141">Bijgewerkte leden: beheerder; ANNB, florencef; pilarp</span><span class="sxs-lookup"><span data-stu-id="916fc-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="916fc-142">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="916fc-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="916fc-143">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="916fc-143">Administrator</span></span> <br> <span data-ttu-id="916fc-144">Bijgewerkte leden: beheerder; ANNB; florencef; pilarp; tonip</span><span class="sxs-lookup"><span data-stu-id="916fc-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="916fc-145">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="916fc-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="916fc-146">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="916fc-146">Administrator</span></span> <br> <span data-ttu-id="916fc-147">Bijgewerkte leden: beheerder; ANNB; florencef; tonip</span><span class="sxs-lookup"><span data-stu-id="916fc-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="916fc-148">In dit voorbeeld hebben we de volgende wijzigingen aangebracht in het gebruikersaccount van de beheerder:</span><span class="sxs-lookup"><span data-stu-id="916fc-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="916fc-149">Op 2/06/2018 hebben ze de gebruikers tonip toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="916fc-149">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="916fc-150">Op 2/19/2018 hebben ze de gebruiker pilarp verwijderd.</span><span class="sxs-lookup"><span data-stu-id="916fc-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="916fc-151">Zelfstandige Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen</span><span class="sxs-lookup"><span data-stu-id="916fc-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="916fc-152">U kunt Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen die voldoen aan de criteria die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="916fc-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="916fc-153">Zie Zoek [criteria zoeken in AdminAuditLog](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)voor een overzicht van zoekcriteria.</span><span class="sxs-lookup"><span data-stu-id="916fc-153">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="916fc-154">Deze procedure gebruikt de **Search-AdminAuditLog-** cmdlet en toont zoekresultaten in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="916fc-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="916fc-155">U kunt deze cmdlet gebruiken wanneer u een reeks resultaten moet retourneren die de limieten voor de **New-AdminAuditLogSearch-** cmdlet of de rapporten van de audittrail-controlerapporten overschrijden.</span><span class="sxs-lookup"><span data-stu-id="916fc-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="916fc-156">Gebruik de volgende syntaxis om in het auditlogboek te zoeken naar criteria die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="916fc-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="916fc-157">Met de cmdlet **Search-AdminAuditLog** wordt standaard een maximum van 1.000-logboekvermeldingen geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="916fc-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="916fc-158">Gebruik de parameter _ResultSize_ om maximaal 250.000 logboekvermeldingen op te geven.</span><span class="sxs-lookup"><span data-stu-id="916fc-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="916fc-159">Of gebruik de waarde `Unlimited` om alle items te retourneren.</span><span class="sxs-lookup"><span data-stu-id="916fc-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="916fc-160">In dit voorbeeld wordt een zoekopdracht uitgevoerd naar alle controlelogboekvermeldingen met de volgende criteria:</span><span class="sxs-lookup"><span data-stu-id="916fc-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="916fc-161">**Begindatum**: 08/04/2018</span><span class="sxs-lookup"><span data-stu-id="916fc-161">**Start date**: 08/04/2018</span></span>
- <span data-ttu-id="916fc-162">**Einddatum**: 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="916fc-162">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="916fc-163">**Gebruikers-id's**: `davids` , `chrisd``kima`</span><span class="sxs-lookup"><span data-stu-id="916fc-163">**User IDs**: `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="916fc-164">**Cmdlets**: **set-mailbox**</span><span class="sxs-lookup"><span data-stu-id="916fc-164">**Cmdlets**: **Set-Mailbox**</span></span>
- <span data-ttu-id="916fc-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="916fc-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="916fc-166">In dit voorbeeld wordt gezocht naar wijzigingen die zijn aangebracht in een specifiek postvak.</span><span class="sxs-lookup"><span data-stu-id="916fc-166">This example searches for changes made to a specific mailbox.</span></span> <span data-ttu-id="916fc-167">Dit is handig als u problemen ondervindt of als u informatie over een onderzoek moet invoeren.</span><span class="sxs-lookup"><span data-stu-id="916fc-167">This is useful if you're troubleshooting or you need to provide information for an investigation.</span></span> <span data-ttu-id="916fc-168">De volgende criteria worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="916fc-168">The following criteria are used:</span></span>

- <span data-ttu-id="916fc-169">**Begindatum**: 05/01/2018</span><span class="sxs-lookup"><span data-stu-id="916fc-169">**Start date**: 05/01/2018</span></span>
- <span data-ttu-id="916fc-170">**Einddatum**: 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="916fc-170">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="916fc-171">**Object-id**: contoso.com/users/DavidS</span><span class="sxs-lookup"><span data-stu-id="916fc-171">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="916fc-172">Als u in uw zoekopdrachten een groot aantal logboekvermeldingen oplevert, is het raadzaam de procedure te volgen die wordt beschreven in **Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen en om resultaten naar een geadresseerde te verzenden** verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="916fc-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="916fc-173">De procedure in dat sectie verzendt een XML-bestand als e-mailbijlage bij de geadresseerden die u opgeeft, zodat u gemakkelijker de gewenste gegevens kunt extraheren.</span><span class="sxs-lookup"><span data-stu-id="916fc-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="916fc-174">Zie [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="916fc-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="916fc-175">Details van controlelogboekvermeldingen weergeven</span><span class="sxs-lookup"><span data-stu-id="916fc-175">View details of audit log entries</span></span>

<span data-ttu-id="916fc-176">Met de cmdlet **Search-AdminAuditLog** worden de velden geretourneerd die zijn beschreven in de inhoud van het [controlelogboek](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span><span class="sxs-lookup"><span data-stu-id="916fc-176">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="916fc-177">Van de velden die worden geretourneerd door de cmdlets, twee velden, **CmdletParameters** en **ModifiedProperties**, bevatten aanvullende informatie die standaard niet kan worden bekeken.</span><span class="sxs-lookup"><span data-stu-id="916fc-177">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="916fc-178">Voer de volgende stappen uit om de inhoud van de velden **CmdletParameters** en **ModifiedProperties** weer te geven.</span><span class="sxs-lookup"><span data-stu-id="916fc-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="916fc-179">U kunt ook de procedure in **Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen en de resultaten naar een geadresseerde te verzenden** verderop in dit artikel als u een XML-bestand wilt maken.</span><span class="sxs-lookup"><span data-stu-id="916fc-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="916fc-180">Deze procedure gebruikt de volgende concepten:</span><span class="sxs-lookup"><span data-stu-id="916fc-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="916fc-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="916fc-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="916fc-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="916fc-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="916fc-183">Bepaal de criteria waarnaar u wilt zoeken, voer de **Search-AdminAuditLog-** cmdlet uit en sla de resultaten op in een variabele met behulp van de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="916fc-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="916fc-184">Elk item in het auditlogboek wordt opgeslagen als een matrixelement in de variabele `$Results` .</span><span class="sxs-lookup"><span data-stu-id="916fc-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="916fc-185">U kunt een matrixelement selecteren door de index van het matrixelement op te geven.</span><span class="sxs-lookup"><span data-stu-id="916fc-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="916fc-186">Matrixelement indexen beginnen op nul (0) voor het eerste matrixelement.</span><span class="sxs-lookup"><span data-stu-id="916fc-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="916fc-187">Als u bijvoorbeeld een vijfde matrixelement wilt ophalen met een index van 4, gebruikt u de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="916fc-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="916fc-188">Met de vorige opdracht wordt de logboekvermelding geretourneerd die is opgeslagen in het matrixelement 4.</span><span class="sxs-lookup"><span data-stu-id="916fc-188">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="916fc-189">Ga als volgt te werk om de inhoud van de velden **CmdletParameters** en **ModifiedProperties** voor dit logboekitem te bekijken.</span><span class="sxs-lookup"><span data-stu-id="916fc-189">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="916fc-190">Als u de inhoud van de **CmdletParameters** -of **ModifiedParameters** -velden in een andere vermelding in het logboek wilt weergeven, wijzigt u de index van het matrixelement.</span><span class="sxs-lookup"><span data-stu-id="916fc-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>
