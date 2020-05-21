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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Meer informatie over het herstellen van een verwijderde Microsoft 365-groep.
ms.openlocfilehash: 123805750beff88904a8e3874f0d4d46a72e8f01
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327626"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="a140e-103">Een verwijderde groep herstellen</span><span class="sxs-lookup"><span data-stu-id="a140e-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a140e-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="a140e-104">The admin center is changing.</span></span> <span data-ttu-id="a140e-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a140e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="a140e-106">Als u een groep hebt verwijderd, wordt deze standaard 30 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="a140e-106">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="a140e-107">Deze periode van 30 dagen wordt beschouwd als een soft-delete omdat u de groep nog steeds herstellen.</span><span class="sxs-lookup"><span data-stu-id="a140e-107">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="a140e-108">Na 30 dagen worden de groep en de bijbehorende inhoud definitief verwijderd en kunnen ze niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="a140e-108">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="a140e-109">Wanneer een groep wordt hersteld, wordt de volgende inhoud hersteld:</span><span class="sxs-lookup"><span data-stu-id="a140e-109">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="a140e-110">Het object, de eigenschappen en leden van Azure Active Directory (AD) Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="a140e-110">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="a140e-111">de e-mailadressen van de groep.</span><span class="sxs-lookup"><span data-stu-id="a140e-111">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="a140e-112">Exchange Online heeft Postvak IN en agenda gedeeld.</span><span class="sxs-lookup"><span data-stu-id="a140e-112">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="a140e-113">SharePoint Online-teamsite en -bestanden.</span><span class="sxs-lookup"><span data-stu-id="a140e-113">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="a140e-114">OneNote-notitieblok</span><span class="sxs-lookup"><span data-stu-id="a140e-114">OneNote notebook</span></span>
    
- <span data-ttu-id="a140e-115">Planner</span><span class="sxs-lookup"><span data-stu-id="a140e-115">Planner</span></span>
    
- <span data-ttu-id="a140e-116">Teams</span><span class="sxs-lookup"><span data-stu-id="a140e-116">Teams</span></span>

- <span data-ttu-id="a140e-117">Yammer-groep en groepsinhoud (Als de Microsoft 365-groep is gemaakt vanuit Yammer)</span><span class="sxs-lookup"><span data-stu-id="a140e-117">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="a140e-118">Een groep herstellen waarvan u eigenaar bent met Outlook</span><span class="sxs-lookup"><span data-stu-id="a140e-118">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="a140e-119">Als u eigenaar bent van een Microsoft 365-groep, u de groep zelf herstellen in Outlook door de volgende stappen te volgen:</span><span class="sxs-lookup"><span data-stu-id="a140e-119">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="a140e-120">Selecteer op de [pagina verwijderde groepen](https://outlook.office.com/people/group/deleted)de optie Groepen **beheren** onder het knooppunt **Groepen** en kies **Vervolgens Verwijderd**.</span><span class="sxs-lookup"><span data-stu-id="a140e-120">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="a140e-121">Klik op het tabblad **Herstellen** naast de groep die u wilt herstellen.</span><span class="sxs-lookup"><span data-stu-id="a140e-121">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="a140e-122">Als de verwijderde groep hier niet wordt weergegeven, neemt u contact op met een beheerder.</span><span class="sxs-lookup"><span data-stu-id="a140e-122">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a140e-123">Een groep herstellen in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="a140e-123">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="a140e-124">Als u een globale beheerder of een groepsbeheerder bent, u een verwijderde groep herstellen in het Microsoft 365-beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="a140e-124">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="a140e-125">Ga naar het [beheercentrum](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a140e-125">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="a140e-126">Groepen **Groups**uitvouwen en vervolgens op **Verwijderde groepen**klikken .</span><span class="sxs-lookup"><span data-stu-id="a140e-126">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="a140e-127">Selecteer de groep die u wilt herstellen en klik op **Groep herstellen**.</span><span class="sxs-lookup"><span data-stu-id="a140e-127">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="a140e-128">In sommige gevallen kan het zo lang duren voordat de groep en al haar gegevens zijn hersteld.</span><span class="sxs-lookup"><span data-stu-id="a140e-128">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="a140e-129">Een Microsoft 365-groep definitief verwijderen</span><span class="sxs-lookup"><span data-stu-id="a140e-129">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="a140e-130">Soms wilt u een groep permanent zuiveren zonder te wachten tot de periode voor het verwijderen van 30 dagen is verlopen.</span><span class="sxs-lookup"><span data-stu-id="a140e-130">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="a140e-131">Hiervoor start u PowerShell en voert u deze opdracht uit om de object-id van de groep op te vragen:</span><span class="sxs-lookup"><span data-stu-id="a140e-131">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="a140e-132">Let op de object-id van de groep of groepen die u permanent wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a140e-132">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a140e-133">Als u een groep permanent verwijdert, kunnen de groep en de bijbehorende gegevens niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="a140e-133">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="a140e-134">Voer deze opdracht uit in PowerShell om de groep permanent te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="a140e-134">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="a140e-p104">U kunt controleren dat de groep definitief is verwijderd door de cmdlet  *Get-AzureADMSDeletedGroup*  opnieuw uit te voeren en te kijken of de groep niet meer wordt vermeld in de lijst met voorlopig verwijderde groepen. In sommige gevallen duurt het wel 24 uur voordat de groep en alle bijbehorende gegevens permanent zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a140e-p104">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="a140e-137">Heb je vragen over Microsoft 365-groepen?</span><span class="sxs-lookup"><span data-stu-id="a140e-137">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="a140e-138">Ga naar de [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) om vragen te plaatsen en deel te nemen aan gesprekken over Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="a140e-138">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="a140e-139">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="a140e-139">Related articles</span></span>

[<span data-ttu-id="a140e-140">Microsoft 365-groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="a140e-140">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
<span data-ttu-id="a140e-141">[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx) (Groepen verwijderen met de cmdlet Remove-UnifiedGroup)</span><span class="sxs-lookup"><span data-stu-id="a140e-141">[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)</span></span>
  
[<span data-ttu-id="a140e-142">De teamsite-instellingen beheren die aan de groep zijn gekoppeld</span><span class="sxs-lookup"><span data-stu-id="a140e-142">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="a140e-143">Een groep verwijderen in Outlook</span><span class="sxs-lookup"><span data-stu-id="a140e-143">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
