---
title: Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Meer informatie over hoe u uw wachtwoorden opnieuw instellen met behulp van het hulpprogramma voor het opnieuw instellen van selfservicewachtwoorden.
ms.openlocfilehash: 5c30d1da20998fb7e9681431173070ba57e1b090
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387031"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="6b460-103">Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen</span><span class="sxs-lookup"><span data-stu-id="6b460-103">Let users reset their own passwords</span></span>

<span data-ttu-id="6b460-104">Wordt u overspoeld door mensen die u vragen hun wachtwoord opnieuw in te stellen?</span><span class="sxs-lookup"><span data-stu-id="6b460-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="6b460-105">Als Microsoft 365-beheerder u mensen het hulpprogramma voor het [opnieuw instellen van selfservicewachtwoorden](https://go.microsoft.com/fwlink/p/?LinkId=522677) laten gebruiken, zodat u geen wachtwoorden voor hen hoeft te resetten.</span><span class="sxs-lookup"><span data-stu-id="6b460-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="6b460-106">Zo hoeft u zelf minder te doen!</span><span class="sxs-lookup"><span data-stu-id="6b460-106">Less work for you!</span></span> 
  
<span data-ttu-id="6b460-107">Hier volgen enkele dingen die u moet weten:</span><span class="sxs-lookup"><span data-stu-id="6b460-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="6b460-108">U krijgt selfservice wachtwoord reset voor cloud-gebruikers **gratis** met een Microsoft 365 business, onderwijs, of non-profit betaald plan.</span><span class="sxs-lookup"><span data-stu-id="6b460-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="6b460-109">Het werkt niet met Microsoft 365 trial.</span><span class="sxs-lookup"><span data-stu-id="6b460-109">It doesn't work with Microsoft 365 trial.</span></span> 
    
- <span data-ttu-id="6b460-p103">Deze maakt gebruik van Azure. Deze functie ontvangt u in Azure automatisch **gratis** wanneer u deze stappen uitvoert. Het kost u niets als u selfservice voor wachtwoordherstel inschakelt als u geen andere Azure-functies gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6b460-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="6b460-p104">**Als u on-premises Active Directory gebruikt**, zijn de twee bovenstaande punten niet van toepassing. U kunt dit instellen, maar **u hebt hiervoor wel een betaald abonnement op Azure AD Premium nodig**.</span><span class="sxs-lookup"><span data-stu-id="6b460-p104">**If you're using an on-premises Active Directory**, the above two points don't apply. Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="6b460-115">Bekijk een korte video over het laten van gebruikers hun eigen wachtwoorden te resetten.</span><span class="sxs-lookup"><span data-stu-id="6b460-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="6b460-116">Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="6b460-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="6b460-117">Laat mensen hun eigen wachtwoorden resetten</span><span class="sxs-lookup"><span data-stu-id="6b460-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="6b460-118">Met deze stappen wordt selfservice voor wachtwoordherstel ingeschakeld voor iedereen in uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="6b460-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1. <span data-ttu-id="6b460-119">Ga in het beheercentrum **Settings** naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Instellingen instellingen.</a></span><span class="sxs-lookup"><span data-stu-id="6b460-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6b460-120">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a>naar de **Settings** \> \*\* &amp; privacypagina Instellingen beveiliging.\*\*</span><span class="sxs-lookup"><span data-stu-id="6b460-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6b460-121">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>naar de **Settings** \> privacypagina **Instellingen** \> \*\* &amp; Beveiliging.\*\*</span><span class="sxs-lookup"><span data-stu-id="6b460-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="6b460-122">Selecteer beveiliging **& Privacy**boven aan de pagina Instellingen .</span><span class="sxs-lookup"><span data-stu-id="6b460-122">At the top of the Settings page select **Security & Privacy**.</span></span>
  
3. <span data-ttu-id="6b460-123">Selecteer **Self Service Password Reset**.</span><span class="sxs-lookup"><span data-stu-id="6b460-123">Select **Self Service Password Reset**.</span></span>
  
4. <span data-ttu-id="6b460-124">Selecteer op de pagina Eigenschappen de optie **Alles** om het in te schakelen voor iedereen in uw bedrijf en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6b460-124">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="6b460-125">Wanneer uw gebruikers zich aanmelden, wordt hen gevraagd aanvullende contactgegevens in te voeren waarmee ze hun wachtwoord in de toekomst kunnen resetten.</span><span class="sxs-lookup"><span data-stu-id="6b460-125">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6b460-126">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="6b460-126">Related articles</span></span>

[<span data-ttu-id="6b460-127">Het wachtwoordverloopbeleid voor uw organisatie instellen:</span><span class="sxs-lookup"><span data-stu-id="6b460-127">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="6b460-128">Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="6b460-128">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="6b460-129">Trainingsvideo's voor Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="6b460-129">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
