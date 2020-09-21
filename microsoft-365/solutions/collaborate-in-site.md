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
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over de Microsoft 365-configuratiestappen die nodig zijn voor het instellen van een SharePoint-site voor samenwerking met gasten.
ms.openlocfilehash: d5a868e57753a6eb05f74b4873ed64ef0a70878e
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171266"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="5311f-103">Samenwerken met gasten op een site</span><span class="sxs-lookup"><span data-stu-id="5311f-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="5311f-104">Als u wilt samenwerken met gasten in documenten, gegevens en lijsten, kunt u een SharePoint-site gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5311f-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="5311f-105">Moderne SharePoint-sites zijn verbonden met Microsoft 365-groepen en kunnen het sitelidmaatschap beheren en aanvullende samenwerkingsprogramma's, zoals een gedeeld postvak en een agenda, verlenen.</span><span class="sxs-lookup"><span data-stu-id="5311f-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="5311f-106">In dit artikel wordt de configuratiestappen voor Microsoft 365 beschreven die nodig zijn voor het instellen van een SharePoint-site voor samenwerking met gasten.</span><span class="sxs-lookup"><span data-stu-id="5311f-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="5311f-107">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="5311f-107">Video demonstration</span></span>

<span data-ttu-id="5311f-108">In deze video ziet u de configuratiestappen die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="5311f-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="5311f-109">Instellingen van Azure organisatie relaties</span><span class="sxs-lookup"><span data-stu-id="5311f-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="5311f-110">Delen in Microsoft 365 wordt bepaald met het hoogste niveau van de [instellingen voor organisatie relaties in azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="5311f-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="5311f-111">Als gasten delen is uitgeschakeld of niet beschikbaar is in azure AD, worden de instellingen voordelen die u configureert in Microsoft 365 genegeerd.</span><span class="sxs-lookup"><span data-stu-id="5311f-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="5311f-112">Controleer de instellingen voor externe samenwerking om ervoor te zorgen dat delen met gasten niet is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="5311f-112">Check the external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de pagina met instellingen voor externe samenwerking van Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="5311f-114">Externe samenwerkings instellingen instellen:</span><span class="sxs-lookup"><span data-stu-id="5311f-114">To set external collaboration settings:</span></span>


1. <span data-ttu-id="5311f-115">Meld u aan bij Microsoft Azure at [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="5311f-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="5311f-116">Klik in het linkernavigatievenster op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5311f-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="5311f-117">Selecteer **externe identiteiten** , en klik op **instellingen voor externe samenwerking**.</span><span class="sxs-lookup"><span data-stu-id="5311f-117">Select **External Identities** and click on **External collaboration settings**.</span></span>
4. <span data-ttu-id="5311f-118">Zorg er in het deelvenster **instellingen voor gast uitnodigen** voor dat **beheerders en gebruikers in de rol van gast uitnodiging kunnen uitnodigen** en dat **leden kunnen uitnodigen** zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="5311f-118">In the **Guest invite settings** pane, ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
5. <span data-ttu-id="5311f-119">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5311f-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="5311f-120">Let op de instellingen in de sectie **samenwerkings beperkingen** .</span><span class="sxs-lookup"><span data-stu-id="5311f-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="5311f-121">Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="5311f-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="5311f-122">Als u met gasten in meerdere organisaties werkt, is het raadzaam om de toegang van Directory-gegevens te beperken.</span><span class="sxs-lookup"><span data-stu-id="5311f-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="5311f-123">Hiermee kunt u voorkomen dat ze zien welke iemand anders een gast is in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="5311f-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="5311f-124">Als u dit wilt doen, selecteert u onder **toegangsbeperkingen**voor gastgebruikers de optie **gastgebruikers beperkte toegang tot eigenschappen en lidmaatschap van adreslijst objecten** of **toegang voor gastgebruikers is beperkt tot eigenschappen en lidmaatschap van eigen directoryobjecten**.</span><span class="sxs-lookup"><span data-stu-id="5311f-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="5311f-125">Gastinstellingen voor Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="5311f-125">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="5311f-126">Moderne SharePoint-sites gebruikmaken Microsoft 365 groepen om de toegang van de site te beheren.</span><span class="sxs-lookup"><span data-stu-id="5311f-126">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="5311f-127">De gastinstellingen voor Microsoft 365 groepen moeten zijn ingeschakeld voor gasttoegang in SharePoint-sites om te werken.</span><span class="sxs-lookup"><span data-stu-id="5311f-127">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="5311f-129">De gastinstellingen van Microsoft 365 groepen instellen</span><span class="sxs-lookup"><span data-stu-id="5311f-129">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="5311f-130">In het Microsoft 365-Beheercentrum, in het linker navigatiemenu, vouwt u **instellingen**uit.</span><span class="sxs-lookup"><span data-stu-id="5311f-130">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="5311f-131">Klik op **Services & invoegtoepassingen**.</span><span class="sxs-lookup"><span data-stu-id="5311f-131">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="5311f-132">Klik in de lijst op **Microsoft 365 groepen**.</span><span class="sxs-lookup"><span data-stu-id="5311f-132">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="5311f-133">Zorg ervoor dat de selectievakjes **leden van uw organisatie toegang hebben tot de groepsinhoud** van de organisatie en **groepseigenaren personen van buiten uw organisatie toevoegen aan groepen** .</span><span class="sxs-lookup"><span data-stu-id="5311f-133">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="5311f-134">Als u wijzigingen hebt aangebracht, klikt u op **wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5311f-134">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="5311f-135">Instellingen voordelen van SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="5311f-135">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="5311f-136">Als u wilt dat gasten toegang hebben tot SharePoint-sites, moet u de instellingen voordelen van SharePoint op organisatieniveau toestaan voordelen met gasten.</span><span class="sxs-lookup"><span data-stu-id="5311f-136">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="5311f-137">De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites.</span><span class="sxs-lookup"><span data-stu-id="5311f-137">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="5311f-138">Site-instellingen kunnen niet hoger zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="5311f-138">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="5311f-139">Als u niet-geverifieerde bestanden en mappen wilt delen, kiest u **iedereen**.</span><span class="sxs-lookup"><span data-stu-id="5311f-139">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="5311f-140">Als u ervoor wilt zorgen dat alle personen van buiten uw organisatie verificatie hebben, kiest u **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="5311f-140">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="5311f-141">Kies de meest strikte instelling die moet worden gebruikt door alle sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5311f-141">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="5311f-143">Instellingen voordelen van SharePoint-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="5311f-143">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="5311f-144">Klik in het Microsoft 365-Beheercentrum, in het linkernavigatievenster, onder **beheer centra**op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5311f-144">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="5311f-145">Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **delen**.</span><span class="sxs-lookup"><span data-stu-id="5311f-145">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="5311f-146">Zorg ervoor dat extern delen voor SharePoint is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="5311f-146">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="5311f-147">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5311f-147">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="5311f-148">Een site maken</span><span class="sxs-lookup"><span data-stu-id="5311f-148">Create a site</span></span>

<span data-ttu-id="5311f-149">De volgende stap is het maken van de site die u wilt gebruiken om samen te werken met gasten.</span><span class="sxs-lookup"><span data-stu-id="5311f-149">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="5311f-150">Een site maken</span><span class="sxs-lookup"><span data-stu-id="5311f-150">To create a site</span></span>
1. <span data-ttu-id="5311f-151">Klik in het SharePoint-beheercentrum onder **Sites** op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="5311f-151">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="5311f-152">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="5311f-152">Click **Create**.</span></span>
3. <span data-ttu-id="5311f-153">Klik op **team site**.</span><span class="sxs-lookup"><span data-stu-id="5311f-153">Click **Team site**.</span></span>
4. <span data-ttu-id="5311f-154">Typ een naam voor de site en voer een naam in voor de eigenaar van de groep (site-eigenaar).</span><span class="sxs-lookup"><span data-stu-id="5311f-154">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="5311f-155">Kies onder **Geavanceerde instellingen**of u wilt dat dit een openbare of persoonlijke site is.</span><span class="sxs-lookup"><span data-stu-id="5311f-155">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="5311f-156">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="5311f-156">Click **Next**.</span></span>
7. <span data-ttu-id="5311f-157">Klik op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="5311f-157">Click **Finish**.</span></span>

<span data-ttu-id="5311f-158">We nodigen later gebruikers uit.</span><span class="sxs-lookup"><span data-stu-id="5311f-158">We'll invite users later.</span></span> <span data-ttu-id="5311f-159">Vervolgens moet u de instellingen voordelen op siteniveau voor deze site controleren.</span><span class="sxs-lookup"><span data-stu-id="5311f-159">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="5311f-160">Instellingen voordelen op het SharePoint-siteniveau</span><span class="sxs-lookup"><span data-stu-id="5311f-160">SharePoint site level sharing settings</span></span>

<span data-ttu-id="5311f-161">Controleer de instellingen op siteniveau delen om ervoor te zorgen dat ze het gewenste type toegang voor deze site toestaan.</span><span class="sxs-lookup"><span data-stu-id="5311f-161">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="5311f-162">Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **iedereen**, maar u wilt dat alle gasten verificatie voor deze site verifiëren, controleert u of de instellingen voordelen op het siteniveau zijn ingesteld op **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="5311f-162">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="5311f-163">Houd er rekening mee dat de site niet kan worden gedeeld met niet-geverifieerde personen (**iedereen** ), maar ook afzonderlijke bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="5311f-163">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="5311f-165">Instellingen voordelen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="5311f-165">To set site-level sharing settings</span></span>
1. <span data-ttu-id="5311f-166">Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="5311f-166">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="5311f-167">Selecteer de site die u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5311f-167">Select the site that you just created.</span></span>
3. <span data-ttu-id="5311f-168">Klik op het lint op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="5311f-168">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="5311f-169">Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="5311f-169">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="5311f-170">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5311f-170">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="5311f-171">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="5311f-171">Invite users</span></span>

<span data-ttu-id="5311f-172">Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u interne gebruikers en gasten aan uw site kunt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5311f-172">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="5311f-173">De toegang tot de site wordt bestuurd via de bijbehorende Microsoft 365-groep, dus we zullen gebruikers daar toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5311f-173">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="5311f-174">Interne gebruikers voor een groep uitnodigen</span><span class="sxs-lookup"><span data-stu-id="5311f-174">To invite internal users to a group</span></span>
1. <span data-ttu-id="5311f-175">Ga naar de site waaraan u gebruikers wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5311f-175">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="5311f-176">Klik in de rechterbovenhoek op **leden** .</span><span class="sxs-lookup"><span data-stu-id="5311f-176">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="5311f-177">Klik op **leden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5311f-177">Click **Add members**.</span></span>
4. <span data-ttu-id="5311f-178">Typ de namen of e-mailadressen van de gebruikers die u wilt uitnodigen voor de site en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5311f-178">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="5311f-179">Gastgebruikers kunnen niet worden toegevoegd van de site.</span><span class="sxs-lookup"><span data-stu-id="5311f-179">Guest users can't be added from the site.</span></span> <span data-ttu-id="5311f-180">U moet ze toevoegen met de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="5311f-180">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="5311f-181">Gasten voor een groep uitnodigen</span><span class="sxs-lookup"><span data-stu-id="5311f-181">To invite guests to a group</span></span>
1. <span data-ttu-id="5311f-182">Klik in de webversie van Outlook, onder **groepen**, op de groep waaraan u leden wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5311f-182">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="5311f-183">Open het visitekaartje van de groep en klik vervolgens onder **meer opties** (...) op **leden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5311f-183">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="5311f-184">Voer de e-mailadressen in van de gasten die u wilt uitnodigen en klik op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5311f-184">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="5311f-185">Klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="5311f-185">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5311f-186">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5311f-186">See Also</span></span>

[<span data-ttu-id="5311f-187">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="5311f-187">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="5311f-188">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="5311f-188">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="5311f-189">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="5311f-189">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="5311f-190">Een B2B-extranet maken met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="5311f-190">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
