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
ms.openlocfilehash: 9efe6ba6704b0e1633973d157c38827221316bbd
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430445"
---
# <a name="work-with-app-control"></a><span data-ttu-id="2d308-103">Werken met App-beheer</span><span class="sxs-lookup"><span data-stu-id="2d308-103">Work with app control</span></span>

<span data-ttu-id="2d308-104">Zodra app-besturingselement in uw omgeving is geïmplementeerd, hebben zowel u als Microsoft Managed Desktop Operations lopende verantwoordelijkheden.</span><span class="sxs-lookup"><span data-stu-id="2d308-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="2d308-105">U bijvoorbeeld een nieuwe app in de omgeving toevoegen of een vertrouwde ondertekenaar toevoegen (of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="2d308-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="2d308-106">Om de beveiliging te verbeteren, moeten alle apps zijn ondertekend met code voordat u ze vrijlaat aan eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="2d308-106">To improve security, all apps should be code-signed before you release them to end users.</span></span> <span data-ttu-id="2d308-107">De uitgeversgegevens van een app bevatten informatie over de ondertekenaar.</span><span class="sxs-lookup"><span data-stu-id="2d308-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="2d308-108">Een nieuwe app toevoegen</span><span class="sxs-lookup"><span data-stu-id="2d308-108">Add a new app</span></span>

<span data-ttu-id="2d308-109">Voer de volgende stappen uit om een nieuwe app toe te voegen:</span><span class="sxs-lookup"><span data-stu-id="2d308-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="2d308-110">Voeg de app toe aan [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="2d308-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="2d308-111">Implementeer de app op elk apparaat in de testring.</span><span class="sxs-lookup"><span data-stu-id="2d308-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="2d308-112">Test uw app op basis van uw standaard bedrijfsprocessen.</span><span class="sxs-lookup"><span data-stu-id="2d308-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="2d308-113">Controleer Logboeken onder **Toepassings- en Serviceslogboeken\Microsoft\Windows\AppLocker**, op zoek naar **8003-** of **8006-gebeurtenissen.**</span><span class="sxs-lookup"><span data-stu-id="2d308-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="2d308-114">Deze gebeurtenissen geven aan dat de app zou worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="2d308-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="2d308-115">Zie [Logboeken gebruiken met AppLocker voor](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)meer informatie over alle App Locker-evenementen en hun betekenissen.</span><span class="sxs-lookup"><span data-stu-id="2d308-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="2d308-116">Als u een van deze gebeurtenissen vindt, opent u een aanvraag voor ondertekenaars met Microsoft Managed Desktop Operations.</span><span class="sxs-lookup"><span data-stu-id="2d308-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="2d308-117">Een vertrouwde ondertekenaar toevoegen (of verwijderen)</span><span class="sxs-lookup"><span data-stu-id="2d308-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="2d308-118">Wanneer u een ondertekenaaraanvraag opent, moet u eerst een aantal belangrijke uitgeversgegevens opgeven.</span><span class="sxs-lookup"><span data-stu-id="2d308-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="2d308-119">Volg dan de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="2d308-119">Then follow these steps:</span></span>

