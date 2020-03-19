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
description: 'Meer informatie over het inschakelen of uitschakelen van de functie Rommel voor alle of specifieke gebruikers in uw organisatie, met Exchange PowerShell. '
ms.openlocfilehash: 65aa614095ecbebaad3d7eb38af1e74166ce20ac
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808886"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="08383-103">Onbelangrijke e-mail configureren voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="08383-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="08383-104">[Postvak IN met prioriteit](../setup/configure-focused-inbox.md) gaat Onbelangrijke e-mail vervangen.</span><span class="sxs-lookup"><span data-stu-id="08383-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="08383-105">Meer informatie: [Update op gerichte inbox en onze plannen voor Rommel](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="08383-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="08383-106">Als beheerder moet u mogelijk de functie Rommel beheren in Office 365.</span><span class="sxs-lookup"><span data-stu-id="08383-106">As an admin, you may have to manage the Clutter feature in Office 365.</span></span> <span data-ttu-id="08383-107">Als u de functie Onbelangrijke e-mail wilt in- of uitschakelen voor gebruikers in uw organisatie, moet u Exchange PowerShell gebruiken.</span><span class="sxs-lookup"><span data-stu-id="08383-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="08383-108">(Personen kunnen dit in- of uitschakelen met behulp van deze instructies: [Onbelangrijke e-mail uit-/inschakelen in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span><span class="sxs-lookup"><span data-stu-id="08383-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span></span> 
  
<span data-ttu-id="08383-109">Zie [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) (PowerShell gebruiken met Exchange Online) en [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) (Verbinding maken met Exchange Online PowerShell) voor informatie over het gebruik van Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08383-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="08383-110">U moet een account hebben met ten minste de functie van Exchange Service-beheerder en de mogelijkheid om verbinding te maken met Exchange Online met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08383-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="08383-111">Onbelangrijke e-mail inschakelen bij gebruik van Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="08383-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="08383-p104">U kunt Onbelangrijke e-mail handmatig voor een postvak inschakelen door de cmdlet [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) uit te voeren. U kunt ook de instellingen voor Onbelangrijke e-mail voor postvakken in uw organisatie weergeven door de cmdlet [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="08383-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="08383-114">Onbelangrijke e-mail voor gebruiker Ilene de Crom inschakelen</span><span class="sxs-lookup"><span data-stu-id="08383-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="08383-115">Onbelangrijke e-mail uitschakelen bij gebruik van Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="08383-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="08383-p105">U kunt Onbelangrijke e-mail handmatig voor een postvak uitschakelen door de cmdlet [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) uit te voeren. U kunt ook de instellingen voor **Onbelangrijke e-mail** voor postvakken in uw organisatie weergeven door de cmdlet [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="08383-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="08383-118">Onbelangrijke e-mail voor gebruiker Ilene de Crom uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="08383-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="08383-119">Als u PowerShell gebruikt om veel gebruikers ineens te maken, dan moet u [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) voor elk postvak van een gebruiker uitvoeren om Onbelangrijke e-mail te beheren.</span><span class="sxs-lookup"><span data-stu-id="08383-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="08383-120">Wanneer krijgen gebruikers de schakeloptie voor het in- en uitschakelen van Onbelangrijke e-mail te zien in de webversie van Outlook?</span><span class="sxs-lookup"><span data-stu-id="08383-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="08383-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="08383-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="08383-122">Als beheerder u Rommel opnieuw inschakelen met Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08383-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="08383-123">Wanneer u dit hebt gedaan, wordt Postvak IN met prioriteit uitgeschakeld en is Onbelangrijke e-mail opnieuw actief.</span><span class="sxs-lookup"><span data-stu-id="08383-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="08383-124">**Als u de webversie van Outlook gebruikt in combinatie met een zakelijk Office 365-abonnement:**</span><span class="sxs-lookup"><span data-stu-id="08383-124">**If you're using Outlook on the web with an Office 365 business subscription:**</span></span>
  
- <span data-ttu-id="08383-125">Als een gebruiker momenteel Onbelangrijke e-mail heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="08383-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="08383-126">Instellingen voor Onbelangrijke e-mail worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="08383-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="08383-127">Als een gebruiker momenteel Postvak IN met prioriteit heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="08383-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="08383-128">Instellingen voor Onbelangrijke e-mail worden niet weergegeven</span><span class="sxs-lookup"><span data-stu-id="08383-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="08383-129">Als Onbelangrijke e-mail en Postvak IN met prioriteit beiden zijn uitgeschakeld:</span><span class="sxs-lookup"><span data-stu-id="08383-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="08383-130">Zowel Onbelangrijke e-mail als Postvak IN met prioriteit worden weergegeven als optie in de E-mailinstellingen van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="08383-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="08383-131">**Als u Outlook.com gebruikt:**</span><span class="sxs-lookup"><span data-stu-id="08383-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="08383-132">Als een gebruiker momenteel Onbelangrijke e-mail heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="08383-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="08383-133">Instellingen voor Onbelangrijke e-mail worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="08383-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="08383-134">Als een gebruiker momenteel Postvak IN met prioriteit heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="08383-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="08383-135">Instellingen voor Onbelangrijke e-mail worden niet weergegeven</span><span class="sxs-lookup"><span data-stu-id="08383-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="08383-136">Als Onbelangrijke e-mail en Postvak IN met prioriteit beiden zijn uitgeschakeld:</span><span class="sxs-lookup"><span data-stu-id="08383-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="08383-137">Zowel Onbelangrijke e-mail als Postvak IN met prioriteit worden weergegeven als optie in de E-mailinstellingen van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="08383-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="08383-138">Als een gebruiker Postvak IN met prioriteit op enig moment in het verleden heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="08383-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="08383-139">Instellingen voor Onbelangrijke e-mail worden nooit weergegeven</span><span class="sxs-lookup"><span data-stu-id="08383-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="08383-140">In alle andere gevallen:</span><span class="sxs-lookup"><span data-stu-id="08383-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="08383-141">Instellingen voor Onbelangrijke e-mail worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="08383-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="08383-142">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="08383-142">Related articles</span></span>
<span data-ttu-id="08383-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="08383-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="08383-144">De functie Onbelangrijke e-mail gebruiken om berichten met een lage prioriteit te sorteren in Outlook</span><span class="sxs-lookup"><span data-stu-id="08383-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.office.com/article/7755ebf5-4585-469b-b1ab-8b12425c6b6b.aspx)
    
[<span data-ttu-id="08383-145">Rommel gebruiken om berichten met lage prioriteit te sorteren in OWA</span><span class="sxs-lookup"><span data-stu-id="08383-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[<span data-ttu-id="08383-146">Onbelangrijke e-mail uitschakelen in Outlook</span><span class="sxs-lookup"><span data-stu-id="08383-146">Turn off Clutter in Outlook</span></span>](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

