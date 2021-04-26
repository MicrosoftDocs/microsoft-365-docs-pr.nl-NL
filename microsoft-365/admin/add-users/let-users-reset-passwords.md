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
description: Lees hoe u uw wachtwoorden opnieuw kunt instellen met behulp van het hulpprogramma voor het opnieuw instellen van wachtwoorden voor selfservice.
ms.openlocfilehash: 0842430eda8c96647dd12d0da6d0c9e0481346dc
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023759"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="ac356-103">Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen</span><span class="sxs-lookup"><span data-stu-id="ac356-103">Let users reset their own passwords</span></span>

<span data-ttu-id="ac356-104">Als Microsoft 365-beheerder kunt u personen het hulpprogramma voor het opnieuw instellen van wachtwoorden voor [selfservice](https://go.microsoft.com/fwlink/p/?LinkId=522677) laten gebruiken, zodat u geen wachtwoorden opnieuw hoeft in te stellen.</span><span class="sxs-lookup"><span data-stu-id="ac356-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="ac356-105">Zo hoeft u zelf minder te doen!</span><span class="sxs-lookup"><span data-stu-id="ac356-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="ac356-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="ac356-106">Before you begin</span></span>
  
- <span data-ttu-id="ac356-107">U krijgt gratis selfservicewachtwoord  opnieuw instellen voor cloudgebruikers met elk betaald abonnement van Microsoft 365 voor bedrijven, onderwijs of non-profitorganisaties.</span><span class="sxs-lookup"><span data-stu-id="ac356-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="ac356-108">De proefversie van Microsoft 365 werkt niet.</span><span class="sxs-lookup"><span data-stu-id="ac356-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="ac356-p103">Deze maakt gebruik van Azure. Deze functie ontvangt u in Azure automatisch **gratis** wanneer u deze stappen uitvoert. Het kost u niets als u selfservice voor wachtwoordherstel inschakelt als u geen andere Azure-functies gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ac356-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="ac356-p104">**Als u on-premises Active Directory gebruikt**, zijn de twee bovenstaande punten niet van toepassing. U kunt dit instellen, maar **u hebt hiervoor wel een betaald abonnement op Azure AD Premium nodig**.</span><span class="sxs-lookup"><span data-stu-id="ac356-p104">**If you're using an on-premises Active Directory**, the above two points don't apply. Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="ac356-114">Dit artikel is bedoeld voor personen die het wachtwoordverloopbeleid voor een bedrijf, school of non-profitorganisatie opstellen.</span><span class="sxs-lookup"><span data-stu-id="ac356-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="ac356-115">Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="ac356-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="ac356-116">Wat is een beheerdersaccount?</span><span class="sxs-lookup"><span data-stu-id="ac356-116">What's an admin account?</span></span>](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)

<span data-ttu-id="ac356-117">U moet een globale [beheerder of wachtwoordbeheerder zijn om](about-admin-roles.md) deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ac356-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="ac356-118">Kijken: Gebruikers hun eigen wachtwoorden opnieuw laten instellen</span><span class="sxs-lookup"><span data-stu-id="ac356-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="ac356-119">Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="ac356-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="ac356-120">Stappen: Personen hun eigen wachtwoorden opnieuw laten instellen</span><span class="sxs-lookup"><span data-stu-id="ac356-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="ac356-121">Met deze stappen wordt selfservice voor wachtwoordherstel ingeschakeld voor iedereen in uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="ac356-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="ac356-122">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">het beheercentrum</a>naar de pagina **Instellingen** > **organisatie-instellingen.**</span><span class="sxs-lookup"><span data-stu-id="ac356-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ac356-123">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">het beheercentrum</a>naar de **privacypagina** \> **&amp; Beveiligingsinstellingen.**</span><span class="sxs-lookup"><span data-stu-id="ac356-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ac356-124">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">het beheercentrum</a>naar de privacypagina  \> **Instellingen** \> **&amp;** beveiligingsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="ac356-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="ac356-125">Selecteer boven aan de **pagina Organisatie-instellingen** het tabblad **& Privacy.**</span><span class="sxs-lookup"><span data-stu-id="ac356-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="ac356-126">Selecteer **Selfservice Password Reset**.</span><span class="sxs-lookup"><span data-stu-id="ac356-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="ac356-127">Selecteer **onder Selfservice password reset** de optie Ga naar de Azure Portal om **selfservice password reset in te stellen.**</span><span class="sxs-lookup"><span data-stu-id="ac356-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="ac356-128">Selecteer in het linkernavigatiedeelvenster **Gebruikers** en klik vervolgens op **de | Alle gebruikerspagina,** selecteer **Wachtwoord opnieuw instellen.**</span><span class="sxs-lookup"><span data-stu-id="ac356-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="ac356-129">Selecteer Op **de pagina** Eigenschappen de optie **Alles** om dit in te stellen voor iedereen in uw bedrijf en selecteer vervolgens **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="ac356-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="ac356-130">Wanneer uw gebruikers zich aanmelden, wordt hen gevraagd om aanvullende contactgegevens in te voeren, zodat ze hun wachtwoord in de toekomst opnieuw kunnen instellen.</span><span class="sxs-lookup"><span data-stu-id="ac356-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="ac356-131">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ac356-131">Related content</span></span>

[<span data-ttu-id="ac356-132">Het wachtwoordverloopbeleid voor uw organisatie instellen:</span><span class="sxs-lookup"><span data-stu-id="ac356-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="ac356-133">Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="ac356-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="ac356-134">Trainingsvideo's voor Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="ac356-134">Microsoft 365 Business training videos</span></span>](../../business-video/index.yml)
