---
title: Geïsoleerd team voor een hoofd-geheim project van Contoso B.v.
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
description: 'Overzicht: hoe contoso een team gebruikte met behulp van beveiligings isolatie voor een hoofd-geheim project om een nieuwe suite met producten en services te ontwikkelen.'
ms.openlocfilehash: 16d10f5d6e5b5939172c02746c9324eb20b6987e
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399487"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="19643-103">Geïsoleerd team voor een hoofd-geheim project van Contoso B.v.</span><span class="sxs-lookup"><span data-stu-id="19643-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="19643-104">Na een uitvoerend manager heeft de directeur van Contoso de ontwikkeling van een nieuwe suite van producten en diensten besteld die in de komende vijf jaar de winstgevendste functies kon opleveren.</span><span class="sxs-lookup"><span data-stu-id="19643-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="19643-105">Het belangrijkste geheim project voor het ontwikkelen van het bedrijf, de engineering en de markt van een markt met name **project** , IT-medewerkers en IT-medewerkers zijn gewerfd.</span><span class="sxs-lookup"><span data-stu-id="19643-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="19643-106">De tijdlijnen voor onderzoek en ontwikkeling waren strak, wat bedoeld voor de samenwerking en het zorgen voor veilig vergaderen, lopende gesprekken en bestandsopslag.</span><span class="sxs-lookup"><span data-stu-id="19643-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="19643-107">De resultaten van project 2X waren bedrijfsplannen, specificaties van producten en technische specificaties, en marketingmaterialen en planningen in de vorm van Word-, Excel-en PowerPoint-bestanden.</span><span class="sxs-lookup"><span data-stu-id="19643-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="19643-108">Vanwege hun gevoelige aard zijn de toegang tot deze bestanden:</span><span class="sxs-lookup"><span data-stu-id="19643-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="19643-109">Beperkt tot project en teamleden en senior leiderschap.</span><span class="sxs-lookup"><span data-stu-id="19643-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="19643-110">Versleuteld en beveiligd met machtigingen voor toegang tot project en de teamleden en senior leiderschap, zelfs als de bestanden buiten hun beveiligde mappen zijn gedistribueerd.</span><span class="sxs-lookup"><span data-stu-id="19643-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="19643-111">Contoso IT-personeel heeft een [team gebruikt met beveiligings isolatie](secure-teams-security-isolation.md) voor project 2 en deze stappen.</span><span class="sxs-lookup"><span data-stu-id="19643-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="19643-112">Stap 1: een privé team maken</span><span class="sxs-lookup"><span data-stu-id="19643-112">Step 1: Created a private team</span></span>

