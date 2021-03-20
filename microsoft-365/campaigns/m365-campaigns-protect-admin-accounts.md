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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Meer informatie over het instellen en beveiligen van uw beheerdersaccounts.
ms.openlocfilehash: ec5b971ba4f1fdc8834e10ddf90ff219f763f805
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912172"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="114bf-103">Uw beheerdersaccounts beveiligen</span><span class="sxs-lookup"><span data-stu-id="114bf-103">Protect your administrator accounts</span></span>

<span data-ttu-id="114bf-104">Aangezien beheerdersaccounts met verhoogde bevoegdheden worden gebruikt, zijn ze waardevolle doelen voor hackers en cybercriminelen.</span><span class="sxs-lookup"><span data-stu-id="114bf-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="114bf-105">In dit artikel wordt het volgende beschreven:</span><span class="sxs-lookup"><span data-stu-id="114bf-105">This article describes:</span></span>

- <span data-ttu-id="114bf-106">Een extra beheerdersaccount instellen voor noodgevallen.</span><span class="sxs-lookup"><span data-stu-id="114bf-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="114bf-107">Deze accounts beveiligen.</span><span class="sxs-lookup"><span data-stu-id="114bf-107">How to protect these accounts.</span></span>

<span data-ttu-id="114bf-108">Wanneer u zich registreert voor Microsoft 365 en uw gegevens in typt, wordt u automatisch de globale beheerder. Een globale beheerder heeft de ultieme controle over gebruikersaccounts en alle andere instellingen in het Microsoft-beheercentrum, maar er zijn veel verschillende soorten beheerdersaccounts met verschillende toegangsgraden.</span><span class="sxs-lookup"><span data-stu-id="114bf-108">When you sign up for Microsoft 365 and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="114bf-109">Zie [beheerdersrollen voor](/office365/admin/add-users/about-admin-roles) informatie over de verschillende toegangsniveaus voor elk type beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="114bf-109">See [about admin roles](/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>

## <a name="create-additional-admin-accounts"></a><span data-ttu-id="114bf-110">Extra beheerdersaccounts maken</span><span class="sxs-lookup"><span data-stu-id="114bf-110">Create additional admin accounts</span></span>

<span data-ttu-id="114bf-111">Beheeraccounts alleen gebruiken voor beheer.</span><span class="sxs-lookup"><span data-stu-id="114bf-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="114bf-112">Beheerders moeten een afzonderlijk gebruikersaccount hebben voor regelmatig gebruik van Office-apps en hun beheeraccount alleen gebruiken wanneer dat nodig is voor het beheren van accounts en apparaten en tijdens het werken aan andere beheerfuncties.</span><span class="sxs-lookup"><span data-stu-id="114bf-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="114bf-113">Het is ook een goed idee om de Microsoft 365-licentie te verwijderen uit de beheerdersaccounts, zodat u er niet voor hoeft te betalen.</span><span class="sxs-lookup"><span data-stu-id="114bf-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="114bf-114">U wilt ten minste één extra globale beheerdersaccount instellen om beheerder toegang te geven tot een andere vertrouwde werknemer.</span><span class="sxs-lookup"><span data-stu-id="114bf-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="114bf-115">U kunt ook afzonderlijke beheerdersaccounts maken voor gebruikersbeheer (deze rol wordt **beheerder gebruikersbeheer genoemd).**</span><span class="sxs-lookup"><span data-stu-id="114bf-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="114bf-116">Zie beheerdersrollen [voor meer informatie.](/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="114bf-116">For more information, see [about admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="114bf-117">Extra beheerdersaccounts maken:</span><span class="sxs-lookup"><span data-stu-id="114bf-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="114bf-118">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">beheercentrum en</a> kies **gebruikers actieve** \> **gebruikers** in het linkernavigatienavigatiepunt.</span><span class="sxs-lookup"><span data-stu-id="114bf-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Kies Gebruikers en vervolgens Actieve gebruikers in de linkernavigatiebalk](../media/Activeusers.png)

 2. <span data-ttu-id="114bf-120">Selecteer op **de pagina** Actieve gebruikers de optie Een gebruiker  **toevoegen** boven aan de pagina en voer in het deelvenster Nieuwe gebruiker de naam en andere informatie in.</span><span class="sxs-lookup"><span data-stu-id="114bf-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
 3. <span data-ttu-id="114bf-121">Vouw de **sectie Rollen** uit en kies Globale **beheerder om** deze gebruiker globale beheerderstoegang te geven.</span><span class="sxs-lookup"><span data-stu-id="114bf-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="114bf-122">U kunt ook **Aangepaste beheerder kiezen** en een van de rollen kiezen die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="114bf-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="114bf-123">Voer een alternatief e-mailbericht in het **tekstvak Alternatief e-mailadres** in.</span><span class="sxs-lookup"><span data-stu-id="114bf-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="114bf-124">U kunt dit adres gebruiken om uw wachtwoordgegevens te herstellen als u wordt vergrendeld. Voor globale beheerders wordt ook een factuuroverzicht naar dit adres verzonden.</span><span class="sxs-lookup"><span data-stu-id="114bf-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![De beheerdersrol kiezen](../media/adminroles.png)

 4. <span data-ttu-id="114bf-126">Verplaats in **de sectie Productlicenties** de selector voor **Microsoft 365 Business** naar **Uit** en de gebruiker **zonder productlicentie** maken naar **Aan.**</span><span class="sxs-lookup"><span data-stu-id="114bf-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![De productlicentie kiezen](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="114bf-128">Een account voor noodgevallenbeheerder maken</span><span class="sxs-lookup"><span data-stu-id="114bf-128">Create an emergency admin account</span></span>

