---
title: Leden toestaan te verzenden als of te verzenden namens een groep
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
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
description: Meer informatie over het toestaan van leden om e-mail te verzenden als Office 365-groep of e-mail te verzenden namens een Office 365-groep.
ms.openlocfilehash: 0179dbd2e3093ce80929f6c5f9e689aece845a40
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42809218"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="1100a-103">Leden toestaan te verzenden als of te verzenden namens een groep</span><span class="sxs-lookup"><span data-stu-id="1100a-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="1100a-104">Een lid van een Office 365-groep aan wie de machtigingen **Verzenden als** en **Verzenden namens** is verleend, kan nu e-mail verzenden als de groep of namens de groep.</span><span class="sxs-lookup"><span data-stu-id="1100a-104">A member of an Office 365 Group who has been granted **Send as** or **Send on behalf** permissions can now send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="1100a-105">In dit onderwerp wordt uitgelegd hoe een beheerder deze machtigingen kan instellen.</span><span class="sxs-lookup"><span data-stu-id="1100a-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="1100a-106">Als Megan Bowen bijvoorbeeld deel uitmaakt van de **Training** Office 365-groep en **verzenden als** machtigingen voor de groep heeft, ziet het eruit als de trainingsgroep de e-mail heeft verzonden als ze een e-mail stuurt als de groep, als ze een e-mail verzendt, het lijkt erop dat de **trainingsgroep** de e-mail heeft verzonden.</span><span class="sxs-lookup"><span data-stu-id="1100a-106">For example, if Megan Bowen is part of the **Training** Office 365 Group, and has **Send as** permissions on the group, if she sends an email as the Group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="1100a-107">Met de machtiging **Verzenden namens naam** kan een gebruiker e-mail verzenden namens een Office 365-groep.</span><span class="sxs-lookup"><span data-stu-id="1100a-107">The **Send on Behalf** permission lets a user send email on behalf of an Office 365 Group.</span></span> <span data-ttu-id="1100a-108">Als Alex Wilber bijvoorbeeld deel uitmaakt van de **Marketing** Office 365-groep en machtigingen **namens Verzenden** heeft en een e-mail als groep verzendt, lijkt de e-mail namens **Marketing.**</span><span class="sxs-lookup"><span data-stu-id="1100a-108">For example, if Alex Wilber is a part of the **Marketing** Office 365 Group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1100a-109">U **Verzenden als** **verzenden** namens een bepaalde gebruiker configureren, maar niet beide.</span><span class="sxs-lookup"><span data-stu-id="1100a-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="1100a-110">Als u beide configureert, wordt deze standaard **verzonden als**.</span><span class="sxs-lookup"><span data-stu-id="1100a-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="1100a-111">Bekijk de stappen in [E-mail verzenden vanuit of namens een Office 365-groep](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) voor meer informatie over het gebruik van Outlook en Outlook op internet om e-mail vanuit een groep te verzenden.</span><span class="sxs-lookup"><span data-stu-id="1100a-111">Check the out the steps in [Send email from or on behalf of an Office 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from a Group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="1100a-112">Leden toestaan e-mail als groep te verzenden</span><span class="sxs-lookup"><span data-stu-id="1100a-112">Allow members to send email as a Group</span></span>

<span data-ttu-id="1100a-113">In deze sectie wordt uitgelegd hoe gebruikers e-mail als groep kunnen verzenden in het [Exchange-beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1100a-113">This section explains how to allow users to send email as a Group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="1100a-114">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>naar **Geadresseerdengroepen** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="1100a-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="1100a-115">Selecteer **Edit**![Groepspictogram](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Bewerken bewerken in Groep waarmee gebruikers kunnen worden verzonden.  </span><span class="sxs-lookup"><span data-stu-id="1100a-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="1100a-116">Selecteer **delegering van groepen**.</span><span class="sxs-lookup"><span data-stu-id="1100a-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="1100a-117">Selecteer in de sectie **+** Verzenden **als** het teken om de gebruikers toe te voegen die u als groep wilt verzenden.</span><span class="sxs-lookup"><span data-stu-id="1100a-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Selecteer het plusteken om de gebruikers toe te voegen die u als Office 365-groep wilt verzenden](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="1100a-119">Typ om te zoeken of kies een gebruiker uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="1100a-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="1100a-120">Selecteer **OK** en **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1100a-120">Select **OK** and **Save**.</span></span>
    
    ![Typ om een gebruiker in de lijst te zoeken of te kiezen](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="1100a-122">Leden toestaan e-mail te verzenden namens een groep</span><span class="sxs-lookup"><span data-stu-id="1100a-122">Allow members to send email on behalf of a Group</span></span>

<span data-ttu-id="1100a-123">In deze sectie wordt uitgelegd hoe gebruikers e-mail kunnen verzenden namens een groep in het Exchange-beheercentrum (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1100a-123">This section explains how to allow users to send email on behalf of a Group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="1100a-124">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>naar **Geadresseerdengroepen** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="1100a-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="1100a-125">Selecteer **Edit** ![Groepspictogram](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Bewerken bewerken in de groep die gebruikers als wilt laten verzenden.</span><span class="sxs-lookup"><span data-stu-id="1100a-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="1100a-126">Selecteer **delegering van groepen**.</span><span class="sxs-lookup"><span data-stu-id="1100a-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="1100a-127">Selecteer in de sectie Verzenden **+** namens het teken om de gebruikers toe te voegen die u als groep wilt verzenden.</span><span class="sxs-lookup"><span data-stu-id="1100a-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Selecteer het plusteken om de gebruikers toe te voegen die u als Office 365-groep wilt verzenden](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="1100a-129">Typ om te zoeken of kies een gebruiker uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="1100a-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="1100a-130">Selecteer **OK** en **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1100a-130">Select **OK** and **Save**.</span></span>
    
    ![Typ om een gebruiker in de lijst te zoeken of te kiezen](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="1100a-132">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="1100a-132">Related articles</span></span>

[<span data-ttu-id="1100a-133">Meer informatie over Office 365-groepen</span><span class="sxs-lookup"><span data-stu-id="1100a-133">Learn more about Office 365 Groups</span></span>](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[<span data-ttu-id="1100a-134">Toestemming voor invoegontvangers</span><span class="sxs-lookup"><span data-stu-id="1100a-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="1100a-135">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="1100a-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
