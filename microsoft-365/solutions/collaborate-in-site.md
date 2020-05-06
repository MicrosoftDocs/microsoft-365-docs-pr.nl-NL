---
title: Samenwerken met gasten op een site
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
ms.custom:
- M365solutions
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over de Microsoft 365-configuratiestappen die nodig zijn om een SharePoint-site in te stellen voor samenwerking met gasten.
ms.openlocfilehash: f79846de5d4fd8661205e549db3457a7696e9770
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035993"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="c79d8-103">Samenwerken met gasten op een site</span><span class="sxs-lookup"><span data-stu-id="c79d8-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="c79d8-104">Als u met gasten wilt samenwerken in alle documenten, gegevens en lijsten, u een SharePoint-site gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c79d8-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="c79d8-105">Moderne SharePoint-sites zijn verbonden met Microsoft 365-groepen en kunnen het sitelidmaatschap beheren en aanvullende samenwerkingstools bieden, zoals een gedeeld postvak en agenda.</span><span class="sxs-lookup"><span data-stu-id="c79d8-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="c79d8-106">In dit artikel doorlopen we de Microsoft 365-configuratiestappen die nodig zijn om een SharePoint-site in te stellen voor samenwerking met gasten.</span><span class="sxs-lookup"><span data-stu-id="c79d8-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="c79d8-107">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="c79d8-107">Video demonstration</span></span>