1. <span data-ttu-id="2d308-120">[Gegevens van uitgevers verzamelen.](#gather-publisher-details)</span><span class="sxs-lookup"><span data-stu-id="2d308-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="2d308-121">Open een ticket met Microsoft Managed Desktop Operations om de ondertekenaarregel op te vragen en de volgende details op te nemen:</span><span class="sxs-lookup"><span data-stu-id="2d308-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="2d308-122">Toepassingsnaam</span><span class="sxs-lookup"><span data-stu-id="2d308-122">Application name</span></span> 
    - <span data-ttu-id="2d308-123">Toepassingsversie</span><span class="sxs-lookup"><span data-stu-id="2d308-123">Application version</span></span> 
    - <span data-ttu-id="2d308-124">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2d308-124">Description</span></span> 
    - <span data-ttu-id="2d308-125">Type wijzigen ('toevoegen' of 'verwijderen')</span><span class="sxs-lookup"><span data-stu-id="2d308-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="2d308-126">Uitgeversgegevens (bijvoorbeeld: "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="2d308-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="2d308-127">Als u vertrouwen voor een app wilt verwijderen, voert u dezelfde stappen uit, maar stelt **u Type Wijzigen** in om te *verwijderen.*</span><span class="sxs-lookup"><span data-stu-id="2d308-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="2d308-128">Operations implementeert geleidelijk beleid naar implementatiegroepen volgens deze planning:</span><span class="sxs-lookup"><span data-stu-id="2d308-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="2d308-129">Implementatiegroep</span><span class="sxs-lookup"><span data-stu-id="2d308-129">Deployment group</span></span>  |<span data-ttu-id="2d308-130">Beleidstype</span><span class="sxs-lookup"><span data-stu-id="2d308-130">Policy type</span></span>  |<span data-ttu-id="2d308-131">Timing</span><span class="sxs-lookup"><span data-stu-id="2d308-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2d308-132">Test</span><span class="sxs-lookup"><span data-stu-id="2d308-132">Test</span></span>     |  <span data-ttu-id="2d308-133">Audit</span><span class="sxs-lookup"><span data-stu-id="2d308-133">Audit</span></span>       |  <span data-ttu-id="2d308-134">Dag 0</span><span class="sxs-lookup"><span data-stu-id="2d308-134">Day 0</span></span>       |
|<span data-ttu-id="2d308-135">Eerste</span><span class="sxs-lookup"><span data-stu-id="2d308-135">First</span></span>     | <span data-ttu-id="2d308-136">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="2d308-136">Enforced</span></span>        | <span data-ttu-id="2d308-137">Dag 1</span><span class="sxs-lookup"><span data-stu-id="2d308-137">Day 1</span></span>        |
|<span data-ttu-id="2d308-138">Snel</span><span class="sxs-lookup"><span data-stu-id="2d308-138">Fast</span></span>     | <span data-ttu-id="2d308-139">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="2d308-139">Enforced</span></span>        |  <span data-ttu-id="2d308-140">Dag 2</span><span class="sxs-lookup"><span data-stu-id="2d308-140">Day 2</span></span>       |
|<span data-ttu-id="2d308-141">Brede</span><span class="sxs-lookup"><span data-stu-id="2d308-141">Broad</span></span>     | <span data-ttu-id="2d308-142">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="2d308-142">Enforced</span></span>        |  <span data-ttu-id="2d308-143">Dag 3</span><span class="sxs-lookup"><span data-stu-id="2d308-143">Day 3</span></span>       |


<span data-ttu-id="2d308-144">U de implementatie op elk gewenst moment tijdens de implementatie onderbreken of terugdraaien.</span><span class="sxs-lookup"><span data-stu-id="2d308-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="2d308-145">Open hiervoor een andere serviceaanvraag met Operations.</span><span class="sxs-lookup"><span data-stu-id="2d308-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="2d308-146">Als u de release van een ondertekenaarregel onderbreekt, moet deze regel worden teruggedraaid of voltooid voordat een andere implementatie kan worden gestart.</span><span class="sxs-lookup"><span data-stu-id="2d308-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="2d308-147">Uitgeversgegevens verzamelen</span><span class="sxs-lookup"><span data-stu-id="2d308-147">Gather publisher details</span></span>

<span data-ttu-id="2d308-148">Voer de volgende stappen uit om toegang te krijgen tot de uitgeversgegevens voor een app:</span><span class="sxs-lookup"><span data-stu-id="2d308-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="2d308-149">Zoek een Microsoft Managed Desktop-apparaat in de testring waarop een controlemodusbeleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="2d308-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="2d308-150">Probeer de app op het apparaat te installeren.</span><span class="sxs-lookup"><span data-stu-id="2d308-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="2d308-151">Open Logboeken op dat apparaat.</span><span class="sxs-lookup"><span data-stu-id="2d308-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="2d308-152">Navigeer in Logboeken naar **toepassings- en serviceslogboeken\Microsoft\Windows**en selecteer **vervolgens AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="2d308-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="2d308-153">Zoek een gebeurtenis van **8003** of **8006** en kopieer vervolgens informatie uit de gebeurtenis:</span><span class="sxs-lookup"><span data-stu-id="2d308-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="2d308-154">Toepassingsnaam</span><span class="sxs-lookup"><span data-stu-id="2d308-154">Application name</span></span> 
    - <span data-ttu-id="2d308-155">Toepassingsversie</span><span class="sxs-lookup"><span data-stu-id="2d308-155">Application version</span></span> 
    - <span data-ttu-id="2d308-156">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2d308-156">Description</span></span> 
    - <span data-ttu-id="2d308-157">Uitgeversgegevens (bijvoorbeeld: "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="2d308-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 
