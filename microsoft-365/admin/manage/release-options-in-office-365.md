---
title: De Standard Release- of Targeted Release-opties in Office 365 instellen
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Meer informatie over het instellen van de releaseoptie voor nieuwe product- en functies-updates in het Microsoft 365-beheercentrum.
ms.openlocfilehash: d6c2eab340f4401fb31e4d9e814fbd326573569a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42806930"
---
# <a name="set-up-the-standard-or-targeted-release-options-in-office-365"></a><span data-ttu-id="7aa24-103">De Standard Release- of Targeted Release-opties in Office 365 instellen</span><span class="sxs-lookup"><span data-stu-id="7aa24-103">Set up the Standard or Targeted release options in Office 365</span></span>

<span data-ttu-id="7aa24-p101">Met Office 365 ontvangt u nieuwe productupdates en functies zodra deze beschikbaar zijn, in plaats van dat u om de paar jaar dure updates moet uitvoeren. U kunt beheren hoe uw organisatie deze updates ontvangt. U kunt u bijvoorbeeld registreren voor een vroege release, zodat uw organisatie updates als eerste ontvangt. U kunt bepaalde personen aanwijzen die als enigen de updates ontvangen. Of u blijft het standaardreleaseschema volgen en ontvangt de updates later. In dit artikel worden de verschillende releaseopties besproken en wordt uitgelegd hoe u deze kunt gebruiken voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7aa24-p101">With Office 365, you receive new product updates and features as they become available instead of doing costly updates every few years. You can manage how your organization receives these updates. For example, you can sign up for an early release so that your organization receives updates first. You can designate that only certain individuals receive the updates. Or, you can remain on the default release schedule and receive the updates later. This article explain the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7aa24-p102">De Office 365-updates die in dit artikel worden beschreven, zijn van toepassing op Office 365, SharePoint Online en Exchange Online. Ze zijn niet van toepassing op Skype voor Bedrijven en gerelateerde services. Deze releaseopties zijn doelgerichte methoden om wijzigingen in Office 365 vrij te geven. We kunnen echter niet garanderen dat deze opties altijd voor alle updates beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="7aa24-p102">The Office 365 updates described in this article apply to Office 365, SharePoint Online, and Exchange Online. They do not apply to Skype for Business and related services. These release options are targeted, best effort ways to release changes to Office 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="7aa24-113">Hoe het werkt: validatie van releases</span><span class="sxs-lookup"><span data-stu-id="7aa24-113">How it works - release validation</span></span>

<span data-ttu-id="7aa24-114">Elke nieuwe release wordt eerst getest en gevalideerd door het functieteam, vervolgens door het hele Office 365-functieteam, gevolgd door heel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7aa24-114">Any new release is first tested and validated by the feature team, then by the entire Office 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="7aa24-115">Na intern testen en valideren bestaat de volgende stap uit een **Targeted Release** (eerder bekend als First Release) voor klanten die zich aanmelden.</span><span class="sxs-lookup"><span data-stu-id="7aa24-115">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="7aa24-116">Bij elke release-ring verzamelt Microsoft feedback en valideert de kwaliteit verder door belangrijke gebruiksgegevens te controleren.</span><span class="sxs-lookup"><span data-stu-id="7aa24-116">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="7aa24-117">Deze reeks van toenemende validatie is ingesteld om er voor te zorgen dat de mondiale release zo robuust mogelijk is.</span><span class="sxs-lookup"><span data-stu-id="7aa24-117">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="7aa24-118">De releases worden in de volgende afbeelding geïllustreerd.</span><span class="sxs-lookup"><span data-stu-id="7aa24-118">The releases are pictured in the following figure.</span></span> 
  
