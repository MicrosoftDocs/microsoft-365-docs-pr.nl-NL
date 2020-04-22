---
title: Team voor een zeer geheim project van Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Samenvatting: Hoe Contoso een team gebruikte voor sterk gereguleerde gegevens voor een topgeheim project om een nieuwe reeks producten en diensten te ontwikkelen.'
ms.openlocfilehash: 310ef33d4add7d71616aee8808515ca90536d8c1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636496"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="ed9f9-103">Team voor een zeer geheim project van Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="ed9f9-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="ed9f9-104">Na een executive offsite, Contoso's CEO beval de ontwikkeling van een nieuwe suite van producten en diensten die de winst van Contoso zou kunnen verdubbelen in de komende vijf jaar.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="ed9f9-105">Het topgeheime project voor de ontwikkeling van het bedrijfs-, engineering- en marktplan kreeg de naam **Project 2X** en belangrijke medewerkers in het hele bedrijf werden aangeworven.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="ed9f9-106">De tijdlijnen voor onderzoek en ontwikkeling waren strak, wat betekende dat samenwerking efficiënt moest zijn en moest zorgen voor veilige vergaderingen, lopende gesprekken en bestandsopslag.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="ed9f9-107">De resulterende deliverables voor Project 2X waren bedrijfsplannen, product- en engineeringspecificaties en marketingmaterialen en -schema's in de vorm van Word-, Excel- en PowerPoint-bestanden.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="ed9f9-108">Vanwege hun gevoelige aard, de toegang tot deze bestanden waren:</span><span class="sxs-lookup"><span data-stu-id="ed9f9-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="ed9f9-109">Beperkt tot Project 2X-teamleden.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="ed9f9-110">Beschermd met een DLP-beleid (Data Loss Prevention) om te voorkomen dat Project 2X-teamleden ze buiten het team delen.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="ed9f9-111">Versleuteld en beveiligd met machtigingen om alleen toegang te verlenen aan Project 2X-teamleden, zelfs als de bestanden buiten Contoso zijn gedistribueerd.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="ed9f9-112">Het [IT-personeel](secure-teams-highly-regulated-data-scenario.md) van Contoso gebruikte een team voor sterk gereguleerde gegevens voor Project 2X en deze stappen.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="ed9f9-113">Stap 1: Een privéteam maken en de onderliggende SharePoint-site vergrendeld</span><span class="sxs-lookup"><span data-stu-id="ed9f9-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="ed9f9-114">Om de toegang tot de onderliggende SharePoint-site voor het team te beschermen, hebben De IT-beheerders van Contoso het [aanbevolen SharePoint-toegangsbeleid](sharepoint-file-access-policies.md)geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="ed9f9-115">Vervolgens heeft een It-beheerder van Contoso een nieuw privéteam met de naam Project 2X gemaakt en de gebruikersaccounts van Project 2X-medewerkers als leden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="ed9f9-116">Vervolgens hebben ze extra machtigingsinstellingen voor de site geconfigureerd om te voorkomen dat Project 2X toegang tot de site deelt en om te voorkomen dat andere toegang tot de site aanvragen.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="ed9f9-117">Zie [SharePoint-instellingen voor een sterk gereguleerd team voor](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams)de configuratiegegevens.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="ed9f9-118">Stap 2: Een DLP-beleid en de onderliggende site configureren voor een bewaarlabel</span><span class="sxs-lookup"><span data-stu-id="ed9f9-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="ed9f9-119">Ten eerste pasten Contoso-beheerders het bestaande **label voor zeer vertrouwelijke** bewaarwaarde toe op de sectie **Documenten** van de onderliggende SharePoint-site van het Project 2X-team.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-119">First, Contoso admins applied the existing **Highly Confidential** retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="ed9f9-120">Vervolgens hebben ze een nieuw DLP-beleid gemaakt met de naam **Project 2X** dat:</span><span class="sxs-lookup"><span data-stu-id="ed9f9-120">Next, they created a new DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="ed9f9-121">Gebruikt het highly confidential retention label.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-121">Uses the Highly Confidential retention label.</span></span>
- <span data-ttu-id="ed9f9-122">Blokkeert gebruikers wanneer ze proberen een bestand te delen in het Project 2X-team buiten Contoso.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="ed9f9-123">Zie Bestanden beveiligen [in teams met bewaarlabels en DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)voor de configuratiegegevens.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="ed9f9-124">Stap 3: Een gevoeligheidslabel maken voor het Project 2X-team</span><span class="sxs-lookup"><span data-stu-id="ed9f9-124">Step 3: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="ed9f9-125">Contoso-beheerders hebben een nieuw gevoeligheidslabel gemaakt met de naam **Project 2X** dat:</span><span class="sxs-lookup"><span data-stu-id="ed9f9-125">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="ed9f9-126">Vereist versleuteling.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-126">Requires encryption.</span></span>
- <span data-ttu-id="ed9f9-127">Hiermee kunnen machtigingen voor co-auteur worden toegestaan voor de Project 2X Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-127">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="ed9f9-128">Hier is de resulterende configuratie van het Project 2X-team.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-128">Here is the resulting configuration of the Project 2X team.</span></span>

