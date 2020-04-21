---
title: De standaard- of gerichte releaseopties instellen
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
description: Meer informatie over het instellen van de releaseoptie voor nieuwe product- en functiesupdates in het Microsoft 365-beheercentrum.
ms.openlocfilehash: 11672e46acb3124c8fd840ab19ee683cfd6af94f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628110"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="1e4b4-103">De standaard- of gerichte releaseopties instellen</span><span class="sxs-lookup"><span data-stu-id="1e4b4-103">Set up the Standard or Targeted release options</span></span>

<span data-ttu-id="1e4b4-104">Met Microsoft 365 ontvangt u nieuwe productupdates en -functies zodra deze beschikbaar zijn in plaats van om de paar jaar dure updates uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-104">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="1e4b4-105">U kunt beheren hoe uw organisatie deze updates ontvangt.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-105">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="1e4b4-106">U kunt u bijvoorbeeld registreren voor een vroege release, zodat uw organisatie updates als eerste ontvangt.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-106">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="1e4b4-107">U kunt bepaalde personen aanwijzen die als enigen de updates ontvangen.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-107">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="1e4b4-108">Of u blijft het standaardreleaseschema volgen en ontvangt de updates later.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-108">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="1e4b4-109">In dit artikel worden de verschillende releaseopties besproken en wordt uitgelegd hoe u deze kunt gebruiken voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-109">This article explain the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1e4b4-110">De in dit artikel beschreven Microsoft 365-updates zijn van toepassing op Microsoft 365, SharePoint Online en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-110">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="1e4b4-111">Ze zijn niet van toepassing op Skype voor Bedrijven en gerelateerde services.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-111">They do not apply to Skype for Business and related services.</span></span> <span data-ttu-id="1e4b4-112">Deze release opties zijn gericht, best effort manieren om wijzigingen in Microsoft 365 release, maar kan niet worden gegarandeerd te allen tijde of voor alle updates.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-112">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="1e4b4-113">Hoe het werkt: validatie van releases</span><span class="sxs-lookup"><span data-stu-id="1e4b4-113">How it works - release validation</span></span>

<span data-ttu-id="1e4b4-114">Elke nieuwe release wordt eerst getest en gevalideerd door het featureteam, vervolgens door het hele Microsoft 365-functieteam, gevolgd door heel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-114">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="1e4b4-115">Na intern testen en valideren bestaat de volgende stap uit een **Targeted Release** (eerder bekend als First Release) voor klanten die zich aanmelden.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-115">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="1e4b4-116">Bij elke release-ring verzamelt Microsoft feedback en valideert de kwaliteit verder door belangrijke gebruiksgegevens te controleren.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-116">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="1e4b4-117">Deze reeks van toenemende validatie is ingesteld om er voor te zorgen dat de mondiale release zo robuust mogelijk is.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-117">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="1e4b4-118">De releases worden in de volgende afbeelding geïllustreerd.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-118">The releases are pictured in the following figure.</span></span> 
  
