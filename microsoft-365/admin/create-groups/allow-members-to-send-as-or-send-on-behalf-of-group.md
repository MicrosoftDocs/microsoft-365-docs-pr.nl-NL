---
title: Leden toestaan om namens een groep te verzenden of te verzenden
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Meer informatie over hoe u leden toestaat e-mail te verzenden als een Microsoft 365-groep of e-mail te verzenden namens een Microsoft 365-groep.
ms.openlocfilehash: ce4527321468ee01864177fc1a607fab6a474481
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049385"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="5b653-103">Leden toestaan om namens een groep te verzenden of te verzenden</span><span class="sxs-lookup"><span data-stu-id="5b653-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="5b653-104">Een lid van een Microsoft 365-groep aan wie **machtigingen verzenden als** of verzenden is **verleend,** kan e-mail verzenden als groep of namens de groep.</span><span class="sxs-lookup"><span data-stu-id="5b653-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="5b653-105">In dit onderwerp wordt uitgelegd hoe een beheerder deze machtigingen kan instellen.</span><span class="sxs-lookup"><span data-stu-id="5b653-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="5b653-106">Als Megan Bowen bijvoorbeeld deel uitmaakt van de groep Microsoft 365 **trainen** en **Verzenden als** machtigingen voor de groep heeft, als ze een e-mail stuurt als de groep, lijkt het erop dat de groep **Training** de e-mail heeft verzonden.</span><span class="sxs-lookup"><span data-stu-id="5b653-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="5b653-107">Met de machtiging **Verzenden namens** kan een gebruiker e-mail verzenden namens een Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="5b653-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="5b653-108">Als Alex Wilber bijvoorbeeld deel uitmaakt van de **groep Marketing** Microsoft 365 en machtigingen voor verzenden **namens de** naam heeft en een e-mail als groep verzendt, ziet de e-mail eruit alsof deze is verzonden door **Alex Wilber namens Marketing.**</span><span class="sxs-lookup"><span data-stu-id="5b653-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b653-109">U **Verzenden als** of Verzenden namens **een** bepaalde gebruiker configureren, maar niet beide.</span><span class="sxs-lookup"><span data-stu-id="5b653-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="5b653-110">Als u beide configureert, wordt standaard **verzonden als**.</span><span class="sxs-lookup"><span data-stu-id="5b653-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="5b653-111">Zie [E-mail verzenden van of namens een Microsoft 365-groep](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) voor meer informatie over het gebruik van Outlook en Outlook op internet om e-mail vanuit een groep te verzenden.</span><span class="sxs-lookup"><span data-stu-id="5b653-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="5b653-112">Leden toestaan om e-mail als groep te verzenden</span><span class="sxs-lookup"><span data-stu-id="5b653-112">Allow members to send email as a group</span></span>

<span data-ttu-id="5b653-113">In dit gedeelte wordt uitgelegd hoe u gebruikers toestaat om als groep e-mail te verzenden in het [Exchange-beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5b653-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="5b653-114">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>naar \> **Ontvangersgroepen**. **Recipients**</span><span class="sxs-lookup"><span data-stu-id="5b653-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="5b653-115">Selecteer **Edit**![groepspictogram](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken in Groep waarvan u gebruikers wilt toestaan als te verzenden.  </span><span class="sxs-lookup"><span data-stu-id="5b653-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="5b653-116">Selecteer **delegering van groepen**.</span><span class="sxs-lookup"><span data-stu-id="5b653-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="5b653-117">Selecteer in de sectie **+** Verzenden **als** het teken om de gebruikers toe te voegen die u als groep wilt verzenden.</span><span class="sxs-lookup"><span data-stu-id="5b653-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Selecteer het plusteken om de gebruikers toe te voegen die u wilt verzenden als de Microsoft 365-groep](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="5b653-119">Typ om te zoeken of kies een gebruiker uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="5b653-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="5b653-120">Selecteer **OK** en **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5b653-120">Select **OK** and **Save**.</span></span>
    
    ![Typ om een gebruiker uit de lijst te zoeken of te kiezen](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="5b653-122">Leden toestaan e-mail namens een groep te verzenden</span><span class="sxs-lookup"><span data-stu-id="5b653-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="5b653-123">In dit gedeelte wordt uitgelegd hoe u gebruikers toestaat e-mail namens een groep te verzenden in het Exchange-beheercentrum (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5b653-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="5b653-124">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>naar \> **Ontvangersgroepen**. **Recipients**</span><span class="sxs-lookup"><span data-stu-id="5b653-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="5b653-125">Selecteer **Edit** ![groepspictogram](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken in de groep die gebruikers wilt toestaan te verzenden als.</span><span class="sxs-lookup"><span data-stu-id="5b653-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="5b653-126">Selecteer **delegering van groepen**.</span><span class="sxs-lookup"><span data-stu-id="5b653-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="5b653-127">Selecteer in de sectie Verzenden **+** namens het teken om de gebruikers toe te voegen die u als groep wilt verzenden.</span><span class="sxs-lookup"><span data-stu-id="5b653-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Selecteer het plusteken om de gebruikers toe te voegen die u wilt verzenden als de Microsoft 365-groep](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="5b653-129">Typ om te zoeken of kies een gebruiker uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="5b653-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="5b653-130">Selecteer **OK** en **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5b653-130">Select **OK** and **Save**.</span></span>
    
    ![Typ om een gebruiker uit de lijst te zoeken of te kiezen](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="5b653-132">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="5b653-132">Related articles</span></span>

[<span data-ttu-id="5b653-133">Meer informatie over Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="5b653-133">Learn more about Microsoft 365 groups</span></span>](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="5b653-134">Machtiging voor geadresseerden toevoegen</span><span class="sxs-lookup"><span data-stu-id="5b653-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="5b653-135">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="5b653-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
