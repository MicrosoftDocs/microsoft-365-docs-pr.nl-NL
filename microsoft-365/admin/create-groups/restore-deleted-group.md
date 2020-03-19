---
title: Een verwijderde Office 365-groep herstellen
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
description: Meer informatie over het herstellen van een verwijderde Office 365-groep.
ms.openlocfilehash: 31d6481f87d7da219e042eefa8f004425caee133
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2020
ms.locfileid: "42810288"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="b7588-103">Een verwijderde Office 365-groep herstellen</span><span class="sxs-lookup"><span data-stu-id="b7588-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="b7588-104">Als u een groep hebt verwijderd, blijft deze standaard 30 dagen behouden.</span><span class="sxs-lookup"><span data-stu-id="b7588-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="b7588-105">Deze periode van 30 dagen wordt beschouwd als een soft-delete, omdat u de groep nog steeds herstellen.</span><span class="sxs-lookup"><span data-stu-id="b7588-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="b7588-106">Na 30 dagen worden de groep en de bijbehorende inhoud definitief verwijderd en kunnen deze niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="b7588-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="b7588-107">Wanneer een groep wordt hersteld, wordt de volgende inhoud hersteld:</span><span class="sxs-lookup"><span data-stu-id="b7588-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="b7588-108">Azure Active Directory (AD) Office 365 groepeert object, eigenschappen en leden.</span><span class="sxs-lookup"><span data-stu-id="b7588-108">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="b7588-109">E-mailadressen van de groep.</span><span class="sxs-lookup"><span data-stu-id="b7588-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="b7588-110">Exchange Online heeft Inbox en agenda gedeeld.</span><span class="sxs-lookup"><span data-stu-id="b7588-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="b7588-111">SharePoint Online-teamsite en -bestanden.</span><span class="sxs-lookup"><span data-stu-id="b7588-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="b7588-112">OneNote-notitieblok</span><span class="sxs-lookup"><span data-stu-id="b7588-112">OneNote notebook</span></span>
    
- <span data-ttu-id="b7588-113">Planner</span><span class="sxs-lookup"><span data-stu-id="b7588-113">Planner</span></span>
    
- <span data-ttu-id="b7588-114">Teams</span><span class="sxs-lookup"><span data-stu-id="b7588-114">Teams</span></span>

- <span data-ttu-id="b7588-115">Yammer-groeps- en groepsinhoud (als de Office 365-groep is gemaakt vanuit Yammer)</span><span class="sxs-lookup"><span data-stu-id="b7588-115">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="b7588-116">Een groep herstellen die u bezit met Outlook</span><span class="sxs-lookup"><span data-stu-id="b7588-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="b7588-117">Als u de eigenaar bent van een Office 365-groep, u de groep zelf herstellen in Outlook door de volgende stappen te volgen:</span><span class="sxs-lookup"><span data-stu-id="b7588-117">If you are the owner of an Office 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="b7588-118">Selecteer op de [pagina Verwijderde groepen](https://outlook.office.com/people/group/deleted)de optie Groepen **beheren** onder het knooppunt **Groepen** en kies Vervolgens **Verwijderd**.</span><span class="sxs-lookup"><span data-stu-id="b7588-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="b7588-119">Klik op het tabblad **Herstellen** naast de groep die u wilt herstellen.</span><span class="sxs-lookup"><span data-stu-id="b7588-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="b7588-120">Als de verwijderde groep hier niet wordt weergegeven, neemt u contact op met een beheerder.</span><span class="sxs-lookup"><span data-stu-id="b7588-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b7588-121">Een groep herstellen in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="b7588-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="b7588-122">Als u een globale beheerder of een groepsbeheerder bent, u een verwijderde groep herstellen in het Microsoft 365-beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="b7588-122">If you are a global administrator or a groups admin, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="b7588-123">Ga naar het beheercentrum via [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b7588-123">Go to the admin center at [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="b7588-124">Groepen **Groups**uitvouwen en klik vervolgens op **Verwijderde groepen**.</span><span class="sxs-lookup"><span data-stu-id="b7588-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="b7588-125">Selecteer de groep die u wilt herstellen en klik op **Groep herstellen**.</span><span class="sxs-lookup"><span data-stu-id="b7588-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="b7588-126">Een Office 365-groep permanent verwijderen</span><span class="sxs-lookup"><span data-stu-id="b7588-126">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="b7588-127">Soms wilt u een groep permanent verwijderen zonder te wachten tot de periode van 30 dagen soft-deletion is verstreken.</span><span class="sxs-lookup"><span data-stu-id="b7588-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="b7588-128">Hiervoor start u PowerShell en voert u deze opdracht uit om de object-id van de groep op te vragen:</span><span class="sxs-lookup"><span data-stu-id="b7588-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="b7588-129">Noteer de object-id van de groep of groepen die u permanent wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b7588-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b7588-130">Als u een groep permanent verwijdert, kunnen de groep en de bijbehorende gegevens niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="b7588-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="b7588-131">Voer deze opdracht uit in PowerShell om de groep permanent te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="b7588-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="b7588-p103">U kunt controleren dat de groep definitief is verwijderd door de cmdlet  *Get-AzureADMSDeletedGroup*  opnieuw uit te voeren en te kijken of de groep niet meer wordt vermeld in de lijst met voorlopig verwijderde groepen. In sommige gevallen duurt het wel 24 uur voordat de groep en alle bijbehorende gegevens permanent zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b7588-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="b7588-134">Hebt u vragen over Office 365 Groepen?</span><span class="sxs-lookup"><span data-stu-id="b7588-134">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="b7588-135">Ga naar de [Microsoft Tech-community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) om vragen te plaatsen en deel te nemen aan gesprekken over Office 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="b7588-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="b7588-136">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="b7588-136">Related articles</span></span>

[<span data-ttu-id="b7588-137">Manage Office 365 Groups with PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7588-137">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
<span data-ttu-id="b7588-138">[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx) (Groepen verwijderen met de cmdlet Remove-UnifiedGroup)</span><span class="sxs-lookup"><span data-stu-id="b7588-138">[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)</span></span>
  
[<span data-ttu-id="b7588-139">De teamsite-instellingen beheren die aan de groep zijn gekoppeld</span><span class="sxs-lookup"><span data-stu-id="b7588-139">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="b7588-140">Een groep verwijderen in Outlook</span><span class="sxs-lookup"><span data-stu-id="b7588-140">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
