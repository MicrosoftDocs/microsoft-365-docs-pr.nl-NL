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
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917638"
---
# <a name="work-with-app-control"></a><span data-ttu-id="b4bc7-103">Werken met App-beheer</span><span class="sxs-lookup"><span data-stu-id="b4bc7-103">Work with app control</span></span>

<span data-ttu-id="b4bc7-104">Nadat app-beheer is geïmplementeerd in uw omgeving, hebben zowel u als Microsoft Managed Desktop Operations lopende verantwoordelijkheden.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="b4bc7-105">U kunt bijvoorbeeld een nieuwe app in de omgeving toevoegen of een vertrouwde ondertekenaar toevoegen (of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="b4bc7-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="b4bc7-106">Om de beveiliging te verbeteren, moeten alle apps code-ondertekend zijn voordat u ze aan gebruikers los laat.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="b4bc7-107">De uitgeverdetails van een app bevatten informatie over de ondertekenaar.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="b4bc7-108">Een nieuwe app toevoegen</span><span class="sxs-lookup"><span data-stu-id="b4bc7-108">Add a new app</span></span>

<span data-ttu-id="b4bc7-109">Als u een nieuwe app wilt toevoegen, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="b4bc7-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="b4bc7-110">Voeg de app toe aan [Microsoft Intune.](/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="b4bc7-110">Add the app to [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="b4bc7-111">Implementeer de app op elk apparaat in de testring.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="b4bc7-112">Test uw app op basis van uw standaard bedrijfsprocessen.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="b4bc7-113">Controleer Gebeurtenisviewer onder **Toepassings- en serviceslogboeken\Microsoft\Windows\AppLocker**, op zoek naar **8003** of **8006 gebeurtenissen.**</span><span class="sxs-lookup"><span data-stu-id="b4bc7-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="b4bc7-114">Deze gebeurtenissen geven aan dat de app wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="b4bc7-115">Zie [Gebeurtenisviewer gebruiken met AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)voor meer informatie over alle gebeurtenissen in App Locker en hun betekenis.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="b4bc7-116">Als u een van deze gebeurtenissen vindt, opent u een aanmeldingsaanvraag met Microsoft Managed Desktop Operations.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="b4bc7-117">Een vertrouwde ondertekenaar toevoegen (of verwijderen)</span><span class="sxs-lookup"><span data-stu-id="b4bc7-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="b4bc7-118">Wanneer u een aanvraag voor een ondertekenaar opent, moet u eerst enkele belangrijke details van de uitgever verstrekken.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="b4bc7-119">Volg vervolgens de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="b4bc7-119">Then follow these steps:</span></span>

1. <span data-ttu-id="b4bc7-120">[Publisher-details verzamelen.](#gather-publisher-details)</span><span class="sxs-lookup"><span data-stu-id="b4bc7-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="b4bc7-121">Open een ticket met Microsoft Managed Desktop Operations om de ondertekenaarsregel aan te vragen en neem de volgende details op:</span><span class="sxs-lookup"><span data-stu-id="b4bc7-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="b4bc7-122">Naam van toepassing</span><span class="sxs-lookup"><span data-stu-id="b4bc7-122">Application name</span></span> 
    - <span data-ttu-id="b4bc7-123">Toepassingsversie</span><span class="sxs-lookup"><span data-stu-id="b4bc7-123">Application version</span></span> 
    - <span data-ttu-id="b4bc7-124">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b4bc7-124">Description</span></span> 
    - <span data-ttu-id="b4bc7-125">Type wijzigen ("toevoegen" of "verwijderen")</span><span class="sxs-lookup"><span data-stu-id="b4bc7-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="b4bc7-126">Publisher details (bijvoorbeeld: "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="b4bc7-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="b4bc7-127">Als u vertrouwen voor een app wilt verwijderen, volgt u dezelfde stappen, maar stelt u **Type wijzigen in** om deze te *verwijderen.*</span><span class="sxs-lookup"><span data-stu-id="b4bc7-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="b4bc7-128">In Operations worden beleidsregels geleidelijk geïmplementeerd voor implementatiegroepen volgens deze planning:</span><span class="sxs-lookup"><span data-stu-id="b4bc7-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="b4bc7-129">Implementatiegroep</span><span class="sxs-lookup"><span data-stu-id="b4bc7-129">Deployment group</span></span>  |<span data-ttu-id="b4bc7-130">Beleidstype</span><span class="sxs-lookup"><span data-stu-id="b4bc7-130">Policy type</span></span>  |<span data-ttu-id="b4bc7-131">Tijdsinstellingen</span><span class="sxs-lookup"><span data-stu-id="b4bc7-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b4bc7-132">Test</span><span class="sxs-lookup"><span data-stu-id="b4bc7-132">Test</span></span>     |  <span data-ttu-id="b4bc7-133">Controle</span><span class="sxs-lookup"><span data-stu-id="b4bc7-133">Audit</span></span>       |  <span data-ttu-id="b4bc7-134">Dag 0</span><span class="sxs-lookup"><span data-stu-id="b4bc7-134">Day 0</span></span>       |
|<span data-ttu-id="b4bc7-135">Eerst</span><span class="sxs-lookup"><span data-stu-id="b4bc7-135">First</span></span>     | <span data-ttu-id="b4bc7-136">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="b4bc7-136">Enforced</span></span>        | <span data-ttu-id="b4bc7-137">Dag 1</span><span class="sxs-lookup"><span data-stu-id="b4bc7-137">Day 1</span></span>        |
|<span data-ttu-id="b4bc7-138">Snel</span><span class="sxs-lookup"><span data-stu-id="b4bc7-138">Fast</span></span>     | <span data-ttu-id="b4bc7-139">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="b4bc7-139">Enforced</span></span>        |  <span data-ttu-id="b4bc7-140">Dag 2</span><span class="sxs-lookup"><span data-stu-id="b4bc7-140">Day 2</span></span>       |
|<span data-ttu-id="b4bc7-141">Breed</span><span class="sxs-lookup"><span data-stu-id="b4bc7-141">Broad</span></span>     | <span data-ttu-id="b4bc7-142">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="b4bc7-142">Enforced</span></span>        |  <span data-ttu-id="b4bc7-143">Dag 3</span><span class="sxs-lookup"><span data-stu-id="b4bc7-143">Day 3</span></span>       |


<span data-ttu-id="b4bc7-144">U kunt de implementatie op elk moment tijdens de implementatie onderbreken of terugdraaien.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="b4bc7-145">Open hiervoor een andere serviceaanvraag met Operations.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="b4bc7-146">Als u de release van een ondertekenaarsregel pauzeert, moet deze regel worden teruggedraaid of voltooid voordat een andere uitrol kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="b4bc7-147">Publisher-details verzamelen</span><span class="sxs-lookup"><span data-stu-id="b4bc7-147">Gather publisher details</span></span>

<span data-ttu-id="b4bc7-148">Als u de publisher-gegevens voor een app wilt openen, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="b4bc7-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="b4bc7-149">Zoek een Microsoft Managed Desktop apparaat in de testring waarin een auditmodusbeleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="b4bc7-150">Probeer de app op het apparaat te installeren.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="b4bc7-151">Open Gebeurtenisviewer op dat apparaat.</span><span class="sxs-lookup"><span data-stu-id="b4bc7-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="b4bc7-152">Ga in Gebeurtenisviewer naar **Toepassings- en serviceslogboeken\Microsoft\Windows** en selecteer **Vervolgens AppLocker.**</span><span class="sxs-lookup"><span data-stu-id="b4bc7-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="b4bc7-153">Zoek een **8003-** of **8006-gebeurtenis** en kopieer gegevens uit de gebeurtenis:</span><span class="sxs-lookup"><span data-stu-id="b4bc7-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="b4bc7-154">Naam van toepassing</span><span class="sxs-lookup"><span data-stu-id="b4bc7-154">Application name</span></span> 
    - <span data-ttu-id="b4bc7-155">Toepassingsversie</span><span class="sxs-lookup"><span data-stu-id="b4bc7-155">Application version</span></span> 
    - <span data-ttu-id="b4bc7-156">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b4bc7-156">Description</span></span> 
    - <span data-ttu-id="b4bc7-157">Publisher details (bijvoorbeeld: "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="b4bc7-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span>