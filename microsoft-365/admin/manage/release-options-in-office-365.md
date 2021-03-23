---
title: De opties Standaard of Targeted Release instellen
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
description: Meer informatie over het instellen van de releaseoptie voor nieuwe product- en functiesupdates in het Microsoft 365-beheercentrum.
ms.openlocfilehash: e909cdf35ba9dd8282540783f7c362e5ae49212e
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034077"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="8f7fe-103">De opties Standaard of Targeted Release instellen</span><span class="sxs-lookup"><span data-stu-id="8f7fe-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8f7fe-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-104">The admin center is changing.</span></span> <span data-ttu-id="8f7fe-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="8f7fe-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

> [!IMPORTANT]
> <span data-ttu-id="8f7fe-106">De microsoft 365-updates die in dit artikel worden beschreven, zijn van toepassing op Microsoft 365, SharePoint Online en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-106">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="8f7fe-107">Deze releaseopties zijn doelgerichte manieren om wijzigingen in Microsoft 365 vrij te geven, maar kunnen niet altijd of voor alle updates worden gegarandeerd.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-107">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="8f7fe-108">Ze zijn niet van toepassing op Microsoft 365-apps, Skype voor Bedrijven, Microsoft Teams en gerelateerde services.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-108">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="8f7fe-109">Zie Overzicht van updatekanalen voor Microsoft 365-apps voor informatie over releaseopties voor [Microsoft 365-apps.](/deployoffice/overview-update-channels)</span><span class="sxs-lookup"><span data-stu-id="8f7fe-109">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="8f7fe-110">Met Microsoft 365 ontvangt u nieuwe productupdates en -functies zodra deze beschikbaar komen in plaats van om de paar jaar dure updates uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-110">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="8f7fe-111">U kunt beheren hoe uw organisatie deze updates ontvangt.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-111">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="8f7fe-112">U kunt u bijvoorbeeld registreren voor een vroege release, zodat uw organisatie updates als eerste ontvangt.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-112">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="8f7fe-113">U kunt bepaalde personen aanwijzen die als enigen de updates ontvangen.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-113">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="8f7fe-114">Of u blijft het standaardreleaseschema volgen en ontvangt de updates later.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-114">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="8f7fe-115">In dit artikel worden de verschillende releaseopties beschreven en wordt uitgelegd hoe u deze voor uw organisatie kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-115">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="8f7fe-116">Hoe het werkt: validatie van releases</span><span class="sxs-lookup"><span data-stu-id="8f7fe-116">How it works - release validation</span></span>

<span data-ttu-id="8f7fe-117">Een nieuwe release wordt eerst getest en gevalideerd door het functieteam, vervolgens door het hele Microsoft 365-functieteam, gevolgd door heel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="8f7fe-118">Na intern testen en valideren bestaat de volgende stap uit een **Targeted Release** (eerder bekend als First Release) voor klanten die zich aanmelden.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="8f7fe-119">Bij elke release-ring verzamelt Microsoft feedback en valideert de kwaliteit verder door belangrijke gebruiksgegevens te controleren.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="8f7fe-120">Deze reeks van toenemende validatie is ingesteld om er voor te zorgen dat de mondiale release zo robuust mogelijk is.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="8f7fe-121">De releases worden in de volgende afbeelding geïllustreerd.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-121">The releases are pictured in the following figure.</span></span> 
  
