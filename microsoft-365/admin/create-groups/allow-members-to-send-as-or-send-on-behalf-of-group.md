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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Meer informatie over het toestaan van leden om e-mail te verzenden als Microsoft 365-groep of e-mail te verzenden namens een Microsoft 365-groep.
ms.openlocfilehash: 3a93dda83b10d7c38c8c6e7d8fd484b37df565d0
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780467"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="99294-103">Leden toestaan om namens een groep te verzenden of te verzenden</span><span class="sxs-lookup"><span data-stu-id="99294-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="99294-104">Een lid van een Microsoft 365-groep die namens machtigingen **verzenden of** **verzenden** heeft gekregen, kan e-mail verzenden als groep of namens de groep.</span><span class="sxs-lookup"><span data-stu-id="99294-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="99294-105">In dit onderwerp wordt uitgelegd hoe een beheerder deze machtigingen kan instellen.</span><span class="sxs-lookup"><span data-stu-id="99294-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="99294-106">Als Megan Bowen bijvoorbeeld deel uitmaakt van de Microsoft 365-groep **Training** en **als** machtigingen voor de groep heeft verzonden, lijkt het erop dat de **groep Training** de e-mail heeft verzonden als ze een e-mail stuurt als de groep.</span><span class="sxs-lookup"><span data-stu-id="99294-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="99294-107">Met de machtiging **Verzenden namens naam** kan een gebruiker e-mail verzenden namens een Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="99294-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="99294-108">Als Alex Wilber bijvoorbeeld deel uitmaakt van de **Marketing** Microsoft 365-groep en **machtigingen namens verzenden** heeft en een e-mail als groep verzendt, ziet de e-mail eruit alsof deze is verzonden door Alex **Wilber namens Marketing.**</span><span class="sxs-lookup"><span data-stu-id="99294-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99294-109">U **Verzenden als** of Verzenden **namens** een bepaalde gebruiker configureren, maar niet beide.</span><span class="sxs-lookup"><span data-stu-id="99294-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="99294-110">Als u beide configureert, wordt deze standaard **verzonden als**.</span><span class="sxs-lookup"><span data-stu-id="99294-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="99294-111">Zie [E-mail verzenden vanuit of namens een Microsoft 365-groep](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) voor meer informatie over het gebruik van Outlook en Outlook op internet om e-mail vanuit een groep te verzenden.</span><span class="sxs-lookup"><span data-stu-id="99294-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="99294-112">Leden toestaan om e-mail als groep te verzenden</span><span class="sxs-lookup"><span data-stu-id="99294-112">Allow members to send email as a group</span></span>

<span data-ttu-id="99294-113">In deze sectie wordt uitgelegd hoe gebruikers e-mail als groep kunnen verzenden in het [Exchange-beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="99294-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="99294-114">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>naar **Groepen ontvangers** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="99294-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="99294-115">Selecteer **Het** ![ groeppictogram Bewerken bewerken in groep dat gebruikers ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) als of te sturen wilt toestaan.  </span><span class="sxs-lookup"><span data-stu-id="99294-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="99294-116">Selecteer **delegering van groepen**.</span><span class="sxs-lookup"><span data-stu-id="99294-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="99294-117">Selecteer **in** de sectie Verzenden als het **+** teken om de gebruikers toe te voegen die u als groep wilt verzenden.</span><span class="sxs-lookup"><span data-stu-id="99294-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Selecteer het plusteken om de gebruikers toe te voegen die u als Microsoft 365-groep wilt verzenden](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="99294-119">Typ om te zoeken of kies een gebruiker uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="99294-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="99294-120">Selecteer **OK** en **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="99294-120">Select **OK** and **Save**.</span></span>
    
    ![Typ om een gebruiker uit de lijst te zoeken of te kiezen](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="99294-122">Leden toestaan om namens een groep e-mail te verzenden</span><span class="sxs-lookup"><span data-stu-id="99294-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="99294-123">In deze sectie wordt uitgelegd hoe gebruikers e-mail namens een groep kunnen verzenden in het Exchange-beheercentrum (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="99294-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="99294-124">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>naar **Groepen ontvangers** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="99294-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="99294-125">Selecteer **Het** ![ groeppictogram Bewerken bewerken in de groep die ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) gebruikers als of te sturen wilt toestaan.</span><span class="sxs-lookup"><span data-stu-id="99294-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="99294-126">Selecteer **delegering van groepen**.</span><span class="sxs-lookup"><span data-stu-id="99294-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="99294-127">Selecteer in de sectie Verzenden namens naam het **+** teken om de gebruikers toe te voegen die u als groep wilt verzenden.</span><span class="sxs-lookup"><span data-stu-id="99294-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Selecteer het plusteken om de gebruikers toe te voegen die u als Microsoft 365-groep wilt verzenden](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="99294-129">Typ om te zoeken of kies een gebruiker uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="99294-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="99294-130">Selecteer **OK** en **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="99294-130">Select **OK** and **Save**.</span></span>
    
    ![Typ om een gebruiker uit de lijst te zoeken of te kiezen](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="99294-132">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="99294-132">Related articles</span></span>

[<span data-ttu-id="99294-133">Meer informatie over Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="99294-133">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="99294-134">Bijvoegtoepassing Permissie</span><span class="sxs-lookup"><span data-stu-id="99294-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="99294-135">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="99294-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
