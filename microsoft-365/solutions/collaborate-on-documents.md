---
title: Samenwerken met gasten aan een document
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
description: In dit artikel leert u hoe u kunt samenwerken met gasten aan een document in SharePoint en OneDrive.
ms.openlocfilehash: 1a7591915efa82f1995ce2789e181dc350cd3784
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357780"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="3f6b9-103">Samenwerken met gasten aan een document</span><span class="sxs-lookup"><span data-stu-id="3f6b9-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="3f6b9-104">Als u met personen buiten uw organisatie moet samenwerken aan documenten in SharePoint of OneDrive, kunt u een koppeling voordelen naar het document verzenden.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing link to the document.</span></span> <span data-ttu-id="3f6b9-105">In dit artikel worden 365 de stappen beschreven die u moet uitvoeren om koppelingen voordelen voor SharePoint en OneDrive in te stellen voor de behoeften van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="3f6b9-106">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="3f6b9-106">Video demonstration</span></span>

<span data-ttu-id="3f6b9-107">In deze video ziet u de configuratiestappen die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="3f6b9-108">Instellingen van Azure organisatie relaties</span><span class="sxs-lookup"><span data-stu-id="3f6b9-108">Azure Organizational relationships settings</span></span>

<span data-ttu-id="3f6b9-109">Delen in Microsoft 365 wordt bepaald met het hoogste niveau van de [instellingen voor organisatie relaties in azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="3f6b9-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="3f6b9-110">Als gasten delen is uitgeschakeld of niet beschikbaar is in azure AD, worden de instellingen voordelen die u configureert in Microsoft 365 genegeerd.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-110">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="3f6b9-111">Controleer de instellingen van de organisatie om te controleren of delen met gasten niet is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="3f6b9-113">Instellingen voor organisatie relaties instellen</span><span class="sxs-lookup"><span data-stu-id="3f6b9-113">To set organizational relationship settings</span></span>

1. <span data-ttu-id="3f6b9-114">Meld u aan bij Microsoft Azure at [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="3f6b9-114">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="3f6b9-115">Klik in het linkernavigatievenster op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-115">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="3f6b9-116">Klik in het deelvenster **overzicht** op **organisatie relaties**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-116">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="3f6b9-117">Klik in het deelvenster **relaties organisatie** op **instellingen**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-117">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="3f6b9-118">Zorg ervoor dat **beheerders en gebruikers in de rol gast uitnodiging kunnen uitnodigen** en dat **leden kunnen uitnodigen** zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="3f6b9-119">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="3f6b9-120">Let op de instellingen in de sectie **samenwerkings beperkingen** .</span><span class="sxs-lookup"><span data-stu-id="3f6b9-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="3f6b9-121">Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="3f6b9-122">Als u met gasten in meerdere organisaties werkt, is het raadzaam om de toegang van Directory-gegevens te beperken.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="3f6b9-123">Hiermee kunt u voorkomen dat ze zien welke iemand anders een gast is in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="3f6b9-124">Als u dit wilt doen, selecteert u onder **toegangsbeperkingen**voor gastgebruikers de optie **gastgebruikers beperkte toegang tot eigenschappen en lidmaatschap van adreslijst objecten** of **toegang voor gastgebruikers is beperkt tot eigenschappen en lidmaatschap van eigen directoryobjecten**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="3f6b9-125">Instellingen voordelen van SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="3f6b9-125">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="3f6b9-126">Als u wilt dat personen van buiten uw organisatie toegang hebben tot een document in SharePoint of OneDrive, moeten de instellingen voordelen van SharePoint en OneDrive delen toestaan voordelen met personen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="3f6b9-127">De instellingen op organisatieniveau voor SharePoint bepalen welke instellingen beschikbaar zijn voor afzonderlijke SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-127">The organization-level settings for SharePoint determine what settings are available for individual SharePoint sites.</span></span> <span data-ttu-id="3f6b9-128">Site-instellingen kunnen niet hoger zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="3f6b9-129">Met de instelling op organisatieniveau voor OneDrive wordt bepaald welk niveau van delen beschikbaar is in de OneDrive-bibliotheken van de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-129">The organization-level setting for OneDrive determines what level of sharing is available in users' OneDrive libraries.</span></span>

<span data-ttu-id="3f6b9-130">Voor SharePoint en OneDrive, als u niet-geverifieerde bestanden en mappen wilt delen, kiest u **iedereen**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="3f6b9-131">Als u er zeker van wilt zijn dat mensen van buiten uw organisatie verificatie hebben, kiest u **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="3f6b9-132">*Iedereen* is de eenvoudigste manier om te delen: personen buiten uw organisatie kunnen de koppeling openen zonder verificatie en kunnen deze ook aan anderen doorgeven.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-132">*Anyone* links are the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="3f6b9-133">Voor SharePoint kiest u de meest strikte instelling die moet worden gebruikt door alle sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="3f6b9-135">Instellingen voordelen van SharePoint-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="3f6b9-135">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="3f6b9-136">Klik in het Microsoft 365-Beheercentrum, in het linkernavigatievenster, onder **beheer centra**op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-136">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="3f6b9-137">Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **delen**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-137">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="3f6b9-138">Zorg ervoor dat extern delen voor SharePoint of OneDrive is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="3f6b9-139">(Houd er rekening mee dat de instelling OneDrive niet hoger is dan de instelling van SharePoint).</span><span class="sxs-lookup"><span data-stu-id="3f6b9-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="3f6b9-140">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="3f6b9-141">Standaard koppelingsinstellingen SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="3f6b9-141">SharePoint organization level default link settings</span></span>

<span data-ttu-id="3f6b9-142">De standaardinstellingen voor het koppelen van bestanden en mappen bepalen welke koppelingsoptie standaard voor de gebruiker wordt weergegeven wanneer ze een bestand of map delen.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-142">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="3f6b9-143">Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat u het deelt.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-143">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="3f6b9-144">Houd er rekening mee dat deze instelling van invloed is op SharePoint-sites in uw organisatie en in OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="3f6b9-145">Kies het type koppeling dat standaard wordt geselecteerd wanneer gebruikers bestanden en mappen delen:</span><span class="sxs-lookup"><span data-stu-id="3f6b9-145">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="3f6b9-146">**Iedereen met de koppeling** : Kies deze optie als u verwacht dat u een groot aantal niet-geverifieerde bestanden en mappen wilt delen.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="3f6b9-147">Als u iedereen wilt toestaan die wel of niet is gemachtigd voor het delen van *onbevoegd* delen, kunt u het beste een van de andere opties als standaard instellen.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="3f6b9-148">Dit koppelingstype is alleen beschikbaar als **iedereen** het delen heeft toegestaan.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="3f6b9-149">**Alleen personen in uw organisatie** : Kies deze optie als u verwacht dat u de meeste bestanden en mappen wilt delen met personen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="3f6b9-150">**Specifieke personen** : Houd deze optie ingedrukt als u verwacht dat u een groot aantal bestanden en mappen deelt met gasten.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="3f6b9-151">Dit type koppeling werkt met gasten en vereist ze voor verificatie.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="3f6b9-153">De standaardinstellingen voor de koppeling naar het SharePoint-en OneDrive-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="3f6b9-153">To set the SharePoint and OneDrive organization level default link settings</span></span>

1. <span data-ttu-id="3f6b9-154">Ga naar de pagina delen in het SharePoint-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="3f6b9-155">Selecteer onder **koppelingen voor bestanden en mappen**de standaardkoppeling voordelen die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="3f6b9-156">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-156">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="3f6b9-157">Instellingen voordelen op het SharePoint-siteniveau</span><span class="sxs-lookup"><span data-stu-id="3f6b9-157">SharePoint site level sharing settings</span></span>

<span data-ttu-id="3f6b9-158">Als u bestanden en mappen deelt die zich op een SharePoint-site bevinden, moet u ook de instellingen voordelen op siteniveau voor die site controleren.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-158">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="3f6b9-160">Instellingen voordelen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="3f6b9-160">To set site-level sharing settings</span></span>
1. <span data-ttu-id="3f6b9-161">Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-161">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="3f6b9-162">Selecteer de site die u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-162">Select the site that you just created.</span></span>
3. <span data-ttu-id="3f6b9-163">Klik op het lint op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-163">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="3f6b9-164">Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-164">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="3f6b9-165">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-165">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="3f6b9-166">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="3f6b9-166">Invite users</span></span>

<span data-ttu-id="3f6b9-167">Instellingen voor het delen van inhoud zijn nu geconfigureerd, zodat gebruikers nu bestanden en mappen kunnen delen met personen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-167">Guest sharing settings are now configured, so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="3f6b9-168">Zie [bestanden en mappen in OneDrive delen](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) en [SharePoint-bestanden of-mappen delen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-168">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f6b9-169">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3f6b9-169">See Also</span></span>

[<span data-ttu-id="3f6b9-170">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="3f6b9-170">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="3f6b9-171">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="3f6b9-171">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="3f6b9-172">Integratie van SharePoint en OneDrive met Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="3f6b9-172">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)