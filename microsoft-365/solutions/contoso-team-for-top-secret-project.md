---
title: Geïsoleerd team voor een topgeheim project van de Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Samenvatting: Hoe Contoso een team met beveiligingsisolatie gebruikte voor een topgeheim project om een nieuwe reeks producten en diensten te ontwikkelen.'
ms.openlocfilehash: 2da51890001a2890b2d65bc6b71537b51c335eb4
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002773"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="557e7-103">Geïsoleerd team voor een topgeheim project van de Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="557e7-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="557e7-104">Na een executive offsite, Contoso's CEO beval de ontwikkeling van een nieuwe suite van producten en diensten die de winst van Contoso zou kunnen verdubbelen in de komende vijf jaar.</span><span class="sxs-lookup"><span data-stu-id="557e7-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="557e7-105">Het topgeheime project voor de ontwikkeling van het bedrijfs-, engineering- en marktplan kreeg de naam **Project 2X** en belangrijke medewerkers in het hele bedrijf werden aangeworven.</span><span class="sxs-lookup"><span data-stu-id="557e7-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="557e7-106">De tijdlijnen voor onderzoek en ontwikkeling waren strak, wat betekende dat samenwerking efficiënt moest zijn en moest zorgen voor veilige vergaderingen, lopende gesprekken en bestandsopslag.</span><span class="sxs-lookup"><span data-stu-id="557e7-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="557e7-107">De resulterende deliverables voor Project 2X waren bedrijfsplannen, product- en engineeringspecificaties en marketingmaterialen en -schema's in de vorm van Word-, Excel- en PowerPoint-bestanden.</span><span class="sxs-lookup"><span data-stu-id="557e7-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="557e7-108">Vanwege hun gevoelige aard, de toegang tot deze bestanden waren:</span><span class="sxs-lookup"><span data-stu-id="557e7-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="557e7-109">Beperkt tot Project 2X-teamleden.</span><span class="sxs-lookup"><span data-stu-id="557e7-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="557e7-110">Versleuteld en beveiligd met machtigingen om alleen toegang te verlenen aan Project 2X-teamleden, zelfs als de bestanden buiten hun beveiligde mappen zijn gedistribueerd.</span><span class="sxs-lookup"><span data-stu-id="557e7-110">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="557e7-111">Het IT-personeel van Contoso maakte voor Project 2X en deze stappen gebruik van een [team met beveiligingsisolatie.](secure-teams-security-isolation.md)</span><span class="sxs-lookup"><span data-stu-id="557e7-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="557e7-112">Stap 1: Een privéteam maken</span><span class="sxs-lookup"><span data-stu-id="557e7-112">Step 1: Created a private team</span></span>