![Validatieringen voor Office 365 vrijgeven](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="7aa24-120">Voor belangrijke updates worden Office-klanten in eerste instantie op de hoogte gebracht door de [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="7aa24-120">For significant updates, Office customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="7aa24-121">Naarmate een update dichter bij de uitrol komt, wordt deze gecommuniceerd via uw [Office 365-berichtencentrum.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="7aa24-121">As an update gets closer to rolling out, it is communicated through your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="7aa24-122">U hebt een Office 365- of Azure AD-account nodig om toegang te krijgen tot uw berichtencentrum via het [beheercentrum.](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="7aa24-122">You need an Office 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="7aa24-123">Gebruikers van office 365-thuisplannen hebben geen beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="7aa24-123">Office 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="7aa24-124">Standard Release</span><span class="sxs-lookup"><span data-stu-id="7aa24-124">Standard release</span></span>

<span data-ttu-id="7aa24-125">Dit is de standaardoptie waarbij u en uw gebruikers de nieuwste updates ontvangen wanneer ze breed worden vrijgegeven aan alle klanten.</span><span class="sxs-lookup"><span data-stu-id="7aa24-125">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="7aa24-126">Een goede praktijk is om de meerderheid van de gebruikers te verlaten in **Standaard release** en IT-pro's en power users in **Targeted release** om nieuwe functies te evalueren en teams voor te bereiden om zakelijke gebruikers en leidinggevenden te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="7aa24-126">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7aa24-127">Als u van het First Release-programma teruggaat naar het Standard Release-programma, hebben uw gebruikers mogelijk geen toegang meer tot functies die nog niet zijn opgenomen in het Standard Release-programma.</span><span class="sxs-lookup"><span data-stu-id="7aa24-127">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="7aa24-128">Targeted Release</span><span class="sxs-lookup"><span data-stu-id="7aa24-128">Targeted release</span></span>

<span data-ttu-id="7aa24-p106">Met deze optie zien u en uw gebruikers als eersten de nieuwste updates en kunt u helpen het product te vormen door vroege feedback te geven. U kunt bepalen of de vroege updates naar afzonderlijke personen of naar de hele organisatie worden gestuurd.</span><span class="sxs-lookup"><span data-stu-id="7aa24-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7aa24-p107">Bij grote of complexe updates duurt dit mogelijk langer dan bij andere updates zodat er geen gebruikers negatief worden beïnvloed. De exacte tijdlijn van een release kan niet worden gegarandeerd.</span><span class="sxs-lookup"><span data-stu-id="7aa24-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="7aa24-133">Targeted Release voor de hele organisatie</span><span class="sxs-lookup"><span data-stu-id="7aa24-133">Targeted release for entire organization</span></span>

<span data-ttu-id="7aa24-134">Als u [de releaseoptie in stelt in het beheercentrum](#set-up-the-release-option-in-the-admin-center) voor deze optie, krijgen al uw gebruikers de gerichte release-ervaring.</span><span class="sxs-lookup"><span data-stu-id="7aa24-134">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="7aa24-135">Voor organisaties met meer dan 300 gebruikers wordt een testabonnement op deze optie aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="7aa24-135">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="7aa24-136">Neem contact op met uw Microsoft-contactpersoon voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7aa24-136">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="7aa24-137">Targeted Release voor specifieke gebruikers</span><span class="sxs-lookup"><span data-stu-id="7aa24-137">Targeted release for selected users</span></span>

<span data-ttu-id="7aa24-138">Als u [de releaseoptie in stelt in het beheercentrum](#set-up-the-release-option-in-the-admin-center) voor deze optie, u specifieke gebruikers definiëren, meestal power users, om vroege toegang tot functies en functionaliteit te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="7aa24-138">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="7aa24-139">Voordelen van Targeted Release</span><span class="sxs-lookup"><span data-stu-id="7aa24-139">Benefits of Targeted release</span></span>

<span data-ttu-id="7aa24-140">Met Targeted Release kunnen beheerders, wijzigingsbeheerders of anderen die verantwoordelijk zijn voor Office 365-updates zich voorbereiden op aanstaande wijzigingen. Hierdoor kunnen ze:</span><span class="sxs-lookup"><span data-stu-id="7aa24-140">Targeted release allows admins, change managers, or anyone else responsible for Office 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="7aa24-141">Nieuwe updates testen en valideren voordat deze worden uitgebracht voor alle gebruikers in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="7aa24-141">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="7aa24-142">Meldingen en documentatie voor gebruikers voorbereiden voordat de updates mondiaal worden uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="7aa24-142">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="7aa24-143">Een interne helpdesk in verband met aanstaande updates voorbereiden</span><span class="sxs-lookup"><span data-stu-id="7aa24-143">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="7aa24-144">Beoordelingen betreffende naleving en beveiliging doornemen.</span><span class="sxs-lookup"><span data-stu-id="7aa24-144">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="7aa24-145">Besturingselementen voor functies gebruiken om de uitgifte van updates voor eindgebruikers te reguleren.</span><span class="sxs-lookup"><span data-stu-id="7aa24-145">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="7aa24-146">De releaseoptie instellen in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="7aa24-146">Set up the release option in the admin center</span></span>

<span data-ttu-id="7aa24-p109">U kunt wijzigen hoe uw organisatie Office 365-updates ontvangt door de volgende stappen uit te voeren. U moet een globale beheerder zijn voor Office 365 om u te kunnen aanmelden.</span><span class="sxs-lookup"><span data-stu-id="7aa24-p109">You can change how your organization receives Office 365 updates by following these steps. You have to be a global admin in Office 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7aa24-p110">Het duurt maximaal 24 uur voor de onderstaande wijzigingen zijn doorgevoerd in Office 365. Als u zich afmeldt nadat u het programma hebt ingeschakeld, hebben uw gebruikers mogelijk geen toegang meer tot functies waarvan de geplande release nog niet beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="7aa24-p110">It can take up to 24 hours for the below changes to take effect in Office 365. If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="7aa24-151">Ga in het beheercentrum naar de**instelling** **Instellingen** > en kies onder het tabblad **Organisatieprofiel** **de voorkeuren vrijgeven**.</span><span class="sxs-lookup"><span data-stu-id="7aa24-151">In the admin center, go to the **Settings** > **Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="7aa24-152">Als u de gerichte release wilt uitschakelen, selecteert u **Standaardrelease**en selecteert u **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7aa24-152">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="7aa24-153">Als u gerichte release wilt inschakelen voor alle gebruikers in uw organisatie, selecteert u **Gerichte release voor iedereen**en selecteert u Wijzigingen **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="7aa24-153">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="7aa24-154">Als u gerichte release wilt inschakelen voor sommige mensen in uw organisatie, selecteert u **Gerichte release voor geselecteerde gebruikers**en selecteert u Wijzigingen **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7aa24-154">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="7aa24-155">Kies **Gebruikers selecteren** om gebruikers één voor één toe te voegen of Gebruikers **uploaden** om ze in bulk toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="7aa24-155">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="7aa24-156">Wanneer u klaar bent met het toevoegen van gebruikers, selecteert u **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7aa24-156">When you're done adding users, select **Save changes**.</span></span>



## <a name="get-the-targeted-release-version-of-office"></a><span data-ttu-id="7aa24-157">De beoogde versie van Office weergeven</span><span class="sxs-lookup"><span data-stu-id="7aa24-157">Get the Targeted release version of Office</span></span>

<span data-ttu-id="7aa24-p111">Als u een Targeted Release-versie van Office wilt installeren, [volgt u deze stappen](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). Zo krijgt u vroegtijdige toegang tot de nieuwe functies van Office 2016 voor Windows-desktopcomputers.</span><span class="sxs-lookup"><span data-stu-id="7aa24-p111">To install a targeted release build of Office, [follow these steps](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). This gives you early access to the new features of Office 2016 for Windows desktops.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="7aa24-160">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="7aa24-160">Learn more</span></span>

<span data-ttu-id="7aa24-161">Ontdek hoe u [berichten beheert](https://docs.microsoft.com/office365/admin/manage/message-center) in uw [Office 365-berichtencentrum](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) om meldingen te ontvangen over aankomende Office 365-updates en -releases.</span><span class="sxs-lookup"><span data-stu-id="7aa24-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Office 365 updates and releases.</span></span>
