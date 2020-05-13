---
title: Bekijk het logboek voor beheerderscontrole in zelfstandige EOP
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
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Beheerders kunnen leren hoe ze het beheercontrolelogboek in de zelfstandige Exchange Online Protection (EOP) kunnen bekijken en doorzoeken.
ms.openlocfilehash: 3aedebc97ccd32c1641510017a276ddbe4770633
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208474"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="0fa96-103">Bekijk het logboek voor beheerderscontrole in zelfstandige EOP</span><span class="sxs-lookup"><span data-stu-id="0fa96-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="0fa96-104">In zelfstandige Exchange Online Protection-organisaties (EOP)-organisaties zonder Exchange Online-postvakken u het Exchange-beheercentrum (EAC) of de zelfstandige EOP PowerShell gebruiken om items in het beheercontrolelogboek te zoeken en weer te geven.</span><span class="sxs-lookup"><span data-stu-id="0fa96-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="0fa96-105">Het beheercontrolelogboek registreert specifieke acties op basis van zelfstandige EOP PowerShell-cmdlets, uitgevoerd door beheerders en gebruikers aan welke beheerders beheerdersbevoegdheden zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0fa96-105">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="0fa96-106">Vermeldingen in het beheercontrolelogboek geven u informatie over welke cmdlet werd uitgevoerd, welke parameters werden gebruikt, wie de cmdlet heeft uitgevoerd en welke objecten zijn beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="0fa96-106">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
> <ul><li><span data-ttu-id="0fa96-107">Logboekregistratie voor beheerderscontrole is standaard ingeschakeld en u deze niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="0fa96-107">Admin auditing logging is enabled by default, and you can't disable it.</span></span></li><li><span data-ttu-id="0fa96-108">Het beheercontrolelogboek registreert geen acties op basis van cmdlets die beginnen met de werkwoorden **Get,** **Search**of **Test**.</span><span class="sxs-lookup"><span data-stu-id="0fa96-108">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span></li><li><span data-ttu-id="0fa96-109">Controlelogboekvermeldingen worden 90 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="0fa96-109">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="0fa96-110">Wanneer een item ouder is dan 90 dagen, wordt het verwijderd</span><span class="sxs-lookup"><span data-stu-id="0fa96-110">When an entry is older than 90 days, it's deleted</span></span></li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0fa96-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="0fa96-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0fa96-112">Zie [Exchange-beheercentrum in het zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md)om het Exchange-beheercentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="0fa96-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="0fa96-113">Zie Verbinding maken met Exchange [Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)als u verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0fa96-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0fa96-114">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0fa96-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="0fa96-115">U hebt in het bijzonder de rol Controlelogboeken of Alleen-weergavecontrolelogboeken nodig, die standaard zijn toegewezen aan de rolgroepen ComplianceManagement, OrganizationManagement (globale beheerders) en SecurityAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0fa96-115">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="0fa96-116">Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de [EAC wijzigen de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0fa96-116">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="0fa96-117">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="0fa96-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="0fa96-118">Heb je problemen?</span><span class="sxs-lookup"><span data-stu-id="0fa96-118">Having problems?</span></span> <span data-ttu-id="0fa96-119">Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="0fa96-119">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="0fa96-120">De EAC gebruiken om het controlelogboek van de beheerder weer te geven</span><span class="sxs-lookup"><span data-stu-id="0fa96-120">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="0fa96-121">Ga in de EAC naar **Compliance management** \> **Auditing**en kies **Vervolgens het rapport Beheercontrole uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="0fa96-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="0fa96-122">Kies in de pagina **Zoeken naar wijzigingen in beheerdersrolgroepen** die wordt geopend een **begindatum** en **einddatum** (het standaardbereik is de afgelopen twee weken) en kies **Vervolgens Zoeken**.</span><span class="sxs-lookup"><span data-stu-id="0fa96-122">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="0fa96-123">Alle configuratiewijzigingen die tijdens de opgegeven periode zijn aangebracht, worden weergegeven en kunnen worden gesorteerd met behulp van de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="0fa96-123">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="0fa96-124">**Datum:** de datum en tijd waarop de configuratiewijziging is aangebracht.</span><span class="sxs-lookup"><span data-stu-id="0fa96-124">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="0fa96-125">De datum en tijd worden opgeslagen in de indeling Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="0fa96-125">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="0fa96-126">**Cmdlet**: De naam van de cmdlet die werd gebruikt om de configuratie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0fa96-126">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="0fa96-127">**Gebruiker:** de naam van het gebruikersaccount van de gebruiker die de configuratie heeft gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="0fa96-127">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="0fa96-128">Op meerdere pagina's worden maximaal 5000 vermeldingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0fa96-128">Up to 5000 entries will be displayed on multiple pages.</span></span> <span data-ttu-id="0fa96-129">Geef een kleiner datumbereik op als u uw resultaten wilt beperken.</span><span class="sxs-lookup"><span data-stu-id="0fa96-129">Specify a smaller date range if you need to narrow your results.</span></span> <span data-ttu-id="0fa96-130">Als u een afzonderlijk zoekresultaat selecteert, wordt de volgende aanvullende informatie weergegeven in het detailvenster:</span><span class="sxs-lookup"><span data-stu-id="0fa96-130">If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="0fa96-131">**Object gewijzigd**: het object dat is gewijzigd door de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0fa96-131">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="0fa96-132">**Parameters (parameter:waarde):** de cmdletparameters die zijn gebruikt en elke waarde die met de parameter is opgegeven.</span><span class="sxs-lookup"><span data-stu-id="0fa96-132">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="0fa96-133">Als u een specifieke controlelogboekvermelding wilt afdrukken, kiest u de knop **Afdrukken** in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="0fa96-133">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="0fa96-134">Gebruik standalone EOP PowerShell om het beheercontrolelogboek weer te geven</span><span class="sxs-lookup"><span data-stu-id="0fa96-134">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="0fa96-135">U standalone EOP PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen die voldoen aan de criteria die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="0fa96-135">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="0fa96-136">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0fa96-136">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="0fa96-137">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="0fa96-137">**Notes**:</span></span>