![Validatieringen vrijgeven voor Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="1e4b4-120">Voor belangrijke updates worden Office-klanten in eerste instantie op de hoogte gebracht door de [Microsoft 365 Roadmap.](https://products.office.com/business/office-365-roadmap)</span><span class="sxs-lookup"><span data-stu-id="1e4b4-120">For significant updates, Office customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="1e4b4-121">Naarmate een update dichter bij de uitrol komt, wordt deze gecommuniceerd via uw [Microsoft 365 Message Center.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="1e4b4-121">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="1e4b4-122">U hebt een Microsoft 365- of Azure AD-account nodig om toegang te krijgen tot uw Berichtencentrum via het [beheercentrum.](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="1e4b4-122">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="1e4b4-123">Microsoft 365 home plan gebruikers hebben geen admin center.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-123">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="1e4b4-124">Standard Release</span><span class="sxs-lookup"><span data-stu-id="1e4b4-124">Standard release</span></span>

<span data-ttu-id="1e4b4-125">Dit is de standaardoptie waarbij u en uw gebruikers de nieuwste updates ontvangen wanneer ze breed worden uitgebracht voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-125">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="1e4b4-126">Een goede gewoonte is om de meerderheid van de gebruikers in **Standard release** en IT-professionals en power users in **Targeted release** om nieuwe functies te evalueren en teams voor te bereiden op zakelijke gebruikers en leidinggevenden te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-126">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1e4b4-127">Als u van het First Release-programma teruggaat naar het Standard Release-programma, hebben uw gebruikers mogelijk geen toegang meer tot functies die nog niet zijn opgenomen in het Standard Release-programma.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-127">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="1e4b4-128">Targeted Release</span><span class="sxs-lookup"><span data-stu-id="1e4b4-128">Targeted release</span></span>

<span data-ttu-id="1e4b4-p106">Met deze optie zien u en uw gebruikers als eersten de nieuwste updates en kunt u helpen het product te vormen door vroege feedback te geven. U kunt bepalen of de vroege updates naar afzonderlijke personen of naar de hele organisatie worden gestuurd.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1e4b4-p107">Bij grote of complexe updates duurt dit mogelijk langer dan bij andere updates zodat er geen gebruikers negatief worden beïnvloed. De exacte tijdlijn van een release kan niet worden gegarandeerd.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="1e4b4-133">Targeted Release voor de hele organisatie</span><span class="sxs-lookup"><span data-stu-id="1e4b4-133">Targeted release for entire organization</span></span>

<span data-ttu-id="1e4b4-134">Als u [de releaseoptie instelt in het beheercentrum](#set-up-the-release-option-in-the-admin-center) voor deze optie, krijgen al uw gebruikers de gerichte release-ervaring.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-134">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="1e4b4-135">Voor organisaties met meer dan 300 gebruikers wordt een testabonnement op deze optie aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-135">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="1e4b4-136">Neem contact op met uw Microsoft-contactpersoon voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-136">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="1e4b4-137">Targeted Release voor specifieke gebruikers</span><span class="sxs-lookup"><span data-stu-id="1e4b4-137">Targeted release for selected users</span></span>

<span data-ttu-id="1e4b4-138">Als u [de releaseoptie inhet beheercentrum](#set-up-the-release-option-in-the-admin-center) voor deze optie instelt, u specifieke gebruikers, meestal powerusers, definiëren om vroege toegang tot functies en functionaliteit te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-138">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="1e4b4-139">Voordelen van Targeted Release</span><span class="sxs-lookup"><span data-stu-id="1e4b4-139">Benefits of Targeted release</span></span>

<span data-ttu-id="1e4b4-140">Met gerichte release kunnen beheerders, wijzigingsmanagers of iemand anders die verantwoordelijk is voor Microsoft 365-updates zich voorbereiden op de komende wijzigingen door ze te laten zien:</span><span class="sxs-lookup"><span data-stu-id="1e4b4-140">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="1e4b4-141">Nieuwe updates testen en valideren voordat deze worden uitgebracht voor alle gebruikers in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-141">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="1e4b4-142">Meldingen en documentatie voor gebruikers voorbereiden voordat de updates mondiaal worden uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-142">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="1e4b4-143">Een interne helpdesk in verband met aanstaande updates voorbereiden</span><span class="sxs-lookup"><span data-stu-id="1e4b4-143">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="1e4b4-144">Beoordelingen betreffende naleving en beveiliging doornemen.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-144">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="1e4b4-145">Besturingselementen voor functies gebruiken om de uitgifte van updates voor eindgebruikers te reguleren.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-145">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="1e4b4-146">De releaseoptie instellen in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="1e4b4-146">Set up the release option in the admin center</span></span>

<span data-ttu-id="1e4b4-147">U de manier wijzigen waarop uw organisatie Microsoft 365-updates ontvangt door deze stappen te volgen.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-147">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="1e4b4-148">Je moet een globale beheerder in Microsoft 365 zijn om je aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-148">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1e4b4-149">Het kan tot 24 uur duren voordat de onderstaande wijzigingen van kracht worden in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-149">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="1e4b4-150">Als u zich afmeldt nadat u het programma hebt ingeschakeld, hebben uw gebruikers mogelijk geen toegang meer tot functies waarvan de geplande release nog niet beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-150">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="1e4b4-151">Ga in het beheercentrum naar de > **instellingeninstelling**en kies onder het tabblad **Organisatieprofiel** de **optie Voorkeuren vrijgeven**. **Settings**</span><span class="sxs-lookup"><span data-stu-id="1e4b4-151">In the admin center, go to the **Settings** > **Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="1e4b4-152">Als u gerichte release wilt uitschakelen, selecteert u **Standaardrelease**en selecteert u **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-152">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="1e4b4-153">Als u gerichte release wilt inschakelen voor alle gebruikers in uw organisatie, selecteert u **Gerichte release voor iedereen**en selecteert u Wijzigingen **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-153">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="1e4b4-154">Als u gerichte release voor sommige mensen in uw organisatie wilt inschakelen, selecteert u **Gerichte release voor geselecteerde gebruikers**en selecteert u Wijzigingen **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-154">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="1e4b4-155">Kies **Gebruikers selecteren** om gebruikers één voor één toe te voegen of Gebruikers **uploaden** om ze in bulk toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-155">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="1e4b4-156">Wanneer u klaar bent met het toevoegen van gebruikers, selecteert u **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-156">When you're done adding users, select **Save changes**.</span></span>



## <a name="get-the-targeted-release-version-of-office"></a><span data-ttu-id="1e4b4-157">De gerichte releaseversie van Office krijgen</span><span class="sxs-lookup"><span data-stu-id="1e4b4-157">Get the Targeted release version of Office</span></span>

<span data-ttu-id="1e4b4-p111">Als u een Targeted Release-versie van Office wilt installeren, [volgt u deze stappen](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). Zo krijgt u vroegtijdige toegang tot de nieuwe functies van Office 2016 voor Windows-desktopcomputers.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-p111">To install a targeted release build of Office, [follow these steps](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). This gives you early access to the new features of Office 2016 for Windows desktops.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="1e4b4-160">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="1e4b4-160">Learn more</span></span>

<span data-ttu-id="1e4b4-161">Ontdek hoe u [berichten beheert](https://docs.microsoft.com/office365/admin/manage/message-center) in uw [Microsoft 365-berichtencentrum](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) om meldingen te ontvangen over aankomende Microsoft 365-updates en -releases.</span><span class="sxs-lookup"><span data-stu-id="1e4b4-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
