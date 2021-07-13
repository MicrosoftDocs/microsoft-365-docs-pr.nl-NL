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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Informatie over het in- of uitschakelen van de functie Onbelangrijke e-mail voor alle of specifieke gebruikers in uw organisatie, met Exchange PowerShell. '
ms.openlocfilehash: 91098047bdf2ab8190283990bdc6b0292e3e57ba
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393977"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="e2e22-103">Onbelangrijke e-mail configureren voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="e2e22-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="e2e22-104">[Postvak IN met prioriteit](../setup/configure-focused-inbox.md) gaat Onbelangrijke e-mail vervangen.</span><span class="sxs-lookup"><span data-stu-id="e2e22-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="e2e22-105">Meer informatie: Update over Postvak IN met focus [en onze plannen voor Onbelangrijke e-mail](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="e2e22-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="e2e22-106">Als beheerder moet u mogelijk de functie Onbelangrijke e-mail beheren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2e22-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="e2e22-107">Als u de functie Onbelangrijke e-mail wilt in- of uitschakelen voor gebruikers in uw organisatie, moet u Exchange PowerShell gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e2e22-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="e2e22-108">(Personen kunnen het in- of uitschakelen met behulp van deze instructies: Onbelangrijke e-mail in- of uitschakelen [in Outlook.](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)</span><span class="sxs-lookup"><span data-stu-id="e2e22-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="e2e22-109">Zie [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) (PowerShell gebruiken met Exchange Online) en [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor informatie over het gebruik van Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2e22-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="e2e22-110">U moet een account hebben dat ten minste de rol Exchange servicebeheerder en de mogelijkheid om verbinding te maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2e22-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="e2e22-111">Onbelangrijke e-mail inschakelen bij gebruik van Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2e22-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="e2e22-p104">U kunt Onbelangrijke e-mail handmatig voor een postvak inschakelen door de cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter) uit te voeren. U kunt ook de instellingen voor Onbelangrijke e-mail voor postvakken in uw organisatie weergeven door de cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter) uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="e2e22-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="e2e22-114">Onbelangrijke e-mail voor gebruiker Ilene de Crom inschakelen</span><span class="sxs-lookup"><span data-stu-id="e2e22-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="e2e22-115">Onbelangrijke e-mail uitschakelen bij gebruik van Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2e22-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="e2e22-p105">U kunt Onbelangrijke e-mail handmatig voor een postvak uitschakelen door de cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter) uit te voeren. U kunt ook de instellingen voor **Onbelangrijke e-mail** voor postvakken in uw organisatie weergeven door de cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter) uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="e2e22-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="e2e22-118">Onbelangrijke e-mail voor gebruiker Ilene de Crom uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="e2e22-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="e2e22-119">Als u PowerShell gebruikt om veel gebruikers ineens te maken, dan moet u [Set-Clutter](/powershell/module/exchange/set-clutter) voor elk postvak van een gebruiker uitvoeren om Onbelangrijke e-mail te beheren.</span><span class="sxs-lookup"><span data-stu-id="e2e22-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="e2e22-120">Wanneer krijgen gebruikers de schakeloptie voor het in- en uitschakelen van Onbelangrijke e-mail te zien in de webversie van Outlook?</span><span class="sxs-lookup"><span data-stu-id="e2e22-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="e2e22-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="e2e22-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="e2e22-122">Als beheerder kunt u Onbelangrijke e-mail opnieuw inschakelen met Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2e22-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="e2e22-123">Wanneer u dit hebt gedaan, wordt Postvak IN met prioriteit uitgeschakeld en is Onbelangrijke e-mail opnieuw actief.</span><span class="sxs-lookup"><span data-stu-id="e2e22-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="e2e22-124">**Als u een abonnement webversie van Outlook met Microsoft 365 Business Premium abonnement:**</span><span class="sxs-lookup"><span data-stu-id="e2e22-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="e2e22-125">Als een gebruiker momenteel Onbelangrijke e-mail heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="e2e22-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="e2e22-126">Instellingen voor Onbelangrijke e-mail worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="e2e22-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="e2e22-127">Als een gebruiker momenteel Postvak IN met prioriteit heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="e2e22-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="e2e22-128">Instellingen voor Onbelangrijke e-mail worden niet weergegeven</span><span class="sxs-lookup"><span data-stu-id="e2e22-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="e2e22-129">Als Onbelangrijke e-mail en Postvak IN met prioriteit beiden zijn uitgeschakeld:</span><span class="sxs-lookup"><span data-stu-id="e2e22-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="e2e22-130">Zowel Onbelangrijke e-mail als Postvak IN met prioriteit worden weergegeven als optie in de E-mailinstellingen van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="e2e22-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="e2e22-131">**Als u Outlook.com gebruikt:**</span><span class="sxs-lookup"><span data-stu-id="e2e22-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="e2e22-132">Als een gebruiker momenteel Onbelangrijke e-mail heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="e2e22-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="e2e22-133">Instellingen voor Onbelangrijke e-mail worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="e2e22-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="e2e22-134">Als een gebruiker momenteel Postvak IN met prioriteit heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="e2e22-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="e2e22-135">Instellingen voor Onbelangrijke e-mail worden niet weergegeven</span><span class="sxs-lookup"><span data-stu-id="e2e22-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="e2e22-136">Als Onbelangrijke e-mail en Postvak IN met prioriteit beiden zijn uitgeschakeld:</span><span class="sxs-lookup"><span data-stu-id="e2e22-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="e2e22-137">Zowel Onbelangrijke e-mail als Postvak IN met prioriteit worden weergegeven als optie in de E-mailinstellingen van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="e2e22-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="e2e22-138">Als een gebruiker Postvak IN met prioriteit op enig moment in het verleden heeft ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="e2e22-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="e2e22-139">Instellingen voor Onbelangrijke e-mail worden nooit weergegeven</span><span class="sxs-lookup"><span data-stu-id="e2e22-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="e2e22-140">In alle andere gevallen:</span><span class="sxs-lookup"><span data-stu-id="e2e22-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="e2e22-141">Instellingen voor Onbelangrijke e-mail worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="e2e22-141">Clutter settings will appear</span></span>
    
## <a name="related-content"></a><span data-ttu-id="e2e22-142">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="e2e22-142">Related content</span></span>

<span data-ttu-id="e2e22-143">[Onbelangrijke e-mail gebruiken om](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) berichten met een lage prioriteit te sorteren in Outlook (artikel)</span><span class="sxs-lookup"><span data-stu-id="e2e22-143">[Use Clutter to sort low priority messages in Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (article)</span></span>\
<span data-ttu-id="e2e22-144">[Onbelangrijke e-mail gebruiken om](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) berichten met een lage prioriteit te sorteren in OWA (artikel)</span><span class="sxs-lookup"><span data-stu-id="e2e22-144">[Use Clutter to sort low priority messages in OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (article)</span></span>\
<span data-ttu-id="e2e22-145">[Onbelangrijke e-mail uitschakelen in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (artikel)</span><span class="sxs-lookup"><span data-stu-id="e2e22-145">[Turn off Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (article)</span></span>
