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
recommendations: false
description: Meer informatie over de Microsoft 365 configuratiestappen die nodig zijn voor het instellen van een SharePoint site voor samenwerking met gasten.
ms.openlocfilehash: f91b9c64dbdca8ed7e3ada3315cb57f1c728f838
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539249"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="dc2bb-103">Samenwerken met gasten op een site</span><span class="sxs-lookup"><span data-stu-id="dc2bb-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="dc2bb-104">Als u wilt samenwerken met gasten in documenten, gegevens en lijsten, kunt u een SharePoint gebruiken.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="dc2bb-105">Moderne SharePoint sites zijn verbonden met Microsoft 365 Groepen en kunnen het lidmaatschap van de site beheren en extra samenwerkingshulpmiddelen bieden, zoals een gedeeld postvak en een agenda.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="dc2bb-106">In dit artikel lopen we door de Microsoft 365 configuratiestappen die nodig zijn om een SharePoint voor samenwerking met gasten.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="dc2bb-107">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="dc2bb-107">Video demonstration</span></span>

<span data-ttu-id="dc2bb-108">In deze video ziet u de configuratiestappen die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="dc2bb-109">Externe samenwerkingsinstellingen voor Azure</span><span class="sxs-lookup"><span data-stu-id="dc2bb-109">Azure external collaboration settings</span></span>