<span data-ttu-id="19643-113">Als u de toegang tot de onderliggende SharePoint-site voor het team wilt beveiligen, zijn de beheerders van Contoso IT de [Aanbevolen beleidsregels voor toegang tot SharePoint](../security/office-365-security/sharepoint-file-access-policies.md)geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="19643-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="19643-114">Vervolgens heeft een contoso IT-beheerder een nieuw privé team gemaakt met de naam Project 2 en worden de gebruikersaccounts van project en de werknemers toegevoegd als leden.</span><span class="sxs-lookup"><span data-stu-id="19643-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="19643-115">Ze hebben ook het team geconfigureerd, zodat alleen project van team eigenaren persoonlijke kanalen kan maken.</span><span class="sxs-lookup"><span data-stu-id="19643-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="19643-116">Zie [een privé team maken](secure-teams-security-isolation.md#create-a-private-team)voor meer informatie over de configuratie.</span><span class="sxs-lookup"><span data-stu-id="19643-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="19643-117">Stap 2: een gevoeligheids label voor het project, 2 en team maken</span><span class="sxs-lookup"><span data-stu-id="19643-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="19643-118">Contoso-beheerders hebben een nieuwe vertrouwelijkheids label gemaakt, met de naam **Project 2** :</span><span class="sxs-lookup"><span data-stu-id="19643-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="19643-119">Versleuteling ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="19643-119">Enabled encryption.</span></span>
- <span data-ttu-id="19643-120">Machtigingen voor Co-Author toegestaan voor de groep project 2 en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19643-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="19643-121">Toegestane Viewer machtigingen voor de Senior leiderschaps groep.</span><span class="sxs-lookup"><span data-stu-id="19643-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="19643-122">Toegang tot niet-beheerde apparaten is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="19643-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="19643-123">Bestanden in de sectie **documenten** van het onderliggende project van de SharePoint-site zijn beschermd door:</span><span class="sxs-lookup"><span data-stu-id="19643-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="19643-124">De site machtigingen, die alleen volledige machtigingen toestaan voor leden van het project en de Microsoft 365-groep en machtigingen voor lezen voor de Senior leiderschaps groep.</span><span class="sxs-lookup"><span data-stu-id="19643-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="19643-125">Het bestand voor de vertrouwelijkheids label van het project en de machtigingen die met het bestand worden verplaatst of gekopieerd van de site.</span><span class="sxs-lookup"><span data-stu-id="19643-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="19643-126">Zie [een gevoeligheids label maken](secure-teams-security-isolation.md#create-a-sensitivity-label)voor meer informatie over de configuratie.</span><span class="sxs-lookup"><span data-stu-id="19643-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="19643-127">Stap 3: de onderliggende SharePoint-site is geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="19643-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="19643-128">Als u de toegang tot de onderliggende SharePoint-site voor het team wilt beveiligen, zijn de beheerders van Contoso IT de [Aanbevolen beleidsregels voor toegang tot SharePoint](../security/office-365-security/sharepoint-file-access-policies.md)geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="19643-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="19643-129">Vervolgens hebben ze extra machtigingsinstellingen voor de site geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="19643-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="19643-130">Om te voorkomen dat project en groepsleden toegang kunnen delen tot de site.</span><span class="sxs-lookup"><span data-stu-id="19643-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="19643-131">Zie voor meer informatie over de configuratie van [SharePoint-instellingen voor een team met beveiligings isolatie](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="19643-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="19643-132">Voor leesmachtigingen voor de Senior leiderschaps groep.</span><span class="sxs-lookup"><span data-stu-id="19643-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="19643-133">Vervolgens hebben ze extra machtigingsinstellingen voor de site geconfigureerd om te voorkomen dat project en groepsleden toegang kunnen delen tot de site.</span><span class="sxs-lookup"><span data-stu-id="19643-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="19643-134">Als private-kanalen voor het project van twee 2X werden gemaakt, zijn de groepseigenaren uitgeschakeld voor het delen van gasten en stelt u de standaardkoppeling voordelen in op de waarde van **bepaalde personen** .</span><span class="sxs-lookup"><span data-stu-id="19643-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="19643-135">Dit is de uitkomst van de configuratie van het project en het team en het team van beveiligings isolatie.</span><span class="sxs-lookup"><span data-stu-id="19643-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![De resultaten configuratie van het project en het team.](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="19643-137">Stap 4: opgeleid project van teamleden</span><span class="sxs-lookup"><span data-stu-id="19643-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="19643-138">Contoso beveiligingspersoneel heeft het project en de teamleden getraind in een verplichte cursus waarin ze worden getrapt:</span><span class="sxs-lookup"><span data-stu-id="19643-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="19643-139">U kunt toegang krijgen tot het nieuwe project van het team, van vergaderingen en chats, en hoe u kunt samenwerken aan team bestanden.</span><span class="sxs-lookup"><span data-stu-id="19643-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="19643-140">Het maken van nieuwe bestanden in het team en het uploaden van nieuwe bestanden die lokaal zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="19643-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="19643-141">Een label voor het delen van bestanden met het vertrouwelijkheids label van project 2.</span><span class="sxs-lookup"><span data-stu-id="19643-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="19643-142">In dit voorblad kunt u zien hoe het project en het label een bestand beschermt, zelfs als het team van het team valt.</span><span class="sxs-lookup"><span data-stu-id="19643-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="19643-143">Het eindresultaat is een veilige omgeving waarin project van teamleden in een beveiligde omgeving is samengewerkt voor chat gesprekken, vergaderingen en bestanden.</span><span class="sxs-lookup"><span data-stu-id="19643-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="19643-144">Hier ziet u een voorbeeld van een bestand dat is opgeslagen in het onderliggende project en de site van het onderliggende project.</span><span class="sxs-lookup"><span data-stu-id="19643-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Een voorbeeld van een bestand dat is opgeslagen in het onderliggende project van de site.](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="19643-146">In een aantal gevallen hebben project en teamleden gedownloade bestanden die zijn beveiligd door het project en het label voor een lokaal station voor offline werken.</span><span class="sxs-lookup"><span data-stu-id="19643-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="19643-147">Wanneer u de persoon opent, kunt u zich echter eerst een foutmelding krijgen en de referenties verwijderen.</span><span class="sxs-lookup"><span data-stu-id="19643-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="19643-148">Vanwege de samenwerkingsomgeving van teams en de beveiligingsfuncties van Microsoft 365, zijn de details van project 2X lang geheim voor de duur van het project.</span><span class="sxs-lookup"><span data-stu-id="19643-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="19643-149">Contoso heeft zijn of haar plannen bekendgemaakt en is bezig met de implementatie van de nieuwe producten en diensten in het licht van zijn klanten en beleggers en de Chagrin van zijn concurrenten.</span><span class="sxs-lookup"><span data-stu-id="19643-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="19643-150">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="19643-150">Next step</span></span>

<span data-ttu-id="19643-151">[Implementeer een team met beveiligings isolatie](secure-teams-security-isolation.md) in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="19643-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

