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
ms.openlocfilehash: 022811be642a79c07c632cefcc67a27f19e3af4f
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422603"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="b89be-103">Samenwerken met gasten aan een document</span><span class="sxs-lookup"><span data-stu-id="b89be-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="b89be-104">Als u met personen buiten uw organisatie moet samenwerken aan documenten in SharePoint of OneDrive, kunt u een koppeling naar het document verzenden.</span><span class="sxs-lookup"><span data-stu-id="b89be-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="b89be-105">In dit artikel worden de stappen beschreven die u moet uitvoeren om delen van SharePoint en OneDrive in te stellen voor de behoeften van uw organisatie in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b89be-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="b89be-106">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="b89be-106">Video demonstration</span></span>

<span data-ttu-id="b89be-107">In deze video ziet u de configuratiestappen die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="b89be-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="b89be-108">Instellingen van Azure organisatie relaties</span><span class="sxs-lookup"><span data-stu-id="b89be-108">Azure organizational relationships settings</span></span>

<span data-ttu-id="b89be-109">Delen in Microsoft 365 wordt bepaald met het hoogste niveau van de [instellingen voor organisatie relaties in azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="b89be-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="b89be-110">Als gasten delen is uitgeschakeld of niet beschikbaar is in azure AD, worden de instellingen voordelen overschreven die u configureert in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b89be-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="b89be-111">Controleer de instellingen van de organisatie om te controleren of delen met gasten niet is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="b89be-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="b89be-113">Instellingen voor organisatie relaties instellen</span><span class="sxs-lookup"><span data-stu-id="b89be-113">To set organizational relationship settings</span></span>

<span data-ttu-id="b89be-114">Externe samenwerkings instellingen instellen</span><span class="sxs-lookup"><span data-stu-id="b89be-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="b89be-115">Meld u aan bij Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="b89be-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="b89be-116">Klik in het linker navigatiedeelvenster op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b89be-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="b89be-117">Klik op **externe identiteiten**.</span><span class="sxs-lookup"><span data-stu-id="b89be-117">Click **External identities**.</span></span>
4. <span data-ttu-id="b89be-118">Klik in het scherm aan de **slag** in het linker navigatiedeelvenster op **instellingen voor externe samenwerking**.</span><span class="sxs-lookup"><span data-stu-id="b89be-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="b89be-119">Zorg ervoor dat **beheerders en gebruikers in de rol gast uitnodiging kunnen uitnodigen** en dat **leden kunnen uitnodigen** zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b89be-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="b89be-120">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b89be-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="b89be-121">Let op de instellingen in de sectie **samenwerkings beperkingen** .</span><span class="sxs-lookup"><span data-stu-id="b89be-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="b89be-122">Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="b89be-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="b89be-123">Als u met gasten in meerdere organisaties werkt, is het raadzaam om de toegang van Directory-gegevens te beperken.</span><span class="sxs-lookup"><span data-stu-id="b89be-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="b89be-124">Hiermee kunt u voorkomen dat ze zien welke iemand anders een gast is in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="b89be-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="b89be-125">Als u dit wilt doen, selecteert u onder **toegangsbeperkingen**voor gastgebruikers de optie **gastgebruikers beperkte toegang tot eigenschappen en lidmaatschap van adreslijst objecten** of **toegang voor gastgebruikers is beperkt tot eigenschappen en lidmaatschap van eigen directoryobjecten**.</span><span class="sxs-lookup"><span data-stu-id="b89be-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="b89be-126">Instellingen voordelen op SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="b89be-126">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="b89be-127">Als u wilt dat personen van buiten uw organisatie toegang hebben tot een document in SharePoint of OneDrive, moeten de instellingen voordelen van SharePoint en OneDrive delen toestaan voordelen met personen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b89be-127">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="b89be-128">De instellingen op organisatieniveau voor SharePoint bepalen de instellingen die beschikbaar zijn voor afzonderlijke SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="b89be-128">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="b89be-129">Site-instellingen kunnen niet hoger zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="b89be-129">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="b89be-130">Met de instelling op organisatieniveau voor OneDrive bepaalt u het niveau van delen dat beschikbaar is in de OneDrive-bibliotheken van de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b89be-130">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="b89be-131">Voor SharePoint en OneDrive, als u niet-geverifieerde bestanden en mappen wilt delen, kiest u **iedereen**.</span><span class="sxs-lookup"><span data-stu-id="b89be-131">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="b89be-132">Als u er zeker van wilt zijn dat mensen van buiten uw organisatie verificatie hebben, kiest u **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="b89be-132">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="b89be-133">*Iedereen* is de eenvoudigste manier om te delen: personen buiten uw organisatie kunnen de koppeling openen zonder verificatie en kunnen ze ook aan anderen doorgeven.</span><span class="sxs-lookup"><span data-stu-id="b89be-133">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="b89be-134">Voor SharePoint kiest u de meest strikte instelling die moet worden gebruikt door alle sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b89be-134">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="b89be-136">Instellingen voordelen van SharePoint op organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="b89be-136">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="b89be-137">Klik in het Microsoft 365-Beheercentrum, in het linker navigatiedeelvenster, onder **beheer centra**op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b89be-137">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="b89be-138">Klik in het SharePoint-Beheercentrum, in het linker navigatiedeelvenster, onder **beleid**, op **delen**.</span><span class="sxs-lookup"><span data-stu-id="b89be-138">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="b89be-139">Zorg ervoor dat extern delen voor SharePoint of OneDrive is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="b89be-139">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="b89be-140">(Houd er rekening mee dat de instelling OneDrive niet hoger is dan de instelling van SharePoint).</span><span class="sxs-lookup"><span data-stu-id="b89be-140">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="b89be-141">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b89be-141">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="b89be-142">Standaard koppelingsinstellingen op SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="b89be-142">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="b89be-143">De standaardinstellingen voor het koppelen van bestanden en mappen bepalen de koppelingsoptie die standaard wordt getoond aan gebruikers wanneer ze een bestand of map delen.</span><span class="sxs-lookup"><span data-stu-id="b89be-143">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="b89be-144">Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat u het deelt.</span><span class="sxs-lookup"><span data-stu-id="b89be-144">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="b89be-145">Houd er rekening mee dat deze instelling van invloed is op SharePoint-sites in uw organisatie en in OneDrive.</span><span class="sxs-lookup"><span data-stu-id="b89be-145">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="b89be-146">Kies een koppeling uit een van de volgende typen die standaard wordt geselecteerd wanneer gebruikers bestanden en mappen delen:</span><span class="sxs-lookup"><span data-stu-id="b89be-146">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="b89be-147">**Iedereen met de koppeling** : Kies deze optie als u verwacht dat u een groot aantal niet-geverifieerde bestanden en mappen wilt delen.</span><span class="sxs-lookup"><span data-stu-id="b89be-147">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="b89be-148">Als u iedereen wilt toestaan die wel of niet is gemachtigd voor het delen van *onbevoegd* delen, kunt u het beste een van de andere opties als standaard instellen.</span><span class="sxs-lookup"><span data-stu-id="b89be-148">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="b89be-149">Dit koppelingstype is alleen beschikbaar als **iedereen** het delen heeft toegestaan.</span><span class="sxs-lookup"><span data-stu-id="b89be-149">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="b89be-150">**Alleen personen in uw organisatie** : Kies deze optie als u verwacht dat u de meeste bestanden en mappen wilt delen met personen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b89be-150">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="b89be-151">**Specifieke personen** : Houd deze optie ingedrukt als u verwacht dat u een groot aantal bestanden en mappen deelt met gasten.</span><span class="sxs-lookup"><span data-stu-id="b89be-151">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="b89be-152">Dit type koppeling werkt met gasten en vereist ze voor verificatie.</span><span class="sxs-lookup"><span data-stu-id="b89be-152">This type of link works with guests and requires them to authenticate.</span></span>
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="b89be-154">De instellingen voor de standaardkoppeling van SharePoint en OneDrive instellen op organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="b89be-154">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="b89be-155">Ga naar de pagina delen in het SharePoint-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b89be-155">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="b89be-156">Selecteer onder **koppelingen voor bestanden en mappen**de standaardkoppeling voordelen die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b89be-156">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="b89be-157">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b89be-157">If you made changes, click **Save**.</span></span>

<span data-ttu-id="b89be-158">Als u de machtiging voor de koppeling voordelen wilt instellen, klikt u onder **Kies de machtiging die standaard wordt geselecteerd voor koppelingen voordelen.**</span><span class="sxs-lookup"><span data-stu-id="b89be-158">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="b89be-159">Selecteer **weergeven** als u niet wilt dat niet-geverifieerde gebruikers wijzigingen aanbrengen in de bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="b89be-159">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="b89be-160">Selecteer **bewerken** als u wilt dat niet-geverifieerde gebruikers wijzigingen kunnen aanbrengen in de bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="b89be-160">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="b89be-161">Houd er rekening mee dat de twee bemissieings opties niet alleen voor gasten en externe gebruikers maar ook voor interne gebruikers kunnen worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="b89be-161">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="b89be-162">De optie voor de machtiging die u kiest, wordt bepaald door de eigen goeddunken.</span><span class="sxs-lookup"><span data-stu-id="b89be-162">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="b89be-163">Machtigingen instellen voor koppelingen waarmee u met iedereen kunt delen</span><span class="sxs-lookup"><span data-stu-id="b89be-163">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="b89be-164">In het deelvenster **deze koppelingen kunnen deze machtigingen geven:** subvenster</span><span class="sxs-lookup"><span data-stu-id="b89be-164">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="b89be-165">In de vervolgkeuzelijst **bestanden** ,</span><span class="sxs-lookup"><span data-stu-id="b89be-165">From the **Files** drop-down list,</span></span> 
        1. <span data-ttu-id="b89be-166">Selecteer **weergeven en bewerken** als u niet-geverifieerde gebruikers wilt toestaan om wijzigingen aan te brengen in de bestanden.</span><span class="sxs-lookup"><span data-stu-id="b89be-166">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        2. <span data-ttu-id="b89be-167">Selecteer **weergeven** als u niet wilt dat niet-geverifieerde gebruikers wijzigingen in de bestanden aanbrengen.</span><span class="sxs-lookup"><span data-stu-id="b89be-167">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="b89be-168">In de vervolgkeuzelijst **mappen** ,</span><span class="sxs-lookup"><span data-stu-id="b89be-168">From the **Folders** drop-down list,</span></span>
        1. <span data-ttu-id="b89be-169">Selecteer **weergeven, bewerken en uploaden** als u niet-geverifieerde gebruikers wilt toestaan om wijzigingen aan te brengen in de mappen.</span><span class="sxs-lookup"><span data-stu-id="b89be-169">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        2. <span data-ttu-id="b89be-170">Selecteer **weergeven** als u niet wilt dat niet-geverifieerde gebruikers wijzigingen in de mappen aanbrengen.</span><span class="sxs-lookup"><span data-stu-id="b89be-170">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="b89be-171">Instellingen voordelen op SharePoint-siteniveau</span><span class="sxs-lookup"><span data-stu-id="b89be-171">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="b89be-172">Als u bestanden en mappen deelt die zich op een SharePoint-site bevinden, moet u ook de instellingen voordelen op siteniveau voor die site controleren.</span><span class="sxs-lookup"><span data-stu-id="b89be-172">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="b89be-174">Instellingen voordelen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="b89be-174">To set site-level sharing settings</span></span>

1. <span data-ttu-id="b89be-175">Vouw in het SharePoint-Beheercentrum in het linker navigatievenster **sites** uit en klik op **actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="b89be-175">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="b89be-176">Selecteer de site waarop u bestanden en mappen wilt delen met gasten.</span><span class="sxs-lookup"><span data-stu-id="b89be-176">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="b89be-177">Schuif naar rechts om de rij (waarin de geselecteerde site wordt weergegeven) en klik op een willekeurige plaats in de kolom **extern delen** .</span><span class="sxs-lookup"><span data-stu-id="b89be-177">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="b89be-178">Op de pagina die verschijnt, klikt u op het tabblad **beleidsregels** .</span><span class="sxs-lookup"><span data-stu-id="b89be-178">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="b89be-179">Klik onder het deelvenster **extern delen** op **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="b89be-179">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="b89be-180">Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="b89be-180">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="b89be-181">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b89be-181">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="b89be-182">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="b89be-182">Invite users</span></span>

<span data-ttu-id="b89be-183">Instellingen voor het delen van gasten zijn nu geconfigureerd; gebruikers kunnen nu bestanden en mappen delen met personen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b89be-183">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="b89be-184">Zie [bestanden en mappen in OneDrive delen](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) en [SharePoint-bestanden of-mappen delen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b89be-184">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="b89be-185">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b89be-185">See also</span></span>

[<span data-ttu-id="b89be-186">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="b89be-186">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="b89be-187">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="b89be-187">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="b89be-188">Integratie van SharePoint en OneDrive met Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="b89be-188">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
