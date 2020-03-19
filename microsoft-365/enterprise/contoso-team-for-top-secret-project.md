---
title: Team voor een topgeheim project van de Contoso Corporation
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
description: 'Samenvatting: Hoe Contoso een team gebruikte voor sterk gereguleerde gegevens voor een topgeheim project om een nieuwe suite van producten en diensten te ontwikkelen.'
ms.openlocfilehash: 58d381751db3e94f35a0c1b8f7a14c191918e754
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805717"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="c68ca-103">Team voor een topgeheim project van de Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="c68ca-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="c68ca-104">Na een executive offsite, contoso's CEO bestelde de ontwikkeling van een nieuwe suite van producten en diensten die contoso's winst zou kunnen verdubbelen in de komende vijf jaar.</span><span class="sxs-lookup"><span data-stu-id="c68ca-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="c68ca-105">Het topgeheime project voor de ontwikkeling van het business, engineering en marktplan kreeg de naam **Project 2X** en belangrijke medewerkers in het hele bedrijf werden aangeworven.</span><span class="sxs-lookup"><span data-stu-id="c68ca-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="c68ca-106">De tijdlijnen voor onderzoek en ontwikkeling waren krap, wat betekende dat de samenwerking efficiënt moest zijn en veilige vergaderingen, lopende gesprekken en bestandsopslag moest bieden.</span><span class="sxs-lookup"><span data-stu-id="c68ca-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="c68ca-107">De resulterende deliverables voor Project 2X waren bedrijfsplannen, product- en technische specificaties en marketingmateriaal en -schema's in de vorm van Word-, Excel- en PowerPoint-bestanden.</span><span class="sxs-lookup"><span data-stu-id="c68ca-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="c68ca-108">Vanwege hun gevoelige aard, de toegang tot deze bestanden waren:</span><span class="sxs-lookup"><span data-stu-id="c68ca-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="c68ca-109">Beperkt tot Project 2X-teamleden.</span><span class="sxs-lookup"><span data-stu-id="c68ca-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="c68ca-110">Beschermd met een DLP-beleid (Data Loss Prevention) om te voorkomen dat Project 2X-teamleden ze buiten het team delen.</span><span class="sxs-lookup"><span data-stu-id="c68ca-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="c68ca-111">Versleuteld en beveiligd met machtigingen om alleen toegang toe te staan aan Project 2X-teamleden, zelfs als de bestanden buiten Contoso zijn gedistribueerd.</span><span class="sxs-lookup"><span data-stu-id="c68ca-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="c68ca-112">Contoso IT-medewerkers gebruikten een [team voor sterk gereguleerde gegevens](secure-teams-highly-regulated-data-scenario.md) voor Project 2X en deze stappen.</span><span class="sxs-lookup"><span data-stu-id="c68ca-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="c68ca-113">Stap 1: Een privéteam maken en de onderliggende SharePoint-site vergrendeld</span><span class="sxs-lookup"><span data-stu-id="c68ca-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="c68ca-114">Om de toegang tot de onderliggende SharePoint-site voor het team te beschermen, hebben Contoso IT-beheerders het [aanbevolen SharePoint-toegangsbeleid](sharepoint-file-access-policies.md)geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="c68ca-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="c68ca-115">Vervolgens heeft een Contoso IT-beheerder een nieuw privéteam gemaakt met de naam Project 2X en de gebruikersaccounts van Project 2X-medewerkers toegevoegd als leden.</span><span class="sxs-lookup"><span data-stu-id="c68ca-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="c68ca-116">Vervolgens hebben ze aanvullende machtigingsinstellingen voor de site geconfigureerd om te voorkomen dat Project 2X toegang tot de site kan delen en om te voorkomen dat andere toegang tot de site zouden aanvragen.</span><span class="sxs-lookup"><span data-stu-id="c68ca-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="c68ca-117">Zie [SharePoint-instellingen voor een sterk gereguleerd team voor](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams)de configuratiegegevens.</span><span class="sxs-lookup"><span data-stu-id="c68ca-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="c68ca-118">Stap 2: Een DLP-beleid en de onderliggende site voor een bewaarlabel geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="c68ca-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="c68ca-119">Ten eerste hebben Contoso-beheerders het bestaande **zeer vertrouwelijke** Office 365-bewaarlabel toegepast op de sectie **Documenten** van de onderliggende SharePoint-site van het Project 2X-team.</span><span class="sxs-lookup"><span data-stu-id="c68ca-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="c68ca-120">Vervolgens hebben ze een nieuw Office 365 DLP-beleid gemaakt met de naam **Project 2X,** dat:</span><span class="sxs-lookup"><span data-stu-id="c68ca-120">Next, they created a new Office 365 DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="c68ca-121">Gebruikt het bewaarlabel Zeer vertrouwelijk Office 365.</span><span class="sxs-lookup"><span data-stu-id="c68ca-121">Uses the Highly Confidential Office 365 retention label.</span></span>
- <span data-ttu-id="c68ca-122">Hiermee blokkeert u gebruikers wanneer ze een bestand proberen te delen in het Project 2X-team buiten Contoso.</span><span class="sxs-lookup"><span data-stu-id="c68ca-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="c68ca-123">Zie Bestanden beveiligen [in teams met bewaarlabels en DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)voor de configuratiegegevens.</span><span class="sxs-lookup"><span data-stu-id="c68ca-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="c68ca-124">Stap 3: Een Office 365-gevoeligheidslabel gemaakt voor het Project 2X-team</span><span class="sxs-lookup"><span data-stu-id="c68ca-124">Step 3: Created an Office 365 sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="c68ca-125">Contoso-beheerders hebben een nieuw Office 365-gevoeligheidslabel gemaakt met de naam **Project 2X,** dat:</span><span class="sxs-lookup"><span data-stu-id="c68ca-125">Contoso admins created a new Office 365 sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="c68ca-126">Vereist encryptie.</span><span class="sxs-lookup"><span data-stu-id="c68ca-126">Requires encryption.</span></span>
- <span data-ttu-id="c68ca-127">Hiermee u machtigingen voor co-auteur toestaan voor de groep Project 2X Office 365.</span><span class="sxs-lookup"><span data-stu-id="c68ca-127">Allows Co-Author permissions for the Project 2X Office 365 group.</span></span>

