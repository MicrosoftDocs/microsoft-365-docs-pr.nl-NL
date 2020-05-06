---
title: Een rapport over groepen met beheerdersrollen uitvoeren in EOP
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
description: In dit artikel leert u hoe u een rapport met een beheerdersrolgroep uitvoert in Exchange Online Protection (EOP).
ms.openlocfilehash: d3c4db8079a71ba054f323617d3ade65083a3a04
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034454"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="6041e-103">Een rapport over groepen met beheerdersrollen uitvoeren in EOP</span><span class="sxs-lookup"><span data-stu-id="6041e-103">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="6041e-104">Wanneer een beheerder leden toevoegt aan of verwijdert uit beheerdersrolgroepen, registreert Exchange Online Protection (EOP) elke gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="6041e-104">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="6041e-105">Wanneer u een rapport met een beheerdersrolgroep uitvoert in het Exchange-beheercentrum (EAC), worden items weergegeven als zoekresultaten en worden de betrokken rolgroepen opgenomen, wie het lidmaatschap van de rolgroep heeft gewijzigd en wanneer en welke lidmaatschapsupdates zijn uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="6041e-105">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="6041e-106">Gebruik dit rapport om wijzigingen in de beheerdersmachtigingen te controleren die zijn toegewezen aan gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6041e-106">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6041e-107">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="6041e-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6041e-108">Geschatte tijd om te voltooien: 2 minuten</span><span class="sxs-lookup"><span data-stu-id="6041e-108">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="6041e-109">Zie [Exchange-beheercentrum in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum wilt openen.</span><span class="sxs-lookup"><span data-stu-id="6041e-109">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="6041e-110">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="6041e-110">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="6041e-111">Zie het gedeelte 'Rapporten' van het onderwerp [Functiemachtigingen in het EOP-onderwerp](feature-permissions-in-eop.md) om te zien welke machtigingen u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="6041e-111">To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="6041e-112">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="6041e-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="6041e-113">Heb je problemen?</span><span class="sxs-lookup"><span data-stu-id="6041e-113">Having problems?</span></span> <span data-ttu-id="6041e-114">Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="6041e-114">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="6041e-115">De EAC gebruiken om een rapport van een beheerdersrolgroep uit te voeren</span><span class="sxs-lookup"><span data-stu-id="6041e-115">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="6041e-116">Voer het rapport van de groep beheerdersrollen uit om de wijzigingen in beheerrolgroepen in uw organisatie binnen een bepaald tijdsbestek te vinden.</span><span class="sxs-lookup"><span data-stu-id="6041e-116">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="6041e-117">Navigeer in de EAC naar \> **Compliancemanagementcontrole**en kies **Een rapport met een beheerdersrolgroep uitvoeren**. **Compliance management**</span><span class="sxs-lookup"><span data-stu-id="6041e-117">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="6041e-118">Kies de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="6041e-118">Choose the **Start date** and **End date**.</span></span> <span data-ttu-id="6041e-119">Standaard wordt in het rapport gezocht naar wijzigingen die in de afgelopen twee weken zijn aangebracht in beheerdersrolgroepen.</span><span class="sxs-lookup"><span data-stu-id="6041e-119">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="6041e-120">Als u de wijzigingen voor een specifieke rolgroep wilt weergeven, klikt u op **Rolgroepen selecteren**.</span><span class="sxs-lookup"><span data-stu-id="6041e-120">To view the changes for a specific role group, click **Select role groups**.</span></span> <span data-ttu-id="6041e-121">Selecteer de rolgroep (of groepen) in het volgende dialoogvenster en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="6041e-121">Select the role group (or groups) in the subsequent dialog box, and click **OK**.</span></span> <span data-ttu-id="6041e-122">U het veld ook leeg laten om alle gewijzigde rolgroepen te vinden.</span><span class="sxs-lookup"><span data-stu-id="6041e-122">You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="6041e-123">Klik **op Zoeken**.</span><span class="sxs-lookup"><span data-stu-id="6041e-123">Click **Search**.</span></span>

