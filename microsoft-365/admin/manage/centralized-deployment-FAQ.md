---
title: Veelgestelde vragen over Gecentraliseerde implementatie
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Bekijk de antwoorden op veelgestelde vragen over gecentraliseerde implementatie vanuit het Microsoft 365-beheercentrum.
ms.openlocfilehash: 06e3b7973a209cdf40446c5a9511713d779373b8
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221833"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="30ea1-103">Veelgestelde vragen over Gecentraliseerde implementatie</span><span class="sxs-lookup"><span data-stu-id="30ea1-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="30ea1-104">Gecentraliseerde implementatie is de aanbevolen manier voor een Office 365-beheerder om Office-invoegingen (Word, Excel, PowerPoint en Outlook) te implementeren voor gebruikers en groepen binnen een organisatie, mits de organisatie voldoet aan alle vereisten voor het gebruik van Gecentraliseerde implementatie, zoals wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="30ea1-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="30ea1-105">Hoe weet ik of mijn organisatie is ingesteld voor gecentraliseerde implementatie?</span><span class="sxs-lookup"><span data-stu-id="30ea1-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="30ea1-106">Gecentraliseerde implementatie van invoegvoegingen vereist dat gebruikers Microsoft 365 Apps voor ondernemingen gebruiken (en zijn aangemeld bij Office met hun organisatieloggegevens) en exchange Online-postvakken hebben.</span><span class="sxs-lookup"><span data-stu-id="30ea1-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="30ea1-107">Uw abonnementslijst moet zich in Azure Active Directory hebben of aan azure hebben ge federated.</span><span class="sxs-lookup"><span data-stu-id="30ea1-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="30ea1-108">Gecentraliseerde implementatie wordt alleen ondersteund voor onlinepostvakken.</span><span class="sxs-lookup"><span data-stu-id="30ea1-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="30ea1-109">De implementatie van on-premises Exchange-postvakken wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="30ea1-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="30ea1-110">U kunt de compatibiliteitscontrole voor gecentraliseerde implementatie gebruiken [](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   om te bepalen of uw abonnement in aanmerking komt.</span><span class="sxs-lookup"><span data-stu-id="30ea1-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="30ea1-111">Hoe doelt u gebruikerstoewijzingen voor invoeggebruik met Gecentraliseerde implementatie?</span><span class="sxs-lookup"><span data-stu-id="30ea1-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="30ea1-112">Gecentraliseerde implementatie ondersteunt opdrachten aan afzonderlijke gebruikers, groepen en iedereen in de tenant.</span><span class="sxs-lookup"><span data-stu-id="30ea1-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="30ea1-113">Gecentraliseerde implementatie kan worden gebruikt voor gebruikers in groepen op het hoogste niveau of groepen zonder bovenliggende groepen, maar niet voor gebruikers in geneste groepen of groepen met bovenliggende groepen.</span><span class="sxs-lookup"><span data-stu-id="30ea1-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="30ea1-114">Gecentraliseerde implementatie maakt ook deel uit van de meeste Azure Active Directory-groepen, waaronder Office 365-groepen, distributielijsten en beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="30ea1-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="30ea1-115">Het is beter om groepentoewijzingen te gebruiken in plaats van afzonderlijke gebruikerstoewijzingen voor eenvoudiger beheer.</span><span class="sxs-lookup"><span data-stu-id="30ea1-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="30ea1-116">Zie Gebruikers- en [groepstoewijzingen voor meer informatie.](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments)</span><span class="sxs-lookup"><span data-stu-id="30ea1-116">For more details, see [User and Group assignments](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="30ea1-117">Hoe lang duurt het voordat invoegvoegingen voor alle gebruikers worden opdagen?</span><span class="sxs-lookup"><span data-stu-id="30ea1-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="30ea1-118">Het kan tot 24 uur duren voordat een invoeging wordt voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="30ea1-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="30ea1-119">Het kan even lang duren voor invoeg-updates, wijzigingen van in- of uitschakelen of verwijderingen van invoegvoegingen.</span><span class="sxs-lookup"><span data-stu-id="30ea1-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="30ea1-120">Hoe beheer ik als beheerder de gebruikerstoegang tot invoegingen voor mijn organisatie?</span><span class="sxs-lookup"><span data-stu-id="30ea1-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="30ea1-121">Voor eenvoudige implementatie van invoegvoegingen voor gebruikers, groepen of voor uw hele organisatie, raden we beheerders aan gecentraliseerde implementatie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="30ea1-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="30ea1-122">Zie voor meer informatie over het beheren van gebruikerstoegang:</span><span class="sxs-lookup"><span data-stu-id="30ea1-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="30ea1-123">Invoegversies voorkomen door de Office Store uit te schakelen voor alle clients (behalve Outlook)</span><span class="sxs-lookup"><span data-stu-id="30ea1-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="30ea1-124">Geef de beheerders en gebruikers op die invoegingen voor Outlook kunnen installeren en beheren</span><span class="sxs-lookup"><span data-stu-id="30ea1-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="30ea1-125">Bieden gecentraliseerde implementatie beheerders de flexibiliteit om de implementatiemethode voor Outlook-invoegvoegingen te kiezen?</span><span class="sxs-lookup"><span data-stu-id="30ea1-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="30ea1-126">Ja.</span><span class="sxs-lookup"><span data-stu-id="30ea1-126">Yes.</span></span> <span data-ttu-id="30ea1-127">Gecentraliseerde implementatie biedt beheerders de flexibiliteit om een van de drie implementatiemethoden voor Outlook-invoegvoegingen te kiezen tijdens de implementatie van de invoegversie:</span><span class="sxs-lookup"><span data-stu-id="30ea1-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="30ea1-128">**Opgelost (standaard)**   De invoegvoegvoeging wordt automatisch geïmplementeerd voor de toegewezen gebruikers en kan niet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="30ea1-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="30ea1-129">**Beschikbaar** Gebruikers kunnen de invoegversie in Outlook installeren door startpagina te kiezen > Meer invoegvoegingen downloaden **> beheerd door de beheerder.**</span><span class="sxs-lookup"><span data-stu-id="30ea1-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="30ea1-130">**Optioneel** De invoegvoegvoeging wordt automatisch geïmplementeerd voor de toegewezen gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="30ea1-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="30ea1-131">Kunnen beheerders lob-invoegvoegingen (Line-of-Business) bijwerken?</span><span class="sxs-lookup"><span data-stu-id="30ea1-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="30ea1-132">Ja.</span><span class="sxs-lookup"><span data-stu-id="30ea1-132">Yes.</span></span> <span data-ttu-id="30ea1-133">Beheerders kunnen een nieuw manifestbestand uploaden ter ondersteuning van metagegevenswijzigingen voor door beheerders geïmplementeerde LOB-invoegingen. De invoegtoepassingen worden bijgewerkt de volgende keer dat de Office-toepassingen worden gestart.</span><span class="sxs-lookup"><span data-stu-id="30ea1-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="30ea1-134">De webtoepassing kan elk moment worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="30ea1-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="30ea1-135">Zie [line-of-business-invoegvoeging voor meer informatie.](./manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="30ea1-135">For more information, see [line-of-business add-in](./manage-addins-in-the-admin-center.md).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="30ea1-136">Kunnen beheerders invoegvoegingen uitschakelen?</span><span class="sxs-lookup"><span data-stu-id="30ea1-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="30ea1-137">Ja.</span><span class="sxs-lookup"><span data-stu-id="30ea1-137">Yes.</span></span> <span data-ttu-id="30ea1-138">Beheerders kunnen de invoegvoegingen die ze voor alle gebruikers implementeren in- of uitschakelen vanuit het Microsoft-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="30ea1-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="30ea1-139">Zie Invoeg staten [voor meer informatie.](./manage-addins-in-the-admin-center.md#add-in-states)</span><span class="sxs-lookup"><span data-stu-id="30ea1-139">For more information, see [Add-in states](./manage-addins-in-the-admin-center.md#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="30ea1-140">Kunnen beheerders invoegingen verwijderen of verwijderen?</span><span class="sxs-lookup"><span data-stu-id="30ea1-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="30ea1-141">Ja.</span><span class="sxs-lookup"><span data-stu-id="30ea1-141">Yes.</span></span> <span data-ttu-id="30ea1-142">Beheerders kunnen invoegingen die ze voor alle gebruikers hebben geïmplementeerd, verwijderen uit het Microsoft-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="30ea1-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="30ea1-143">Zie Een [invoeging verwijderen voor meer informatie.](./manage-addins-in-the-admin-center.md#delete-an-add-in)</span><span class="sxs-lookup"><span data-stu-id="30ea1-143">For more information, see [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="30ea1-144">Kunnen beheerders betaalde invoegvoegingen implementeren vanuit de Office Store met gecentraliseerde implementatie?</span><span class="sxs-lookup"><span data-stu-id="30ea1-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="30ea1-145">Nee.</span><span class="sxs-lookup"><span data-stu-id="30ea1-145">No.</span></span> <span data-ttu-id="30ea1-146">U kunt op dit moment geen betaalde invoegvoegingen vanuit de Office Store implementeren met gecentraliseerde implementatie.</span><span class="sxs-lookup"><span data-stu-id="30ea1-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="30ea1-147">We raden u aan contact op te zoeken met de isv-ontwikkelaar voor de betaalde invoegvoeging om een manifestbestand of een URL aan te vragen.</span><span class="sxs-lookup"><span data-stu-id="30ea1-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="30ea1-148">De tenantbeheerder kan de invoegvoeging vervolgens implementeren als een LOB-invoegvoeging met gecentraliseerde implementatie.</span><span class="sxs-lookup"><span data-stu-id="30ea1-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="30ea1-149">Welke beheerdersrol heb ik nodig om invoegingen voor mijn organisatie te beheren?</span><span class="sxs-lookup"><span data-stu-id="30ea1-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="30ea1-150">Globale beheerder is de aanbevolen rol met volledige toegang tot de levenscyclus van het invoegbeheer.</span><span class="sxs-lookup"><span data-stu-id="30ea1-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="30ea1-151">Andere beheerdersrollen hebben beperkte toegang tot de levenscyclus van de invoegfase.</span><span class="sxs-lookup"><span data-stu-id="30ea1-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="30ea1-152">Als u de persoon bent die uw Microsoft 365 voor Bedrijven-abonnement heeft gekocht, bent u de globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="30ea1-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="30ea1-153">Uw abonnement wordt geleverd met een set beheerdersrollen die u kunt toewijzen aan andere gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="30ea1-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="30ea1-154">Elke beheerdersrol wordt toekend aan algemene zakelijke functies en geeft personen in uw organisatie machtigingen om specifieke taken uit te voeren in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="30ea1-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="30ea1-155">Zie Beheerdersrollen toewijzen voor [meer informatie.](../add-users/assign-admin-roles.md?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="30ea1-155">For more information, see [Assign admin roles](../add-users/assign-admin-roles.md?view=o365-worldwide).</span></span> 