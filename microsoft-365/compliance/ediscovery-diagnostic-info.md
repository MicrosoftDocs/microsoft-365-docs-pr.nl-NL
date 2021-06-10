---
title: Diagnostische gegevens voor eDiscovery verzamelen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het verzamelen van diagnostische gegevens voor eDiscovery voor een microsoft-ondersteuningscase.
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162158"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="a9d1d-103">Diagnostische gegevens voor eDiscovery verzamelen</span><span class="sxs-lookup"><span data-stu-id="a9d1d-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="a9d1d-104">Soms hebben technici van Microsoft Support specifieke informatie over uw probleem nodig wanneer u een ondersteuningscase opent met betrekking tot Core eDiscovery of Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="a9d1d-105">Dit artikel bevat richtlijnen voor het verzamelen van diagnostische gegevens om ondersteuningstechnici te helpen bij het onderzoeken en oplossen van problemen.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="a9d1d-106">Meestal hoeft u deze gegevens pas te verzamelen als u daarom wordt gevraagd door een microsoft-ondersteuningstechnicus.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9d1d-107">De uitvoer van de cmdlets en diagnostische informatie die in dit artikel wordt beschreven, kan gevoelige informatie bevatten over rechtszaken of interne onderzoeken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="a9d1d-108">Voordat u de onbewerkte diagnostische gegevens naar Microsoft Support verstuurt, moet u de informatie controleren en alle gevoelige informatie (zoals namen of andere informatie over partijen bij rechtszaken of onderzoeken) opnieuw uitvoeren door deze te vervangen door `XXXXXXX` .</span><span class="sxs-lookup"><span data-stu-id="a9d1d-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="a9d1d-109">Als u deze methode gebruikt, wordt ook aan de microsoft-ondersteuningstechnicus aangegeven dat de gegevens opnieuw zijn verwerkt.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="a9d1d-110">Diagnostische gegevens verzamelen voor Core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a9d1d-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="a9d1d-111">Het verzamelen van diagnostische gegevens voor Core eDiscovery is cmdletgebaseerd, dus u moet Beveiligings- & Compliancecentrum PowerShell gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="a9d1d-112">In de volgende PowerShell-voorbeelden worden cmdlets uitgevoerd en wordt de uitvoer opgeslagen in een opgegeven tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="a9d1d-113">In de meeste ondersteuningsgevallen hoeft u slechts één van deze opdrachten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="a9d1d-114">Als u de volgende cmdlets wilt uitvoeren, maakt u verbinding met [Security & Compliance Center PowerShell </span> ](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="a9d1d-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="a9d1d-115">Nadat u bent verbonden, voert u een of meer van de volgende opdrachten uit en moet u tijdelijke aanduidingen vervangen door de werkelijke objectnamen.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="a9d1d-116">Nadat u het gegenereerde tekstbestand hebt beoordeeld en gevoelige informatie opnieuw hebt gemaakt, stuurt u deze naar de Microsoft Support-engineer die aan uw zaak werkt.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="a9d1d-117">U kunt ook de opdrachten in deze sectie uitvoeren om diagnostische  gegevens te verzamelen voor de zoekopdrachten en exporten die worden weergegeven op de pagina Inhoud zoeken in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="a9d1d-118">Informatie over zoekopdrachten verzamelen</span><span class="sxs-lookup"><span data-stu-id="a9d1d-118">Collect information about searches</span></span>

<span data-ttu-id="a9d1d-119">Met de volgende opdracht worden gegevens verzameld die nuttig zijn bij het onderzoeken van problemen met een inhoudszoekactie of een zoekopdracht die is gekoppeld aan een Core eDiscovery-zaak.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="a9d1d-120">Gegevens verzamelen over zoekacties</span><span class="sxs-lookup"><span data-stu-id="a9d1d-120">Collect information about search actions</span></span>

<span data-ttu-id="a9d1d-121">Met de volgende opdracht worden gegevens verzameld om problemen te onderzoeken met het bekijken, exporteren of verwijderen van de resultaten van een inhoudszoekactie of een zoekopdracht die is gekoppeld aan een Core eDiscovery-zaak.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="a9d1d-122">U kunt de naam van de zoekactie identificeren door te klikken op een export die wordt weergegeven op het **tabblad** Export. Als u de namen van voorbeeld- en purgeacties wilt identificeren, kunt u de **cmdlet Get-ComplianceSearchAction** uitvoeren om een lijst met alle acties weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="a9d1d-123">De notatie voor de naam van de zoekactie wordt samengesteld op basis van het gebruik of de `_Preview` `_Export` naam van de `_Purge` bijbehorende zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="a9d1d-124">Gegevens verzamelen over eDiscovery-bezit</span><span class="sxs-lookup"><span data-stu-id="a9d1d-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="a9d1d-125">Wanneer een eDiscovery-hold die is gekoppeld aan een Core eDiscovery-zaak niet werkt zoals verwacht, voer dan de volgende opdracht uit om informatie te verzamelen over het beleid voor het in de wacht houden van gevallen en de bijbehorende case hold-regel voor de eDiscovery-hold.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="a9d1d-126">De *naam van het case hold-beleid* in de volgende opdracht is hetzelfde als de naam van de eDiscovery-hold.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="a9d1d-127">U kunt deze naam identificeren op de **tabbladen Holds** in de hoofd-eDiscovery-zaak.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="a9d1d-128">Alle case-informatie verzamelen</span><span class="sxs-lookup"><span data-stu-id="a9d1d-128">Collect all case information</span></span>

<span data-ttu-id="a9d1d-129">Soms is het niet duidelijk welke informatie vereist is door Microsoft Support om uw probleem te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="a9d1d-130">In deze situatie kunt u alle diagnostische gegevens verzamelen voor een kern-eDiscovery-zaak.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="a9d1d-131">De hoofdnaam van de hoofdzaak *eDiscovery* in de volgende opdracht is hetzelfde als de naam van een zaak die wordt weergegeven op de pagina Core **eDiscovery** in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="a9d1d-132">Diagnostische gegevens verzamelen voor Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a9d1d-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="a9d1d-133">Met **Instellingen** tabblad in een Advanced eDiscovery kunt u snel de diagnostische gegevens voor de zaak kopiëren.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="a9d1d-134">De diagnostische gegevens worden opgeslagen op het klembord, zodat u deze in een tekstbestand kunt plakken en naar Microsoft Ondersteuning kunt verzenden.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="a9d1d-135">Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op Alle > **eDiscovery > Geavanceerd.**</span><span class="sxs-lookup"><span data-stu-id="a9d1d-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="a9d1d-136">Selecteer een zaak en klik vervolgens op **Instellingen** tabblad.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="a9d1d-137">Klik **onder Case Information** op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="a9d1d-137">Under **Case Information**, click **Select**.</span></span>

4. <span data-ttu-id="a9d1d-138">Klik op de flyoutpagina op **Diagnostische gegevens kopiëren** om de informatie naar het klembord te kopiëren.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="a9d1d-139">Open een tekstbestand (in Kladblok) en plak de gegevens in het tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="a9d1d-140">Sla het tekstbestand op en noem het een naam `AeD Diagnostic Info YYYY.MM.DD` als `AeD Diagnostic Info 2020.11.03` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="a9d1d-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="a9d1d-141">Nadat u het bestand hebt beoordeeld en gevoelige informatie opnieuw hebt gemaakt, stuurt u deze naar de Microsoft Support-engineer die aan uw zaak werkt.</span><span class="sxs-lookup"><span data-stu-id="a9d1d-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>