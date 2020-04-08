---
title: Bepalen of gecentraliseerde implementatie van invoegingen werkt voor uw organisatie
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
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
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Bepaal of uw Office 365-tenant en -gebruikers aan de vereisten voldoen, zodat u gecentraliseerde implementatie gebruiken om Office-invoegtoepassingen te implementeren.
ms.openlocfilehash: d6b81a5ac5ef3b5287810110e5d0582bf34bff93
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2020
ms.locfileid: "43189018"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="7f080-103">Bepalen of gecentraliseerde implementatie van invoegingen werkt voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="7f080-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="7f080-104">Gecentraliseerde implementatie is de aanbevolen en meest veelzijdige manier voor de meeste klanten om Office-invoegtoepassingen te implementeren voor gebruikers en groepen binnen de Office 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="7f080-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your Office 365 organization.</span></span> <span data-ttu-id="7f080-105">Als u een beheerder bent, gebruikt u deze richtlijnen om te bepalen of uw tenant en gebruikers aan de vereisten voldoen, zodat u gecentraliseerde implementatie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7f080-105">If you're an admin, use this guidance to determine if your tenant and users meet the requirements so that you can use Centralized Deployment.</span></span>
<span data-ttu-id="7f080-106">Gecentraliseerde implementatie ondersteunt Windows-, Mac-, iOS-, Android- en Online Office-apps.</span><span class="sxs-lookup"><span data-stu-id="7f080-106">Centralized Deployment supports Windows, Mac, iOS, Android and Online Office apps.</span></span>
<span data-ttu-id="7f080-107">Het kan maximaal 24 uur duren voordat een invoegtoepassing aan alle gebruikers wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7f080-107">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="7f080-108">Vereisten</span><span class="sxs-lookup"><span data-stu-id="7f080-108">Requirements</span></span>

