---
title: Een verwijderde groep herstellen
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Lees hoe u een verwijderde Microsoft 365-groep kunt herstellen.
ms.openlocfilehash: 30e267a149bc18c2425d4ea38423b887116794c6
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681644"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="c9783-103">Een verwijderde groep herstellen</span><span class="sxs-lookup"><span data-stu-id="c9783-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c9783-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="c9783-104">The admin center is changing.</span></span> <span data-ttu-id="c9783-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c9783-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

> [!NOTE]
> <span data-ttu-id="c9783-106">In dit artikel wordt beschreven hoe u alleen Microsoft 365 groepen herstelt.</span><span class="sxs-lookup"><span data-stu-id="c9783-106">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="c9783-107">Alle overige groepen kunnen na verwijdering niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="c9783-107">All other groups cannot be restored once deleted.</span></span>

<span data-ttu-id="c9783-108">Als u een groep hebt verwijderd, wordt deze standaard 30 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="c9783-108">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="c9783-109">Deze periode van 30 dagen wordt als ' zacht verwijderen ' beschouwd omdat u de groep toch kunt herstellen.</span><span class="sxs-lookup"><span data-stu-id="c9783-109">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="c9783-110">Na 30 dagen worden de groep en de bijbehorende inhoud permanent verwijderd en kunnen ze niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="c9783-110">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="c9783-111">Wanneer een groep wordt hersteld, wordt de volgende inhoud hersteld:</span><span class="sxs-lookup"><span data-stu-id="c9783-111">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="c9783-112">Objecten, eigenschappen en leden van Azure Active Directory (AD) Microsoft 365 groepen.</span><span class="sxs-lookup"><span data-stu-id="c9783-112">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="c9783-113">De e-mailadressen van de groep.</span><span class="sxs-lookup"><span data-stu-id="c9783-113">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="c9783-114">Gedeeld postvak in en agenda van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c9783-114">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="c9783-115">Team site en bestanden van SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c9783-115">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="c9783-116">OneNote-notitieblok</span><span class="sxs-lookup"><span data-stu-id="c9783-116">OneNote notebook</span></span>
    
- <span data-ttu-id="c9783-117">Planner</span><span class="sxs-lookup"><span data-stu-id="c9783-117">Planner</span></span>
    
- <span data-ttu-id="c9783-118">Teams</span><span class="sxs-lookup"><span data-stu-id="c9783-118">Teams</span></span>

- <span data-ttu-id="c9783-119">Inhoud van Yammer-groepen en-groepen (als de groep Microsoft 365 is gemaakt van Yammer)</span><span class="sxs-lookup"><span data-stu-id="c9783-119">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a><span data-ttu-id="c9783-120">Een groep herstellen waarvan u de eigenaar bent met de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="c9783-120">Restore a group that you own by using Outlook on the web</span></span>

<span data-ttu-id="c9783-121">Als u de eigenaar bent van een Microsoft 365-groep, kunt u de groep zelf herstellen in de webversie van Outlook door de volgende stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="c9783-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="c9783-122">Selecteer op de [pagina verwijderde groepen](https://outlook.office.com/people/group/deleted)de optie **groepen beheren** onder het knooppunt **groepen** en kies vervolgens **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="c9783-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="c9783-123">Klik op het tabblad **herstellen** naast de groep die u wilt herstellen.</span><span class="sxs-lookup"><span data-stu-id="c9783-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="c9783-124">Neem contact op met een beheerder als de verwijderde groep hier niet wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c9783-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="c9783-125">Een groep herstellen in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="c9783-125">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="c9783-126">Als u een globale beheerder of een groepsbeheerder bent, kunt u een verwijderde groep herstellen in het Microsoft 365-Beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="c9783-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="c9783-127">Ga naar het [Beheercentrum](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c9783-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="c9783-128">Vouw **groepen**uit en klik vervolgens op **Verwijderde groepen**.</span><span class="sxs-lookup"><span data-stu-id="c9783-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="c9783-129">Selecteer de groep die u wilt herstellen en klik op **groep herstellen**.</span><span class="sxs-lookup"><span data-stu-id="c9783-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="c9783-130">In sommige gevallen kan het tot 24 uur duren voordat de groepsgegevens worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="c9783-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="c9783-131">Een Microsoft 365-groep permanent verwijderen</span><span class="sxs-lookup"><span data-stu-id="c9783-131">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="c9783-132">Het kan soms voorkomen dat u een groep permanent wilt verwijderen zonder te hoeven wachten tot de dertig dagen dat de tijdelijke verwijdering duurt verloopt.</span><span class="sxs-lookup"><span data-stu-id="c9783-132">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="c9783-133">Hiervoor start u PowerShell en voert u deze opdracht uit om de object-id van de groep op te vragen:</span><span class="sxs-lookup"><span data-stu-id="c9783-133">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="c9783-134">Noteer de object-ID van de groep of groepen die u permanent wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="c9783-134">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c9783-135">Als u een groep permanent verwijdert, kunnen de groep en de bijbehorende gegevens niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="c9783-135">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="c9783-136">Voer deze opdracht uit in PowerShell om de groep permanent te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="c9783-136">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="c9783-p105">U kunt controleren dat de groep definitief is verwijderd door de cmdlet  *Get-AzureADMSDeletedGroup*  opnieuw uit te voeren en te kijken of de groep niet meer wordt vermeld in de lijst met voorlopig verwijderde groepen. In sommige gevallen duurt het wel 24 uur voordat de groep en alle bijbehorende gegevens permanent zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c9783-p105">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="c9783-139">Hebt u vragen over Microsoft 365-groepen?</span><span class="sxs-lookup"><span data-stu-id="c9783-139">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="c9783-140">Bezoek de [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) voor het plaatsen van vragen en deelnemen aan gesprekken over microsoft 365 groepen.</span><span class="sxs-lookup"><span data-stu-id="c9783-140">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="c9783-141">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="c9783-141">Related articles</span></span>

[<span data-ttu-id="c9783-142">Microsoft 365-groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9783-142">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
<span data-ttu-id="c9783-143">[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx) (Groepen verwijderen met de cmdlet Remove-UnifiedGroup)</span><span class="sxs-lookup"><span data-stu-id="c9783-143">[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)</span></span>
  
[<span data-ttu-id="c9783-144">De teamsite-instellingen beheren die aan de groep zijn gekoppeld</span><span class="sxs-lookup"><span data-stu-id="c9783-144">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="c9783-145">Een groep verwijderen in Outlook</span><span class="sxs-lookup"><span data-stu-id="c9783-145">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