![Releasevalidatieringen voor Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="8f7fe-123">Voor belangrijke updates krijgen klanten in eerste instantie een melding via de [Routekaart voor Microsoft 365.](https://products.office.com/business/office-365-roadmap)</span><span class="sxs-lookup"><span data-stu-id="8f7fe-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="8f7fe-124">Naarmate een update dichter bij de uitrol komt, wordt deze gecommuniceerd via uw [Microsoft 365-berichtencentrum.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="8f7fe-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="8f7fe-125">U hebt een Microsoft 365- of Azure AD-account nodig om toegang te krijgen tot uw Berichtencentrum via [het beheercentrum.](/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="8f7fe-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="8f7fe-126">Gebruikers van een Microsoft 365 Home-abonnement hebben geen beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="8f7fe-127">Standard Release</span><span class="sxs-lookup"><span data-stu-id="8f7fe-127">Standard release</span></span>

<span data-ttu-id="8f7fe-128">Dit is de standaardoptie waarbij u en uw gebruikers de meest recente updates ontvangen wanneer ze breed worden uitgebracht voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="8f7fe-129">Een goede gewoonte is om de meerderheid van de gebruikers in standard release en **IT-professionals** en power users achter te laten in **targeted release** om nieuwe functies te evalueren en teams voor te bereiden om zakelijke gebruikers en leidinggevenden te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8f7fe-130">Als u van het First Release-programma teruggaat naar het Standard Release-programma, hebben uw gebruikers mogelijk geen toegang meer tot functies die nog niet zijn opgenomen in het Standard Release-programma.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="8f7fe-131">Targeted Release</span><span class="sxs-lookup"><span data-stu-id="8f7fe-131">Targeted release</span></span>

<span data-ttu-id="8f7fe-p107">Met deze optie zien u en uw gebruikers als eersten de nieuwste updates en kunt u helpen het product te vormen door vroege feedback te geven. U kunt bepalen of de vroege updates naar afzonderlijke personen of naar de hele organisatie worden gestuurd.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8f7fe-p108">Bij grote of complexe updates duurt dit mogelijk langer dan bij andere updates zodat er geen gebruikers negatief worden beïnvloed. De exacte tijdlijn van een release kan niet worden gegarandeerd.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="8f7fe-136">Targeted Release voor de hele organisatie</span><span class="sxs-lookup"><span data-stu-id="8f7fe-136">Targeted release for entire organization</span></span>

<span data-ttu-id="8f7fe-137">Als u [de releaseoptie in het beheercentrum](#set-up-the-release-option-in-the-admin-center) voor deze optie in stelt, krijgen al uw gebruikers de targeted release-ervaring.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="8f7fe-138">Voor organisaties met meer dan 300 gebruikers wordt een testabonnement op deze optie aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="8f7fe-139">Neem contact op met uw Microsoft-contactpersoon voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="8f7fe-140">Targeted Release voor specifieke gebruikers</span><span class="sxs-lookup"><span data-stu-id="8f7fe-140">Targeted release for selected users</span></span>

<span data-ttu-id="8f7fe-141">Als u [de releaseoptie in](#set-up-the-release-option-in-the-admin-center) het beheercentrum voor deze optie in stelt, kunt u specifieke gebruikers definiëren, meestal power users, om vroegtijdige toegang te krijgen tot functies en functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="8f7fe-142">Voordelen van Targeted Release</span><span class="sxs-lookup"><span data-stu-id="8f7fe-142">Benefits of Targeted release</span></span>

<span data-ttu-id="8f7fe-143">Met een gerichte release kunnen beheerders, wijzigingsmanagers of andere verantwoordelijken voor Microsoft 365-updates zich voorbereiden op de komende wijzigingen door ze te laten:</span><span class="sxs-lookup"><span data-stu-id="8f7fe-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="8f7fe-144">Nieuwe updates testen en valideren voordat deze worden uitgebracht voor alle gebruikers in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="8f7fe-145">Meldingen en documentatie voor gebruikers voorbereiden voordat de updates mondiaal worden uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="8f7fe-146">Een interne helpdesk in verband met aanstaande updates voorbereiden</span><span class="sxs-lookup"><span data-stu-id="8f7fe-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="8f7fe-147">Beoordelingen betreffende naleving en beveiliging doornemen.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="8f7fe-148">Besturingselementen voor functies gebruiken om de uitgifte van updates voor eindgebruikers te reguleren.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="8f7fe-149">De releaseoptie instellen in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="8f7fe-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="8f7fe-150">U kunt de manier wijzigen waarop uw organisatie Microsoft 365-updates ontvangt door deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="8f7fe-151">U moet een globale beheerder zijn in Microsoft 365 om u aan te kunnen.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8f7fe-152">Het kan tot 24 uur duren voordat de onderstaande wijzigingen van kracht worden in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="8f7fe-153">Als u zich afmeldt nadat u het programma hebt ingeschakeld, hebben uw gebruikers mogelijk geen toegang meer tot functies waarvan de geplande release nog niet beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="8f7fe-154">Ga in het beheercentrum naar **instellingen** organisatieinstelling en kies onder het tabblad  >  Organisatieprofiel de optie **Releasevoorkeuren.** </span><span class="sxs-lookup"><span data-stu-id="8f7fe-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="8f7fe-155">Als u gerichte release wilt uitschakelen, selecteert u **Standaardversie** en **selecteert u Vervolgens Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="8f7fe-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="8f7fe-156">Als u een gerichte release wilt inschakelen voor alle gebruikers in uw organisatie, **selecteert** u Targeted release voor iedereen en selecteert u **Vervolgens Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="8f7fe-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="8f7fe-157">Als u gerichte release wilt inschakelen voor sommige personen in uw organisatie, **selecteert** u Targeted release voor geselecteerde gebruikers en selecteert u **Vervolgens Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="8f7fe-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="8f7fe-158">Kies **Gebruikers selecteren** om gebruikers één voor één toe te voegen of Gebruikers uploaden **om** ze bulksgewijs toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="8f7fe-159">Wanneer u klaar bent met het toevoegen van gebruikers, selecteert u **Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="8f7fe-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="8f7fe-160">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="8f7fe-160">Learn more</span></span>

<span data-ttu-id="8f7fe-161">Ontdek hoe u [berichten beheert](/office365/admin/manage/message-center) in uw [Microsoft 365-berichtencentrum](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) om meldingen te krijgen over toekomstige Updates en releases van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f7fe-161">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8f7fe-162">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="8f7fe-162">Related Articles</span></span>

[<span data-ttu-id="8f7fe-163">Office Insider</span><span class="sxs-lookup"><span data-stu-id="8f7fe-163">Office Insider</span></span>](https://insider.office.com/join/windows)