- <span data-ttu-id="0fa96-138">U de parameter _Parameters_ alleen gebruiken samen met de parameter _Cmdlets._</span><span class="sxs-lookup"><span data-stu-id="0fa96-138">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="0fa96-139">De parameter _ObjectIds filtert_ de resultaten door het object dat is gewijzigd door de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0fa96-139">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="0fa96-140">Een geldige waarde is afhankelijk van hoe het object wordt weergegeven in het controlelogboek.</span><span class="sxs-lookup"><span data-stu-id="0fa96-140">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="0fa96-141">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="0fa96-141">For example:</span></span>

  - <span data-ttu-id="0fa96-142">Name</span><span class="sxs-lookup"><span data-stu-id="0fa96-142">Name</span></span>
  - <span data-ttu-id="0fa96-143">Canonieke voornaam (bijvoorbeeld contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="0fa96-143">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="0fa96-144">U zult waarschijnlijk andere filterparameters op deze cmdlet moeten gebruiken om de resultaten te beperken en de typen objecten te identificeren waarin u geïnteresseerd bent.</span><span class="sxs-lookup"><span data-stu-id="0fa96-144">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="0fa96-145">De parameter _UserIds filtert_ de resultaten door de gebruiker die de wijziging heeft aangebracht (die de cmdlet heeft uitgevoerd).</span><span class="sxs-lookup"><span data-stu-id="0fa96-145">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="0fa96-146">Als u voor de parameters _StartDate_ en _EndDate_ een datum-/tijdwaarde opgeeft zonder tijdzone, is de waarde in Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="0fa96-146">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="0fa96-147">Als u een datum-tijdwaarde voor deze parameter wilt opgeven, gebruikt u een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="0fa96-147">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="0fa96-148">Geef de datum/tijdwaarde op in UTC: '2016-05-06 14:30:00z'.</span><span class="sxs-lookup"><span data-stu-id="0fa96-148">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="0fa96-149">Geef de datum/tijdwaarde op als een formule die de datum/tijd in uw lokale tijdzone omzet in UTC: bijvoorbeeld `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` .</span><span class="sxs-lookup"><span data-stu-id="0fa96-149">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="0fa96-150">Zie [Datum op de dag komen](https://go.microsoft.com/fwlink/p/?LinkID=113313)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0fa96-150">For more information, see [Get-Date](https://go.microsoft.com/fwlink/p/?LinkID=113313).</span></span>

- <span data-ttu-id="0fa96-151">De cmdlet retourneert standaard maximaal 1.000 logboekvermeldingen.</span><span class="sxs-lookup"><span data-stu-id="0fa96-151">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="0fa96-152">Gebruik de parameter _ResultSize_ om maximaal 250.000 logboekvermeldingen op te geven.</span><span class="sxs-lookup"><span data-stu-id="0fa96-152">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="0fa96-153">Of gebruik de waarde `Unlimited` om alle items terug te sturen.</span><span class="sxs-lookup"><span data-stu-id="0fa96-153">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="0fa96-154">In dit voorbeeld wordt gezocht naar alle controlelogboekvermeldingen met de volgende criteria:</span><span class="sxs-lookup"><span data-stu-id="0fa96-154">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="0fa96-155">**Startdatum**: 4 augustus 2019</span><span class="sxs-lookup"><span data-stu-id="0fa96-155">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="0fa96-156">**Einddatum**: 3 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="0fa96-156">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="0fa96-157">**Cmdlets**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="0fa96-157">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="0fa96-158">Zie [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="0fa96-158">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="0fa96-159">Details van controlelogboekvermeldingen weergeven</span><span class="sxs-lookup"><span data-stu-id="0fa96-159">View details of audit log entries</span></span>

<span data-ttu-id="0fa96-160">De cmdlet **Search-AdminAuditLog** retourneert de velden die later in dit onderwerp in de [inhoudssectie van het logboek controleren](#audit-log-contents) worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="0fa96-160">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this topic.</span></span> <span data-ttu-id="0fa96-161">Van de velden die door de cmdlet worden geretourneerd, bevatten twee **velden, CmdletParameters** en **ModifiedProperties,** aanvullende informatie die niet standaard wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="0fa96-161">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="0fa96-162">Als u de inhoud van de velden **CmdletParameters** en **ModifiedProperties wilt** weergeven, gebruikt u de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="0fa96-162">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="0fa96-163">Bepaal de criteria die u wilt zoeken, voer de cmdlet **Search-AdminAuditLog** uit en bewaar de resultaten in een variabele met de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="0fa96-163">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="0fa96-164">Elke controlelogboekvermelding wordt opgeslagen als een arrayelement in de variabele `$Results` .</span><span class="sxs-lookup"><span data-stu-id="0fa96-164">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="0fa96-165">U een arrayelement selecteren door de arrayelementindex op te geven.</span><span class="sxs-lookup"><span data-stu-id="0fa96-165">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="0fa96-166">Arrayelementindexen beginnen bij nul (0) voor het eerste matrixelement.</span><span class="sxs-lookup"><span data-stu-id="0fa96-166">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="0fa96-167">Als u bijvoorbeeld het 5e arrayelement wilt ophalen, dat een index van 4 heeft, gebruikt u de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="0fa96-167">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="0fa96-168">Met de vorige opdracht wordt de logboekinvoer geretourneerd die is opgeslagen in arrayelement 4.</span><span class="sxs-lookup"><span data-stu-id="0fa96-168">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="0fa96-169">Als u de inhoud van de velden **CmdletParameters** en **ModifiedProperties** voor deze logboekvermelding wilt bekijken, gebruikt u de volgende opdrachten.</span><span class="sxs-lookup"><span data-stu-id="0fa96-169">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="0fa96-170">Als u de inhoud van de velden **CmdletParameters** of **ModifiedParameters** in een andere logboekvermelding wilt weergeven, wijzigt u de arrayelementindex.</span><span class="sxs-lookup"><span data-stu-id="0fa96-170">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="0fa96-171">Inhoud van controlelogboeken</span><span class="sxs-lookup"><span data-stu-id="0fa96-171">Audit log contents</span></span>

<span data-ttu-id="0fa96-172">Elke controlelogvermelding bevat de informatie die in de volgende tabel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="0fa96-172">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="0fa96-173">Het controlelogboek bevat een of meer controlelogboekvermeldingen.</span><span class="sxs-lookup"><span data-stu-id="0fa96-173">The audit log contains one or more audit log entries.</span></span>

|||
|---|---|
|<span data-ttu-id="0fa96-174">**Veld**</span><span class="sxs-lookup"><span data-stu-id="0fa96-174">**Field**</span></span>|<span data-ttu-id="0fa96-175">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="0fa96-175">**Description**</span></span>|
|`RunspaceId`|<span data-ttu-id="0fa96-176">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="0fa96-176">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="0fa96-177">Dit veld bevat het object dat is gewijzigd door de cmdlet die in het veld is `CmdletName` opgegeven.</span><span class="sxs-lookup"><span data-stu-id="0fa96-177">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="0fa96-178">Dit veld bevat de naam van de cmdlet die door de gebruiker in het veld is `Caller` uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0fa96-178">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="0fa96-179">Dit veld bevat de parameters die zijn opgegeven toen de cmdlet in het `CmdletName` veld werd uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0fa96-179">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="0fa96-180">Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, is de waarde die is opgegeven met de parameter, indien aanwezig.</span><span class="sxs-lookup"><span data-stu-id="0fa96-180">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="0fa96-181">Dit veld bevat de eigenschappen die zijn gewijzigd op het object in het `ObjectModified` veld.</span><span class="sxs-lookup"><span data-stu-id="0fa96-181">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="0fa96-182">Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, zijn de oude waarde van de eigenschap en de nieuwe waarde die is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="0fa96-182">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="0fa96-183">Dit veld bevat het gebruikersaccount van de gebruiker die de cmdlet in het veld heeft `CmdletName` uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0fa96-183">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="0fa96-184">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="0fa96-184">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="0fa96-185">Dit veld geeft aan of de cmdlet in het `CmdletName` veld is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0fa96-185">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="0fa96-186">De waarde is of `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="0fa96-186">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="0fa96-187">Dit veld bevat het foutbericht dat is gegenereerd als de cmdlet in het `CmdletName` veld niet is voltooid.</span><span class="sxs-lookup"><span data-stu-id="0fa96-187">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="0fa96-188">Dit veld bevat de datum en tijd waarop de cmdlet in het `CmdletName` veld is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0fa96-188">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="0fa96-189">De datum en tijd worden opgeslagen in de indeling Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="0fa96-189">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="0fa96-190">Dit veld geeft de server aan waarop de in het veld opgegeven cmdlet `CmdletName` is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0fa96-190">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="0fa96-191">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="0fa96-191">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="0fa96-192">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="0fa96-192">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="0fa96-193">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="0fa96-193">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="0fa96-194">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="0fa96-194">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="0fa96-195">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="0fa96-195">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="0fa96-196">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="0fa96-196">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="0fa96-197">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="0fa96-197">This field is used internally by EOP.</span></span>|
|
