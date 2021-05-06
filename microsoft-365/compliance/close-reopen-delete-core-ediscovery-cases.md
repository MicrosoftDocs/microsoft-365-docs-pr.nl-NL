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
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2020
ms.locfileid: "52161463"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="634e7-104">Een Hoofd-eDiscovery-zaak sluiten, opnieuw openen en verwijderen</span><span class="sxs-lookup"><span data-stu-id="634e7-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="634e7-105">In dit artikel wordt beschreven hoe u core-eDiscovery-zaken sluit, opnieuw opent en verwijdert in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="634e7-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="634e7-106">Een zaak sluiten</span><span class="sxs-lookup"><span data-stu-id="634e7-106">Close a case</span></span>

<span data-ttu-id="634e7-107">Wanneer de juridische zaak of het onderzoek dat wordt ondersteund door een Core eDiscovery-zaak is voltooid, kunt u de zaak sluiten.</span><span class="sxs-lookup"><span data-stu-id="634e7-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="634e7-108">Dit gebeurt er als u een zaak sluit:</span><span class="sxs-lookup"><span data-stu-id="634e7-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="634e7-109">Als de zaak inhoudslocaties bevat in de eDiscovery-wacht, worden deze in de wacht geplaatst.</span><span class="sxs-lookup"><span data-stu-id="634e7-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="634e7-110">Nadat de wachtstand is uitgeschakeld, wordt een respijtperiode van 30 dagen (een zogenaamde *vertragingstermijn)* toegepast op inhoudslocaties die in de wachtstand stonden.</span><span class="sxs-lookup"><span data-stu-id="634e7-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="634e7-111">Dit helpt voorkomen dat inhoud onmiddellijk wordt verwijderd en biedt beheerders de mogelijkheid om inhoud te zoeken en te herstellen voordat deze definitief kan worden verwijderd nadat de vertragingsperiode is verstreken.</span><span class="sxs-lookup"><span data-stu-id="634e7-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="634e7-112">Zie Inhoudslocaties verwijderen uit een [eDiscovery-hold voor meer informatie.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="634e7-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="634e7-113">Als u een zaak sluit, worden alleen de aan die zaak gekoppelde insluiten uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="634e7-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="634e7-114">Als andere bewaringen worden geplaatst op een inhoudslocatie (zoals een procesovergang, een bewaarbeleid of een bewaring vanuit een andere Core eDiscovery-zaak), blijven deze bewaringen behouden.</span><span class="sxs-lookup"><span data-stu-id="634e7-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="634e7-115">De zaak wordt nog steeds vermeld op de pagina Core eDiscovery in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="634e7-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="634e7-116">De details, bewaart, zoekt en leden van een gesloten zaak blijven behouden.</span><span class="sxs-lookup"><span data-stu-id="634e7-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="634e7-117">U kunt een zaak bewerken nadat deze is gesloten.</span><span class="sxs-lookup"><span data-stu-id="634e7-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="634e7-118">U kunt bijvoorbeeld leden toevoegen of verwijderen, zoekopdrachten maken en zoekresultaten exporteren.</span><span class="sxs-lookup"><span data-stu-id="634e7-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="634e7-119">Het primaire verschil tussen actieve en gesloten zaken is dat eDiscovery-holds zijn uitgeschakeld wanneer een zaak wordt gesloten.</span><span class="sxs-lookup"><span data-stu-id="634e7-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="634e7-120">Een zaak sluiten:</span><span class="sxs-lookup"><span data-stu-id="634e7-120">To close a case:</span></span>
  
1. <span data-ttu-id="634e7-121">Klik in Microsoft 365 compliancecentrum op **eDiscovery** Core om de lijst weer te geven met  >   Core eDiscovery-zaken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="634e7-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="634e7-122">Klik op de naam van de zaak die u wilt sluiten.</span><span class="sxs-lookup"><span data-stu-id="634e7-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="634e7-123">De **pagina Manage this case** flyout wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="634e7-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="634e7-124">Klik **onder Casestatus beheren** op Zaak **sluiten.**</span><span class="sxs-lookup"><span data-stu-id="634e7-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="634e7-125">Er wordt een waarschuwing weergegeven waarin wordt gezegd dat de aan de zaak gekoppelde in- en uit-standen worden uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="634e7-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="634e7-126">Klik **op Ja** om de zaak te sluiten.</span><span class="sxs-lookup"><span data-stu-id="634e7-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="634e7-127">De status op de **flyoutpagina Deze zaak** beheren wordt gewijzigd van **Actief in** **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="634e7-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="634e7-128">Sluit de **pagina Deze zaak** beheren.</span><span class="sxs-lookup"><span data-stu-id="634e7-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="634e7-129">Klik op **de pagina Core eDiscovery** **op** Vernieuwen om de status van de gesloten zaak bij te werken.</span><span class="sxs-lookup"><span data-stu-id="634e7-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="634e7-130">Het kan tot 60 minuten duren voordat het sluitingsproces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="634e7-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="634e7-131">Wanneer het proces is voltooid, wordt de status van de zaak gewijzigd in **Gesloten** op de **pagina Core eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="634e7-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="634e7-132">Klik nogmaals op de naam  van de zaak om de flyout pagina Deze zaak beheren weer te geven, die informatie bevat over wanneer de zaak is gesloten en wie de zaak heeft gesloten.</span><span class="sxs-lookup"><span data-stu-id="634e7-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="634e7-133">Een gesloten zaak opnieuw openen</span><span class="sxs-lookup"><span data-stu-id="634e7-133">Reopen a closed case</span></span>

