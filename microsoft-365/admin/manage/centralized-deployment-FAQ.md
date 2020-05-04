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
search.appverid:
- BCS160
- MET150
- MOE150
description: Bekijk de antwoorden op veelgestelde vragen over gecentraliseerde implementatie vanuit het Microsoft 365-beheercentrum.
ms.openlocfilehash: c389ab07136b8a6e625db9ecfeff514a6899cd7d
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011733"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="84504-103">Veelgestelde vragen over Gecentraliseerde implementatie</span><span class="sxs-lookup"><span data-stu-id="84504-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="84504-104">Gecentraliseerde implementatie is de aanbevolen manier voor een Office 365-beheerder om Office-invoegtoepassing (Word, Excel, PowerPoint en Outlook) te implementeren voor gebruikers en groepen binnen een organisatie, op voorwaarde dat de organisatie voldoet aan alle vereisten voor het gebruik van gecentraliseerde implementatie zoals beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="84504-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="84504-105">Hoe weet ik of mijn organisatie is ingesteld voor gecentraliseerde implementatie?</span><span class="sxs-lookup"><span data-stu-id="84504-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="84504-106">Voor een gecentraliseerde implementatie van invoegtoepassingmoet worden vereist dat gebruikers Microsoft 365 Apps voor ondernemingen gebruiken (en zijn aangemeld bij Office met behulp van hun inloggegevens voor de organisatie) en dat ze Exchange Online-postvakken hebben.</span><span class="sxs-lookup"><span data-stu-id="84504-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="84504-107">Uw abonnementsmap moet zich in Azure Active Directory bevinden of worden gefedereerd.</span><span class="sxs-lookup"><span data-stu-id="84504-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="84504-108">Gecentraliseerde implementatie wordt alleen ondersteund voor online postvakken.</span><span class="sxs-lookup"><span data-stu-id="84504-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="84504-109">Het ondersteunt geen implementatie naar on-premises Exchange-postvakken.</span><span class="sxs-lookup"><span data-stu-id="84504-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>
 
