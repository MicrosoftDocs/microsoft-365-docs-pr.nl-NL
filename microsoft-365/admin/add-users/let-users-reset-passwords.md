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
description: Ontdek hoe u uw wachtwoorden opnieuw instellen met behulp van de selfservice tool voor het opnieuw instellen van wachtwoorden.
ms.openlocfilehash: 40f094489a1981302e97043b019e8c90a52ffc55
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678680"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="5491b-103">Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen</span><span class="sxs-lookup"><span data-stu-id="5491b-103">Let users reset their own passwords</span></span>

<span data-ttu-id="5491b-104">Wordt u overspoeld door mensen die u vragen hun wachtwoord opnieuw in te stellen?</span><span class="sxs-lookup"><span data-stu-id="5491b-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="5491b-105">Als Microsoft 365-beheerder u mensen de [selfservice-tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) voor het opnieuw instellen van wachtwoorden laten gebruiken, zodat u wachtwoorden niet hoeft te resetten.</span><span class="sxs-lookup"><span data-stu-id="5491b-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="5491b-106">Zo hoeft u zelf minder te doen!</span><span class="sxs-lookup"><span data-stu-id="5491b-106">Less work for you!</span></span> 
  
<span data-ttu-id="5491b-107">Hier volgen enkele dingen die u moet weten:</span><span class="sxs-lookup"><span data-stu-id="5491b-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="5491b-108">U krijgt gratis selfservicewachtwoorden opnieuw instellen voor **cloudgebruikers** met een betaald Microsoft 365-abonnement voor bedrijven, onderwijs of non-profitorganisaties.</span><span class="sxs-lookup"><span data-stu-id="5491b-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="5491b-109">Het werkt niet met Microsoft 365 trial.</span><span class="sxs-lookup"><span data-stu-id="5491b-109">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="5491b-p103">Deze maakt gebruik van Azure. Deze functie ontvangt u in Azure automatisch **gratis** wanneer u deze stappen uitvoert. Het kost u niets als u selfservice voor wachtwoordherstel inschakelt als u geen andere Azure-functies gebruikt.</span><span class="sxs-lookup"><span data-stu-id="5491b-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="5491b-p104">**Als u on-premises Active Directory gebruikt**, zijn de twee bovenstaande punten niet van toepassing. U kunt dit instellen, maar **u hebt hiervoor wel een betaald abonnement op Azure AD Premium nodig**.</span><span class="sxs-lookup"><span data-stu-id="5491b-p104">**If you're using an on-premises Active Directory**, the above two points don't apply. Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="5491b-115">Bekijk een korte video over het laten resetten van hun eigen wachtwoorden door gebruikers.</span><span class="sxs-lookup"><span data-stu-id="5491b-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="5491b-116">Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="5491b-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="5491b-117">Laat mensen hun eigen wachtwoorden resetten</span><span class="sxs-lookup"><span data-stu-id="5491b-117">Let people reset their own passwords</span></span>

<span data-ttu-id="5491b-118">Met deze stappen wordt selfservice voor wachtwoordherstel ingeschakeld voor iedereen in uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="5491b-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="5491b-119">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">beheercentrum</a>naar de **Settings** > **instellingenpagina van instellingen.**</span><span class="sxs-lookup"><span data-stu-id="5491b-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5491b-120">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a>naar de **Settings** \> \*\* &amp; privacypagina Instellingenbeveiliging.\*\*</span><span class="sxs-lookup"><span data-stu-id="5491b-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5491b-121">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>naar de **Settings** \> **Settings** \> \*\* &amp; privacypagina\*\* Instellingen beveiliging.</span><span class="sxs-lookup"><span data-stu-id="5491b-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="5491b-122">Selecteer boven aan de pagina Instellingen voor **Organisatie** het tabblad **Beveiliging & privacy.**</span><span class="sxs-lookup"><span data-stu-id="5491b-122">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="5491b-123">Selecteer **Selfservice Wachtwoord opnieuw instellen**.</span><span class="sxs-lookup"><span data-stu-id="5491b-123">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="5491b-124">Selecteer Onder **Selfservice-wachtwoord opnieuw instellen**de optie **Ga naar de Azure-portal om het resetten van zelfservicewachtwoorden in te schakelen.**</span><span class="sxs-lookup"><span data-stu-id="5491b-124">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="5491b-125">Selecteer **gebruikers in**het linkernavigatiedeelvenster en vervolgens op de **Gebruikers | Alle gebruikers** pagina, selecteer **Wachtwoord resetten**.</span><span class="sxs-lookup"><span data-stu-id="5491b-125">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="5491b-126">Selecteer **Alles** op de pagina **Eigenschappen** om het voor iedereen in uw bedrijf in te schakelen en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5491b-126">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="5491b-127">Wanneer uw gebruikers zich aanmelden, wordt hen gevraagd om aanvullende contactgegevens in te voeren waarmee ze hun wachtwoord in de toekomst opnieuw kunnen instellen.</span><span class="sxs-lookup"><span data-stu-id="5491b-127">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5491b-128">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="5491b-128">Related articles</span></span>

[<span data-ttu-id="5491b-129">Het wachtwoordverloopbeleid voor uw organisatie instellen:</span><span class="sxs-lookup"><span data-stu-id="5491b-129">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="5491b-130">Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="5491b-130">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="5491b-131">Trainingsvideo's voor Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="5491b-131">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