<span data-ttu-id="634e7-134">Wanneer u een zaak opnieuw opent, worden eDiscovery-gegevens die waren ingesteld toen de zaak werd gesloten, niet automatisch hersteld.</span><span class="sxs-lookup"><span data-stu-id="634e7-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="634e7-135">Nadat de zaak opnieuw is geopend, moet  u naar de pagina Houdt gaan en de vorige in- en uit te zetten.</span><span class="sxs-lookup"><span data-stu-id="634e7-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="634e7-136">Als u een wachtruimte wilt in- of uitschakelen, selecteert u deze om de flyoutpagina weer te geven en stelt u de schakelknop **Status** in op **Aan.**</span><span class="sxs-lookup"><span data-stu-id="634e7-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="634e7-137">Klik in Microsoft 365 compliancecentrum op **eDiscovery** Core om de lijst weer te geven met  >   Core eDiscovery-zaken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="634e7-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="634e7-138">Klik op de naam van de zaak die u opnieuw wilt openen.</span><span class="sxs-lookup"><span data-stu-id="634e7-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="634e7-139">De **pagina Manage this case** flyout wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="634e7-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="634e7-140">Klik **onder Casestatus beheren** op Zaak opnieuw **openen.**</span><span class="sxs-lookup"><span data-stu-id="634e7-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="634e7-141">Er wordt een waarschuwing weergegeven met de melding dat de aan de zaak gekoppelde in- en uitstal nen niet automatisch worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="634e7-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="634e7-142">Klik **op Ja** om de zaak opnieuw te openen.</span><span class="sxs-lookup"><span data-stu-id="634e7-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="634e7-143">De status op de **flyoutpagina Deze zaak** beheren wordt gewijzigd van **Gesloten in** **Actief.**</span><span class="sxs-lookup"><span data-stu-id="634e7-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="634e7-144">Sluit de **pagina Deze zaak** beheren.</span><span class="sxs-lookup"><span data-stu-id="634e7-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="634e7-145">Klik op **de pagina Core eDiscovery** **op** Vernieuwen om de status van de opnieuw geopende zaak bij te werken.</span><span class="sxs-lookup"><span data-stu-id="634e7-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="634e7-146">Het kan tot 60 minuten duren voordat het heropeningsproces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="634e7-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="634e7-147">Wanneer het proces is voltooid, wordt de status van de zaak gewijzigd in **Actief** op de **pagina Core eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="634e7-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="634e7-148">Een zaak verwijderen</span><span class="sxs-lookup"><span data-stu-id="634e7-148">Delete a case</span></span>

<span data-ttu-id="634e7-149">U kunt ook actieve en gesloten Core eDiscovery-zaken verwijderen.</span><span class="sxs-lookup"><span data-stu-id="634e7-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="634e7-150">Wanneer u een zaak verwijdert, worden alle zoekopdrachten en exporten in de zaak verwijderd en wordt de zaak verwijderd uit de lijst met zaken op de **pagina Core eDiscovery** in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="634e7-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="634e7-151">U kunt een verwijderde zaak niet opnieuw openen.</span><span class="sxs-lookup"><span data-stu-id="634e7-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="634e7-152">Voordat u een zaak kunt verwijderen (of deze nu  actief of gesloten is), moet u eerst alle eDiscovery-items verwijderen die aan de zaak zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="634e7-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="634e7-153">Dit geldt ook voor het verwijderen van in-standen met de status **Uit.**</span><span class="sxs-lookup"><span data-stu-id="634e7-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="634e7-154">Een eDiscovery-hold verwijderen:</span><span class="sxs-lookup"><span data-stu-id="634e7-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="634e7-155">Ga naar **het tabblad** Houdt in het geval dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="634e7-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="634e7-156">Klik op de wacht die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="634e7-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="634e7-157">Klik op de flyoutpagina op **Wacht houden verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="634e7-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="634e7-158">Een zaak verwijderen:</span><span class="sxs-lookup"><span data-stu-id="634e7-158">To delete a case:</span></span>

1. <span data-ttu-id="634e7-159">Klik in Microsoft 365 compliancecentrum op **eDiscovery** Core om de lijst weer te geven met  >   Core eDiscovery-zaken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="634e7-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="634e7-160">Klik op de naam van de zaak die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="634e7-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="634e7-161">Klik **onder Hoofd zaakstatus** beheren op de flyout-pagina op **Hoofd zaak verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="634e7-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="634e7-162">Als de zaak die u probeert te verwijderen nog steeds eDiscovery bevat, ontvangt u een foutbericht.</span><span class="sxs-lookup"><span data-stu-id="634e7-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="634e7-163">U moet alle aan de zaak gekoppelde items verwijderen en vervolgens opnieuw proberen om de zaak te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="634e7-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
