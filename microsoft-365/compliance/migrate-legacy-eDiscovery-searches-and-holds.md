---
title: Oudere eDiscovery-zoekopdrachten migreren naar het Microsoft 365 compliancecentrum
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: aaae5e6bddc48f29cc0766fe26a1976672c7dd49
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310793"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="0b56b-102">Oudere eDiscovery-zoekopdrachten migreren naar het Microsoft 365 compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="0b56b-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="0b56b-103">Het Microsoft 365 compliancecentrum biedt een verbeterde ervaring voor eDiscovery-gebruik, waaronder: hogere betrouwbaarheid, betere prestaties en veel functies die zijn afgestemd op eDiscovery-werkstromen, waaronder zaken om uw inhoud per zaak te ordenen, sets controleren om inhoud en analyses te bekijken, om gegevens te verwijderen voor controle, zoals near-duplicate groepering, e-mailthreading, themaanalyse en voorspellende codering.</span><span class="sxs-lookup"><span data-stu-id="0b56b-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance, and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="0b56b-104">Om klanten te helpen profiteren van de nieuwe en verbeterde functionaliteit, bevat dit artikel basishulp voor het migreren van In-Place eDiscovery-zoekopdrachten en -bezit van het Exchange-beheercentrum naar het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="0b56b-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="0b56b-105">Omdat er veel verschillende scenario's zijn, bevat dit artikel algemene richtlijnen voor het overstappen van zoekopdrachten en houdt het vast aan een kern-eDiscovery-zaak in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="0b56b-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0b56b-106">Het gebruik van eDiscovery-zaken is niet altijd vereist, maar ze voegen een extra beveiligingslaag toe door u machtigingen toe te wijzen om te bepalen wie toegang heeft tot de eDiscovery-zaken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0b56b-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0b56b-107">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="0b56b-107">Before you begin</span></span>

- <span data-ttu-id="0b56b-108">U moet lid zijn van de rollengroep eDiscovery Manager in het beveiligings- & compliancecentrum om de PowerShell-opdrachten uit te voeren die in dit artikel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="0b56b-108">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="0b56b-109">U moet ook lid zijn van de rollengroep Discovery Management in het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0b56b-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="0b56b-110">Dit artikel bevat richtlijnen voor het maken van een eDiscovery-wacht.</span><span class="sxs-lookup"><span data-stu-id="0b56b-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="0b56b-111">Het holdbeleid wordt toegepast op postvakken via een asynchron proces.</span><span class="sxs-lookup"><span data-stu-id="0b56b-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="0b56b-112">Wanneer u een eDiscovery-wachtplaats maakt, moet u zowel een CaseHoldPolicy als CaseHoldRule maken, anders wordt de wacht niet gemaakt en worden inhoudslocaties niet in de wacht geplaatst.</span><span class="sxs-lookup"><span data-stu-id="0b56b-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a><span data-ttu-id="0b56b-113">Stap 1: Verbinding maken Exchange Online PowerShell en & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b56b-113">Step 1: Connect to Exchange Online PowerShell and Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="0b56b-114">De eerste stap is om verbinding te maken met Exchange Online PowerShell en & Compliance Center PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b56b-114">The first step is to connect to Exchange Online PowerShell and Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="0b56b-115">U kunt het volgende script kopiëren, plakken in een PowerShell-venster en vervolgens uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0b56b-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="0b56b-116">U wordt gevraagd om referenties voor de organisatie met wie u verbinding wilt maken.</span><span class="sxs-lookup"><span data-stu-id="0b56b-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="0b56b-117">U moet de opdrachten uitvoeren in de volgende stappen in deze PowerShell-sessie.</span><span class="sxs-lookup"><span data-stu-id="0b56b-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="0b56b-118">Stap 2: Een lijst met In-Place eDiscovery-zoekopdrachten met behulp van Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="0b56b-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="0b56b-119">Nadat u zich hebt geverifieerd, kunt u een lijst met In-Place eDiscovery-zoekopdrachten krijgen door de **cmdlet Get-MailboxSearch** uit te lopen.</span><span class="sxs-lookup"><span data-stu-id="0b56b-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="0b56b-120">Kopieer en plak de volgende opdracht in PowerShell en voer deze uit.</span><span class="sxs-lookup"><span data-stu-id="0b56b-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="0b56b-121">Er wordt een lijst met zoekopdrachten weergegeven met hun namen en de status van alle In-Place in.</span><span class="sxs-lookup"><span data-stu-id="0b56b-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="0b56b-122">De uitvoer van de cmdlet lijkt op het volgende:</span><span class="sxs-lookup"><span data-stu-id="0b56b-122">The cmdlet output will be similar to the following:</span></span>

