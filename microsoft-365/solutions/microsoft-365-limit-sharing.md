---
title: Delen beperken in Microsoft 365
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
search.appverid:
- SPO160
- MET150
f1.keywords: NOCSH
ms.custom: ''
localization_priority: Priority
description: Leer meer over de mogelijkheden om delen in Microsoft 365 te beperken of uit te schakelen.
ms.openlocfilehash: 69a71d84f32316278353f8de392202f1a92dc22d
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528180"
---
# <a name="limit-sharing-in-microsoft-365"></a><span data-ttu-id="d21ac-103">Delen beperken in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d21ac-103">Limit sharing in Microsoft 365</span></span>

<span data-ttu-id="d21ac-104">Hoewel u interne delen niet volledig kunt uitschakelen en de Delen-knop niet van sites kunt verwijderen, kunt u op verschillende manieren het delen in Microsoft 365 beperken om tegemoet te komen aan de behoeften van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d21ac-104">While you can't disable internal sharing entirely or remove the Share button from sites, there are a variety of ways that you can limit sharing in Microsoft 365 to meet the needs of your organization.</span></span>

<span data-ttu-id="d21ac-105">De methoden voor het delen van bestanden worden weergegeven in de onderstaande tabel.</span><span class="sxs-lookup"><span data-stu-id="d21ac-105">The methods of sharing files are listed in the table below.</span></span> <span data-ttu-id="d21ac-106">Klik op de link in de kolom **Deelmethode** voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d21ac-106">Click the link in the **Sharing method** column for detailed information.</span></span>