<span data-ttu-id="7f080-109">Voor een gecentraliseerde implementatie van invoegingen moeten de gebruikers Office 365 ProPlus gebruiken (en zijn aangemeld bij Office met hun organisatie-id) en hebben ze Exchange Online- en actieve Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="7f080-109">Centralized deployment of add-ins requires that the users are using Office 365 ProPlus (and are signed into Office using their Organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="7f080-110">De map van uw abonnement moet zich in of gefedereerd hebben in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7f080-110">Your subscription'd directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="7f080-111">U hieronder specifieke vereisten voor Office en Exchange bekijken of de [office 365-controlevoor compatibiliteitscontrole voor gecentraliseerde implementatie](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7f080-111">You can view specific requirements for Office and Exchange below, or use the [Office 365 Centralized Deployment Compatibility Checker](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="7f080-112">Gecentraliseerde implementatie biedt geen ondersteuning voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="7f080-112">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="7f080-113">Invoegtoepassingen die zijn gericht op Word, Excel of PowerPoint in Office 2013</span><span class="sxs-lookup"><span data-stu-id="7f080-113">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span>
    
- <span data-ttu-id="7f080-114">Een on-premises adreslijstservice</span><span class="sxs-lookup"><span data-stu-id="7f080-114">An on-premises directory service</span></span>
    
- <span data-ttu-id="7f080-115">Implementatie van invoegtoepassingen op SharePoint</span><span class="sxs-lookup"><span data-stu-id="7f080-115">Add-in deployment to SharePoint</span></span>  

- <span data-ttu-id="7f080-116">Teams-apps</span><span class="sxs-lookup"><span data-stu-id="7f080-116">Teams apps</span></span>
   
- <span data-ttu-id="7f080-117">Implementatie van COM- (Component Object Model) of VSTO-invoegtoepassingen (Visual Studio Tools for Office)</span><span class="sxs-lookup"><span data-stu-id="7f080-117">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
    
- <span data-ttu-id="7f080-118">Implementaties van Office 365 die geen Exchange bevatten, zoals Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="7f080-118">Deployments of Office 365 that do not include Exchange such as Office 365 Business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="7f080-119">Office-vereisten</span><span class="sxs-lookup"><span data-stu-id="7f080-119">Office Requirements</span></span>

- <span data-ttu-id="7f080-120">Voor Word-, Excel- en PowerPoint-invoegtoepassings moeten uw gebruikers een van de volgende opties gebruiken:</span><span class="sxs-lookup"><span data-stu-id="7f080-120">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="7f080-121">Op een Windows-apparaat, versie 1704 of hoger van Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="7f080-121">On a Windows device, Version 1704 or later of Office 365 ProPlus.</span></span>
  - <span data-ttu-id="7f080-122">Op een Mac, versie 15.34 of hoger.</span><span class="sxs-lookup"><span data-stu-id="7f080-122">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="7f080-123">Voor Outlook moeten uw gebruikers een van de volgende opties gebruiken:</span><span class="sxs-lookup"><span data-stu-id="7f080-123">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="7f080-124">Versie 1701 of hoger van Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="7f080-124">Version 1701 or later of Office 365 ProPlus.</span></span>
  - <span data-ttu-id="7f080-125">Versie 1808 of hoger van Office Professional Plus 2019 of Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="7f080-125">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="7f080-126">Versie 16.0.4494.1000 of hoger van Office Professional Plus 2016 (MSI) of Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="7f080-126">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="7f080-127">Versie 15.0.4937.1000 of hoger van Office Professional Plus 2013 (MSI) of Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="7f080-127">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="7f080-128">Versie 16.0.9318.1000 of hoger van Office 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="7f080-128">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="7f080-129">Versie 2.75.0 of hoger van Outlook mobile voor iOS</span><span class="sxs-lookup"><span data-stu-id="7f080-129">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="7f080-130">Versie 2.2.145 of hoger van Outlook mobile voor Android</span><span class="sxs-lookup"><span data-stu-id="7f080-130">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="7f080-131">\*MSI-versies van Outlook tonen door de beheerder geïnstalleerde invoegingen in het juiste Outlook-lint, niet in de sectie Mijn invoegingen.</span><span class="sxs-lookup"><span data-stu-id="7f080-131">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-office-365-proplus-is-installed"></a><span data-ttu-id="7f080-132">Controleren of Office 365 ProPlus is geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="7f080-132">Find out if Office 365 ProPlus is installed</span></span>

<span data-ttu-id="7f080-133">Als u Office 365 ProPlus wilt gebruiken, moet een gebruiker een Office 365-account hebben en een licentie hebben gekregen.</span><span class="sxs-lookup"><span data-stu-id="7f080-133">To use Office 365 ProPlus, a user must have an Office 365 account and must have been assigned a license.</span></span> <span data-ttu-id="7f080-134">Zie [Overzicht van Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7f080-134">For more information, see [Overview of Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="7f080-135">De eenvoudigste manier om te detecteren of een gebruiker Office 365 ProPlus heeft geïnstalleerd en het onlangs heeft gebruikt, is door het microsoft Office-activeringsrapport te gebruiken, dat beschikbaar is in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="7f080-135">The simplest way to detect if a user has Office 365 ProPlus installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7f080-136">Het rapport biedt een lijst met alle gebruikers die Office 365 ProPlus in de afgelopen 7 dagen, 30 dagen, 90 dagen of 180 dagen hebben geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="7f080-136">The report provides a list of all users who have activated Office 365 ProPlus within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="7f080-137">Voor gecentraliseerde implementatiedoeleinden zijn de bureaubladactiveringen voor Windows of Mac de belangrijke kolommen in het rapport.</span><span class="sxs-lookup"><span data-stu-id="7f080-137">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="7f080-138">U kunt het rapport exporteren naar Excel.</span><span class="sxs-lookup"><span data-stu-id="7f080-138">You can export the report to Excel.</span></span> <span data-ttu-id="7f080-139">Zie [Office 365-rapporten in het beheercentrum - Microsoft Office-activeringen](../activity-reports/microsoft-office-activations.md) voor meer informatie over het rapport.</span><span class="sxs-lookup"><span data-stu-id="7f080-139">For more information about the report, see [Office 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="7f080-140">Als u het rapport Activeringen niet wilt gebruiken, u een gebruiker vragen een Office-toepassing zoals Word op zijn of haar machine te openen en vervolgens **Account** \> **bestand**te kiezen.</span><span class="sxs-lookup"><span data-stu-id="7f080-140">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="7f080-141">Onder **Productinformatie** zou u **Abonnementsproduct** en **Microsoft Office 365 ProPlus** moeten zien, zoals weergegeven in de volgende afbeelding.</span><span class="sxs-lookup"><span data-stu-id="7f080-141">Under **Product Information**, you should see **Subscription Product** and **Microsoft Office 365 ProPlus**, as shown in the following image.</span></span>

![Productinformatie in een Office-toepassing](../../media/4bff2bb8-0690-4d22-ac1f-b8881807fa39.png)
  
<span data-ttu-id="7f080-143">Voor hulp met Office 365 ProPlus raadpleegt u [Tips voor het oplossen van problemen met Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846339).</span><span class="sxs-lookup"><span data-stu-id="7f080-143">For help with Office 365 ProPlus, see [Troubleshooting tips for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-online-requirements"></a><span data-ttu-id="7f080-144">Exchange Online-vereisten</span><span class="sxs-lookup"><span data-stu-id="7f080-144">Exchange Online requirements</span></span>

<span data-ttu-id="7f080-145">Microsoft Exchange slaat de invoegtoepassingsmanifesten op in de tenant van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7f080-145">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="7f080-146">De beheerder die invoegingen implementeert en de gebruikers die deze invoegingen ontvangen, moeten zich op een versie van Exchange Online begeven die OAuth-verificatie ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="7f080-146">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="7f080-p107">Vraag de Exchange-beheerder van uw organisatie welke configuratie in gebruik is. OAuth-connectiviteit per gebruiker kan worden geverifieerd door de PowerShell-cmdlet [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7f080-p107">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="office-365-centralized-deployment-compatibility-checker"></a><span data-ttu-id="7f080-149">Compatibiliteitscontrole van Gecentraliseerde implementatie in Office 365</span><span class="sxs-lookup"><span data-stu-id="7f080-149">Office 365 Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="7f080-p108">Met de compatibiliteitscontrole van Office 365 Gecentraliseerde implementatie kunt u controleren of de gebruikers in uw tenant zijn ingesteld voor het gebruik van Gecentraliseerde implementatie voor Word, Excel en PowerPoint. De compatibiliteitscontrole is niet vereist voor ondersteuning voor Outlook. Download [hier](https://aka.ms/officeaddindeploymentorgcompatibilitychecker) de compatibiliteitscontrole.</span><span class="sxs-lookup"><span data-stu-id="7f080-p108">Using the Office 365 Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint. The Compatibility Checker is not required for Outlook support. Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="7f080-153">De compatibiliteitscontrole uitvoeren</span><span class="sxs-lookup"><span data-stu-id="7f080-153">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="7f080-154">Start een verhoogd PowerShell.exe-venster.</span><span class="sxs-lookup"><span data-stu-id="7f080-154">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="7f080-155">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="7f080-155">Run the following command:</span></span>

```powershell
Import-Module O365CompatibilityChecker
```
    
3. <span data-ttu-id="7f080-156">Voer de opdracht **Aanroepen-CompatabilityCheck uit:**</span><span class="sxs-lookup"><span data-stu-id="7f080-156">Run the **Invoke-CompatabilityCheck** command:</span></span>

```powershell
Invoke-CompatibilityCheck
```
   <span data-ttu-id="7f080-157">die u vraagt voor *_TenantDomain_* (bijvoorbeeld *TailspinToysIncorporated.onmicrosoft.</span> com)* en *_TenantAdmin-referenties_* (gebruik uw globale beheerdersreferenties) en vraagt vervolgens toestemming.</span><span class="sxs-lookup"><span data-stu-id="7f080-157">which prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7f080-158">Afhankelijk van het aantal gebruikers in uw tenant, kan het afronden van de controle minuten of uren in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="7f080-158">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="7f080-159">Als het hulpprogramma is uitgevoerd, wordt een uitvoerbestand gegenereerd in een CSV-indeling (door komma's gescheiden).</span><span class="sxs-lookup"><span data-stu-id="7f080-159">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="7f080-160">Het bestand wordt standaard opgeslagen in **C:\windows\system32.**</span><span class="sxs-lookup"><span data-stu-id="7f080-160">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="7f080-161">Het uitvoerbestand bevat de volgende gegevens:</span><span class="sxs-lookup"><span data-stu-id="7f080-161">The output file contains the following information:</span></span>
  
- <span data-ttu-id="7f080-162">Gebruikersnaam</span><span class="sxs-lookup"><span data-stu-id="7f080-162">User Name</span></span>
    
- <span data-ttu-id="7f080-163">Gebruikers-id (e-mailadres van de gebruiker)</span><span class="sxs-lookup"><span data-stu-id="7f080-163">User ID (User's email address)</span></span>
    
- <span data-ttu-id="7f080-164">Geschikt voor Gecentraliseerde implementatie (als de overige items waar zijn)</span><span class="sxs-lookup"><span data-stu-id="7f080-164">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="7f080-165">Office-abonnement - Het office-abonnement waarvoor ze een licentie hebben</span><span class="sxs-lookup"><span data-stu-id="7f080-165">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="7f080-166">Office geactiveerd (als Office is geactiveerd)</span><span class="sxs-lookup"><span data-stu-id="7f080-166">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="7f080-167">Ondersteund postvak (als er een OAuth-postvak wordt gebruikt)</span><span class="sxs-lookup"><span data-stu-id="7f080-167">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>


  
## <a name="user-and-group-assignments"></a><span data-ttu-id="7f080-168">Toewijzingen van gebruikers en groepen</span><span class="sxs-lookup"><span data-stu-id="7f080-168">User and group assignments</span></span>

<span data-ttu-id="7f080-169">De functie Gecentraliseerde implementatie ondersteunt momenteel de meeste groepen die worden ondersteund door Azure Active Directory, waaronder Office 365 Groepen, distributielijsten en beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="7f080-169">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Office 365 Groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f080-170">Niet door e-mail ingeschakelde beveiligingsgroepen worden momenteel niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="7f080-170">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="7f080-171">Gecentraliseerde implementatie ondersteunt toewijzingen aan individuele gebruikers, groepen en iedereen in de tenant.</span><span class="sxs-lookup"><span data-stu-id="7f080-171">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="7f080-172">Gecentraliseerde implementatie ondersteunt gebruikers in groepen op het hoogste niveau of groepen zonder bovenliggende groepen, maar niet gebruikers in geneste groepen of groepen die bovenliggende groepen hebben.</span><span class="sxs-lookup"><span data-stu-id="7f080-172">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="7f080-p111">Bekijk het volgende voorbeeld, waarin Femke, Assia en de groep Verkoopafdeling zijn toegewezen aan een invoegtoepassing. Omdat de afdeling Verkoop regio West een geneste groep is, zijn Jaap en Roelf niet toegewezen aan een invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="7f080-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagram van de verkoopafdeling](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="7f080-176">Controleren of een groep geneste groepen bevat</span><span class="sxs-lookup"><span data-stu-id="7f080-176">Find out if a group contains nested groups</span></span>

<span data-ttu-id="7f080-177">De gemakkelijkste manier om te controleren of een groep geneste groepen bevat, is het visitekaartje van de groep in Outlook te bekijken.</span><span class="sxs-lookup"><span data-stu-id="7f080-177">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="7f080-178">Als u de groepsnaam invoert in het veld **Aan** van een e-mail en vervolgens de groepsnaam selecteert wanneer deze wordt opgelost, wordt u weergegeven of deze gebruikers of geneste groepen bevat.</span><span class="sxs-lookup"><span data-stu-id="7f080-178">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="7f080-179">In het onderstaande voorbeeld toont het tabblad **Leden** van het Outlook-visitekaartje voor de Testgroep geen gebruikers en slechts twee subgroepen.</span><span class="sxs-lookup"><span data-stu-id="7f080-179">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Tabblad Leden van Outlook-visitekaartje](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="7f080-p113">U kunt de tegenovergestelde query uitvoeren door de groep om te zetten om te zien of deze een lid van een groep is. In het onderstaande voorbeeld kunt u op het tabblad **Lidmaatschap** van het Outlook-visitekaartje zien dat Subgroep 1 een lid van de Testgroep is.</span><span class="sxs-lookup"><span data-stu-id="7f080-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Tabblad Lidmaatschap van het Outlook-visitekaartje](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="7f080-p114">U kunt ook de Azure Active Directory Graph API gebruiken voor het uitvoeren van query's om de lijst met groepen in een groep te vinden. Zie [Bewerkingen op groepen | Graph API-verwijzing](https://go.microsoft.com/fwlink/p/?linkid=846342) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7f080-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="7f080-186">Contact opnemen met Microsoft voor ondersteuning</span><span class="sxs-lookup"><span data-stu-id="7f080-186">Contacting Microsoft for support</span></span>

<span data-ttu-id="7f080-187">Als u of uw gebruikers problemen ondervinden bij het laden van de invoegtoepassing tijdens het gebruik van Office-apps voor het web (Word, Excel, enz.), die centraal zijn geïmplementeerd, moet u mogelijk contact opnemen met microsoft-ondersteuning[(meer informatie).](../contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="7f080-187">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="7f080-188">Geef de volgende informatie over uw Office 365-omgeving in het ondersteuningsticket.</span><span class="sxs-lookup"><span data-stu-id="7f080-188">Provide the following information about your Office 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="7f080-189">**Platform**</span><span class="sxs-lookup"><span data-stu-id="7f080-189">**Platform**</span></span>|<span data-ttu-id="7f080-190">**Foutopsporingsgegevens**</span><span class="sxs-lookup"><span data-stu-id="7f080-190">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7f080-191">Office</span><span class="sxs-lookup"><span data-stu-id="7f080-191">Office</span></span>  <br/> | <span data-ttu-id="7f080-192">Charles/Fiddler-logboeken</span><span class="sxs-lookup"><span data-stu-id="7f080-192">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="7f080-193">Tenant-ID ( [meer informatie over hoe](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))</span><span class="sxs-lookup"><span data-stu-id="7f080-193">Tenant ID ( [learn how](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))</span></span>  <br/>  <span data-ttu-id="7f080-194">Correlatie-ID.</span><span class="sxs-lookup"><span data-stu-id="7f080-194">CorrelationID.</span></span> <span data-ttu-id="7f080-195">Bekijk de bron van een van de kantoorpagina's en zoek naar de correlatie-id-waarde en stuur deze naar ondersteuning:</span><span class="sxs-lookup"><span data-stu-id="7f080-195">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="7f080-196">Uitgebreide clients (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="7f080-196">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="7f080-197">Charles/Fiddler-logboeken</span><span class="sxs-lookup"><span data-stu-id="7f080-197">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="7f080-198">Nummers van de client-app maken (bij voorkeur als screenshot van **Bestand/Account)**</span><span class="sxs-lookup"><span data-stu-id="7f080-198">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   

