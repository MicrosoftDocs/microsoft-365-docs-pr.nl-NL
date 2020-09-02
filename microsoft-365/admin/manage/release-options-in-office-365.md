---
title: De Standard-of targeted release-opties instellen
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
description: Meer informatie over het instellen van de release optie voor nieuwe updates van producten en onderdelen in het Microsoft 365-Beheercentrum.
ms.openlocfilehash: 110cefa646f7c42c6979a97ca617b015a100866e
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324534"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="d7994-103">De Standard-of targeted release-opties instellen</span><span class="sxs-lookup"><span data-stu-id="d7994-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d7994-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d7994-104">The admin center is changing.</span></span> <span data-ttu-id="d7994-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="d7994-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

> [!IMPORTANT]
> <span data-ttu-id="d7994-106">De Microsoft 365-updates die in dit artikel worden beschreven, zijn van toepassing op Microsoft 365, SharePoint Online en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d7994-106">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="d7994-107">Deze release opties zijn bedoeld en best effort manieren om wijzigingen aan te brengen in Microsoft 365, maar kunnen op elk moment niet worden gegarandeerd of voor alle updates.</span><span class="sxs-lookup"><span data-stu-id="d7994-107">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="d7994-108">Ze zijn niet van toepassing op Microsoft 365-apps, Skype voor bedrijven, Microsoft teams en gerelateerde services.</span><span class="sxs-lookup"><span data-stu-id="d7994-108">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="d7994-109">Zie [overzicht van update kanalen voor Microsoft 365-apps](https://docs.microsoft.com/deployoffice/overview-update-channels)voor meer informatie over release opties voor microsoft 365-apps.</span><span class="sxs-lookup"><span data-stu-id="d7994-109">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="d7994-110">Met Microsoft 365 ontvangt u nieuwe productupdates en-functies wanneer deze beschikbaar komen, in plaats van dat u elk paar jaar kosten hoeft te worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="d7994-110">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="d7994-111">U kunt beheren hoe uw organisatie deze updates ontvangt.</span><span class="sxs-lookup"><span data-stu-id="d7994-111">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="d7994-112">U kunt u bijvoorbeeld registreren voor een vroege release, zodat uw organisatie updates als eerste ontvangt.</span><span class="sxs-lookup"><span data-stu-id="d7994-112">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="d7994-113">U kunt bepaalde personen aanwijzen die als enigen de updates ontvangen.</span><span class="sxs-lookup"><span data-stu-id="d7994-113">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="d7994-114">Of u blijft het standaardreleaseschema volgen en ontvangt de updates later.</span><span class="sxs-lookup"><span data-stu-id="d7994-114">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="d7994-115">In dit artikel worden de verschillende versies beschreven en wordt uitgelegd hoe u deze kunt gebruiken voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d7994-115">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="d7994-116">Hoe het werkt: validatie van releases</span><span class="sxs-lookup"><span data-stu-id="d7994-116">How it works - release validation</span></span>

<span data-ttu-id="d7994-117">Een nieuwe release wordt eerst getest en gevalideerd door het team van functies, vervolgens door het volledige Microsoft 365-onderdelen team, gevolgd door alle Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d7994-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="d7994-118">Na intern testen en valideren bestaat de volgende stap uit een **Targeted Release** (eerder bekend als First Release) voor klanten die zich aanmelden.</span><span class="sxs-lookup"><span data-stu-id="d7994-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="d7994-119">Bij elke release-ring verzamelt Microsoft feedback en valideert de kwaliteit verder door belangrijke gebruiksgegevens te controleren.</span><span class="sxs-lookup"><span data-stu-id="d7994-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="d7994-120">Deze reeks van toenemende validatie is ingesteld om er voor te zorgen dat de mondiale release zo robuust mogelijk is.</span><span class="sxs-lookup"><span data-stu-id="d7994-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="d7994-121">De releases worden in de volgende afbeelding geïllustreerd.</span><span class="sxs-lookup"><span data-stu-id="d7994-121">The releases are pictured in the following figure.</span></span> 
  
