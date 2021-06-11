---
title: Samenwerken met gasten aan een document
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
recommendations: false
description: In dit artikel leert u hoe u met gasten kunt samenwerken aan een document in SharePoint en OneDrive.
ms.openlocfilehash: 338c7f32944bccb766ed923c12a9fceee4d81db8
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537833"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="3a145-103">Samenwerken met gasten aan een document</span><span class="sxs-lookup"><span data-stu-id="3a145-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="3a145-104">Als u met personen buiten uw organisatie wilt samenwerken aan documenten in SharePoint of OneDrive, kunt u ze een koppeling voor delen naar het document sturen.</span><span class="sxs-lookup"><span data-stu-id="3a145-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="3a145-105">In dit artikel volgen we de Microsoft 365 configuratiestappen die nodig zijn om koppelingen voor delen in te stellen voor SharePoint en OneDrive voor de behoeften van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3a145-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="3a145-106">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="3a145-106">Video demonstration</span></span>

<span data-ttu-id="3a145-107">In deze video ziet u de configuratiestappen die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="3a145-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="3a145-108">Externe samenwerkingsinstellingen voor Azure</span><span class="sxs-lookup"><span data-stu-id="3a145-108">Azure external collaboration settings</span></span>

<span data-ttu-id="3a145-109">Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de [B2B-instellingen voor externe samenwerking in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="3a145-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="3a145-110">Als gast delen is uitgeschakeld of beperkt in Azure AD, worden met deze instelling alle instellingen voor delen die u configureert in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3a145-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="3a145-111">Controleer de B2B-instellingen voor externe samenwerking om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="3a145-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="3a145-113">Instellingen voor externe samenwerking instellen</span><span class="sxs-lookup"><span data-stu-id="3a145-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="3a145-114">Meld u aan bij Azure Active Directory op [https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="3a145-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="3a145-115">Klik in het linkernavigatiedeelvenster op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="3a145-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="3a145-116">Klik **Externe identiteiten**.</span><span class="sxs-lookup"><span data-stu-id="3a145-116">Click **External identities**.</span></span>
4. <span data-ttu-id="3a145-117">Klik in het linkernavigatiedeelvenster **Aan de slag** op **Instellingen voor externe samenwerking**.</span><span class="sxs-lookup"><span data-stu-id="3a145-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="3a145-118">Zorg ervoor dat **Beheerders en gebruikers in de rol van Afzender van gastuitnodigingen kunnen uitnodigingen verzenden** en **Leden kunnen uitnodigingen verzenden** beide zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3a145-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="3a145-119">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3a145-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="3a145-120">Let op de instellingen in de sectie **Samenwerkingsbeperkingen**.</span><span class="sxs-lookup"><span data-stu-id="3a145-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="3a145-121">Zorg ervoor dat de domeinen van de gasten met wie u wilt samenwerken, niet worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="3a145-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="3a145-122">Als u met gasten van meerdere organisaties werkt, wilt u mogelijk hun toegang tot adreslijstgegevens beperken.</span><span class="sxs-lookup"><span data-stu-id="3a145-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="3a145-123">Hiermee voorkomt u dat ze kunnen zien wie er nog meer een gast is in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="3a145-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="3a145-124">Hiervoor selecteert u onder **Toegangsbeperkingen voor gastgebruikers** de optie **Gastgebruikers hebben beperkte toegang tot eigenschappen en lidmaatschap van instellingen voor adreslijstobjecten** of **Toegang van gastgebruikers is beperkt tot eigenschappen en lidmaatschappen van hun eigen adreslijstobjecten**.</span><span class="sxs-lookup"><span data-stu-id="3a145-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="3a145-125">SharePoint instellingen voor delen op organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="3a145-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="3a145-126">Als u wilt dat personen buiten uw organisatie toegang hebben tot een document in SharePoint of OneDrive, moeten de instellingen voor delen op SharePoint en OneDrive organisatieniveau toestaan dat ze kunnen delen met personen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3a145-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="3a145-127">De instellingen op organisatieniveau voor SharePoint bepalen de instellingen die beschikbaar zijn voor afzonderlijke SharePoint sites.</span><span class="sxs-lookup"><span data-stu-id="3a145-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="3a145-128">Site-instellingen mogen niet meer toestaan dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="3a145-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="3a145-129">De instelling op organisatieniveau voor OneDrive bepaalt het niveau van delen dat beschikbaar is in de bibliotheken OneDrive gebruikers.</span><span class="sxs-lookup"><span data-stu-id="3a145-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="3a145-130">Als SharePoint en OneDrive wilt toestaan dat niet-nautisch bestanden en mappen worden gedeeld, kiest u **Iedereen.**</span><span class="sxs-lookup"><span data-stu-id="3a145-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="3a145-131">Als u ervoor wilt zorgen dat personen buiten uw organisatie zich moeten verifiëren, kiest u **Nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="3a145-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="3a145-132">*Iedereen* met koppelingen is de eenvoudigste manier om te delen: personen buiten uw organisatie kunnen de koppeling zonder verificatie openen en kunnen deze aan anderen doorgeven.</span><span class="sxs-lookup"><span data-stu-id="3a145-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="3a145-133">Kies SharePoint de meest permissieve instelling die nodig is voor elke site in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3a145-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="3a145-135">Instellingen voor delen op organisatieniveau van SharePoint instellen</span><span class="sxs-lookup"><span data-stu-id="3a145-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="3a145-136">In het Microsoft 365-beheercentrum klikt u onder **Beheercentra** op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="3a145-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="3a145-137">Klik in SharePoint beheercentrum in het linkernavigatiedeelvenster onder Beleid **op** **Delen.**</span><span class="sxs-lookup"><span data-stu-id="3a145-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="3a145-138">Zorg ervoor dat extern delen voor SharePoint of OneDrive is ingesteld op **Iedereen** of **Nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="3a145-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="3a145-139">(Houd er rekening mee dat OneDrive instelling niet meer mag zijn dan de instelling SharePoint instelling.)</span><span class="sxs-lookup"><span data-stu-id="3a145-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="3a145-140">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3a145-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="3a145-141">Standaardkoppelingsinstellingen op organisatieniveau van SharePoint</span><span class="sxs-lookup"><span data-stu-id="3a145-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="3a145-142">De standaardkoppelingsinstellingen voor bestanden en mappen bepalen de koppelingsoptie die standaard voor gebruikers wordt weergegeven wanneer ze een bestand of map delen.</span><span class="sxs-lookup"><span data-stu-id="3a145-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="3a145-143">Gebruikers kunnen voor het delen desgewenst het koppelingstype wijzigen in een van de andere opties.</span><span class="sxs-lookup"><span data-stu-id="3a145-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="3a145-144">Houd er rekening mee dat deze instelling van invloed is op SharePoint sites in uw organisatie, evenals OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3a145-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="3a145-145">Kies een koppeling uit een van de volgende typen die vervolgens standaard wordt geselecteerd wanneer gebruikers bestanden en mappen delen:</span><span class="sxs-lookup"><span data-stu-id="3a145-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="3a145-146">**Iedereen met de koppeling:** kies deze optie als u veel niet-genautenteerde bestanden en mappen wilt delen.</span><span class="sxs-lookup"><span data-stu-id="3a145-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="3a145-147">Als u *Iedereen*-koppelingen wilt toestaan, maar u zich zorgen maakt over onbedoeld niet-geverifieerd delen, kunt u een van de andere opties als standaardoptie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3a145-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="3a145-148">Dit koppelingstype is alleen beschikbaar als u **Iedereen** hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="3a145-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="3a145-149">**Alleen personen in uw organisatie**: kies deze optie als u verwacht dat de meeste bestanden en mappen worden gedeeld met personen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3a145-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="3a145-150">**Specifieke personen** - overweeg deze optie als u verwacht veel bestanden en mappen te delen met gasten.</span><span class="sxs-lookup"><span data-stu-id="3a145-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="3a145-151">Dit type koppeling werkt met gasten en vereist verificatie.</span><span class="sxs-lookup"><span data-stu-id="3a145-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="3a145-153">De standaardkoppelingsinstellingen SharePoint en OneDrive op organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="3a145-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="3a145-154">Navigeer naar de pagina Delen in het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="3a145-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="3a145-155">Selecteer onder **Koppelingen naar bestanden en mappen** de standaardkoppeling voor delen die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3a145-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="3a145-156">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3a145-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="3a145-157">Als u de machtiging voor de koppeling voor delen wilt instellen, gaat u naar Kies de machtiging die standaard is **geselecteerd voor koppelingen voor delen.**</span><span class="sxs-lookup"><span data-stu-id="3a145-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="3a145-158">Selecteer **Beeld** als u niet wilt dat niet-nautische gebruikers wijzigingen aanbrengen in de bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="3a145-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="3a145-159">Selecteer **Bewerken** als u niet-nautische gebruikers wilt toestaan wijzigingen aan te brengen in de bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="3a145-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="3a145-160">Houd er rekening mee dat de bovenstaande twee premission-opties niet alleen kunnen worden toegepast voor gasten/externe gebruikers, maar ook voor interne gebruikers.</span><span class="sxs-lookup"><span data-stu-id="3a145-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="3a145-161">De machtigingsoptie die u kiest, wordt bepaald door zelfre discretionaire bevoegdheid.</span><span class="sxs-lookup"><span data-stu-id="3a145-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="3a145-162">Machtigingen instellen voor koppelingen waarmee delen met iedereen kan worden toegestaan</span><span class="sxs-lookup"><span data-stu-id="3a145-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="3a145-163">Onder deze **koppelingen kunnen deze machtigingen worden gegeven:** subdeelvenster,</span><span class="sxs-lookup"><span data-stu-id="3a145-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="3a145-164">In de **vervolgkeuzelijst** Bestanden</span><span class="sxs-lookup"><span data-stu-id="3a145-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="3a145-165">Selecteer **Weergeven en bewerken** als u wilt toestaan dat niet-genautische gebruikers wijzigingen in de bestanden aanbrengen.</span><span class="sxs-lookup"><span data-stu-id="3a145-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="3a145-166">Selecteer **Beeld** als u niet wilt dat niet-genauteerde gebruikers wijzigingen aanbrengen in de bestanden.</span><span class="sxs-lookup"><span data-stu-id="3a145-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="3a145-167">In de **vervolgkeuzelijst** Mappen</span><span class="sxs-lookup"><span data-stu-id="3a145-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="3a145-168">Selecteer **Weergeven, bewerken en uploaden** als u niet-nautische gebruikers wilt toestaan wijzigingen aan te brengen in de mappen.</span><span class="sxs-lookup"><span data-stu-id="3a145-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="3a145-169">Selecteer **Beeld** als u niet wilt dat niet-genauteerde gebruikers wijzigingen aanbrengen in de mappen.</span><span class="sxs-lookup"><span data-stu-id="3a145-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="3a145-170">Instellingen voor het delen op siteniveau in SharePoint</span><span class="sxs-lookup"><span data-stu-id="3a145-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="3a145-171">Als u bestanden en mappen deelt die zich in een SharePoint site, moet u ook de instellingen voor delen op siteniveau voor die site controleren.</span><span class="sxs-lookup"><span data-stu-id="3a145-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="3a145-173">Instellingen voor delen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="3a145-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="3a145-174">Vouw in het SharePoint-beheercentrum **Sites** uit in het navigatievenster aan de linkerkant en klik op **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="3a145-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="3a145-175">Selecteer de site waarop u bestanden en mappen met gasten wilt delen.</span><span class="sxs-lookup"><span data-stu-id="3a145-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="3a145-176">Schuif naar rechts over de rij (waarin de geselecteerde site aanwezig is) en klik ergens in **de kolom Extern** delen.</span><span class="sxs-lookup"><span data-stu-id="3a145-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="3a145-177">Klik op de pagina die wordt weergegeven op **het tabblad** Beleid.</span><span class="sxs-lookup"><span data-stu-id="3a145-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="3a145-178">Klik onder **het deelvenster** Extern delen op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="3a145-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="3a145-179">Zorg ervoor dat delen is ingesteld op **Iedereen** of **Nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="3a145-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="3a145-180">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3a145-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="3a145-181">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="3a145-181">Invite users</span></span>

<span data-ttu-id="3a145-182">Instellingen voor het delen van gasten zijn nu geconfigureerd. zodat gebruikers nu bestanden en mappen kunnen delen met personen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3a145-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="3a145-183">Zie [Bestanden OneDrive en](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) mappen delen en SharePoint of [mappen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) delen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3a145-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a145-184">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3a145-184">See also</span></span>

[<span data-ttu-id="3a145-185">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="3a145-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="3a145-186">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="3a145-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="3a145-187">Integratie van SharePoint en OneDrive met Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="3a145-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)