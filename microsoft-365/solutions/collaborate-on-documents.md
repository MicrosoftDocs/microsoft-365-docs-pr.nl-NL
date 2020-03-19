---
title: Samenwerken met gasten aan een document
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over hoe u met gasten samenwerken aan een document in SharePoint en OneDrive.
ms.openlocfilehash: 139533b2d7bf65ddd9584007a5ac03800c731d0b
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2020
ms.locfileid: "42810366"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="3bd71-103">Samenwerken met gasten aan een document</span><span class="sxs-lookup"><span data-stu-id="3bd71-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="3bd71-104">Als u met mensen buiten uw organisatie moet samenwerken aan documenten in SharePoint of OneDrive, u ze een koppeling voor delen naar het document sturen.</span><span class="sxs-lookup"><span data-stu-id="3bd71-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing link to the document.</span></span> <span data-ttu-id="3bd71-105">In dit artikel doorlopen we de configuratiestappen van Microsoft 365 die nodig zijn om koppelingen voor delen voor SharePoint en OneDrive in te stellen voor de behoeften van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3bd71-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="3bd71-106">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="3bd71-106">Video demonstration</span></span>

<span data-ttu-id="3bd71-107">In deze video worden de configuratiestappen weergegeven die in dit document worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="3bd71-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="3bd71-108">Instellingen voor Azure Organizational Relationships</span><span class="sxs-lookup"><span data-stu-id="3bd71-108">Azure Organizational relationships settings</span></span>

