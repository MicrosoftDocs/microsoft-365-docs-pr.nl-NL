---
title: Samenwerken met gasten in een team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over hoe u samenwerken met gasten in Teams.
ms.openlocfilehash: 54bf52eebc77e1cce8e1c05a708572d7d1e7fdae
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2020
ms.locfileid: "42806265"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="94249-103">Samenwerken met gasten in een team</span><span class="sxs-lookup"><span data-stu-id="94249-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="94249-104">Als u met gasten wilt samenwerken in documenten, taken en gesprekken, raden we u aan Microsoft Teams te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="94249-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="94249-105">Teams biedt alle samenwerkingsfuncties die beschikbaar zijn in Office en SharePoint met permanente chat en een aanpasbare en uitbreidbare set samenwerkingstools in een uniforme gebruikerservaring.</span><span class="sxs-lookup"><span data-stu-id="94249-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="94249-106">In dit artikel doorlopen we de Microsoft 365-configuratiestappen die nodig zijn om een team op te zetten voor samenwerking met gasten.</span><span class="sxs-lookup"><span data-stu-id="94249-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="94249-107">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="94249-107">Video demonstration</span></span>

<span data-ttu-id="94249-108">In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="94249-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="94249-109">Instellingen voor Azure Organizational Relationships</span><span class="sxs-lookup"><span data-stu-id="94249-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="94249-110">Delen in Microsoft 365 wordt op het hoogste niveau geregeld door de instellingen voor organisatierelaties in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="94249-110">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="94249-111">Als het delen van gasten is uitgeschakeld of beperkt in Azure AD, worden alle instellingen voor delen die u configureert in Microsoft 365, overschreven.</span><span class="sxs-lookup"><span data-stu-id="94249-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="94249-112">Controleer de instellingen voor organisatierelaties om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="94249-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de pagina Instellingen voor Azure Active Directory-organisatierelaties](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="94249-114">Instellingen voor organisatierelatie instellen</span><span class="sxs-lookup"><span data-stu-id="94249-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="94249-115">Log in bij [https://portal.azure.com](https://portal.azure.com)Microsoft Azure bij .</span><span class="sxs-lookup"><span data-stu-id="94249-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="94249-116">Klik in de linkernavigatie op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="94249-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="94249-117">Klik in het deelvenster **Overzicht** op **Organisatierelaties**.</span><span class="sxs-lookup"><span data-stu-id="94249-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="94249-118">Klik in het deelvenster **Organisatierelaties** op **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="94249-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="94249-119">Zorg ervoor dat **beheerders en gebruikers in de rol gastgenodigden kunnen uitnodigen** en leden kunnen **uitnodigen,** zijn beide ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="94249-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="94249-120">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="94249-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="94249-121">Let op de instellingen in de sectie **Beperkingen voor samenwerking.**</span><span class="sxs-lookup"><span data-stu-id="94249-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="94249-122">Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken niet worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="94249-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="94249-123">Instellingen voor gasttoegang teams</span><span class="sxs-lookup"><span data-stu-id="94249-123">Teams guest access settings</span></span>

<span data-ttu-id="94249-124">Teams heeft een master aan/uit-schakelaar voor gasttoegang en een verscheidenheid aan instellingen beschikbaar om te bepalen wat gasten in een team kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="94249-124">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="94249-125">De master switch, **Toestaan dat gasttoegang in Teams** moet **ingeschakeld** zijn voor gasttoegang tot het werk in Teams.</span><span class="sxs-lookup"><span data-stu-id="94249-125">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="94249-126">Controleer of de toegang tot gasten is ingeschakeld in Teams en elke aanpassing aan de gastinstellingen aan te passen op basis van uw zakelijke behoeften.</span><span class="sxs-lookup"><span data-stu-id="94249-126">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="94249-127">Houd er rekening mee dat deze instellingen van invloed zijn op alle teams.</span><span class="sxs-lookup"><span data-stu-id="94249-127">Keep in mind that these settings affect all teams.</span></span>

![Schermafbeelding van de toegang tot Teams-gasten om te schakelen](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="94249-129">Instellingen voor gasttoegang van Teams instellen</span><span class="sxs-lookup"><span data-stu-id="94249-129">To set Teams guest access settings</span></span>

1. <span data-ttu-id="94249-130">Log in bij het Microsoft 365-beheercentrum bij [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="94249-130">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="94249-131">Klik in de linkernavigatie op **Alles weergeven**.</span><span class="sxs-lookup"><span data-stu-id="94249-131">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="94249-132">Klik onder **Beheercentra**op **Teams**.</span><span class="sxs-lookup"><span data-stu-id="94249-132">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="94249-133">Vouw in het beheercentrum Teams in de linkernavigatie **organigrambrede instellingen** uit en klik op **Gasttoegang.**</span><span class="sxs-lookup"><span data-stu-id="94249-133">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="94249-134">Zorg ervoor dat **gasttoegang toestaan in Teams** is ingesteld op **Aan.**</span><span class="sxs-lookup"><span data-stu-id="94249-134">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="94249-135">Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="94249-135">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="94249-136">Het kan tot vierentwintig uur duren voordat de teams-gastinstelling actief zijn nadat u de instelling hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="94249-136">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

## <a name="office-365-groups-guest-settings"></a><span data-ttu-id="94249-137">Gastinstellingen voor Office 365-groepen</span><span class="sxs-lookup"><span data-stu-id="94249-137">Office 365 Groups guest settings</span></span>

<span data-ttu-id="94249-138">Teams gebruiken Office 365-groepen voor het lidmaatschap van het team.</span><span class="sxs-lookup"><span data-stu-id="94249-138">Teams uses Office 365 Groups for team membership.</span></span> <span data-ttu-id="94249-139">De gastinstellingen voor Office 365-groepen moeten zijn ingeschakeld om gasttoegang in Teams te laten werken.</span><span class="sxs-lookup"><span data-stu-id="94249-139">The Office 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Schermafbeelding van gastinstellingen voor Office 365-groepen in het Microsoft 365-beheercentrum](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="94249-141">Gastinstellingen voor Office 365-groepen instellen</span><span class="sxs-lookup"><span data-stu-id="94249-141">To set Office 365 Groups guest settings</span></span>

1. <span data-ttu-id="94249-142">Vouw instellingen in het Microsoft 365-beheercentrum in de linkernavigatie **uit**.</span><span class="sxs-lookup"><span data-stu-id="94249-142">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="94249-143">Klik op **Services & invoegins**.</span><span class="sxs-lookup"><span data-stu-id="94249-143">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="94249-144">Klik in de lijst op **Office 365-groepen**.</span><span class="sxs-lookup"><span data-stu-id="94249-144">In the list, click **Office 365 Groups**.</span></span>
4. <span data-ttu-id="94249-145">Zorg ervoor dat de **groepsleden buiten de groepsinhoud van uw organisatie toegang hebben tot groepsinhoud** en **dat groepseigenaren mensen buiten uw organisatie aan groepen** laten toevoegen, beide worden gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="94249-145">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="94249-146">Als u wijzigingen hebt aangebracht, klikt u op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="94249-146">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="94249-147">Instellingen voor delen op sharepoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="94249-147">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="94249-148">Teams-inhoud zoals bestanden, mappen en lijsten worden allemaal opgeslagen in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="94249-148">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="94249-149">Om gasten toegang te geven tot deze items in Teams, moeten de instellingen voor delen op organisatieniveau het delen met gasten mogelijk maken.</span><span class="sxs-lookup"><span data-stu-id="94249-149">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="94249-150">De instellingen op organisatieniveau bepalen welke instellingen beschikbaar zijn voor afzonderlijke sites, inclusief sites die zijn gekoppeld aan teams.</span><span class="sxs-lookup"><span data-stu-id="94249-150">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="94249-151">Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="94249-151">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="94249-152">Als u het delen van bestanden en mappen met niet-geverifieerde personen wilt toestaan, kiest u **Iedereen**.</span><span class="sxs-lookup"><span data-stu-id="94249-152">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="94249-153">Als u ervoor wilt zorgen dat alle gasten zich moeten authenticeren, kiest u **Nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="94249-153">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="94249-154">Kies de meest tolerante instelling die nodig is voor elke site in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="94249-154">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van instellingen voor delen op sharepoint-organisatieniveau](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="94249-156">Instellingen voor delen op sharepoint-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="94249-156">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="94249-157">Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="94249-157">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="94249-158">Klik in het SharePoint-beheercentrum in de linkernavigatie op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="94249-158">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="94249-159">Zorg ervoor dat extern delen voor SharePoint is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="94249-159">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="94249-160">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="94249-160">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="94249-161">Standaardkoppelingsinstellingen voor SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="94249-161">SharePoint organization level default link settings</span></span>

<span data-ttu-id="94249-162">De instellingen voor standaardbestands- en mapkoppelingen bepalen welke koppelingsoptie standaard aan de gebruiker wordt weergegeven wanneer deze een bestand of map deelt.</span><span class="sxs-lookup"><span data-stu-id="94249-162">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="94249-163">Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat ze desgewenst delen.</span><span class="sxs-lookup"><span data-stu-id="94249-163">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="94249-164">Houd er rekening mee dat deze instelling van invloed is op alle teams en SharePoint-sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="94249-164">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="94249-165">Kies het type koppeling dat standaard is geselecteerd wanneer gebruikers bestanden en mappen delen:</span><span class="sxs-lookup"><span data-stu-id="94249-165">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="94249-166">**Iedereen met de link** - Kies deze optie als je verwacht dat je veel niet-geverifieerde delen van bestanden en mappen zult doen.</span><span class="sxs-lookup"><span data-stu-id="94249-166">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="94249-167">Als u *Koppelingen* wilt toestaan, maar zich zorgen maakt over het per ongeluk niet-geverifieerde delen, beschouw dan een van de andere opties als standaard.</span><span class="sxs-lookup"><span data-stu-id="94249-167">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="94249-168">Dit koppelingstype is alleen beschikbaar als u iedereen hebt ingeschakeld om **te** delen.</span><span class="sxs-lookup"><span data-stu-id="94249-168">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="94249-169">**Alleen mensen in uw organisatie** - Kies deze optie als u verwacht dat het delen van bestanden en mappen het meest met mensen binnen uw organisatie is.</span><span class="sxs-lookup"><span data-stu-id="94249-169">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="94249-170">**Specifieke mensen** - Overweeg deze optie als u verwacht veel bestanden en mappen te delen met gasten.</span><span class="sxs-lookup"><span data-stu-id="94249-170">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="94249-171">Dit type koppeling werkt samen met gasten en vereist dat ze zich verifiëren.</span><span class="sxs-lookup"><span data-stu-id="94249-171">This type of link works with guests and requires them to authenticate.</span></span>
 
![Schermafbeelding van instellingen voor delen op organisatieniveau](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="94249-173">Standaardkoppelingsinstellingen voor SharePoint-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="94249-173">To set the SharePoint organization level default link settings</span></span>

1. <span data-ttu-id="94249-174">Navigeer naar de pagina Delen in het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="94249-174">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="94249-175">Selecteer onder **Bestands- en mapkoppelingen**de standaardkoppeling voor delen die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="94249-175">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="94249-176">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="94249-176">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="94249-177">Een team maken</span><span class="sxs-lookup"><span data-stu-id="94249-177">Create a team</span></span>

<span data-ttu-id="94249-178">De volgende stap is het maken van het team dat u wilt gebruiken om samen te werken met gasten.</span><span class="sxs-lookup"><span data-stu-id="94249-178">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="94249-179">Een team maken</span><span class="sxs-lookup"><span data-stu-id="94249-179">To create a team</span></span>
1. <span data-ttu-id="94249-180">Klik in Teams op het tabblad **Teams** op **Deelnemen of maak een team** onder aan het linkerdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="94249-180">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="94249-181">Klik op **Een team maken**.</span><span class="sxs-lookup"><span data-stu-id="94249-181">Click **Create a team**.</span></span>
3. <span data-ttu-id="94249-182">Klik **op Een team helemaal opnieuw samenstellen.**</span><span class="sxs-lookup"><span data-stu-id="94249-182">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="94249-183">Kies **Privé** of **Openbaar**.</span><span class="sxs-lookup"><span data-stu-id="94249-183">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="94249-184">Typ een naam en beschrijving voor het team en klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="94249-184">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="94249-185">Klik op **Overslaan**.</span><span class="sxs-lookup"><span data-stu-id="94249-185">Click **Skip**.</span></span>

<span data-ttu-id="94249-186">We nodigen gebruikers later uit.</span><span class="sxs-lookup"><span data-stu-id="94249-186">We'll invite users later.</span></span> <span data-ttu-id="94249-187">Vervolgens is het belangrijk om de instellingen voor delen op siteniveau te controleren voor de SharePoint-site die aan het team is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="94249-187">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="94249-188">Instellingen voor delen op sharepoint-siteniveau</span><span class="sxs-lookup"><span data-stu-id="94249-188">SharePoint site level sharing settings</span></span>

<span data-ttu-id="94249-189">Controleer de instellingen voor delen op siteniveau om ervoor te zorgen dat ze het gewenste type toegang voor dit team toestaan.</span><span class="sxs-lookup"><span data-stu-id="94249-189">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="94249-190">Als u bijvoorbeeld de instellingen op organisatieniveau instelt op **Iedereen,** maar u wilt dat alle gasten zich voor dit team verifiëren, controleert u of de instellingen voor delen op siteniveau zijn ingesteld op **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="94249-190">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Schermafbeelding van instellingen voor extern delen van de SharePoint-site](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="94249-192">Instellingen voor delen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="94249-192">To set site-level sharing settings</span></span>
1. <span data-ttu-id="94249-193">Vouw **sites** in het SharePoint-beheercentrum uit en klik op **Actieve sites**in het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="94249-193">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="94249-194">Selecteer de site voor het team dat u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="94249-194">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="94249-195">Klik op het lint op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="94249-195">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="94249-196">Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="94249-196">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="94249-197">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="94249-197">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="94249-198">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="94249-198">Invite users</span></span>

<span data-ttu-id="94249-199">Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat u interne gebruikers en gasten toevoegen aan uw team.</span><span class="sxs-lookup"><span data-stu-id="94249-199">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="94249-200">Interne gebruikers uitnodigen voor een team</span><span class="sxs-lookup"><span data-stu-id="94249-200">To invite internal users to a team</span></span>
1. <span data-ttu-id="94249-201">Klik in het team**\*\*** op **Meer opties** ( ) en klik vervolgens op **Lid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="94249-201">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="94249-202">Typ de naam van de persoon die u wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="94249-202">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="94249-203">Klik op **Toevoegen**en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="94249-203">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="94249-204">Gasten uitnodigen voor een team</span><span class="sxs-lookup"><span data-stu-id="94249-204">To invite guests to a team</span></span>
1. <span data-ttu-id="94249-205">Klik in het team**\*\*** op **Meer opties** ( ) en klik vervolgens op **Lid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="94249-205">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="94249-206">Typ het e-mailadres van de gast die u wilt uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="94249-206">Type the email address of the guest who you want to invite.</span></span>
3. <span data-ttu-id="94249-207">Klik **op Gastgegevens bewerken**.</span><span class="sxs-lookup"><span data-stu-id="94249-207">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="94249-208">Typ de volledige naam van de gast en klik op het vinkje.</span><span class="sxs-lookup"><span data-stu-id="94249-208">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="94249-209">Klik op **Toevoegen**en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="94249-209">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="94249-210">Zie ook</span><span class="sxs-lookup"><span data-stu-id="94249-210">See Also</span></span>

[<span data-ttu-id="94249-211">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="94249-211">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="94249-212">Onbedoelde blootstelling aan bestanden beperken wanneer u deelt met gasten</span><span class="sxs-lookup"><span data-stu-id="94249-212">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="94249-213">Een veilige omgeving voor het delen van gasten creëren</span><span class="sxs-lookup"><span data-stu-id="94249-213">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="94249-214">Maak een B2B extranet met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="94249-214">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
