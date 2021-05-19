---
title: Core eDiscovery-zaken sluiten, opnieuw openen en verwijderen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In dit artikel wordt beschreven hoe u Core eDiscovery-zaken kunt beheren. Dit omvat het sluiten van een zaak, het opnieuw openen van een gesloten zaak en het verwijderen van een zaak.
ms.openlocfilehash: 8a54d5c8f93d36351538bc235a6dbeaaa602c3e9
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532444"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="28db2-104">Een Hoofd-eDiscovery-zaak sluiten, opnieuw openen en verwijderen</span><span class="sxs-lookup"><span data-stu-id="28db2-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="28db2-105">In dit artikel wordt beschreven hoe u core-eDiscovery-zaken sluit, opnieuw opent en verwijdert in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28db2-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="28db2-106">Een zaak sluiten</span><span class="sxs-lookup"><span data-stu-id="28db2-106">Close a case</span></span>

<span data-ttu-id="28db2-107">Wanneer de juridische zaak of het onderzoek dat wordt ondersteund door een Core eDiscovery-zaak is voltooid, kunt u de zaak sluiten.</span><span class="sxs-lookup"><span data-stu-id="28db2-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="28db2-108">Dit gebeurt er als u een zaak sluit:</span><span class="sxs-lookup"><span data-stu-id="28db2-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="28db2-109">Als de zaak een eDiscovery-inhoud bevat, worden deze uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="28db2-109">If the case contains any eDiscovery holds, they will be turned off.</span></span> <span data-ttu-id="28db2-110">Nadat de wachtstand is uitgeschakeld, wordt een respijtperiode van 30 dagen (een zogenaamde *vertragingstermijn)* toegepast op inhoudslocaties die in de wachtstand stonden.</span><span class="sxs-lookup"><span data-stu-id="28db2-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="28db2-111">Dit helpt voorkomen dat inhoud onmiddellijk wordt verwijderd en biedt beheerders de mogelijkheid om inhoud te zoeken en te herstellen voordat deze definitief kan worden verwijderd nadat de vertragingsperiode is verstreken.</span><span class="sxs-lookup"><span data-stu-id="28db2-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="28db2-112">Zie Inhoudslocaties verwijderen uit een [eDiscovery-hold voor meer informatie.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="28db2-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="28db2-113">Als u een zaak sluit, worden alleen de aan die zaak gekoppelde insluiten uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="28db2-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="28db2-114">Als andere bewaringen worden geplaatst op een inhoudslocatie (zoals een procesovergang, een bewaarbeleid of een bewaring vanuit een andere Core eDiscovery-zaak), blijven deze bewaringen behouden.</span><span class="sxs-lookup"><span data-stu-id="28db2-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="28db2-115">De zaak wordt nog steeds vermeld op de pagina Core eDiscovery in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="28db2-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="28db2-116">De details, bewaart, zoekt en leden van een gesloten zaak blijven behouden.</span><span class="sxs-lookup"><span data-stu-id="28db2-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="28db2-117">U kunt een zaak bewerken nadat deze is gesloten.</span><span class="sxs-lookup"><span data-stu-id="28db2-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="28db2-118">U kunt bijvoorbeeld leden toevoegen of verwijderen, zoekopdrachten maken en zoekresultaten exporteren.</span><span class="sxs-lookup"><span data-stu-id="28db2-118">For example, you can add or remove members, create searches, and export search results.</span></span> <span data-ttu-id="28db2-119">Het primaire verschil tussen actieve en gesloten zaken is dat eDiscovery-holds zijn uitgeschakeld wanneer een zaak wordt gesloten.</span><span class="sxs-lookup"><span data-stu-id="28db2-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="28db2-120">Een zaak sluiten:</span><span class="sxs-lookup"><span data-stu-id="28db2-120">To close a case:</span></span>
  
1. <span data-ttu-id="28db2-121">Klik in Microsoft 365 compliancecentrum op **eDiscovery** Core om de lijst weer te geven met  >   Core eDiscovery-zaken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="28db2-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="28db2-122">Klik op de naam van de zaak die u wilt sluiten.</span><span class="sxs-lookup"><span data-stu-id="28db2-122">Click the name of the case that you want to close.</span></span>

   ![Hoofdzaak sluiten op startpagina van zaak](../media/eDiscoveryCaseHomePage.png)

3. <span data-ttu-id="28db2-124">Klik op de startpagina onder **Status** op **Hoofdzaak sluiten.**</span><span class="sxs-lookup"><span data-stu-id="28db2-124">On the home page, under **Status**, click **Close case**.</span></span>

    <span data-ttu-id="28db2-125">Er wordt een waarschuwing weergegeven waarin wordt gezegd dat de aan de zaak gekoppelde in- en uit-standen worden uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="28db2-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="28db2-126">Klik **op Ja** om de zaak te sluiten.</span><span class="sxs-lookup"><span data-stu-id="28db2-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="28db2-127">De status op de startpagina van de zaak wordt gewijzigd van **Actief in** **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="28db2-127">The status on the case home page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="28db2-128">Klik op **de pagina Core eDiscovery** **op** Vernieuwen om de status van de gesloten zaak bij te werken.</span><span class="sxs-lookup"><span data-stu-id="28db2-128">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="28db2-129">Het kan tot 60 minuten duren voordat het sluitingsproces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="28db2-129">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="28db2-130">Wanneer het proces is voltooid, wordt de status van de zaak gewijzigd in **Gesloten** op de **pagina Core eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="28db2-130">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="28db2-131">Een gesloten zaak opnieuw openen</span><span class="sxs-lookup"><span data-stu-id="28db2-131">Reopen a closed case</span></span>

<span data-ttu-id="28db2-132">Wanneer u een zaak opnieuw opent, worden eDiscovery-gegevens die waren ingesteld toen de zaak werd gesloten, niet automatisch hersteld.</span><span class="sxs-lookup"><span data-stu-id="28db2-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="28db2-133">Nadat de zaak opnieuw is geopend, moet  u naar de pagina Houdt gaan en de vorige in- en uit te zetten.</span><span class="sxs-lookup"><span data-stu-id="28db2-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="28db2-134">Als u een wachtruimte wilt in- of uitschakelen, selecteert u deze om de flyoutpagina weer te geven en stelt u de schakelknop **Status** in op **Aan.**</span><span class="sxs-lookup"><span data-stu-id="28db2-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="28db2-135">Klik in Microsoft 365 compliancecentrum op **eDiscovery** Core om de lijst weer te geven met  >   Core eDiscovery-zaken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="28db2-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="28db2-136">Klik op de naam van de zaak die u opnieuw wilt openen.</span><span class="sxs-lookup"><span data-stu-id="28db2-136">Click the name of the case that you want to reopen.</span></span>

   ![Een gesloten zaak opnieuw openen](../media/eDiscoveryCaseHomePageReopen.png)

3. <span data-ttu-id="28db2-138">Klik op de startpagina onder **Status** op **Zaak opnieuw openen.**</span><span class="sxs-lookup"><span data-stu-id="28db2-138">On the home page, under **Status**, click **Reopen case**.</span></span>

    <span data-ttu-id="28db2-139">Er wordt een waarschuwing weergegeven met de melding dat de aan de zaak gekoppelde in- en uitstal nen niet automatisch worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="28db2-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="28db2-140">Klik **op Ja** om de zaak opnieuw te openen.</span><span class="sxs-lookup"><span data-stu-id="28db2-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="28db2-141">De status op de startpagina van de hoofdpagina wordt gewijzigd van **Gesloten in** **Actief.**</span><span class="sxs-lookup"><span data-stu-id="28db2-141">The status on the case home page flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="28db2-142">Klik op **de pagina Core eDiscovery** **op** Vernieuwen om de status van de opnieuw geopende zaak bij te werken.</span><span class="sxs-lookup"><span data-stu-id="28db2-142">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="28db2-143">Het kan tot 60 minuten duren voordat het heropeningsproces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="28db2-143">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="28db2-144">Wanneer het proces is voltooid, wordt de status van de zaak gewijzigd in **Actief** op de **pagina Core eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="28db2-144">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span>

6. <span data-ttu-id="28db2-145">(Optioneel) Als u alle wachtposities wilt in-  of in- of uit- zetten die aan de opnieuw geopende zaak zijn gekoppeld, gaat u naar het tabblad Wacht houden, selecteert u een wachtpositie en selecteert u vervolgens het selectievakje onder **Status** op de flyoutpagina van de wachtpositie.</span><span class="sxs-lookup"><span data-stu-id="28db2-145">(Optional) To turn on any holds associated with the reopened case, go to **Holds** tab, select a hold, and then select the checkbox under **Status** on the hold flyout page.</span></span>
  
## <a name="delete-a-case"></a><span data-ttu-id="28db2-146">Een zaak verwijderen</span><span class="sxs-lookup"><span data-stu-id="28db2-146">Delete a case</span></span>

<span data-ttu-id="28db2-147">U kunt ook actieve en gesloten Core eDiscovery-zaken verwijderen.</span><span class="sxs-lookup"><span data-stu-id="28db2-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="28db2-148">Wanneer u een zaak verwijdert, worden alle zoekopdrachten en exporten in de zaak verwijderd en wordt de zaak verwijderd uit de lijst met zaken op de **pagina Core eDiscovery** in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="28db2-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="28db2-149">U kunt een verwijderde zaak niet opnieuw openen.</span><span class="sxs-lookup"><span data-stu-id="28db2-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="28db2-150">Voordat u een zaak kunt verwijderen (of deze nu  actief of gesloten is), moet u eerst alle eDiscovery-items verwijderen die aan de zaak zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="28db2-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="28db2-151">Dit geldt ook voor het verwijderen van in-standen met de status **Uit.**</span><span class="sxs-lookup"><span data-stu-id="28db2-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="28db2-152">Een eDiscovery-hold verwijderen:</span><span class="sxs-lookup"><span data-stu-id="28db2-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="28db2-153">Ga naar **het tabblad** Houdt in het geval dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="28db2-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="28db2-154">Selecteer de wacht die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="28db2-154">Select the hold that you want to delete.</span></span>

3. <span data-ttu-id="28db2-155">Klik op de flyoutpagina op **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="28db2-155">On the flyout page, click **Delete**.</span></span>

      ![Een eDiscovery-hold verwijderen](../media/DeleteeDiscoveryHold.png)

<span data-ttu-id="28db2-157">Een zaak verwijderen:</span><span class="sxs-lookup"><span data-stu-id="28db2-157">To delete a case:</span></span>

1. <span data-ttu-id="28db2-158">Klik in Microsoft 365 compliancecentrum op **eDiscovery** Core om de lijst weer te geven met  >   Core eDiscovery-zaken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="28db2-158">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="28db2-159">Klik op de naam van de zaak die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="28db2-159">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="28db2-160">Klik op de startpagina van de zaak onder **Status** op **Hoofd zaak verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="28db2-160">On the case home page, under **Status**, click **Delete case**.</span></span>

      ![Een zaak verwijderen](../media/eDiscoveryCaseHomePageDelete.png)

<span data-ttu-id="28db2-162">Als de zaak die u probeert te verwijderen nog steeds eDiscovery bevat, ontvangt u een foutbericht.</span><span class="sxs-lookup"><span data-stu-id="28db2-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="28db2-163">U moet alle aan de zaak gekoppelde items verwijderen en vervolgens opnieuw proberen om de zaak te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="28db2-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
