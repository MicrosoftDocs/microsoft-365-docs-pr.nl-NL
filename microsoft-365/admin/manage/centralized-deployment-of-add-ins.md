---
title: Bepalen of gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Bepaal of uw tenant en gebruikers aan de vereisten voldoen, zodat u gecentraliseerde implementatie gebruiken om Office-invoegtoepassingen te implementeren.
ms.openlocfilehash: fbf6ce702cfe0fa3c85b634996a38cc4857190b6
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102870"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="24ba3-103">Bepalen of gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="24ba3-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="24ba3-104">Gecentraliseerde implementatie is de aanbevolen en meest functierijke manier voor de meeste klanten om Office-invoegtoepassingen te implementeren voor gebruikers en groepen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="24ba3-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="24ba3-105">Als u een beheerder bent, gebruikt u deze richtlijnen om te bepalen of uw organisatie en gebruikers voldoen aan de vereisten, zodat u gecentraliseerde implementatie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="24ba3-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="24ba3-106">Gecentraliseerde implementatie biedt de volgende voordelen:</span><span class="sxs-lookup"><span data-stu-id="24ba3-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="24ba3-107">Een globale beheerder kan een invoegtoepassing rechtstreeks toewijzen aan een gebruiker, aan meerdere gebruikers via een groep of aan iedereen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="24ba3-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="24ba3-108">Wanneer de desbetreffende Office-toepassing wordt gestart, wordt de invoegtoepassing automatisch gedownload.</span><span class="sxs-lookup"><span data-stu-id="24ba3-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="24ba3-109">Als de invoegtoepassing invoegopdrachten ondersteunt, wordt de invoegtoepassing automatisch weergegeven op het lint in de Office-toepassing.</span><span class="sxs-lookup"><span data-stu-id="24ba3-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="24ba3-110">Invoegtoepassingen worden niet meer weergegeven voor gebruikers als de beheerder de invoegtoepassing uit- of verwijdert of als de gebruiker wordt verwijderd uit Azure Active Directory of uit een groep waaraan de invoegtoepassing is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="24ba3-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="24ba3-111">Gecentraliseerde implementatie ondersteunt drie desktopplatforms Windows, Mac en Online Office-apps.</span><span class="sxs-lookup"><span data-stu-id="24ba3-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="24ba3-112">Gecentraliseerde implementatie ondersteunt ook iOS en Android (alleen outlook-mobiele invoegtoepassingen).</span><span class="sxs-lookup"><span data-stu-id="24ba3-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="24ba3-113">Het kan maximaal 24 uur duren voordat een invoegtoepassing aan alle gebruikers wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="24ba3-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="24ba3-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="24ba3-114">Requirements</span></span>

