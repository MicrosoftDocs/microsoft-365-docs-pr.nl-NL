---
title: Uw beheerdersaccounts beveiligen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Meer informatie over het instellen en beveiligen van uw beheerdersaccounts.
ms.openlocfilehash: b74d9d2d69549bcaa476a346ba2a61fc24e0b3f3
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808793"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="7b051-103">Uw beheerdersaccounts beveiligen</span><span class="sxs-lookup"><span data-stu-id="7b051-103">Protect your administrator accounts</span></span>

<span data-ttu-id="7b051-104">Omdat admin-accounts worden geleverd met verhoogde privileges, ze zijn waardevolle doelwitten voor hackers en cybercriminelen.</span><span class="sxs-lookup"><span data-stu-id="7b051-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="7b051-105">In dit artikel wordt beschreven:</span><span class="sxs-lookup"><span data-stu-id="7b051-105">This article describes:</span></span>

- <span data-ttu-id="7b051-106">Hoe maak je een extra beheerdersaccount voor noodgevallen in.</span><span class="sxs-lookup"><span data-stu-id="7b051-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="7b051-107">Hoe deze accounts te beschermen.</span><span class="sxs-lookup"><span data-stu-id="7b051-107">How to protect these accounts.</span></span>
 
<span data-ttu-id="7b051-108">Wanneer u zich aanmeldt voor Microsoft 365 Business en uw gegevens invoert, wordt u automatisch de globale beheerder. Een globale beheerder heeft de ultieme controle over gebruikersaccounts en alle andere instellingen in het Microsoft-beheercentrum, maar er zijn veel verschillende soorten beheerdersaccounts met verschillende mate van toegang.</span><span class="sxs-lookup"><span data-stu-id="7b051-108">When you sign up for Microsoft 365 Business and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="7b051-109">Zie [over beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor informatie over de verschillende toegangsniveaus voor elk type beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="7b051-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>


## <a name="create-additional-admin-accounts"></a><span data-ttu-id="7b051-110">Extra beheerdersaccounts maken</span><span class="sxs-lookup"><span data-stu-id="7b051-110">Create additional admin accounts</span></span>

<span data-ttu-id="7b051-111">Gebruik alleen beheerdersaccounts voor beheer.</span><span class="sxs-lookup"><span data-stu-id="7b051-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="7b051-112">Beheerders moeten een apart gebruikersaccount hebben voor regelmatig gebruik van Office-apps en alleen hun beheerdersaccount gebruiken wanneer dat nodig is om accounts en apparaten te beheren en terwijl ze aan andere beheerfuncties werken.</span><span class="sxs-lookup"><span data-stu-id="7b051-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="7b051-113">Het is ook een goed idee om de Microsoft 365 Business-licentie te verwijderen uit de beheerdersaccounts, zodat u er niet voor hoeft te betalen.</span><span class="sxs-lookup"><span data-stu-id="7b051-113">It's also a good idea to remove the Microsoft 365 Business license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="7b051-114">U wilt ten minste één extra globale beheerdersaccount instellen om beheerders toegang te geven tot een andere vertrouwde werknemer.</span><span class="sxs-lookup"><span data-stu-id="7b051-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="7b051-115">U ook afzonderlijke beheerdersaccounts voor gebruikersbeheer maken (deze rol heet **Beheerder gebruikersbeheer).**</span><span class="sxs-lookup"><span data-stu-id="7b051-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="7b051-116">Zie voor meer informatie [over beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="7b051-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="7b051-117">Ga als volgt te werk om extra beheerdersaccounts te maken:</span><span class="sxs-lookup"><span data-stu-id="7b051-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="7b051-118">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">beheercentrum</a> en kies **Gebruikers** \> **actieve gebruikers** in de linkernavigatie.</span><span class="sxs-lookup"><span data-stu-id="7b051-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Gebruikers kiezen en vervolgens Actieve gebruikers in de linkernavigatie](../media/Activeusers.png)

2. <span data-ttu-id="7b051-120">Selecteer op de pagina **Actieve gebruikers** de optie Een gebruiker boven aan de pagina **toevoegen** en voer in het deelvenster **Nieuwe gebruikers** de naam en andere informatie in.</span><span class="sxs-lookup"><span data-stu-id="7b051-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="7b051-121">Vouw de sectie **Rollen** uit en kies **Globale beheerder** om deze gebruikersglobale beheerder toegang te geven.</span><span class="sxs-lookup"><span data-stu-id="7b051-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="7b051-122">U ook **aangepaste beheerder** kiezen en een van de rollen kiezen die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7b051-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="7b051-123">Voer een alternatieve e-mail in het tekstvak **Alternatief e-mailadres** in.</span><span class="sxs-lookup"><span data-stu-id="7b051-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="7b051-124">U dit adres gebruiken om uw wachtwoordgegevens te herstellen als u buitengesloten wordt. Voor globale beheerders wordt ook een factuuroverzicht naar dit adres verzonden.</span><span class="sxs-lookup"><span data-stu-id="7b051-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![De beheerdersrol kiezen](../media/adminroles.png)
    
4. <span data-ttu-id="7b051-126">Verplaats in de sectie **Productlicenties** de kiezer voor **Microsoft 365 Business** naar **Uit** en de gebruiker maken **zonder productlicentie** naar **Aan.**</span><span class="sxs-lookup"><span data-stu-id="7b051-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Kies de productlicentie](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="7b051-128">Een noodbeheerdersaccount maken</span><span class="sxs-lookup"><span data-stu-id="7b051-128">Create an emergency admin account</span></span>

<span data-ttu-id="7b051-129">U moet ook een back-upaccount maken dat niet is ingesteld met multi-factor authenticatie (MFA), zodat u uzelf niet per ongeluk buitensluit (bijvoorbeeld als u uw telefoon verliest die u als tweede verificatieformulier gebruikt).</span><span class="sxs-lookup"><span data-stu-id="7b051-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="7b051-130">Zorg ervoor dat het wachtwoord voor dit account een zin of ten minste 16 tekens lang is.</span><span class="sxs-lookup"><span data-stu-id="7b051-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="7b051-131">Dit wordt vaak aangeduid als een "break-glass account."</span><span class="sxs-lookup"><span data-stu-id="7b051-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="7b051-132">Zelf een gebruikersaccount aanmaken</span><span class="sxs-lookup"><span data-stu-id="7b051-132">Create a user account for yourself</span></span>

<span data-ttu-id="7b051-133">Gebruik uw gebruikersaccount om deel te nemen in samenwerking met uw organisatie, inclusief het controleren van e-mail.</span><span class="sxs-lookup"><span data-stu-id="7b051-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="7b051-134">Dit betekent dat uw beheerdersreferenties vergelijkbaar kunnen zijn met *<span></span>Alice.Chavez @Contoso.org* en dat uw gewone gebruikersaccount mogelijk vergelijkbaar is met *Alice<span></span>@Contoso.com*.</span><span class="sxs-lookup"><span data-stu-id="7b051-134">This means your admin credentials might be similar to  *Alice.Chavez<span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="7b051-135">Ga als lid van het volgende over een nieuw gebruikersaccount:</span><span class="sxs-lookup"><span data-stu-id="7b051-135">To create a new user account:</span></span>
1. <span data-ttu-id="7b051-136">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">beheercentrum</a> en kies **Gebruikers** \> **actieve gebruikers** in de linkernavigatie.</span><span class="sxs-lookup"><span data-stu-id="7b051-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="7b051-137">Selecteer op de pagina **Actieve gebruikers** de optie Een gebruiker boven aan de pagina **toevoegen** en voer in het deelvenster **Nieuwe gebruikers** de naam en andere informatie in.</span><span class="sxs-lookup"><span data-stu-id="7b051-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="7b051-138">Vouw de sectie **Rollen** uit en kies **Gebruiker (geen beheerderstoegang)**.</span><span class="sxs-lookup"><span data-stu-id="7b051-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
1. <span data-ttu-id="7b051-139">Verplaats in de sectie **Productlicenties** de kiezer voor **Microsoft 365 Business** naar **Aan**.</span><span class="sxs-lookup"><span data-stu-id="7b051-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span> 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="7b051-140">Registreer elk van deze accounts voor multi-factor authenticatie</span><span class="sxs-lookup"><span data-stu-id="7b051-140">Register each of these accounts for multi-factor authentication</span></span>


## <a name="additional-recommendations"></a><span data-ttu-id="7b051-141">Aanvullende aanbevelingen</span><span class="sxs-lookup"><span data-stu-id="7b051-141">Additional recommendations</span></span>

- <span data-ttu-id="7b051-142">Zorg ervoor dat beheerdersaccounts ook zijn ingesteld voor meervoudige verificatie.</span><span class="sxs-lookup"><span data-stu-id="7b051-142">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="7b051-143">We laten u zien hoe u dit doet in [Beleid voor voorwaardelijke toegang configureren.](m365-campaigns-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="7b051-143">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="7b051-144">Sluit voordat u beheerdersaccounts gebruikt alle niet-gerelateerde browsersessies en -apps, inclusief persoonlijke e-mailaccounts.</span><span class="sxs-lookup"><span data-stu-id="7b051-144">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="7b051-145">U ook privé- of incognitobrowservensters gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7b051-145">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="7b051-146">Nadat u beheerderstaken hebt voltooid, moet u zich afmelden bij de browsersessie.</span><span class="sxs-lookup"><span data-stu-id="7b051-146">After completing admin tasks, be sure to sign out of the browser session.</span></span>
