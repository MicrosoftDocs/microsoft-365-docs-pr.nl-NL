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
description: In dit artikel leert u hoe u samenwerken met gasten aan een document in SharePoint en OneDrive.
ms.openlocfilehash: cb3c527304f0d286b4a1a0147d07537b0fae4eda
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527916"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="b6e5d-103">Samenwerken met gasten aan een document</span><span class="sxs-lookup"><span data-stu-id="b6e5d-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="b6e5d-104">Als u met mensen buiten uw organisatie moet samenwerken aan documenten in SharePoint of OneDrive, u ze een koppeling voor delen naar het document sturen.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing link to the document.</span></span> <span data-ttu-id="b6e5d-105">In dit artikel doorlopen we de microsoft 365-configuratiestappen die nodig zijn om koppelingen voor delen voor SharePoint en OneDrive in te stellen voor de behoeften van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="b6e5d-106">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="b6e5d-106">Video demonstration</span></span>

<span data-ttu-id="b6e5d-107">In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="b6e5d-108">Azure-instellingen voor organisatierelaties</span><span class="sxs-lookup"><span data-stu-id="b6e5d-108">Azure Organizational relationships settings</span></span>

<span data-ttu-id="b6e5d-109">Delen in Microsoft 365 wordt op het hoogste niveau bepaald door de instellingen voor organisatierelaties in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-109">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="b6e5d-110">Als het delen van gasten is uitgeschakeld of beperkt in Azure AD, worden alle instellingen voor delen die u in Microsoft 365 configureert, overschrijven.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-110">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="b6e5d-111">Controleer de instellingen voor organisatorische relaties om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de instellingenpagina voor organisatierelaties in Microsoft Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="b6e5d-113">Instellingen voor organisatierelaties instellen</span><span class="sxs-lookup"><span data-stu-id="b6e5d-113">To set organizational relationship settings</span></span>

