---
title: Met gasten samenwerken in een team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Meer informatie over de Microsoft 365-configuratiestappen die nodig zijn voor het instellen van een team voor samenwerking met gasten in teams.
ms.openlocfilehash: e92397c7b8d4a4192fb36a52a76679269be53b3b
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357792"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="15a43-103">Met gasten samenwerken in een team</span><span class="sxs-lookup"><span data-stu-id="15a43-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="15a43-104">Als u met gasten in documenten, taken en gesprekken moet samenwerken, is het raadzaam Microsoft teams te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="15a43-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="15a43-105">Teams biedt alle samenwerkingsfuncties die beschikbaar zijn in Office en SharePoint met permanente chat en een aanpasbare en uitbreidbare set samenwerkingsprogramma's in een geïntegreerde gebruikerservaring.</span><span class="sxs-lookup"><span data-stu-id="15a43-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="15a43-106">In dit artikel worden 365 de stappen beschreven die u moet uitvoeren om een team voor samenwerking met gasten in te stellen.</span><span class="sxs-lookup"><span data-stu-id="15a43-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="15a43-107">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="15a43-107">Video demonstration</span></span>

<span data-ttu-id="15a43-108">In deze video ziet u de configuratiestappen die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="15a43-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="15a43-109">Instellingen van Azure organisatie relaties</span><span class="sxs-lookup"><span data-stu-id="15a43-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="15a43-110">Delen in Microsoft 365 wordt bepaald met het hoogste niveau van de [instellingen voor organisatie relaties in azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="15a43-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="15a43-111">Als gasten delen is uitgeschakeld of niet beschikbaar is in azure AD, worden de instellingen voordelen die u configureert in Microsoft 365 genegeerd.</span><span class="sxs-lookup"><span data-stu-id="15a43-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="15a43-112">Controleer de instellingen van de organisatie om te controleren of delen met gasten niet is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="15a43-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="15a43-114">Instellingen voor organisatie relaties instellen</span><span class="sxs-lookup"><span data-stu-id="15a43-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="15a43-115">Meld u aan bij Microsoft Azure at [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="15a43-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="15a43-116">Klik in het linkernavigatievenster op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="15a43-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="15a43-117">Klik in het deelvenster **overzicht** op **externe identiteiten**.</span><span class="sxs-lookup"><span data-stu-id="15a43-117">In the **Overview** pane, click **External identities**.</span></span>
4. <span data-ttu-id="15a43-118">Klik in het deelvenster met **organisatie-id's** op **instellingen voor externe samenwerking**.</span><span class="sxs-lookup"><span data-stu-id="15a43-118">In the **Organizational identities** pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="15a43-119">Zorg ervoor dat **beheerders en gebruikers in de rol gast uitnodiging kunnen uitnodigen** en dat **leden kunnen uitnodigen** zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="15a43-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="15a43-120">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="15a43-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="15a43-121">Let op de instellingen in de sectie **samenwerkings beperkingen** .</span><span class="sxs-lookup"><span data-stu-id="15a43-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="15a43-122">Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="15a43-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="15a43-123">Als u met gasten in meerdere organisaties werkt, is het raadzaam om de toegang van Directory-gegevens te beperken.</span><span class="sxs-lookup"><span data-stu-id="15a43-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="15a43-124">Hiermee kunt u voorkomen dat ze zien welke iemand anders een gast is in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="15a43-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="15a43-125">Als u dit wilt doen, selecteert u onder **toegangsbeperkingen**voor gastgebruikers de optie **gastgebruikers beperkte toegang tot eigenschappen en lidmaatschap van adreslijst objecten** of **toegang voor gastgebruikers is beperkt tot eigenschappen en lidmaatschap van eigen directoryobjecten**.</span><span class="sxs-lookup"><span data-stu-id="15a43-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="15a43-126">Instellingen voor gasttoegang voor teams</span><span class="sxs-lookup"><span data-stu-id="15a43-126">Teams guest access settings</span></span>

<span data-ttu-id="15a43-127">Teams heeft een schakeloptie voor het in-en uitschakelen van een gast verbinding en een verscheidenheid aan instellingen die beschikbaar zijn om te bepalen wat gasten in een team kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="15a43-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="15a43-128">De schakeloptie voor het inschakelen van **gasttoegang in teams** moet zijn **ingeschakeld** voor gasttoegang om in teams te kunnen werken.</span><span class="sxs-lookup"><span data-stu-id="15a43-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="15a43-129">Zorg ervoor dat gasttoegang is ingeschakeld in teams en breng de gewenste wijzigingen aan in de gastinstellingen op basis van de behoeften van uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="15a43-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="15a43-130">Houd er rekening mee dat deze instellingen van invloed zijn op alle teams.</span><span class="sxs-lookup"><span data-stu-id="15a43-130">Keep in mind that these settings affect all teams.</span></span>

![Schermafbeelding van wisselknop Gasttoegang in Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="15a43-132">Instellingen voor gasttoegang in Teams instellen</span><span class="sxs-lookup"><span data-stu-id="15a43-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="15a43-133">Meld u aan bij het Microsoft 365-beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="15a43-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="15a43-134">Klik in het navigatievenster aan de linkerkant op **Alles weergeven**.</span><span class="sxs-lookup"><span data-stu-id="15a43-134">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="15a43-135">Klik onder **Beheercentra** op **Teams**.</span><span class="sxs-lookup"><span data-stu-id="15a43-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="15a43-136">Vouw in het Teams-beheercentrum in het linkernavigatievenster **Instellingen voor hele organisatie** uit en klik vervolgens op **Gasttoegang**.</span><span class="sxs-lookup"><span data-stu-id="15a43-136">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="15a43-137">Zorg ervoor dat **Gasttoegang in Teams toestaan** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="15a43-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="15a43-138">Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="15a43-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="15a43-139">Het kan 24 uur duren voordat de instelling voor gasten in Teams actief wordt nadat u deze hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="15a43-139">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="15a43-140">Gastinstellingen voor Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="15a43-140">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="15a43-141">Teams gebruikt Microsoft 365-groepen voor lidmaatschap van een team.</span><span class="sxs-lookup"><span data-stu-id="15a43-141">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="15a43-142">De instellingen voor gasttoegang in Microsoft 365 groepen moeten zijn ingeschakeld, zodat gasttoegang in teams kan werken.</span><span class="sxs-lookup"><span data-stu-id="15a43-142">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="15a43-144">De gastinstellingen van Microsoft 365 groepen instellen</span><span class="sxs-lookup"><span data-stu-id="15a43-144">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="15a43-145">In het Microsoft 365-Beheercentrum, in het linker navigatiemenu, vouwt u **instellingen**uit.</span><span class="sxs-lookup"><span data-stu-id="15a43-145">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="15a43-146">Klik op **instellingen voor organisatie**.</span><span class="sxs-lookup"><span data-stu-id="15a43-146">Click **Org settings**.</span></span>
3. <span data-ttu-id="15a43-147">Klik in de lijst op **Microsoft 365 groepen**.</span><span class="sxs-lookup"><span data-stu-id="15a43-147">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="15a43-148">Zorg ervoor dat de selectievakjes **leden van uw organisatie toegang hebben tot de groepsinhoud** van de organisatie en **groepseigenaren personen van buiten uw organisatie toevoegen aan groepen** .</span><span class="sxs-lookup"><span data-stu-id="15a43-148">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="15a43-149">Als u wijzigingen hebt aangebracht, klikt u op **wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="15a43-149">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="15a43-150">Instellingen voordelen van SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="15a43-150">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="15a43-151">Inhoud van teams, zoals bestanden, mappen en lijsten, worden allemaal opgeslagen in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="15a43-151">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="15a43-152">Als u wilt dat gasten toegang hebben tot deze items in teams, moet u de instellingen voordelen van SharePoint op organisatieniveau toestaan voordelen met gasten.</span><span class="sxs-lookup"><span data-stu-id="15a43-152">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="15a43-153">De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites, waaronder sites die zijn gekoppeld aan teams.</span><span class="sxs-lookup"><span data-stu-id="15a43-153">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="15a43-154">Site-instellingen kunnen niet hoger zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="15a43-154">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="15a43-155">Als u het delen van bestanden en mappen met niet-geverifieerde personen wilt toestaan, kiest u **iedereen**.</span><span class="sxs-lookup"><span data-stu-id="15a43-155">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="15a43-156">Als u ervoor wilt zorgen dat alle gasten verificatie verifiëren, kiest u **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="15a43-156">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="15a43-157">Kies de meest strikte instelling die moet worden gebruikt door alle sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="15a43-157">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="15a43-159">Instellingen voordelen van SharePoint-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="15a43-159">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="15a43-160">Klik in het Microsoft 365-Beheercentrum, in het linkernavigatievenster, onder **beheer centra**op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="15a43-160">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="15a43-161">Vouw in het SharePoint-Beheercentrum in het linkernavigatievenster **beleidsregels** uit en klik vervolgens op **delen**.</span><span class="sxs-lookup"><span data-stu-id="15a43-161">In the SharePoint admin center, in the left navigation, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="15a43-162">Zorg ervoor dat extern delen voor SharePoint is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="15a43-162">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="15a43-163">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="15a43-163">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="15a43-164">Standaard koppelingsinstellingen SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="15a43-164">SharePoint organization level default link settings</span></span>

<span data-ttu-id="15a43-165">De standaardinstellingen voor het koppelen van bestanden en mappen bepalen welke koppelingsoptie standaard voor de gebruiker wordt weergegeven wanneer ze een bestand of map delen.</span><span class="sxs-lookup"><span data-stu-id="15a43-165">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="15a43-166">Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat u het deelt.</span><span class="sxs-lookup"><span data-stu-id="15a43-166">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="15a43-167">Houd er rekening mee dat deze instelling van invloed is op alle teams en SharePoint-sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="15a43-167">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="15a43-168">Kies het type koppeling dat standaard wordt geselecteerd wanneer gebruikers bestanden en mappen delen:</span><span class="sxs-lookup"><span data-stu-id="15a43-168">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="15a43-169">**Iedereen met de koppeling** : Kies deze optie als u verwacht dat u niet-geverifieerde bestanden en mappen wilt delen.</span><span class="sxs-lookup"><span data-stu-id="15a43-169">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="15a43-170">Als u iedereen wilt toestaan die wel of niet is gemachtigd voor het delen van *onbevoegd* delen, kunt u het beste een van de andere opties als standaard instellen.</span><span class="sxs-lookup"><span data-stu-id="15a43-170">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="15a43-171">Dit koppelingstype is alleen beschikbaar als **iedereen** het delen heeft toegestaan.</span><span class="sxs-lookup"><span data-stu-id="15a43-171">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="15a43-172">**Alleen personen in uw organisatie** : Kies deze optie als u verwacht dat u de meeste bestanden en mappen wilt delen met personen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="15a43-172">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="15a43-173">**Specifieke personen** : Houd deze optie ingedrukt als u verwacht dat u een groot aantal bestanden en mappen deelt met gasten.</span><span class="sxs-lookup"><span data-stu-id="15a43-173">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="15a43-174">Dit type koppeling werkt met gasten en vereist ze voor verificatie.</span><span class="sxs-lookup"><span data-stu-id="15a43-174">This type of link works with guests and requires them to authenticate.</span></span>
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="15a43-176">De standaardinstellingen voor de koppeling naar het SharePoint-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="15a43-176">To set the SharePoint organization level default link settings</span></span>

1. <span data-ttu-id="15a43-177">Ga naar de pagina delen in het SharePoint-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="15a43-177">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="15a43-178">Selecteer onder **koppelingen voor bestanden en mappen**de standaardkoppeling voordelen die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="15a43-178">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="15a43-179">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="15a43-179">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="15a43-180">Een team maken</span><span class="sxs-lookup"><span data-stu-id="15a43-180">Create a team</span></span>

<span data-ttu-id="15a43-181">De volgende stap is het maken van het team dat u wilt gebruiken om samen te werken met gasten.</span><span class="sxs-lookup"><span data-stu-id="15a43-181">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="15a43-182">Een team maken</span><span class="sxs-lookup"><span data-stu-id="15a43-182">To create a team</span></span>
1. <span data-ttu-id="15a43-183">Klik in teams op het tabblad **teams** op **lid worden van een team of een team maken** onderaan in het linkerdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="15a43-183">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="15a43-184">Klik op **een team maken**.</span><span class="sxs-lookup"><span data-stu-id="15a43-184">Click **Create a team**.</span></span>
3. <span data-ttu-id="15a43-185">Klik op **zelf een team samenstellen**.</span><span class="sxs-lookup"><span data-stu-id="15a43-185">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="15a43-186">Kies **privé** of **openbaar**.</span><span class="sxs-lookup"><span data-stu-id="15a43-186">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="15a43-187">Typ een naam en beschrijving voor het team en klik vervolgens op **maken**.</span><span class="sxs-lookup"><span data-stu-id="15a43-187">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="15a43-188">Klik op **overslaan**.</span><span class="sxs-lookup"><span data-stu-id="15a43-188">Click **Skip**.</span></span>

<span data-ttu-id="15a43-189">We nodigen later gebruikers uit.</span><span class="sxs-lookup"><span data-stu-id="15a43-189">We'll invite users later.</span></span> <span data-ttu-id="15a43-190">Vervolgens moet u de instellingen voordelen op siteniveau controleren voor de SharePoint-site die is gekoppeld aan het team.</span><span class="sxs-lookup"><span data-stu-id="15a43-190">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="15a43-191">Instellingen voordelen op het SharePoint-siteniveau</span><span class="sxs-lookup"><span data-stu-id="15a43-191">SharePoint site level sharing settings</span></span>

<span data-ttu-id="15a43-192">Controleer de instellingen voordelen op siteniveau om ervoor te zorgen dat u het gewenste type toegang toestaat voor dit team.</span><span class="sxs-lookup"><span data-stu-id="15a43-192">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="15a43-193">Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **iedereen**, maar u wilt dat alle gasten verificatie voor dit team hebben, controleert u of de instellingen voordelen op het siteniveau zijn ingesteld op **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="15a43-193">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="15a43-195">Instellingen voordelen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="15a43-195">To set site-level sharing settings</span></span>
1. <span data-ttu-id="15a43-196">Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="15a43-196">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="15a43-197">Selecteer de site voor het team dat u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="15a43-197">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="15a43-198">Klik op het lint op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="15a43-198">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="15a43-199">Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="15a43-199">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="15a43-200">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="15a43-200">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="15a43-201">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="15a43-201">Invite users</span></span>

<span data-ttu-id="15a43-202">Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u interne gebruikers en gasten aan uw team kunt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="15a43-202">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="15a43-203">Interne gebruikers uitnodigen voor een team</span><span class="sxs-lookup"><span data-stu-id="15a43-203">To invite internal users to a team</span></span>
1. <span data-ttu-id="15a43-204">Klik in het team op **meer opties** ( **\*\*\*** ) en klik vervolgens op **lid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="15a43-204">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="15a43-205">Typ de naam van de persoon die u wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="15a43-205">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="15a43-206">Klik op **toevoegen**en klik vervolgens op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="15a43-206">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="15a43-207">Gasten uitnodigen voor een team</span><span class="sxs-lookup"><span data-stu-id="15a43-207">To invite guests to a team</span></span>
1. <span data-ttu-id="15a43-208">Klik in het team op **meer opties** ( **\*\*\*** ) en klik vervolgens op **lid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="15a43-208">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="15a43-209">Typ het e-mailadres van de gast die u wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="15a43-209">Type the email address of the guest who you want to invite.</span></span>
3. <span data-ttu-id="15a43-210">Klik op **gast gegevens bewerken**.</span><span class="sxs-lookup"><span data-stu-id="15a43-210">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="15a43-211">Typ de volledige naam van de gast en klik op het vinkje.</span><span class="sxs-lookup"><span data-stu-id="15a43-211">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="15a43-212">Klik op **toevoegen**en klik vervolgens op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="15a43-212">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="15a43-213">Zie ook</span><span class="sxs-lookup"><span data-stu-id="15a43-213">See Also</span></span>

[<span data-ttu-id="15a43-214">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="15a43-214">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="15a43-215">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="15a43-215">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="15a43-216">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="15a43-216">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="15a43-217">Een B2B-extranet maken met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="15a43-217">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="15a43-218">Integratie van SharePoint en OneDrive met Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="15a43-218">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)