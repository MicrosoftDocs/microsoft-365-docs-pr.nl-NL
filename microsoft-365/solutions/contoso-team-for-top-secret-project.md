---
title: Geïsoleerd team voor een topgeheim project van de Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Samenvatting: Hoe Contoso een team met beveiligingsisolatie voor een topgeheim project heeft gebruikt om een nieuwe suite met producten en services te ontwikkelen.'
ms.openlocfilehash: d5ab2808251ff6a53f8975ea868431691d3301e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051004"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="0a5c4-103">Geïsoleerd team voor een topgeheim project van de Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="0a5c4-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="0a5c4-104">Nadat de CEO van Contoso een executive offsite had gemaakt, heeft de CEO van Contoso opdracht gegeven een nieuwe suite met producten en services te ontwikkelen die de winst van Contoso in de komende vijf jaar zou kunnen verdubbelen.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="0a5c4-105">Het topgeheime project voor het ontwikkelen van het bedrijfs-, technische en marktplan kreeg de naam **Project 2X** en belangrijke personeelsleden in het hele bedrijf zijn aangeworven.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="0a5c4-106">De tijdlijnen voor onderzoek en ontwikkeling waren strak, wat betekent dat de samenwerking efficiënt moest zijn en veilige vergaderingen, lopende gesprekken en bestandsopslag moest bieden.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="0a5c4-107">De resulterende producten voor Project 2X waren bedrijfsplannen, product- en technische specificaties en marketingmaterialen en -planningen in de vorm van Word-, Excel- en PowerPoint-bestanden.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="0a5c4-108">Vanwege hun gevoelige aard waren de volgende bestanden toegankelijk:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="0a5c4-109">Beperkt tot Project 2X-teamleden en senior leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="0a5c4-110">Versleuteld en beveiligd met machtigingen om alleen toegang toe te staan aan Project 2X-teamleden en senior leidinggevenden, zelfs als de bestanden buiten hun beveiligde mappen zijn gedistribueerd.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="0a5c4-111">It-medewerkers van Contoso hebben een [team gebruikt met beveiligingsisolatie](secure-teams-security-isolation.md) voor Project 2X en deze stappen.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="0a5c4-112">Stap 1: Een privéteam gemaakt</span><span class="sxs-lookup"><span data-stu-id="0a5c4-112">Step 1: Created a private team</span></span>

