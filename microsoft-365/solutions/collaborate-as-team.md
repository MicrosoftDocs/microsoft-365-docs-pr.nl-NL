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
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over de Microsoft 365-configuratiestappen die nodig zijn voor het instellen van een team voor taak, discussie en de samenwerking van documenten met gasten in teams.
ms.openlocfilehash: 34b7d5d47d7fb0c9196beda70184fa6510b6cc33
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780542"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="b6f0c-103">Met gasten samenwerken in een team</span><span class="sxs-lookup"><span data-stu-id="b6f0c-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="b6f0c-104">Als u met gasten in documenten, taken en gesprekken moet samenwerken, is het raadzaam Microsoft teams te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="b6f0c-105">Teams biedt alle samenwerkingsfuncties die beschikbaar zijn in Office en SharePoint met permanente chat en een aanpasbare en uitbreidbare set samenwerkingsprogramma's in een geïntegreerde gebruikerservaring.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="b6f0c-106">In dit artikel worden 365 de stappen beschreven die u moet uitvoeren om een team voor samenwerking met gasten in te stellen.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="b6f0c-107">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="b6f0c-107">Video demonstration</span></span>

<span data-ttu-id="b6f0c-108">In deze video ziet u de configuratiestappen die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="b6f0c-109">Instellingen voor externe samenwerking van Azure</span><span class="sxs-lookup"><span data-stu-id="b6f0c-109">Azure External collaboration settings</span></span>

