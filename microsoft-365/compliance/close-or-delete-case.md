---
title: Een case sluiten of verwijderen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Lees wat er gebeurt wanneer een onderzoek of juridische zaak die wordt ondersteund door een Advanced eDiscovery zaak wordt gesloten of verwijderd.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2020
ms.locfileid: "52161465"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="755c1-103">Een Advanced eDiscovery sluiten of verwijderen</span><span class="sxs-lookup"><span data-stu-id="755c1-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="755c1-104">Wanneer de juridische zaak of het onderzoek dat wordt ondersteund door een Advanced eDiscovery is voltooid, kunt u een zaak sluiten of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="755c1-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="755c1-105">U kunt ook een gesloten zaak opnieuw openen.</span><span class="sxs-lookup"><span data-stu-id="755c1-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="755c1-106">Een zaak sluiten</span><span class="sxs-lookup"><span data-stu-id="755c1-106">Close a case</span></span>

<span data-ttu-id="755c1-107">Dit gebeurt er als u een Advanced eDiscovery sluit:</span><span class="sxs-lookup"><span data-stu-id="755c1-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="755c1-108">Als de zaak inhoudslocaties bevat die in de wacht staan, worden deze in de wacht gezet.</span><span class="sxs-lookup"><span data-stu-id="755c1-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="755c1-109">Nadat de wachtstand is uitgeschakeld, wordt een respijtperiode van 30 dagen (een zogenaamde *vertragingstermijn)* toegepast op inhoudslocaties die in de wachtstand stonden.</span><span class="sxs-lookup"><span data-stu-id="755c1-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="755c1-110">Dit helpt voorkomen dat inhoud onmiddellijk wordt verwijderd en geeft beheerders de mogelijkheid om inhoud te zoeken of te herstellen die definitief wordt verwijderd nadat de vertragingsperiode is verstreken.</span><span class="sxs-lookup"><span data-stu-id="755c1-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="755c1-111">Zie Inhoudslocaties verwijderen uit een [eDiscovery-hold voor meer informatie.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="755c1-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="755c1-112">Als u een zaak sluit, worden alleen de aan die zaak gekoppelde insluiten uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="755c1-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="755c1-113">Als andere ingehouden eDiscovery's op een inhoudslocatie (zoals een procesovergang, core eDiscovery-bezit of een andere Advanced eDiscovery-zaak) worden bewaard, blijven deze in stand.</span><span class="sxs-lookup"><span data-stu-id="755c1-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="755c1-114">De zaak wordt nog steeds weergegeven op de eDiscovery-pagina in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="755c1-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="755c1-115">De details, bewaart, zoekt en leden van een gesloten zaak blijven behouden.</span><span class="sxs-lookup"><span data-stu-id="755c1-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="755c1-116">U kunt een zaak bewerken nadat deze is gesloten.</span><span class="sxs-lookup"><span data-stu-id="755c1-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="755c1-117">U kunt bijvoorbeeld leden toevoegen of verwijderen, zoekopdrachten maken, zoekresultaten exporteren en zoekresultaten voorbereiden voor analyse in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="755c1-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="755c1-118">Het primaire verschil tussen actieve en gesloten zaken is dat deze zijn uitgeschakeld wanneer een zaak wordt gesloten.</span><span class="sxs-lookup"><span data-stu-id="755c1-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="755c1-119">Een zaak sluiten:</span><span class="sxs-lookup"><span data-stu-id="755c1-119">To close a case:</span></span>

1. <span data-ttu-id="755c1-120">Selecteer op **Advanced eDiscovery** pagina de zaak die u wilt sluiten.</span><span class="sxs-lookup"><span data-stu-id="755c1-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="755c1-121">Klik op **Instellingen** tabblad Onder **Hoofdgegevens** op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="755c1-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="755c1-122">Klik **op Zaak sluiten**.</span><span class="sxs-lookup"><span data-stu-id="755c1-122">Click **Close case**.</span></span>

   <span data-ttu-id="755c1-123">Het kan tot 60 minuten duren voordat het sluitingsproces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="755c1-123">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="755c1-124">Een gesloten zaak opnieuw openen</span><span class="sxs-lookup"><span data-stu-id="755c1-124">Reopen a closed case</span></span>

<span data-ttu-id="755c1-125">Wanneer u een Advanced eDiscovery opnieuw opent, worden alle opgeslagen e-Advanced eDiscovery die waren ingesteld toen de zaak werd gesloten, niet automatisch opnieuw hersteld.</span><span class="sxs-lookup"><span data-stu-id="755c1-125">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="755c1-126">Nadat de zaak opnieuw is geopend, moet  u naar het tabblad Houdt gaan en de vorige in- en uit te zetten.</span><span class="sxs-lookup"><span data-stu-id="755c1-126">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="755c1-127">Als u een wachtruimte wilt in- of uitschakelen, selecteert u deze om de flyoutpagina weer te geven en stelt u de schakelknop **Status** in op **Aan.**</span><span class="sxs-lookup"><span data-stu-id="755c1-127">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="755c1-128">Een gesloten zaak opnieuw openen:</span><span class="sxs-lookup"><span data-stu-id="755c1-128">To reopen a closed case:</span></span>

1. <span data-ttu-id="755c1-129">Selecteer op **Advanced eDiscovery** pagina de zaak die u opnieuw wilt openen.</span><span class="sxs-lookup"><span data-stu-id="755c1-129">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="755c1-130">Klik op **Instellingen** tabblad Onder **Hoofdgegevens** op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="755c1-130">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="755c1-131">Klik **op Zaak opnieuw openen**.</span><span class="sxs-lookup"><span data-stu-id="755c1-131">Click **Reopen case**.</span></span>

   <span data-ttu-id="755c1-132">Het kan tot 60 minuten duren voordat het heropeningsproces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="755c1-132">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="755c1-133">Een zaak verwijderen</span><span class="sxs-lookup"><span data-stu-id="755c1-133">Delete a case</span></span>

<span data-ttu-id="755c1-134">U kunt zowel actieve als gesloten Advanced eDiscovery verwijderen.</span><span class="sxs-lookup"><span data-stu-id="755c1-134">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="755c1-135">Wanneer u een zaak verwijdert, worden alle onderdelen die aan de zaak zijn gekoppeld, zoals de lijst met bewaarders, communicatie, zoekopdrachten, revisiesets en exportklus, verwijderd.</span><span class="sxs-lookup"><span data-stu-id="755c1-135">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="755c1-136">De zaak wordt verwijderd uit de lijst met zaken op **de** Advanced eDiscovery pagina in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="755c1-136">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="755c1-137">U kunt een verwijderde zaak niet herstellen of opnieuw openen.</span><span class="sxs-lookup"><span data-stu-id="755c1-137">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="755c1-138">In scenario's voor gegevensmortage kunt u alleen items in een revisieset verwijderen door het Advanced eDiscovery verwijderen.</span><span class="sxs-lookup"><span data-stu-id="755c1-138">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="755c1-139">Andere 'zoek- en verwijdermethoden' verwijderen geen items uit een revisieset.</span><span class="sxs-lookup"><span data-stu-id="755c1-139">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="755c1-140">Voordat u een zaak kunt verwijderen (of deze nu  actief of gesloten is), moet u eerst alle aan de zaak gekoppelde items verwijderen.</span><span class="sxs-lookup"><span data-stu-id="755c1-140">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="755c1-141">Dit geldt ook voor het verwijderen van in-standen met de status **Uit.**</span><span class="sxs-lookup"><span data-stu-id="755c1-141">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="755c1-142">Houd in een zaak verwijderen:</span><span class="sxs-lookup"><span data-stu-id="755c1-142">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="755c1-143">Ga naar **het tabblad** Houdt in het Advanced eDiscovery dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="755c1-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="755c1-144">Klik op de wacht die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="755c1-144">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="755c1-145">Klik op de flyoutpagina op **Wacht houden verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="755c1-145">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="755c1-146">Een zaak verwijderen:</span><span class="sxs-lookup"><span data-stu-id="755c1-146">To delete a case:</span></span>

1. <span data-ttu-id="755c1-147">Selecteer op **Advanced eDiscovery** pagina de zaak die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="755c1-147">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="755c1-148">Klik op **Instellingen** tabblad Onder **Hoofdgegevens** op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="755c1-148">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="755c1-149">Klik **op Case verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="755c1-149">Click **Delete case**.</span></span>