<span data-ttu-id="c68ca-128">Hier is de resulterende configuratie van het Project 2X-team.</span><span class="sxs-lookup"><span data-stu-id="c68ca-128">Here is the resulting configuration of the Project 2X team.</span></span>

![De resulterende configuratie van het Project 2X-team](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="c68ca-130">Bestanden in de sectie Documenten van de onderliggende SharePoint-site project 2X zijn beveiligd door:</span><span class="sxs-lookup"><span data-stu-id="c68ca-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="c68ca-131">De sitemachtigingen, die alleen toegang geven tot leden van de Groep Project 2X Office 365.</span><span class="sxs-lookup"><span data-stu-id="c68ca-131">The site permissions, which only allow access to members of the Project 2X Office 365 group.</span></span>
- <span data-ttu-id="c68ca-132">Het zeer vertrouwelijke bewaarlabel, dat automatisch wordt toegewezen aan nieuwe bestanden.</span><span class="sxs-lookup"><span data-stu-id="c68ca-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="c68ca-133">Een DLP-beleid dat het label en de instellingen voor zeer vertrouwelijk bewaaren gebruikt die blokkeren dat het bestand wordt gedeeld met externe gebruikers.</span><span class="sxs-lookup"><span data-stu-id="c68ca-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="c68ca-134">Het project 2x-gevoeligheidslabel, met versleuteling en machtigingen die met het bestand worden meegenomen als het van de site wordt verplaatst of gekopieerd.</span><span class="sxs-lookup"><span data-stu-id="c68ca-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="c68ca-135">Hier is een voorbeeld van een bestand dat is opgeslagen op de onderliggende Project 2X-site met het hooggereguleerde retentielabel en het toegewezen Label voor gevoeligheid van Project 2X.</span><span class="sxs-lookup"><span data-stu-id="c68ca-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![Een voorbeeld van een bestand dat is opgeslagen op de onderliggende Project 2X-site](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="c68ca-137">Stap 4: Getraind Project 2X teamleden</span><span class="sxs-lookup"><span data-stu-id="c68ca-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="c68ca-138">Contoso security medewerkers trainde de Project 2X teamleden in een verplichte cursus die hen door:</span><span class="sxs-lookup"><span data-stu-id="c68ca-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="c68ca-139">Toegang krijgen tot het nieuwe Project 2X-team, vergaderingen en chats gebruiken en samenwerken aan teambestanden.</span><span class="sxs-lookup"><span data-stu-id="c68ca-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="c68ca-140">Nieuwe bestanden maken in het team en nieuwe bestanden uploaden die lokaal zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="c68ca-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="c68ca-141">Een demonstratie van hoe het DLP-beleid voorkomt dat bestanden extern worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="c68ca-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="c68ca-142">Bestanden labelen met het label Project 2X sensitivity.</span><span class="sxs-lookup"><span data-stu-id="c68ca-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="c68ca-143">Een demonstratie van hoe het Project 2X-label een bestand beschermt, zelfs wanneer het het team verlaat.</span><span class="sxs-lookup"><span data-stu-id="c68ca-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="c68ca-144">Het eindresultaat was een veilige omgeving waarin Project 2X-teamleden samenwerkten in een beveiligde omgeving voor chats, vergaderingen en bestanden.</span><span class="sxs-lookup"><span data-stu-id="c68ca-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="c68ca-145">In een paar gevallen hebben Project 2X-teamleden bestanden gedownload die door het Project 2X-label zijn beveiligd, naar een lokaal station voor offline werk.</span><span class="sxs-lookup"><span data-stu-id="c68ca-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="c68ca-146">Echter, na te zijn gevraagd voor referenties bij het openen van hen, realiseerden ze hun fout en verwijderde ze.</span><span class="sxs-lookup"><span data-stu-id="c68ca-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="c68ca-147">Vanwege de samenwerkingsomgeving van Teams en de beveiligingsfuncties van Microsoft 365 werden de details van Project 2X geheim gehouden voor de duur van het project.</span><span class="sxs-lookup"><span data-stu-id="c68ca-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="c68ca-148">Contoso kondigde haar plannen aan en is bezig met de uitrol van de nieuwe producten en diensten tot grote vreugde van haar klanten en investeerders en de ergernis van haar concurrenten.</span><span class="sxs-lookup"><span data-stu-id="c68ca-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="c68ca-149">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="c68ca-149">Next step</span></span>

<span data-ttu-id="c68ca-150">[Implementeren](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c68ca-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="c68ca-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c68ca-151">See also</span></span>

<span data-ttu-id="c68ca-152">[Microsoft 365-productiviteitsbibliotheek](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="c68ca-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
