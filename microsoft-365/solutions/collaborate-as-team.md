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
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over de configuratiestappen van Microsoft 365 die nodig zijn voor het instellen van een team voor samenwerking aan taken, gesprekken en documentatie met gasten in Teams.
ms.openlocfilehash: 66c5692dd8cd233d8b3639f8ce0755ce51b60c0a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233072"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="8a0c2-103">Samenwerken met gasten in een team</span><span class="sxs-lookup"><span data-stu-id="8a0c2-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="8a0c2-104">Als u met gasten wilt samenwerken in documenten, taken en gesprekken, raden we u aan Microsoft Teams te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="8a0c2-105">Teams biedt alle samenwerkingsfuncties die beschikbaar zijn in Office en SharePoint met permanente chat en een aanpasbare en uitvouwbare set hulpprogramma's voor samenwerking in een geïntegreerde gebruikerservaring.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="8a0c2-106">In dit artikel worden de configuratiestappen voor Microsoft 365 beschreven die nodig zijn om een team in te stellen voor samenwerking met gasten.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="8a0c2-107">Nadat u gasttoegang hebt geconfigureerd, kunt u gasten voor teams uitnodigen door de stappen te volgen in Gasten toevoegen [aan een team in Teams.](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f)</span><span class="sxs-lookup"><span data-stu-id="8a0c2-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="8a0c2-108">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="8a0c2-108">Video demonstration</span></span>

<span data-ttu-id="8a0c2-109">In deze video ziet u de configuratiestappen die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="8a0c2-110">Instellingen voor externe samenwerking van Azure</span><span class="sxs-lookup"><span data-stu-id="8a0c2-110">Azure External collaboration settings</span></span>