![De resulterende configuratie van het Project 2X-team](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="ed9f9-130">Bestanden in de sectie Documenten van de onderliggende Project 2X SharePoint-site zijn beveiligd door:</span><span class="sxs-lookup"><span data-stu-id="ed9f9-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="ed9f9-131">De sitemachtigingen, die alleen toegang geven tot leden van de Project 2X Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-131">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="ed9f9-132">Het label Highly Confidential retention, dat automatisch wordt toegewezen aan nieuwe bestanden.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="ed9f9-133">Een DLP-beleid dat het label Highly Confidential retention en instellingen gebruikt die voorkomen dat het bestand wordt gedeeld met externe gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="ed9f9-134">Het label Voor de gevoeligheid van Project 2X, met versleuteling en machtigingen die met het bestand reizen als het wordt verplaatst of gekopieerd van de site.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="ed9f9-135">Hier is een voorbeeld van een bestand dat is opgeslagen in de onderliggende Project 2X-site met het label Sterk gereguleerd bewaren en het label Project 2X-gevoeligheid toegewezen.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![Een voorbeeld van een bestand dat is opgeslagen in de onderliggende Project 2X-site](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="ed9f9-137">Stap 4: Getrainde Project 2X-teamleden</span><span class="sxs-lookup"><span data-stu-id="ed9f9-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="ed9f9-138">Contoso security medewerkers trainden de Project 2X teamleden in een verplichte cursus die hen door:</span><span class="sxs-lookup"><span data-stu-id="ed9f9-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="ed9f9-139">Hoe u toegang krijgt tot het nieuwe Project 2X-team, vergaderingen en chats gebruiken en samenwerken aan teambestanden.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="ed9f9-140">Nieuwe bestanden maken in het team en nieuwe bestanden uploaden die lokaal zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="ed9f9-141">Een demonstratie van hoe het DLP-beleid blokkeert dat bestanden extern worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="ed9f9-142">Bestanden labelen met het label Project 2X-gevoeligheid.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="ed9f9-143">Een demonstratie van hoe het Project 2X-label een bestand beschermt, zelfs wanneer het team verlaat.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="ed9f9-144">Het eindresultaat was een veilige omgeving waarin Project 2X-teamleden samenwerkten in een veilige omgeving voor chats, vergaderingen en bestanden.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="ed9f9-145">In een paar gevallen hebben project 2X-teamleden bestanden die door het Project 2X-label zijn beveiligd, gedownload naar een lokale schijf voor offline werk.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="ed9f9-146">Echter, na te zijn gevraagd om referenties bij het openen van hen, realiseerden ze hun fout en verwijderde ze.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="ed9f9-147">Vanwege de samenwerkingsomgeving van Teams en de beveiligingsfuncties van Microsoft 365 werden de details van Project 2X geheim gehouden voor de duur van het project.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="ed9f9-148">Contoso kondigde haar plannen aan en is bezig met de uitrol van de nieuwe producten en diensten tot grote vreugde van haar klanten en investeerders en de ergernis van haar concurrenten.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="ed9f9-149">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="ed9f9-149">Next step</span></span>

<span data-ttu-id="ed9f9-150">[Implementeren](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ed9f9-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed9f9-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ed9f9-151">See also</span></span>

<span data-ttu-id="ed9f9-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="ed9f9-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
