---
title: Toestaan dat leden verzenden als of verzenden namens een groep
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Meer informatie over het toestaan dat groepsleden e-mail verzenden als een Microsoft 365-groep of e-mail verzenden namens een Microsoft 365-groep.
ms.openlocfilehash: 44a0a7a690c8faa9fe00732e8154f36aa5a6fe6f
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727077"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="fae69-103">Toestaan dat leden verzenden als of verzenden namens een groep</span><span class="sxs-lookup"><span data-stu-id="fae69-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="fae69-104">Een lid van een Microsoft 365-groep  die machtigingen voor Verzenden **als** of Namens verzenden heeft gekregen, kan e-mail verzenden als de groep of namens de groep.</span><span class="sxs-lookup"><span data-stu-id="fae69-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="fae69-105">(Gasten in de groep kunnen deze machtigingen niet krijgen.)</span><span class="sxs-lookup"><span data-stu-id="fae69-105">(Guests in the group cannot be granted these permissions.)</span></span>

<span data-ttu-id="fae69-106">In dit artikel wordt uitgelegd hoe een globale of Exchange-beheerder deze machtigingen kan instellen.</span><span class="sxs-lookup"><span data-stu-id="fae69-106">This article explains how a global or Exchange administrator can set these permissions.</span></span>
  
<span data-ttu-id="fae69-107">Als Megan Bowen bijvoorbeeld deel uitmaakt van de **groep** Training  Microsoft 365 en heeft verzenden als machtigingen voor de  groep, lijkt het erop dat de groep Training de e-mail heeft verzonden als ze een e-mailbericht verzendt als de groep.</span><span class="sxs-lookup"><span data-stu-id="fae69-107">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="fae69-108">Met **de machtiging Namens verzenden** kan een gebruiker e-mail verzenden namens een Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="fae69-108">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="fae69-109">Als Alex Wilber bijvoorbeeld deel uitmaakt van de **groep Marketing** Microsoft  365 en machtigingen voor Verzenden namens heeft en een e-mailbericht als de groep verzendt, ziet het eruit alsof het e-mailbericht is verzonden door **Alex Wilber** namens Marketing.</span><span class="sxs-lookup"><span data-stu-id="fae69-109">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fae69-110">U kunt Verzenden **als of** Verzenden namens een bepaalde gebruiker **configureren,** maar niet beide.</span><span class="sxs-lookup"><span data-stu-id="fae69-110">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="fae69-111">Als u beide configureert, wordt deze standaard ingesteld op **Verzenden als**.</span><span class="sxs-lookup"><span data-stu-id="fae69-111">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="fae69-112">Zie [E-mail verzenden vanuit of namens een Microsoft 365-groep](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) voor meer informatie over het gebruik van Outlook en de webversie van Outlook om e-mail te verzenden vanuit een groep.</span><span class="sxs-lookup"><span data-stu-id="fae69-112">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="fae69-113">Toestaan dat leden e-mail verzenden als een groep</span><span class="sxs-lookup"><span data-stu-id="fae69-113">Allow members to send email as a group</span></span>

<span data-ttu-id="fae69-114">In deze sectie wordt uitgelegd hoe gebruikers e-mail kunnen verzenden als een groep in het [Exchange-beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fae69-114">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="fae69-115">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">het Exchange-beheercentrum</a>naar **Geadresseerdengroepen.** \> </span><span class="sxs-lookup"><span data-stu-id="fae69-115">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="fae69-116">Selecteer **Groepspictogram** ![ Bewerken bewerken in de groep die u wilt toestaan dat gebruikers verzenden ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) als.  </span><span class="sxs-lookup"><span data-stu-id="fae69-116">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="fae69-117">Selecteer **delegering van groepen**.</span><span class="sxs-lookup"><span data-stu-id="fae69-117">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="fae69-118">Selecteer in **de sectie Verzenden als** het teken om de gebruikers toe te voegen die u als groep wilt **+** verzenden.</span><span class="sxs-lookup"><span data-stu-id="fae69-118">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Schermafbeelding van het dialoogvenster Verzenden als](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="fae69-120">Typ om te zoeken of kies een gebruiker uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="fae69-120">Type to search or pick a user from the list.</span></span> <span data-ttu-id="fae69-121">Selecteer **OK** en **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="fae69-121">Select **OK** and **Save**.</span></span>
    
    ![Typ om een gebruiker in de lijst te zoeken of te kiezen](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="fae69-123">Leden toestaan e-mail te verzenden namens een groep</span><span class="sxs-lookup"><span data-stu-id="fae69-123">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="fae69-124">In deze sectie wordt uitgelegd hoe gebruikers e-mail kunnen verzenden namens een groep in het Exchange-beheercentrum (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fae69-124">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="fae69-125">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">het Exchange-beheercentrum</a>naar **Geadresseerdengroepen.** \> </span><span class="sxs-lookup"><span data-stu-id="fae69-125">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="fae69-126">Selecteer **Groepspictogram** ![ Bewerken bewerken in de groep die u wilt toestaan dat gebruikers verzenden ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) als.</span><span class="sxs-lookup"><span data-stu-id="fae69-126">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="fae69-127">Selecteer **delegering van groepen**.</span><span class="sxs-lookup"><span data-stu-id="fae69-127">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="fae69-128">Selecteer in de sectie Namens verzenden het teken om de gebruikers toe te voegen **+** die u als groep wilt verzenden.</span><span class="sxs-lookup"><span data-stu-id="fae69-128">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Schermafbeelding van verzenden namens dialoogvenster](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="fae69-130">Typ om te zoeken of kies een gebruiker uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="fae69-130">Type to search or pick a user from the list.</span></span> <span data-ttu-id="fae69-131">Selecteer **OK** en **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="fae69-131">Select **OK** and **Save**.</span></span>
    
    ![Typ om een gebruiker in de lijst te zoeken of te kiezen](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="fae69-133">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="fae69-133">Related articles</span></span>

[<span data-ttu-id="fae69-134">Planning van samenwerkingsbeheer stap voor stap</span><span class="sxs-lookup"><span data-stu-id="fae69-134">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="fae69-135">Uw samenwerkingsbeheerplan maken</span><span class="sxs-lookup"><span data-stu-id="fae69-135">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="fae69-136">Meer informatie over Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="fae69-136">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="fae69-137">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="fae69-137">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="fae69-138">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="fae69-138">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
