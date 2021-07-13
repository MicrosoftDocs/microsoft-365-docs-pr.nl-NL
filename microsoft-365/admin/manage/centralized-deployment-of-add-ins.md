---
title: Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt voor uw organisatie
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Bepaal of uw tenant en gebruikers aan de vereisten voldoen, zodat u gecentraliseerde implementatie kunt gebruiken om Office te implementeren.
ms.openlocfilehash: cb1cc019cfd87ee05112ea0ac1f0f1675316c6d3
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393701"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="3c97a-103">Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="3c97a-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="3c97a-104">Gecentraliseerde implementatie is de aanbevolen en meest uitgebreide manier voor de meeste klanten om Office te implementeren voor gebruikers en groepen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3c97a-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="3c97a-105">Als u een beheerder bent, gebruikt u deze richtlijnen om te bepalen of uw organisatie en gebruikers voldoen aan de vereisten, zodat u gecentraliseerde implementatie kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3c97a-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="3c97a-106">Gecentraliseerde implementatie biedt de volgende voordelen:</span><span class="sxs-lookup"><span data-stu-id="3c97a-106">Centralized Deployment provides the following benefits:</span></span>

- <span data-ttu-id="3c97a-107">Een globale beheerder kan een invoegvoeging rechtstreeks toewijzen aan een gebruiker, aan meerdere gebruikers via een groep of aan iedereen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="3c97a-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>

- <span data-ttu-id="3c97a-108">Wanneer de desbetreffende Office wordt gestart, wordt de invoegtoepassing automatisch gedownload.</span><span class="sxs-lookup"><span data-stu-id="3c97a-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="3c97a-109">Als de invoegtoepassing invoegopdrachten ondersteunt, wordt de invoegtoepassing automatisch weergegeven op het lint in de Office toepassing.</span><span class="sxs-lookup"><span data-stu-id="3c97a-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>

- <span data-ttu-id="3c97a-110">Invoegvoegingen worden niet meer weergegeven voor gebruikers als de beheerder de invoeging uit- of verwijdert, of als de gebruiker wordt verwijderd uit Azure Active Directory of uit een groep aan wie de invoegvoeging is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="3c97a-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="3c97a-111">Gecentraliseerde implementatie ondersteunt drie bureaubladplatforms Windows, Mac en Online Office apps.</span><span class="sxs-lookup"><span data-stu-id="3c97a-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="3c97a-112">Gecentraliseerde implementatie ondersteunt ook iOS en Android (Outlook alleen mobiele invoegvoegingen).</span><span class="sxs-lookup"><span data-stu-id="3c97a-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="3c97a-113">Het kan maximaal 24 uur duren voordat een invoegtoepassing aan alle gebruikers wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3c97a-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3c97a-114">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="3c97a-114">Before you begin</span></span>

<span data-ttu-id="3c97a-115">Gecentraliseerde implementatie van invoegvoegingen vereist dat de gebruikers Microsoft 365 Enterprise SKU's gebruiken: E3/E5/F3 of Zakelijke SKU's: Business Basic, Business Standard, Business Premium (en zijn aangemeld bij Office met hun organisatie-id) en hebben Exchange Online en actieve Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="3c97a-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="3c97a-116">Uw abonnementsmap moet zijn opgenomen of federatief zijn Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3c97a-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="3c97a-117">U kunt hieronder specifieke vereisten voor Office en Exchange of de compatibiliteitscontrole voor gecentraliseerde implementatie [gebruiken.](#centralized-deployment-compatibility-checker)</span><span class="sxs-lookup"><span data-stu-id="3c97a-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="3c97a-118">Gecentraliseerde implementatie biedt geen ondersteuning voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="3c97a-118">Centralized Deployment doesn't support the following:</span></span>

