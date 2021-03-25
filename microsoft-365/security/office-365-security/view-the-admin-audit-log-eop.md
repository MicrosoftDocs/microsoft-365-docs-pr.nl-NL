---
title: Het auditlogboek van de beheerder bekijken in standalone EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Beheerders kunnen leren hoe ze het auditlogboek van de beheerder kunnen bekijken en doorzoeken in de zelfstandige Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed1d1eb121c06e6f5727e8782ba1d8bc8d23a99
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203984"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="eee66-103">Het auditlogboek van de beheerder bekijken in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="eee66-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="eee66-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="eee66-104">**Applies to**</span></span>
- [<span data-ttu-id="eee66-105">Zelfstandige Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eee66-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="eee66-106">In zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken kunt u het Exchange-beheercentrum (EAC) of zelfstandige EOP PowerShell gebruiken om items in het beheerdersauditlogboek te zoeken en weer te geven.</span><span class="sxs-lookup"><span data-stu-id="eee66-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="eee66-107">Het auditlogboek van de beheerder registreert specifieke acties, op basis van zelfstandige EOP PowerShell-cmdlets, uitgevoerd door beheerders en gebruikers aan wie beheerdersbevoegdheden zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="eee66-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="eee66-108">Items in het auditlogboek van de beheerder geven u informatie over welke cmdlet is uitgevoerd, welke parameters zijn gebruikt, wie de cmdlet heeft uitgevoerd en welke objecten zijn beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="eee66-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="eee66-109">Logboekregistratie voor beheerdersaudits is standaard ingeschakeld en u kunt deze niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="eee66-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="eee66-110">In het auditlogboek van de beheerder worden geen acties opgeslagen op basis van cmdlets die beginnen met de werkwoorden **Get,** **Search** of **Test.**</span><span class="sxs-lookup"><span data-stu-id="eee66-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="eee66-111">Controlelogboekgegevens worden 90 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="eee66-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="eee66-112">Wanneer een item ouder is dan 90 dagen, wordt het verwijderd</span><span class="sxs-lookup"><span data-stu-id="eee66-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eee66-113">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="eee66-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eee66-114">Zie Exchange-beheercentrum in zelfstandige EOP om het Exchange-beheercentrum [te openen.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="eee66-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="eee66-115">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eee66-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="eee66-116">U moet machtigingen krijgen toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="eee66-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="eee66-117">U hebt met name de rol  **Auditlogboeken** of **Alleen-weergeven auditlogboeken** nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer, **Compliancebeheer** en Beveiligingsbeheerder. </span><span class="sxs-lookup"><span data-stu-id="eee66-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="eee66-118">Zie Machtigingen in zelfstandige [EOP](feature-permissions-in-eop.md) en Gebruik de EAC om de lijst met [leden in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="eee66-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="eee66-119">Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in [dit artikel.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="eee66-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="eee66-120">Hebt u problemen?</span><span class="sxs-lookup"><span data-stu-id="eee66-120">Having problems?</span></span> <span data-ttu-id="eee66-121">Vraag om hulp in het [Exchange Online Protection-forum.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="eee66-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="eee66-122">Het EAC gebruiken om het auditlogboek van de beheerder te bekijken</span><span class="sxs-lookup"><span data-stu-id="eee66-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="eee66-123">Ga in het EAC naar **Compliance management** \> **Auditing** en kies **vervolgens Het auditlogboekrapport voor** beheerders uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="eee66-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="eee66-124">Kies **op de** pagina Zoeken naar wijzigingen in beheerdersrolgroepen die wordt geopend een **Begindatum** en Einddatum **(het** standaardbereik is de afgelopen twee weken) en kies **vervolgens Zoeken**.</span><span class="sxs-lookup"><span data-stu-id="eee66-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="eee66-125">Alle configuratiewijzigingen die tijdens de opgegeven periode zijn aangebracht, worden weergegeven en kunnen worden gesorteerd aan de hand van de volgende gegevens:</span><span class="sxs-lookup"><span data-stu-id="eee66-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="eee66-126">**Datum:** De datum en tijd waarop de configuratiewijziging is aangebracht.</span><span class="sxs-lookup"><span data-stu-id="eee66-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="eee66-127">De datum en tijd worden opgeslagen in de UTC-indeling (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="eee66-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="eee66-128">**Cmdlet:** de naam van de cmdlet die is gebruikt om de configuratie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="eee66-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="eee66-129">**Gebruiker:** De naam van het gebruikersaccount van de gebruiker die de configuratie heeft gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="eee66-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="eee66-130">Er worden maximaal 5000 items weergegeven op meerdere pagina's.</span><span class="sxs-lookup"><span data-stu-id="eee66-130">Up to 5000 entries will be displayed on multiple pages.</span></span> <span data-ttu-id="eee66-131">Geef een kleiner datumbereik op als u de resultaten wilt beperken.</span><span class="sxs-lookup"><span data-stu-id="eee66-131">Specify a smaller date range if you need to narrow your results.</span></span> <span data-ttu-id="eee66-132">Als u een afzonderlijk zoekresultaat selecteert, worden de volgende aanvullende gegevens weergegeven in het detailvenster:</span><span class="sxs-lookup"><span data-stu-id="eee66-132">If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="eee66-133">**Object gewijzigd:** het object dat is gewijzigd door de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eee66-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="eee66-134">**Parameters (parameter:waarde)**: de gebruikte cmdletparameters en elke waarde die met de parameter is opgegeven.</span><span class="sxs-lookup"><span data-stu-id="eee66-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="eee66-135">Als u een specifiek auditlogboek wilt afdrukken, kiest u de knop **Afdrukken** in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="eee66-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="eee66-136">Zelfstandige EOP PowerShell gebruiken om het auditlogboek van de beheerder weer te geven</span><span class="sxs-lookup"><span data-stu-id="eee66-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="eee66-137">U kunt zelfstandige EOP PowerShell gebruiken om te zoeken naar controlelogboekgegevens die voldoen aan de criteria die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="eee66-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="eee66-138">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="eee66-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="eee66-139">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="eee66-139">**Notes**:</span></span>

- <span data-ttu-id="eee66-140">U kunt de parameter _Parameters alleen_ samen met de _parameter Cmdlets_ gebruiken.</span><span class="sxs-lookup"><span data-stu-id="eee66-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="eee66-141">Met _de parameter ObjectIds_ worden de resultaten gefilterd op het object dat door de cmdlet is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="eee66-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="eee66-142">Een geldige waarde is afhankelijk van de manier waarop het object wordt weergegeven in het auditlogboek.</span><span class="sxs-lookup"><span data-stu-id="eee66-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="eee66-143">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="eee66-143">For example:</span></span>

  - <span data-ttu-id="eee66-144">Naam</span><span class="sxs-lookup"><span data-stu-id="eee66-144">Name</span></span>
  - <span data-ttu-id="eee66-145">Canonieke naam (bijvoorbeeld contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="eee66-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="eee66-146">U moet waarschijnlijk andere filterparameters op deze cmdlet gebruiken om de resultaten te beperken en de typen objecten te identificeren waarin u geïnteresseerd bent.</span><span class="sxs-lookup"><span data-stu-id="eee66-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="eee66-147">Met _de parameter UserIds_ worden de resultaten gefilterd door de gebruiker die de wijziging heeft aangebracht (die de cmdlet heeft gebruikt).</span><span class="sxs-lookup"><span data-stu-id="eee66-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="eee66-148">Als u voor  _de parameters Begindatum_ en Einddatum een datum-/tijdwaarde zonder tijdzone opgeeft, bevindt de waarde zich in Gecoördineerde universele tijd (UTC).</span><span class="sxs-lookup"><span data-stu-id="eee66-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="eee66-149">Als u een datum-/tijdwaarde voor deze parameter wilt opgeven, gebruikt u een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="eee66-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="eee66-150">Geef de datum-/tijdwaarde op in UTC: bijvoorbeeld '2016-05-06 14:30:00z'.</span><span class="sxs-lookup"><span data-stu-id="eee66-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="eee66-151">Geef de datum-/tijdwaarde op als een formule die de datum/tijd in uw lokale tijdzone converteert naar UTC: `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` Bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="eee66-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="eee66-152">Zie [Get-Date](/powershell/module/microsoft.powershell.utility/get-date)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eee66-152">For more information, see [Get-Date](/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="eee66-153">De cmdlet retourneert standaard maximaal 1.000 logboekgegevens.</span><span class="sxs-lookup"><span data-stu-id="eee66-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="eee66-154">Gebruik de _parameter ResultSize_ om maximaal 250.000 logboekgegevens op te geven.</span><span class="sxs-lookup"><span data-stu-id="eee66-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="eee66-155">Of gebruik de waarde om `Unlimited` alle items te retourneren.</span><span class="sxs-lookup"><span data-stu-id="eee66-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="eee66-156">In dit voorbeeld wordt een zoekopdracht uitgevoerd naar alle controlelogboekgegevens met de volgende criteria:</span><span class="sxs-lookup"><span data-stu-id="eee66-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="eee66-157">**Begindatum**: 4 augustus 2019</span><span class="sxs-lookup"><span data-stu-id="eee66-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="eee66-158">**Einddatum**: 3 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="eee66-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="eee66-159">**Cmdlets**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="eee66-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="eee66-160">Zie [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="eee66-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="eee66-161">Details van controlelogboekgegevens weergeven</span><span class="sxs-lookup"><span data-stu-id="eee66-161">View details of audit log entries</span></span>

<span data-ttu-id="eee66-162">De **cmdlet Search-AdminAuditLog** retourneert de velden die worden beschreven in de sectie [Auditlog-inhoud](#audit-log-contents) verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="eee66-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="eee66-163">Van de velden die door de cmdlet worden geretourneerd, bevatten twee velden, **CmdletParameters** en **ModifiedProperties,** aanvullende informatie die niet standaard wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="eee66-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="eee66-164">Als u de inhoud van de **velden CmdletParameters** en **ModifiedProperties** wilt weergeven, gebruikt u de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="eee66-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="eee66-165">Bepaal de criteria die u wilt zoeken, voer de cmdlet **Search-AdminAuditLog** uit en sla de resultaten op in een variabele met de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="eee66-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="eee66-166">Elke auditlogboekinvoer wordt opgeslagen als een matrixelement in de variabele `$Results` .</span><span class="sxs-lookup"><span data-stu-id="eee66-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="eee66-167">U kunt een matrixelement selecteren door de matrixelementindex op te geven.</span><span class="sxs-lookup"><span data-stu-id="eee66-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="eee66-168">Matrixelementindexen beginnen bij nul (0) voor het eerste matrixelement.</span><span class="sxs-lookup"><span data-stu-id="eee66-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="eee66-169">Als u bijvoorbeeld het 5e matrixelement wilt ophalen met een index van 4, gebruikt u de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="eee66-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="eee66-170">De vorige opdracht retourneert de logboekinvoer die is opgeslagen in matrixelement 4.</span><span class="sxs-lookup"><span data-stu-id="eee66-170">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="eee66-171">Als u de inhoud van de **velden CmdletParameters** en **ModifiedProperties** voor deze logboekinvoer wilt zien, gebruikt u de volgende opdrachten.</span><span class="sxs-lookup"><span data-stu-id="eee66-171">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="eee66-172">Als u de inhoud van de **velden CmdletParameters** of **ModifiedParameters** wilt weergeven in een andere logboekinvoer, wijzigt u de matrixelementindex.</span><span class="sxs-lookup"><span data-stu-id="eee66-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="eee66-173">Inhoud van auditlogboek</span><span class="sxs-lookup"><span data-stu-id="eee66-173">Audit log contents</span></span>

<span data-ttu-id="eee66-174">Elke auditlogboekinvoer bevat de informatie die in de volgende tabel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="eee66-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="eee66-175">Het auditlogboek bevat een of meer auditlogboekgegevens.</span><span class="sxs-lookup"><span data-stu-id="eee66-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="eee66-176">Veld</span><span class="sxs-lookup"><span data-stu-id="eee66-176">Field</span></span>|<span data-ttu-id="eee66-177">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="eee66-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="eee66-178">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="eee66-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="eee66-179">Dit veld bevat het object dat is gewijzigd door de cmdlet die in het veld is `CmdletName` opgegeven.</span><span class="sxs-lookup"><span data-stu-id="eee66-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="eee66-180">Dit veld bevat de naam van de cmdlet die door de gebruiker in het veld is `Caller` uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="eee66-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="eee66-181">Dit veld bevat de parameters die zijn opgegeven toen de cmdlet in het `CmdletName` veld werd uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="eee66-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="eee66-182">Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, is de waarde die is opgegeven met de parameter, indien aanwezig.</span><span class="sxs-lookup"><span data-stu-id="eee66-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="eee66-183">Dit veld bevat de eigenschappen die zijn gewijzigd voor het object in het `ObjectModified` veld.</span><span class="sxs-lookup"><span data-stu-id="eee66-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="eee66-184">Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, zijn de oude waarde van de eigenschap en de nieuwe waarde die is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="eee66-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="eee66-185">Dit veld bevat het gebruikersaccount van de gebruiker die de cmdlet in het veld `CmdletName` heeft gelopen.</span><span class="sxs-lookup"><span data-stu-id="eee66-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="eee66-186">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="eee66-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="eee66-187">In dit veld wordt aangegeven of de cmdlet in het `CmdletName` veld is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="eee66-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="eee66-188">De waarde is ofwel `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="eee66-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="eee66-189">Dit veld bevat het foutbericht dat is gegenereerd als de cmdlet in het `CmdletName` veld niet is voltooid.</span><span class="sxs-lookup"><span data-stu-id="eee66-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="eee66-190">Dit veld bevat de datum en tijd waarop de cmdlet in `CmdletName` het veld is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="eee66-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="eee66-191">De datum en tijd worden opgeslagen in de UTC-indeling (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="eee66-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="eee66-192">Dit veld geeft de server aan waarop de in het veld opgegeven cmdlet `CmdletName` is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="eee66-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="eee66-193">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="eee66-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="eee66-194">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="eee66-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="eee66-195">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="eee66-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="eee66-196">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="eee66-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="eee66-197">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="eee66-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="eee66-198">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="eee66-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="eee66-199">Dit veld wordt intern gebruikt door EOP.</span><span class="sxs-lookup"><span data-stu-id="eee66-199">This field is used internally by EOP.</span></span>|
|