<span data-ttu-id="24ba3-115">Voor gecentraliseerde implementatie van invoegtoepassingen moet de gebruikers Microsoft 365 Apps voor bedrijven gebruiken (en zijn aangemeld bij Office met hun organisatie-ID) en beschikken over Exchange Online- en actieve Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="24ba3-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="24ba3-116">Uw abonnementsmap moet zich bevinden of worden gefedereerd naar Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="24ba3-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="24ba3-117">U hieronder specifieke vereisten voor Office en Exchange bekijken of de [gecentraliseerde implementatiecompatibiliteitscontrole](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="24ba3-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="24ba3-118">Gecentraliseerde implementatie biedt geen ondersteuning voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="24ba3-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="24ba3-119">Invoegtoepassingen die zijn gericht op Word, Excel of PowerPoint in Office 2013</span><span class="sxs-lookup"><span data-stu-id="24ba3-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="24ba3-120">Een on-premises adreslijstservice</span><span class="sxs-lookup"><span data-stu-id="24ba3-120">An on-premises directory service</span></span>
- <span data-ttu-id="24ba3-121">Invoegtoepassing voor een Exchange On-Prem-postvak</span><span class="sxs-lookup"><span data-stu-id="24ba3-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="24ba3-122">Implementatie van invoegtoepassingen op SharePoint</span><span class="sxs-lookup"><span data-stu-id="24ba3-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="24ba3-123">Teams-apps</span><span class="sxs-lookup"><span data-stu-id="24ba3-123">Teams apps</span></span>
- <span data-ttu-id="24ba3-124">Implementatie van COM- (Component Object Model) of VSTO-invoegtoepassingen (Visual Studio Tools for Office)</span><span class="sxs-lookup"><span data-stu-id="24ba3-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
- <span data-ttu-id="24ba3-125">Implementaties van Microsoft 365 die geen Exchange bevatten, zoals Microsoft 365 Apps voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="24ba3-125">Deployments of Microsoft 365 that do not include Exchange such as Microsoft 365 Apps for business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="24ba3-126">Office-vereisten</span><span class="sxs-lookup"><span data-stu-id="24ba3-126">Office Requirements</span></span>

- <span data-ttu-id="24ba3-127">Voor Word-, Excel- en PowerPoint-invoegtoepassingen moeten uw gebruikers een van de volgende opties gebruiken:</span><span class="sxs-lookup"><span data-stu-id="24ba3-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="24ba3-128">Op een Windows-apparaat, versie 1704 of hoger van Microsoft 365 Apps voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="24ba3-128">On a Windows device, Version 1704 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="24ba3-129">Op een Mac, versie 15.34 of hoger.</span><span class="sxs-lookup"><span data-stu-id="24ba3-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="24ba3-130">Voor Outlook moeten uw gebruikers een van de volgende opties gebruiken:</span><span class="sxs-lookup"><span data-stu-id="24ba3-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="24ba3-131">Versie 1701 of later van Microsoft 365 Apps voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="24ba3-131">Version 1701 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="24ba3-132">Versie 1808 of hoger van Office Professional Plus 2019 of Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="24ba3-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="24ba3-133">Versie 16.0.4494.1000 of hoger van Office Professional Plus 2016 (MSI) of Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="24ba3-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="24ba3-134">Versie 15.0.4937.1000 of hoger van Office Professional Plus 2013 (MSI) of Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="24ba3-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="24ba3-135">Versie 16.0.9318.1000 of hoger van Office 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="24ba3-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="24ba3-136">Versie 2.75.0 of hoger van Outlook mobile voor iOS</span><span class="sxs-lookup"><span data-stu-id="24ba3-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="24ba3-137">Versie 2.2.145 of hoger van Outlook mobile voor Android</span><span class="sxs-lookup"><span data-stu-id="24ba3-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="24ba3-138">\*MSI-versies van Outlook tonen door beheerders geïnstalleerde invoegtoepassingen op het juiste Outlook-lint, niet in de sectie Mijn invoegtoepassingen.</span><span class="sxs-lookup"><span data-stu-id="24ba3-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a><span data-ttu-id="24ba3-139">Ontdek of Microsoft 365 Apps for Enterprise is geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="24ba3-139">Find out if Microsoft 365 Apps for enterprise is installed</span></span>

<span data-ttu-id="24ba3-140">Als u Microsoft 365 Apps voor bedrijven wilt gebruiken, moet een gebruiker een Microsoft 365-account hebben en moet een licentie zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="24ba3-140">To use Microsoft 365 Apps for enterprise, a user must have an Microsoft 365 account and must have been assigned a license.</span></span> <span data-ttu-id="24ba3-141">Zie [Overzicht van Microsoft 365-apps voor bedrijven voor](https://go.microsoft.com/fwlink/p/?linkid=846328)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="24ba3-141">For more information, see [Overview of Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="24ba3-142">De eenvoudigste manier om te detecteren of een gebruiker Microsoft 365 Apps for enterprise heeft geïnstalleerd en onlangs heeft gebruikt, is door het Microsoft Office Activations-rapport te gebruiken, dat beschikbaar is in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="24ba3-142">The simplest way to detect if a user has Microsoft 365 Apps for enterprise installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="24ba3-143">Het rapport bevat een lijst met alle gebruikers die Microsoft 365 Apps voor bedrijven hebben geactiveerd in de afgelopen 7 dagen, 30 dagen, 90 dagen of 180 dagen.</span><span class="sxs-lookup"><span data-stu-id="24ba3-143">The report provides a list of all users who have activated Microsoft 365 Apps for enterprise within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="24ba3-144">Voor gecentraliseerde implementatiedoeleinden zijn de bureaubladactiveringen voor Windows of Mac de belangrijke kolommen in het rapport.</span><span class="sxs-lookup"><span data-stu-id="24ba3-144">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="24ba3-145">U kunt het rapport exporteren naar Excel.</span><span class="sxs-lookup"><span data-stu-id="24ba3-145">You can export the report to Excel.</span></span> <span data-ttu-id="24ba3-146">Zie [Microsoft 365-rapporten in het beheercentrum - Microsoft Office-activeringen voor](../activity-reports/microsoft-office-activations.md)meer informatie over het rapport .</span><span class="sxs-lookup"><span data-stu-id="24ba3-146">For more information about the report, see [Microsoft 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="24ba3-147">Als u het rapport Activeringen niet wilt gebruiken, u een gebruiker vragen een Office-toepassing zoals Word op zijn of haar computer te openen en **vervolgens Bestandsaccount** \> **Account**kiezen.</span><span class="sxs-lookup"><span data-stu-id="24ba3-147">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="24ba3-148">Zie onder **Productgegevens** **Abonnementsproduct** en **Microsoft 365 voor bedrijven,** zoals in de volgende afbeelding wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="24ba3-148">Under **Product Information**, you should see **Subscription Product** and **Microsoft 365 for enterprise**, as shown in the following image.</span></span>

![Productgegevens in een Office-toepassing](../../media/product-information-microsoft-365-enterprise.png)
  
<span data-ttu-id="24ba3-150">Zie Tips voor [probleemoplossing voor Microsoft 365-apps voor bedrijven voor](https://go.microsoft.com/fwlink/p/?linkid=846339)hulp bij Microsoft 365 Apps voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="24ba3-150">For help with Microsoft 365 Apps for enterprise, see [Troubleshooting tips for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-online-requirements"></a><span data-ttu-id="24ba3-151">Vereisten voor Exchange Online</span><span class="sxs-lookup"><span data-stu-id="24ba3-151">Exchange Online requirements</span></span>

<span data-ttu-id="24ba3-152">Microsoft Exchange slaat de invoegtoepassingsmanifesten op in de tenant van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="24ba3-152">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="24ba3-153">De beheerder die invoegtoepassingen implementeert en de gebruikers die deze invoegtoepassingen ontvangen, moeten zich op een versie van Exchange Online hebben geplaatst die OAuth-verificatie ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="24ba3-153">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="24ba3-154">Check with your organization's Exchange admin to find out which configuration is in use.</span><span class="sxs-lookup"><span data-stu-id="24ba3-154">Check with your organization's Exchange admin to find out which configuration is in use.</span></span> <span data-ttu-id="24ba3-155">OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span><span class="sxs-lookup"><span data-stu-id="24ba3-155">OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="24ba3-156">Gecentraliseerde implementatiecompatibiliteitscontrole</span><span class="sxs-lookup"><span data-stu-id="24ba3-156">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="24ba3-157">Met de gecentraliseerde implementatiecompatibiliteitscontrole u controleren of de gebruikers op uw tenant zijn ingesteld om gecentraliseerde implementatie voor Word, Excel en PowerPoint te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="24ba3-157">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="24ba3-158">De compatibiliteitscontrole is niet vereist voor ondersteuning voor Outlook.</span><span class="sxs-lookup"><span data-stu-id="24ba3-158">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="24ba3-159">Download [hier](https://aka.ms/officeaddindeploymentorgcompatibilitychecker) de compatibiliteitscontrole.</span><span class="sxs-lookup"><span data-stu-id="24ba3-159">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="24ba3-160">De compatibiliteitscontrole uitvoeren</span><span class="sxs-lookup"><span data-stu-id="24ba3-160">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="24ba3-161">Start een verhoogd PowerShell.exe-venster.</span><span class="sxs-lookup"><span data-stu-id="24ba3-161">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="24ba3-162">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="24ba3-162">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="24ba3-163">Voer de opdracht **Aanroepen-CompatabilityCheck** uit:</span><span class="sxs-lookup"><span data-stu-id="24ba3-163">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="24ba3-164">Met deze opdracht wordt u gevraagd voor *_TenantDomain_* (bijvoorbeeld *TailspinToysIncorporated.onmicrosoft. </span> com)* en *_TenantAdmin-referenties_* (gebruik uw globale beheerdersreferenties) en vraagt vervolgens toestemming.</span><span class="sxs-lookup"><span data-stu-id="24ba3-164">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="24ba3-165">Afhankelijk van het aantal gebruikers in uw tenant, kan het afronden van de controle minuten of uren in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="24ba3-165">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="24ba3-166">Als het hulpprogramma is uitgevoerd, wordt een uitvoerbestand gegenereerd in een CSV-indeling (door komma's gescheiden).</span><span class="sxs-lookup"><span data-stu-id="24ba3-166">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="24ba3-167">Het bestand wordt standaard opgeslagen in **C:\windows\system32.**</span><span class="sxs-lookup"><span data-stu-id="24ba3-167">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="24ba3-168">Het uitvoerbestand bevat de volgende gegevens:</span><span class="sxs-lookup"><span data-stu-id="24ba3-168">The output file contains the following information:</span></span>
  
- <span data-ttu-id="24ba3-169">Gebruikersnaam</span><span class="sxs-lookup"><span data-stu-id="24ba3-169">User Name</span></span>
    
- <span data-ttu-id="24ba3-170">Gebruikers-id (e-mailadres van de gebruiker)</span><span class="sxs-lookup"><span data-stu-id="24ba3-170">User ID (User's email address)</span></span>
    
- <span data-ttu-id="24ba3-171">Geschikt voor Gecentraliseerde implementatie (als de overige items waar zijn)</span><span class="sxs-lookup"><span data-stu-id="24ba3-171">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="24ba3-172">Office-abonnement - Het office-abonnement waarvoor ze een licentie hebben</span><span class="sxs-lookup"><span data-stu-id="24ba3-172">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="24ba3-173">Office geactiveerd (als Office is geactiveerd)</span><span class="sxs-lookup"><span data-stu-id="24ba3-173">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="24ba3-174">Ondersteund postvak (als er een OAuth-postvak wordt gebruikt)</span><span class="sxs-lookup"><span data-stu-id="24ba3-174">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>


  
## <a name="user-and-group-assignments"></a><span data-ttu-id="24ba3-175">Toewijzingen van gebruikers en groepen</span><span class="sxs-lookup"><span data-stu-id="24ba3-175">User and group assignments</span></span>

<span data-ttu-id="24ba3-176">De functie Gecentraliseerde implementatie ondersteunt momenteel de meeste groepen die worden ondersteund door Azure Active Directory, waaronder Microsoft 365-groepen, distributielijsten en beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="24ba3-176">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24ba3-177">Niet door e-mail ingeschakelde beveiligingsgroepen worden momenteel niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="24ba3-177">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="24ba3-178">Gecentraliseerde implementatie ondersteunt toewijzingen aan individuele gebruikers, groepen en iedereen in de tenant.</span><span class="sxs-lookup"><span data-stu-id="24ba3-178">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="24ba3-179">Gecentraliseerde implementatie ondersteunt gebruikers in groepen op het hoogste niveau of groepen zonder bovenliggende groepen, maar niet gebruikers in geneste groepen of groepen die bovenliggende groepen hebben.</span><span class="sxs-lookup"><span data-stu-id="24ba3-179">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="24ba3-180">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in.</span><span class="sxs-lookup"><span data-stu-id="24ba3-180">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in.</span></span> <span data-ttu-id="24ba3-181">Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span><span class="sxs-lookup"><span data-stu-id="24ba3-181">Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagram van de verkoopafdeling](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="24ba3-183">Controleren of een groep geneste groepen bevat</span><span class="sxs-lookup"><span data-stu-id="24ba3-183">Find out if a group contains nested groups</span></span>

<span data-ttu-id="24ba3-184">De gemakkelijkste manier om te controleren of een groep geneste groepen bevat, is het visitekaartje van de groep in Outlook te bekijken.</span><span class="sxs-lookup"><span data-stu-id="24ba3-184">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="24ba3-185">Als u de groepsnaam invoert in het veld **Aan** van een e-mail en vervolgens de groepsnaam selecteert wanneer deze is opgelost, wordt u weergegeven of deze gebruikers of geneste groepen bevat.</span><span class="sxs-lookup"><span data-stu-id="24ba3-185">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="24ba3-186">In het onderstaande voorbeeld toont het tabblad **Leden** van het Outlook-visitekaartje voor de Testgroep geen gebruikers en slechts twee subgroepen.</span><span class="sxs-lookup"><span data-stu-id="24ba3-186">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Tabblad Leden van Outlook-visitekaartje](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="24ba3-188">You can do the opposite query by resolving the group to see if it's a member of any group.</span><span class="sxs-lookup"><span data-stu-id="24ba3-188">You can do the opposite query by resolving the group to see if it's a member of any group.</span></span> <span data-ttu-id="24ba3-189">In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span><span class="sxs-lookup"><span data-stu-id="24ba3-189">In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Tabblad Lidmaatschap van het Outlook-visitekaartje](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="24ba3-191">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group.</span><span class="sxs-lookup"><span data-stu-id="24ba3-191">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group.</span></span> <span data-ttu-id="24ba3-192">For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="24ba3-192">For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="24ba3-193">Contact opnemen met Microsoft voor ondersteuning</span><span class="sxs-lookup"><span data-stu-id="24ba3-193">Contacting Microsoft for support</span></span>

<span data-ttu-id="24ba3-194">Als u of uw gebruikers problemen ondervinden bij het laden van de invoegtoepassing tijdens het gebruik van Office-apps voor het web (Word, Excel, enz.), die centraal zijn geïmplementeerd, moet u mogelijk contact opnemen met microsoft-ondersteuning[(lees hoe).](../contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="24ba3-194">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="24ba3-195">Geef de volgende informatie over uw Microsoft 365-omgeving op in het ondersteuningsticket.</span><span class="sxs-lookup"><span data-stu-id="24ba3-195">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="24ba3-196">**Platform**</span><span class="sxs-lookup"><span data-stu-id="24ba3-196">**Platform**</span></span>|<span data-ttu-id="24ba3-197">**Foutopsporingsgegevens**</span><span class="sxs-lookup"><span data-stu-id="24ba3-197">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="24ba3-198">Office</span><span class="sxs-lookup"><span data-stu-id="24ba3-198">Office</span></span>  <br/> | <span data-ttu-id="24ba3-199">Charles/Fiddler-logboeken</span><span class="sxs-lookup"><span data-stu-id="24ba3-199">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="24ba3-200">Tenant-ID ( [meer informatie over hoe](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="24ba3-200">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="24ba3-201">CorrelatieID.</span><span class="sxs-lookup"><span data-stu-id="24ba3-201">CorrelationID.</span></span> <span data-ttu-id="24ba3-202">Bekijk de bron van een van de kantoorpagina's en zoek naar de waarde Correlatie-id en stuur deze naar ondersteuning:</span><span class="sxs-lookup"><span data-stu-id="24ba3-202">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="24ba3-203">Uitgebreide clients (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="24ba3-203">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="24ba3-204">Charles/Fiddler-logboeken</span><span class="sxs-lookup"><span data-stu-id="24ba3-204">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="24ba3-205">Nummers van de client-app maken (bij voorkeur als screenshot van **Bestand/account)**</span><span class="sxs-lookup"><span data-stu-id="24ba3-205">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   

