---
title: Samenwerken met gasten op een site
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over het samenwerken met gasten in een SharePoint-site.
ms.openlocfilehash: 3a7c14cc4cd31961b0d4c1054f88b5ed276b3b1a
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2020
ms.locfileid: "42811099"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="ac2ce-103">Samenwerken met gasten op een site</span><span class="sxs-lookup"><span data-stu-id="ac2ce-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="ac2ce-104">Als u met gasten wilt samenwerken in alle documenten, gegevens en lijsten, u een SharePoint-site gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="ac2ce-105">Moderne SharePoint-sites zijn verbonden met Office 365-groepen die het sitelidmaatschap kunnen beheren en aanvullende samenwerkingstools kunnen bieden, zoals een gedeeld postvak en agenda.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-105">Modern SharePoint sites are connected to Office 365 Groups which can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="ac2ce-106">In dit artikel doorlopen we de Microsoft 365-configuratiestappen die nodig zijn om een SharePoint-site in te stellen voor samenwerking met gasten.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="ac2ce-107">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="ac2ce-107">Video demonstration</span></span>

<span data-ttu-id="ac2ce-108">In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="ac2ce-109">Instellingen voor Azure-organisatierelaties</span><span class="sxs-lookup"><span data-stu-id="ac2ce-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="ac2ce-110">Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de instellingen voor organisatierelaties in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-110">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="ac2ce-111">Als het delen van gasten is uitgeschakeld of beperkt in Azure AD, worden alle instellingen voor delen die u configureert in Microsoft 365 overschreven.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="ac2ce-112">Controleer de instellingen voor organisatorische relaties om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de pagina Instellingen voor Azure Active Directory-organisatierelaties](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="ac2ce-114">Instellingen voor organisatierelaties instellen</span><span class="sxs-lookup"><span data-stu-id="ac2ce-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="ac2ce-115">Meld u aan [https://portal.azure.com](https://portal.azure.com)bij Microsoft Azure op .</span><span class="sxs-lookup"><span data-stu-id="ac2ce-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="ac2ce-116">Klik in de linkernavigatie op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="ac2ce-117">Klik in het deelvenster **Overzicht** op **Organisatierelaties**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="ac2ce-118">Klik in het deelvenster **Organisatierelaties** op **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="ac2ce-119">Zorg ervoor dat **beheerders en gebruikers in de gastuitnodigingsrol kunnen uitnodigen** en dat leden kunnen **uitnodigen,** beide zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="ac2ce-120">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="ac2ce-121">Let op de instellingen in de sectie **Samenwerkingsbeperkingen.**</span><span class="sxs-lookup"><span data-stu-id="ac2ce-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="ac2ce-122">Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="office-365-groups-guest-settings"></a><span data-ttu-id="ac2ce-123">Gastinstellingen voor Office 365-groepen</span><span class="sxs-lookup"><span data-stu-id="ac2ce-123">Office 365 Groups guest settings</span></span>

<span data-ttu-id="ac2ce-124">Moderne SharePoint-sites gebruiken Office 365-groepen om de toegang tot de site te beheren.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-124">Modern SharePoint sites use Office 365 Groups to control site access.</span></span> <span data-ttu-id="ac2ce-125">De gastinstellingen van Office 365-groepen moeten zijn ingeschakeld om gasttoegang in SharePoint-sites te laten werken.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-125">The Office 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Schermafbeelding van gastinstellingen van Office 365-groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="ac2ce-127">Gastinstellingen voor Office 365-groepen instellen</span><span class="sxs-lookup"><span data-stu-id="ac2ce-127">To set Office 365 Groups guest settings</span></span>

1. <span data-ttu-id="ac2ce-128">Vouw in het Microsoft 365-beheercentrum in de linkernavigatie **instellingen**uit .</span><span class="sxs-lookup"><span data-stu-id="ac2ce-128">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="ac2ce-129">Klik **op Services &-invoegtoepassing .**</span><span class="sxs-lookup"><span data-stu-id="ac2ce-129">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="ac2ce-130">Klik in de lijst op **Office 365-groepen**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-130">In the list, click **Office 365 Groups**.</span></span>
4. <span data-ttu-id="ac2ce-131">Zorg ervoor dat de **groepsleden buiten uw organisatie toegang krijgen tot groepsinhoud** en **groepseigenaren mensen buiten uw organisatie toevoegen aan de** selectievakjes groepen, beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-131">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="ac2ce-132">Als u wijzigingen hebt aangebracht, klikt u op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-132">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="ac2ce-133">Instellingen voor delen van SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="ac2ce-133">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="ac2ce-134">Om ervoor te zorgen dat gasten toegang hebben tot SharePoint-sites, moeten de instellingen voor delen op SharePoint-organisatieniveau het delen met gasten mogelijk maken.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-134">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="ac2ce-135">De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-135">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="ac2ce-136">Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-136">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="ac2ce-137">Als u het delen van niet-geverifieerde bestanden en mappen wilt toestaan, kiest u **Iedereen**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-137">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="ac2ce-138">Als u ervoor wilt zorgen dat alle mensen buiten uw organisatie zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="ac2ce-138">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="ac2ce-139">Kies de meest tolerante instelling die nodig is voor elke site in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-139">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van sharepoint-instellingen voor delen op organisatieniveau](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="ac2ce-141">Instellingen voor delen van SharePoint-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="ac2ce-141">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="ac2ce-142">Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-142">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="ac2ce-143">Klik in het SharePoint-beheercentrum in de linkernavigatie op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-143">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="ac2ce-144">Controleer of extern delen voor SharePoint is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="ac2ce-144">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="ac2ce-145">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-145">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="ac2ce-146">Een site maken</span><span class="sxs-lookup"><span data-stu-id="ac2ce-146">Create a site</span></span>

<span data-ttu-id="ac2ce-147">De volgende stap is het maken van de site die u van plan bent te gebruiken om samen te werken met gasten.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-147">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="ac2ce-148">Een site maken</span><span class="sxs-lookup"><span data-stu-id="ac2ce-148">To create a site</span></span>
1. <span data-ttu-id="ac2ce-149">Klik in het SharePoint-beheercentrum onder **Sites**op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-149">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="ac2ce-150">Klik **op Maken**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-150">Click **Create**.</span></span>
3. <span data-ttu-id="ac2ce-151">Klik **op Teamsite**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-151">Click **Team site**.</span></span>
4. <span data-ttu-id="ac2ce-152">Typ een sitenaam en voer een naam in voor de eigenaar van de groep (site-eigenaar).</span><span class="sxs-lookup"><span data-stu-id="ac2ce-152">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="ac2ce-153">Kies **onder Geavanceerde instellingen**of u wilt dat dit een openbare of privésite is.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-153">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="ac2ce-154">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-154">Click **Next**.</span></span>
7. <span data-ttu-id="ac2ce-155">Klik op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-155">Click **Finish**.</span></span>

<span data-ttu-id="ac2ce-156">We nodigen gebruikers later uit.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-156">We'll invite users later.</span></span> <span data-ttu-id="ac2ce-157">Vervolgens is het belangrijk om de instellingen voor het delen op siteniveau voor deze site te controleren.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-157">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="ac2ce-158">Instellingen voor delen op SharePoint-siteniveau</span><span class="sxs-lookup"><span data-stu-id="ac2ce-158">SharePoint site level sharing settings</span></span>

<span data-ttu-id="ac2ce-159">Controleer de instellingen voor delen op siteniveau om ervoor te zorgen dat deze toegang voor deze site mogelijk maken.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-159">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="ac2ce-160">Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **Iedereen,** maar u wilt dat alle gasten zich voor deze site verifiëren, controleert u of de instellingen voor delen op siteniveau zijn ingesteld op **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="ac2ce-160">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="ac2ce-161">Houd er rekening mee dat de site niet kan worden gedeeld met niet-geverifieerde personen **(Instellingen voor iedereen),** maar afzonderlijke bestanden en mappen wel.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-161">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![Schermafbeelding van instellingen voor extern delen van SharePoint-site](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="ac2ce-163">Instellingen voor delen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="ac2ce-163">To set site-level sharing settings</span></span>
1. <span data-ttu-id="ac2ce-164">Vouw in het SharePoint-beheercentrum in de linkernavigatie **Sites** uit en klik op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-164">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="ac2ce-165">Selecteer de site die u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-165">Select the site that you just created.</span></span>
3. <span data-ttu-id="ac2ce-166">Klik op het lint op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-166">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="ac2ce-167">Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="ac2ce-167">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="ac2ce-168">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-168">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="ac2ce-169">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="ac2ce-169">Invite users</span></span>

<span data-ttu-id="ac2ce-170">Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u beginnen met het toevoegen van interne gebruikers en gasten aan uw site.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-170">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="ac2ce-171">Toegang tot de site wordt beheerd via de bijbehorende Office 365-groep, dus we voegen daar gebruikers toe.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-171">Site access is controlled through the associated Office 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="ac2ce-172">Interne gebruikers uitnodigen voor een groep</span><span class="sxs-lookup"><span data-stu-id="ac2ce-172">To invite internal users to a group</span></span>
1. <span data-ttu-id="ac2ce-173">Navigeer naar de site waar u gebruikers wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-173">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="ac2ce-174">Klik rechtsboven op **Leden.**</span><span class="sxs-lookup"><span data-stu-id="ac2ce-174">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="ac2ce-175">Klik **op Leden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-175">Click **Add members**.</span></span>
4. <span data-ttu-id="ac2ce-176">Typ de namen of e-mailadressen van de gebruikers die u wilt uitnodigen voor de site en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-176">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="ac2ce-177">Gastgebruikers kunnen niet worden toegevoegd vanaf de site.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-177">Guest users can't be added from the site.</span></span> <span data-ttu-id="ac2ce-178">U moet ze toevoegen met de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-178">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="ac2ce-179">Gasten uitnodigen voor een groep</span><span class="sxs-lookup"><span data-stu-id="ac2ce-179">To invite guests to a group</span></span>
1. <span data-ttu-id="ac2ce-180">Klik in de webversie van Outlook onder **Groepen**op de groep waar u leden wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-180">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="ac2ce-181">Open het groepsvisitekaartje en klik onder **Meer opties** (...)op **Leden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-181">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="ac2ce-182">Typ de e-mailadressen van de gasten die u wilt uitnodigen en klik op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-182">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="ac2ce-183">Klik **op Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="ac2ce-183">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac2ce-184">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ac2ce-184">See Also</span></span>

[<span data-ttu-id="ac2ce-185">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="ac2ce-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="ac2ce-186">Onbedoelde blootstelling aan bestanden beperken wanneer u met gasten deelt</span><span class="sxs-lookup"><span data-stu-id="ac2ce-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="ac2ce-187">Een veilige omgeving voor het delen van gasten maken</span><span class="sxs-lookup"><span data-stu-id="ac2ce-187">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="ac2ce-188">Maak een B2B extranet met managed guests</span><span class="sxs-lookup"><span data-stu-id="ac2ce-188">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

