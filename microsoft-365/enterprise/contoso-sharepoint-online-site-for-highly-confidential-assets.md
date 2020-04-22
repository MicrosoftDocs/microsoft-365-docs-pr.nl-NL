---
title: SharePoint-site voor zeer vertrouwelijke digitale activa van de Contoso Corporation
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
description: 'Samenvatting: Hoe Contoso een SharePoint-site implementeerde voor sterk gereguleerde gegevens voor een eenvoudigere samenwerking tussen zijn onderzoeksteams.'
ms.openlocfilehash: 0a4bc2f685cf015611da62ebbed000218f37f31e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634250"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="bb5da-103">SharePoint-site voor zeer vertrouwelijke digitale activa van de Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="bb5da-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

<span data-ttu-id="bb5da-104">Contoso's meest waardevolle activa zijn de intellectuele eigendom in de vorm van bedrijfsgeheimen, zoals gepatenteerde productietechnieken, en ontwerpspecificaties voor producten die in ontwikkeling zijn.</span><span class="sxs-lookup"><span data-stu-id="bb5da-104">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="bb5da-105">Deze assets waren in digitale vorm, oorspronkelijk opgeslagen als bestanden op een SharePoint Server 2016-site.</span><span class="sxs-lookup"><span data-stu-id="bb5da-105">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="bb5da-106">Toen Contoso Microsoft 365 Enterprise inzette, wilden ze hun on-premises digitale assets naar de cloud overzetten voor gemakkelijkere toegang en meer open samenwerking tussen onderzoeksteams in Parijs, Moskou, New York, Beijing en Bangalore.</span><span class="sxs-lookup"><span data-stu-id="bb5da-106">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="bb5da-107">Vanwege hun gevoelige aard moet de toegang tot deze bestanden echter:</span><span class="sxs-lookup"><span data-stu-id="bb5da-107">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="bb5da-108">Beperkt tot de groep mensen die toegang hebben tot hen.</span><span class="sxs-lookup"><span data-stu-id="bb5da-108">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="bb5da-109">Beschermd met een DLP-beleid (Data Loss Prevention) om te voorkomen dat gebruikers ze buiten de site distribueren.</span><span class="sxs-lookup"><span data-stu-id="bb5da-109">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="bb5da-110">Versleuteld en beveiligd met machtigingen om te voorkomen dat onbevoegde gebruikers toegang krijgen tot hun inhoud, zelfs als ze buiten de site worden gedistribueerd.</span><span class="sxs-lookup"><span data-stu-id="bb5da-110">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="bb5da-111">Security- en SharePoint-beheerders in de IT-afdeling van Contoso besloten een [SharePoint-site](teams-sharepoint-online-sites-highly-regulated-data.md)te gebruiken voor sterk gereguleerde gegevens.</span><span class="sxs-lookup"><span data-stu-id="bb5da-111">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="bb5da-112">Contoso gebruikte deze stappen om een SharePoint-teamsites voor hun onderzoeksteams te maken en te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="bb5da-112">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="bb5da-113">Stap 1: Een eigen SharePoint-teamsite maken</span><span class="sxs-lookup"><span data-stu-id="bb5da-113">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="bb5da-114">Om de toegang tot de SharePoint-site te beschermen, heeft Contoso IT het [aanbevolen SharePoint-toegangsbeleid](sharepoint-file-access-policies.md)geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="bb5da-114">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="bb5da-115">Vervolgens stelden De it-beheerders van Contoso een lijst samen van de gebruikersaccounts van de onderzoekers in hun kantoren in Parijs, Moskou, New York, Beijing en Bangalore.</span><span class="sxs-lookup"><span data-stu-id="bb5da-115">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="bb5da-116">Vervolgens heeft een Contoso IT-beheerder een nieuwe privéteamsite met de naam **Research** gemaakt en alle gebruikersaccounts voor zijn onderzoekers toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="bb5da-116">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="bb5da-117">Vervolgens configureerden ze extra machtigingsinstellingen voor de site om te voorkomen dat onderzoekers toegang tot de site delen en om te voorkomen dat niet-onderzoekers toegang tot de site aanvragen.</span><span class="sxs-lookup"><span data-stu-id="bb5da-117">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="bb5da-118">Stap 2: De site configureren voor een restrictief DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="bb5da-118">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="bb5da-119">Ten eerste pasten Contoso-beheerders het bestaande **label voor zeer vertrouwelijke** bewaartoepassing toe op de map Documenten van de **onderzoekssite.**</span><span class="sxs-lookup"><span data-stu-id="bb5da-119">First, Contoso admins applied the existing **Highly Confidential** retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="bb5da-120">Vervolgens hebben ze een nieuw DLP-beleid gemaakt met de naam **Research** dat:</span><span class="sxs-lookup"><span data-stu-id="bb5da-120">Next, they created a new DLP policy named **Research** that:</span></span>

- <span data-ttu-id="bb5da-121">Gebruikt het **highly confidential** retention label.</span><span class="sxs-lookup"><span data-stu-id="bb5da-121">Uses the **Highly Confidential** retention label.</span></span> 
- <span data-ttu-id="bb5da-122">Blokkeert gebruikers wanneer ze proberen een digitaal actief te delen op de **onderzoekssite** buiten Contoso.</span><span class="sxs-lookup"><span data-stu-id="bb5da-122">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="bb5da-123">Zie [SharePoint-bestanden beveiligen met bewaarlabels en DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)voor de configuratiegegevens.</span><span class="sxs-lookup"><span data-stu-id="bb5da-123">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-3-created-a-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="bb5da-124">Stap 3: Een sublabel gevoeligheid voor de site maken</span><span class="sxs-lookup"><span data-stu-id="bb5da-124">Step 3: Created a sensitivity sublabel for the site</span></span>

