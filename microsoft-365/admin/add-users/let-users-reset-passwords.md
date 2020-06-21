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
ms.openlocfilehash: 288613023ee61626bf12f7090ad0ff73139ef06d
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780587"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="ab663-103">Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen</span><span class="sxs-lookup"><span data-stu-id="ab663-103">Let users reset their own passwords</span></span>

<span data-ttu-id="ab663-104">Wordt u overspoeld door mensen die u vragen hun wachtwoord opnieuw in te stellen?</span><span class="sxs-lookup"><span data-stu-id="ab663-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="ab663-105">Als Microsoft 365-beheerder u mensen de [selfservice-tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) voor het opnieuw instellen van wachtwoorden laten gebruiken, zodat u wachtwoorden niet hoeft te resetten.</span><span class="sxs-lookup"><span data-stu-id="ab663-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="ab663-106">Zo hoeft u zelf minder te doen!</span><span class="sxs-lookup"><span data-stu-id="ab663-106">Less work for you!</span></span> 
  
<span data-ttu-id="ab663-107">Hier volgen enkele dingen die u moet weten:</span><span class="sxs-lookup"><span data-stu-id="ab663-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="ab663-108">U krijgt gratis selfservicewachtwoorden opnieuw instellen voor **cloudgebruikers** met een betaald Microsoft 365-abonnement voor bedrijven, onderwijs of non-profitorganisaties.</span><span class="sxs-lookup"><span data-stu-id="ab663-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="ab663-109">Het werkt niet met Microsoft 365 trial.</span><span class="sxs-lookup"><span data-stu-id="ab663-109">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="ab663-110">It uses Azure.</span><span class="sxs-lookup"><span data-stu-id="ab663-110">It uses Azure.</span></span> <span data-ttu-id="ab663-111">You'll automatically get this feature in Azure for **free** when you do these steps.</span><span class="sxs-lookup"><span data-stu-id="ab663-111">You'll automatically get this feature in Azure for **free** when you do these steps.</span></span> <span data-ttu-id="ab663-112">It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span><span class="sxs-lookup"><span data-stu-id="ab663-112">It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="ab663-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span><span class="sxs-lookup"><span data-stu-id="ab663-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="ab663-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="ab663-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="ab663-115">Bekijk een korte video over het laten resetten van hun eigen wachtwoorden door gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ab663-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="ab663-116">Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="ab663-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="ab663-117">Laat mensen hun eigen wachtwoorden resetten</span><span class="sxs-lookup"><span data-stu-id="ab663-117">Let people reset their own passwords</span></span>

<span data-ttu-id="ab663-118">Met deze stappen wordt selfservice voor wachtwoordherstel ingeschakeld voor iedereen in uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="ab663-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="ab663-119">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">beheercentrum</a>naar de **Settings** > **instellingenpagina van instellingen.**</span><span class="sxs-lookup"><span data-stu-id="ab663-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ab663-120">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a>naar de **Settings** \> \*\* &amp; privacypagina Instellingenbeveiliging.\*\*</span><span class="sxs-lookup"><span data-stu-id="ab663-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ab663-121">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>naar de **Settings** \> **Settings** \> \*\* &amp; privacypagina\*\* Instellingen beveiliging.</span><span class="sxs-lookup"><span data-stu-id="ab663-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="ab663-122">Selecteer boven aan de pagina Instellingen voor **Organisatie** het tabblad **Beveiliging & privacy.**</span><span class="sxs-lookup"><span data-stu-id="ab663-122">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="ab663-123">Selecteer **Selfservice Wachtwoord opnieuw instellen**.</span><span class="sxs-lookup"><span data-stu-id="ab663-123">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="ab663-124">Selecteer Onder **Selfservice-wachtwoord opnieuw instellen**de optie **Ga naar de Azure-portal om het resetten van zelfservicewachtwoorden in te schakelen.**</span><span class="sxs-lookup"><span data-stu-id="ab663-124">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="ab663-125">Selecteer **gebruikers in**het linkernavigatiedeelvenster en vervolgens op de **Gebruikers | Alle gebruikers** pagina, selecteer **Wachtwoord resetten**.</span><span class="sxs-lookup"><span data-stu-id="ab663-125">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="ab663-126">Selecteer **Alles** op de pagina **Eigenschappen** om het voor iedereen in uw bedrijf in te schakelen en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ab663-126">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="ab663-127">Wanneer uw gebruikers zich aanmelden, wordt hen gevraagd om aanvullende contactgegevens in te voeren waarmee ze hun wachtwoord in de toekomst opnieuw kunnen instellen.</span><span class="sxs-lookup"><span data-stu-id="ab663-127">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ab663-128">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="ab663-128">Related articles</span></span>

[<span data-ttu-id="ab663-129">Het wachtwoordverloopbeleid voor uw organisatie instellen:</span><span class="sxs-lookup"><span data-stu-id="ab663-129">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="ab663-130">Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="ab663-130">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="ab663-131">Trainingsvideo's voor Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="ab663-131">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