<span data-ttu-id="3bd71-109">Delen in Microsoft 365 wordt op het hoogste niveau geregeld door de instellingen voor organisatierelaties in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3bd71-109">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="3bd71-110">Als het delen van gasten is uitgeschakeld of beperkt in Azure AD, worden alle instellingen voor delen die u configureert in Microsoft 365, overschreven.</span><span class="sxs-lookup"><span data-stu-id="3bd71-110">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="3bd71-111">Controleer de instellingen voor organisatierelaties om ervoor te zorgen dat delen met gasten niet wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="3bd71-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Schermafbeelding van de pagina Instellingen voor Azure Active Directory-organisatierelaties](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="3bd71-113">Instellingen voor organisatierelatie instellen</span><span class="sxs-lookup"><span data-stu-id="3bd71-113">To set organizational relationship settings</span></span>

1. <span data-ttu-id="3bd71-114">Log in bij [https://portal.azure.com](https://portal.azure.com)Microsoft Azure bij .</span><span class="sxs-lookup"><span data-stu-id="3bd71-114">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="3bd71-115">Klik in de linkernavigatie op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="3bd71-115">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="3bd71-116">Klik in het deelvenster **Overzicht** op **Organisatierelaties**.</span><span class="sxs-lookup"><span data-stu-id="3bd71-116">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="3bd71-117">Klik in het deelvenster **Organisatierelaties** op **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="3bd71-117">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="3bd71-118">Zorg ervoor dat **beheerders en gebruikers in de rol gastgenodigden kunnen uitnodigen** en leden kunnen **uitnodigen,** zijn beide ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3bd71-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="3bd71-119">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3bd71-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="3bd71-120">Let op de instellingen in de sectie **Beperkingen voor samenwerking.**</span><span class="sxs-lookup"><span data-stu-id="3bd71-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="3bd71-121">Zorg ervoor dat de domeinen van de gasten waarmee u wilt samenwerken niet worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="3bd71-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="3bd71-122">Instellingen voor delen op sharepoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="3bd71-122">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="3bd71-123">Om ervoor te zorgen dat mensen buiten uw organisatie toegang hebben tot een document in SharePoint of OneDrive, moeten de instellingen voor delen op organisatieniveau op organisatieniveau het delen met mensen buiten uw organisatie mogelijk maken.</span><span class="sxs-lookup"><span data-stu-id="3bd71-123">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="3bd71-124">De instellingen op organisatieniveau voor SharePoint bepalen welke instellingen beschikbaar zijn voor afzonderlijke SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="3bd71-124">The organization-level settings for SharePoint determine what settings are available for individual SharePoint sites.</span></span> <span data-ttu-id="3bd71-125">Site-instellingen kunnen niet toleranter zijn dan de instellingen op organisatieniveau.</span><span class="sxs-lookup"><span data-stu-id="3bd71-125">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="3bd71-126">De instelling op organisatieniveau voor OneDrive bepaalt welk niveau van delen beschikbaar is in de OneDrive-bibliotheken van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="3bd71-126">The organization-level setting for OneDrive determines what level of sharing is available in users' OneDrive libraries.</span></span>

<span data-ttu-id="3bd71-127">Kies Voor SharePoint en OneDrive de optie **Iedereen**kiezen als u niet-geverifieerde bestanden en mappen wilt delen.</span><span class="sxs-lookup"><span data-stu-id="3bd71-127">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="3bd71-128">Als u ervoor wilt zorgen dat mensen buiten uw organisatie zich moeten authenticeren, kiest u **Nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="3bd71-128">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="3bd71-129">*Iedereen* links zijn de makkelijkste manier om te delen: mensen buiten uw organisatie kunnen de link openen zonder authenticatie en zijn vrij om het door te geven aan anderen.</span><span class="sxs-lookup"><span data-stu-id="3bd71-129">*Anyone* links are the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="3bd71-130">Kies voor SharePoint de meest tolerante instelling die nodig is voor elke site in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3bd71-130">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Schermafbeelding van instellingen voor delen op sharepoint-organisatieniveau](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="3bd71-132">Instellingen voor delen op sharepoint-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="3bd71-132">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="3bd71-133">Klik in het Microsoft 365-beheercentrum in de linkernavigatie onder **Beheercentra**op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="3bd71-133">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="3bd71-134">Klik in het SharePoint-beheercentrum in de linkernavigatie op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="3bd71-134">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="3bd71-135">Zorg ervoor dat extern delen voor SharePoint of OneDrive is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="3bd71-135">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="3bd71-136">(Houd er rekening mee dat de Instelling OneDrive niet toleranter kan zijn dan de SharePoint-instelling.)</span><span class="sxs-lookup"><span data-stu-id="3bd71-136">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="3bd71-137">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3bd71-137">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="3bd71-138">Standaardkoppelingsinstellingen voor SharePoint-organisatieniveau</span><span class="sxs-lookup"><span data-stu-id="3bd71-138">SharePoint organization level default link settings</span></span>

<span data-ttu-id="3bd71-139">De instellingen voor standaardbestands- en mapkoppelingen bepalen welke koppelingsoptie standaard aan de gebruiker wordt weergegeven wanneer deze een bestand of map deelt.</span><span class="sxs-lookup"><span data-stu-id="3bd71-139">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="3bd71-140">Gebruikers kunnen het koppelingstype wijzigen in een van de andere opties voordat ze desgewenst delen.</span><span class="sxs-lookup"><span data-stu-id="3bd71-140">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="3bd71-141">Houd er rekening mee dat deze instelling van invloed is op SharePoint-sites in uw organisatie en op OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3bd71-141">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="3bd71-142">Kies het type koppeling dat standaard is geselecteerd wanneer gebruikers bestanden en mappen delen:</span><span class="sxs-lookup"><span data-stu-id="3bd71-142">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="3bd71-143">**Iedereen met de koppeling** - Kies deze optie als u verwacht veel niet-geverifieerde bestanden en mappen te delen.</span><span class="sxs-lookup"><span data-stu-id="3bd71-143">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="3bd71-144">Als u *Koppelingen* wilt toestaan, maar zich zorgen maakt over het per ongeluk niet-geverifieerde delen, beschouw dan een van de andere opties als standaard.</span><span class="sxs-lookup"><span data-stu-id="3bd71-144">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="3bd71-145">Dit koppelingstype is alleen beschikbaar als u iedereen hebt ingeschakeld om **te** delen.</span><span class="sxs-lookup"><span data-stu-id="3bd71-145">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="3bd71-146">**Alleen mensen in uw organisatie** - Kies deze optie als u verwacht dat het delen van bestanden en mappen het meest met mensen binnen uw organisatie is.</span><span class="sxs-lookup"><span data-stu-id="3bd71-146">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="3bd71-147">**Specifieke mensen** - Overweeg deze optie als u verwacht veel bestanden en mappen te delen met gasten.</span><span class="sxs-lookup"><span data-stu-id="3bd71-147">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="3bd71-148">Dit type koppeling werkt samen met gasten en vereist dat ze zich verifiëren.</span><span class="sxs-lookup"><span data-stu-id="3bd71-148">This type of link works with guests and requires them to authenticate.</span></span>
 
![Schermafbeelding van instellingen voor delen op organisatieniveau](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="3bd71-150">Standaardkoppelingsinstellingen voor SharePoint- en OneDrive-organisatieniveau instellen</span><span class="sxs-lookup"><span data-stu-id="3bd71-150">To set the SharePoint and OneDrive organization level default link settings</span></span>

1. <span data-ttu-id="3bd71-151">Navigeer naar de pagina Delen in het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="3bd71-151">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="3bd71-152">Selecteer onder **Bestands- en mapkoppelingen**de standaardkoppeling voor delen die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3bd71-152">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="3bd71-153">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3bd71-153">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="3bd71-154">Instellingen voor delen op sharepoint-siteniveau</span><span class="sxs-lookup"><span data-stu-id="3bd71-154">SharePoint site level sharing settings</span></span>

<span data-ttu-id="3bd71-155">Als u bestanden en fodlers deelt die zich op een SharePoint-site bevinden, moet u ook de instellingen voor het delen op siteniveau voor die site controleren.</span><span class="sxs-lookup"><span data-stu-id="3bd71-155">If you're sharing files and fodlers that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Schermafbeelding van instellingen voor extern delen van de SharePoint-site](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="3bd71-157">Instellingen voor delen op siteniveau instellen</span><span class="sxs-lookup"><span data-stu-id="3bd71-157">To set site-level sharing settings</span></span>
1. <span data-ttu-id="3bd71-158">Vouw **sites** in het SharePoint-beheercentrum uit en klik op **Actieve sites**in het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="3bd71-158">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="3bd71-159">Selecteer de site die u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="3bd71-159">Select the site that you just created.</span></span>
3. <span data-ttu-id="3bd71-160">Klik op het lint op **Delen**.</span><span class="sxs-lookup"><span data-stu-id="3bd71-160">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="3bd71-161">Zorg ervoor dat delen is ingesteld op **iedereen** of **nieuwe en bestaande gasten.**</span><span class="sxs-lookup"><span data-stu-id="3bd71-161">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="3bd71-162">Als u wijzigingen hebt aangebracht, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3bd71-162">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="3bd71-163">Gebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="3bd71-163">Invite users</span></span>

<span data-ttu-id="3bd71-164">Instellingen voor het delen van gasten zijn nu geconfigureerd, zodat gebruikers nu bestanden en mappen kunnen delen met mensen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3bd71-164">Guest sharing settings are now configured, so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="3bd71-165">Zie [OneDrive-bestanden en -mappen delen](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) en [SharePoint-bestanden of -mappen delen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3bd71-165">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="3bd71-166">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3bd71-166">See Also</span></span>

[<span data-ttu-id="3bd71-167">Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="3bd71-167">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="3bd71-168">Onbedoelde blootstelling aan bestanden beperken wanneer u deelt met gasten</span><span class="sxs-lookup"><span data-stu-id="3bd71-168">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)