- <span data-ttu-id="3c97a-119">Invoegtoepassingen die zijn gericht op Word, Excel of PowerPoint in Office 2013</span><span class="sxs-lookup"><span data-stu-id="3c97a-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span>
- <span data-ttu-id="3c97a-120">Een on-premises adreslijstservice</span><span class="sxs-lookup"><span data-stu-id="3c97a-120">An on-premises directory service</span></span>
- <span data-ttu-id="3c97a-121">Implementatie van invoeggebruik in een Exchange postvak on-prem</span><span class="sxs-lookup"><span data-stu-id="3c97a-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="3c97a-122">Implementatie van invoegtoepassingen op SharePoint</span><span class="sxs-lookup"><span data-stu-id="3c97a-122">Add-in deployment to SharePoint</span></span>
- <span data-ttu-id="3c97a-123">Teams apps</span><span class="sxs-lookup"><span data-stu-id="3c97a-123">Teams apps</span></span>
- <span data-ttu-id="3c97a-124">Implementatie van componentobjectmodel (COM) of Visual Studio hulpprogramma's voor Office (VSTO) invoegingen.</span><span class="sxs-lookup"><span data-stu-id="3c97a-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="3c97a-125">Implementaties van Microsoft 365 die geen Exchange Online zoals SKU's: Microsoft 365-apps voor Bedrijven en Microsoft 365-apps voor Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3c97a-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="3c97a-126">Office Vereisten</span><span class="sxs-lookup"><span data-stu-id="3c97a-126">Office Requirements</span></span>

- <span data-ttu-id="3c97a-127">Voor Word, Excel en PowerPoint moeten uw gebruikers een van de volgende gebruiken:</span><span class="sxs-lookup"><span data-stu-id="3c97a-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="3c97a-128">Op een Windows apparaat, versie 1704 of hoger van Microsoft 365 Enterprise SKU's: E3/E5/F3 of Zakelijke SKU's: Business Basic, Business Standard, Business Standard, Premium.</span><span class="sxs-lookup"><span data-stu-id="3c97a-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="3c97a-129">Op een Mac, versie 15.34 of hoger.</span><span class="sxs-lookup"><span data-stu-id="3c97a-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="3c97a-130">Voor Outlook moeten uw gebruikers een van de volgende opties gebruiken:</span><span class="sxs-lookup"><span data-stu-id="3c97a-130">For Outlook, your users must be using one of the following:</span></span>
  - <span data-ttu-id="3c97a-131">Versie 1701 of hoger van Microsoft 365 Enterprise SKU's: E3/E5/F3 of Zakelijke SKU's: Business Basic, Business Standard, Premium.</span><span class="sxs-lookup"><span data-stu-id="3c97a-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="3c97a-132">Versie 1808 of hoger van Office Professional Plus 2019 of Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="3c97a-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="3c97a-133">Versie 16.0.4494.1000 of hoger van Office Professional Plus 2016 (MSI) of Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="3c97a-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="3c97a-134">Versie 15.0.4937.1000 of hoger van Office Professional Plus 2013 (MSI) of Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="3c97a-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="3c97a-135">Versie 16.0.9318.1000 of hoger van Office 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="3c97a-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span>
- <span data-ttu-id="3c97a-136">Versie 2.75.0 of hoger van Outlook mobiel voor iOS</span><span class="sxs-lookup"><span data-stu-id="3c97a-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span>
- <span data-ttu-id="3c97a-137">Versie 2.2.145 of hoger van Outlook voor Android</span><span class="sxs-lookup"><span data-stu-id="3c97a-137">Version 2.2.145 or later of Outlook mobile for Android</span></span>

    <span data-ttu-id="3c97a-138">\*MSI-versies van Outlook worden door beheerders geïnstalleerde invoegvoegingen weergegeven op het Outlook lint, niet in de sectie 'Mijn invoegvoegingen'.</span><span class="sxs-lookup"><span data-stu-id="3c97a-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="3c97a-139">Exchange Online vereisten</span><span class="sxs-lookup"><span data-stu-id="3c97a-139">Exchange Online requirements</span></span>

<span data-ttu-id="3c97a-140">Microsoft Exchange slaat de invoegtoepassingsmanifesten op in de tenant van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3c97a-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="3c97a-141">De beheerder die invoegvoegingen implementeert en de gebruikers die deze invoegvoegingen ontvangen, moeten zich op een versie van Exchange Online die OAuth-verificatie ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="3c97a-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>

