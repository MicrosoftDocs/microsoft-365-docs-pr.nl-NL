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
description: Bekijk de antwoorden op veelgestelde vragen over gecentraliseerde implementatie in het Microsoft 365-Beheercentrum.
ms.openlocfilehash: 555496f15663b6607ebc785498bdc94b5e51b9c9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948686"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="54d69-103">Veelgestelde vragen over Gecentraliseerde implementatie</span><span class="sxs-lookup"><span data-stu-id="54d69-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="54d69-104">Gecentraliseerde implementatie is de aanbevolen manier voor een Office 365-beheerder om Office-invoegtoepassingen (Word, Excel, PowerPoint en Outlook) te implementeren voor gebruikers en groepen binnen een organisatie, mits de organisatie voldoet aan alle vereisten voor het gebruik van gecentraliseerde implementatie zoals in dit artikel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="54d69-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="54d69-105">Hoe weet ik of mijn organisatie is geconfigureerd voor gecentraliseerde implementatie?</span><span class="sxs-lookup"><span data-stu-id="54d69-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="54d69-106">Gecentraliseerde implementatie van invoegtoepassingen vereist dat gebruikers Microsoft 365-apps gebruiken voor Enterprise (en zijn aangemeld bij Office met hun organisatie inlog referenties) en Exchange Online-postvakken hebben.</span><span class="sxs-lookup"><span data-stu-id="54d69-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="54d69-107">Uw abonnements gids moet zich in de map bevinden, of federatief, Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="54d69-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="54d69-108">Gecentraliseerde implementatie wordt alleen ondersteund voor Online postvakken.</span><span class="sxs-lookup"><span data-stu-id="54d69-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="54d69-109">Het biedt geen ondersteuning voor de implementatie van on-premises Exchange-postvakken.</span><span class="sxs-lookup"><span data-stu-id="54d69-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="54d69-110">U kunt de [compatibiliteitscontrole voor gecentraliseerde implementatie](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)gebruiken   om te bepalen of uw abonnement in aanmerking komt.</span><span class="sxs-lookup"><span data-stu-id="54d69-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="54d69-111">Hoe kan ik de Gebruikerstoewijzingen van de invoegtoepassing richten met gecentraliseerde implementatie?</span><span class="sxs-lookup"><span data-stu-id="54d69-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="54d69-112">Gecentraliseerde implementatie ondersteunt opdrachten voor afzonderlijke gebruikers, groepen en iedereen in de Tenant.</span><span class="sxs-lookup"><span data-stu-id="54d69-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="54d69-113">Gecentraliseerde implementatie kan worden gebruikt voor gebruikers in groepen van het hoogste niveau of groepen zonder bovenliggende groepen, maar niet voor gebruikers in geneste groepen of groepen met bovenliggende groepen.</span><span class="sxs-lookup"><span data-stu-id="54d69-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="54d69-114">Gecentraliseerde implementatie maakt ook deel uit van de meeste Azure Active Directory-groepen, waaronder Office 365-groepen, distributielijsten en beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="54d69-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="54d69-115">U kunt beter de toewijzingen groepen gebruiken in plaats van afzonderlijke gebruikers opdrachten voor eenvoudiger beheer.</span><span class="sxs-lookup"><span data-stu-id="54d69-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="54d69-116">Zie [toewijzingen van gebruikers en groepen](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="54d69-116">For more details, see [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="54d69-117">Hoe lang duurt het voordat invoegtoepassingen worden weergegeven voor alle gebruikers?</span><span class="sxs-lookup"><span data-stu-id="54d69-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="54d69-118">Het kan tot 24 uur duren voordat een invoegtoepassing voor alle gebruikers wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="54d69-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="54d69-119">Het kan even duren voor updates van de invoegtoepassing, de wijzigingen van de optie voor het in-of uitschakelen van de invoegtoepassing of het verwijderen van de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="54d69-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="54d69-120">Hoe kan ik de toegang van gebruikers tot invoegtoepassingen voor mijn organisatie beheren?</span><span class="sxs-lookup"><span data-stu-id="54d69-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="54d69-121">Voor een eenvoudige implementatie van invoegtoepassingen aan gebruikers, groepen en de hele organisatie raden wij beheerders aan gecentraliseerde implementatie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="54d69-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="54d69-122">Zie voor meer informatie over het beheren van gebruikers toegang:</span><span class="sxs-lookup"><span data-stu-id="54d69-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="54d69-123">Downloads van invoegtoepassingen voorkomen door Office Store op alle clients uit te schakelen (met uitzondering van Outlook)</span><span class="sxs-lookup"><span data-stu-id="54d69-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="54d69-124">Beheerders en gebruikers opgeven die invoegtoepassingen voor Outlook kunnen installeren en beheren</span><span class="sxs-lookup"><span data-stu-id="54d69-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](https://docs.microsoft.com/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="54d69-125">Zorgt gecentraliseerde implementatie voor beheerders de flexibiliteit voor het kiezen van de implementatiemethode voor Outlook-invoegtoepassingen?</span><span class="sxs-lookup"><span data-stu-id="54d69-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="54d69-126">Ja.</span><span class="sxs-lookup"><span data-stu-id="54d69-126">Yes.</span></span> <span data-ttu-id="54d69-127">Gecentraliseerde implementatie biedt beheerders de flexibiliteit voor het kiezen van een van de volgende drie implementatiemethoden voor Outlook-invoegtoepassingen tijdens de implementatie van invoegtoepassingen:</span><span class="sxs-lookup"><span data-stu-id="54d69-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="54d69-128">**Vast (standaard)**   De invoegtoepassing wordt automatisch geïmplementeerd voor de toegewezen gebruikers en kan deze niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="54d69-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="54d69-129">**Beschikbaar** Gebruikers kunnen de invoegtoepassing in Outlook installeren door **start > meer invoegtoepassingen voor het beheren van beheerders te kiezen > beheerbare beheerder**.</span><span class="sxs-lookup"><span data-stu-id="54d69-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="54d69-130">**Optioneel** De invoegtoepassing wordt automatisch geïmplementeerd voor de toegewezen gebruikers, maar ze kunnen de optie wel verwijderen.</span><span class="sxs-lookup"><span data-stu-id="54d69-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="54d69-131">Kunnen beheerdersupdate van line-of-Business-invoegtoepassingen (LOB) toevoegen?</span><span class="sxs-lookup"><span data-stu-id="54d69-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="54d69-132">Ja.</span><span class="sxs-lookup"><span data-stu-id="54d69-132">Yes.</span></span> <span data-ttu-id="54d69-133">Beheerders kunnen een nieuw manifestbestand uploaden om wijzigingen in de metagegevens van door de beheerder geïmplementeerde LOB-invoegtoepassingen te ondersteunen. De invoegtoepassing wordt bijgewerkt wanneer de Office-toepassingen de volgende keer worden gestart.</span><span class="sxs-lookup"><span data-stu-id="54d69-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="54d69-134">De webtoepassing kan elk moment worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="54d69-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="54d69-135">Zie [line-of-Business-invoegtoepassing](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="54d69-135">For more information, see [line-of-business add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="54d69-136">Kunnen beheerders invoegtoepassingen uitschakelen?</span><span class="sxs-lookup"><span data-stu-id="54d69-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="54d69-137">Ja.</span><span class="sxs-lookup"><span data-stu-id="54d69-137">Yes.</span></span> <span data-ttu-id="54d69-138">Beheerders kunnen de invoegtoepassingen die ze voor alle gebruikers implementeren, in-of uitschakelen via het Microsoft-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="54d69-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="54d69-139">Zie [Staten van invoegtoepassingen](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="54d69-139">For more information, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="54d69-140">Kunnen beheerders invoegtoepassingen verwijderen of verwijderen?</span><span class="sxs-lookup"><span data-stu-id="54d69-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="54d69-141">Ja.</span><span class="sxs-lookup"><span data-stu-id="54d69-141">Yes.</span></span> <span data-ttu-id="54d69-142">Beheerders kunnen invoegtoepassingen verwijderen die ze voor alle gebruikers in het Microsoft-Beheercentrum hebben geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="54d69-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="54d69-143">Zie [een invoegtoepassing verwijderen](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="54d69-143">For more information, see [Delete an add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="54d69-144">Kunnen beheerders betaalde invoegtoepassingen implementeren vanuit de Office Store met behulp van gecentraliseerde implementatie?</span><span class="sxs-lookup"><span data-stu-id="54d69-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="54d69-145">Nee.</span><span class="sxs-lookup"><span data-stu-id="54d69-145">No.</span></span> <span data-ttu-id="54d69-146">Op dit moment kunt u betaalde invoegtoepassingen in de Office Store niet implementeren met behulp van gecentraliseerde implementatie.</span><span class="sxs-lookup"><span data-stu-id="54d69-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="54d69-147">We raden u aan om bij de ISV-ontwikkelaar voor de betaalde invoegtoepassing een manifestbestand of een URL aan te vragen.</span><span class="sxs-lookup"><span data-stu-id="54d69-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="54d69-148">De tenantbeheerder kan de invoegtoepassing vervolgens implementeren als een LOB-invoegtoepassing met gecentraliseerde implementatie.</span><span class="sxs-lookup"><span data-stu-id="54d69-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="54d69-149">Welke beheerdersrol heb ik nodig voor het beheren van invoegtoepassingen voor mijn organisatie?</span><span class="sxs-lookup"><span data-stu-id="54d69-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="54d69-150">Globale beheerder is de aanbevolen rol met volledige toegang tot de beheer levensduur van de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="54d69-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="54d69-151">Andere beheerdersrollen hebben een beperkte toegang tot de implementatie levensduur van de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="54d69-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="54d69-152">Als u de persoon bent die uw abonnement op Microsoft 365 for Business heeft aangeschaft, bent u de globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="54d69-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="54d69-153">Uw abonnement bevat een reeks beheerdersrollen die u kunt toewijzen aan andere gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="54d69-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="54d69-154">Elke beheerdersrol is toegewezen aan veelvoorkomende zakelijke functies en geeft personen in uw organisatie machtigingen voor het uitvoeren van bepaalde taken in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="54d69-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="54d69-155">Zie [beheerdersrollen toewijzen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="54d69-155">For more information, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>  


