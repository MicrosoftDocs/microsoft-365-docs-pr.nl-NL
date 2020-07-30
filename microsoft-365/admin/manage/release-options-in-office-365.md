---
title: De opties voor standaard of gerichte release instellen
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Meer informatie over het instellen van de releaseoptie voor nieuwe product- en functies-updates in het Microsoft 365-beheercentrum.
ms.openlocfilehash: 3baec050f33893357b25c832552643cf3a6d10d0
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502877"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="e8035-103">De opties voor standaard of gerichte release instellen</span><span class="sxs-lookup"><span data-stu-id="e8035-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e8035-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="e8035-104">The admin center is changing.</span></span> <span data-ttu-id="e8035-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e8035-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e8035-106">Met Microsoft 365 ontvangt u nieuwe productupdates en -functies zodra deze beschikbaar zijn in plaats van om de paar jaar dure updates uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="e8035-106">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="e8035-107">U kunt beheren hoe uw organisatie deze updates ontvangt.</span><span class="sxs-lookup"><span data-stu-id="e8035-107">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="e8035-108">U kunt u bijvoorbeeld registreren voor een vroege release, zodat uw organisatie updates als eerste ontvangt.</span><span class="sxs-lookup"><span data-stu-id="e8035-108">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="e8035-109">U kunt bepaalde personen aanwijzen die als enigen de updates ontvangen.</span><span class="sxs-lookup"><span data-stu-id="e8035-109">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="e8035-110">Of u blijft het standaardreleaseschema volgen en ontvangt de updates later.</span><span class="sxs-lookup"><span data-stu-id="e8035-110">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="e8035-111">In dit artikel worden de verschillende releaseopties uitgelegd en hoe u deze gebruiken voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e8035-111">This article explains the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e8035-112">De In dit artikel beschreven Microsoft 365-updates zijn van toepassing op Microsoft 365, SharePoint Online en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e8035-112">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="e8035-113">Ze zijn niet van toepassing op Skype voor Bedrijven en gerelateerde services.</span><span class="sxs-lookup"><span data-stu-id="e8035-113">They do not apply to Skype for Business and related services.</span></span> <span data-ttu-id="e8035-114">Deze releaseopties zijn gerichte manieren om wijzigingen in Microsoft 365 vrij te geven, maar kunnen niet te allen tijde of voor alle updates worden gegarandeerd.</span><span class="sxs-lookup"><span data-stu-id="e8035-114">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> 

