---
title: Een verwijderde Microsoft 365 herstellen
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
description: Een verwijderde groep blijft 30 dagen behouden en u kunt de groep nog steeds herstellen. Na 30 dagen worden de groep en de inhoud ervan definitief verwijderd.
ms.openlocfilehash: 2c20c2bd3ce91331e7160132047dbf3ecd79c4b8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635736"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="02311-104">Een verwijderde Microsoft 365 herstellen</span><span class="sxs-lookup"><span data-stu-id="02311-104">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="02311-105">Als u een groep hebt verwijderd, wordt deze standaard 30 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="02311-105">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="02311-106">Deze periode van 30 dagen wordt beschouwd als een 'soft-delete' omdat u de groep nog steeds kunt herstellen.</span><span class="sxs-lookup"><span data-stu-id="02311-106">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="02311-107">Na 30 dagen worden de groep en de bijbehorende inhoud definitief verwijderd en kan deze niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="02311-107">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="02311-108">Wanneer een groep wordt hersteld, wordt de volgende inhoud hersteld:</span><span class="sxs-lookup"><span data-stu-id="02311-108">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="02311-109">Azure Active Directory (AD) Microsoft 365 Groepen object, eigenschappen en leden.</span><span class="sxs-lookup"><span data-stu-id="02311-109">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="02311-110">E-mailadressen van de groep.</span><span class="sxs-lookup"><span data-stu-id="02311-110">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="02311-111">Exchange Online gedeeld Postvak IN en agenda.</span><span class="sxs-lookup"><span data-stu-id="02311-111">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="02311-112">SharePoint Online teamsite en bestanden.</span><span class="sxs-lookup"><span data-stu-id="02311-112">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="02311-113">OneNote-notitieblok</span><span class="sxs-lookup"><span data-stu-id="02311-113">OneNote notebook</span></span>
    
- <span data-ttu-id="02311-114">Planner</span><span class="sxs-lookup"><span data-stu-id="02311-114">Planner</span></span>
    
- <span data-ttu-id="02311-115">Teams</span><span class="sxs-lookup"><span data-stu-id="02311-115">Teams</span></span>

- <span data-ttu-id="02311-116">Yammer groeps- en groepsinhoud (Als de Microsoft 365 groep is gemaakt op Yammer)</span><span class="sxs-lookup"><span data-stu-id="02311-116">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="02311-117">In dit artikel wordt het herstellen van alleen Microsoft 365 beschreven.</span><span class="sxs-lookup"><span data-stu-id="02311-117">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="02311-118">Alle andere groepen kunnen niet worden hersteld nadat ze zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="02311-118">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="02311-119">Een groep herstellen</span><span class="sxs-lookup"><span data-stu-id="02311-119">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="02311-120">Outlook</span><span class="sxs-lookup"><span data-stu-id="02311-120">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="02311-121">Als u de eigenaar bent van een Microsoft 365 groep, kunt u de groep zelf herstellen in Outlook web door de volgende stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="02311-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="02311-122">Selecteer op [de pagina Verwijderde](https://outlook.office.com/people/group/deleted)groepen de  optie Groepen **beheren** onder het knooppunt Groepen en kies **vervolgens Verwijderd.**</span><span class="sxs-lookup"><span data-stu-id="02311-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="02311-123">Klik op het **tabblad** Herstellen naast de groep die u wilt herstellen.</span><span class="sxs-lookup"><span data-stu-id="02311-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="02311-124">Als de verwijderde groep hier niet wordt weergegeven, neemt u contact op met een beheerder.</span><span class="sxs-lookup"><span data-stu-id="02311-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="02311-125">Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="02311-125">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="02311-126">Als u een globale beheerder of een groepsbeheerder bent, kunt u een verwijderde groep herstellen in het Microsoft 365 beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="02311-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="02311-127">Ga naar het [beheercentrum.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="02311-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="02311-128">Vouw **Groepen** uit en klik vervolgens **op Verwijderde groepen.**</span><span class="sxs-lookup"><span data-stu-id="02311-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="02311-129">Selecteer de groep die u wilt herstellen en klik vervolgens op **Groep herstellen.**</span><span class="sxs-lookup"><span data-stu-id="02311-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="02311-130">In sommige gevallen kan het 24 uur duren voordat de groep en alle gegevens zijn hersteld.</span><span class="sxs-lookup"><span data-stu-id="02311-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="02311-131">Hebt u vragen over Microsoft 365 Groepen?</span><span class="sxs-lookup"><span data-stu-id="02311-131">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="02311-132">Ga naar [de Microsoft Tech Community om](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) vragen te posten en deel te nemen aan gesprekken over Microsoft 365 groepen.</span><span class="sxs-lookup"><span data-stu-id="02311-132">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="02311-133">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="02311-133">Related content</span></span>

<span data-ttu-id="02311-134">[Groepen Microsoft 365 beheren met PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="02311-134">[Manage Microsoft 365 Groups with PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (article)</span></span>\
<span data-ttu-id="02311-135">[Groepen verwijderen met de Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (artikel)</span><span class="sxs-lookup"><span data-stu-id="02311-135">[Delete groups using the Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (article)</span></span>\
<span data-ttu-id="02311-136">[Uw teamsite-instellingen met een groep beheren](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (artikel)</span><span class="sxs-lookup"><span data-stu-id="02311-136">[Manage your group-connected team site settings](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (article)</span></span>\
<span data-ttu-id="02311-137">[Een groep verwijderen in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (artikel)</span><span class="sxs-lookup"><span data-stu-id="02311-137">[Delete a group in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (article)</span></span>