<span data-ttu-id="b6f0c-110">Delen in Microsoft 365 wordt bepaald door de [instellingen voor B2B External collaboration in azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="b6f0c-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="b6f0c-111">Als gasten delen is uitgeschakeld of niet beschikbaar is in azure AD, worden de instellingen voordelen overschreven die u configureert in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="b6f0c-112">Controleer de instellingen van de externe samenwerkings instellingen om te controleren of delen met gasten niet is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-112">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="b6f0c-114">Externe samenwerkings instellingen instellen</span><span class="sxs-lookup"><span data-stu-id="b6f0c-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="b6f0c-115">Meld u aan bij Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="b6f0c-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="b6f0c-116">Klik in het linker navigatiedeelvenster op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="b6f0c-117">Klik op **externe identiteiten**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-117">Click **External identities**.</span></span>
4. <span data-ttu-id="b6f0c-118">Klik in het scherm aan de **slag** in het linker navigatiedeelvenster op **instellingen voor externe samenwerking**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="b6f0c-119">Zorg ervoor dat **beheerders en gebruikers in de rol gast uitnodiging kunnen uitnodigen** en dat **leden kunnen uitnodigen** zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="b6f0c-120">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="b6f0c-121">Let op de instellingen in de sectie **samenwerkings beperkingen** .</span><span class="sxs-lookup"><span data-stu-id="b6f0c-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="b6f0c-122">Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="b6f0c-123">Als u met gasten in meerdere organisaties werkt, is het raadzaam om de toegang van Directory-gegevens te beperken.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="b6f0c-124">Hiermee kunt u voorkomen dat ze zien welke iemand anders een gast is in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="b6f0c-125">Als u dit wilt doen, selecteert u onder **toegangsbeperkingen** voor gastgebruikers de optie **gastgebruikers beperkte toegang tot eigenschappen en lidmaatschap van adreslijst objecten** of **toegang voor gastgebruikers is beperkt tot eigenschappen en lidmaatschap van eigen directoryobjecten**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="b6f0c-126">Instellingen voor gasttoegang voor teams</span><span class="sxs-lookup"><span data-stu-id="b6f0c-126">Teams guest access settings</span></span>

<span data-ttu-id="b6f0c-127">Teams heeft een schakeloptie voor het in-en uitschakelen van een gast verbinding en een verscheidenheid aan instellingen die beschikbaar zijn om te bepalen wat gasten in een team kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="b6f0c-128">De schakeloptie voor het inschakelen van **gasttoegang in teams** moet zijn **ingeschakeld** voor gasttoegang om in teams te kunnen werken.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="b6f0c-129">Zorg ervoor dat gasttoegang is ingeschakeld in teams en breng de gewenste wijzigingen aan in de gastinstellingen op basis van de behoeften van uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="b6f0c-130">Houd er rekening mee dat deze instellingen van invloed zijn op alle teams.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-130">Keep in mind that these settings affect all teams.</span></span>

![Schermafbeelding van wisselknop Gasttoegang in Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="b6f0c-132">Instellingen voor gasttoegang in Teams instellen</span><span class="sxs-lookup"><span data-stu-id="b6f0c-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="b6f0c-133">Meld u aan bij het Microsoft 365-beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b6f0c-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="b6f0c-134">Klik in het linker navigatiedeelvenster op **AllesWeergeven**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="b6f0c-135">Klik onder **Beheercentra** op **Teams**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="b6f0c-136">Vouw in het team centrum voor teams in het linker navigatiedeelvenster **instellingen voor de gehele organisatie** uit en klik op **gasttoegang**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="b6f0c-137">Zorg ervoor dat **Gasttoegang in Teams toestaan** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="b6f0c-138">Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="b6f0c-139">Wanneer teams gasttoegang is ingeschakeld, kunt u optioneel gasttoegang tot afzonderlijke teams en de bijbehorende SharePoint-sites met behulp van behulp van vertrouwelijkheids labels beheren.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-139">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="b6f0c-140">Zie [Gevoeligheidslabels gebruiken om inhoud te beveiligen in Microsoft Teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-140">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="b6f0c-141">Het kan tot 24 uur duren voordat de instellingen van de team gast actief raken nadat u deze hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-141">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="b6f0c-142">Gastinstellingen voor Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="b6f0c-142">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="b6f0c-143">Teams gebruikt Microsoft 365-groepen voor lidmaatschap van een team.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-143">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="b6f0c-144">De instellingen voor gasttoegang in Microsoft 365 groepen moeten zijn ingeschakeld, zodat gasttoegang in teams kan werken.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-144">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="b6f0c-146">De gastinstellingen van Microsoft 365 groepen instellen</span><span class="sxs-lookup"><span data-stu-id="b6f0c-146">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="b6f0c-147">In het Microsoft 365-Beheercentrum, in het linker navigatiedeelvenster, vouwt u **instellingen** uit.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-147">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="b6f0c-148">Klik op **instellingen voor organisatie**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-148">Click **Org settings**.</span></span>
3. <span data-ttu-id="b6f0c-149">Klik in de lijst op **Microsoft 365 groepen**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-149">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="b6f0c-150">Zorg ervoor dat de selectievakjes **eigenaren van gebruikers buiten uw organisatie toevoegen aan Microsoft 365-groepen als gasten** en de selectievakjes voor **groepsleden toegang krijgen tot groepsinhoud** beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-150">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="b6f0c-151">Als u wijzigingen hebt aangebracht, klikt u op **wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-151">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="b6f0c-152">Instellingen voordelen van SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="b6f0c-152">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="b6f0c-153">Inhoud van teams, zoals bestanden, mappen en lijsten, worden allemaal opgeslagen in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-153">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="b6f0c-154">Als u wilt dat gasten toegang hebben tot deze items in teams, moet u de instellingen voordelen van SharePoint op organisatieniveau toestaan voordelen met gasten.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-154">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="b6f0c-155">De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites, waaronder sites die zijn gekoppeld aan teams.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-155">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="b6f0c-156">Site-instellingen kunnen niet hoger zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-156">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="b6f0c-157">Als u het delen van bestanden en mappen met niet-geverifieerde personen wilt toestaan, kiest u **iedereen**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-157">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="b6f0c-158">Als u ervoor wilt zorgen dat alle gasten verificatie verifiëren, kiest u **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-158">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="b6f0c-159">Kies de meest strikte instelling die moet worden gebruikt door alle sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-159">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="b6f0c-161">Instellingen voordelen van SharePoint op organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="b6f0c-161">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="b6f0c-162">Klik in het Microsoft 365-Beheercentrum, in het linker navigatiedeelvenster, onder **beheer centra** op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-162">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="b6f0c-163">Vouw in het SharePoint-Beheercentrum in het linker navigatievenster **beleidsregels** uit en klik vervolgens op **delen**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-163">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="b6f0c-164">Zorg ervoor dat extern delen voor SharePoint is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-164">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="b6f0c-165">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-165">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="b6f0c-166">Standaard koppelingsinstellingen op SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="b6f0c-166">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="b6f0c-167">De standaardinstellingen voor het koppelen van bestanden en mappen bepalen de koppelingsoptie die standaard wordt getoond aan gebruikers wanneer ze een bestand of map delen.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-167">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="b6f0c-168">Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat u het deelt.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-168">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="b6f0c-169">Houd er rekening mee dat deze instelling van invloed is op alle teams en SharePoint-sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-169">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="b6f0c-170">Kies een van de volgende koppelingstypen die standaard worden geselecteerd wanneer gebruikers bestanden en mappen delen:</span><span class="sxs-lookup"><span data-stu-id="b6f0c-170">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="b6f0c-171">**Iedereen met de koppeling** : Kies deze optie als u verwacht dat u niet-geverifieerde bestanden en mappen wilt delen.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-171">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="b6f0c-172">Als u iedereen wilt toestaan die wel of niet is gemachtigd voor het delen van *onbevoegd* delen, kunt u het beste een van de andere opties als standaard instellen.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-172">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="b6f0c-173">Dit koppelingstype is alleen beschikbaar als **iedereen** het delen heeft toegestaan.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-173">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="b6f0c-174">**Alleen personen in uw organisatie** : Kies deze optie als u verwacht dat u de meeste bestanden en mappen wilt delen met personen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-174">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="b6f0c-175">**Specifieke personen** : Houd deze optie ingedrukt als u verwacht dat u een groot aantal bestanden en mappen deelt met gasten.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-175">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="b6f0c-176">Dit type koppeling werkt met gasten en vereist ze voor verificatie.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-176">This type of link works with guests and requires them to authenticate.</span></span>
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="b6f0c-178">De standaardinstellingen voor de koppeling naar het SharePoint-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="b6f0c-178">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="b6f0c-179">Ga naar de pagina delen in het SharePoint-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-179">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="b6f0c-180">Selecteer onder **koppelingen voor bestanden en mappen** de standaardkoppeling voordelen die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-180">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="b6f0c-181">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-181">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="b6f0c-182">Een team maken</span><span class="sxs-lookup"><span data-stu-id="b6f0c-182">Create a team</span></span>

<span data-ttu-id="b6f0c-183">De volgende stap is het maken van het team dat u wilt gebruiken om samen te werken met gasten.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-183">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="b6f0c-184">Een team maken</span><span class="sxs-lookup"><span data-stu-id="b6f0c-184">To create a team</span></span>
1. <span data-ttu-id="b6f0c-185">Klik in teams op het tabblad **teams** op **lid worden van een team of een team maken** onderaan in het linkerdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-185">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="b6f0c-186">Klik op **een team maken**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-186">Click **Create a team**.</span></span>
3. <span data-ttu-id="b6f0c-187">Klik op **zelf een team samenstellen**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-187">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="b6f0c-188">Kies **privé** of **openbaar**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-188">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="b6f0c-189">Typ een naam en beschrijving voor het team en klik vervolgens op **maken**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-189">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="b6f0c-190">Klik op **overslaan**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-190">Click **Skip**.</span></span>

<span data-ttu-id="b6f0c-191">We nodigen later gebruikers uit.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-191">We'll invite users later.</span></span> <span data-ttu-id="b6f0c-192">Vervolgens moet u de instellingen voordelen op siteniveau controleren voor de SharePoint-site die is gekoppeld aan het team.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-192">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="b6f0c-193">Instellingen voordelen op SharePoint-siteniveau</span><span class="sxs-lookup"><span data-stu-id="b6f0c-193">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="b6f0c-194">Controleer de instellingen voordelen op siteniveau om ervoor te zorgen dat u het gewenste type toegang toestaat voor dit team.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-194">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="b6f0c-195">Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **iedereen**, maar u wilt dat alle gasten verificatie voor dit team hebben, controleert u of de instellingen voordelen op het siteniveau zijn ingesteld op **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-195">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="b6f0c-197">Instellingen voordelen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="b6f0c-197">To set site-level sharing settings</span></span>
1. <span data-ttu-id="b6f0c-198">Vouw in het SharePoint-Beheercentrum in het linker navigatievenster **sites** uit en klik op **actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-198">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="b6f0c-199">Selecteer de site voor het team dat u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-199">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="b6f0c-200">Klik op... en kies **delen**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-200">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="b6f0c-201">Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-201">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="b6f0c-202">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-202">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="b6f0c-203">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="b6f0c-203">Invite users</span></span>

<span data-ttu-id="b6f0c-204">Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u interne gebruikers en gasten aan uw team kunt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-204">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="b6f0c-205">Interne gebruikers uitnodigen voor een team</span><span class="sxs-lookup"><span data-stu-id="b6f0c-205">To invite internal users to a team</span></span>
1. <span data-ttu-id="b6f0c-206">Klik in het team op **meer opties** ( **\*\*\*** ) en klik vervolgens op **lid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-206">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="b6f0c-207">Typ de naam van de persoon die u wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-207">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="b6f0c-208">Klik op **toevoegen** en klik vervolgens op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-208">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="b6f0c-209">Gasten uitnodigen voor een team</span><span class="sxs-lookup"><span data-stu-id="b6f0c-209">To invite guests to a team</span></span>
1. <span data-ttu-id="b6f0c-210">Klik in het team op **meer opties** ( **\*\*\*** ) en klik vervolgens op **lid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-210">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="b6f0c-211">Voer het e-mailadres in van de gast die u wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-211">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="b6f0c-212">Klik op **gast gegevens bewerken**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-212">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="b6f0c-213">Typ de volledige naam van de gast en klik op het vinkje.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-213">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="b6f0c-214">Klik op **toevoegen** en klik vervolgens op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="b6f0c-214">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6f0c-215">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b6f0c-215">See also</span></span>

[<span data-ttu-id="b6f0c-216">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="b6f0c-216">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="b6f0c-217">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="b6f0c-217">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="b6f0c-218">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="b6f0c-218">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="b6f0c-219">Een B2B-extranet maken met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="b6f0c-219">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="b6f0c-220">Integratie van SharePoint en OneDrive met Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="b6f0c-220">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="b6f0c-221">Opties voordelen zijn niet beschikbaar wanneer u deelt via SharePoint of OneDrive</span><span class="sxs-lookup"><span data-stu-id="b6f0c-221">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
