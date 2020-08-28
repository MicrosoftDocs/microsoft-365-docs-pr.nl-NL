---
title: Werken met App-beheer
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289457"
---
# <a name="work-with-app-control"></a><span data-ttu-id="f621c-103">Werken met App-beheer</span><span class="sxs-lookup"><span data-stu-id="f621c-103">Work with app control</span></span>

<span data-ttu-id="f621c-104">Wanneer het app-besturingselement is geïmplementeerd in uw omgeving, hebben zowel u als door Microsoft beheerde bureaublad bewerkingen voortdurend verantwoordelijkheden.</span><span class="sxs-lookup"><span data-stu-id="f621c-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="f621c-105">U kunt bijvoorbeeld een nieuwe app toevoegen aan de omgeving of een vertrouwde ondertekenaar toevoegen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f621c-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="f621c-106">Ter verbetering van de beveiliging moeten alle apps met een code zijn ondertekend voordat u ze vrijgeeft aan gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f621c-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="f621c-107">De details van de app van een app bevatten informatie over de ondertekenaar.</span><span class="sxs-lookup"><span data-stu-id="f621c-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="f621c-108">Een nieuwe app toevoegen</span><span class="sxs-lookup"><span data-stu-id="f621c-108">Add a new app</span></span>

<span data-ttu-id="f621c-109">Voer de volgende stappen uit om een nieuwe app toe te voegen:</span><span class="sxs-lookup"><span data-stu-id="f621c-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="f621c-110">Voeg de app toe aan [Microsoft intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="f621c-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="f621c-111">Implementeer de app op een willekeurig apparaat in de test ring.</span><span class="sxs-lookup"><span data-stu-id="f621c-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="f621c-112">Test de app op basis van uw standaardbedrijfsprocessen.</span><span class="sxs-lookup"><span data-stu-id="f621c-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="f621c-113">Ga naar Logboekinzage onder **toepassingen en services Logs\Microsoft\Windows\AppLocker**en zoek naar gebeurtenissen van **8003** of **8006** .</span><span class="sxs-lookup"><span data-stu-id="f621c-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="f621c-114">Deze gebeurtenissen geven aan dat de app wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="f621c-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="f621c-115">Zie voor meer informatie over de app-waarschuwingen en hun betekenissen [Logboeken met behulp van AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span><span class="sxs-lookup"><span data-stu-id="f621c-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="f621c-116">Als u een van deze gebeurtenissen vindt, opent u een aanvraag voor een afzender met Microsoft beheerde bureaublad bewerkingen.</span><span class="sxs-lookup"><span data-stu-id="f621c-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="f621c-117">Een vertrouwde ondertekenaar toevoegen (of verwijderen)</span><span class="sxs-lookup"><span data-stu-id="f621c-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="f621c-118">Wanneer u een Onderteken aanvraag opent, moet u eerst enkele belangrijke details van de uitgever geven.</span><span class="sxs-lookup"><span data-stu-id="f621c-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="f621c-119">Voer daarna de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="f621c-119">Then follow these steps:</span></span>

1. <span data-ttu-id="f621c-120">[Details van de uitgever verzamelen](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="f621c-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="f621c-121">Open een ticket met door Microsoft beheerde bureaublad bewerkingen om de ondertekenaars regel te aanvragen en de volgende details weer te geven:</span><span class="sxs-lookup"><span data-stu-id="f621c-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="f621c-122">Naam van toepassing</span><span class="sxs-lookup"><span data-stu-id="f621c-122">Application name</span></span> 
    - <span data-ttu-id="f621c-123">Toepassingsversie</span><span class="sxs-lookup"><span data-stu-id="f621c-123">Application version</span></span> 
    - <span data-ttu-id="f621c-124">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f621c-124">Description</span></span> 
    - <span data-ttu-id="f621c-125">Type wijzigen (' toevoegen ' of ' verwijderen ')</span><span class="sxs-lookup"><span data-stu-id="f621c-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="f621c-126">Details van de uitgever (bijvoorbeeld: "O = <publisher name> , L = <location> , S = staat, C = Country")</span><span class="sxs-lookup"><span data-stu-id="f621c-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="f621c-127">Als u het vertrouwen voor een app wilt verwijderen, voert u dezelfde stappen uit maar stelt u het **type wijzigen** in dat u wilt *verwijderen*.</span><span class="sxs-lookup"><span data-stu-id="f621c-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="f621c-128">Met bewerkingen worden de beleidsregels progressief geïmplementeerd voor implementatie groepen die het volgende schema volgen:</span><span class="sxs-lookup"><span data-stu-id="f621c-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="f621c-129">Implementatiegroep</span><span class="sxs-lookup"><span data-stu-id="f621c-129">Deployment group</span></span>  |<span data-ttu-id="f621c-130">Beleidstype</span><span class="sxs-lookup"><span data-stu-id="f621c-130">Policy type</span></span>  |<span data-ttu-id="f621c-131">Tijdsinstellingen</span><span class="sxs-lookup"><span data-stu-id="f621c-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f621c-132">Wedstrijden</span><span class="sxs-lookup"><span data-stu-id="f621c-132">Test</span></span>     |  <span data-ttu-id="f621c-133">Oordeel</span><span class="sxs-lookup"><span data-stu-id="f621c-133">Audit</span></span>       |  <span data-ttu-id="f621c-134">Dag 0</span><span class="sxs-lookup"><span data-stu-id="f621c-134">Day 0</span></span>       |
|<span data-ttu-id="f621c-135">Eerste</span><span class="sxs-lookup"><span data-stu-id="f621c-135">First</span></span>     | <span data-ttu-id="f621c-136">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="f621c-136">Enforced</span></span>        | <span data-ttu-id="f621c-137">Dag 1</span><span class="sxs-lookup"><span data-stu-id="f621c-137">Day 1</span></span>        |
|<span data-ttu-id="f621c-138">Razendsnelle</span><span class="sxs-lookup"><span data-stu-id="f621c-138">Fast</span></span>     | <span data-ttu-id="f621c-139">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="f621c-139">Enforced</span></span>        |  <span data-ttu-id="f621c-140">Dag 2</span><span class="sxs-lookup"><span data-stu-id="f621c-140">Day 2</span></span>       |
|<span data-ttu-id="f621c-141">Scala</span><span class="sxs-lookup"><span data-stu-id="f621c-141">Broad</span></span>     | <span data-ttu-id="f621c-142">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="f621c-142">Enforced</span></span>        |  <span data-ttu-id="f621c-143">Dag 3</span><span class="sxs-lookup"><span data-stu-id="f621c-143">Day 3</span></span>       |


<span data-ttu-id="f621c-144">U kunt op elk gewenst moment tijdens de implementatie de implementatie onderbreken of terugdraaien.</span><span class="sxs-lookup"><span data-stu-id="f621c-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="f621c-145">Open hiervoor een andere serviceaanvraag met bewerkingen.</span><span class="sxs-lookup"><span data-stu-id="f621c-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="f621c-146">Als u de release van een handtekeningregel onderbreekt, moet die regel worden hersteld of voltooid voordat een andere implementatie kan worden gestart.</span><span class="sxs-lookup"><span data-stu-id="f621c-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="f621c-147">Details van de uitgever verzamelen</span><span class="sxs-lookup"><span data-stu-id="f621c-147">Gather publisher details</span></span>

<span data-ttu-id="f621c-148">Voer de volgende stappen uit om toegang te krijgen tot de gegevens van de uitgever van de app:</span><span class="sxs-lookup"><span data-stu-id="f621c-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="f621c-149">Zoek een Microsoft-beheerapparaat in de test ring waarop een beleid voor controlemodus is toegepast.</span><span class="sxs-lookup"><span data-stu-id="f621c-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="f621c-150">Probeer de app op het apparaat te installeren.</span><span class="sxs-lookup"><span data-stu-id="f621c-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="f621c-151">Open de logboek viewer op dat apparaat.</span><span class="sxs-lookup"><span data-stu-id="f621c-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="f621c-152">Ga in logboeken naar **toepassingen en services Logs\Microsoft\Windows**en selecteer vervolgens **AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="f621c-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="f621c-153">Zoek een willekeurige gebeurtenis in **8003** of **8006** en kopieer de gegevens uit de gebeurtenis:</span><span class="sxs-lookup"><span data-stu-id="f621c-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="f621c-154">Naam van toepassing</span><span class="sxs-lookup"><span data-stu-id="f621c-154">Application name</span></span> 
    - <span data-ttu-id="f621c-155">Toepassingsversie</span><span class="sxs-lookup"><span data-stu-id="f621c-155">Application version</span></span> 
    - <span data-ttu-id="f621c-156">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f621c-156">Description</span></span> 
    - <span data-ttu-id="f621c-157">Details van de uitgever (bijvoorbeeld: "O = <publisher name> , L = <location> , S = staat, C = Country")</span><span class="sxs-lookup"><span data-stu-id="f621c-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 
