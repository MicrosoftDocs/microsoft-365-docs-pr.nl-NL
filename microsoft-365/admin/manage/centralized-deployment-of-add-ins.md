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
description: Bepaal of uw Tenant en gebruikers aan de vereisten voldoen, zodat u gecentraliseerde implementatie kunt gebruiken om Office-invoegtoepassingen te implementeren.
ms.openlocfilehash: 04c5f9090ca788f00f2d17d3af59e8022195e9be
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519363"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="28002-103">Bepalen of gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="28002-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="28002-104">Gecentraliseerde implementatie is de aanbevolen en krach functionele manier voor de meeste klanten om Office-invoegtoepassingen te implementeren voor gebruikers en groepen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="28002-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="28002-105">Als u een beheerder bent, kunt u deze richtlijnen gebruiken om te bepalen of uw organisatie en gebruikers aan de vereisten voldoen, zodat u gecentraliseerde implementatie kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="28002-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="28002-106">Gecentraliseerde implementatie biedt de volgende voordelen:</span><span class="sxs-lookup"><span data-stu-id="28002-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="28002-107">Een globale beheerder kan een invoegtoepassing rechtstreeks aan een gebruiker toewijzen, aan meerdere gebruikers via een groep of aan iedereen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="28002-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="28002-108">Wanneer de relevante Office-toepassing wordt gestart, wordt de invoegtoepassing automatisch gedownload.</span><span class="sxs-lookup"><span data-stu-id="28002-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="28002-109">Als de invoegtoepassing ondersteuning biedt voor opdrachten van invoegtoepassingen, wordt de invoegtoepassing automatisch weergegeven op het lint in de Office-toepassing.</span><span class="sxs-lookup"><span data-stu-id="28002-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="28002-110">Invoegtoepassingen worden niet langer weergegeven voor gebruikers als de beheerder de invoegtoepassing uitschakelt of verwijdert, of als de gebruiker wordt verwijderd uit Azure Active Directory of een groep waaraan de invoegtoepassing is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="28002-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="28002-111">Gecentraliseerde implementatie ondersteunt drie bureaublad platforms, Windows-apps en online Office-apps.</span><span class="sxs-lookup"><span data-stu-id="28002-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="28002-112">Gecentraliseerde implementatie biedt ook ondersteuning voor iOS en Android (alleen voor mobiele Outlook-invoegtoepassingen).</span><span class="sxs-lookup"><span data-stu-id="28002-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="28002-113">Het kan maximaal 24 uur duren voordat een invoegtoepassing aan alle gebruikers wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="28002-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="28002-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="28002-114">Requirements</span></span>

