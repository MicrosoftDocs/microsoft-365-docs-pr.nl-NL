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
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe ze een beheerdersrolgroeprapport kunnen uitvoeren in zelfstandige Exchange Online Protection (EOP). Dit rapport wordt logboeken wanneer een beheerder leden toevoegt aan of verwijdert uit beheerdersrollengroepen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0281dcb13f5cee0ba8db8c4faed5054f481337cf
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204708"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="c2682-104">Een rapport over groepen met beheerdersrollen uitvoeren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="c2682-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c2682-105">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="c2682-105">**Applies to**</span></span>
-  [<span data-ttu-id="c2682-106">Zelfstandige Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c2682-106">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="c2682-107">In zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, wanneer een beheerder leden toevoegt aan of verwijdert uit beheerdersrollengroepen, registreert de service elk exemplaar.</span><span class="sxs-lookup"><span data-stu-id="c2682-107">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="c2682-108">Zie Machtigingen in zelfstandige EOP voor meer informatie over rollengroepen in zelfstandige [EOP.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="c2682-108">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="c2682-109">Wanneer u een rapport van een beheerdersrolgroep in het Exchange-beheercentrum (EAC) uitvoert, worden items weergegeven als zoekresultaten en worden de betrokken rollengroepen weergegeven, wie het lidmaatschap van de rollengroep heeft gewijzigd en wanneer en welke lidmaatschapsupdates zijn uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c2682-109">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="c2682-110">Gebruik dit rapport om wijzigingen in de beheerdersmachtigingen te controleren die zijn toegewezen aan gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c2682-110">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c2682-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="c2682-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c2682-112">Zie Exchange-beheercentrum in zelfstandige EOP om het Exchange-beheercentrum [te openen.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="c2682-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="c2682-113">U moet machtigingen krijgen toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="c2682-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="c2682-114">U hebt met name de rol  **Auditlogboeken** of **Alleen-weergeven auditlogboeken** nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer, **Compliancebeheer** en Beveiligingsbeheerder. </span><span class="sxs-lookup"><span data-stu-id="c2682-114">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="c2682-115">Zie Machtigingen in zelfstandige [EOP](feature-permissions-in-eop.md) en Gebruik de EAC om de lijst met [leden in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="c2682-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="c2682-116">Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in [dit artikel.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="c2682-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="c2682-117">Hebt u problemen?</span><span class="sxs-lookup"><span data-stu-id="c2682-117">Having problems?</span></span> <span data-ttu-id="c2682-118">Vraag om hulp in het [Exchange Online Protection-forum.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="c2682-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="c2682-119">Het EAC gebruiken om een beheerdersrolgroeprapport uit te voeren</span><span class="sxs-lookup"><span data-stu-id="c2682-119">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="c2682-120">Voer het rapport beheerdersrolgroep uit om de wijzigingen in beheerrolgroepen binnen een bepaald tijdsbestek te vinden.</span><span class="sxs-lookup"><span data-stu-id="c2682-120">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="c2682-121">Ga in het EAC naar **Compliance management** \> **Auditing** en kies **vervolgens Een beheerdersrolgroeprapport uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="c2682-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="c2682-122">Configureer de volgende instellingen op de pagina Zoeken naar wijzigingen in **beheerdersrolgroepen** die worden geopend:</span><span class="sxs-lookup"><span data-stu-id="c2682-122">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="c2682-123">**Begindatum** en **einddatum:** Voer een datumbereik in.</span><span class="sxs-lookup"><span data-stu-id="c2682-123">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="c2682-124">Standaard wordt in het rapport gezocht naar wijzigingen die zijn aangebracht in beheerdersrolgroepen in de afgelopen twee weken.</span><span class="sxs-lookup"><span data-stu-id="c2682-124">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="c2682-125">**Rolgroepen selecteren:** standaard worden alle rollengroepen doorzocht.</span><span class="sxs-lookup"><span data-stu-id="c2682-125">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="c2682-126">Als u de resultaten wilt filteren op specifieke rollengroepen, klikt **u op Rolgroepen selecteren.**</span><span class="sxs-lookup"><span data-stu-id="c2682-126">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="c2682-127">Selecteer in het dialoogvenster dat wordt weergegeven een rollengroep en klik **op Toevoegen ->.**</span><span class="sxs-lookup"><span data-stu-id="c2682-127">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="c2682-128">Herhaal deze stap zo vaak als nodig en klik op **OK** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="c2682-128">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="c2682-129">Wanneer u klaar bent, klikt u op **Zoeken**.</span><span class="sxs-lookup"><span data-stu-id="c2682-129">When you're finished, click **Search**.</span></span>

<span data-ttu-id="c2682-130">Als er wijzigingen worden gevonden aan de hand van de criteria die u hebt opgegeven, worden deze weergegeven in het resultatenvenster.</span><span class="sxs-lookup"><span data-stu-id="c2682-130">If any changes are found using the criteria you specified, they will appear in the results pane.</span></span> <span data-ttu-id="c2682-131">Klik op een rollengroep in de zoekresultaten om de wijzigingen in het detailvenster weer te geven.</span><span class="sxs-lookup"><span data-stu-id="c2682-131">Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c2682-132">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="c2682-132">How do you know this worked?</span></span>

<span data-ttu-id="c2682-133">Als u een rapport met beheerdersrolgroepen hebt uitgevoerd, worden rollengroepen die binnen het datumbereik zijn gewijzigd, weergegeven in het deelvenster zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="c2682-133">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane.</span></span> <span data-ttu-id="c2682-134">Als er geen resultaten zijn, zijn er geen wijzigingen in rollengroepen doorgevoerd binnen het opgegeven datumbereik.</span><span class="sxs-lookup"><span data-stu-id="c2682-134">If there are no results, then no changes to role groups have taken place within the specified date range.</span></span> <span data-ttu-id="c2682-135">Als u denkt dat er resultaten moeten zijn, wijzigt u het datumbereik en wordt het rapport opnieuw uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c2682-135">If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="c2682-136">Wijzigingen in lidmaatschap van rollengroep controleren</span><span class="sxs-lookup"><span data-stu-id="c2682-136">Monitor changes to role group membership</span></span>

<span data-ttu-id="c2682-137">Wanneer leden worden toegevoegd aan of verwijderd uit een rollengroep, geven de zoekresultaten die worden weergegeven in het detailvenster aan dat het lidmaatschap van de rollengroep is bijgewerkt en de huidige leden worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c2682-137">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members.</span></span> <span data-ttu-id="c2682-138">In de resultaten wordt niet expliciet vermeld welke gebruiker is toegevoegd of verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c2682-138">The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="c2682-139">Als u wilt bepalen of een gebruiker is toegevoegd of verwijderd, moet u twee afzonderlijke vermeldingen in het rapport vergelijken.</span><span class="sxs-lookup"><span data-stu-id="c2682-139">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="c2682-140">Laten we bijvoorbeeld de volgende logboekgegevens voor de **helpdesk-rollengroep** bekijken:</span><span class="sxs-lookup"><span data-stu-id="c2682-140">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="c2682-141">27-17-2018 16:43 uur</span><span class="sxs-lookup"><span data-stu-id="c2682-141">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="c2682-142">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="c2682-142">Administrator</span></span> <br> <span data-ttu-id="c2682-143">Bijgewerkte leden: Administrator;annb,firenzev;pilarp</span><span class="sxs-lookup"><span data-stu-id="c2682-143">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="c2682-144">06-2018 10:09</span><span class="sxs-lookup"><span data-stu-id="c2682-144">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="c2682-145">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="c2682-145">Administrator</span></span> <br> <span data-ttu-id="c2682-146">Bijgewerkte leden: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="c2682-146">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="c2682-147">19-2-2018 14:12</span><span class="sxs-lookup"><span data-stu-id="c2682-147">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="c2682-148">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="c2682-148">Administrator</span></span> <br> <span data-ttu-id="c2682-149">Bijgewerkte leden: Administrator;annb;firenip;tonip</span><span class="sxs-lookup"><span data-stu-id="c2682-149">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="c2682-150">In dit voorbeeld heeft het gebruikersaccount beheerder de volgende wijzigingen aangebracht:</span><span class="sxs-lookup"><span data-stu-id="c2682-150">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="c2682-151">Op 06-2-2018 hebben ze de gebruikers-tonip toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="c2682-151">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="c2682-152">Op 19-2-2-2018 hebben ze de gebruikers pilarp verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c2682-152">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="c2682-153">Zelfstandige Exchange Online PowerShell gebruiken om te zoeken naar auditlogboekgegevens</span><span class="sxs-lookup"><span data-stu-id="c2682-153">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="c2682-154">U kunt Exchange Online PowerShell gebruiken om te zoeken naar auditlogboekgegevens die voldoen aan de criteria die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="c2682-154">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="c2682-155">Zie Zoekcriteria voor [Search-AdminAuditLog voor](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)een lijst met zoekcriteria.</span><span class="sxs-lookup"><span data-stu-id="c2682-155">For a list of search criteria, see [Search-AdminAuditLog search criteria](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="c2682-156">In deze procedure wordt de **cmdlet Search-AdminAuditLog** gebruikt en worden zoekresultaten weergegeven in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2682-156">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="c2682-157">U kunt deze cmdlet gebruiken wanneer u een reeks resultaten wilt retourneren die de limieten overschrijdt die zijn gedefinieerd op de cmdlet **New-AdminAuditLogSearch** of in de EAC-auditrapportagerapporten.</span><span class="sxs-lookup"><span data-stu-id="c2682-157">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="c2682-158">Als u in het auditlogboek wilt zoeken naar criteria die u opgeeft, gebruikt u de volgende syntaxis.</span><span class="sxs-lookup"><span data-stu-id="c2682-158">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="c2682-159">De **cmdlet Search-AdminAuditLog** retourneert standaard maximaal 1.000 logboekgegevens.</span><span class="sxs-lookup"><span data-stu-id="c2682-159">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="c2682-160">Gebruik de _parameter ResultSize_ om maximaal 250.000 logboekgegevens op te geven.</span><span class="sxs-lookup"><span data-stu-id="c2682-160">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="c2682-161">Of gebruik de waarde om `Unlimited` alle items te retourneren.</span><span class="sxs-lookup"><span data-stu-id="c2682-161">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="c2682-162">In dit voorbeeld wordt een zoekopdracht uitgevoerd naar alle controlelogboekgegevens met de volgende criteria:</span><span class="sxs-lookup"><span data-stu-id="c2682-162">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="c2682-163">**Begindatum**: 08-04-2018</span><span class="sxs-lookup"><span data-stu-id="c2682-163">**Start date**: 08/04/2018</span></span>
- <span data-ttu-id="c2682-164">**Einddatum**: 03-10-2018</span><span class="sxs-lookup"><span data-stu-id="c2682-164">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="c2682-165">**Gebruikers-ID's:** `davids` `chrisd` , , `kima`</span><span class="sxs-lookup"><span data-stu-id="c2682-165">**User IDs**: `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="c2682-166">**Cmdlets**: **Postvak instellen**</span><span class="sxs-lookup"><span data-stu-id="c2682-166">**Cmdlets**: **Set-Mailbox**</span></span>
- <span data-ttu-id="c2682-167">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="c2682-167">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="c2682-168">In dit voorbeeld wordt gezocht naar wijzigingen in een specifiek postvak.</span><span class="sxs-lookup"><span data-stu-id="c2682-168">This example searches for changes made to a specific mailbox.</span></span> <span data-ttu-id="c2682-169">Dit is handig als u problemen oplost of als u informatie wilt verstrekken voor een onderzoek.</span><span class="sxs-lookup"><span data-stu-id="c2682-169">This is useful if you're troubleshooting or you need to provide information for an investigation.</span></span> <span data-ttu-id="c2682-170">De volgende criteria worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="c2682-170">The following criteria are used:</span></span>

- <span data-ttu-id="c2682-171">**Begindatum**: 05-01-2018</span><span class="sxs-lookup"><span data-stu-id="c2682-171">**Start date**: 05/01/2018</span></span>
- <span data-ttu-id="c2682-172">**Einddatum**: 03-10-2018</span><span class="sxs-lookup"><span data-stu-id="c2682-172">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="c2682-173">**Object-id:** contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="c2682-173">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="c2682-174">Als uw zoekopdrachten veel logboekgegevens retourneren, raden we u aan de procedure in **Exchange Online PowerShell** te gebruiken om te zoeken naar auditlogboekgegevens en resultaten te verzenden naar een geadresseerde verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="c2682-174">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="c2682-175">Met de procedure in die sectie wordt een XML-bestand als e-mailbijlage verzonden naar de geadresseerden die u opgeeft, zodat u gemakkelijker de gegevens kunt oppakken waarin u geïnteresseerd bent.</span><span class="sxs-lookup"><span data-stu-id="c2682-175">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="c2682-176">Zie [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="c2682-176">For detailed syntax and parameter information, see [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="c2682-177">Details van controlelogboekgegevens weergeven</span><span class="sxs-lookup"><span data-stu-id="c2682-177">View details of audit log entries</span></span>

<span data-ttu-id="c2682-178">De **cmdlet Search-AdminAuditLog** retourneert de velden die worden beschreven in [de inhoud van het auditlogboek.](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)</span><span class="sxs-lookup"><span data-stu-id="c2682-178">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="c2682-179">Van de velden die door de cmdlet worden geretourneerd, bevatten twee velden, **CmdletParameters** en **ModifiedProperties,** aanvullende informatie die standaard niet kan worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c2682-179">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="c2682-180">Als u de inhoud van de **velden CmdletParameters** en **ModifiedProperties** wilt weergeven, gebruikt u de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="c2682-180">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="c2682-181">U kunt de procedure in **Exchange Online PowerShell** ook gebruiken om te zoeken naar auditlogboekgegevens en resultaten te verzenden naar een geadresseerde verderop in dit artikel om een XML-bestand te maken.</span><span class="sxs-lookup"><span data-stu-id="c2682-181">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="c2682-182">In deze procedure worden de volgende concepten gebruikt:</span><span class="sxs-lookup"><span data-stu-id="c2682-182">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="c2682-183">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="c2682-183">about_Arrays</span></span>](/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="c2682-184">about_Variables</span><span class="sxs-lookup"><span data-stu-id="c2682-184">about_Variables</span></span>](/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="c2682-185">Bepaal de criteria die u wilt zoeken, voer de cmdlet **Search-AdminAuditLog** uit en sla de resultaten op in een variabele met de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="c2682-185">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="c2682-186">Elke auditlogboekinvoer wordt opgeslagen als een matrixelement in de variabele `$Results` .</span><span class="sxs-lookup"><span data-stu-id="c2682-186">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="c2682-187">U kunt een matrixelement selecteren door de matrixelementindex op te geven.</span><span class="sxs-lookup"><span data-stu-id="c2682-187">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="c2682-188">Matrixelementindexen beginnen bij nul (0) voor het eerste matrixelement.</span><span class="sxs-lookup"><span data-stu-id="c2682-188">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="c2682-189">Als u bijvoorbeeld het 5e matrixelement wilt ophalen met een index van 4, gebruikt u de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="c2682-189">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="c2682-190">De vorige opdracht retourneert de logboekinvoer die is opgeslagen in matrixelement 4.</span><span class="sxs-lookup"><span data-stu-id="c2682-190">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="c2682-191">Als u de inhoud van de **velden CmdletParameters** en **ModifiedProperties** voor deze logboekinvoer wilt zien, gebruikt u de volgende opdrachten.</span><span class="sxs-lookup"><span data-stu-id="c2682-191">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="c2682-192">Als u de inhoud van de **velden CmdletParameters** of **ModifiedParameters** wilt weergeven in een andere logboekinvoer, wijzigt u de matrixelementindex.</span><span class="sxs-lookup"><span data-stu-id="c2682-192">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>