<span data-ttu-id="8a0c2-111">Delen in Microsoft 365 wordt op het hoogste niveau beheerd door de instellingen voor externe samenwerking van [B2B in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)</span><span class="sxs-lookup"><span data-stu-id="8a0c2-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="8a0c2-112">Als delen voor gasten is uitgeschakeld of beperkt in Azure AD, overschrijven deze instelling alle instellingen voor delen die u configureert in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="8a0c2-113">Controleer de instellingen voor externe samenwerking in B2B om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="8a0c2-115">Instellingen voor externe samenwerking instellen</span><span class="sxs-lookup"><span data-stu-id="8a0c2-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="8a0c2-116">Meld u aan bij Azure Active Directory op [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="8a0c2-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="8a0c2-117">Klik in het linkernavigatiedeelvenster op **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="8a0c2-118">Klik **op Externe identiteiten.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-118">Click **External identities**.</span></span>
4. <span data-ttu-id="8a0c2-119">Klik in **het scherm Aan de** slag in het linkernavigatiedeelvenster op Instellingen voor externe **samenwerking.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="8a0c2-120">Zorg ervoor **dat beheerders en gebruikers in** de rol van gast genodigden kunnen uitnodigen en dat Leden kunnen **uitnodigen** beide zijn ingesteld op **Ja.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="8a0c2-121">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="8a0c2-122">Let op de instellingen in **de sectie Beperkingen voor** samenwerking.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="8a0c2-123">Zorg ervoor dat de domeinen van de gasten met wie u wilt samenwerken, niet zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="8a0c2-124">Als u met gasten van meerdere organisaties werkt, wilt u mogelijk de toegang tot adreslijstgegevens beperken.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="8a0c2-125">Hierdoor kunnen ze niet zien wie er nog meer gast is in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="8a0c2-126">Selecteer hiervoor gastgebruikers die beperkte toegang hebben tot eigenschappen en het lidmaatschap van de instellingen voor adreslijstobjecten **of** de toegang van gastgebruikers **tot** eigenschappen en lidmaatschap van hun eigen adreslijstobjecten. </span><span class="sxs-lookup"><span data-stu-id="8a0c2-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="8a0c2-127">Instellingen voor gasttoegang in Teams</span><span class="sxs-lookup"><span data-stu-id="8a0c2-127">Teams guest access settings</span></span>

<span data-ttu-id="8a0c2-128">Teams heeft een schakelknop voor het in-/uitschakelen van gasten en er zijn diverse instellingen beschikbaar om te bepalen wat gasten in een team kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="8a0c2-129">De hoofdwisselknop, **Gasttoegang in Teams toestaan,** moet **zijn aan** staan om gasttoegang in Teams te kunnen werken.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="8a0c2-130">Controleer of gasttoegang is ingeschakeld in Teams en controleer of de gastinstellingen worden aangepast op basis van uw zakelijke behoeften.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-130">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="8a0c2-131">Houd er rekening mee dat deze instellingen van invloed zijn op alle teams.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-131">Keep in mind that these settings affect all teams.</span></span>

![Schermafbeelding van wisselknop Gasttoegang in Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="8a0c2-133">Instellingen voor gasttoegang in Teams instellen</span><span class="sxs-lookup"><span data-stu-id="8a0c2-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="8a0c2-134">Meld u aan bij het Microsoft 365-beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8a0c2-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="8a0c2-135">Klik in het linkernavigatiedeelvenster op **Alles weergeven.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="8a0c2-136">Klik onder **Beheercentra** op **Teams**.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="8a0c2-137">Vouw in het teams-beheercentrum in het linkernavigatiedeelvenster **de instellingen** voor de hele organisatie uit en klik op **Gasttoegang.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="8a0c2-138">Zorg ervoor dat **Gasttoegang in Teams toestaan** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="8a0c2-139">Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="8a0c2-140">Zodra gasttoegang in Teams is ingeschakeld, kunt u desgewenst de gasttoegang tot afzonderlijke teams en de bijbehorende SharePoint-sites bepalen aan de hand van gevoeligheidslabels.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="8a0c2-141">Zie [Gevoeligheidslabels gebruiken om inhoud te beveiligen in Microsoft Teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="8a0c2-142">Het kan tot 24 uur duren voordat de instellingen voor teams-gasten actief worden nadat u deze hebt in schakeld.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="8a0c2-143">Gastinstellingen voor Microsoft 365 Groepen</span><span class="sxs-lookup"><span data-stu-id="8a0c2-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="8a0c2-144">Teams gebruikt Microsoft 365 Groepen voor teamlidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-144">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="8a0c2-145">De gastinstellingen voor Microsoft 365 Groepen moeten zijn ingeschakeld om de gasttoegang in Teams te laten werken.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-145">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="8a0c2-147">Gastinstellingen voor Microsoft 365 Groepen instellen</span><span class="sxs-lookup"><span data-stu-id="8a0c2-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="8a0c2-148">Vouw in het Microsoft 365-beheercentrum in het linkernavigatiedeelvenster Instellingen **uit.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="8a0c2-149">Klik **op Organisatie-instellingen.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="8a0c2-150">Klik in de lijst op **Microsoft 365 Groepen.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="8a0c2-151">Zorg ervoor dat groepseigenaren personen van buiten uw organisatie als  gast aan **Microsoft 365** Groepen kunnen toevoegen en dat leden van de gastgroep toegang hebben tot de inhoud van de groep beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="8a0c2-152">Als u wijzigingen hebt aangebracht, klikt u **op Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="8a0c2-153">Instellingen voor delen op organisatieniveau van SharePoint</span><span class="sxs-lookup"><span data-stu-id="8a0c2-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="8a0c2-154">Inhoud van Teams, zoals bestanden, mappen en lijsten, worden allemaal opgeslagen in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="8a0c2-155">Om gasten toegang te geven tot deze items in Teams, moeten de instellingen voor delen op organisatieniveau toestaan dat ze kunnen delen met gasten.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="8a0c2-156">De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites, inclusief sites die zijn gekoppeld aan teams.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="8a0c2-157">Site-instellingen mogen niet meer ruim zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="8a0c2-158">Als u het delen van bestanden en mappen met niet-geauteerde personen wilt toestaan, kiest u **Iedereen.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="8a0c2-159">Als u ervoor wilt zorgen dat alle gasten zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="8a0c2-160">Kies de meest recente instelling die nodig is voor elke site in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="8a0c2-162">Instellingen voor delen op organisatieniveau instellen in SharePoint</span><span class="sxs-lookup"><span data-stu-id="8a0c2-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="8a0c2-163">Klik in het Microsoft 365-beheercentrum in het linkernavigatiedeelvenster, onder **Beheercentra,** op **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="8a0c2-164">Vouw in het SharePoint-beheercentrum in het linkernavigatiedeelvenster **Beleid** uit en klik op **Delen.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="8a0c2-165">Zorg ervoor dat extern delen voor SharePoint is ingesteld op **Iedereen** of **Nieuw en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="8a0c2-166">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="8a0c2-167">Standaardkoppelingsinstellingen op organisatieniveau in SharePoint</span><span class="sxs-lookup"><span data-stu-id="8a0c2-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="8a0c2-168">De standaardinstellingen voor bestands- en mapkoppelingen bepalen de koppelingsoptie die standaard aan gebruikers wordt weergegeven wanneer ze een bestand of map delen.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="8a0c2-169">Gebruikers kunnen desgewenst het koppelingstype wijzigen in een van de andere opties voordat ze gaan delen.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="8a0c2-170">Houd er rekening mee dat deze instelling van invloed is op alle teams en SharePoint-sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="8a0c2-171">Kies een van de volgende koppelingstypen die standaard wordt geselecteerd wanneer gebruikers bestanden en mappen delen:</span><span class="sxs-lookup"><span data-stu-id="8a0c2-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="8a0c2-172">**Iedereen met de koppeling:** kies deze optie als u verwacht dat er veel bestanden en mappen niet geauverticeerd worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="8a0c2-173">Als u iedereen-koppelingen *wilt* toestaan, maar u zich zorgen maakt over onbedoeld niet-geauteerde delen, kunt u een van de andere opties als standaardwaarde gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="8a0c2-174">Dit type koppeling is alleen beschikbaar als delen met iedereen **is** ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="8a0c2-175">**Alleen personen in uw organisatie:** kies deze optie als u verwacht dat de meeste bestanden en mappen worden gedeeld met personen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="8a0c2-176">**Specifieke personen:** overweeg deze optie als u veel bestanden en mappen met gasten wilt delen.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="8a0c2-177">Dit type koppeling werkt met gasten en vereist verificatie.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="8a0c2-179">De standaardkoppelingsinstellingen op organisatieniveau van SharePoint instellen</span><span class="sxs-lookup"><span data-stu-id="8a0c2-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="8a0c2-180">Ga naar de pagina Delen in het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="8a0c2-181">Selecteer **onder Koppelingen naar bestanden en** mappen de standaardkoppeling voor delen die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="8a0c2-182">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="8a0c2-183">Een team maken</span><span class="sxs-lookup"><span data-stu-id="8a0c2-183">Create a team</span></span>

<span data-ttu-id="8a0c2-184">De volgende stap is het maken van het team dat u wilt gebruiken om samen te werken met gasten.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="8a0c2-185">Een team maken</span><span class="sxs-lookup"><span data-stu-id="8a0c2-185">To create a team</span></span>
1. <span data-ttu-id="8a0c2-186">Klik in Teams op het **tabblad Teams** op Deelnemen of maak een **team** onderaan het linkerdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="8a0c2-187">Klik **op Een team maken.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="8a0c2-188">Klik **op Een nieuw team maken.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="8a0c2-189">Kies **Privé** of **Openbaar.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="8a0c2-190">Typ een naam en beschrijving voor het team en klik op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="8a0c2-191">Klik **op Overslaan.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-191">Click **Skip**.</span></span>

<span data-ttu-id="8a0c2-192">We nodigen gebruikers later uit.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-192">We'll invite users later.</span></span> <span data-ttu-id="8a0c2-193">Vervolgens is het belangrijk dat u de instellingen voor delen op siteniveau controleert voor de SharePoint-site die aan het team is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-193">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="8a0c2-194">Instellingen voor delen op siteniveau van SharePoint</span><span class="sxs-lookup"><span data-stu-id="8a0c2-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="8a0c2-195">Controleer de instellingen voor delen op siteniveau om er zeker van te zijn dat het type toegang is toegestaan dat u voor dit team wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="8a0c2-196">Als u bijvoorbeeld de instellingen op organisatieniveau in stelt op **Iedereen,** maar u wilt dat alle gasten worden geverifieerd voor dit team, moet u ervoor zorgen dat de instellingen voor delen op siteniveau zijn ingesteld op Nieuwe en bestaande **gasten.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="8a0c2-198">Instellingen voor delen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="8a0c2-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="8a0c2-199">Vouw in het SharePoint-beheercentrum in het linkernavigatiedeelvenster **Sites uit en** klik op Actieve **sites.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="8a0c2-200">Selecteer de site voor het team dat u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="8a0c2-201">Klik op ... en kies **Delen.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="8a0c2-202">Zorg ervoor dat delen is ingesteld **op Iedereen** of Nieuw en **bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="8a0c2-203">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="8a0c2-204">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="8a0c2-204">Invite users</span></span>

<span data-ttu-id="8a0c2-205">Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u kunt beginnen met het toevoegen van interne gebruikers en gasten aan uw team.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="8a0c2-206">Interne gebruikers uitnodigen voor een team</span><span class="sxs-lookup"><span data-stu-id="8a0c2-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="8a0c2-207">Klik in het team op **Meer opties** ( ) en klik vervolgens op **\*\*\*** Lid **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="8a0c2-208">Typ de naam van de persoon die u wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="8a0c2-209">Klik **op** Toevoegen en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="8a0c2-210">Gasten uitnodigen voor een team</span><span class="sxs-lookup"><span data-stu-id="8a0c2-210">To invite guests to a team</span></span>
1. <span data-ttu-id="8a0c2-211">Klik in het team op **Meer opties** ( ) en klik vervolgens op **\*\*\*** Lid **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="8a0c2-212">Typ het e-mailadres van de gast die u wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="8a0c2-213">Klik **op Gastgegevens bewerken.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="8a0c2-214">Typ de volledige naam van de gast en klik op het vinkje.</span><span class="sxs-lookup"><span data-stu-id="8a0c2-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="8a0c2-215">Klik **op** Toevoegen en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="8a0c2-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a0c2-216">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8a0c2-216">See also</span></span>

[<span data-ttu-id="8a0c2-217">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="8a0c2-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="8a0c2-218">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="8a0c2-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="8a0c2-219">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="8a0c2-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="8a0c2-220">Een B2B-extranet maken met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="8a0c2-220">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="8a0c2-221">Integratie van SharePoint en OneDrive met Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="8a0c2-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="8a0c2-222">Opties voor delen worden grijs 2010 wanneer u deelt vanuit SharePoint of OneDrive</span><span class="sxs-lookup"><span data-stu-id="8a0c2-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
