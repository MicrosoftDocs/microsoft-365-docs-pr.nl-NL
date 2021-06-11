---
title: De opties Standaard of Targeted Release instellen
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
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
description: Meer informatie over het instellen van de releaseoptie voor nieuwe product- en functiesupdates in het Microsoft 365 beheercentrum.
ms.openlocfilehash: 5060e2dc99355d89928ec91c96b7d25e2016c7c4
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593943"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="58fb4-103">De opties Standaard of Targeted Release instellen</span><span class="sxs-lookup"><span data-stu-id="58fb4-103">Set up the Standard or Targeted release options</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58fb4-104">De Microsoft 365 in dit artikel beschreven updates zijn van toepassing op Microsoft 365, SharePoint Online en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="58fb4-104">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="58fb4-105">Deze releaseopties zijn doelgerichte manieren om wijzigingen in Microsoft 365 vrij te geven, maar kunnen niet altijd of voor alle updates worden gegarandeerd.</span><span class="sxs-lookup"><span data-stu-id="58fb4-105">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="58fb4-106">Ze zijn niet van toepassing op Microsoft 365-apps, Skype voor Bedrijven, Microsoft Teams en gerelateerde services.</span><span class="sxs-lookup"><span data-stu-id="58fb4-106">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="58fb4-107">Zie Overzicht van updatekanalen voor Microsoft 365-apps voor meer informatie over [releaseopties voor Microsoft 365-apps.](/deployoffice/overview-update-channels)</span><span class="sxs-lookup"><span data-stu-id="58fb4-107">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="58fb4-108">Met Microsoft 365 ontvangt u nieuwe productupdates en -functies zodra deze beschikbaar komen in plaats van om de paar jaar dure updates uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="58fb4-108">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="58fb4-109">U kunt beheren hoe uw organisatie deze updates ontvangt.</span><span class="sxs-lookup"><span data-stu-id="58fb4-109">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="58fb4-110">U kunt u bijvoorbeeld registreren voor een vroege release, zodat uw organisatie updates als eerste ontvangt.</span><span class="sxs-lookup"><span data-stu-id="58fb4-110">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="58fb4-111">U kunt bepaalde personen aanwijzen die als enigen de updates ontvangen.</span><span class="sxs-lookup"><span data-stu-id="58fb4-111">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="58fb4-112">Of u blijft het standaardreleaseschema volgen en ontvangt de updates later.</span><span class="sxs-lookup"><span data-stu-id="58fb4-112">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="58fb4-113">In dit artikel worden de verschillende releaseopties beschreven en wordt uitgelegd hoe u deze voor uw organisatie kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="58fb4-113">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="58fb4-114">Hoe het werkt: validatie van releases</span><span class="sxs-lookup"><span data-stu-id="58fb4-114">How it works - release validation</span></span>

<span data-ttu-id="58fb4-115">Een nieuwe release wordt eerst getest en gevalideerd door het functieteam, vervolgens door het hele Microsoft 365-functieteam, gevolgd door heel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="58fb4-115">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="58fb4-116">Na intern testen en valideren bestaat de volgende stap uit een **Targeted Release** (eerder bekend als First Release) voor klanten die zich aanmelden.</span><span class="sxs-lookup"><span data-stu-id="58fb4-116">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="58fb4-117">Bij elke release-ring verzamelt Microsoft feedback en valideert de kwaliteit verder door belangrijke gebruiksgegevens te controleren.</span><span class="sxs-lookup"><span data-stu-id="58fb4-117">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="58fb4-118">Deze reeks van toenemende validatie is ingesteld om er voor te zorgen dat de mondiale release zo robuust mogelijk is.</span><span class="sxs-lookup"><span data-stu-id="58fb4-118">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="58fb4-119">De releases worden in de volgende afbeelding geïllustreerd.</span><span class="sxs-lookup"><span data-stu-id="58fb4-119">The releases are pictured in the following figure.</span></span> 
  