> [!NOTE]
> <span data-ttu-id="e8035-115">Zie [Overzicht van updatekanalen voor Microsoft 365 Apps voor](https://docs.microsoft.com/deployoffice/overview-update-channels)informatie over updatekanalen voor toepassingen.</span><span class="sxs-lookup"><span data-stu-id="e8035-115">For information about update channels for applications, see [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="e8035-116">Hoe het werkt: validatie van releases</span><span class="sxs-lookup"><span data-stu-id="e8035-116">How it works - release validation</span></span>

<span data-ttu-id="e8035-117">Elke nieuwe release wordt eerst getest en gevalideerd door het functieteam, vervolgens door het hele Microsoft 365-functieteam, gevolgd door heel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e8035-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="e8035-118">Na intern testen en valideren bestaat de volgende stap uit een **Targeted Release** (eerder bekend als First Release) voor klanten die zich aanmelden.</span><span class="sxs-lookup"><span data-stu-id="e8035-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="e8035-119">Bij elke release-ring verzamelt Microsoft feedback en valideert de kwaliteit verder door belangrijke gebruiksgegevens te controleren.</span><span class="sxs-lookup"><span data-stu-id="e8035-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="e8035-120">Deze reeks van toenemende validatie is ingesteld om er voor te zorgen dat de mondiale release zo robuust mogelijk is.</span><span class="sxs-lookup"><span data-stu-id="e8035-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="e8035-121">De releases worden in de volgende afbeelding geïllustreerd.</span><span class="sxs-lookup"><span data-stu-id="e8035-121">The releases are pictured in the following figure.</span></span> 
  
![Validatieringen voor Microsoft 365 vrijgeven](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="e8035-123">Voor belangrijke updates worden klanten in eerste instantie op de hoogte gebracht door de [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="e8035-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="e8035-124">Als een update dichter bij de uitrol komt, wordt deze gecommuniceerd via uw [Microsoft 365 Message center.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="e8035-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="e8035-125">U hebt een Microsoft 365- of Azure AD-account nodig om toegang te krijgen tot uw Berichtencentrum via het [beheercentrum.](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="e8035-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="e8035-126">Gebruikers van Microsoft 365 home plan hebben geen beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="e8035-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="e8035-127">Standard Release</span><span class="sxs-lookup"><span data-stu-id="e8035-127">Standard release</span></span>

<span data-ttu-id="e8035-128">Dit is de standaardoptie waarbij u en uw gebruikers de nieuwste updates ontvangen wanneer ze breed worden vrijgegeven aan alle klanten.</span><span class="sxs-lookup"><span data-stu-id="e8035-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="e8035-129">Een goede praktijk is om de meerderheid van de gebruikers in **Standard release** en IT Pro's en power users in **Targeted release** om nieuwe functies te evalueren en teams voor te bereiden om zakelijke gebruikers en leidinggevenden te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="e8035-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e8035-130">Als u van het First Release-programma teruggaat naar het Standard Release-programma, hebben uw gebruikers mogelijk geen toegang meer tot functies die nog niet zijn opgenomen in het Standard Release-programma.</span><span class="sxs-lookup"><span data-stu-id="e8035-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="e8035-131">Targeted Release</span><span class="sxs-lookup"><span data-stu-id="e8035-131">Targeted release</span></span>

<span data-ttu-id="e8035-p107">Met deze optie zien u en uw gebruikers als eersten de nieuwste updates en kunt u helpen het product te vormen door vroege feedback te geven. U kunt bepalen of de vroege updates naar afzonderlijke personen of naar de hele organisatie worden gestuurd.</span><span class="sxs-lookup"><span data-stu-id="e8035-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e8035-p108">Bij grote of complexe updates duurt dit mogelijk langer dan bij andere updates zodat er geen gebruikers negatief worden beïnvloed. De exacte tijdlijn van een release kan niet worden gegarandeerd.</span><span class="sxs-lookup"><span data-stu-id="e8035-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="e8035-136">Targeted Release voor de hele organisatie</span><span class="sxs-lookup"><span data-stu-id="e8035-136">Targeted release for entire organization</span></span>

<span data-ttu-id="e8035-137">Als u de releaseoptie voor deze optie [in het beheercentrum instelt,](#set-up-the-release-option-in-the-admin-center) krijgen al uw gebruikers de gerichte release-ervaring.</span><span class="sxs-lookup"><span data-stu-id="e8035-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="e8035-138">Voor organisaties met meer dan 300 gebruikers wordt een testabonnement op deze optie aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="e8035-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="e8035-139">Neem contact op met uw Microsoft-contactpersoon voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e8035-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="e8035-140">Targeted Release voor specifieke gebruikers</span><span class="sxs-lookup"><span data-stu-id="e8035-140">Targeted release for selected users</span></span>

<span data-ttu-id="e8035-141">Als u de releaseoptie voor deze optie [in het beheercentrum instelt,](#set-up-the-release-option-in-the-admin-center) u specifieke gebruikers definiëren, meestal power users, om vroegtijdig toegang te krijgen tot functies en functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="e8035-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="e8035-142">Voordelen van Targeted Release</span><span class="sxs-lookup"><span data-stu-id="e8035-142">Benefits of Targeted release</span></span>

<span data-ttu-id="e8035-143">Met gerichte release kunnen beheerders, change managers of iemand anders die verantwoordelijk zijn voor Microsoft 365-updates zich voorbereiden op de komende wijzigingen door ze te laten:</span><span class="sxs-lookup"><span data-stu-id="e8035-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="e8035-144">Nieuwe updates testen en valideren voordat deze worden uitgebracht voor alle gebruikers in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="e8035-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="e8035-145">Meldingen en documentatie voor gebruikers voorbereiden voordat de updates mondiaal worden uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="e8035-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="e8035-146">Een interne helpdesk in verband met aanstaande updates voorbereiden</span><span class="sxs-lookup"><span data-stu-id="e8035-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="e8035-147">Beoordelingen betreffende naleving en beveiliging doornemen.</span><span class="sxs-lookup"><span data-stu-id="e8035-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="e8035-148">Besturingselementen voor functies gebruiken om de uitgifte van updates voor eindgebruikers te reguleren.</span><span class="sxs-lookup"><span data-stu-id="e8035-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="e8035-149">De releaseoptie instellen in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="e8035-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="e8035-150">U de manier wijzigen waarop uw organisatie Microsoft 365-updates ontvangt door deze stappen te volgen.</span><span class="sxs-lookup"><span data-stu-id="e8035-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="e8035-151">Je moet een wereldwijde beheerder in Microsoft 365 om in te kiezen.</span><span class="sxs-lookup"><span data-stu-id="e8035-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e8035-152">Het kan tot 24 uur duren voordat de onderstaande wijzigingen van kracht worden in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8035-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="e8035-153">Als u zich afmeldt nadat u het programma hebt ingeschakeld, hebben uw gebruikers mogelijk geen toegang meer tot functies waarvan de geplande release nog niet beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="e8035-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="e8035-154">Ga in het beheercentrum **Settings**naar de  >  **instelling Instellingen organisatie**en kies onder het profiel van de **organisatie** de optie **Voorkeuren vrijgeven**.</span><span class="sxs-lookup"><span data-stu-id="e8035-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="e8035-155">Als u gerichte release wilt uitschakelen, selecteert u **Standaardrelease**en selecteert u **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e8035-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="e8035-156">Als u gerichte release voor alle gebruikers in uw organisatie wilt inschakelen, selecteert u **Gerichte release voor iedereen**en selecteert u Wijzigingen **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="e8035-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="e8035-157">Als u gerichte release voor sommige mensen in uw organisatie wilt inschakelen, selecteert u **Gerichte release voor geselecteerde gebruikers**en selecteert u Wijzigingen **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="e8035-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="e8035-158">Kies **Gebruikers selecteren** om gebruikers één voor één toe te voegen of Upload **gebruikers** om ze in bulk toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="e8035-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="e8035-159">Wanneer u klaar bent met het toevoegen van gebruikers, selecteert u **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e8035-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="e8035-160">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="e8035-160">Learn more</span></span>

<span data-ttu-id="e8035-161">Ontdek hoe u [berichten beheert](https://docs.microsoft.com/office365/admin/manage/message-center) in uw [Microsoft 365-berichtencentrum](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) om meldingen te ontvangen over toekomstige Microsoft 365-updates en -releases.</span><span class="sxs-lookup"><span data-stu-id="e8035-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
