---
title: Personen hun eigen wachtwoorden opnieuw laten instellen in Office 365
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Ontdek hoe u uw wachtwoorden resetten met behulp van de hulpprogramma voor het opnieuw instellen van wachtwoorden voor selfservice.
ms.openlocfilehash: 87accc393d08b922ebc3f75ef1aa5ddb2d0b2955
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806903"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="a9d3c-103">Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen</span><span class="sxs-lookup"><span data-stu-id="a9d3c-103">Let users reset their own passwords</span></span>

<span data-ttu-id="a9d3c-104">Wordt u overspoeld door mensen die u vragen hun wachtwoord opnieuw in te stellen?</span><span class="sxs-lookup"><span data-stu-id="a9d3c-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="a9d3c-105">Als Microsoft 365-beheerder u mensen de hulpprogramma voor het opnieuw instellen van wachtwoorden voor [selfservice](https://go.microsoft.com/fwlink/p/?LinkId=522677) laten gebruiken, zodat u geen wachtwoorden voor hen hoeft te resetten.</span><span class="sxs-lookup"><span data-stu-id="a9d3c-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="a9d3c-106">Zo hoeft u zelf minder te doen!</span><span class="sxs-lookup"><span data-stu-id="a9d3c-106">Less work for you!</span></span> 
  
<span data-ttu-id="a9d3c-107">Hier volgen enkele dingen die u moet weten:</span><span class="sxs-lookup"><span data-stu-id="a9d3c-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="a9d3c-p102">Selfservice voor wachtwoordherstel is **gratis** inbegrepen voor cloudgebruikers bij een betaald abonnement op Office 365 Business, Education of Nonprofit. Deze functie werkt niet in de proefversie van Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9d3c-p102">You get self-service password reset for cloud users **free** with any Office 365 business, education, or nonprofit paid plan. It doesn't work with Office 365 trial.</span></span> 
    
- <span data-ttu-id="a9d3c-p103">Deze maakt gebruik van Azure. Deze functie ontvangt u in Azure automatisch **gratis** wanneer u deze stappen uitvoert. Het kost u niets als u selfservice voor wachtwoordherstel inschakelt als u geen andere Azure-functies gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a9d3c-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="a9d3c-p104">**Als u on-premises Active Directory gebruikt**, zijn de twee bovenstaande punten niet van toepassing. U kunt dit instellen, maar **u hebt hiervoor wel een betaald abonnement op Azure AD Premium nodig**.</span><span class="sxs-lookup"><span data-stu-id="a9d3c-p104">**If you're using an on-premises Active Directory**, the above two points don't apply. Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="a9d3c-115">Bekijk een korte video over het laten resetten van hun eigen wachtwoorden door gebruikers.</span><span class="sxs-lookup"><span data-stu-id="a9d3c-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="a9d3c-116">Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="a9d3c-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="a9d3c-117">Laat mensen hun eigen wachtwoorden resetten</span><span class="sxs-lookup"><span data-stu-id="a9d3c-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="a9d3c-118">Met deze stappen wordt selfservice voor wachtwoordherstel ingeschakeld voor iedereen in uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="a9d3c-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1.  <span data-ttu-id="a9d3c-119">Ga in het beheercentrum naar de pagina **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">voor beveiliging &.</a></span><span class="sxs-lookup"><span data-stu-id="a9d3c-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a9d3c-120">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a>naar de **privacypagina &amp; Instellingenbeveiliging.** **Settings** \></span><span class="sxs-lookup"><span data-stu-id="a9d3c-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a9d3c-121">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>naar de **privacypagina &amp; Instellingenbeveiliging.** **Settings** \></span><span class="sxs-lookup"><span data-stu-id="a9d3c-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="a9d3c-122">Selecteer onder **Laat uw mensen hun eigen wachtwoorden opnieuw instellen**en selecteert u de koppeling voor het Azure **AD-beheercentrum**.</span><span class="sxs-lookup"><span data-stu-id="a9d3c-122">Under **Let your people reset their own passwords**, select the link for the **Azure AD admin center**.</span></span> <span data-ttu-id="a9d3c-123">U ontvangt Azure vervolgens gratis.</span><span class="sxs-lookup"><span data-stu-id="a9d3c-123">You'll get Azure for free!</span></span>
  
3. <span data-ttu-id="a9d3c-124">Selecteer **Gebruikers** in de linkernavigatie en selecteer **Vervolgens Wachtwoordopnieuw instellen**.</span><span class="sxs-lookup"><span data-stu-id="a9d3c-124">Select **Users** in the left navigation, and then select **Password reset**.</span></span>
  
4. <span data-ttu-id="a9d3c-125">Selecteer **Alles** op de pagina Eigenschappen om alles in te schakelen voor iedereen in uw bedrijf en selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="a9d3c-125">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="a9d3c-126">Wanneer gebruikers zich aanmelden bij Office 365, wordt ze gevraagd aanvullende contactgegevens op te geven waarmee ze in de toekomst hun wachtwoord opnieuw kunnen instellen.</span><span class="sxs-lookup"><span data-stu-id="a9d3c-126">When your users sign in to Office 365, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a9d3c-127">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="a9d3c-127">Related articles</span></span>

[<span data-ttu-id="a9d3c-128">Het wachtwoordverloopbeleid voor uw organisatie instellen:</span><span class="sxs-lookup"><span data-stu-id="a9d3c-128">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="a9d3c-129">Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="a9d3c-129">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="a9d3c-130">Trainingsvideo's voor Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="a9d3c-130">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