<span data-ttu-id="557e7-113">Ten eerste, om de toegang tot de onderliggende SharePoint-site voor het team te beschermen, hebben De IT-beheerders van Contoso het [aanbevolen SharePoint-toegangsbeleid](../enterprise/sharepoint-file-access-policies.md)geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="557e7-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="557e7-114">Vervolgens heeft een It-beheerder van Contoso een nieuw privéteam met de naam Project 2X gemaakt en de gebruikersaccounts van Project 2X-medewerkers als leden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="557e7-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="557e7-115">Zie [Een privéteam maken](secure-teams-security-isolation.md#create-a-private-team)voor de configuratiegegevens.</span><span class="sxs-lookup"><span data-stu-id="557e7-115">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="557e7-116">Stap 2: Een gevoeligheidslabel maken voor het Project 2X-team</span><span class="sxs-lookup"><span data-stu-id="557e7-116">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="557e7-117">Contoso-beheerders hebben een nieuw gevoeligheidslabel gemaakt met de naam **Project 2X** dat:</span><span class="sxs-lookup"><span data-stu-id="557e7-117">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="557e7-118">Vereist versleuteling.</span><span class="sxs-lookup"><span data-stu-id="557e7-118">Requires encryption.</span></span>
- <span data-ttu-id="557e7-119">Hiermee kunnen machtigingen voor co-auteur worden toegestaan voor de Project 2X Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="557e7-119">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="557e7-120">Bestanden in de sectie **Documenten** van de onderliggende Project 2X SharePoint-site zijn beveiligd door:</span><span class="sxs-lookup"><span data-stu-id="557e7-120">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="557e7-121">De sitemachtigingen, die alleen toegang geven tot leden van de Project 2X Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="557e7-121">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="557e7-122">Het label Voor de gevoeligheid van Project 2X, met versleuteling en machtigingen die met het bestand reizen als het wordt verplaatst of gekopieerd van de site.</span><span class="sxs-lookup"><span data-stu-id="557e7-122">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="557e7-123">Zie [Een gevoeligheidslabel maken](secure-teams-security-isolation.md#create-a-sensitivity-label)voor de configuratiedetails.</span><span class="sxs-lookup"><span data-stu-id="557e7-123">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="557e7-124">Stap 3: De onderliggende SharePoint-site configureren</span><span class="sxs-lookup"><span data-stu-id="557e7-124">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="557e7-125">Ten eerste, om de toegang tot de onderliggende SharePoint-site voor het team te beschermen, hebben De IT-beheerders van Contoso het [aanbevolen SharePoint-toegangsbeleid](../enterprise/sharepoint-file-access-policies.md)geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="557e7-125">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="557e7-126">Vervolgens hebben ze extra machtigingsinstellingen voor de site geconfigureerd om te voorkomen dat Project 2X toegang tot de site deelt.</span><span class="sxs-lookup"><span data-stu-id="557e7-126">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site.</span></span> <span data-ttu-id="557e7-127">Zie [SharePoint-instellingen voor een team met beveiligingsisolatie voor](secure-teams-security-isolation.md#sharepoint-settings)de configuratiegegevens.</span><span class="sxs-lookup"><span data-stu-id="557e7-127">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>

<span data-ttu-id="557e7-128">Hier is de resulterende configuratie van het Project 2X-team.</span><span class="sxs-lookup"><span data-stu-id="557e7-128">Here is the resulting configuration of the Project 2X team.</span></span>

![De resulterende configuratie van het Project 2X-team](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="557e7-130">Stap 4: Getrainde Project 2X-teamleden</span><span class="sxs-lookup"><span data-stu-id="557e7-130">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="557e7-131">Contoso security medewerkers trainden de Project 2X teamleden in een verplichte cursus die hen door:</span><span class="sxs-lookup"><span data-stu-id="557e7-131">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="557e7-132">Hoe u toegang krijgt tot het nieuwe Project 2X-team, vergaderingen en chats gebruiken en samenwerken aan teambestanden.</span><span class="sxs-lookup"><span data-stu-id="557e7-132">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="557e7-133">Nieuwe bestanden maken in het team en nieuwe bestanden uploaden die lokaal zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="557e7-133">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="557e7-134">Een demonstratie van hoe het DLP-beleid blokkeert dat bestanden extern worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="557e7-134">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="557e7-135">Bestanden labelen met het label Project 2X-gevoeligheid.</span><span class="sxs-lookup"><span data-stu-id="557e7-135">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="557e7-136">Een demonstratie van hoe het Project 2X-label een bestand beschermt, zelfs wanneer het team verlaat.</span><span class="sxs-lookup"><span data-stu-id="557e7-136">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="557e7-137">Het eindresultaat was een veilige omgeving waarin Project 2X-teamleden samenwerkten in een veilige omgeving voor chats, vergaderingen en bestanden.</span><span class="sxs-lookup"><span data-stu-id="557e7-137">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="557e7-138">Hier vindt u een voorbeeld van een bestand dat is opgeslagen in de onderliggende Project 2X-site met het label Project 2X-gevoeligheid toegewezen.</span><span class="sxs-lookup"><span data-stu-id="557e7-138">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Een voorbeeld van een bestand dat is opgeslagen in de onderliggende Project 2X-site](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="557e7-140">In een paar gevallen hebben project 2X-teamleden bestanden die door het Project 2X-label zijn beveiligd, gedownload naar een lokale schijf voor offline werk.</span><span class="sxs-lookup"><span data-stu-id="557e7-140">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="557e7-141">Echter, na te zijn gevraagd om referenties bij het openen van hen, realiseerden ze hun fout en verwijderde ze.</span><span class="sxs-lookup"><span data-stu-id="557e7-141">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="557e7-142">Vanwege de samenwerkingsomgeving van Teams en de beveiligingsfuncties van Microsoft 365 werden de details van Project 2X geheim gehouden voor de duur van het project.</span><span class="sxs-lookup"><span data-stu-id="557e7-142">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="557e7-143">Contoso kondigde haar plannen aan en is bezig met de uitrol van de nieuwe producten en diensten tot grote vreugde van haar klanten en investeerders en de ergernis van haar concurrenten.</span><span class="sxs-lookup"><span data-stu-id="557e7-143">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="557e7-144">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="557e7-144">Next step</span></span>

<span data-ttu-id="557e7-145">[Implementeer een team met beveiligingsisolatie](secure-teams-security-isolation.md) in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="557e7-145">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