<span data-ttu-id="6041e-124">Als er wijzigingen worden gevonden aan de hand van de criteria die u hebt opgegeven, worden deze weergegeven in het resultatenvenster.</span><span class="sxs-lookup"><span data-stu-id="6041e-124">If any changes are found using the criteria you specified, they will appear in the results pane.</span></span> <span data-ttu-id="6041e-125">Klik op een rolgroep in de zoekresultaten om de wijzigingen in het detailvenster te bekijken.</span><span class="sxs-lookup"><span data-stu-id="6041e-125">Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6041e-126">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="6041e-126">How do you know this worked?</span></span>

<span data-ttu-id="6041e-127">Als u een groepsrapport voor beheerdersrollen hebt uitgevoerd, worden rolgroepen die binnen het datumbereik zijn gewijzigd, weergegeven in het deelvenster zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="6041e-127">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane.</span></span> <span data-ttu-id="6041e-128">Als er geen resultaten zijn, hebben er binnen het opgegeven datumbereik geen wijzigingen in rolgroepen plaatsgevonden.</span><span class="sxs-lookup"><span data-stu-id="6041e-128">If there are no results, then no changes to role groups have taken place within the specified date range.</span></span> <span data-ttu-id="6041e-129">Als u denkt dat er resultaten moeten zijn, wijzigt u het datumbereik en voert u het rapport opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="6041e-129">If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="6041e-130">Wijzigingen in het lidmaatschap van rolgroepen controleren</span><span class="sxs-lookup"><span data-stu-id="6041e-130">Monitor changes to role group membership</span></span>

<span data-ttu-id="6041e-131">Wanneer leden worden toegevoegd aan of verwijderd uit een rolgroep, geven de zoekresultaten in het detailvenster aan dat het lidmaatschap van de rolgroep is bijgewerkt en worden de huidige leden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6041e-131">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members.</span></span> <span data-ttu-id="6041e-132">In de resultaten wordt niet expliciet vermeld welke gebruiker is toegevoegd of verwijderd.</span><span class="sxs-lookup"><span data-stu-id="6041e-132">The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="6041e-133">Als u wilt bepalen of een gebruiker is toegevoegd of verwijderd, moet u twee afzonderlijke vermeldingen in het rapport vergelijken.</span><span class="sxs-lookup"><span data-stu-id="6041e-133">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="6041e-134">Laten we bijvoorbeeld de volgende logboekvermeldingen voor de **HelpDesk-rolgroep** bekijken:</span><span class="sxs-lookup"><span data-stu-id="6041e-134">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="6041e-135">1/27/2018 16:43</span><span class="sxs-lookup"><span data-stu-id="6041e-135">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="6041e-136">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="6041e-136">Administrator</span></span> <br> <span data-ttu-id="6041e-137">Bijgewerkte leden: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="6041e-137">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="6041e-138">2/06/2018 10:09</span><span class="sxs-lookup"><span data-stu-id="6041e-138">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="6041e-139">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="6041e-139">Administrator</span></span> <br> <span data-ttu-id="6041e-140">Bijgewerkte leden: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="6041e-140">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="6041e-141">2/19/2018 14:12</span><span class="sxs-lookup"><span data-stu-id="6041e-141">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="6041e-142">Administrator (Beheerder)</span><span class="sxs-lookup"><span data-stu-id="6041e-142">Administrator</span></span> <br> <span data-ttu-id="6041e-143">Bijgewerkte leden: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="6041e-143">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="6041e-144">In dit voorbeeld heeft het gebruikersaccount van de beheerder de volgende wijzigingen aangebracht:</span><span class="sxs-lookup"><span data-stu-id="6041e-144">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="6041e-145">Op 2/06/2018 hebben ze de user tonip toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="6041e-145">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="6041e-146">Op 2/19/2018 hebben ze de gebruiker verwijderd.</span><span class="sxs-lookup"><span data-stu-id="6041e-146">On 2/19/2018, they removed the user pilarp.</span></span>
