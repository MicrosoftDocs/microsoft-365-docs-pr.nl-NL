---
title: Toestaan dat leden namens een groep verzenden of verzenden
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
description: Lees hoe u leden toestaat e-mail te verzenden als een Microsoft 365-groep of e-mail te verzenden namens een groep Microsoft 365.
ms.openlocfilehash: 9ccaeff49914dd5b510beb80f40a3a3b790ce831
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377591"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="e2278-103">Toestaan dat leden namens een groep verzenden of verzenden</span><span class="sxs-lookup"><span data-stu-id="e2278-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="e2278-104">Een lid van een Microsoft 365-groep aan wie de machtiging **verzenden als** of **Verzenden namens** is toegewezen, kan e-mail verzenden als de groep of namens de groep.</span><span class="sxs-lookup"><span data-stu-id="e2278-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="e2278-105">In dit artikel wordt uitgelegd hoe een beheerder deze machtigingen kan instellen.</span><span class="sxs-lookup"><span data-stu-id="e2278-105">This article explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="e2278-106">Als Megan Bowen deel uitmaakt van de groep **training** microsoft 365 en als ze een e-mailbericht **verzendt als de** groep, ziet het er als volgt uit: de **trainings** groep stuurt de e-mail.</span><span class="sxs-lookup"><span data-stu-id="e2278-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="e2278-107">Met de machtiging **Verzenden namens** kan een gebruiker e-mail verzenden namens een groep microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2278-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="e2278-108">Als Alex Wilber een onderdeel is van de groep **marketing** microsoft 365 en de machtiging **Verzenden namens** en een e-mailbericht verzendt als de groep, ziet de e-mail eruit alsof de E-mail is verzonden door **Alex Wilber namens marketing**.</span><span class="sxs-lookup"><span data-stu-id="e2278-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2278-109">U kunt **verzenden als** of **Verzenden namens** configureren voor een bepaalde gebruiker, maar niet beide.</span><span class="sxs-lookup"><span data-stu-id="e2278-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="e2278-110">Als u beide configureert, wordt het standaard **bericht verzonden als**.</span><span class="sxs-lookup"><span data-stu-id="e2278-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="e2278-111">Zie [E-mail verzenden vanuit of namens een Microsoft 365-groep](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) voor meer informatie over het gebruik van Outlook en de webversie van Outlook om e-mail te verzenden vanuit een groep.</span><span class="sxs-lookup"><span data-stu-id="e2278-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="e2278-112">Toestaan dat leden e-mail verzenden als groep</span><span class="sxs-lookup"><span data-stu-id="e2278-112">Allow members to send email as a group</span></span>

<span data-ttu-id="e2278-113">In deze sectie wordt uitgelegd hoe u gebruikers kunt toestaan e-mail te verzenden als een groep in het [Exchange-Beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2059104) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e2278-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="e2278-114">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>naar groepen met **geadresseerden** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="e2278-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="e2278-115">Selecteer **bewerkings** ![ pictogram bewerken ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) voor de groep die u wilt toestaan dat gebruikers verzenden als.  </span><span class="sxs-lookup"><span data-stu-id="e2278-115">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="e2278-116">Selecteer **delegering van groepen**.</span><span class="sxs-lookup"><span data-stu-id="e2278-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="e2278-117">Selecteer in de sectie **verzenden als** het **+** teken om de gebruikers toe te voegen die u als de groep wilt verzenden.</span><span class="sxs-lookup"><span data-stu-id="e2278-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Schermafbeelding van het dialoogvenster verzenden als](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="e2278-119">Typ om te zoeken of kies een gebruiker uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="e2278-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="e2278-120">Selecteer **OK** en **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e2278-120">Select **OK** and **Save**.</span></span>
    
    ![Typ om te zoeken of selecteer een gebruiker in de lijst](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="e2278-122">Toestaan dat leden e-mail verzenden namens een groep</span><span class="sxs-lookup"><span data-stu-id="e2278-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="e2278-123">In deze sectie wordt uitgelegd hoe u gebruikers kunt toestaan e-mail te verzenden namens een groep in het Exchange-Beheercentrum in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e2278-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="e2278-124">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>naar groepen met **geadresseerden** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="e2278-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="e2278-125">Selecteer **bewerkings** ![ pictogram bewerken ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) voor de groep die u wilt toestaan dat gebruikers verzenden als.</span><span class="sxs-lookup"><span data-stu-id="e2278-125">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="e2278-126">Selecteer **delegering van groepen**.</span><span class="sxs-lookup"><span data-stu-id="e2278-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="e2278-127">Selecteer in de sectie verzenden namens het **+** teken om de gebruikers toe te voegen die u als de groep wilt verzenden.</span><span class="sxs-lookup"><span data-stu-id="e2278-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Schermafbeelding van het dialoogvenster Verzenden namens](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="e2278-129">Typ om te zoeken of kies een gebruiker uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="e2278-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="e2278-130">Selecteer **OK** en **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e2278-130">Select **OK** and **Save**.</span></span>
    
    ![Typ om te zoeken of selecteer een gebruiker in de lijst](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="e2278-132">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="e2278-132">Related articles</span></span>

[<span data-ttu-id="e2278-133">Meer informatie over Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="e2278-133">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="e2278-134">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="e2278-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="e2278-135">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="e2278-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