<span data-ttu-id="bb5da-125">Contoso-beheerders hebben een nieuw sublabel voor gevoeligheid gemaakt met de naam **Research Teams** van het **label Highly Confidential** dat:</span><span class="sxs-lookup"><span data-stu-id="bb5da-125">Contoso admins created a new sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="bb5da-126">Vereist versleuteling.</span><span class="sxs-lookup"><span data-stu-id="bb5da-126">Requires encryption.</span></span>
- <span data-ttu-id="bb5da-127">Machtigingen voor co-auteur toestaan voor de **Groep Onderzoek** Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bb5da-127">Allows Co-Author permissions for the **Research** Microsoft 365 group</span></span>
- <span data-ttu-id="bb5da-128">Van toepassing op de **Groep Onderzoek** Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bb5da-128">Applies to the **Research** Microsoft 365 group</span></span>

<span data-ttu-id="bb5da-129">Hier is de resulterende configuratie van de **research** team site voor zeer vertrouwelijke activa.</span><span class="sxs-lookup"><span data-stu-id="bb5da-129">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![De resulterende configuratie van de research team site voor zeer vertrouwelijke activa](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="bb5da-131">Bestanden in mappen van de **onderzoekssite** worden beschermd door:</span><span class="sxs-lookup"><span data-stu-id="bb5da-131">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="bb5da-132">De sitemachtigingen, die alleen toegang geven tot leden van de **Groep Research** Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb5da-132">The site permissions, which only allow access to members of the **Research** Microsoft 365 group.</span></span>
- <span data-ttu-id="bb5da-133">Het **Research** DLP-beleid, dat gebruik maakt van het **label Highly Confidential** retention en instellingen die voorkomen dat het bestand wordt gedeeld met externe gebruikers.</span><span class="sxs-lookup"><span data-stu-id="bb5da-133">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="bb5da-134">Het sublabel voor gevoeligheid **van Onderzoeksteams,** met versleuteling en machtigingen die met het bestand reizen als het wordt verplaatst of gekopieerd van de **onderzoekssite.**</span><span class="sxs-lookup"><span data-stu-id="bb5da-134">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="bb5da-135">Hier is een voorbeeld van een bestand dat is opgeslagen op de **onderzoekssite** met het sublabel Gevoeligheid **van onderzoeksteams** toegewezen.</span><span class="sxs-lookup"><span data-stu-id="bb5da-135">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![De resulterende configuratie van de research team site voor zeer vertrouwelijke activa](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="bb5da-137">Stap 4: De on-premises SharePoint-onderzoeksgegevens gemigreerd</span><span class="sxs-lookup"><span data-stu-id="bb5da-137">Step 4: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="bb5da-138">Contoso-beheerders hebben alle on-premises onderzoeksbestanden in de on-premises SharePoint Server 2016-site verplaatst naar mappen in de nieuwe SharePoint-site **voor onderzoek.**</span><span class="sxs-lookup"><span data-stu-id="bb5da-138">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-5-trained-their-researchers"></a><span data-ttu-id="bb5da-139">Stap 5: Getrainde hun onderzoekers</span><span class="sxs-lookup"><span data-stu-id="bb5da-139">Step 5: Trained their researchers</span></span>

<span data-ttu-id="bb5da-140">Contoso-beveiligingspersoneel heeft de leden van de **Research** Microsoft 365-groep getraind in een verplichte cursus die hen doorzette:</span><span class="sxs-lookup"><span data-stu-id="bb5da-140">Contoso security staff trained the members of the **Research** Microsoft 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="bb5da-141">Hoe toegang te krijgen tot de nieuwe **Research-site** en de bestaande bestanden.</span><span class="sxs-lookup"><span data-stu-id="bb5da-141">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="bb5da-142">hoe ze nieuwe bestanden op de site kunnen maken en nieuwe bestanden kunnen uploaden die lokaal zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="bb5da-142">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="bb5da-143">Een demonstratie van hoe het **Research** DLP-beleid blokkeert dat bestanden extern worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="bb5da-143">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="bb5da-144">Hoe bestanden te labelen met het sublabel **Gevoeligheid van onderzoeksteams.**</span><span class="sxs-lookup"><span data-stu-id="bb5da-144">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="bb5da-145">Een demonstratie van hoe het **sublabel van** de Onderzoeksteams een bestand beschermt, zelfs wanneer het van de site wordt gelekt.</span><span class="sxs-lookup"><span data-stu-id="bb5da-145">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="bb5da-146">Het eindresultaat is een veilige omgeving waarin de onderzoekers in een beveiligde omgeving kunnen samenwerken in een beveiligde omgeving aan bestanden met onderzoeksinformatie.</span><span class="sxs-lookup"><span data-stu-id="bb5da-146">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="bb5da-147">Als een onderzoeksdocument met het sublabel **Research Teams** de **onderzoekssite** verlaat, wordt het alleen versleuteld en toegankelijk voor leden van de **Research** Microsoft 365-groep met geldige gebruikersaccountgegevens.</span><span class="sxs-lookup"><span data-stu-id="bb5da-147">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Microsoft 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="bb5da-148">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="bb5da-148">Next step</span></span>

<span data-ttu-id="bb5da-149">[Implementeren](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bb5da-149">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb5da-150">Zie ook</span><span class="sxs-lookup"><span data-stu-id="bb5da-150">See also</span></span>

<span data-ttu-id="bb5da-151">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="bb5da-151">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
