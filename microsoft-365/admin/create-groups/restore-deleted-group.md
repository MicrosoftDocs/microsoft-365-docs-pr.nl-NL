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
description: Lees hoe u een verwijderde Microsoft 365-groep kunt herstellen.
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753241"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="d97e6-103">Een verwijderde Microsoft 365-groep herstellen</span><span class="sxs-lookup"><span data-stu-id="d97e6-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="d97e6-104">Als u een groep hebt verwijderd, wordt deze standaard 30 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="d97e6-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="d97e6-105">Deze periode van 30 dagen wordt als ' zacht verwijderen ' beschouwd omdat u de groep toch kunt herstellen.</span><span class="sxs-lookup"><span data-stu-id="d97e6-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="d97e6-106">Na 30 dagen worden de groep en de bijbehorende inhoud permanent verwijderd en kunnen ze niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="d97e6-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="d97e6-107">Wanneer een groep wordt hersteld, wordt de volgende inhoud hersteld:</span><span class="sxs-lookup"><span data-stu-id="d97e6-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="d97e6-108">Objecten, eigenschappen en leden van Azure Active Directory (AD) Microsoft 365 groepen.</span><span class="sxs-lookup"><span data-stu-id="d97e6-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="d97e6-109">De e-mailadressen van de groep.</span><span class="sxs-lookup"><span data-stu-id="d97e6-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="d97e6-110">Gedeeld postvak in en agenda van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d97e6-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="d97e6-111">Team site en bestanden van SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d97e6-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="d97e6-112">OneNote-notitieblok</span><span class="sxs-lookup"><span data-stu-id="d97e6-112">OneNote notebook</span></span>
    
- <span data-ttu-id="d97e6-113">Planner</span><span class="sxs-lookup"><span data-stu-id="d97e6-113">Planner</span></span>
    
- <span data-ttu-id="d97e6-114">Teams</span><span class="sxs-lookup"><span data-stu-id="d97e6-114">Teams</span></span>

- <span data-ttu-id="d97e6-115">Inhoud van Yammer-groepen en-groepen (als de groep Microsoft 365 is gemaakt van Yammer)</span><span class="sxs-lookup"><span data-stu-id="d97e6-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="d97e6-116">In dit artikel wordt beschreven hoe u alleen Microsoft 365 groepen herstelt.</span><span class="sxs-lookup"><span data-stu-id="d97e6-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="d97e6-117">Alle overige groepen kunnen na verwijdering niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="d97e6-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="d97e6-118">Een groep herstellen</span><span class="sxs-lookup"><span data-stu-id="d97e6-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="d97e6-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="d97e6-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="d97e6-120">Als u de eigenaar bent van een Microsoft 365-groep, kunt u de groep zelf herstellen in de webversie van Outlook door de volgende stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="d97e6-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="d97e6-121">Selecteer op de [pagina verwijderde groepen](https://outlook.office.com/people/group/deleted)de optie **groepen beheren** onder het knooppunt **groepen** en kies vervolgens **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="d97e6-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="d97e6-122">Klik op het tabblad **herstellen** naast de groep die u wilt herstellen.</span><span class="sxs-lookup"><span data-stu-id="d97e6-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="d97e6-123">Neem contact op met een beheerder als de verwijderde groep hier niet wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d97e6-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="d97e6-124">Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="d97e6-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="d97e6-125">Als u een globale beheerder of een groepsbeheerder bent, kunt u een verwijderde groep herstellen in het Microsoft 365-Beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="d97e6-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="d97e6-126">Ga naar het [Beheercentrum](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d97e6-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="d97e6-127">Vouw **groepen**uit en klik vervolgens op **Verwijderde groepen**.</span><span class="sxs-lookup"><span data-stu-id="d97e6-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="d97e6-128">Selecteer de groep die u wilt herstellen en klik op **groep herstellen**.</span><span class="sxs-lookup"><span data-stu-id="d97e6-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="d97e6-129">In sommige gevallen kan het tot 24 uur duren voordat de groepsgegevens worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="d97e6-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="d97e6-130">Hebt u vragen over Microsoft 365-groepen?</span><span class="sxs-lookup"><span data-stu-id="d97e6-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="d97e6-131">Bezoek de [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) voor het plaatsen van vragen en deelnemen aan gesprekken over microsoft 365 groepen.</span><span class="sxs-lookup"><span data-stu-id="d97e6-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="d97e6-132">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="d97e6-132">Related articles</span></span>

[<span data-ttu-id="d97e6-133">Microsoft 365-groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d97e6-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
<span data-ttu-id="d97e6-134">[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx) (Groepen verwijderen met de cmdlet Remove-UnifiedGroup)</span><span class="sxs-lookup"><span data-stu-id="d97e6-134">[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)</span></span>
  
[<span data-ttu-id="d97e6-135">De teamsite-instellingen beheren die aan de groep zijn gekoppeld</span><span class="sxs-lookup"><span data-stu-id="d97e6-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="d97e6-136">Een groep verwijderen in Outlook</span><span class="sxs-lookup"><span data-stu-id="d97e6-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