![Releasevalidatieringen voor Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="58fb4-121">Voor belangrijke updates worden klanten in eerste instantie op de hoogte gesteld door [de Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="58fb4-121">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="58fb4-122">Naarmate een update dichter bij de uitrol komt, wordt deze gecommuniceerd via [uw Microsoft 365 Berichtencentrum.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="58fb4-122">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="58fb4-123">U hebt een Microsoft 365 of Azure AD-account nodig om toegang te krijgen tot uw Berichtencentrum via [het beheercentrum.](/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="58fb4-123">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="58fb4-124">Microsoft 365 gebruikers van een thuisplan hebben geen beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="58fb4-124">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="58fb4-125">Standard Release</span><span class="sxs-lookup"><span data-stu-id="58fb4-125">Standard release</span></span>

<span data-ttu-id="58fb4-126">Dit is de standaardoptie waarbij u en uw gebruikers de meest recente updates ontvangen wanneer ze breed worden uitgebracht voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="58fb4-126">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="58fb4-127">Een goede gewoonte is om de meerderheid van de gebruikers in standard release en **IT-professionals** en power users achter te laten in **targeted release** om nieuwe functies te evalueren en teams voor te bereiden om zakelijke gebruikers en leidinggevenden te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="58fb4-127">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="58fb4-128">Als u van het First Release-programma teruggaat naar het Standard Release-programma, hebben uw gebruikers mogelijk geen toegang meer tot functies die nog niet zijn opgenomen in het Standard Release-programma.</span><span class="sxs-lookup"><span data-stu-id="58fb4-128">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="58fb4-129">Targeted Release</span><span class="sxs-lookup"><span data-stu-id="58fb4-129">Targeted release</span></span>

<span data-ttu-id="58fb4-p106">Met deze optie zien u en uw gebruikers als eersten de nieuwste updates en kunt u helpen het product te vormen door vroege feedback te geven. U kunt bepalen of de vroege updates naar afzonderlijke personen of naar de hele organisatie worden gestuurd.</span><span class="sxs-lookup"><span data-stu-id="58fb4-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="58fb4-p107">Bij grote of complexe updates duurt dit mogelijk langer dan bij andere updates zodat er geen gebruikers negatief worden beïnvloed. De exacte tijdlijn van een release kan niet worden gegarandeerd.</span><span class="sxs-lookup"><span data-stu-id="58fb4-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="58fb4-134">Targeted Release voor de hele organisatie</span><span class="sxs-lookup"><span data-stu-id="58fb4-134">Targeted release for entire organization</span></span>

<span data-ttu-id="58fb4-135">Als u [de releaseoptie in het beheercentrum](#set-up-the-release-option-in-the-admin-center) voor deze optie in stelt, krijgen al uw gebruikers de targeted release-ervaring.</span><span class="sxs-lookup"><span data-stu-id="58fb4-135">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="58fb4-136">Voor organisaties met meer dan 300 gebruikers wordt een testabonnement op deze optie aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="58fb4-136">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="58fb4-137">Neem contact op met uw Microsoft-contactpersoon voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="58fb4-137">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="58fb4-138">Targeted Release voor specifieke gebruikers</span><span class="sxs-lookup"><span data-stu-id="58fb4-138">Targeted release for selected users</span></span>

<span data-ttu-id="58fb4-139">Als u [de releaseoptie in](#set-up-the-release-option-in-the-admin-center) het beheercentrum voor deze optie in stelt, kunt u specifieke gebruikers definiëren, meestal power users, om vroegtijdige toegang te krijgen tot functies en functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="58fb4-139">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="58fb4-140">Voordelen van Targeted Release</span><span class="sxs-lookup"><span data-stu-id="58fb4-140">Benefits of Targeted release</span></span>

<span data-ttu-id="58fb4-141">Met een gerichte release kunnen beheerders, wijzigingsmanagers of andere verantwoordelijken Microsoft 365 updates voorbereiden op de komende wijzigingen door ze te laten:</span><span class="sxs-lookup"><span data-stu-id="58fb4-141">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="58fb4-142">Nieuwe updates testen en valideren voordat deze worden uitgebracht voor alle gebruikers in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="58fb4-142">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="58fb4-143">Meldingen en documentatie voor gebruikers voorbereiden voordat de updates mondiaal worden uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="58fb4-143">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="58fb4-144">Een interne helpdesk in verband met aanstaande updates voorbereiden</span><span class="sxs-lookup"><span data-stu-id="58fb4-144">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="58fb4-145">Beoordelingen betreffende naleving en beveiliging doornemen.</span><span class="sxs-lookup"><span data-stu-id="58fb4-145">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="58fb4-146">Besturingselementen voor functies gebruiken om de uitgifte van updates voor eindgebruikers te reguleren.</span><span class="sxs-lookup"><span data-stu-id="58fb4-146">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="58fb4-147">De releaseoptie instellen in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="58fb4-147">Set up the release option in the admin center</span></span>

<span data-ttu-id="58fb4-148">U kunt de manier wijzigen waarop uw organisatie updates Microsoft 365 ontvangen door deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="58fb4-148">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="58fb4-149">U moet een globale beheerder zijn in Microsoft 365 om u aan te kunnen.</span><span class="sxs-lookup"><span data-stu-id="58fb4-149">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="58fb4-150">Het kan tot 24 uur duren voordat de onderstaande wijzigingen van kracht worden in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58fb4-150">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="58fb4-151">Als u zich afmeldt nadat u het programma hebt ingeschakeld, hebben uw gebruikers mogelijk geen toegang meer tot functies waarvan de geplande release nog niet beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="58fb4-151">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="58fb4-152">Ga in het beheercentrum naar de **Instellingen** organisatieinstelling en kies onder het profieltabblad Organisatie de optie  >    **Releasevoorkeuren.**</span><span class="sxs-lookup"><span data-stu-id="58fb4-152">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="58fb4-153">Als u gerichte release wilt uitschakelen, selecteert u **Standaardversie** en **selecteert u Vervolgens Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="58fb4-153">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="58fb4-154">Als u een gerichte release wilt inschakelen voor alle gebruikers in uw organisatie, **selecteert** u Targeted release voor iedereen en selecteert u **Vervolgens Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="58fb4-154">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="58fb4-155">Als u gerichte release wilt inschakelen voor sommige personen in uw organisatie, **selecteert** u Targeted release voor geselecteerde gebruikers en selecteert u **Vervolgens Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="58fb4-155">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="58fb4-156">Kies **Gebruikers selecteren** om gebruikers één voor één toe te voegen of kies Upload **gebruikers** om ze bulksgewijs toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="58fb4-156">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="58fb4-157">Wanneer u klaar bent met het toevoegen van gebruikers, selecteert u **Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="58fb4-157">When you're done adding users, select **Save changes**.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="58fb4-158">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="58fb4-158">Next steps</span></span>

<span data-ttu-id="58fb4-159">Ontdek hoe u [berichten beheert](/office365/admin/manage/message-center) in uw [Microsoft 365 berichtencentrum](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) om meldingen te krijgen over toekomstige Microsoft 365 updates en releases.</span><span class="sxs-lookup"><span data-stu-id="58fb4-159">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-content"></a><span data-ttu-id="58fb4-160">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="58fb4-160">Related content</span></span>

<span data-ttu-id="58fb4-161">[Deelnemen aan Office Insider-programma](https://insider.office.com/join/windows) (artikel)</span><span class="sxs-lookup"><span data-stu-id="58fb4-161">[Join the Office Insider Program](https://insider.office.com/join/windows) (article)</span></span>
