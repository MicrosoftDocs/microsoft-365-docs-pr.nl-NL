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
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657637"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="77fd1-103">Een Advanced eDiscovery sluiten of verwijderen</span><span class="sxs-lookup"><span data-stu-id="77fd1-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="77fd1-104">Wanneer de juridische zaak of het onderzoek dat wordt ondersteund door een Advanced eDiscovery is voltooid, kunt u een zaak sluiten of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="77fd1-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="77fd1-105">U kunt ook een gesloten zaak opnieuw openen.</span><span class="sxs-lookup"><span data-stu-id="77fd1-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="77fd1-106">Een zaak sluiten</span><span class="sxs-lookup"><span data-stu-id="77fd1-106">Close a case</span></span>

<span data-ttu-id="77fd1-107">Dit gebeurt er als u een Advanced eDiscovery sluit:</span><span class="sxs-lookup"><span data-stu-id="77fd1-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="77fd1-108">Als de zaak inhoudslocaties bevat die in de wacht staan, worden deze in de wacht gezet.</span><span class="sxs-lookup"><span data-stu-id="77fd1-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="77fd1-109">Nadat de wachtstand is uitgeschakeld, wordt een respijtperiode van 30 dagen (een zogenaamde *vertragingstermijn)* toegepast op inhoudslocaties die in de wachtstand stonden.</span><span class="sxs-lookup"><span data-stu-id="77fd1-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="77fd1-110">Dit helpt voorkomen dat inhoud onmiddellijk wordt verwijderd en geeft beheerders de mogelijkheid om inhoud te zoeken of te herstellen die definitief wordt verwijderd nadat de vertragingsperiode is verstreken.</span><span class="sxs-lookup"><span data-stu-id="77fd1-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="77fd1-111">Zie Inhoudslocaties verwijderen uit een [eDiscovery-hold voor meer informatie.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="77fd1-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="77fd1-112">Als u een zaak sluit, worden alleen de aan die zaak gekoppelde insluiten uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="77fd1-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="77fd1-113">Als andere ingehouden eDiscovery's op een inhoudslocatie (zoals een procesovergang, core eDiscovery-bezit of een andere Advanced eDiscovery-zaak) worden bewaard, blijven deze in stand.</span><span class="sxs-lookup"><span data-stu-id="77fd1-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="77fd1-114">De zaak wordt nog steeds weergegeven op de eDiscovery-pagina in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="77fd1-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="77fd1-115">De details, bewaart, zoekt en leden van een gesloten zaak blijven behouden.</span><span class="sxs-lookup"><span data-stu-id="77fd1-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="77fd1-116">U kunt een zaak bewerken nadat deze is gesloten.</span><span class="sxs-lookup"><span data-stu-id="77fd1-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="77fd1-117">U kunt bijvoorbeeld leden toevoegen of verwijderen, zoekopdrachten maken, zoekresultaten exporteren en zoekresultaten voorbereiden voor analyse in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="77fd1-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="77fd1-118">Het primaire verschil tussen actieve en gesloten zaken is dat deze zijn uitgeschakeld wanneer een zaak wordt gesloten.</span><span class="sxs-lookup"><span data-stu-id="77fd1-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="77fd1-119">Een zaak sluiten:</span><span class="sxs-lookup"><span data-stu-id="77fd1-119">To close a case:</span></span>

1. <span data-ttu-id="77fd1-120">Selecteer op **Advanced eDiscovery** pagina de zaak die u wilt sluiten.</span><span class="sxs-lookup"><span data-stu-id="77fd1-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="77fd1-121">Klik op **Instellingen** tabblad Onder **Hoofdgegevens** op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="77fd1-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="77fd1-122">Klik onder aan de **flyoutpagina Hoofdgegevens** op (**...**) **Meer opties** en klik vervolgens op **Zaak sluiten.**</span><span class="sxs-lookup"><span data-stu-id="77fd1-122">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Close case**.</span></span>

   ![Optie in het menu Meer opties om een Advanced eDiscovery sluiten](..\Media\CloseAdvancedeDiscoveryCase.png)

   <span data-ttu-id="77fd1-124">Het kan tot 60 minuten duren voordat het sluitingsproces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="77fd1-124">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="77fd1-125">Een gesloten zaak opnieuw openen</span><span class="sxs-lookup"><span data-stu-id="77fd1-125">Reopen a closed case</span></span>

<span data-ttu-id="77fd1-126">Wanneer u een Advanced eDiscovery opnieuw opent, worden alle opgeslagen e-Advanced eDiscovery die waren ingesteld toen de zaak werd gesloten, niet automatisch opnieuw hersteld.</span><span class="sxs-lookup"><span data-stu-id="77fd1-126">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="77fd1-127">Nadat de zaak opnieuw is geopend, moet  u naar het tabblad Houdt gaan en de vorige in- en uit te zetten.</span><span class="sxs-lookup"><span data-stu-id="77fd1-127">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="77fd1-128">Als u een wachtruimte wilt in- of uitschakelen, selecteert u deze om de flyoutpagina weer te geven en stelt u de schakelknop **Status** in op **Aan.**</span><span class="sxs-lookup"><span data-stu-id="77fd1-128">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="77fd1-129">Een gesloten zaak opnieuw openen:</span><span class="sxs-lookup"><span data-stu-id="77fd1-129">To reopen a closed case:</span></span>

1. <span data-ttu-id="77fd1-130">Selecteer op **Advanced eDiscovery** pagina de zaak die u opnieuw wilt openen.</span><span class="sxs-lookup"><span data-stu-id="77fd1-130">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="77fd1-131">Klik op **Instellingen** tabblad Onder **Hoofdgegevens** op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="77fd1-131">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="77fd1-132">Klik onder aan de **flyoutpagina Hoofdgegevens** op (**...**) **Meer opties** en klik vervolgens op **Zaak opnieuw openen.**</span><span class="sxs-lookup"><span data-stu-id="77fd1-132">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Reopen case**.</span></span>

   ![Optie in het menu Meer opties om een nieuwe Advanced eDiscovery openen](..\Media\ReopenAdvancedeDiscoveryCase.png)

   <span data-ttu-id="77fd1-134">Het kan tot 60 minuten duren voordat het heropeningsproces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="77fd1-134">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="77fd1-135">Een zaak verwijderen</span><span class="sxs-lookup"><span data-stu-id="77fd1-135">Delete a case</span></span>

<span data-ttu-id="77fd1-136">U kunt zowel actieve als gesloten Advanced eDiscovery verwijderen.</span><span class="sxs-lookup"><span data-stu-id="77fd1-136">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="77fd1-137">Wanneer u een zaak verwijdert, worden alle onderdelen die aan de zaak zijn gekoppeld, zoals de lijst met bewaarders, communicatie, zoekopdrachten, revisiesets en exportklus, verwijderd.</span><span class="sxs-lookup"><span data-stu-id="77fd1-137">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="77fd1-138">De zaak wordt verwijderd uit de lijst met zaken op **de** Advanced eDiscovery pagina in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="77fd1-138">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="77fd1-139">U kunt een verwijderde zaak niet herstellen of opnieuw openen.</span><span class="sxs-lookup"><span data-stu-id="77fd1-139">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="77fd1-140">In scenario's voor gegevensmortage kunt u alleen items in een revisieset verwijderen door het Advanced eDiscovery verwijderen.</span><span class="sxs-lookup"><span data-stu-id="77fd1-140">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="77fd1-141">Andere 'zoek- en verwijdermethoden' verwijderen geen items uit een revisieset.</span><span class="sxs-lookup"><span data-stu-id="77fd1-141">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="77fd1-142">Voordat u een zaak kunt verwijderen (of deze nu  actief of gesloten is), moet u eerst alle aan de zaak gekoppelde items verwijderen.</span><span class="sxs-lookup"><span data-stu-id="77fd1-142">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="77fd1-143">Dit geldt ook voor het verwijderen van in-standen met de status **Uit.**</span><span class="sxs-lookup"><span data-stu-id="77fd1-143">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="77fd1-144">Houd in een zaak verwijderen:</span><span class="sxs-lookup"><span data-stu-id="77fd1-144">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="77fd1-145">Ga naar **het tabblad** Houdt in het Advanced eDiscovery dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="77fd1-145">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="77fd1-146">Klik op de wacht die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="77fd1-146">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="77fd1-147">Klik op de flyoutpagina op **Wacht houden verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="77fd1-147">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="77fd1-148">Een zaak verwijderen:</span><span class="sxs-lookup"><span data-stu-id="77fd1-148">To delete a case:</span></span>

1. <span data-ttu-id="77fd1-149">Selecteer op **Advanced eDiscovery** pagina de zaak die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="77fd1-149">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="77fd1-150">Klik op **Instellingen** tabblad Onder **Hoofdgegevens** op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="77fd1-150">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="77fd1-151">Klik onder aan de **flyoutpagina Hoofdgegevens** op (**...**) **Meer opties** en klik vervolgens op **Case verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="77fd1-151">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Delete case**.</span></span>

   ![Optie in het menu Meer opties om een Advanced eDiscovery verwijderen](..\Media\DeleteAdvancedeDiscoveryCase.png)
