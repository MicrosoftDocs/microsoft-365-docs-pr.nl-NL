---
title: Samenwerken met gasten in een team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- M365solutions
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over de Microsoft 365-configuratiestappen die nodig zijn om een team in te stellen voor samenwerking met gasten in Teams.
ms.openlocfilehash: dabcfa53e9ccf4b3ea136b5ab522619fe81ae738
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160025"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="7241e-103">Samenwerken met gasten in een team</span><span class="sxs-lookup"><span data-stu-id="7241e-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="7241e-104">Als u met gasten wilt samenwerken in alle documenten, taken en gesprekken, raden we u aan Microsoft Teams te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7241e-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="7241e-105">Teams biedt alle samenwerkingsfuncties die beschikbaar zijn in Office en SharePoint met permanente chat en een aanpasbare en uitbreidbare set samenwerkingstools in een uniforme gebruikerservaring.</span><span class="sxs-lookup"><span data-stu-id="7241e-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="7241e-106">In dit artikel doorlopen we de Microsoft 365-configuratiestappen die nodig zijn om een team in te stellen voor samenwerking met gasten.</span><span class="sxs-lookup"><span data-stu-id="7241e-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="7241e-107">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="7241e-107">Video demonstration</span></span>

<span data-ttu-id="7241e-108">In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="7241e-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="7241e-109">Instellingen voor Azure-organisatierelaties</span><span class="sxs-lookup"><span data-stu-id="7241e-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="7241e-110">Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de instellingen voor organisatierelaties in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7241e-110">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="7241e-111">Als het delen van gasten is uitgeschakeld of beperkt in Azure AD, worden alle instellingen voor delen die u configureert in Microsoft 365 overschreven.</span><span class="sxs-lookup"><span data-stu-id="7241e-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="7241e-112">Controleer de instellingen voor organisatorische relaties om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="7241e-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="7241e-114">Instellingen voor organisatierelaties instellen</span><span class="sxs-lookup"><span data-stu-id="7241e-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="7241e-115">Meld u aan [https://portal.azure.com](https://portal.azure.com)bij Microsoft Azure op .</span><span class="sxs-lookup"><span data-stu-id="7241e-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="7241e-116">Klik in de linkernavigatie op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7241e-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="7241e-117">Klik in het deelvenster **Overzicht** op **Organisatierelaties**.</span><span class="sxs-lookup"><span data-stu-id="7241e-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="7241e-118">Klik in het deelvenster **Organisatierelaties** op **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="7241e-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="7241e-119">Zorg ervoor dat **beheerders en gebruikers in de gastuitnodigingsrol kunnen uitnodigen** en dat leden kunnen **uitnodigen,** beide zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7241e-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="7241e-120">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7241e-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="7241e-121">Let op de instellingen in de sectie **Samenwerkingsbeperkingen.**</span><span class="sxs-lookup"><span data-stu-id="7241e-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="7241e-122">Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="7241e-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="7241e-123">Instellingen voor gasttoegang van Teams</span><span class="sxs-lookup"><span data-stu-id="7241e-123">Teams guest access settings</span></span>

<span data-ttu-id="7241e-124">Teams heeft een master-aan/uit-schakelaar voor gasttoegang en een verscheidenheid aan instellingen beschikbaar om te bepalen wat gasten in een team kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="7241e-124">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="7241e-125">De **hoofdschakelaar, Gasttoegang toestaan in Teams** moet **ingeschakeld** zijn voor gasttoegang om in Teams te werken.</span><span class="sxs-lookup"><span data-stu-id="7241e-125">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="7241e-126">Controleer of de toegang van gasten is ingeschakeld in Teams en breng de gastinstellingen aan op basis van uw bedrijfsbehoeften.</span><span class="sxs-lookup"><span data-stu-id="7241e-126">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="7241e-127">Houd er rekening mee dat deze instellingen van invloed zijn op alle teams.</span><span class="sxs-lookup"><span data-stu-id="7241e-127">Keep in mind that these settings affect all teams.</span></span>

![Schermafbeelding van wisselknop Gasttoegang in Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="7241e-129">Instellingen voor gasttoegang in Teams instellen</span><span class="sxs-lookup"><span data-stu-id="7241e-129">To set Teams guest access settings</span></span>

1. <span data-ttu-id="7241e-130">Meld u aan bij het Microsoft 365-beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7241e-130">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="7241e-131">Klik in het navigatievenster aan de linkerkant op **Alles weergeven**.</span><span class="sxs-lookup"><span data-stu-id="7241e-131">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="7241e-132">Klik onder **Beheercentra** op **Teams**.</span><span class="sxs-lookup"><span data-stu-id="7241e-132">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="7241e-133">Vouw in het Teams-beheercentrum in het linkernavigatievenster **Instellingen voor hele organisatie** uit en klik vervolgens op **Gasttoegang**.</span><span class="sxs-lookup"><span data-stu-id="7241e-133">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="7241e-134">Zorg ervoor dat **Gasttoegang in Teams toestaan** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="7241e-134">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="7241e-135">Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7241e-135">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="7241e-136">Het kan 24 uur duren voordat de instelling voor gasten in Teams actief wordt nadat u deze hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7241e-136">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="7241e-137">Gastinstellingen voor Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="7241e-137">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="7241e-138">Teams gebruikt Microsoft 365-groepen voor teamlidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="7241e-138">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="7241e-139">De gastinstellingen van Microsoft 365 Groups moeten zijn ingeschakeld om gasttoegang in Teams te laten werken.</span><span class="sxs-lookup"><span data-stu-id="7241e-139">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Schermopname van gastinstellingen van Microsoft 365 Groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="7241e-141">Gastinstellingen voor Microsoft 365-groepen instellen</span><span class="sxs-lookup"><span data-stu-id="7241e-141">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="7241e-142">Vouw in het Microsoft 365-beheercentrum in de linkernavigatie **instellingen**uit .</span><span class="sxs-lookup"><span data-stu-id="7241e-142">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="7241e-143">Klik **op Services &-invoegtoepassing .**</span><span class="sxs-lookup"><span data-stu-id="7241e-143">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="7241e-144">Klik in de lijst op **Microsoft 365-groepen**.</span><span class="sxs-lookup"><span data-stu-id="7241e-144">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="7241e-145">Zorg ervoor dat de **groepsleden buiten uw organisatie toegang krijgen tot groepsinhoud** en **groepseigenaren mensen buiten uw organisatie toevoegen aan de** selectievakjes groepen, beide zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7241e-145">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="7241e-146">Als u wijzigingen hebt aangebracht, klikt u op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7241e-146">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="7241e-147">Instellingen voor delen van SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="7241e-147">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="7241e-148">Teams-inhoud zoals bestanden, mappen en lijsten worden allemaal opgeslagen in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7241e-148">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="7241e-149">Om ervoor te zorgen dat gasten toegang hebben tot deze items in Teams, moeten de instellingen voor delen op SharePoint-organisatieniveau het delen met gasten mogelijk maken.</span><span class="sxs-lookup"><span data-stu-id="7241e-149">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="7241e-150">De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites, inclusief sites die zijn gekoppeld aan teams.</span><span class="sxs-lookup"><span data-stu-id="7241e-150">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="7241e-151">Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="7241e-151">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="7241e-152">Als u het delen van bestanden en mappen met niet-geverifieerde personen wilt toestaan, kiest u **Iedereen**.</span><span class="sxs-lookup"><span data-stu-id="7241e-152">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="7241e-153">Als u ervoor wilt zorgen dat alle gasten zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="7241e-153">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="7241e-154">Kies de meest tolerante instelling die nodig is voor elke site in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7241e-154">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="7241e-156">Instellingen voor delen van SharePoint-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="7241e-156">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="7241e-157">Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7241e-157">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="7241e-158">Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="7241e-158">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="7241e-159">Controleer of extern delen voor SharePoint is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="7241e-159">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="7241e-160">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7241e-160">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="7241e-161">Standaardkoppelingsinstellingen op SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="7241e-161">SharePoint organization level default link settings</span></span>

<span data-ttu-id="7241e-162">De standaardinstellingen voor bestands- en mapkoppeling bepalen welke koppelingsoptie standaard aan de gebruiker wordt weergegeven wanneer ze een bestand of map delen.</span><span class="sxs-lookup"><span data-stu-id="7241e-162">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="7241e-163">Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat ze desgewenst delen.</span><span class="sxs-lookup"><span data-stu-id="7241e-163">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="7241e-164">Houd er rekening mee dat deze instelling van invloed is op alle teams en SharePoint-sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7241e-164">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="7241e-165">Kies het type koppeling dat standaard is geselecteerd wanneer gebruikers bestanden en mappen delen:</span><span class="sxs-lookup"><span data-stu-id="7241e-165">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="7241e-166">**Iedereen met de link** - Kies deze optie als u verwacht veel niet-geverifieerde delen van bestanden en mappen te doen.</span><span class="sxs-lookup"><span data-stu-id="7241e-166">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="7241e-167">Als u *koppelingen voor iedereen* wilt toestaan, maar zich zorgen maakt over het per ongeluk niet-verifiëren delen, u een van de andere opties als standaard beschouwen.</span><span class="sxs-lookup"><span data-stu-id="7241e-167">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="7241e-168">Dit koppelingstype is alleen beschikbaar als u **Delen van iedereen** hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7241e-168">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="7241e-169">**Alleen mensen in uw organisatie** - Kies deze optie als u verwacht dat het delen van bestanden en mappen bij mensen binnen uw organisatie is.</span><span class="sxs-lookup"><span data-stu-id="7241e-169">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="7241e-170">**Specifieke personen** - Overweeg deze optie als u verwacht veel bestanden en mappen te delen met gasten.</span><span class="sxs-lookup"><span data-stu-id="7241e-170">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="7241e-171">Dit type koppeling werkt met gasten en vereist dat ze zich verifiëren.</span><span class="sxs-lookup"><span data-stu-id="7241e-171">This type of link works with guests and requires them to authenticate.</span></span>
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="7241e-173">De standaardkoppelingsinstellingen op SharePoint-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="7241e-173">To set the SharePoint organization level default link settings</span></span>

1. <span data-ttu-id="7241e-174">Navigeer naar de pagina Delen in het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="7241e-174">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="7241e-175">Selecteer **onder Koppelingen voor bestand en map**de standaardkoppeling voor delen die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7241e-175">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="7241e-176">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7241e-176">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="7241e-177">Een team maken</span><span class="sxs-lookup"><span data-stu-id="7241e-177">Create a team</span></span>

<span data-ttu-id="7241e-178">De volgende stap is het creëren van het team dat u wilt gebruiken om samen te werken met gasten.</span><span class="sxs-lookup"><span data-stu-id="7241e-178">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="7241e-179">Een team maken</span><span class="sxs-lookup"><span data-stu-id="7241e-179">To create a team</span></span>
1. <span data-ttu-id="7241e-180">Klik in Teams op het tabblad **Teams** op **Deelnemen of maak een team** onder aan het linkerdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="7241e-180">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="7241e-181">Klik **op Een team maken**.</span><span class="sxs-lookup"><span data-stu-id="7241e-181">Click **Create a team**.</span></span>
3. <span data-ttu-id="7241e-182">Klik **op Een team helemaal opnieuw opbouwen**.</span><span class="sxs-lookup"><span data-stu-id="7241e-182">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="7241e-183">Kies **Privé** of **Openbaar**.</span><span class="sxs-lookup"><span data-stu-id="7241e-183">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="7241e-184">Typ een naam en beschrijving voor het team en klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="7241e-184">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="7241e-185">Klik **op Overslaan**.</span><span class="sxs-lookup"><span data-stu-id="7241e-185">Click **Skip**.</span></span>

<span data-ttu-id="7241e-186">We nodigen gebruikers later uit.</span><span class="sxs-lookup"><span data-stu-id="7241e-186">We'll invite users later.</span></span> <span data-ttu-id="7241e-187">Vervolgens is het belangrijk om de instellingen voor het delen op siteniveau voor de SharePoint-site die aan het team is gekoppeld, te controleren.</span><span class="sxs-lookup"><span data-stu-id="7241e-187">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="7241e-188">Instellingen voor delen op SharePoint-siteniveau</span><span class="sxs-lookup"><span data-stu-id="7241e-188">SharePoint site level sharing settings</span></span>

<span data-ttu-id="7241e-189">Controleer de instellingen voor delen op siteniveau om ervoor te zorgen dat deze het gewenste type toegang voor dit team toestaan.</span><span class="sxs-lookup"><span data-stu-id="7241e-189">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="7241e-190">Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **Iedereen,** maar u wilt dat alle gasten zich voor dit team verifiëren, controleert u of de instellingen voor delen op siteniveau zijn ingesteld op **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="7241e-190">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="7241e-192">Instellingen voor delen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="7241e-192">To set site-level sharing settings</span></span>
1. <span data-ttu-id="7241e-193">Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="7241e-193">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="7241e-194">Selecteer de site voor het team dat u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7241e-194">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="7241e-195">Klik op het lint op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="7241e-195">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="7241e-196">Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="7241e-196">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="7241e-197">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7241e-197">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="7241e-198">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="7241e-198">Invite users</span></span>

<span data-ttu-id="7241e-199">Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u beginnen met het toevoegen van interne gebruikers en gasten aan uw team.</span><span class="sxs-lookup"><span data-stu-id="7241e-199">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="7241e-200">Interne gebruikers uitnodigen voor een team</span><span class="sxs-lookup"><span data-stu-id="7241e-200">To invite internal users to a team</span></span>
1. <span data-ttu-id="7241e-201">Klik in het team**\*\*** op **Meer opties** ( ) en klik vervolgens op **Lid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7241e-201">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="7241e-202">Typ de naam van de persoon die u wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="7241e-202">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="7241e-203">Klik **op Toevoegen**en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="7241e-203">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="7241e-204">Gasten uitnodigen voor een team</span><span class="sxs-lookup"><span data-stu-id="7241e-204">To invite guests to a team</span></span>
1. <span data-ttu-id="7241e-205">Klik in het team**\*\*** op **Meer opties** ( ) en klik vervolgens op **Lid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7241e-205">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="7241e-206">Typ het e-mailadres van de gast die u wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="7241e-206">Type the email address of the guest who you want to invite.</span></span>
3. <span data-ttu-id="7241e-207">Klik **op Gastgegevens bewerken**.</span><span class="sxs-lookup"><span data-stu-id="7241e-207">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="7241e-208">Typ de volledige naam van de gast en klik op het vinkje.</span><span class="sxs-lookup"><span data-stu-id="7241e-208">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="7241e-209">Klik **op Toevoegen**en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="7241e-209">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7241e-210">Zie ook</span><span class="sxs-lookup"><span data-stu-id="7241e-210">See Also</span></span>

[<span data-ttu-id="7241e-211">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="7241e-211">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="7241e-212">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="7241e-212">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="7241e-213">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="7241e-213">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="7241e-214">Een B2B-extranet maken met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="7241e-214">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