![Release validatie belsignalen voor Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="d7994-123">Voor belangrijke updates worden klanten in eerste instantie op de hoogte gesteld van het [Microsoft 365-wegwijzer](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="d7994-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="d7994-124">Aangezien een update dichter bij de IT komt, wordt deze gecommuniceerd via uw [Microsoft 365 berichtencentrum](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span><span class="sxs-lookup"><span data-stu-id="d7994-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="d7994-125">U hebt een Microsoft 365-of Azure AD-account nodig om toegang te krijgen tot uw Berichtencentrum via het [Beheercentrum](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="d7994-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="d7994-126">Microsoft 365 Home-abonnement gebruikers hebben geen Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d7994-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="d7994-127">Standard Release</span><span class="sxs-lookup"><span data-stu-id="d7994-127">Standard release</span></span>

<span data-ttu-id="d7994-128">Dit is de standaardoptie waarbij u en uw gebruikers de nieuwste updates ontvangen wanneer deze algemeen beschikbaar worden voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="d7994-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="d7994-129">Het is een goede gewoonte om het merendeel van de gebruikers in de **standaardrelease** en IT-professionals en gevorderde gebruikers in **target** te laten gaan door nieuwe functies te evalueren en teams voor te bereiden voor de ondersteuning van zakelijke gebruikers en leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="d7994-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d7994-130">Als u van het First Release-programma teruggaat naar het Standard Release-programma, hebben uw gebruikers mogelijk geen toegang meer tot functies die nog niet zijn opgenomen in het Standard Release-programma.</span><span class="sxs-lookup"><span data-stu-id="d7994-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="d7994-131">Targeted Release</span><span class="sxs-lookup"><span data-stu-id="d7994-131">Targeted release</span></span>

<span data-ttu-id="d7994-p107">Met deze optie zien u en uw gebruikers als eersten de nieuwste updates en kunt u helpen het product te vormen door vroege feedback te geven. U kunt bepalen of de vroege updates naar afzonderlijke personen of naar de hele organisatie worden gestuurd.</span><span class="sxs-lookup"><span data-stu-id="d7994-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d7994-p108">Bij grote of complexe updates duurt dit mogelijk langer dan bij andere updates zodat er geen gebruikers negatief worden beïnvloed. De exacte tijdlijn van een release kan niet worden gegarandeerd.</span><span class="sxs-lookup"><span data-stu-id="d7994-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="d7994-136">Targeted Release voor de hele organisatie</span><span class="sxs-lookup"><span data-stu-id="d7994-136">Targeted release for entire organization</span></span>

<span data-ttu-id="d7994-137">Als u [de release optie in het Beheercentrum instelt](#set-up-the-release-option-in-the-admin-center) voor deze optie, krijgen alle gebruikers de gerichte release-ervaring.</span><span class="sxs-lookup"><span data-stu-id="d7994-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="d7994-138">Voor organisaties met meer dan 300 gebruikers wordt een testabonnement op deze optie aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="d7994-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="d7994-139">Neem contact op met uw Microsoft-contactpersoon voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d7994-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="d7994-140">Targeted Release voor specifieke gebruikers</span><span class="sxs-lookup"><span data-stu-id="d7994-140">Targeted release for selected users</span></span>

<span data-ttu-id="d7994-141">Als u [de release optie in het Beheercentrum instelt](#set-up-the-release-option-in-the-admin-center) voor deze optie, kunt u bepaalde gebruikers definiëren, gewoonlijk Hoofdgebruikers, die vroegtijdig toegang krijgen tot functies en functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="d7994-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="d7994-142">Voordelen van Targeted Release</span><span class="sxs-lookup"><span data-stu-id="d7994-142">Benefits of Targeted release</span></span>

<span data-ttu-id="d7994-143">Targeted release dit kan beheerders, beheerders wijzigen of andere verantwoordelijke voor Microsoft 365-updates voorbereidingen treffen voor het aanstellen van de komende wijzigingen door ze te laten doen:</span><span class="sxs-lookup"><span data-stu-id="d7994-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="d7994-144">Nieuwe updates testen en valideren voordat deze worden uitgebracht voor alle gebruikers in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="d7994-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="d7994-145">Meldingen en documentatie voor gebruikers voorbereiden voordat de updates mondiaal worden uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="d7994-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="d7994-146">Een interne helpdesk in verband met aanstaande updates voorbereiden</span><span class="sxs-lookup"><span data-stu-id="d7994-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="d7994-147">Beoordelingen betreffende naleving en beveiliging doornemen.</span><span class="sxs-lookup"><span data-stu-id="d7994-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="d7994-148">Besturingselementen voor functies gebruiken om de uitgifte van updates voor eindgebruikers te reguleren.</span><span class="sxs-lookup"><span data-stu-id="d7994-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="d7994-149">De release optie instellen in het Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="d7994-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="d7994-150">U kunt wijzigen hoe uw organisatie Microsoft 365-updates ontvangt door de volgende stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d7994-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="d7994-151">U moet een globale beheerder in Microsoft 365 zijn om u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="d7994-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d7994-152">Het kan tot 24 uur duren voordat de volgende wijzigingen zijn doorgevoerd in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d7994-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="d7994-153">Als u zich afmeldt nadat u het programma hebt ingeschakeld, hebben uw gebruikers mogelijk geen toegang meer tot functies waarvan de geplande release nog niet beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="d7994-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="d7994-154">Ga in het Beheercentrum naar **instellingen**  >  **organisatie**en kies onder het tabblad **organisatieprofiel** de optie **release voorkeuren**.</span><span class="sxs-lookup"><span data-stu-id="d7994-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="d7994-155">Als u targeted release wilt uitschakelen, selecteert u **Standard release**en selecteert u **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="d7994-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="d7994-156">Als u de targeted release wilt inschakelen voor alle gebruikers in uw organisatie, selecteert u **targeted release voor iedereen**en selecteert u **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="d7994-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="d7994-157">Als u de targeted release wilt inschakelen voor sommige personen in de organisatie, selecteert u **targeted release voor geselecteerde gebruikers**en selecteert u vervolgens **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="d7994-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="d7994-158">Kies **gebruikers selecteren** om gebruikers één voor één toe te voegen of om **gebruikers** tegelijk toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="d7994-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="d7994-159">Wanneer u klaar bent met het toevoegen van gebruikers, selecteert u **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="d7994-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="d7994-160">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="d7994-160">Learn more</span></span>

<span data-ttu-id="d7994-161">Ontdek hoe u [berichten kunt beheren](https://docs.microsoft.com/office365/admin/manage/message-center) in uw [Microsoft 365 berichtencentrum](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) voor meldingen over toekomstige updates en versies van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d7994-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