|<span data-ttu-id="d21ac-107">Deelmethode</span><span class="sxs-lookup"><span data-stu-id="d21ac-107">Sharing method</span></span>|<span data-ttu-id="d21ac-108">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d21ac-108">Description</span></span>|<span data-ttu-id="d21ac-109">Mogelijkheden beperken</span><span class="sxs-lookup"><span data-stu-id="d21ac-109">Limiting options</span></span>|
|:-------------|:----------|:-------------|
|[<span data-ttu-id="d21ac-110">Microsoft 365-groep of -team</span><span class="sxs-lookup"><span data-stu-id="d21ac-110">Microsoft 365 group or team</span></span>](#microsoft-365-group-or-team)|<span data-ttu-id="d21ac-111">Personen die toegang hebben tot een team van Microsoft Teams of Microsoft 365, hebben toegang tot bestanden in de gekoppelde SharePoint-site.</span><span class="sxs-lookup"><span data-stu-id="d21ac-111">People granted access to a Microsoft Teams team or Microsoft 365 group have edit access to files in the associated SharePoint site.</span></span>|<span data-ttu-id="d21ac-112">Indien de groep of het team privé is, worden uitnodigingen om lid te worden van het team naar de eigenaar gestuurd voor goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="d21ac-112">If the group or team is private, sharing invitations to join the team go to the owner for approval.</span></span> <span data-ttu-id="d21ac-113">Beheerders kunnen gasttoegang uitschakelen om te voorkomen dat personen van buiten de organisatie toegang krijgen.</span><span class="sxs-lookup"><span data-stu-id="d21ac-113">Admins can disable guest access to prevent access by people from outside the organization.</span></span>|
|[<span data-ttu-id="d21ac-114">SharePoint-site</span><span class="sxs-lookup"><span data-stu-id="d21ac-114">SharePoint site</span></span>](#sharepoint-site)|<span data-ttu-id="d21ac-115">Personen kunnen toegang krijgen tot een SharePoint-site als Eigenaar, Lid of Bezoeker, en hebben op dit niveau toegang tot bestanden op de site.</span><span class="sxs-lookup"><span data-stu-id="d21ac-115">People can be granted Owner, Member, or Visitor access to a SharePoint site and will have that level of access to files in the site.</span></span>|<span data-ttu-id="d21ac-116">Sitemachtigingen kunnen worden beperkt, zodat alleen site-eigenaren de site kunnen delen.</span><span class="sxs-lookup"><span data-stu-id="d21ac-116">Site permissions can be restricted so that only site owners can share the site.</span></span>|
|[<span data-ttu-id="d21ac-117">Delen met specifieke personen</span><span class="sxs-lookup"><span data-stu-id="d21ac-117">Sharing with specific people</span></span>](#sharing-with-specific-people)|<span data-ttu-id="d21ac-118">Siteleden en personen met machtiging voor bewerkingen kunnen rechtstreekse machtigingen geven voor bestanden en mappen of ze delen met behulp van *Specifieke personen*-links.</span><span class="sxs-lookup"><span data-stu-id="d21ac-118">Site members and people with edit permissions can give direct permissions to files and folders or share them by using *Specific people* links.</span></span>|<span data-ttu-id="d21ac-119">Sitemachtigingen kunnen worden beperkt, zodat alleen site-eigenaren de bestanden en mappen kunnen delen.</span><span class="sxs-lookup"><span data-stu-id="d21ac-119">Site permissions can be restricted so that only site owners can share files and folders.</span></span> <span data-ttu-id="d21ac-120">In dit geval wordt het delen van rechtstreekse toegang en een *Specifieke personen*-link aan de site-eigenaar voorgelegd voor toestemming.</span><span class="sxs-lookup"><span data-stu-id="d21ac-120">In this case, direct access and *Specific people* link sharing by site members goes to site owner for approval.</span></span>|
|[<span data-ttu-id="d21ac-121">SharePoint-gast delen</span><span class="sxs-lookup"><span data-stu-id="d21ac-121">SharePoint guest sharing</span></span>](#sharepoint-guest-sharing)|<span data-ttu-id="d21ac-122">SharePoint-site-eigenaren en -leden kunnen bestanden en mappen delen met personen buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="d21ac-122">SharePoint site owners and members can share files and folders with people outside the organization.</span></span>|<span data-ttu-id="d21ac-123">Het delen van gasten kan worden uitgeschakeld voor de hele organisatie of voor afzonderlijke sites.</span><span class="sxs-lookup"><span data-stu-id="d21ac-123">Guest sharing can be disabled for the entire organization or for individual sites.</span></span>|
|[<span data-ttu-id="d21ac-124">*Personen in uw organisatie* links delen</span><span class="sxs-lookup"><span data-stu-id="d21ac-124">*People in your organization* sharing links</span></span>](#people-in-your-organization-sharing-links)|<span data-ttu-id="d21ac-125">SharePoint-site-eigenaren en -leden kunnen bestanden delen met *Personen in uw organisatie*-links. Dit werkt voor iedereen binnen de organisatie.</span><span class="sxs-lookup"><span data-stu-id="d21ac-125">SharePoint site owners and members can share files using *People in your organization* links, which will work for anyone inside the organization.</span></span>|<span data-ttu-id="d21ac-126">*Personen in uw organisatie*-links kunnen worden uitgeschakeld op siteniveau.</span><span class="sxs-lookup"><span data-stu-id="d21ac-126">*People in your organization* links can be disabled at the site level.</span></span>|
|[<span data-ttu-id="d21ac-127">E-mail</span><span class="sxs-lookup"><span data-stu-id="d21ac-127">Email</span></span>](#email)|<span data-ttu-id="d21ac-128">Personen met toegang tot een bestand kunnen het via e-mail naar anderen verzenden.</span><span class="sxs-lookup"><span data-stu-id="d21ac-128">People with access to a file can send it to others via email.</span></span>|<span data-ttu-id="d21ac-129">Beheerders kunnen bestanden versleutelen met behulp van gevoeligheidslabels om te voorkomen dat ze worden gedeeld met niet-geautoriseerde personen.</span><span class="sxs-lookup"><span data-stu-id="d21ac-129">Admins can encrypt files by using sensitivity labels to prevent them being shared with unauthorized people.</span></span>|
|[<span data-ttu-id="d21ac-130">Bestanden downloaden of kopiëren</span><span class="sxs-lookup"><span data-stu-id="d21ac-130">Download or file copy</span></span>](#download-or-file-copy)|<span data-ttu-id="d21ac-131">Personen met toegang tot een bestand kunnen het downloaden of kopiëren en delen met anderen buiten het bereik van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d21ac-131">People with access to a file can download or copy it and share it with others outside the scope of Microsoft 365.</span></span>|<span data-ttu-id="d21ac-132">Beheerders kunnen bestanden versleutelen met behulp van gevoeligheidslabels om te voorkomen dat ze worden gedeeld met niet-geautoriseerde personen.</span><span class="sxs-lookup"><span data-stu-id="d21ac-132">Admins can encrypt files by using sensitivity labels to prevent them being shared with unauthorized people.</span></span>|

<span data-ttu-id="d21ac-133">U kunt de beheerdersbesturingselementen die in dit artikel worden beschreven, gebruiken om het delen binnen uw organisatie te beperken. U wordt ten zeerste aangeraden de beveiligings- en compliance-functies in Microsoft 365 te gebruiken om een veilige deelomgeving te creëren.</span><span class="sxs-lookup"><span data-stu-id="d21ac-133">While you can use the admin controls described in this article to limit sharing in your organization, we highly recommend that you consider using the security and compliance features available in Microsoft 365 to create a secure sharing environment.</span></span> <span data-ttu-id="d21ac-134">Zie [Samenwerken aan bestanden in SharePoint met Microsoft 365](https://docs.microsoft.com/sharepoint/deploy-file-collaboration) en [Teams voor sterk gereglementeerde gegevens](https://docs.microsoft.com/microsoft-365/enterprise/secure-teams-highly-regulated-data-scenario) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d21ac-134">See [File collaboration in SharePoint with Microsoft 365](https://docs.microsoft.com/sharepoint/deploy-file-collaboration) and [Teams for highly regulated data](https://docs.microsoft.com/microsoft-365/enterprise/secure-teams-highly-regulated-data-scenario) for information.</span></span>

<span data-ttu-id="d21ac-135">Als u wilt weten hoe delen wordt gebruikt binnen uw organisatie, [laat u een rapport opstellen over het delen van bestanden en mappen](https://docs.microsoft.com/sharepoint/sharing-reports).</span><span class="sxs-lookup"><span data-stu-id="d21ac-135">To understand how sharing is being used in your organization, [run a report on file and folder sharing](https://docs.microsoft.com/sharepoint/sharing-reports).</span></span>

## <a name="microsoft-365-group-or-team"></a><span data-ttu-id="d21ac-136">Microsoft 365-groep of -team</span><span class="sxs-lookup"><span data-stu-id="d21ac-136">Microsoft 365 group or team</span></span>

<span data-ttu-id="d21ac-137">Als u het delen binnen een Microsoft 365-groep of Microsoft Teams-team wilt beperken, is het belangrijk dat u de groep of het team privé maakt.</span><span class="sxs-lookup"><span data-stu-id="d21ac-137">If you want to limit sharing in a Microsoft 365 group or Microsoft Teams team, it's important to make the group or team private.</span></span> <span data-ttu-id="d21ac-138">Personen binnen uw organisatie kunnen op elk gewenst moment lid worden van een openbare groep of team.</span><span class="sxs-lookup"><span data-stu-id="d21ac-138">People inside your organization can join a public group or team anytime.</span></span> <span data-ttu-id="d21ac-139">Tenzij de groep of het team privé is, kunt u het delen van het team of de bestanden binnen de organisatie niet beperken.</span><span class="sxs-lookup"><span data-stu-id="d21ac-139">Unless the group or team is private, there's no way to limit sharing of the team or its files within the organization.</span></span>

### <a name="guest-sharing"></a><span data-ttu-id="d21ac-140">Gasten delen</span><span class="sxs-lookup"><span data-stu-id="d21ac-140">Guest sharing</span></span>

<span data-ttu-id="d21ac-141">Als u wilt voorkomen dat gasttoegang in Teams wordt ingeschakeld, kunt u het delen met gasten uitschakelen in het Beheercentrum van Teams.</span><span class="sxs-lookup"><span data-stu-id="d21ac-141">If you want to prevent guest access in Teams, you can turn off guest sharing in the Teams admin center.</span></span>

<span data-ttu-id="d21ac-142">Het delen met gasten uitschakelen voor Teams</span><span class="sxs-lookup"><span data-stu-id="d21ac-142">To turn off guest sharing for Teams</span></span>
1. <span data-ttu-id="d21ac-143">Vouw in het Beheercentrum van Teams **Instellingen voor hele organisatie** uit en klik vervolgens op **Gasttoegang**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-143">In the Teams admin center, expand **Org-wide settings**, and then click **Guest access**.</span></span>
2. <span data-ttu-id="d21ac-144">Schakel **Gasttoegang in Teams toestaan** uit.</span><span class="sxs-lookup"><span data-stu-id="d21ac-144">Turn off **Allow guest access in Teams**.</span></span>
3. <span data-ttu-id="d21ac-145">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-145">Click **Save**.</span></span>

<span data-ttu-id="d21ac-146">Als u gasttoegang in Microsoft 365-groepen wilt voorkomen, kunt u de instellingen voor gasttoegang in het Microsoft 365-beheercentrum uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="d21ac-146">If you want to prevent guest access in Microsoft 365 Groups, you can turn off the groups guest access settings in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="d21ac-147">Het delen met gasten uitschakelen in Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="d21ac-147">To turn off guest sharing in Microsoft 365 Groups</span></span>
1. <span data-ttu-id="d21ac-148">In het Microsoft 365-beheercentrum klikt u op **Instellingen** en vervolgens op **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-148">In the Microsoft 365 admin center, click **Settings**, and then click **Settings**.</span></span>
2. <span data-ttu-id="d21ac-149">Klik in het tabblad **Services** op **Microsoft 365-groepen**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-149">On the **Services** tab, click **Microsoft 365 Groups**.</span></span>
3. <span data-ttu-id="d21ac-150">Schakel de selectievakjes voor **Groepsleden buiten uw organisatie toegang geven tot groepsinhoud** en **Groepseigenaren personen van buiten uw organisatie toe laten voegen aan groepen** uit.</span><span class="sxs-lookup"><span data-stu-id="d21ac-150">Clear the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes.</span></span>
4. <span data-ttu-id="d21ac-151">Klik op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-151">Click **Save changes**.</span></span>

    ![Schermopname van gastinstellingen van Microsoft 365-groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings-off.png)

> [!NOTE]
> <span data-ttu-id="d21ac-153">Als u het delen met gasten voor een bepaalde groep of een bepaald team wilt voorkomen, kunt u dit doen met behulp van Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d21ac-153">If you want to prevent guest sharing for a particular group or team, you can do so by using Microsoft PowerShell.</span></span> <span data-ttu-id="d21ac-154">Zie [Gastgebruikers voor een specifieke groep blokkeren](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#block-guest-users-from-a-specific-group) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d21ac-154">See [Block guest users from a specific group](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#block-guest-users-from-a-specific-group) for details.</span></span>

<span data-ttu-id="d21ac-155">U kunt het delen met gasten beperken voor gebruikers van specifieke domeinen door domeinen toe te staan of te blokkeren in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d21ac-155">You can limit guest sharing to users from specific domains by allowing or blocking domains in Azure Active Directory.</span></span> <span data-ttu-id="d21ac-156">Dit is ook van invloed op het delen met gasten in SharePoint, als u [SharePoint-en OneDrive-integratie met Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d21ac-156">This will also affect guest sharing in SharePoint if you have enabled [SharePoint and OneDrive integration with Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="d21ac-157">Uitnodigingen voor delen alleen bij specifieke domeinen toestaan</span><span class="sxs-lookup"><span data-stu-id="d21ac-157">To allow sharing invitations only from specified domains</span></span>
1. <span data-ttu-id="d21ac-158">Klik in Azure Active Directory op de Overzichtspagina op **Organisatierelaties**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-158">In Azure Active Directory, on the Overview page, click **Organizational relationships**.</span></span>
2. <span data-ttu-id="d21ac-159">Klik op **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-159">Click **Settings**.</span></span>
3. <span data-ttu-id="d21ac-160">Onder **Samenwerkingsbeperkingen**selecteert u **Uitnodigingen weigeren bij de gespecificeerde domeinen** of **Alleen uitnodigingen toestaan voor de gespecificeerde domeinen**en typ vervolgens de domeinen in die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d21ac-160">Under **Collaboration restrictions**, select **Deny invitations to the specified domains** or **Allow invitations only to the specified domains**, and then type the domains that you want to use.</span></span>
4. <span data-ttu-id="d21ac-161">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-161">Click **Save**.</span></span>

    ![Schermafbeelding van de instellingen voor samenwerkingsbeperkingen in Azure Active Directory](../media/azure-ad-allow-only-specified-domains.png)

## <a name="sharepoint-site"></a><span data-ttu-id="d21ac-163">SharePoint-site</span><span class="sxs-lookup"><span data-stu-id="d21ac-163">SharePoint site</span></span>

<span data-ttu-id="d21ac-164">U kunt het delen van SharePoint-sites beperken tot alleen site-eigenaren.</span><span class="sxs-lookup"><span data-stu-id="d21ac-164">You can limit SharePoint site sharing to site owners only.</span></span> <span data-ttu-id="d21ac-165">Hiermee voorkomt u dat siteleden de site delen.</span><span class="sxs-lookup"><span data-stu-id="d21ac-165">This prevents site members from sharing the site.</span></span> <span data-ttu-id="d21ac-166">Als de site is verbonden met een Microsoft 365-groep, kunnen groepsleden anderen uitnodigen voor de groep en kunnen deze gebruikers toegang krijgen tot de site.</span><span class="sxs-lookup"><span data-stu-id="d21ac-166">Keep in mind that if the site is connected to a Microsoft 365 group, group members can invite others to the group and those users will have site access.</span></span>

<span data-ttu-id="d21ac-167">Het delen van een site beperken tot eigenaren</span><span class="sxs-lookup"><span data-stu-id="d21ac-167">To limit site sharing to owners</span></span>
1. <span data-ttu-id="d21ac-168">Klik in de werkbalk op het pictogram voor Instellingen en vervolgens op **Site-machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-168">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="d21ac-169">Klik onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-169">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="d21ac-170">Selecteer **Site-eigenaren en -leden, en personen met machtigingen voor bewerken kunnen bestanden en mappen delen, maar alleen site-eigenaren kunnen de site delen**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-170">Select **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**.</span></span>
4. <span data-ttu-id="d21ac-171">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-171">Click **Save**.</span></span>

    ![Schermafbeelding van de instellingen voor het delen van machtigingen op een SharePoint-site](../media/sharepoint-site-sharing-permissions-level-two.png)

<span data-ttu-id="d21ac-173">U kunt voorkomen dat gebruikers die geen deel uitmaken van de site toegang aanvragen door toegangsaanvragen uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="d21ac-173">You can prevent users who are not members of the site from requesting access by turning off access requests.</span></span>

<span data-ttu-id="d21ac-174">Toegangsaanvragen uitschakelen</span><span class="sxs-lookup"><span data-stu-id="d21ac-174">To turn off access requests</span></span>
1. <span data-ttu-id="d21ac-175">Klik in de werkbalk op het pictogram voor Instellingen en vervolgens op **Site-machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-175">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="d21ac-176">Klik onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-176">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="d21ac-177">Schakel **Toegangsaanvragen toestaan** uit en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-177">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="d21ac-178">U kunt het delen van een site beperken tot specifieke domeinen door domeinen toe te staan of te blokkeren voor de site.</span><span class="sxs-lookup"><span data-stu-id="d21ac-178">You can limit site sharing to specific domains by allowing or blocking domains for the site.</span></span>

<span data-ttu-id="d21ac-179">Het delen van een site beperken</span><span class="sxs-lookup"><span data-stu-id="d21ac-179">To limit site sharing by domain</span></span>
1. <span data-ttu-id="d21ac-180">Klik in het SharePoint-beheercentrum onder **Sites** op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-180">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="d21ac-181">Klik op de site die u wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="d21ac-181">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="d21ac-182">Klik op het tabblad **Beleid** onder **Extern delen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-182">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="d21ac-183">Onder **Geavanceerde instellingen voor extern delen** selecteert u **Delen beperken per domein**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-183">Under **Advanced settings for external sharing**, select the **Limit sharing by domain**.</span></span>
5. <span data-ttu-id="d21ac-184">Voeg de domeinen toe die u wilt toelaten of blokkeren en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-184">Add the domains that you want to allow or block, and then click **Save**.</span></span>
6. <span data-ttu-id="d21ac-185">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-185">Click **Save**.</span></span>

    ![Schermafbeelding van instellingen voor toegestane domeinen op siteniveau](../media/limit-site-sharing-by-domain.png)

## <a name="sharing-with-specific-people"></a><span data-ttu-id="d21ac-187">Delen met specifieke personen</span><span class="sxs-lookup"><span data-stu-id="d21ac-187">Sharing with specific people</span></span>

<span data-ttu-id="d21ac-188">Als u het delen van een site of de inhoud ervan wilt beperken, kunt u de site zo configureren dat alleen site-eigenaren bestanden, mappen en de site kunnen delen.</span><span class="sxs-lookup"><span data-stu-id="d21ac-188">if you want to limit the sharing of a site or its contents, you can configure the site to only allow site owners to share files, folders, and the site.</span></span> <span data-ttu-id="d21ac-189">Wanneer dit is geconfigureerd, worden pogingen van siteleden om bestanden of mappen te delen met behulp van *Specifieke personen*-links naar de site-eigenaar doorgestuurd voor goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="d21ac-189">When this is configured, site members' attempts to share files or folders by using *Specific people* links will go to the site owner for approval.</span></span>

<span data-ttu-id="d21ac-190">Het delen van de site, bestanden of mappen beperken tot eigenaren</span><span class="sxs-lookup"><span data-stu-id="d21ac-190">To limit site, file, and folder sharing to owners</span></span>
1. <span data-ttu-id="d21ac-191">Klik in de werkbalk op het pictogram voor Instellingen en vervolgens op **Site-machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-191">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="d21ac-192">Klik onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-192">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="d21ac-193">Selecteer **Alleen site-eigenaren kunnen bestanden, mappen en de site** delen.</span><span class="sxs-lookup"><span data-stu-id="d21ac-193">Select **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="d21ac-194">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-194">Click **Save**.</span></span>

    ![Schermafbeelding van de instellingen voor het delen van machtigingen op een SharePoint-site](../media/sharepoint-site-only-site-owners-can-share.png)

## <a name="sharepoint-guest-sharing"></a><span data-ttu-id="d21ac-196">Delen met gasten in SharePoint</span><span class="sxs-lookup"><span data-stu-id="d21ac-196">SharePoint guest sharing</span></span>

<span data-ttu-id="d21ac-197">Als u wilt voorkomen dat SharePoint- of OneDrive-bestanden of -mappen worden gedeeld met personen buiten uw organisatie, kunt u het delen met gasten voor de hele organisatie of voor een afzonderlijke site uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="d21ac-197">If you want to prevent sharing SharePoint or OneDrive files and folders with people outside your organization, you can turn off guest sharing for the entire organization or for an individual site.</span></span>

<span data-ttu-id="d21ac-198">Delen met gasten in SharePoint uitschakelen voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="d21ac-198">To turn off SharePoint guest sharing for your organization</span></span>
1. <span data-ttu-id="d21ac-199">Klik in het SharePoint-beheercentrum onder **Beleid** op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-199">In the SharePoint admin center, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="d21ac-200">Sleep de SharePoint-schuifregelaar onder **Extern delen** naar **Alleen personen in uw organisatie**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-200">Under **External sharing**, drag the SharePoint slider down to **Only people in your organization**.</span></span>
3. <span data-ttu-id="d21ac-201">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-201">Click **Save**.</span></span>

    ![Schermafbeelding van de instellingen voor delen op organisatieniveau in SharePoint](../media/sharepoint-tenant-sharing-off.png)


<span data-ttu-id="d21ac-203">Het delen met gasten uitschakelen voor een site</span><span class="sxs-lookup"><span data-stu-id="d21ac-203">To turn off guest sharing for a site</span></span>
1. <span data-ttu-id="d21ac-204">Klik in het SharePoint-beheercentrum onder **Sites** op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-204">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="d21ac-205">Klik op de site die u wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="d21ac-205">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="d21ac-206">Klik op het tabblad **Beleid** onder **Extern delen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-206">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="d21ac-207">Kies onder**Extern delen** voor **Alleen personen in uw organisatie** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-207">Under **External sharing**, choose **Only people in your organization**, and then click **Save**.</span></span>

    ![Schermafbeelding van de instellingen voor het delen op siteniveau in SharePoint](../media/sharepoint-site-external-sharing-settings-off.png)

<span data-ttu-id="d21ac-209">Als u het delen met personen buiten uw organisatie wilt toestaan, maar wel wilt dat iedereen wordt geverifieerd, kunt u de *Iedereen*-links (anoniem delen) voor de hele organisatie of voor een afzonderlijke site uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="d21ac-209">If you would like to allow sharing with people outside your organization but you want to make sure that everyone authenticates, you can disable *Anyone* (anonymous sharing) links for the entire organization or for an individual site.</span></span>

<span data-ttu-id="d21ac-210">*Iedereen*-links op organisatieniveau uitschakelen</span><span class="sxs-lookup"><span data-stu-id="d21ac-210">To turn off *Anyone* links at the organization level</span></span>
1. <span data-ttu-id="d21ac-211">Klik in het SharePoint-beheercentrum onder **Beleid** op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-211">In the SharePoint admin center, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="d21ac-212">Sleep de SharePoint-schuifregelaar onder **Extern delen** naar **Nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-212">Under **External sharing**, drag the SharePoint slider down to **New and existing guests**.</span></span>
3. <span data-ttu-id="d21ac-213">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-213">Click **Save**.</span></span>

    ![Schermafbeelding van de instellingen voor het delen op siteniveau in SharePoint](../media/sharepoint-guest-sharing-new-existing-guests.png)

<span data-ttu-id="d21ac-215">*Iedereen*-links voor een site uitschakelen</span><span class="sxs-lookup"><span data-stu-id="d21ac-215">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="d21ac-216">Klik in het SharePoint-beheercentrum onder **Sites** op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-216">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="d21ac-217">Klik op de site die u wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="d21ac-217">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="d21ac-218">Klik op het tabblad **Beleid** onder **Extern delen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-218">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="d21ac-219">Kies onder **Extern delen** voor **Nieuwe en bestaande gasten** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d21ac-219">Under **External sharing**, choose **New and existing guests**, and then click **Save**.</span></span>

    ![Schermafbeelding van de instellingen voor het delen op siteniveau in SharePoint](../media/sharepoint-site-external-sharing-settings-new-existing-guests.png)

## <a name="people-in-your-organization-sharing-links"></a><span data-ttu-id="d21ac-221">*Personen in uw organisatie*-links delen</span><span class="sxs-lookup"><span data-stu-id="d21ac-221">*People in your organization* sharing links</span></span>

<span data-ttu-id="d21ac-222">Leden van een site kunnen standaard bestanden en mappen delen met andere personen in uw organisatie met behulp van een *Personen in uw organisatie*-link.</span><span class="sxs-lookup"><span data-stu-id="d21ac-222">By default, members of a site can share files and folders with other people in your organization by using a *People in your organization* link.</span></span> <span data-ttu-id="d21ac-223">Met PowerShell kunt u *Personen in uw organisatie*-links uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="d21ac-223">You can disable *People in your organization* links by using PowerShell:</span></span>

`Set-SPOSite -Identity <site> -DisableCompanyWideSharingLinks`

<span data-ttu-id="d21ac-224">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d21ac-224">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com -DisableCompanyWideSharingLinks`

## <a name="email"></a><span data-ttu-id="d21ac-225">E-mail</span><span class="sxs-lookup"><span data-stu-id="d21ac-225">Email</span></span>

<span data-ttu-id="d21ac-226">U kunt ongewenste e-mailberichten voorkomen door versleuteling te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d21ac-226">You can prevent unwanted sharing of emails by using encryption.</span></span> <span data-ttu-id="d21ac-227">Dit voorkomt dat e-mails worden doorgestuurd of op een andere manier worden gedeeld met niet-geautoriseerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d21ac-227">This prevents emails being forwarded or otherwise shared with unauthorized users.</span></span> <span data-ttu-id="d21ac-228">U kunt e-mailversleuteling inschakelen met behulp van gevoeligheidslabels.</span><span class="sxs-lookup"><span data-stu-id="d21ac-228">Email encryption can be enabled by using sensitivity labels.</span></span> <span data-ttu-id="d21ac-229">Zie [Toegang tot inhoud beperken door versleuteling te gebruiken met gevoeligheidslabels](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d21ac-229">See [Restrict access to content by using encryption in sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) for details.</span></span>

## <a name="download-or-file-copy"></a><span data-ttu-id="d21ac-230">Bestanden downloaden of kopiëren</span><span class="sxs-lookup"><span data-stu-id="d21ac-230">Download or file copy</span></span>

<span data-ttu-id="d21ac-231">Gebruikers die toegang hebben tot bestanden en mappen in Microsoft 365, kunnen bestanden downloaden en naar externe media kopiëren.</span><span class="sxs-lookup"><span data-stu-id="d21ac-231">Users who have access to files and folders in Microsoft 365 can download files and copy them to external media.</span></span> <span data-ttu-id="d21ac-232">U kunt het risico op ongewenste bestandsdeling beperken door de inhoud te versleutelen met behulp van gevoeligheidslabels.</span><span class="sxs-lookup"><span data-stu-id="d21ac-232">To reduce the risk of unwanted file sharing, you can encrypt the content by using sensitivity labels.</span></span>

## <a name="see-also"></a><span data-ttu-id="d21ac-233">Zie ook</span><span class="sxs-lookup"><span data-stu-id="d21ac-233">See also</span></span>

[<span data-ttu-id="d21ac-234">Overzicht van instellingen voor delen met gasten in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d21ac-234">Microsoft 365 guest sharing settings reference</span></span>](microsoft-365-guest-settings.md)
