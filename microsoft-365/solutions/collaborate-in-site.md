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
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over de Microsoft 365-configuratiestappen die nodig zijn voor het instellen van een SharePoint-site voor samenwerking met gasten.
ms.openlocfilehash: 6862fe715fe2f19b968b773bc6df6c70c207a44f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663522"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="01922-103">Samenwerken met gasten op een site</span><span class="sxs-lookup"><span data-stu-id="01922-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="01922-104">Als u wilt samenwerken met gasten in documenten, gegevens en lijsten, kunt u een SharePoint-site gebruiken.</span><span class="sxs-lookup"><span data-stu-id="01922-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="01922-105">Moderne SharePoint-sites zijn verbonden met Microsoft 365-groepen en kunnen het sitelidmaatschap beheren en aanvullende samenwerkingsprogramma's, zoals een gedeeld postvak en een agenda, verlenen.</span><span class="sxs-lookup"><span data-stu-id="01922-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="01922-106">In dit artikel wordt de configuratiestappen voor Microsoft 365 beschreven die nodig zijn voor het instellen van een SharePoint-site voor samenwerking met gasten.</span><span class="sxs-lookup"><span data-stu-id="01922-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="01922-107">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="01922-107">Video demonstration</span></span>

<span data-ttu-id="01922-108">In deze video ziet u de configuratiestappen die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="01922-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="01922-109">Instellingen voor externe samenwerking van Azure</span><span class="sxs-lookup"><span data-stu-id="01922-109">Azure external collaboration settings</span></span>