<span data-ttu-id="28002-115">Gecentraliseerde implementatie van invoegtoepassingen vereist dat de gebruikers Microsoft 365 Enterprise-Sku's: E3/E5/F3 of Business Sku's: Business Basic, Business Standard, Business Premium (en zijn aangemeld bij Office met hun organisatie-ID), en de postvakken Exchange Online en Active Exchange Online gebruiken.</span><span class="sxs-lookup"><span data-stu-id="28002-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="28002-116">Uw abonnements gids moet zijn aangemeld of federatief zijn voor Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="28002-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="28002-117">U kunt de specifieke vereisten voor Office en Exchange bekijken of de [compatibiliteitscontrole voor gecentraliseerde implementatie](#centralized-deployment-compatibility-checker)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="28002-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="28002-118">Gecentraliseerde implementatie biedt geen ondersteuning voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="28002-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="28002-119">Invoegtoepassingen die zijn gericht op Word, Excel of PowerPoint in Office 2013</span><span class="sxs-lookup"><span data-stu-id="28002-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="28002-120">Een on-premises adreslijstservice</span><span class="sxs-lookup"><span data-stu-id="28002-120">An on-premises directory service</span></span>
- <span data-ttu-id="28002-121">Implementatie van invoegtoepassing aan een Exchange on-premises Postvak</span><span class="sxs-lookup"><span data-stu-id="28002-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="28002-122">Implementatie van invoegtoepassingen op SharePoint</span><span class="sxs-lookup"><span data-stu-id="28002-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="28002-123">Teams-apps</span><span class="sxs-lookup"><span data-stu-id="28002-123">Teams apps</span></span>
- <span data-ttu-id="28002-124">Implementatie van COM-invoegtoepassingen (Component Object Model) of VSTO-invoegtoepassingen (Visual Studio Tools for Office).</span><span class="sxs-lookup"><span data-stu-id="28002-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="28002-125">Implementaties van Microsoft 365 die geen Exchange Online bevatten, zoals Sku's: Microsoft 365 apps for Business en Microsoft 365 apps for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="28002-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="28002-126">Office-vereisten</span><span class="sxs-lookup"><span data-stu-id="28002-126">Office Requirements</span></span>

- <span data-ttu-id="28002-127">Voor Word-, Excel-en PowerPoint-invoegtoepassingen moeten de gebruikers een van de volgende handelingen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="28002-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="28002-128">Op een Windows-apparaat, versie 1704 of hoger van Microsoft 365 Enterprise Sku's: E3/E5/F3 of Business Sku's: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="28002-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="28002-129">Op een Mac, versie 15,34 of hoger.</span><span class="sxs-lookup"><span data-stu-id="28002-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="28002-130">Voor Outlook moeten de gebruikers een van de volgende handelingen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="28002-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="28002-131">Versie 1701 of hoger van Microsoft 365 Enterprise Sku's: E3/E5/F3 of Business Sku's: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="28002-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="28002-132">Versie 1808 of hoger van Office Professional Plus 2019 of Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="28002-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="28002-133">Versie 16.0.4494.1000 of hoger van Office Professional Plus 2016 (MSI) of Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="28002-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="28002-134">Versie 15.0.4937.1000 of hoger van Office Professional Plus 2013 (MSI) of Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="28002-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="28002-135">Versie 16.0.9318.1000 of hoger van Office 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="28002-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="28002-136">Versie 2.75.0 of hoger van Outlook Mobile voor iOS</span><span class="sxs-lookup"><span data-stu-id="28002-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="28002-137">Versie 2.2.145 of hoger van Outlook Mobile voor Android</span><span class="sxs-lookup"><span data-stu-id="28002-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="28002-138">\* MSI-versies van Outlook tonen beheerders geïnstalleerde invoegtoepassingen op het juiste Outlook-lint, niet de sectie ' mijn invoegtoepassingen '.</span><span class="sxs-lookup"><span data-stu-id="28002-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="28002-139">Vereisten voor Exchange Online</span><span class="sxs-lookup"><span data-stu-id="28002-139">Exchange Online requirements</span></span>

<span data-ttu-id="28002-140">Microsoft Exchange slaat de invoegtoepassingsmanifesten op in de tenant van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="28002-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="28002-141">De beheerder die invoegtoepassingen implementeert en de gebruikers die deze invoegtoepassingen ontvangen, moeten beschikken over een versie van Exchange Online die OAuth-verificatie ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="28002-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="28002-p106">Vraag de Exchange-beheerder van uw organisatie welke configuratie in gebruik is. OAuth-connectiviteit per gebruiker kan worden geverifieerd door de PowerShell-cmdlet [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="28002-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="28002-144">Compatibiliteitscontrole voor gecentraliseerde implementatie</span><span class="sxs-lookup"><span data-stu-id="28002-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="28002-145">Met behulp van de compatibiliteitscontrole voor gecentraliseerde implementatie kunt u controleren of de gebruikers in uw Tenant zijn geconfigureerd voor het gebruik van gecentraliseerde implementatie voor Word, Excel en PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="28002-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="28002-146">De compatibiliteitscontrole is niet vereist voor ondersteuning voor Outlook.</span><span class="sxs-lookup"><span data-stu-id="28002-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="28002-147">Download [hier](https://aka.ms/officeaddindeploymentorgcompatibilitychecker) de compatibiliteitscontrole.</span><span class="sxs-lookup"><span data-stu-id="28002-147">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="28002-148">De compatibiliteitscontrole uitvoeren</span><span class="sxs-lookup"><span data-stu-id="28002-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="28002-149">Start een verhoogd PowerShell.exe-venster.</span><span class="sxs-lookup"><span data-stu-id="28002-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="28002-150">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="28002-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="28002-151">Voer de opdracht **invoke-CompatabilityCheck** uit:</span><span class="sxs-lookup"><span data-stu-id="28002-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="28002-152">Met deze opdracht vraagt u om  *_TenantDomain_* (bijvoorbeeld *TailspinToysIncorporated. onmicrosoft. </span> com*-en  *_TenantAdmin_* -referenties (gebruik uw globale-beheerdersreferenties) en vraagt u om toestemming.</span><span class="sxs-lookup"><span data-stu-id="28002-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="28002-153">Afhankelijk van het aantal gebruikers in uw tenant, kan het afronden van de controle minuten of uren in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="28002-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="28002-154">Als het hulpprogramma is uitgevoerd, wordt een uitvoerbestand gegenereerd in een CSV-indeling (door komma's gescheiden).</span><span class="sxs-lookup"><span data-stu-id="28002-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="28002-155">Het bestand wordt standaard opgeslagen in **C:\Windows\System32** .</span><span class="sxs-lookup"><span data-stu-id="28002-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="28002-156">Het uitvoerbestand bevat de volgende gegevens:</span><span class="sxs-lookup"><span data-stu-id="28002-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="28002-157">Gebruikersnaam</span><span class="sxs-lookup"><span data-stu-id="28002-157">User Name</span></span>
    
- <span data-ttu-id="28002-158">Gebruikers-id (e-mailadres van de gebruiker)</span><span class="sxs-lookup"><span data-stu-id="28002-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="28002-159">Geschikt voor Gecentraliseerde implementatie (als de overige items waar zijn)</span><span class="sxs-lookup"><span data-stu-id="28002-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="28002-160">Kantoor abonnement: het abonnement van de Office-licentie voor</span><span class="sxs-lookup"><span data-stu-id="28002-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="28002-161">Office geactiveerd (als Office is geactiveerd)</span><span class="sxs-lookup"><span data-stu-id="28002-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="28002-162">Ondersteund postvak (als er een OAuth-postvak wordt gebruikt)</span><span class="sxs-lookup"><span data-stu-id="28002-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="28002-163">Meervoudige verificatie wordt niet ondersteund wanneer u de PowerShell-module van de centrale implementatie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="28002-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="28002-164">Toewijzingen van gebruikers en groepen</span><span class="sxs-lookup"><span data-stu-id="28002-164">User and group assignments</span></span>

<span data-ttu-id="28002-165">De functie gecentraliseerde implementatie ondersteunt momenteel de meeste groepen die worden ondersteund door Azure Active Directory, waaronder Microsoft 365-groepen, distributielijsten en beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="28002-165">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="28002-166">Niet door e-mail ingeschakelde beveiligingsgroepen worden momenteel niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="28002-166">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="28002-167">Gecentraliseerde implementatie ondersteunt opdrachten voor afzonderlijke gebruikers, groepen en iedereen in de Tenant.</span><span class="sxs-lookup"><span data-stu-id="28002-167">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="28002-168">Gecentraliseerde implementatie ondersteunt gebruikers in groepen op het hoogste niveau of groepen zonder bovenliggende groepen, maar niet gebruikers in geneste groepen of groepen die bovenliggende groepen hebben.</span><span class="sxs-lookup"><span data-stu-id="28002-168">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="28002-p110">Bekijk het volgende voorbeeld, waarin Femke, Assia en de groep Verkoopafdeling zijn toegewezen aan een invoegtoepassing. Omdat de afdeling Verkoop regio West een geneste groep is, zijn Jaap en Roelf niet toegewezen aan een invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="28002-p110">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagram van verkoopafdeling](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="28002-172">Controleren of een groep geneste groepen bevat</span><span class="sxs-lookup"><span data-stu-id="28002-172">Find out if a group contains nested groups</span></span>

<span data-ttu-id="28002-173">De gemakkelijkste manier om te controleren of een groep geneste groepen bevat, is het visitekaartje van de groep in Outlook te bekijken.</span><span class="sxs-lookup"><span data-stu-id="28002-173">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="28002-174">Als u de groepsnaam opgeeft in het veld **aan** van een e-mailbericht en vervolgens de groepsnaam selecteert wanneer deze wordt opgelost, wordt u weergegeven als het een of meer gebruikers zijn met een geneste groep.</span><span class="sxs-lookup"><span data-stu-id="28002-174">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="28002-175">In het onderstaande voorbeeld toont het tabblad **Leden** van het Outlook-visitekaartje voor de Testgroep geen gebruikers en slechts twee subgroepen.</span><span class="sxs-lookup"><span data-stu-id="28002-175">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Tabblad leden van Outlook-visitekaartje](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="28002-p112">U kunt de tegenovergestelde query uitvoeren door de groep om te zetten om te zien of deze een lid van een groep is. In het onderstaande voorbeeld kunt u op het tabblad **Lidmaatschap** van het Outlook-visitekaartje zien dat Subgroep 1 een lid van de Testgroep is.</span><span class="sxs-lookup"><span data-stu-id="28002-p112">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Het tabblad lidmaatschap van het Outlook-visitekaartje](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="28002-p113">U kunt ook de Azure Active Directory Graph API gebruiken voor het uitvoeren van query's om de lijst met groepen in een groep te vinden. Zie [Bewerkingen op groepen | Graph API-verwijzing](https://go.microsoft.com/fwlink/p/?linkid=846342) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="28002-p113">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="28002-182">Contact opnemen met Microsoft voor ondersteuning</span><span class="sxs-lookup"><span data-stu-id="28002-182">Contacting Microsoft for support</span></span>

<span data-ttu-id="28002-183">Als u of uw gebruikers problemen ondervinden bij het laden van de invoegtoepassing wanneer u Office-apps gebruikt voor het web (Word, Excel, enzovoort) die centraal zijn geïmplementeerd, moet u mogelijk contact opnemen met Microsoft ondersteuning ([meer informatie](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="28002-183">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="28002-184">Voer de volgende informatie in over uw Microsoft 365-omgeving in het ondersteuningsticket.</span><span class="sxs-lookup"><span data-stu-id="28002-184">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="28002-185">**Platform**</span><span class="sxs-lookup"><span data-stu-id="28002-185">**Platform**</span></span>|<span data-ttu-id="28002-186">**Foutopsporingsgegevens**</span><span class="sxs-lookup"><span data-stu-id="28002-186">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28002-187">Office</span><span class="sxs-lookup"><span data-stu-id="28002-187">Office</span></span>  <br/> | <span data-ttu-id="28002-188">Charles/Fiddler-logboeken</span><span class="sxs-lookup"><span data-stu-id="28002-188">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="28002-189">Tenant-ID ( [meer informatie over hoe](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="28002-189">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="28002-190">39379.</span><span class="sxs-lookup"><span data-stu-id="28002-190">CorrelationID.</span></span> <span data-ttu-id="28002-191">Geef de bron van een van de Office-pagina's weer en zoek de waarde van de correlatie-ID en verzend deze naar ondersteuning:</span><span class="sxs-lookup"><span data-stu-id="28002-191">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="28002-192">Uitgebreide clients (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="28002-192">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="28002-193">Charles/Fiddler-logboeken</span><span class="sxs-lookup"><span data-stu-id="28002-193">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="28002-194">Bouw nummers van de client-app (bij voorkeur als een schermafbeelding van **bestand/account**)</span><span class="sxs-lookup"><span data-stu-id="28002-194">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   