<span data-ttu-id="84504-110">U de [office 365-controlecompatibiliteitscontrole](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker) voor gecentraliseerde implementatie gebruiken om te bepalen of uw abonnement in aanmerking komt.</span><span class="sxs-lookup"><span data-stu-id="84504-110">You can use the [Office 365 Centralized Deployment Compatibility Checker](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="84504-111">Hoe target u invoegtoepassinggebruikerstoewijzingen met gecentraliseerde implementatie?</span><span class="sxs-lookup"><span data-stu-id="84504-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="84504-112">Gecentraliseerde implementatie ondersteunt toewijzingen aan individuele gebruikers, groepen en iedereen in de tenant.</span><span class="sxs-lookup"><span data-stu-id="84504-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="84504-113">Gecentraliseerde implementatie kan worden gebruikt voor gebruikers in groepen of groepen op het hoogste niveau zonder bovenliggende groepen, maar niet voor gebruikers in geneste groepen of groepen met bovenliggende groepen.</span><span class="sxs-lookup"><span data-stu-id="84504-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="84504-114">Gecentraliseerde implementatie maakt ook deel uit van de meeste Azure Active Directory-groepen, waaronder Office 365-groepen, distributielijsten en beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="84504-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="84504-115">Het is beter om groepstoewijzingen te gebruiken in plaats van individuele gebruikerstoewijzing voor eenvoudiger beheer.</span><span class="sxs-lookup"><span data-stu-id="84504-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="84504-116">Zie [Gebruikers- en groepstoewijzingen](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="84504-116">For more details, see [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="84504-117">Hoe lang duurt het voordat invoegingen voor alle gebruikers worden weergegeven?</span><span class="sxs-lookup"><span data-stu-id="84504-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="84504-118">Het kan tot 24 uur duren voordat een invoegtoepassing voor alle gebruikers wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="84504-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="84504-119">Het kan evenveel tijd in beslag nemen voor invoegupdates, wijzigingen vanaf het in- of uitschakelen of invoegingsverwijderingen.</span><span class="sxs-lookup"><span data-stu-id="84504-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="84504-120">Hoe beheer ik als beheerder de toegang van de gebruiker tot invoegingen voor mijn organisatie?</span><span class="sxs-lookup"><span data-stu-id="84504-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="84504-121">Voor eenvoudige implementatie van invoegingen voor gebruikers, groepen of uw hele organisatie, raden we beheerders aan gecentraliseerde implementatie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="84504-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="84504-122">Zie voor meer informatie over het beheren van gebruikerstoegang</span><span class="sxs-lookup"><span data-stu-id="84504-122">For more information about managing user access, see</span></span> </br><span data-ttu-id="84504-123">[Invoegdownloads voorkomen door de Office Store voor alle clients uit te schakelen (behalve Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) en</span><span class="sxs-lookup"><span data-stu-id="84504-123">[Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) and</span></span> </br><span data-ttu-id="84504-124">[Geef de beheerders en gebruikers op die invoegingen voor Outlook kunnen installeren en beheren.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN)</span><span class="sxs-lookup"><span data-stu-id="84504-124">[Specify the administrators and users who can install and manage add-ins for Outlook](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).</span></span>

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="84504-125">Biedt gecentraliseerde implementatie beheerders de flexibiliteit om de implementatiemethode voor Outlook-invoegins te kiezen?</span><span class="sxs-lookup"><span data-stu-id="84504-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="84504-126">Ja.</span><span class="sxs-lookup"><span data-stu-id="84504-126">Yes.</span></span> <span data-ttu-id="84504-127">Gecentraliseerde implementatie biedt beheerders de flexibiliteit om een van de drie implementatiemethoden te kiezen voor Outlook-invoegtoepassing tijdens de invoegtoepassing:</span><span class="sxs-lookup"><span data-stu-id="84504-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="84504-128">**Fixed (Default)**   The inis is automatically ployed to the assigned users, they cannot remove it.</span><span class="sxs-lookup"><span data-stu-id="84504-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="84504-129">**Beschikbaar** Gebruikers kunnen de invoegtoepassing in Outlook installeren door Home > Get More-ins te kiezen > beheerde beheerder.</span><span class="sxs-lookup"><span data-stu-id="84504-129">**Available** Users can install the add-in in Outlook by choosing Home > Get More add-ins > Admin-managed.</span></span>   
 
<span data-ttu-id="84504-130">**Optioneel** De invoegtoepassing wordt automatisch geïmplementeerd voor de toegewezen gebruikers, maar ze kunnen ervoor kiezen om de invoeging te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="84504-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="84504-131">Kunnen beheerders lob-invoegingen (Line-of-Business) bijwerken?</span><span class="sxs-lookup"><span data-stu-id="84504-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="84504-132">Ja.</span><span class="sxs-lookup"><span data-stu-id="84504-132">Yes.</span></span> <span data-ttu-id="84504-133">Beheerders kunnen een nieuw manifestbestand uploaden ter ondersteuning van metagegevenswijzigingen voor door de beheerder geïmplementeerde LOB-invoegingen. De invoegtoepassing wordt bijgewerkt wanneer de Office-toepassingen de volgende keer worden gestart.</span><span class="sxs-lookup"><span data-stu-id="84504-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="84504-134">De webtoepassing kan elk moment worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="84504-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="84504-135">Zie [line-of-business add-in voor](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="84504-135">For more information, see [line-of-business add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="84504-136">Kunnen beheerders invoegtoepassing uitschakelen?</span><span class="sxs-lookup"><span data-stu-id="84504-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="84504-137">Ja.</span><span class="sxs-lookup"><span data-stu-id="84504-137">Yes.</span></span> <span data-ttu-id="84504-138">Beheerders kunnen de invoegingen die ze implementeren voor alle gebruikers vanuit het Microsoft-beheercentrum in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="84504-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="84504-139">Zie [Invoegstatussen voor](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states)meer informatie .</span><span class="sxs-lookup"><span data-stu-id="84504-139">For more information, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="84504-140">Kunnen beheerders invoegfouten verwijderen of verwijderen?</span><span class="sxs-lookup"><span data-stu-id="84504-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="84504-141">Ja.</span><span class="sxs-lookup"><span data-stu-id="84504-141">Yes.</span></span> <span data-ttu-id="84504-142">Beheerders kunnen invoegingen die ze hebben geïmplementeerd voor alle gebruikers verwijderen uit het Microsoft-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="84504-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="84504-143">Zie [De invoegtoepassing verwijderen](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="84504-143">For more information, see [Delete the add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="84504-144">Kunnen beheerders betaalde invoegingen implementeren vanuit de Office Store met behulp van gecentraliseerde implementatie?</span><span class="sxs-lookup"><span data-stu-id="84504-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="84504-145">Nee.</span><span class="sxs-lookup"><span data-stu-id="84504-145">No.</span></span> <span data-ttu-id="84504-146">U op dit moment geen betaalde invoegingen uit de Office Store implementeren met gecentraliseerde implementatie.</span><span class="sxs-lookup"><span data-stu-id="84504-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="84504-147">We raden u aan contact op te nemen met de ISV-ontwikkelaar voor de betaalde invoegtoepassing om een manifestbestand of een URL aan te vragen.</span><span class="sxs-lookup"><span data-stu-id="84504-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="84504-148">De tenantbeheerder kan de invoegtoepassing vervolgens implementeren als EEN LOB-invoegtoepassing met behulp van gecentraliseerde implementatie.</span><span class="sxs-lookup"><span data-stu-id="84504-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="84504-149">Welke beheerdersrol heb ik nodig om invoegingen voor mijn organisatie te beheren?</span><span class="sxs-lookup"><span data-stu-id="84504-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="84504-150">U moet de globale beheerrol hebben om invoegingen te beheren. Als u de persoon bent die uw Microsoft 365 voor Bedrijven-abonnement heeft gekocht, bent u de globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="84504-150">You must have the Global admin role to manage add-ins. If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="84504-151">Uw abonnement wordt geleverd met een reeks beheerdersrollen die u toewijzen aan andere gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="84504-151">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="84504-152">Elke beheerrol wordt toegewezen aan algemene bedrijfsfuncties en geeft mensen in uw organisatie machtigingen om specifieke taken uit te voeren in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="84504-152">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="84504-153">Zie [Beheerdersrollen toewijzen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="84504-153">For more information, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>  