<span data-ttu-id="114bf-129">U moet ook een back-upaccount maken dat niet is ingesteld met meervoudige verificatie (MFA), zodat u uzelf niet per ongeluk vergrendelt (bijvoorbeeld als u uw telefoon verliest die u gebruikt als een tweede verificatieformulier).</span><span class="sxs-lookup"><span data-stu-id="114bf-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="114bf-130">Zorg ervoor dat het wachtwoord voor dit account een woordgroep of ten minste 16 tekens lang is.</span><span class="sxs-lookup"><span data-stu-id="114bf-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="114bf-131">Dit wordt vaak een 'break-glass account' genoemd.</span><span class="sxs-lookup"><span data-stu-id="114bf-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="114bf-132">Een gebruikersaccount voor uzelf maken</span><span class="sxs-lookup"><span data-stu-id="114bf-132">Create a user account for yourself</span></span>

<span data-ttu-id="114bf-133">Gebruik uw gebruikersaccount om deel te nemen aan samenwerking met uw organisatie, inclusief het controleren van e-mail.</span><span class="sxs-lookup"><span data-stu-id="114bf-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="114bf-134">Dit betekent dat uw beheerdersreferenties vergelijkbaar kunnen zijn met *De <span></span> @Contoso.org van Alice.Chavez* en dat uw gewone gebruikersaccount vergelijkbaar kan zijn met *De <span></span> @Contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="114bf-134">This means your admin credentials might be similar to  *Alice.Chavez <span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="114bf-135">Een nieuw gebruikersaccount maken:</span><span class="sxs-lookup"><span data-stu-id="114bf-135">To create a new user account:</span></span>

1. <span data-ttu-id="114bf-136">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">beheercentrum en</a> kies **gebruikers actieve** \> **gebruikers** in het linkernavigatienavigatiepunt.</span><span class="sxs-lookup"><span data-stu-id="114bf-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="114bf-137">Selecteer op **de pagina** Actieve gebruikers de optie Een gebruiker  **toevoegen** boven aan de pagina en voer in het deelvenster Nieuwe gebruiker de naam en andere informatie in.</span><span class="sxs-lookup"><span data-stu-id="114bf-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="114bf-138">Vouw de **sectie Rollen** uit en kies **Gebruiker (geen beheerderstoegang).**</span><span class="sxs-lookup"><span data-stu-id="114bf-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
4. <span data-ttu-id="114bf-139">Verplaats in **de sectie Productlicenties** de selector voor **Microsoft 365 Business** naar **Aan.**</span><span class="sxs-lookup"><span data-stu-id="114bf-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span>

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="114bf-140">Elk van deze accounts registreren voor meervoudige verificatie</span><span class="sxs-lookup"><span data-stu-id="114bf-140">Register each of these accounts for multi-factor authentication</span></span>

<span data-ttu-id="114bf-141">Zorg ervoor dat deze accounts meervoudige [verificatie gebruiken.](m365-campaigns-multifactor-authenication.md)</span><span class="sxs-lookup"><span data-stu-id="114bf-141">Make sure these accounts are using [multifactor authentication](m365-campaigns-multifactor-authenication.md).</span></span>

## <a name="additional-recommendations"></a><span data-ttu-id="114bf-142">Aanvullende aanbevelingen</span><span class="sxs-lookup"><span data-stu-id="114bf-142">Additional recommendations</span></span>

- <span data-ttu-id="114bf-143">Zorg ervoor dat beheerdersaccounts ook zijn ingesteld voor meervoudige verificatie.</span><span class="sxs-lookup"><span data-stu-id="114bf-143">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="114bf-144">We laten u zien hoe u dit doet in [Beleid voor voorwaardelijke toegang configureren.](m365-campaigns-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="114bf-144">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="114bf-145">Sluit alle niet-gerelateerde browsersessies en -apps, inclusief persoonlijke e-mailaccounts, voordat u beheerdersaccounts gebruikt.</span><span class="sxs-lookup"><span data-stu-id="114bf-145">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="114bf-146">U kunt ook in privé- of incognitobrowservensters gebruiken.</span><span class="sxs-lookup"><span data-stu-id="114bf-146">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="114bf-147">Nadat u beheerderstaken heeft uitgevoerd, moet u zich af melden bij de browsersessie.</span><span class="sxs-lookup"><span data-stu-id="114bf-147">After completing admin tasks, be sure to sign out of the browser session.</span></span>