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
description: Beheerders kunnen informatie krijgen over het uitvoeren van een beheerdersrolgroeprapport in de zelfstandige versie van Exchange Online Protection (EOP). Dit rapport registreert wanneer een beheerder leden toevoegt aan of verwijdert uit beheerdersrolgroepen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 507fbe6fb6c99677cf91b6eb824bf110f1c826f3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166625"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="8f6ca-104">Een rapport over groepen met beheerdersrollen uitvoeren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="8f6ca-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8f6ca-105">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="8f6ca-105">**Applies to**</span></span>
-  [<span data-ttu-id="8f6ca-106">Zelfstandige versie van Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8f6ca-106">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="8f6ca-107">Als een beheerder in zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken leden toevoegt aan of verwijdert uit beheerrolgroepen, wordt elke gebeurtenis in de servicelogboeken bij de service logboeken geplaatst.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-107">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="8f6ca-108">Zie Machtigingen in de zelfstandige EOP voor meer informatie over rollengroepen in zelfstandige [EOP.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="8f6ca-108">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="8f6ca-109">Wanneer u een rapport voor een beheerdersrolgroep in het Exchange-beheercentrum (EAC) runt, worden vermeldingen weergegeven als zoekresultaten en worden de betrokken rollengroepen vermeld, wie het lidmaatschap van de rollengroep heeft gewijzigd en wanneer en welke lidmaatschapsupdates zijn aangebracht.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-109">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="8f6ca-110">Gebruik dit rapport om wijzigingen bij te houden in de beheerdersmachtigingen die zijn toegewezen aan gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-110">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8f6ca-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="8f6ca-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8f6ca-112">Als u het Exchange-beheercentrum wilt openen, gaat u naar [het Exchange-beheercentrum in de zelfstandige EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="8f6ca-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="8f6ca-113">U moet machtigingen toegewezen krijgen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="8f6ca-114">U hebt met name de rol  **Auditlogboeken** of Auditlogboeken voor alleen **weergeven** nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer,  **Compliancebeheer** en Beveiligingsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-114">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="8f6ca-115">Zie Machtigingen in zelfstandige EOP en gebruik het [EAC](feature-permissions-in-eop.md) om de lijst met leden [in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="8f6ca-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="8f6ca-116">Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over [sneltoetsen](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)die van toepassing kunnen zijn op de procedures in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="8f6ca-117">Hebt u problemen?</span><span class="sxs-lookup"><span data-stu-id="8f6ca-117">Having problems?</span></span> <span data-ttu-id="8f6ca-118">Vraag om hulp op het forum [van Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="8f6ca-118">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="8f6ca-119">Het EAC gebruiken om een beheerdersrolgroepsrapport uit te voeren</span><span class="sxs-lookup"><span data-stu-id="8f6ca-119">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="8f6ca-120">Voer het rapport beheerdersrolgroep uit om de wijzigingen in beheerrolgroepen binnen een bepaalde periode te vinden.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-120">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="8f6ca-121">Ga in het Beheerbeheer naar  \> **Auditing** en **kies Een rapport met beheerdersrolgroep uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="8f6ca-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="8f6ca-122">Configureer **de volgende instellingen op** de pagina Zoeken naar wijzigingen in beheerdersrolgroepen die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="8f6ca-122">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="8f6ca-123">**Begindatum** **en einddatum:** voer een datumbereik in.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-123">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="8f6ca-124">In het rapport wordt standaard gezocht naar wijzigingen die in de afgelopen twee weken zijn aangebracht in beheerdersrolgroepen.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-124">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="8f6ca-125">**Rollengroepen selecteren:** standaard worden alle rollengroepen doorzocht.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-125">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="8f6ca-126">Als u de resultaten wilt filteren op specifieke rollengroepen, klikt u **op Rollengroepen selecteren.**</span><span class="sxs-lookup"><span data-stu-id="8f6ca-126">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="8f6ca-127">Selecteer een rollengroep in het dialoogvenster dat wordt weergegeven en klik op **toevoegen ->.**</span><span class="sxs-lookup"><span data-stu-id="8f6ca-127">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="8f6ca-128">Herhaal deze stap zo vaak als nodig is en klik op **OK** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-128">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="8f6ca-129">Klik op Zoeken wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="8f6ca-129">When you're finished, click **Search**.</span></span>

<span data-ttu-id="8f6ca-130">Als er wijzigingen worden aangetroffen aan de hand van de criteria die u hebt opgegeven, worden deze weergegeven in het deelvenster met resultaten.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-130">If any changes are found using the criteria you specified, they will appear in the results pane.</span></span> <span data-ttu-id="8f6ca-131">Klik op een rollengroep in de zoekresultaten om de wijzigingen in het detailvenster te bekijken.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-131">Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8f6ca-132">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="8f6ca-132">How do you know this worked?</span></span>

<span data-ttu-id="8f6ca-133">Als u een rapport met beheerdersrolgroepen hebt uitgevoerd, worden rollengroepen die zijn gewijzigd binnen het datumbereik weergegeven in het deelvenster met zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-133">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane.</span></span> <span data-ttu-id="8f6ca-134">Als er geen resultaten zijn, hebben er geen wijzigingen in rollengroepen plaatsgevonden binnen het opgegeven datumbereik.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-134">If there are no results, then no changes to role groups have taken place within the specified date range.</span></span> <span data-ttu-id="8f6ca-135">Als u denkt dat er resultaten moeten zijn, wijzigt u het datumbereik en voer u het rapport opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-135">If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="8f6ca-136">Wijzigingen in lidmaatschap van rollengroep controleren</span><span class="sxs-lookup"><span data-stu-id="8f6ca-136">Monitor changes to role group membership</span></span>

<span data-ttu-id="8f6ca-137">Wanneer leden worden toegevoegd aan of verwijderd uit een rollengroep, geven de zoekresultaten in het detailvenster aan dat het lidmaatschap van de rollengroep is bijgewerkt en dat de huidige leden worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-137">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members.</span></span> <span data-ttu-id="8f6ca-138">In de resultaten wordt niet expliciet vermeld welke gebruiker is toegevoegd of verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-138">The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="8f6ca-139">Om te bepalen of een gebruiker is toegevoegd of verwijderd, moet u twee afzonderlijke vermeldingen in het rapport vergelijken.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-139">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="8f6ca-140">Bekijk bijvoorbeeld de volgende logboekgegevens voor de **HelpDesk-rollengroep:**</span><span class="sxs-lookup"><span data-stu-id="8f6ca-140">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="8f6ca-141">27-1-2018 16:43 uur</span><span class="sxs-lookup"><span data-stu-id="8f6ca-141">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="8f6ca-142">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="8f6ca-142">Administrator</span></span> <br> <span data-ttu-id="8f6ca-143">Bijgewerkte leden: Administrator;annb,provider;pilarp</span><span class="sxs-lookup"><span data-stu-id="8f6ca-143">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="8f6ca-144">06-02-2018 10:09 uur</span><span class="sxs-lookup"><span data-stu-id="8f6ca-144">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="8f6ca-145">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="8f6ca-145">Administrator</span></span> <br> <span data-ttu-id="8f6ca-146">Bijgewerkte leden: Administrator;annb;administratorf;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="8f6ca-146">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="8f6ca-147">19-2-2018 14:12 uur</span><span class="sxs-lookup"><span data-stu-id="8f6ca-147">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="8f6ca-148">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="8f6ca-148">Administrator</span></span> <br> <span data-ttu-id="8f6ca-149">Bijgewerkte leden: Administrator;annb;administratorf;tonip</span><span class="sxs-lookup"><span data-stu-id="8f6ca-149">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="8f6ca-150">In dit voorbeeld heeft het beheerdersaccount de volgende wijzigingen aangebracht:</span><span class="sxs-lookup"><span data-stu-id="8f6ca-150">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="8f6ca-151">Op 6-2-2018 is de tonip van de gebruiker toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-151">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="8f6ca-152">Op 19-2-2018 wordt de gebruiker pilarp verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-152">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="8f6ca-153">Zelfstandige Exchange Online PowerShell gebruiken om te zoeken naar vermeldingen in het auditlogboek</span><span class="sxs-lookup"><span data-stu-id="8f6ca-153">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="8f6ca-154">U kunt Exchange Online PowerShell gebruiken om te zoeken naar vermeldingen in het auditlogboek die voldoen aan de criteria die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-154">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="8f6ca-155">Zie zoekcriteria in [Search-AdminAuditLog voor een lijst met zoekcriteria.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)</span><span class="sxs-lookup"><span data-stu-id="8f6ca-155">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="8f6ca-156">Voor deze procedure wordt de cmdlet **Search-AdminAuditLog** gebruikt en worden zoekresultaten weergegeven in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-156">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="8f6ca-157">U kunt deze cmdlet gebruiken als u een set resultaten wilt retourneren die de limieten overschrijdt die zijn gedefinieerd voor de cmdlet **New-AdminAuditLogSearch** of in de rapporten van de EAC-auditrapportage.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-157">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="8f6ca-158">Gebruik de volgende syntaxis om in het auditlogboek te zoeken naar criteria die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-158">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="8f6ca-159">De **cmdlet Search-AdminAuditLog** retourneert standaard maximaal 1000 logboekgegevens.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-159">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="8f6ca-160">Gebruik de _parameter ResultSize_ om maximaal 250.000 logboekgegevens op te geven.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-160">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="8f6ca-161">Of gebruik de waarde om `Unlimited` alle items te retourneren.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-161">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="8f6ca-162">In dit voorbeeld wordt gezocht naar alle vermeldingen in het auditlogboek met de volgende criteria:</span><span class="sxs-lookup"><span data-stu-id="8f6ca-162">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="8f6ca-163">**Begindatum:** 04-08-2018</span><span class="sxs-lookup"><span data-stu-id="8f6ca-163">**Start date**: 08/04/2018</span></span>
- <span data-ttu-id="8f6ca-164">**Einddatum:** 3-10-2018</span><span class="sxs-lookup"><span data-stu-id="8f6ca-164">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="8f6ca-165">**Gebruikers-ids:** `davids` `chrisd` , `kima`</span><span class="sxs-lookup"><span data-stu-id="8f6ca-165">**User IDs**: `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="8f6ca-166">**Cmdlets:** **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="8f6ca-166">**Cmdlets**: **Set-Mailbox**</span></span>
- <span data-ttu-id="8f6ca-167">**Parameters:** _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="8f6ca-167">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="8f6ca-168">In dit voorbeeld wordt gezocht naar wijzigingen in een specifiek postvak.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-168">This example searches for changes made to a specific mailbox.</span></span> <span data-ttu-id="8f6ca-169">Dit is handig als u aan het oplossen van problemen werkt of als u informatie moet geven voor een onderzoek.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-169">This is useful if you're troubleshooting or you need to provide information for an investigation.</span></span> <span data-ttu-id="8f6ca-170">De volgende criteria worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="8f6ca-170">The following criteria are used:</span></span>

- <span data-ttu-id="8f6ca-171">**Begindatum:** 01-05-2018</span><span class="sxs-lookup"><span data-stu-id="8f6ca-171">**Start date**: 05/01/2018</span></span>
- <span data-ttu-id="8f6ca-172">**Einddatum:** 3-10-2018</span><span class="sxs-lookup"><span data-stu-id="8f6ca-172">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="8f6ca-173">**Object-id:** contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="8f6ca-173">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="8f6ca-174">Als uw zoekopdrachten veel logboekgegevens retourneren, raden we u aan de procedure in **Exchange Online PowerShell** te gebruiken om te zoeken naar vermeldingen in het auditlogboek en resultaten te verzenden naar een geadresseerde verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-174">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="8f6ca-175">Met de procedure in die sectie wordt een XML-bestand als e-mailbijlage verzonden naar de geadresseerden die u opgeeft, zodat u de geïnteresseerde gegevens gemakkelijker kunt extraheren.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-175">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="8f6ca-176">Zie [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-176">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="8f6ca-177">Details van vermeldingen in het auditlogboek weergeven</span><span class="sxs-lookup"><span data-stu-id="8f6ca-177">View details of audit log entries</span></span>

<span data-ttu-id="8f6ca-178">De **cmdlet Search-AdminAuditLog** retourneert de velden die worden beschreven in de [inhoud van het auditlogboek.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)</span><span class="sxs-lookup"><span data-stu-id="8f6ca-178">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="8f6ca-179">Van de velden die worden geretourneerd door de cmdlet, bevatten twee velden, **CmdletParameters** en **ModifiedProperties,** aanvullende informatie die standaard niet kan worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-179">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="8f6ca-180">Als u de inhoud van de **velden CmdletParameters** en **ModifiedProperties** wilt weergeven, gebruikt u de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-180">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="8f6ca-181">U kunt ook de procedure in **Exchange Online PowerShell** gebruiken om te zoeken naar vermeldingen in het auditlogboek en resultaten te verzenden naar een geadresseerde verderop in dit artikel om een XML-bestand te maken.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-181">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="8f6ca-182">Voor deze procedure worden de volgende concepten gebruikt:</span><span class="sxs-lookup"><span data-stu-id="8f6ca-182">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="8f6ca-183">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="8f6ca-183">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="8f6ca-184">about_Variables</span><span class="sxs-lookup"><span data-stu-id="8f6ca-184">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="8f6ca-185">Bepaal de criteria die u wilt zoeken, voer de cmdlet **Search-AdminAuditLog** uit en sla de resultaten op in een variabele met behulp van de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-185">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="8f6ca-186">Elke auditlogboekinvoer wordt opgeslagen als een matrixelement in de `$Results` variabele.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-186">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="8f6ca-187">U kunt een matrixelement selecteren door de index van het matrixelement op te geven.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-187">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="8f6ca-188">Indexen van matrixelementen beginnen bij nul (0) voor het eerste matrixelement.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-188">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="8f6ca-189">Als u bijvoorbeeld het vijfde matrixelement wilt ophalen, dat een index van 4 bevat, gebruikt u de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-189">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="8f6ca-190">De vorige opdracht retourneert de logboekinvoer die is opgeslagen in matrixelement 4.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-190">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="8f6ca-191">Gebruik de volgende opdrachten om de inhoud van de velden **CmdletParameters** en **ModifiedProperties** voor deze logboekinvoer te bekijken.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-191">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="8f6ca-192">Als u de inhoud van de **velden CmdletParameters** of **ModifiedParameters** wilt weergeven in een andere logboekinvoer, wijzigt u de index van het matrixelement.</span><span class="sxs-lookup"><span data-stu-id="8f6ca-192">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>
