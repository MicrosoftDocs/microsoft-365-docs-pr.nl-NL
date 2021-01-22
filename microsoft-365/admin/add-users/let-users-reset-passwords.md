---
title: Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen
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
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Lees hoe u wachtwoorden opnieuw kunt instellen met het selfservicehulpprogramma voor wachtwoord opnieuw instellen.
ms.openlocfilehash: c777b9d840e0e9e467c1283fff94eca9a061ee73
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925552"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="8641a-103">Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen</span><span class="sxs-lookup"><span data-stu-id="8641a-103">Let users reset their own passwords</span></span>

<span data-ttu-id="8641a-104">Als Microsoft 365-beheerder kunt u [](https://go.microsoft.com/fwlink/p/?LinkId=522677) instellen dat personen zelf het hulpprogramma voor het opnieuw instellen van wachtwoorden kunnen gebruiken, zodat u hun wachtwoorden niet opnieuw hoeft in te stellen.</span><span class="sxs-lookup"><span data-stu-id="8641a-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="8641a-105">Zo hoeft u zelf minder te doen!</span><span class="sxs-lookup"><span data-stu-id="8641a-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="8641a-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="8641a-106">Before you begin</span></span>
  
- <span data-ttu-id="8641a-107">Selfservice voor wachtwoordreset voor cloudgebruikers **is** gratis bij een betaald abonnement op Microsoft 365 Business, Education of Nonprofit.</span><span class="sxs-lookup"><span data-stu-id="8641a-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="8641a-108">Dit werkt niet in de proefversie van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8641a-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="8641a-p103">Deze maakt gebruik van Azure. Deze functie ontvangt u in Azure automatisch **gratis** wanneer u deze stappen uitvoert. Het kost u niets als u selfservice voor wachtwoordherstel inschakelt als u geen andere Azure-functies gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8641a-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="8641a-p104">**Als u on-premises Active Directory gebruikt**, zijn de twee bovenstaande punten niet van toepassing. U kunt dit instellen, maar **u hebt hiervoor wel een betaald abonnement op Azure AD Premium nodig**.</span><span class="sxs-lookup"><span data-stu-id="8641a-p104">**If you're using an on-premises Active Directory**, the above two points don't apply. Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="8641a-114">Dit artikel is bedoeld voor personen die het wachtwoordverloopbeleid voor een bedrijf, school of non-profitorganisatie opstellen.</span><span class="sxs-lookup"><span data-stu-id="8641a-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="8641a-115">Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="8641a-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="8641a-116">Wat is een beheerdersaccount?</span><span class="sxs-lookup"><span data-stu-id="8641a-116">What's an admin account?</span></span>](../admin-overview/admin-overview.md)

<span data-ttu-id="8641a-117">U moet een globale [beheerder of wachtwoordbeheerder zijn om](about-admin-roles.md) deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8641a-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="8641a-118">Bekijken: Gebruikers hun eigen wachtwoorden opnieuw laten instellen</span><span class="sxs-lookup"><span data-stu-id="8641a-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="8641a-119">Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="8641a-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="8641a-120">Stappen: Personen hun eigen wachtwoorden opnieuw laten instellen</span><span class="sxs-lookup"><span data-stu-id="8641a-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="8641a-121">Met deze stappen wordt selfservice voor wachtwoordherstel ingeschakeld voor iedereen in uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="8641a-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="8641a-122">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">het beheercentrum</a>naar de pagina **Instellingen** > **organisatie-instellingen.**</span><span class="sxs-lookup"><span data-stu-id="8641a-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8641a-123">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">het beheercentrum</a>naar de  \> **privacypagina Beveiliging &amp; instellingen.**</span><span class="sxs-lookup"><span data-stu-id="8641a-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8641a-124">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">het beheercentrum</a>naar de **privacypagina** \> **Instellingen** \> **&amp; beveiligingsinstellingen.**</span><span class="sxs-lookup"><span data-stu-id="8641a-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="8641a-125">Selecteer boven aan de pagina **Organisatie-instellingen** het tabblad **& privacy.**</span><span class="sxs-lookup"><span data-stu-id="8641a-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="8641a-126">Selecteer **Selfservice voor wachtwoord opnieuw instellen.**</span><span class="sxs-lookup"><span data-stu-id="8641a-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="8641a-127">Selecteer **onder Selfservice voor wachtwoord opnieuw instellen** de optie Ga naar Azure Portal om selfservice voor wachtwoord opnieuw instellen in te **stellen.**</span><span class="sxs-lookup"><span data-stu-id="8641a-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="8641a-128">Selecteer gebruikers in het linkernavigatiedeelvenster en selecteer vervolgens op **het | Pagina Alle gebruikers,** selecteer **Wachtwoord opnieuw instellen.**</span><span class="sxs-lookup"><span data-stu-id="8641a-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="8641a-129">Selecteer Op **de pagina** Eigenschappen de optie **Alles om** dit in te stellen voor iedereen in uw bedrijf en selecteert u **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="8641a-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="8641a-130">Wanneer uw gebruikers zich aanmelden, wordt hun gevraagd aanvullende contactgegevens op te geven zodat ze hun wachtwoord in de toekomst opnieuw kunnen instellen.</span><span class="sxs-lookup"><span data-stu-id="8641a-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="8641a-131">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8641a-131">Related content</span></span>

[<span data-ttu-id="8641a-132">Het wachtwoordverloopbeleid voor uw organisatie instellen:</span><span class="sxs-lookup"><span data-stu-id="8641a-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="8641a-133">Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="8641a-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="8641a-134">Trainingsvideo's voor Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="8641a-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