<span data-ttu-id="3c97a-p106">Vraag de Exchange-beheerder van uw organisatie welke configuratie in gebruik is. OAuth-connectiviteit per gebruiker kan worden geverifieerd door de PowerShell-cmdlet [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3c97a-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.</span></span>


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="3c97a-144">Gecentraliseerde compatibiliteitscontrole voor implementatie</span><span class="sxs-lookup"><span data-stu-id="3c97a-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="3c97a-145">Met de compatibiliteitscontrole voor gecentraliseerde implementatie kunt u controleren of de gebruikers in uw tenant zijn ingesteld voor het gebruik van Gecentraliseerde implementatie voor Word, Excel en PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="3c97a-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="3c97a-146">De compatibiliteitscontrole is niet vereist voor ondersteuning voor Outlook.</span><span class="sxs-lookup"><span data-stu-id="3c97a-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="3c97a-147">Download de [compatibiliteitscontrole](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="3c97a-147">Download the [compatibility checker](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>

#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="3c97a-148">De compatibiliteitscontrole uitvoeren</span><span class="sxs-lookup"><span data-stu-id="3c97a-148">Run the compatibility checker</span></span>

1. <span data-ttu-id="3c97a-149">Start een verhoogd PowerShell.exe-venster.</span><span class="sxs-lookup"><span data-stu-id="3c97a-149">Start an elevated PowerShell.exe window.</span></span>

2. <span data-ttu-id="3c97a-150">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="3c97a-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```

3. <span data-ttu-id="3c97a-151">Voer de **opdracht Invoke-CompatabilityCheck** uit:</span><span class="sxs-lookup"><span data-stu-id="3c97a-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="3c97a-152">Met deze opdracht wordt u gevraagd  *_om TenantDomain_* (bijvoorbeeld *TailspinToysIncorporated.onmicrosoft. </span> com*) en  *_TenantAdmin-referenties_* (gebruik uw globale beheerdersreferenties) en vraagt vervolgens toestemming.</span><span class="sxs-lookup"><span data-stu-id="3c97a-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3c97a-153">Afhankelijk van het aantal gebruikers in uw tenant, kan het afronden van de controle minuten of uren in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="3c97a-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span>

<span data-ttu-id="3c97a-154">Als het hulpprogramma is uitgevoerd, wordt een uitvoerbestand gegenereerd in een CSV-indeling (door komma's gescheiden).</span><span class="sxs-lookup"><span data-stu-id="3c97a-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="3c97a-155">Het bestand wordt standaard **opgeslagen in C:\windows\system32.**</span><span class="sxs-lookup"><span data-stu-id="3c97a-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="3c97a-156">Het uitvoerbestand bevat de volgende gegevens:</span><span class="sxs-lookup"><span data-stu-id="3c97a-156">The output file contains the following information:</span></span>

- <span data-ttu-id="3c97a-157">Gebruikersnaam</span><span class="sxs-lookup"><span data-stu-id="3c97a-157">User Name</span></span>

- <span data-ttu-id="3c97a-158">Gebruikers-id (e-mailadres van de gebruiker)</span><span class="sxs-lookup"><span data-stu-id="3c97a-158">User ID (User's email address)</span></span>

- <span data-ttu-id="3c97a-159">Geschikt voor Gecentraliseerde implementatie (als de overige items waar zijn)</span><span class="sxs-lookup"><span data-stu-id="3c97a-159">Centralized Deployment ready - If the remaining items are true</span></span>

- <span data-ttu-id="3c97a-160">Office plan - Het plan van Office waar ze een licentie voor hebben</span><span class="sxs-lookup"><span data-stu-id="3c97a-160">Office plan - The plan of Office they are licensed for</span></span>

- <span data-ttu-id="3c97a-161">Office geactiveerd (als Office is geactiveerd)</span><span class="sxs-lookup"><span data-stu-id="3c97a-161">Office Activated - If they have activated Office</span></span>

- <span data-ttu-id="3c97a-162">Ondersteund postvak (als er een OAuth-postvak wordt gebruikt)</span><span class="sxs-lookup"><span data-stu-id="3c97a-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="3c97a-163">Meervoudige verificatie wordt niet ondersteund wanneer u de PowerShell-module voor centrale implementatie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3c97a-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span> <span data-ttu-id="3c97a-164">De module werkt alleen met Basisverificatie.</span><span class="sxs-lookup"><span data-stu-id="3c97a-164">The module only works with Basic authentication.</span></span>

## <a name="user-and-group-assignments"></a><span data-ttu-id="3c97a-165">Toewijzingen van gebruikers en groepen</span><span class="sxs-lookup"><span data-stu-id="3c97a-165">User and group assignments</span></span>

<span data-ttu-id="3c97a-166">De functie Gecentraliseerde implementatie ondersteunt momenteel de meeste groepen die door Azure Active Directory worden ondersteund, Microsoft 365 groepen, distributielijsten en beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="3c97a-166">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="3c97a-167">Niet door e-mail ingeschakelde beveiligingsgroepen worden momenteel niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="3c97a-167">Non-mail enabled security groups are not currently supported.</span></span>

<span data-ttu-id="3c97a-168">Gecentraliseerde implementatie ondersteunt opdrachten aan afzonderlijke gebruikers, groepen en iedereen in de tenant.</span><span class="sxs-lookup"><span data-stu-id="3c97a-168">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="3c97a-169">Gecentraliseerde implementatie ondersteunt gebruikers in groepen op het hoogste niveau of groepen zonder bovenliggende groepen, maar niet gebruikers in geneste groepen of groepen die bovenliggende groepen hebben.</span><span class="sxs-lookup"><span data-stu-id="3c97a-169">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>

<span data-ttu-id="3c97a-p111">Bekijk het volgende voorbeeld, waarin Femke, Assia en de groep Verkoopafdeling zijn toegewezen aan een invoegtoepassing. Omdat de afdeling Verkoop regio West een geneste groep is, zijn Jaap en Roelf niet toegewezen aan een invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="3c97a-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>

![Diagram van verkoopafdeling](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)


### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="3c97a-173">Controleren of een groep geneste groepen bevat</span><span class="sxs-lookup"><span data-stu-id="3c97a-173">Find out if a group contains nested groups</span></span>

<span data-ttu-id="3c97a-174">De gemakkelijkste manier om te controleren of een groep geneste groepen bevat, is het visitekaartje van de groep in Outlook te bekijken.</span><span class="sxs-lookup"><span data-stu-id="3c97a-174">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="3c97a-175">Als u de naam  van de groep in het veld Aan van een e-mailbericht op typt en vervolgens de groepsnaam selecteert wanneer deze is opgelost, wordt in de groep de naam van de groep besleed als deze gebruikers of geneste groepen bevat.</span><span class="sxs-lookup"><span data-stu-id="3c97a-175">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="3c97a-176">In het onderstaande voorbeeld toont het tabblad **Leden** van het Outlook-visitekaartje voor de Testgroep geen gebruikers en slechts twee subgroepen.</span><span class="sxs-lookup"><span data-stu-id="3c97a-176">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span>

![Tabblad Leden van Outlook visitekaartje](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

<span data-ttu-id="3c97a-p113">U kunt de tegenovergestelde query uitvoeren door de groep om te zetten om te zien of deze een lid van een groep is. In het onderstaande voorbeeld kunt u op het tabblad **Lidmaatschap** van het Outlook-visitekaartje zien dat Subgroep 1 een lid van de Testgroep is.</span><span class="sxs-lookup"><span data-stu-id="3c97a-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span>

![Tabblad Lidmaatschap van het Outlook visitekaartje](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

<span data-ttu-id="3c97a-p114">U kunt ook de Azure Active Directory Graph API gebruiken voor het uitvoeren van query's om de lijst met groepen in een groep te vinden. Zie [Bewerkingen op groepen | Graph API-verwijzing](/previous-versions/azure/ad/graph/api/groups-operations) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3c97a-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations).</span></span>

### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="3c97a-183">Contact opnemen met Microsoft voor ondersteuning</span><span class="sxs-lookup"><span data-stu-id="3c97a-183">Contacting Microsoft for support</span></span>

<span data-ttu-id="3c97a-184">Als u of uw gebruikers problemen ondervinden bij het laden van de invoegservice tijdens het gebruik van Office-apps voor het web (Word, Excel, enzovoort), die centraal zijn geïmplementeerd, moet u mogelijk contact opnemen met microsoft-ondersteuning[(meer](../../business-video/get-help-support.md)informatie).</span><span class="sxs-lookup"><span data-stu-id="3c97a-184">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../../business-video/get-help-support.md)).</span></span> <span data-ttu-id="3c97a-185">Geef de volgende informatie over uw Microsoft 365 in het ondersteuningsticket.</span><span class="sxs-lookup"><span data-stu-id="3c97a-185">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>

|<span data-ttu-id="3c97a-186">**Platform**</span><span class="sxs-lookup"><span data-stu-id="3c97a-186">**Platform**</span></span>|<span data-ttu-id="3c97a-187">**Foutopsporingsgegevens**</span><span class="sxs-lookup"><span data-stu-id="3c97a-187">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3c97a-188">Office</span><span class="sxs-lookup"><span data-stu-id="3c97a-188">Office</span></span>  <br/> | <span data-ttu-id="3c97a-189">Charles/Fiddler-logboeken</span><span class="sxs-lookup"><span data-stu-id="3c97a-189">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="3c97a-190">Tenant-id[(meer informatie)](/onedrive/find-your-office-365-tenant-id)</span><span class="sxs-lookup"><span data-stu-id="3c97a-190">Tenant ID ([learn how](/onedrive/find-your-office-365-tenant-id))</span></span>  <br/>  <span data-ttu-id="3c97a-191">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="3c97a-191">CorrelationID.</span></span> <span data-ttu-id="3c97a-192">Bekijk de bron van een van de office-pagina's en zoek naar de waarde Correlatie-id en stuur deze naar ondersteuning:</span><span class="sxs-lookup"><span data-stu-id="3c97a-192">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="3c97a-193">Uitgebreide clients (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="3c97a-193">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="3c97a-194">Charles/Fiddler-logboeken</span><span class="sxs-lookup"><span data-stu-id="3c97a-194">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="3c97a-195">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span><span class="sxs-lookup"><span data-stu-id="3c97a-195">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |

## <a name="related-content"></a><span data-ttu-id="3c97a-196">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="3c97a-196">Related content</span></span>

<span data-ttu-id="3c97a-197">[Invoegvoegingen implementeren in het beheercentrum](../manage/manage-deployment-of-add-ins.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="3c97a-197">[Deploy add-ins in the admin center](../manage/manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="3c97a-198">[Invoegvoegingen beheren in het beheercentrum](manage-addins-in-the-admin-center.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="3c97a-198">[Manage add-ins in the admin center](manage-addins-in-the-admin-center.md) (article)</span></span>\
<span data-ttu-id="3c97a-199">[Veelgestelde vragen over gecentraliseerde](../manage/centralized-deployment-faq.md) implementatie (artikel)</span><span class="sxs-lookup"><span data-stu-id="3c97a-199">[Centralized Deployment FAQ](../manage/centralized-deployment-faq.md) (article)</span></span>\
<span data-ttu-id="3c97a-200">[Uw Microsoft 365 voor zakelijke gebruikers upgraden naar de](../setup/upgrade-users-to-latest-office-client.md) nieuwste Office client (artikel)</span><span class="sxs-lookup"><span data-stu-id="3c97a-200">[Upgrade your Microsoft 365 for business users to the latest Office client](../setup/upgrade-users-to-latest-office-client.md) (article)</span></span>
 