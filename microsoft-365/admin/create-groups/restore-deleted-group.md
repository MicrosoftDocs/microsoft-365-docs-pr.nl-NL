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
description: Meer informatie over het herstellen van een verwijderde Microsoft 365-groep.
ms.openlocfilehash: d7cf548816af1661298458f27c704d654845075d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818505"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="f7f51-103">Een verwijderde groep herstellen</span><span class="sxs-lookup"><span data-stu-id="f7f51-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f7f51-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="f7f51-104">The admin center is changing.</span></span> <span data-ttu-id="f7f51-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="f7f51-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="f7f51-106">Als u een groep hebt verwijderd, wordt deze standaard 30 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="f7f51-106">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="f7f51-107">Deze periode van 30 dagen wordt beschouwd als een soft-delete, omdat u de groep nog steeds herstellen.</span><span class="sxs-lookup"><span data-stu-id="f7f51-107">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="f7f51-108">Na 30 dagen worden de groep en de bijbehorende inhoud permanent verwijderd en kunnen ze niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="f7f51-108">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="f7f51-109">Wanneer een groep wordt hersteld, wordt de volgende inhoud hersteld:</span><span class="sxs-lookup"><span data-stu-id="f7f51-109">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="f7f51-110">Azure Active Directory (AD) Microsoft 365 Groepen object, eigenschappen en leden.</span><span class="sxs-lookup"><span data-stu-id="f7f51-110">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="f7f51-111">e-mailadressen van de groep.</span><span class="sxs-lookup"><span data-stu-id="f7f51-111">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="f7f51-112">Exchange Online heeft Inbox en agenda gedeeld.</span><span class="sxs-lookup"><span data-stu-id="f7f51-112">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="f7f51-113">SharePoint Online-teamsite en -bestanden.</span><span class="sxs-lookup"><span data-stu-id="f7f51-113">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="f7f51-114">OneNote-notitieblok</span><span class="sxs-lookup"><span data-stu-id="f7f51-114">OneNote notebook</span></span>
    
- <span data-ttu-id="f7f51-115">Planner</span><span class="sxs-lookup"><span data-stu-id="f7f51-115">Planner</span></span>
    
- <span data-ttu-id="f7f51-116">Teams</span><span class="sxs-lookup"><span data-stu-id="f7f51-116">Teams</span></span>

- <span data-ttu-id="f7f51-117">Yammer-groeps- en groepsinhoud (Als de Microsoft 365-groep is gemaakt vanuit Yammer)</span><span class="sxs-lookup"><span data-stu-id="f7f51-117">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a><span data-ttu-id="f7f51-118">Een groep herstellen die u bezit met de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="f7f51-118">Restore a group that you own by using Outlook on the web</span></span>

<span data-ttu-id="f7f51-119">Als u de eigenaar bent van een Microsoft 365-groep, u de groep zelf herstellen in de webversie van Outlook door de volgende stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="f7f51-119">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="f7f51-120">Selecteer op de [pagina Verwijderde groepen](https://outlook.office.com/people/group/deleted)de optie **Groepen beheren** onder het knooppunt **Groepen** en kies **Vervolgens Verwijderd**.</span><span class="sxs-lookup"><span data-stu-id="f7f51-120">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="f7f51-121">Klik op het tabblad **Herstellen** naast de groep die u wilt herstellen.</span><span class="sxs-lookup"><span data-stu-id="f7f51-121">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="f7f51-122">Als de verwijderde groep hier niet wordt weergegeven, neemt u contact op met een beheerder.</span><span class="sxs-lookup"><span data-stu-id="f7f51-122">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f7f51-123">Een groep herstellen in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="f7f51-123">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="f7f51-124">Als u een globale beheerder of een groepsbeheerder bent, u een verwijderde groep herstellen in het Microsoft 365-beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="f7f51-124">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="f7f51-125">Ga naar het [beheercentrum](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f7f51-125">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="f7f51-126">Groepen **Groups**uitvouwen en klik vervolgens op **Verwijderde groepen**.</span><span class="sxs-lookup"><span data-stu-id="f7f51-126">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="f7f51-127">Selecteer de groep die u wilt herstellen en klik op **Groep herstellen**.</span><span class="sxs-lookup"><span data-stu-id="f7f51-127">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="f7f51-128">In sommige gevallen kan het 24 uur duren voordat de groep en al haar gegevens worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="f7f51-128">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="f7f51-129">Een Microsoft 365-groep permanent verwijderen</span><span class="sxs-lookup"><span data-stu-id="f7f51-129">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="f7f51-130">Soms wilt u een groep permanent zuiveren zonder te wachten tot de 30-dagen wachttijd voor het verwijderen van zachte verwijdering is verlopen.</span><span class="sxs-lookup"><span data-stu-id="f7f51-130">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="f7f51-131">Hiervoor start u PowerShell en voert u deze opdracht uit om de object-id van de groep op te vragen:</span><span class="sxs-lookup"><span data-stu-id="f7f51-131">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="f7f51-132">Let op de object-id van de groep of groepen die u permanent wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f7f51-132">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f7f51-133">Als u een groep permanent verwijdert, kunnen de groep en de bijbehorende gegevens niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="f7f51-133">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="f7f51-134">Voer deze opdracht uit in PowerShell om de groep permanent te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="f7f51-134">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="f7f51-p104">U kunt controleren dat de groep definitief is verwijderd door de cmdlet  *Get-AzureADMSDeletedGroup*  opnieuw uit te voeren en te kijken of de groep niet meer wordt vermeld in de lijst met voorlopig verwijderde groepen. In sommige gevallen duurt het wel 24 uur voordat de groep en alle bijbehorende gegevens permanent zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f7f51-p104">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="f7f51-137">Heeft u vragen over Microsoft 365-groepen?</span><span class="sxs-lookup"><span data-stu-id="f7f51-137">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="f7f51-138">Ga naar de [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) om vragen te plaatsen en deel te nemen aan gesprekken over Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="f7f51-138">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="f7f51-139">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="f7f51-139">Related articles</span></span>

[<span data-ttu-id="f7f51-140">Microsoft 365-groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7f51-140">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
<span data-ttu-id="f7f51-141">[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx) (Groepen verwijderen met de cmdlet Remove-UnifiedGroup)</span><span class="sxs-lookup"><span data-stu-id="f7f51-141">[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)</span></span>
  
[<span data-ttu-id="f7f51-142">De teamsite-instellingen beheren die aan de groep zijn gekoppeld</span><span class="sxs-lookup"><span data-stu-id="f7f51-142">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="f7f51-143">Een groep verwijderen in Outlook</span><span class="sxs-lookup"><span data-stu-id="f7f51-143">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