<span data-ttu-id="c79d8-108">In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="c79d8-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="c79d8-109">Instellingen voor Azure-organisatierelaties</span><span class="sxs-lookup"><span data-stu-id="c79d8-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="c79d8-110">Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de instellingen voor organisatierelaties in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c79d8-110">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="c79d8-111">Als het delen van gasten is uitgeschakeld of beperkt in Azure AD, worden alle instellingen voor delen die u configureert in Microsoft 365 overschreven.</span><span class="sxs-lookup"><span data-stu-id="c79d8-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="c79d8-112">Controleer de instellingen voor organisatorische relaties om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="c79d8-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="c79d8-114">Instellingen voor organisatierelaties instellen</span><span class="sxs-lookup"><span data-stu-id="c79d8-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="c79d8-115">Meld u aan [https://portal.azure.com](https://portal.azure.com)bij Microsoft Azure op .</span><span class="sxs-lookup"><span data-stu-id="c79d8-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="c79d8-116">Klik in de linkernavigatie op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="c79d8-117">Klik in het deelvenster **Overzicht** op **Organisatierelaties**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="c79d8-118">Klik in het deelvenster **Organisatierelaties** op **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="c79d8-119">Zorg ervoor dat **beheerders en gebruikers in de gastuitnodigingsrol kunnen uitnodigen** en dat leden kunnen **uitnodigen,** beide zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="c79d8-120">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="c79d8-121">Let op de instellingen in de sectie **Samenwerkingsbeperkingen.**</span><span class="sxs-lookup"><span data-stu-id="c79d8-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="c79d8-122">Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="c79d8-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="c79d8-123">Gastinstellingen voor Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="c79d8-123">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="c79d8-124">Moderne SharePoint-sites gebruiken Microsoft 365-groepen om de toegang tot de site te beheren.</span><span class="sxs-lookup"><span data-stu-id="c79d8-124">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="c79d8-125">De gastinstellingen van Microsoft 365-groepen moeten zijn ingeschakeld om gasttoegang in SharePoint-sites te laten werken.</span><span class="sxs-lookup"><span data-stu-id="c79d8-125">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="c79d8-127">Gastinstellingen voor Microsoft 365-groepen instellen</span><span class="sxs-lookup"><span data-stu-id="c79d8-127">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="c79d8-128">Vouw in het Microsoft 365-beheercentrum in de linkernavigatie **instellingen**uit .</span><span class="sxs-lookup"><span data-stu-id="c79d8-128">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="c79d8-129">Klik **op Services &-invoegtoepassing .**</span><span class="sxs-lookup"><span data-stu-id="c79d8-129">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="c79d8-130">Klik in de lijst op **Microsoft 365-groepen**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-130">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="c79d8-131">Zorg ervoor dat de **groepsleden buiten uw organisatie toegang krijgen tot groepsinhoud** en **groepseigenaren mensen buiten uw organisatie toevoegen aan de** selectievakjes groepen, beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c79d8-131">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="c79d8-132">Als u wijzigingen hebt aangebracht, klikt u op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-132">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="c79d8-133">Instellingen voor delen van SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="c79d8-133">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="c79d8-134">Om ervoor te zorgen dat gasten toegang hebben tot SharePoint-sites, moeten de instellingen voor delen op SharePoint-organisatieniveau het delen met gasten mogelijk maken.</span><span class="sxs-lookup"><span data-stu-id="c79d8-134">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="c79d8-135">De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites.</span><span class="sxs-lookup"><span data-stu-id="c79d8-135">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="c79d8-136">Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="c79d8-136">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="c79d8-137">Als u het delen van niet-geverifieerde bestanden en mappen wilt toestaan, kiest u **Iedereen**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-137">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="c79d8-138">Als u ervoor wilt zorgen dat alle mensen buiten uw organisatie zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="c79d8-138">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="c79d8-139">Kies de meest tolerante instelling die nodig is voor elke site in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c79d8-139">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="c79d8-141">Instellingen voor delen van SharePoint-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="c79d8-141">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="c79d8-142">Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-142">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="c79d8-143">Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-143">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="c79d8-144">Controleer of extern delen voor SharePoint is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="c79d8-144">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="c79d8-145">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-145">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="c79d8-146">Een site maken</span><span class="sxs-lookup"><span data-stu-id="c79d8-146">Create a site</span></span>

<span data-ttu-id="c79d8-147">De volgende stap is het maken van de site die u van plan bent te gebruiken om samen te werken met gasten.</span><span class="sxs-lookup"><span data-stu-id="c79d8-147">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="c79d8-148">Een site maken</span><span class="sxs-lookup"><span data-stu-id="c79d8-148">To create a site</span></span>
1. <span data-ttu-id="c79d8-149">Klik in het SharePoint-beheercentrum onder **Sites** op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-149">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="c79d8-150">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-150">Click **Create**.</span></span>
3. <span data-ttu-id="c79d8-151">Klik **op Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-151">Click **Team site**.</span></span>
4. <span data-ttu-id="c79d8-152">Typ een sitenaam en voer een naam in voor de eigenaar van de groep (site-eigenaar).</span><span class="sxs-lookup"><span data-stu-id="c79d8-152">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="c79d8-153">Kies **onder Geavanceerde instellingen**of u wilt dat dit een openbare of privésite is.</span><span class="sxs-lookup"><span data-stu-id="c79d8-153">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="c79d8-154">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-154">Click **Next**.</span></span>
7. <span data-ttu-id="c79d8-155">Klik op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-155">Click **Finish**.</span></span>

<span data-ttu-id="c79d8-156">We nodigen gebruikers later uit.</span><span class="sxs-lookup"><span data-stu-id="c79d8-156">We'll invite users later.</span></span> <span data-ttu-id="c79d8-157">Vervolgens is het belangrijk om de instellingen voor het delen op siteniveau voor deze site te controleren.</span><span class="sxs-lookup"><span data-stu-id="c79d8-157">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="c79d8-158">Instellingen voor delen op SharePoint-siteniveau</span><span class="sxs-lookup"><span data-stu-id="c79d8-158">SharePoint site level sharing settings</span></span>

<span data-ttu-id="c79d8-159">Controleer de instellingen voor delen op siteniveau om ervoor te zorgen dat deze toegang voor deze site mogelijk maken.</span><span class="sxs-lookup"><span data-stu-id="c79d8-159">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="c79d8-160">Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **Iedereen,** maar u wilt dat alle gasten zich voor deze site verifiëren, controleert u of de instellingen voor delen op siteniveau zijn ingesteld op **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="c79d8-160">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="c79d8-161">Houd er rekening mee dat de site niet kan worden gedeeld met niet-geverifieerde personen **(Instellingen voor iedereen),** maar afzonderlijke bestanden en mappen wel.</span><span class="sxs-lookup"><span data-stu-id="c79d8-161">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="c79d8-163">Instellingen voor delen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="c79d8-163">To set site-level sharing settings</span></span>
1. <span data-ttu-id="c79d8-164">Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-164">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="c79d8-165">Selecteer de site die u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="c79d8-165">Select the site that you just created.</span></span>
3. <span data-ttu-id="c79d8-166">Klik op het lint op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-166">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="c79d8-167">Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="c79d8-167">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="c79d8-168">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-168">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="c79d8-169">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="c79d8-169">Invite users</span></span>

<span data-ttu-id="c79d8-170">Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u beginnen met het toevoegen van interne gebruikers en gasten aan uw site.</span><span class="sxs-lookup"><span data-stu-id="c79d8-170">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="c79d8-171">Toegang tot de site wordt beheerd via de bijbehorende Microsoft 365-groep, dus we voegen daar gebruikers toe.</span><span class="sxs-lookup"><span data-stu-id="c79d8-171">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="c79d8-172">Interne gebruikers uitnodigen voor een groep</span><span class="sxs-lookup"><span data-stu-id="c79d8-172">To invite internal users to a group</span></span>
1. <span data-ttu-id="c79d8-173">Navigeer naar de site waar u gebruikers wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c79d8-173">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="c79d8-174">Klik rechtsboven op **Leden.**</span><span class="sxs-lookup"><span data-stu-id="c79d8-174">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="c79d8-175">Klik **op Leden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-175">Click **Add members**.</span></span>
4. <span data-ttu-id="c79d8-176">Typ de namen of e-mailadressen van de gebruikers die u wilt uitnodigen voor de site en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-176">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="c79d8-177">Gastgebruikers kunnen niet worden toegevoegd vanaf de site.</span><span class="sxs-lookup"><span data-stu-id="c79d8-177">Guest users can't be added from the site.</span></span> <span data-ttu-id="c79d8-178">U moet ze toevoegen met de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="c79d8-178">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="c79d8-179">Gasten uitnodigen voor een groep</span><span class="sxs-lookup"><span data-stu-id="c79d8-179">To invite guests to a group</span></span>
1. <span data-ttu-id="c79d8-180">Klik in de webversie van Outlook onder **Groepen**op de groep waar u leden wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c79d8-180">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="c79d8-181">Open het groepsvisitekaartje en klik onder **Meer opties** (...)op **Leden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-181">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="c79d8-182">Typ de e-mailadressen van de gasten die u wilt uitnodigen en klik op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-182">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="c79d8-183">Klik **op Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-183">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c79d8-184">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c79d8-184">See Also</span></span>

[<span data-ttu-id="c79d8-185">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="c79d8-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="c79d8-186">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="c79d8-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="c79d8-187">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="c79d8-187">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="c79d8-188">Een B2B-extranet maken met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="c79d8-188">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

