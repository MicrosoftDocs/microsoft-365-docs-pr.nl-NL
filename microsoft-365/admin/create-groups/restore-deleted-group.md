---
title: Een verwijderde Microsoft 365-groep herstellen
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910544"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="d4bd4-103">Een verwijderde Microsoft 365-groep herstellen</span><span class="sxs-lookup"><span data-stu-id="d4bd4-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="d4bd4-104">Als u een groep hebt verwijderd, wordt deze standaard 30 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="d4bd4-105">Deze periode van 30 dagen wordt beschouwd als een 'soft-delete' omdat u de groep nog steeds kunt herstellen.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="d4bd4-106">Na 30 dagen worden de groep en de bijbehorende inhoud definitief verwijderd en kan deze niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="d4bd4-107">Wanneer een groep wordt hersteld, wordt de volgende inhoud hersteld:</span><span class="sxs-lookup"><span data-stu-id="d4bd4-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="d4bd4-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="d4bd4-109">E-mailadressen van de groep.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="d4bd4-110">Exchange Online heeft postvak IN en agenda gedeeld.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="d4bd4-111">SharePoint Online-teamsite en bestanden.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="d4bd4-112">OneNote-notitieblok</span><span class="sxs-lookup"><span data-stu-id="d4bd4-112">OneNote notebook</span></span>
    
- <span data-ttu-id="d4bd4-113">Planner</span><span class="sxs-lookup"><span data-stu-id="d4bd4-113">Planner</span></span>
    
- <span data-ttu-id="d4bd4-114">Teams</span><span class="sxs-lookup"><span data-stu-id="d4bd4-114">Teams</span></span>

- <span data-ttu-id="d4bd4-115">Yammer-groeps- en groepsinhoud (Als de Microsoft 365-groep is gemaakt vanuit Yammer)</span><span class="sxs-lookup"><span data-stu-id="d4bd4-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="d4bd4-116">In dit artikel wordt beschreven hoe u alleen Microsoft 365-groepen kunt herstellen.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="d4bd4-117">Alle andere groepen kunnen niet worden hersteld nadat ze zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="d4bd4-118">Een groep herstellen</span><span class="sxs-lookup"><span data-stu-id="d4bd4-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="d4bd4-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="d4bd4-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="d4bd4-120">Als u de eigenaar bent van een Microsoft 365-groep, kunt u de groep zelf herstellen in de webversie van Outlook door de volgende stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="d4bd4-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="d4bd4-121">Selecteer op [de pagina Verwijderde](https://outlook.office.com/people/group/deleted)groepen de  optie Groepen **beheren** onder het knooppunt Groepen en kies **vervolgens Verwijderd.**</span><span class="sxs-lookup"><span data-stu-id="d4bd4-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="d4bd4-122">Klik op het **tabblad** Herstellen naast de groep die u wilt herstellen.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="d4bd4-123">Als de verwijderde groep hier niet wordt weergegeven, neemt u contact op met een beheerder.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="d4bd4-124">Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="d4bd4-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="d4bd4-125">Als u een globale beheerder of groepsbeheerder bent, kunt u een verwijderde groep herstellen in het Microsoft 365-beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="d4bd4-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="d4bd4-126">Ga naar het [beheercentrum.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d4bd4-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="d4bd4-127">Vouw **Groepen** uit en klik vervolgens **op Verwijderde groepen.**</span><span class="sxs-lookup"><span data-stu-id="d4bd4-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="d4bd4-128">Selecteer de groep die u wilt herstellen en klik vervolgens op **Groep herstellen.**</span><span class="sxs-lookup"><span data-stu-id="d4bd4-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="d4bd4-129">In sommige gevallen kan het 24 uur duren voordat de groep en alle gegevens zijn hersteld.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="d4bd4-130">Hebt u vragen over Microsoft 365 Groepen?</span><span class="sxs-lookup"><span data-stu-id="d4bd4-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="d4bd4-131">Ga naar [de Microsoft Tech Community om](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) vragen te posten en deel te nemen aan gesprekken over Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="d4bd4-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="d4bd4-132">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="d4bd4-132">Related articles</span></span>

[<span data-ttu-id="d4bd4-133">Microsoft 365-groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4bd4-133">Manage Microsoft 365 Groups with PowerShell</span></span>](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
<span data-ttu-id="d4bd4-134">[Delete groups using the Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (Groepen verwijderen met de cmdlet Remove-UnifiedGroup)</span><span class="sxs-lookup"><span data-stu-id="d4bd4-134">[Delete groups using the Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup)</span></span>
  
[<span data-ttu-id="d4bd4-135">De teamsite-instellingen beheren die aan de groep zijn gekoppeld</span><span class="sxs-lookup"><span data-stu-id="d4bd4-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="d4bd4-136">Een groep verwijderen in Outlook</span><span class="sxs-lookup"><span data-stu-id="d4bd4-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)