---
title: Samenwerken met gasten in een team
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
localization_priority: Priority
f1.keywords: NOCSH
description: Lees meer over de Microsoft 365-configuratiestappen die nodig zijn om een team in te stellen voor samenwerking aan taken, gesprekken en documentatie met gasten in Teams.
ms.openlocfilehash: 986f9c1f343c8ccc3d76557291938d170923c89b
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712316"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="6a785-103">Samenwerken met gasten in een team</span><span class="sxs-lookup"><span data-stu-id="6a785-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="6a785-104">Als u samen met gasten aan verschillende documenten, taken en gesprekken wilt werken, raden we u aan Microsoft Teams te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6a785-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="6a785-105">Teams biedt alle samenwerkingsfuncties die beschikbaar zijn in Office en SharePoint met een permanente chatfunctie en een aanpasbare en uitbreidbare set samenwerkingshulpmiddelen in een geïntegreerde gebruikerservaring.</span><span class="sxs-lookup"><span data-stu-id="6a785-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="6a785-106">In dit artikel worden de benodigde Microsoft 365-configuratiestappen beschreven voor het instellen van een team voor samenwerking met gasten.</span><span class="sxs-lookup"><span data-stu-id="6a785-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="6a785-107">Nadat u gasttoegang hebt geconfigureerd, kunt u gasten uitnodigen voor teams door de stappen te volgen in [Gasten toevoegen aan een team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="6a785-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="6a785-108">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="6a785-108">Video demonstration</span></span>

<span data-ttu-id="6a785-109">In deze video ziet u de configuratiestappen die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="6a785-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="6a785-110">Azure External-samenwerkingsinstellingen</span><span class="sxs-lookup"><span data-stu-id="6a785-110">Azure External collaboration settings</span></span>

<span data-ttu-id="6a785-111">Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de [B2B-instellingen voor externe samenwerking in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="6a785-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="6a785-112">Als delen met gasten is uitgeschakeld of wordt beperkt in Azure AD, overschrijft deze instelling alle instellingen voor delen die u configureert in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a785-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="6a785-113">Controleer de B2B-instellingen voor externe samenwerking om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="6a785-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="6a785-115">Instellingen voor externe samenwerking instellen</span><span class="sxs-lookup"><span data-stu-id="6a785-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="6a785-116">Meld u aan bij Azure Active Directory op [https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="6a785-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="6a785-117">Klik in het linkernavigatiedeelvenster op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6a785-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="6a785-118">Klik **Externe identiteiten**.</span><span class="sxs-lookup"><span data-stu-id="6a785-118">Click **External identities**.</span></span>
4. <span data-ttu-id="6a785-119">Klik in het linkernavigatiedeelvenster **Aan de slag** op **Instellingen voor externe samenwerking**.</span><span class="sxs-lookup"><span data-stu-id="6a785-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="6a785-120">Zorg ervoor dat **Beheerders en gebruikers in de rol van Afzender van gastuitnodigingen kunnen uitnodigingen verzenden** en **Leden kunnen uitnodigingen verzenden** beide zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="6a785-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="6a785-121">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a785-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="6a785-122">Let op de instellingen in de sectie **Samenwerkingsbeperkingen**.</span><span class="sxs-lookup"><span data-stu-id="6a785-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="6a785-123">Zorg ervoor dat de domeinen van de gasten met wie u wilt samenwerken, niet worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="6a785-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="6a785-124">Als u met gasten van meerdere organisaties werkt, wilt u mogelijk hun toegang tot adreslijstgegevens beperken.</span><span class="sxs-lookup"><span data-stu-id="6a785-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="6a785-125">Hiermee voorkomt u dat ze kunnen zien wie er nog meer een gast is in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="6a785-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="6a785-126">Hiervoor selecteert u onder **Toegangsbeperkingen voor gastgebruikers** de optie **Gastgebruikers hebben beperkte toegang tot eigenschappen en lidmaatschap van instellingen voor adreslijstobjecten** of **Toegang van gastgebruikers is beperkt tot eigenschappen en lidmaatschappen van hun eigen adreslijstobjecten**.</span><span class="sxs-lookup"><span data-stu-id="6a785-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="6a785-127">Instellingen voor gasttoegang in Teams</span><span class="sxs-lookup"><span data-stu-id="6a785-127">Teams guest access settings</span></span>

<span data-ttu-id="6a785-128">Teams heeft een hoofdoptie voor het in- en uitschakelen van gasttoegang en diverse instellingen die beschikbaar om te bepalen wat gasten in een team kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="6a785-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="6a785-129">De hoofdoptie, **Gasttoegang toestaan in Teams**, moet **aan** zijn voor gasttoegang in Teams.</span><span class="sxs-lookup"><span data-stu-id="6a785-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="6a785-130">Controleer of gasttoegang is ingeschakeld in Teams en pas de instellingen voor gasten aan op basis van de behoeften van uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="6a785-130">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="6a785-131">Houd er rekening mee dat deze instellingen van invloed zijn op alle teams.</span><span class="sxs-lookup"><span data-stu-id="6a785-131">Keep in mind that these settings affect all teams.</span></span>

![Schermafbeelding van wisselknop Gasttoegang in Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="6a785-133">Instellingen voor gasttoegang in Teams instellen</span><span class="sxs-lookup"><span data-stu-id="6a785-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="6a785-134">Meld u aan bij het Microsoft 365-beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6a785-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="6a785-135">Klik in het navigatievenster aan de linkerkant op **Alles weergeven**.</span><span class="sxs-lookup"><span data-stu-id="6a785-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="6a785-136">Klik onder **Beheercentra** op **Teams**.</span><span class="sxs-lookup"><span data-stu-id="6a785-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="6a785-137">Vouw in het Teams-beheercentrum in het linkernavigatievenster **Instellingen voor hele organisatie** uit en klik vervolgens op **Gasttoegang**.</span><span class="sxs-lookup"><span data-stu-id="6a785-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="6a785-138">Zorg ervoor dat **Gasttoegang in Teams toestaan** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="6a785-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="6a785-139">Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a785-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="6a785-140">Wanneer gasttoegang in Teams is ingeschakeld, kunt u desgewenst gasttoegang tot afzonderlijke teams en de bijbehorende SharePoint-sites bepalen met behulp van gevoeligheidslabels.</span><span class="sxs-lookup"><span data-stu-id="6a785-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="6a785-141">Zie [Gevoeligheidslabels gebruiken om inhoud te beveiligen in Microsoft Teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6a785-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="6a785-142">Het kan 24 uur duren voordat de instellingen voor gasten in Teams actief worden nadat u deze hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6a785-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="6a785-143">Gastinstellingen van Microsoft 365 Groepen</span><span class="sxs-lookup"><span data-stu-id="6a785-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="6a785-144">Teams gebruikt Microsoft 365 Groepen voor teamlidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="6a785-144">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="6a785-145">De gastinstellingen voor Microsoft 365 Groepen moeten zijn ingeschakeld om gasttoegang in Teams te laten werken.</span><span class="sxs-lookup"><span data-stu-id="6a785-145">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="6a785-147">Gastinstellingen van Microsoft 365 Groepen instellen</span><span class="sxs-lookup"><span data-stu-id="6a785-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="6a785-148">Vouw in het Microsoft 365-beheercentrum **Instellingen** uit in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="6a785-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="6a785-149">Klik op **Organisatie-instellingen**.</span><span class="sxs-lookup"><span data-stu-id="6a785-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="6a785-150">Klik in de lijst op **Microsoft 365 Groepen**.</span><span class="sxs-lookup"><span data-stu-id="6a785-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="6a785-151">Zorg ervoor dat de selectievakjes **Groepseigenaren toestaan personen van buiten de organisatie als gast aan Microsoft 365 Groepen toe te voegen** en **Gastgroepsleden toegang geven tot groepsinhoud** beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6a785-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="6a785-152">Als u wijzigingen hebt aangebracht, klikt u op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a785-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="6a785-153">Instellingen voor delen op organisatieniveau van SharePoint</span><span class="sxs-lookup"><span data-stu-id="6a785-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="6a785-154">Alle inhoud van Teams (zoals bestanden, mappen en lijsten) wordt opgeslagen in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6a785-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="6a785-155">Om gasten toegang te geven tot deze items in Teams, moeten de SharePoint-instellingen voor delen op organisatieniveau delen met gasten toestaan.</span><span class="sxs-lookup"><span data-stu-id="6a785-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="6a785-156">De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites, waaronder sites die zijn gekoppeld aan teams.</span><span class="sxs-lookup"><span data-stu-id="6a785-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="6a785-157">Site-instellingen mogen niet meer toestaan dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="6a785-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="6a785-158">Als u delen van bestanden en mappen met niet-geverifieerde personen wilt toestaan, kiest u **Iedereen**.</span><span class="sxs-lookup"><span data-stu-id="6a785-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="6a785-159">Als u ervoor wilt zorgen dat alle gasten zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="6a785-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="6a785-160">Kies de ruimste instelling die nodig is voor de sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6a785-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="6a785-162">Instellingen voor delen op organisatieniveau van SharePoint instellen</span><span class="sxs-lookup"><span data-stu-id="6a785-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="6a785-163">In het Microsoft 365-beheercentrum klikt u onder **Beheercentra** op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="6a785-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="6a785-164">Vouw in het SharePoint-beheercentrum **Beleid** uit in het navigatievenster aan de linkerkant en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="6a785-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="6a785-165">Zorg ervoor dat extern delen voor SharePoint is ingesteld op **Iedereen** of **Nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="6a785-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="6a785-166">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a785-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="6a785-167">Standaardkoppelingsinstellingen op organisatieniveau van SharePoint</span><span class="sxs-lookup"><span data-stu-id="6a785-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="6a785-168">De standaardkoppelingsinstellingen voor bestanden en mappen bepalen de koppelingsoptie die standaard voor gebruikers wordt weergegeven wanneer ze een bestand of map delen.</span><span class="sxs-lookup"><span data-stu-id="6a785-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="6a785-169">Gebruikers kunnen voor het delen desgewenst het koppelingstype wijzigen in een van de andere opties.</span><span class="sxs-lookup"><span data-stu-id="6a785-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="6a785-170">Houd er rekening mee dat deze instelling van invloed is op alle teams en SharePoint-sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6a785-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="6a785-171">Kies een van de volgende koppelingstypen die standaard wordt geselecteerd wanneer gebruikers bestanden en mappen delen:</span><span class="sxs-lookup"><span data-stu-id="6a785-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="6a785-172">**Iedereen met de koppeling** - Kies deze optie als u verwacht dat u met veel niet-geverifieerde mensen gaat delen.</span><span class="sxs-lookup"><span data-stu-id="6a785-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="6a785-173">Als u *Iedereen*-koppelingen wilt toestaan, maar u zich zorgen maakt over onbedoeld niet-geverifieerd delen, kunt u een van de andere opties als standaardoptie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6a785-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="6a785-174">Dit koppelingstype is alleen beschikbaar als u **Iedereen** hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6a785-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="6a785-175">**Alleen personen in uw organisatie**: kies deze optie als u verwacht dat de meeste bestanden en mappen worden gedeeld met personen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6a785-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="6a785-176">**Specifieke personen** - overweeg deze optie als u verwacht veel bestanden en mappen te delen met gasten.</span><span class="sxs-lookup"><span data-stu-id="6a785-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="6a785-177">Dit type koppeling werkt met gasten en vereist verificatie.</span><span class="sxs-lookup"><span data-stu-id="6a785-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="6a785-179">Standaardkoppelingsinstellingen op organisatieniveau van SharePoint instellen</span><span class="sxs-lookup"><span data-stu-id="6a785-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="6a785-180">Navigeer naar de pagina Delen in het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="6a785-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="6a785-181">Selecteer onder **Koppelingen naar bestanden en mappen** de standaardkoppeling voor delen die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6a785-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="6a785-182">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a785-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="6a785-183">Een team maken</span><span class="sxs-lookup"><span data-stu-id="6a785-183">Create a team</span></span>

<span data-ttu-id="6a785-184">De volgende stap is het maken van het team dat u wilt gebruiken voor samenwerking met gasten.</span><span class="sxs-lookup"><span data-stu-id="6a785-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="6a785-185">Een team maken</span><span class="sxs-lookup"><span data-stu-id="6a785-185">To create a team</span></span>
1. <span data-ttu-id="6a785-186">Klik in Teams op het tabblad **Teams** op **Deelnemen aan een team of een team maken** onderin het linkerdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="6a785-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="6a785-187">Klik op **Een team maken**.</span><span class="sxs-lookup"><span data-stu-id="6a785-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="6a785-188">Klik op **Een volledig nieuw team maken**.</span><span class="sxs-lookup"><span data-stu-id="6a785-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="6a785-189">Kies **Privé** of **Openbaar**.</span><span class="sxs-lookup"><span data-stu-id="6a785-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="6a785-190">Typ een naam en beschrijving voor het team en klik vervolgens op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="6a785-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="6a785-191">Klik op **Overslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a785-191">Click **Skip**.</span></span>

<span data-ttu-id="6a785-192">We nodigen gebruikers later uit.</span><span class="sxs-lookup"><span data-stu-id="6a785-192">We'll invite users later.</span></span> <span data-ttu-id="6a785-193">Vervolgens is het belangrijk dat u de instellingen voor delen op siteniveau controleert voor de SharePoint-site die is gekoppeld aan het team.</span><span class="sxs-lookup"><span data-stu-id="6a785-193">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="6a785-194">Instellingen voor het delen op siteniveau in SharePoint</span><span class="sxs-lookup"><span data-stu-id="6a785-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="6a785-195">Controleer de instellingen voor delen op siteniveau om er zeker van te zijn dat het type toegang wordt toegestaan dat u voor dit team wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6a785-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="6a785-196">Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **Iedereen**, maar u wilt dat alle gasten zich verifiëren voor dit team, zorg er dan voor dat de instellingen voor delen op siteniveau zijn ingesteld op **Nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="6a785-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="6a785-198">Instellingen voor delen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="6a785-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="6a785-199">Vouw in het SharePoint-beheercentrum **Sites** uit in het navigatievenster aan de linkerkant en klik op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="6a785-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="6a785-200">Selecteer de site voor het team dat u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="6a785-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="6a785-201">Klik ... en kies **Delen**.</span><span class="sxs-lookup"><span data-stu-id="6a785-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="6a785-202">Zorg ervoor dat delen is ingesteld op **Iedereen** of **Nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="6a785-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="6a785-203">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a785-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="6a785-204">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="6a785-204">Invite users</span></span>

<span data-ttu-id="6a785-205">Instellingen voor het delen met gasten zijn nu geconfigureerd, zodat u interne gebruikers en gasten kunt toevoegen aan uw team.</span><span class="sxs-lookup"><span data-stu-id="6a785-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="6a785-206">Interne gebruikers uitnodigen voor een team</span><span class="sxs-lookup"><span data-stu-id="6a785-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="6a785-207">Klik in het team op **Meer opties** (**\*\*\***), en klik vervolgens op **Lid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6a785-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="6a785-208">Typ de naam van de persoon die u wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="6a785-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="6a785-209">Klik op **Toevoegen** en klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="6a785-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="6a785-210">Gasten uitnodigen voor een team</span><span class="sxs-lookup"><span data-stu-id="6a785-210">To invite guests to a team</span></span>
1. <span data-ttu-id="6a785-211">Klik in het team op **Meer opties** (**\*\*\***), en klik vervolgens op **Lid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6a785-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="6a785-212">Typ het e-mailadres van de gast die u wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="6a785-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="6a785-213">Klik op **Gegevens van gasten bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6a785-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="6a785-214">Typ de volledige naam van de gast en klik op het vinkje.</span><span class="sxs-lookup"><span data-stu-id="6a785-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="6a785-215">Klik op **Toevoegen** en klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="6a785-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a785-216">Zie ook</span><span class="sxs-lookup"><span data-stu-id="6a785-216">See also</span></span>

[<span data-ttu-id="6a785-217">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="6a785-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="6a785-218">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="6a785-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="6a785-219">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="6a785-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="6a785-220">Een B2B-extranet maken met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="6a785-220">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="6a785-221">Integratie van SharePoint en OneDrive met Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="6a785-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="6a785-222">Opties voor delen worden grijs wanneer u deelt vanuit SharePoint of OneDrive</span><span class="sxs-lookup"><span data-stu-id="6a785-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