<span data-ttu-id="dc2bb-110">Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de [B2B-instellingen voor externe samenwerking in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="dc2bb-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="dc2bb-111">Als delen met gasten is uitgeschakeld of wordt beperkt in Azure AD, overschrijft deze instelling alle instellingen voor delen die u configureert in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="dc2bb-112">Controleer de B2B-instellingen voor externe samenwerking om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van Azure Active Directory pagina Externe samenwerking Instellingen](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="dc2bb-114">Instellingen voor externe samenwerking instellen</span><span class="sxs-lookup"><span data-stu-id="dc2bb-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="dc2bb-115">Meld u aan bij Azure Active Directory op [https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="dc2bb-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="dc2bb-116">Klik in het linkernavigatiedeelvenster op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="dc2bb-117">Klik **Externe identiteiten**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-117">Click **External identities**.</span></span>
4. <span data-ttu-id="dc2bb-118">Klik in het linkernavigatiedeelvenster **Aan de slag** op **Instellingen voor externe samenwerking**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="dc2bb-119">Zorg ervoor dat **Beheerders en gebruikers in de rol van Afzender van gastuitnodigingen kunnen uitnodigingen verzenden** en **Leden kunnen uitnodigingen verzenden** beide zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="dc2bb-120">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="dc2bb-121">Let op de instellingen in de sectie **Samenwerkingsbeperkingen**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="dc2bb-122">Zorg ervoor dat de domeinen van de gasten met wie u wilt samenwerken, niet worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="dc2bb-123">Als u met gasten van meerdere organisaties werkt, wilt u mogelijk hun toegang tot adreslijstgegevens beperken.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="dc2bb-124">Hiermee voorkomt u dat ze kunnen zien wie er nog meer een gast is in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="dc2bb-125">Hiervoor selecteert u onder **Toegangsbeperkingen voor gastgebruikers** de optie **Gastgebruikers hebben beperkte toegang tot eigenschappen en lidmaatschap van instellingen voor adreslijstobjecten** of **Toegang van gastgebruikers is beperkt tot eigenschappen en lidmaatschappen van hun eigen adreslijstobjecten**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="dc2bb-126">Gastinstellingen van Microsoft 365 Groepen</span><span class="sxs-lookup"><span data-stu-id="dc2bb-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="dc2bb-127">Moderne SharePoint sites gebruiken Microsoft 365 Groepen om sitetoegang te bepalen.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="dc2bb-128">De Microsoft 365 Groepen gastinstellingen moeten zijn ingeschakeld zodat gasttoegang op SharePoint sites kan werken.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="dc2bb-130">Gastinstellingen van Microsoft 365 Groepen instellen</span><span class="sxs-lookup"><span data-stu-id="dc2bb-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="dc2bb-131">Vouw in het Microsoft 365-beheercentrum **Instellingen** uit in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="dc2bb-132">Klik op **Organisatie-instellingen**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="dc2bb-133">Klik in de lijst op **Microsoft 365 Groepen**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="dc2bb-134">Zorg ervoor dat de selectievakjes **Groepseigenaren toestaan personen van buiten de organisatie als gast aan Microsoft 365 Groepen toe te voegen** en **Gastgroepsleden toegang geven tot groepsinhoud** beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="dc2bb-135">Als u wijzigingen hebt aangebracht, klikt u op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="dc2bb-136">SharePoint instellingen voor delen op organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="dc2bb-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="dc2bb-137">Om ervoor te zorgen dat gasten toegang hebben tot SharePoint sites, moeten SharePoint instellingen voor delen op organisatieniveau toestaan dat ze kunnen delen met gasten.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="dc2bb-138">De instellingen op organisatieniveau bepalen de instellingen die beschikbaar zijn voor afzonderlijke sites.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="dc2bb-139">Site-instellingen mogen niet meer toestaan dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="dc2bb-140">Als u niet-genautisch bestand en delen van mappen wilt toestaan, kiest u **Iedereen**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="dc2bb-141">Als u ervoor wilt zorgen dat alle personen buiten uw organisatie zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="dc2bb-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="dc2bb-142">Kies de ruimste instelling die nodig is voor de sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="dc2bb-144">Instellingen voor delen op organisatieniveau van SharePoint instellen</span><span class="sxs-lookup"><span data-stu-id="dc2bb-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="dc2bb-145">In het Microsoft 365-beheercentrum klikt u onder **Beheercentra** op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="dc2bb-146">Klik in SharePoint beheercentrum in het linkernavigatiedeelvenster onder Beleid **op** **Delen.**</span><span class="sxs-lookup"><span data-stu-id="dc2bb-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="dc2bb-147">Zorg ervoor dat extern delen voor SharePoint is ingesteld op **Iedereen** of **Nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="dc2bb-148">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="dc2bb-149">Een site maken</span><span class="sxs-lookup"><span data-stu-id="dc2bb-149">Create a site</span></span>

<span data-ttu-id="dc2bb-150">De volgende stap is het maken van de site die u wilt gebruiken om samen te werken met gasten.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="dc2bb-151">Een site maken</span><span class="sxs-lookup"><span data-stu-id="dc2bb-151">To create a site</span></span>
1. <span data-ttu-id="dc2bb-152">Klik in het SharePoint-beheercentrum onder **Sites** op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="dc2bb-153">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-153">Click **Create**.</span></span>
3. <span data-ttu-id="dc2bb-154">Klik **op Teamsite.**</span><span class="sxs-lookup"><span data-stu-id="dc2bb-154">Click **Team site**.</span></span>
4. <span data-ttu-id="dc2bb-155">Typ een sitenaam en voer een naam in voor de groepseigenaar (site-eigenaar).</span><span class="sxs-lookup"><span data-stu-id="dc2bb-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="dc2bb-156">Kies **onder Geavanceerde** instellingen of u wilt dat deze site openbaar of privé is.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="dc2bb-157">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-157">Click **Next**.</span></span>
7. <span data-ttu-id="dc2bb-158">Klik op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-158">Click **Finish**.</span></span>

<span data-ttu-id="dc2bb-159">We nodigen gebruikers later uit.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-159">We'll invite users later.</span></span> <span data-ttu-id="dc2bb-160">Vervolgens is het belangrijk om de instellingen voor delen op siteniveau voor deze site te controleren.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="dc2bb-161">Instellingen voor het delen op siteniveau in SharePoint</span><span class="sxs-lookup"><span data-stu-id="dc2bb-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="dc2bb-162">Controleer de instellingen voor delen op siteniveau om ervoor te zorgen dat het type toegang dat u voor deze site wilt gebruiken, wordt toegestaan.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="dc2bb-163">Als u bijvoorbeeld de instellingen op organisatieniveau in stelt op **Iedereen,** maar u wilt dat alle gasten zich voor deze site verifiëren, moet u ervoor zorgen dat de instellingen voor delen op siteniveau zijn ingesteld op Nieuwe en bestaande **gasten.**</span><span class="sxs-lookup"><span data-stu-id="dc2bb-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="dc2bb-164">Houd er rekening mee dat de site niet kan worden gedeeld met niet-nautische personen **(** Iedereen instelling), maar afzonderlijke bestanden en mappen wel.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="dc2bb-165">U kunt ook [gevoeligheidslabels gebruiken om instellingen voor extern delen](../compliance/sensitivity-labels-teams-groups-sites.md)voor SharePoint beheren.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="dc2bb-167">Instellingen voor delen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="dc2bb-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="dc2bb-168">Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="dc2bb-169">Selecteer de site die u wilt delen.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="dc2bb-170">Klik op ...en klik op **Delen.**</span><span class="sxs-lookup"><span data-stu-id="dc2bb-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="dc2bb-171">Zorg ervoor dat delen is ingesteld op **Iedereen** of **Nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="dc2bb-172">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="dc2bb-173">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="dc2bb-173">Invite users</span></span>

<span data-ttu-id="dc2bb-174">Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u kunt beginnen met het toevoegen van interne gebruikers en gasten aan uw site.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="dc2bb-175">Sitetoegang wordt beheerd via de gekoppelde Microsoft 365 Groep, dus daar worden gebruikers toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="dc2bb-176">Interne gebruikers uitnodigen voor een groep</span><span class="sxs-lookup"><span data-stu-id="dc2bb-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="dc2bb-177">Ga naar de site waar u gebruikers wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="dc2bb-178">Klik **in de** rechterbovenhoek op de koppeling Leden, waarmee het aantal leden wordt aangegeven.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="dc2bb-179">Klik **op Leden toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="dc2bb-179">Click **Add members**.</span></span>
4. <span data-ttu-id="dc2bb-180">Typ de namen of e-mailadressen van de gebruikers die u wilt uitnodigen voor de site en klik vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="dc2bb-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="dc2bb-181">Gasten kunnen niet worden toegevoegd vanaf de site.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-181">Guests can't be added from the site.</span></span> <span data-ttu-id="dc2bb-182">U moet ze toevoegen met Outlook op internet.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="dc2bb-183">Als voorwaarde voor het toevoegen en uitnodigen van gasten voor een groep, klikt u daarom op de URL van de site in de **kolom URL**  om naar de sitespecifieke pagina te gaan.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="dc2bb-184">Klik op deze pagina op het **startpictogram voor apps** en selecteer **Outlook.**</span><span class="sxs-lookup"><span data-stu-id="dc2bb-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="dc2bb-185">Dit is het scherm waaruit u gasten kunt uitnodigen voor een groep, waarvoor de procedure hieronder wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="dc2bb-186">Gasten uitnodigen voor een groep</span><span class="sxs-lookup"><span data-stu-id="dc2bb-186">To invite guests to a group</span></span>
1. <span data-ttu-id="dc2bb-187">Klik **onder** Groepen op de groep waarvoor u gasten wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="dc2bb-188">Open het groepscontactkaart, klik rechtsboven op **De** koppeling Leden (de koppeling waarmee het aantal leden wordt aangegeven).</span><span class="sxs-lookup"><span data-stu-id="dc2bb-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="dc2bb-189">klik **op Leden toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="dc2bb-189">click **Add members**.</span></span>
4. <span data-ttu-id="dc2bb-190">Typ de e-mailadressen van de gasten die u wilt uitnodigen en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="dc2bb-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="dc2bb-191">Klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-191">Click **Close**.</span></span>
<span data-ttu-id="dc2bb-192">Houd er rekening  mee dat u alleen op Sluiten moet klikken als u niet de eigenaar van de groep bent en u daardoor de gast niet aan de groep kunt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="dc2bb-193">In dergelijke gevallen wordt de aanvraag om de gast toe te voegen aan de groep ter goedkeuring overgedragen aan de groepseigenaar.</span><span class="sxs-lookup"><span data-stu-id="dc2bb-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc2bb-194">Zie ook</span><span class="sxs-lookup"><span data-stu-id="dc2bb-194">See also</span></span>

[<span data-ttu-id="dc2bb-195">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="dc2bb-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="dc2bb-196">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="dc2bb-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="dc2bb-197">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="dc2bb-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="dc2bb-198">Een B2B-extranet maken met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="dc2bb-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="dc2bb-199">Integratie van SharePoint en OneDrive met Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="dc2bb-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)