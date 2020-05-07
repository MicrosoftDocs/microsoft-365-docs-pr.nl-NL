---
title: Onbelangrijke e-mail configureren voor uw organisatie
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Leer de functie Rommel in- of uitschakelen voor alle of specifieke gebruikers in uw organisatie met Exchange PowerShell. '
ms.openlocfilehash: 6ba1e3f2b6a8a516a2b55267ab22fb43613350e0
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053834"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="9251d-103">Onbelangrijke e-mail configureren voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="9251d-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="9251d-104">[Postvak IN met prioriteit](../setup/configure-focused-inbox.md) gaat Onbelangrijke e-mail vervangen.</span><span class="sxs-lookup"><span data-stu-id="9251d-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="9251d-105">Meer informatie: [Update op focused inbox en onze plannen voor rommel](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="9251d-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="9251d-106">Als beheerder moet u mogelijk de functie Rommel beheren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9251d-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="9251d-107">Als u de functie Onbelangrijke e-mail wilt in- of uitschakelen voor gebruikers in uw organisatie, moet u Exchange PowerShell gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9251d-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="9251d-108">(Personen kunnen dit in- of uitschakelen met behulp van deze instructies: [Onbelangrijke e-mail uit-/inschakelen in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span><span class="sxs-lookup"><span data-stu-id="9251d-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span></span> 
  
<span data-ttu-id="9251d-109">Zie [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) (PowerShell gebruiken met Exchange Online) en [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) (Verbinding maken met Exchange Online PowerShell) voor informatie over het gebruik van Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9251d-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="9251d-110">U moet een account hebben dat ten minste de Exchange Service-beheerdersrol heeft en de mogelijkheid om verbinding te maken met Exchange Online met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9251d-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="9251d-111">Onbelangrijke e-mail inschakelen bij gebruik van Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="9251d-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="9251d-p104">U kunt Onbelangrijke e-mail handmatig voor een postvak inschakelen door de cmdlet [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) uit te voeren. U kunt ook de instellingen voor Onbelangrijke e-mail voor postvakken in uw organisatie weergeven door de cmdlet [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="9251d-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="9251d-114">Onbelangrijke e-mail voor gebruiker Ilene de Crom inschakelen</span><span class="sxs-lookup"><span data-stu-id="9251d-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="9251d-115">Onbelangrijke e-mail uitschakelen bij gebruik van Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="9251d-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="9251d-p105">U kunt Onbelangrijke e-mail handmatig voor een postvak uitschakelen door de cmdlet [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) uit te voeren. U kunt ook de instellingen voor **Onbelangrijke e-mail** voor postvakken in uw organisatie weergeven door de cmdlet [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="9251d-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="9251d-118">Onbelangrijke e-mail voor gebruiker Ilene de Crom uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="9251d-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="9251d-119">Als u PowerShell gebruikt om veel gebruikers ineens te maken, dan moet u [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) voor elk postvak van een gebruiker uitvoeren om Onbelangrijke e-mail te beheren.</span><span class="sxs-lookup"><span data-stu-id="9251d-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="9251d-120">Wanneer krijgen gebruikers de schakeloptie voor het in- en uitschakelen van Onbelangrijke e-mail te zien in de webversie van Outlook?</span><span class="sxs-lookup"><span data-stu-id="9251d-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="9251d-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="9251d-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="9251d-122">Als beheerder u Rommel opnieuw inschakelen met Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9251d-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="9251d-123">Wanneer u dit hebt gedaan, wordt Postvak IN met prioriteit uitgeschakeld en is Onbelangrijke e-mail opnieuw actief.</span><span class="sxs-lookup"><span data-stu-id="9251d-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="9251d-124">**Als u outlook op internet gebruikt met een Microsoft 365 Business Premium-abonnement:**</span><span class="sxs-lookup"><span data-stu-id="9251d-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="9251d-125">Als een gebruiker momenteel Onbelangrijke e-mail heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="9251d-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="9251d-126">Instellingen voor Onbelangrijke e-mail worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="9251d-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="9251d-127">Als een gebruiker momenteel Postvak IN met prioriteit heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="9251d-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="9251d-128">Instellingen voor Onbelangrijke e-mail worden niet weergegeven</span><span class="sxs-lookup"><span data-stu-id="9251d-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="9251d-129">Als Onbelangrijke e-mail en Postvak IN met prioriteit beiden zijn uitgeschakeld:</span><span class="sxs-lookup"><span data-stu-id="9251d-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="9251d-130">Zowel Onbelangrijke e-mail als Postvak IN met prioriteit worden weergegeven als optie in de E-mailinstellingen van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="9251d-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="9251d-131">**Als u Outlook.com gebruikt:**</span><span class="sxs-lookup"><span data-stu-id="9251d-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="9251d-132">Als een gebruiker momenteel Onbelangrijke e-mail heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="9251d-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="9251d-133">Instellingen voor Onbelangrijke e-mail worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="9251d-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="9251d-134">Als een gebruiker momenteel Postvak IN met prioriteit heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="9251d-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="9251d-135">Instellingen voor Onbelangrijke e-mail worden niet weergegeven</span><span class="sxs-lookup"><span data-stu-id="9251d-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="9251d-136">Als Onbelangrijke e-mail en Postvak IN met prioriteit beiden zijn uitgeschakeld:</span><span class="sxs-lookup"><span data-stu-id="9251d-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="9251d-137">Zowel Onbelangrijke e-mail als Postvak IN met prioriteit worden weergegeven als optie in de E-mailinstellingen van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="9251d-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="9251d-138">Als een gebruiker Postvak IN met prioriteit op enig moment in het verleden heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="9251d-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="9251d-139">Instellingen voor Onbelangrijke e-mail worden nooit weergegeven</span><span class="sxs-lookup"><span data-stu-id="9251d-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="9251d-140">In alle andere gevallen:</span><span class="sxs-lookup"><span data-stu-id="9251d-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="9251d-141">Instellingen voor Onbelangrijke e-mail worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="9251d-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="9251d-142">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="9251d-142">Related articles</span></span>
<span data-ttu-id="9251d-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="9251d-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="9251d-144">De functie Onbelangrijke e-mail gebruiken om berichten met een lage prioriteit te sorteren in Outlook</span><span class="sxs-lookup"><span data-stu-id="9251d-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.office.com/article/use-clutter-to-sort-low-priority-messages-in-outlook-7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="9251d-145">Rommel gebruiken om berichten met een lage prioriteit te sorteren in OWA</span><span class="sxs-lookup"><span data-stu-id="9251d-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[<span data-ttu-id="9251d-146">Onbelangrijke e-mail uitschakelen in Outlook</span><span class="sxs-lookup"><span data-stu-id="9251d-146">Turn off Clutter in Outlook</span></span>](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