<span data-ttu-id="01922-110">Delen in Microsoft 365 wordt bepaald door de [instellingen voor B2B External collaboration in azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="01922-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="01922-111">Als gasten delen is uitgeschakeld of niet beschikbaar is in azure AD, worden de instellingen voordelen overschreven die u configureert in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01922-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="01922-112">Controleer de instellingen voor B2B externe samenwerking om ervoor te zorgen dat delen met gasten niet is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="01922-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de pagina met instellingen voor externe samenwerking van Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="01922-114">Externe samenwerkings instellingen instellen</span><span class="sxs-lookup"><span data-stu-id="01922-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="01922-115">Meld u aan bij Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="01922-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="01922-116">Klik in het linker navigatiedeelvenster op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="01922-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="01922-117">Klik op **externe identiteiten**.</span><span class="sxs-lookup"><span data-stu-id="01922-117">Click **External identities**.</span></span>
4. <span data-ttu-id="01922-118">Klik in het scherm aan de **slag** in het linker navigatiedeelvenster op **instellingen voor externe samenwerking**.</span><span class="sxs-lookup"><span data-stu-id="01922-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="01922-119">Zorg ervoor dat **beheerders en gebruikers in de rol gast uitnodiging kunnen uitnodigen** en dat **leden kunnen uitnodigen** zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="01922-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="01922-120">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="01922-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="01922-121">Let op de instellingen in de sectie **samenwerkings beperkingen** .</span><span class="sxs-lookup"><span data-stu-id="01922-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="01922-122">Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="01922-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="01922-123">Als u met gasten in meerdere organisaties werkt, is het raadzaam om de toegang van Directory-gegevens te beperken.</span><span class="sxs-lookup"><span data-stu-id="01922-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="01922-124">Hiermee kunt u voorkomen dat ze zien welke iemand anders een gast is in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="01922-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="01922-125">Als u dit wilt doen, selecteert u onder **toegangsbeperkingen** voor gastgebruikers de optie **gastgebruikers beperkte toegang tot eigenschappen en lidmaatschap van adreslijst objecten** of **toegang voor gastgebruikers is beperkt tot eigenschappen en lidmaatschap van eigen directoryobjecten**.</span><span class="sxs-lookup"><span data-stu-id="01922-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="01922-126">Gastinstellingen voor Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="01922-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="01922-127">Moderne SharePoint-sites gebruikmaken Microsoft 365 groepen om de toegang van de site te beheren.</span><span class="sxs-lookup"><span data-stu-id="01922-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="01922-128">De gastinstellingen voor Microsoft 365 groepen moeten zijn ingeschakeld voor gasttoegang in SharePoint-sites om te werken.</span><span class="sxs-lookup"><span data-stu-id="01922-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="01922-130">De gastinstellingen van Microsoft 365 groepen instellen</span><span class="sxs-lookup"><span data-stu-id="01922-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="01922-131">In het Microsoft 365-Beheercentrum, in het linker navigatiedeelvenster, vouwt u **instellingen** uit.</span><span class="sxs-lookup"><span data-stu-id="01922-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="01922-132">Klik op **instellingen voor organisatie**.</span><span class="sxs-lookup"><span data-stu-id="01922-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="01922-133">Klik in de lijst op **Microsoft 365 groepen**.</span><span class="sxs-lookup"><span data-stu-id="01922-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="01922-134">Zorg ervoor dat de selectievakjes **eigenaren van gebruikers buiten uw organisatie toevoegen aan Microsoft 365-groepen als gasten** en de selectievakjes voor **groepsleden toegang krijgen tot groepsinhoud** beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="01922-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="01922-135">Als u wijzigingen hebt aangebracht, klikt u op **wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="01922-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="01922-136">Instellingen voordelen op SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="01922-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="01922-137">Als u wilt dat gasten toegang hebben tot SharePoint-sites, moet u de instellingen voordelen van SharePoint op organisatieniveau toestaan voordelen met gasten.</span><span class="sxs-lookup"><span data-stu-id="01922-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="01922-138">De instellingen op het niveau van organisatie bepalen de instellingen die beschikbaar zijn voor afzonderlijke sites.</span><span class="sxs-lookup"><span data-stu-id="01922-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="01922-139">Site-instellingen kunnen niet hoger zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="01922-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="01922-140">Als u niet-geverifieerde bestanden en mappen wilt delen, kiest u **iedereen**.</span><span class="sxs-lookup"><span data-stu-id="01922-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="01922-141">Als u ervoor wilt zorgen dat alle personen van buiten uw organisatie verificatie hebben, kiest u **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="01922-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="01922-142">Kies de meest strikte instelling die moet worden gebruikt door alle sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="01922-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="01922-144">Instellingen voordelen van SharePoint op organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="01922-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="01922-145">Klik in het Microsoft 365-Beheercentrum, in het linker navigatiedeelvenster, onder **beheer centra** op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="01922-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="01922-146">Klik in het SharePoint-Beheercentrum, in het linker navigatiedeelvenster, onder **beleid**, op **delen**.</span><span class="sxs-lookup"><span data-stu-id="01922-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="01922-147">Zorg ervoor dat extern delen voor SharePoint is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="01922-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="01922-148">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="01922-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="01922-149">Een site maken</span><span class="sxs-lookup"><span data-stu-id="01922-149">Create a site</span></span>

<span data-ttu-id="01922-150">De volgende stap is het maken van de site die u wilt gebruiken om samen te werken met gasten.</span><span class="sxs-lookup"><span data-stu-id="01922-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="01922-151">Een site maken</span><span class="sxs-lookup"><span data-stu-id="01922-151">To create a site</span></span>
1. <span data-ttu-id="01922-152">Klik in het SharePoint-beheercentrum onder **Sites** op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="01922-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="01922-153">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="01922-153">Click **Create**.</span></span>
3. <span data-ttu-id="01922-154">Klik op **team site**.</span><span class="sxs-lookup"><span data-stu-id="01922-154">Click **Team site**.</span></span>
4. <span data-ttu-id="01922-155">Typ een naam voor de site en voer een naam in voor de eigenaar van de groep (site-eigenaar).</span><span class="sxs-lookup"><span data-stu-id="01922-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="01922-156">Kies onder **Geavanceerde instellingen** of u deze site een openbare of persoonlijke versie wilt maken.</span><span class="sxs-lookup"><span data-stu-id="01922-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="01922-157">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="01922-157">Click **Next**.</span></span>
7. <span data-ttu-id="01922-158">Klik op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="01922-158">Click **Finish**.</span></span>

<span data-ttu-id="01922-159">We nodigen later gebruikers uit.</span><span class="sxs-lookup"><span data-stu-id="01922-159">We'll invite users later.</span></span> <span data-ttu-id="01922-160">Vervolgens moet u de instellingen voordelen op siteniveau voor deze site controleren.</span><span class="sxs-lookup"><span data-stu-id="01922-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="01922-161">Instellingen voordelen op SharePoint-siteniveau</span><span class="sxs-lookup"><span data-stu-id="01922-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="01922-162">Controleer de instellingen op siteniveau delen om ervoor te zorgen dat ze het gewenste type toegang voor deze site toestaan.</span><span class="sxs-lookup"><span data-stu-id="01922-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="01922-163">Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **iedereen**, maar u wilt dat alle gasten verificatie voor deze site verifiëren, controleert u of de instellingen voordelen op het siteniveau zijn ingesteld op **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="01922-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="01922-164">Houd er rekening mee dat de site niet kan worden gedeeld met niet-geverifieerde personen (**iedereen** ), maar ook afzonderlijke bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="01922-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="01922-165">U kunt ook de [instellingen voor het extern delen van SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)met behulp van palletlabels gebruiken.</span><span class="sxs-lookup"><span data-stu-id="01922-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="01922-167">Instellingen voordelen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="01922-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="01922-168">Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="01922-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="01922-169">Selecteer de site die u wilt delen.</span><span class="sxs-lookup"><span data-stu-id="01922-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="01922-170">Klik op... en klik op **delen**.</span><span class="sxs-lookup"><span data-stu-id="01922-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="01922-171">Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="01922-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="01922-172">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="01922-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="01922-173">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="01922-173">Invite users</span></span>

<span data-ttu-id="01922-174">Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u interne gebruikers en gasten aan uw site kunt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="01922-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="01922-175">De toegang tot de site wordt bestuurd via de bijbehorende Microsoft 365-groep, dus we zullen gebruikers daar toevoegen.</span><span class="sxs-lookup"><span data-stu-id="01922-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="01922-176">Interne gebruikers voor een groep uitnodigen</span><span class="sxs-lookup"><span data-stu-id="01922-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="01922-177">Ga naar de site waaraan u gebruikers wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="01922-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="01922-178">Klik op de koppeling **leden** in de rechterbovenhoek waarmee het aantal leden wordt aangegeven.</span><span class="sxs-lookup"><span data-stu-id="01922-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="01922-179">Klik op **leden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="01922-179">Click **Add members**.</span></span>
4. <span data-ttu-id="01922-180">Typ de namen of e-mailadressen van de gebruikers die u wilt uitnodigen voor de site en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="01922-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="01922-181">U kunt geen gasten toevoegen vanaf de site.</span><span class="sxs-lookup"><span data-stu-id="01922-181">Guests can't be added from the site.</span></span> <span data-ttu-id="01922-182">U moet ze toevoegen met de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="01922-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="01922-183">Daarom moet u als vereisten voor het toevoegen en uitnodigen van gasten aan een groep klikken op de URL van de site in de kolom **URL**  om naar de specifieke sitepagina te gaan.</span><span class="sxs-lookup"><span data-stu-id="01922-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="01922-184">Klik op deze pagina op het pictogram van het **startprogramma voor apps** en selecteer **Outlook**.</span><span class="sxs-lookup"><span data-stu-id="01922-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="01922-185">Dit is het scherm waarmee u gasten kunt uitnodigen voor een groep, waaronder de onderstaande procedure wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="01922-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="01922-186">Gasten voor een groep uitnodigen</span><span class="sxs-lookup"><span data-stu-id="01922-186">To invite guests to a group</span></span>
1. <span data-ttu-id="01922-187">Klik onder **groepen** op de groep waaraan u gasten wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="01922-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="01922-188">Open het visitekaartje van de groep, klik op de koppeling **leden** in de rechterbovenhoek (de koppeling die het aantal leden aanduidt).</span><span class="sxs-lookup"><span data-stu-id="01922-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="01922-189">Klik op **leden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="01922-189">click **Add members**.</span></span>
4. <span data-ttu-id="01922-190">Voer de e-mailadressen in van de gasten die u wilt uitnodigen en klik op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="01922-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="01922-191">Klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="01922-191">Click **Close**.</span></span>
<span data-ttu-id="01922-192">Houd er rekening mee dat u op alleen **sluiten** moet klikken als u niet de eigenaar van de groep bent en daarom niet is toegestaan om de gast toe te voegen aan de groep.</span><span class="sxs-lookup"><span data-stu-id="01922-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="01922-193">In dergelijke gevallen wordt de aanvraag om de gast toe te voegen aan de groep, doorgestuurd naar de groepseigenaar voorgoed keuring.</span><span class="sxs-lookup"><span data-stu-id="01922-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="01922-194">Zie ook</span><span class="sxs-lookup"><span data-stu-id="01922-194">See also</span></span>

[<span data-ttu-id="01922-195">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="01922-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="01922-196">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="01922-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="01922-197">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="01922-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="01922-198">Een B2B-extranet maken met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="01922-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="01922-199">Integratie van SharePoint en OneDrive met Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="01922-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