![Voorbeeld van PowerShell Get-MailboxSearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="0b56b-124">Stap 3: Informatie over de In-Place eDiscovery-zoekopdrachten en -In-Place houdt die u wilt migreren</span><span class="sxs-lookup"><span data-stu-id="0b56b-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="0b56b-125">Opnieuw gebruikt u de **cmdlet Get-MailboxSearch,** maar deze keer om de eigenschappen van de zoekopdracht te krijgen.</span><span class="sxs-lookup"><span data-stu-id="0b56b-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="0b56b-126">U kunt deze eigenschappen opslaan in een variabele voor later gebruik.</span><span class="sxs-lookup"><span data-stu-id="0b56b-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="0b56b-127">In het volgende voorbeeld worden de resultaten van de **cmdlet Get-MailboxSearch** opgeslagen in een variabele en worden vervolgens de eigenschappen van de zoekopdracht weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0b56b-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="0b56b-128">De uitvoer van deze twee opdrachten is vergelijkbaar met de volgende:</span><span class="sxs-lookup"><span data-stu-id="0b56b-128">The output of these two commands will be similar to the following:</span></span>

![Voorbeeld van PowerShell-uitvoer van het gebruik Get-MailboxSearch voor een afzonderlijke zoekopdracht](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="0b56b-130">De duur van de In-Place in dit voorbeeld is onbepaalde tijd *(ItemHoldPeriod: Onbeperkt).*</span><span class="sxs-lookup"><span data-stu-id="0b56b-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="0b56b-131">Dit is typisch voor scenario's voor eDiscovery en juridisch onderzoek.</span><span class="sxs-lookup"><span data-stu-id="0b56b-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="0b56b-132">Als de duur van de bewaring een andere waarde heeft dan voor onbepaalde tijd, is de reden waarschijnlijk dat de bewaring wordt gebruikt om inhoud te behouden in een bewaarscenario.</span><span class="sxs-lookup"><span data-stu-id="0b56b-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="0b56b-133">In plaats van de eDiscovery-cmdlets in Security & Compliance Center PowerShell te gebruiken voor bewaarscenario's, raden we u aan om [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) en [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) te gebruiken om inhoud te behouden.</span><span class="sxs-lookup"><span data-stu-id="0b56b-133">Instead of using the eDiscovery cmdlets in Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="0b56b-134">Het resultaat van het gebruik van deze cmdlets is vergelijkbaar met het gebruik van **New-CaseHoldPolicy** en **New-CaseHoldRule,** maar u kunt een bewaarperiode en een bewaaractie opgeven, zoals het verwijderen van inhoud nadat de bewaarperiode is verlopen.</span><span class="sxs-lookup"><span data-stu-id="0b56b-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="0b56b-135">Als u de bewaar cmdlets gebruikt, hoeft u de bewaarperioden niet te koppelen aan een eDiscovery-zaak.</span><span class="sxs-lookup"><span data-stu-id="0b56b-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="0b56b-136">Stap 4: Een zaak maken in het Microsoft 365 compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="0b56b-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="0b56b-137">Als u een eDiscovery-greep wilt maken, moet u een eDiscovery-zaak maken om de wacht te koppelen aan.</span><span class="sxs-lookup"><span data-stu-id="0b56b-137">To create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="0b56b-138">In het volgende voorbeeld wordt een eDiscovery-zaak gemaakt met een naam van uw keuze.</span><span class="sxs-lookup"><span data-stu-id="0b56b-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="0b56b-139">We slaan de eigenschappen van de nieuwe zaak op in een variabele voor later gebruik.</span><span class="sxs-lookup"><span data-stu-id="0b56b-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="0b56b-140">U kunt deze eigenschappen bekijken door de opdracht `$case | FL` uit te voeren nadat u de zaak hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0b56b-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Voorbeeld van het uitvoeren van de New-ComplianceCase opdracht](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="0b56b-142">Stap 5: De eDiscovery-hold maken</span><span class="sxs-lookup"><span data-stu-id="0b56b-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="0b56b-143">Nadat de zaak is gemaakt, kunt u de wacht houden maken en deze koppelen aan de zaak die u in de vorige stap hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0b56b-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="0b56b-144">Het is belangrijk om te onthouden dat u zowel een case hold-beleid als een case hold-regel moet maken.</span><span class="sxs-lookup"><span data-stu-id="0b56b-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="0b56b-145">Als de regel voor het in de wacht houden van een zaak niet is gemaakt nadat u het beleid voor het houden van een zaak hebt gemaakt, wordt de eDiscovery-wachtplaats niet gemaakt en wordt inhoud niet in de wacht gezet.</span><span class="sxs-lookup"><span data-stu-id="0b56b-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="0b56b-146">Voer de volgende opdrachten uit om de eDiscovery-wacht die u wilt migreren opnieuw te maken.</span><span class="sxs-lookup"><span data-stu-id="0b56b-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="0b56b-147">In deze voorbeelden worden de eigenschappen gebruikt In-Place Van stap 3 houden die u wilt migreren.</span><span class="sxs-lookup"><span data-stu-id="0b56b-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span> <span data-ttu-id="0b56b-148">Met de eerste opdracht wordt een nieuw beleid voor het vasthouden van een zaak gemaakt en worden de eigenschappen op een variabele op slaat.</span><span class="sxs-lookup"><span data-stu-id="0b56b-148">The first command creates a new case hold policy and saves the properties to a variable.</span></span> <span data-ttu-id="0b56b-149">Met de tweede opdracht wordt de bijbehorende regel voor de case hold gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0b56b-149">The second command creates the corresponding case hold rule.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Voorbeeld van het gebruik van NewCaseHoldPolicy en NewCaseHoldRule-cmdlets](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="0b56b-151">Stap 6: De eDiscovery-wacht houden controleren</span><span class="sxs-lookup"><span data-stu-id="0b56b-151">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="0b56b-152">Als u wilt controleren of er geen problemen zijn bij het maken van de wachtpositie, is het goed om te controleren of de distributiestatus van de wachtpositie is geslaagd.</span><span class="sxs-lookup"><span data-stu-id="0b56b-152">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="0b56b-153">Distributie betekent dat de hold is toegepast op alle inhoudslocaties die zijn opgegeven in de *parameter ExchangeLocation* in de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="0b56b-153">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="0b56b-154">Hiervoor kunt u de **cmdlet Get-CaseHoldPolicy** uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0b56b-154">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="0b56b-155">Omdat de eigenschappen die zijn *opgeslagen* in de $policy-variabele die u in de vorige stap hebt gemaakt, niet automatisch worden bijgewerkt in de variabele, moet u de cmdlet opnieuw gebruiken om te controleren of de verdeling is gelukt.</span><span class="sxs-lookup"><span data-stu-id="0b56b-155">Because the properties saved to the *$policy* variable that you created in the previous step aren't automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="0b56b-156">Het kan 5 minuten tot 24 uur duren voordat het beleid voor het vasthouden van een zaak is gedistribueerd.</span><span class="sxs-lookup"><span data-stu-id="0b56b-156">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="0b56b-157">Voer de volgende opdracht uit om te controleren of de eDiscovery-hold is gedistribueerd.</span><span class="sxs-lookup"><span data-stu-id="0b56b-157">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="0b56b-158">De waarde van **Succes** voor de eigenschap *Distributiestatus* geeft aan dat de hold is geplaatst op de inhoudslocaties.</span><span class="sxs-lookup"><span data-stu-id="0b56b-158">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="0b56b-159">Als de verdeling nog niet is voltooid, wordt een waarde van **In** behandeling weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0b56b-159">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![PowerShell Get-CaseHoldPolicy voorbeeld](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="0b56b-161">Stap 7: De zoekopdracht maken</span><span class="sxs-lookup"><span data-stu-id="0b56b-161">Step 7: Create the search</span></span>

<span data-ttu-id="0b56b-162">De laatste stap is het opnieuw maken van de zoekopdracht die u hebt geïdentificeerd in stap 3 en deze te koppelen aan de zaak.</span><span class="sxs-lookup"><span data-stu-id="0b56b-162">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="0b56b-163">Nadat u de zoekopdracht hebt gemaakt, kunt u deze uitvoeren met de **cmdlet Start-ComplianceSearch** of op een later tijdstip uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0b56b-163">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell New-ComplianceSearch voorbeeld](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="0b56b-165">Stap 8: De zaak controleren, vasthouden en zoeken in het Microsoft 365 compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="0b56b-165">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="0b56b-166">Als u wilt controleren of alles correct is ingesteld, gaat u naar het Microsoft 365 compliancecentrum bij en klikt u op [https://compliance.microsoft.com](https://compliance.microsoft.com) **eDiscovery > Core.**</span><span class="sxs-lookup"><span data-stu-id="0b56b-166">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![Microsoft 365 Compliancecentrum eDiscovery](../media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="0b56b-168">De zaak die u in stap 3 hebt gemaakt, wordt weergegeven op de **pagina Core eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="0b56b-168">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="0b56b-169">Open de zaak en let vervolgens op de wacht die u hebt gemaakt in stap 4 in die wordt weergegeven op het **tabblad** Wacht. U kunt de wacht houden selecteren om details te zien op de flyoutpagina, inclusief het aantal postvakken waar de wachtpositie op is toegepast en de distributiestatus.</span><span class="sxs-lookup"><span data-stu-id="0b56b-169">Open the case and then notice the hold that you created in Step 4 in listed on the **Hold** tab. You can select the hold to see details on the flyout page, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![eDiscovery houdt in het Microsoft 365 compliancecentrum](../media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="0b56b-171">De zoekopdracht die u in stap 7 hebt gemaakt, wordt weergegeven op **het tabblad** Zoekopdrachten van de zaak.</span><span class="sxs-lookup"><span data-stu-id="0b56b-171">The search that you created in Step 7 is listed on the **Searches** tab of the case.</span></span>

![eDiscovery case search in the Microsoft 365 compliance center](../media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="0b56b-173">Als u een In-Place eDiscovery-zoekopdracht migreert, maar deze niet koppelt aan een eDiscovery-zaak, wordt deze weergegeven op de pagina Inhoud zoeken in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="0b56b-173">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="0b56b-174">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="0b56b-174">More information</span></span>

- <span data-ttu-id="0b56b-175">Zie voor meer informatie In-Place eDiscovery & In het Exchange beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="0b56b-175">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="0b56b-176">In-place eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0b56b-176">In-Place eDiscovery</span></span>](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="0b56b-177">In-Place Hold and Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="0b56b-177">In-Place Hold and Litigation Hold</span></span>](/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="0b56b-178">Zie voor meer informatie over de PowerShell-cmdlets die in het artikel worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="0b56b-178">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="0b56b-179">Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="0b56b-179">Get-MailboxSearch</span></span>](/powershell/module/exchange/get-mailboxsearch)
  
  - [<span data-ttu-id="0b56b-180">New-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="0b56b-180">New-ComplianceCase</span></span>](/powershell/module/exchange/new-compliancecase)

  - [<span data-ttu-id="0b56b-181">New-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="0b56b-181">New-CaseHoldPolicy</span></span>](/powershell/module/exchange/new-caseholdpolicy)
  
  - [<span data-ttu-id="0b56b-182">New-CaseHoldRule</span><span class="sxs-lookup"><span data-stu-id="0b56b-182">New-CaseHoldRule</span></span>](/powershell/module/exchange/new-caseholdrule)

  - [<span data-ttu-id="0b56b-183">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="0b56b-183">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
  
  - [<span data-ttu-id="0b56b-184">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="0b56b-184">New-ComplianceSearch</span></span>](/powershell/module/exchange/new-compliancesearch)

  - [<span data-ttu-id="0b56b-185">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="0b56b-185">Start-ComplianceSearch</span></span>](/powershell/module/exchange/start-compliancesearch)

- <span data-ttu-id="0b56b-186">Zie Overzicht van het Microsoft 365 compliancecentrum voor meer informatie over [Microsoft 365 compliancecentrum.](microsoft-365-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="0b56b-186">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>