1. <span data-ttu-id="b6e5d-114">Log in bij Microsoft Azure op [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="b6e5d-114">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="b6e5d-115">Klik in de linkernavigatie op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-115">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="b6e5d-116">Klik **in het** deelvenster Overzicht op **Organisatierelaties**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-116">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="b6e5d-117">Klik in het deelvenster **Organisatierelaties** op **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-117">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="b6e5d-118">Zorg ervoor dat **beheerders en gebruikers in de rol van gastuitnodiger kunnen worden uitgenodigd** en dat leden kunnen **uitnodigen,** zijn beide ingesteld op **Ja.**</span><span class="sxs-lookup"><span data-stu-id="b6e5d-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="b6e5d-119">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="b6e5d-120">Let op de instellingen in de sectie **Samenwerkingsbeperkingen.**</span><span class="sxs-lookup"><span data-stu-id="b6e5d-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="b6e5d-121">Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken, niet worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="b6e5d-122">Instellingen voor delen op niveau van SharePoint-organisatie</span><span class="sxs-lookup"><span data-stu-id="b6e5d-122">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="b6e5d-123">Als u ervoor wilt dat mensen buiten uw organisatie toegang hebben tot een document in SharePoint of OneDrive, moeten de instellingen voor delen op organisatieniveau in SharePoint en OneDrive toestaan om te delen met mensen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-123">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="b6e5d-124">De instellingen op organisatieniveau voor SharePoint bepalen welke instellingen beschikbaar zijn voor afzonderlijke SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-124">The organization-level settings for SharePoint determine what settings are available for individual SharePoint sites.</span></span> <span data-ttu-id="b6e5d-125">Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-125">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="b6e5d-126">De instelling op organisatieniveau voor OneDrive bepaalt welk niveau van delen beschikbaar is in de OneDrive-bibliotheken van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-126">The organization-level setting for OneDrive determines what level of sharing is available in users' OneDrive libraries.</span></span>

<span data-ttu-id="b6e5d-127">Als u voor SharePoint en OneDrive het delen van niet-geverifieerde bestanden en mappen wilt toestaan, kiest **u Iedereen**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-127">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="b6e5d-128">Als u ervoor wilt zorgen dat mensen buiten uw organisatie zich moeten authenticeren, kiest u **Nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="b6e5d-128">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="b6e5d-129">*Iedereen* links zijn de makkelijkste manier om te delen: mensen buiten uw organisatie kunnen de link openen zonder authenticatie en zijn vrij om het door te geven aan anderen.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-129">*Anyone* links are the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="b6e5d-130">Kies voor SharePoint de meest tolerante instelling die nodig is voor elke site in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-130">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van de instellingen voor delen op organisatieniveau van SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="b6e5d-132">Instellingen voor delen op niveau van SharePoint instellen</span><span class="sxs-lookup"><span data-stu-id="b6e5d-132">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="b6e5d-133">Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-133">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="b6e5d-134">Klik in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant op **delen**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-134">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="b6e5d-135">Controleer of extern delen voor SharePoint of OneDrive is ingesteld op **Iedereen** of **Nieuw en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-135">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="b6e5d-136">(Houd er rekening mee dat de OneDrive-instelling niet toleranter kan zijn dan de SharePoint-instelling.)</span><span class="sxs-lookup"><span data-stu-id="b6e5d-136">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="b6e5d-137">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-137">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="b6e5d-138">Standaardkoppelingsinstellingen voor SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="b6e5d-138">SharePoint organization level default link settings</span></span>

<span data-ttu-id="b6e5d-139">De standaardinstellingen voor bestands- en mapkoppeling bepalen welke koppelingsoptie standaard aan de gebruiker wordt weergegeven wanneer deze een bestand of map deelt.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-139">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="b6e5d-140">Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat ze desverdeeld delen, indien gewenst.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-140">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="b6e5d-141">Houd er rekening mee dat deze instelling van invloed is op SharePoint-sites in uw organisatie en op OneDrive.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-141">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="b6e5d-142">Kies het type koppeling dat standaard is geselecteerd wanneer gebruikers bestanden en mappen delen:</span><span class="sxs-lookup"><span data-stu-id="b6e5d-142">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="b6e5d-143">**Iedereen met de link** - Kies deze optie als je verwacht veel niet-geverifieerde bestanden en mappen te delen.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-143">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="b6e5d-144">Als u links voor iedereen wilt *toestaan,* maar zich zorgen wilt maken over het per ongeluk delen zonder toestemming, beschouw dan een van de andere opties als de standaardoptie.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-144">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="b6e5d-145">Dit koppelingstype is alleen beschikbaar als je Het delen van **iedereen** hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-145">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="b6e5d-146">**Alleen mensen in uw organisatie** - Kies deze optie als u verwacht dat het delen van bestanden en mappen met mensen binnen uw organisatie is.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-146">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="b6e5d-147">**Specifieke personen** - Overweeg deze optie als u verwacht veel bestands- en mapdelingen met gasten te doen.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-147">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="b6e5d-148">Dit type link werkt samen met gasten en vereist dat ze zich verifiëren.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-148">This type of link works with guests and requires them to authenticate.</span></span>
 
![Schermafbeelding van de instellingen voor delen van bestanden en mappen op organisatieniveau van SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="b6e5d-150">De standaardkoppelingsinstellingen op SharePoint- en OneDrive-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="b6e5d-150">To set the SharePoint and OneDrive organization level default link settings</span></span>

1. <span data-ttu-id="b6e5d-151">Navigeer naar de pagina Delen in het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-151">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="b6e5d-152">Selecteer onder **Koppelingen bestand en mappen**de standaardkoppelingskoppeling die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-152">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="b6e5d-153">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-153">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="b6e5d-154">Instellingen voor delen op SharePoint-siteniveau</span><span class="sxs-lookup"><span data-stu-id="b6e5d-154">SharePoint site level sharing settings</span></span>

<span data-ttu-id="b6e5d-155">Als u bestanden en fodlers deelt die zich op een SharePoint-site bevinden, moet u ook de instellingen voor delen op siteniveau voor die site controleren.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-155">If you're sharing files and fodlers that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Schermafbeelding van de instellingen voor extern delen van SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="b6e5d-157">Instellingen voor delen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="b6e5d-157">To set site-level sharing settings</span></span>
1. <span data-ttu-id="b6e5d-158">Vouw **Sites** uit in het SharePoint Online Beheercentrum in het navigatievenster aan de linkerkant en klik op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-158">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="b6e5d-159">Selecteer de site die u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-159">Select the site that you just created.</span></span>
3. <span data-ttu-id="b6e5d-160">Klik op het lint op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-160">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="b6e5d-161">Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-161">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="b6e5d-162">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-162">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="b6e5d-163">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="b6e5d-163">Invite users</span></span>

<span data-ttu-id="b6e5d-164">Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat gebruikers nu bestanden en mappen kunnen delen met mensen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-164">Guest sharing settings are now configured, so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="b6e5d-165">Zie [OneDrive-bestanden en -mappen delen](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) en [SharePoint-bestanden of -mappen delen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b6e5d-165">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6e5d-166">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b6e5d-166">See Also</span></span>

[<span data-ttu-id="b6e5d-167">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="b6e5d-167">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="b6e5d-168">Accidentele blootstelling aan bestanden beperken tijdens het delen met gasten</span><span class="sxs-lookup"><span data-stu-id="b6e5d-168">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)