<span data-ttu-id="0a5c4-113">Om de toegang tot de onderliggende SharePoint-site voor het team te beveiligen, hebben IT-beheerders van Contoso het aanbevolen [SharePoint-toegangsbeleid geconfigureerd.](../security/defender-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0a5c4-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="0a5c4-114">Vervolgens heeft een CONTOSO-IT-beheerder een nieuw privéteam met de naam Project 2X gemaakt en de gebruikersaccounts van Project 2X-medewerkers toegevoegd als leden.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="0a5c4-115">Ze hebben het team ook zo geconfigureerd dat alleen project 2X-teameigenaren privékanalen kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="0a5c4-116">Zie Een privéteam maken voor de [configuratiegegevens.](secure-teams-security-isolation.md#create-a-private-team)</span><span class="sxs-lookup"><span data-stu-id="0a5c4-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="0a5c4-117">Stap 2: Een gevoeligheidslabel gemaakt voor het Project 2X-team</span><span class="sxs-lookup"><span data-stu-id="0a5c4-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="0a5c4-118">Contoso-beheerders hebben een nieuw gevoeligheidslabel met de naam **Project 2X** gemaakt dat:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="0a5c4-119">Ingeschakelde versleuteling.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-119">Enabled encryption.</span></span>
- <span data-ttu-id="0a5c4-120">Toegestane Co-Author voor de Project 2X Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="0a5c4-121">Machtigingen voor Viewer toegestaan voor de groep Senior Leadership.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="0a5c4-122">Geblokkeerde toegang tot niet-bemande apparaten.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="0a5c4-123">Bestanden in de **sectie Documenten** van de onderliggende Project 2X SharePoint-site zijn beveiligd door:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="0a5c4-124">De sitemachtigingen, die alleen volledige machtigingen toestaan voor leden van de Project 2X Microsoft 365-groep en leesmachtigingen voor de groep Senior Leadership.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="0a5c4-125">Het gevoeligheidslabel Project 2X, met versleuteling en machtigingen die met het bestand worden verplaatst of gekopieerd van de site.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="0a5c4-126">Zie Een gevoeligheidslabel maken voor de [configuratiedetails.](secure-teams-security-isolation.md#create-a-sensitivity-label)</span><span class="sxs-lookup"><span data-stu-id="0a5c4-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="0a5c4-127">Stap 3: De onderliggende SharePoint-site configureren</span><span class="sxs-lookup"><span data-stu-id="0a5c4-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="0a5c4-128">Om de toegang tot de onderliggende SharePoint-site voor het team te beveiligen, hebben IT-beheerders van Contoso het aanbevolen [SharePoint-toegangsbeleid geconfigureerd.](../security/defender-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0a5c4-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="0a5c4-129">Vervolgens hebben ze aanvullende machtigingsinstellingen voor de site geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="0a5c4-130">Om te voorkomen dat leden van de Project 2X-groep toegang tot de site kunnen delen.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="0a5c4-131">Zie SharePoint-instellingen voor een team met beveiligingsisolatie voor de [configuratiegegevens.](secure-teams-security-isolation.md#sharepoint-settings)</span><span class="sxs-lookup"><span data-stu-id="0a5c4-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="0a5c4-132">Voor leesmachtigingen voor de groep Senior Leadership.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="0a5c4-133">Vervolgens hebben ze aanvullende machtigingsinstellingen voor de site geconfigureerd om te voorkomen dat project 2X-groepsleden toegang tot de site kunnen delen.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="0a5c4-134">Aangezien er privékanalen voor Project 2X zijn gemaakt, heeft de groepseigenaar het delen van gasten uitgeschakeld en de standaardkoppeling voor delen ingesteld voor **de waarde Specifieke** personen.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="0a5c4-135">Hier is de resulterende configuratie van het Project 2X-team met beveiligingsisolatie.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![De resulterende configuratie van het Project 2X-team](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="0a5c4-137">Stap 4: Getrainde Project 2X-teamleden</span><span class="sxs-lookup"><span data-stu-id="0a5c4-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="0a5c4-138">De beveiligingsmedewerkers van Contoso hebben de Project 2X-teamleden opgeleid in een verplichte cursus waarin ze het volgende hebben geleerd:</span><span class="sxs-lookup"><span data-stu-id="0a5c4-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="0a5c4-139">Toegang krijgen tot het nieuwe Project 2X-team, vergaderingen en chats gebruiken en samenwerken aan teambestanden.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="0a5c4-140">Nieuwe bestanden in het team maken en nieuwe bestanden uploaden die lokaal zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="0a5c4-141">Bestanden labelen met het gevoeligheidslabel project 2X.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="0a5c4-142">Een demonstratie van hoe het label Project 2X een bestand beschermt, zelfs wanneer het het team verlaat.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="0a5c4-143">Het eindresultaat was een veilige omgeving waarin Project 2X-teamleden samenwerkten in een veilige omgeving voor chats, vergaderingen en bestanden.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="0a5c4-144">Hier is een voorbeeld van een bestand dat is opgeslagen op de onderliggende Project 2X-site met het gevoeligheidslabel Project 2X toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Een voorbeeld van een bestand dat is opgeslagen op de onderliggende Project 2X-site](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="0a5c4-146">In een paar gevallen hebben project 2X-teamleden bestanden gedownload die zijn beveiligd met het label Project 2X naar een lokaal station voor offlinewerk.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="0a5c4-147">Nadat ze bij het openen van de referenties echter om referenties waren gevraagd, beseften ze hun fout en verwijderden ze ze.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="0a5c4-148">Vanwege de samenwerkingsomgeving van Teams en de beveiligingsfuncties van Microsoft 365 zijn de details van Project 2X geheim gehouden gedurende de duur van het project.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="0a5c4-149">Contoso heeft haar plannen aangekondigd en is bezig met de uitrol van de nieuwe producten en services tot grote vreugde van haar klanten en investeerders en tot ergernis van haar concurrenten.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="0a5c4-150">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0a5c4-150">Next step</span></span>

<span data-ttu-id="0a5c4-151">[Implementeer een team met beveiligingsisolatie](secure-teams-security-isolation.md) in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0a5c4-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

