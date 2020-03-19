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
description: 'Samenvatting: Hoe Contoso een SharePoint-site implementeerde voor sterk gereguleerde gegevens voor eenvoudigere samenwerking tussen zijn onderzoeksteams.'
ms.openlocfilehash: a1ffb336e85eb6eb850b53ed14adf947b56642cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806821"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="49fa5-103">SharePoint-site voor zeer vertrouwelijke digitale activa van de Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="49fa5-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

<span data-ttu-id="49fa5-104">Contoso's meest waardevolle activa zijn de intellectuele eigendom in de vorm van bedrijfsgeheimen, zoals gepatenteerde productietechnieken, en ontwerpspecificaties voor producten die in ontwikkeling zijn.</span><span class="sxs-lookup"><span data-stu-id="49fa5-104">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="49fa5-105">Deze elementen waren in digitale vorm, oorspronkelijk opgeslagen als bestanden op een SharePoint Server 2016-site.</span><span class="sxs-lookup"><span data-stu-id="49fa5-105">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="49fa5-106">Toen Contoso Microsoft 365 Enterprise inzette, wilden ze hun on-premises digitale assets naar de cloud overbrengen voor eenvoudigere toegang en meer open samenwerking tussen onderzoeksteams in Parijs, Moskou, New York, Beijing en Bangalore.</span><span class="sxs-lookup"><span data-stu-id="49fa5-106">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="49fa5-107">Vanwege hun gevoelige karakter moet de toegang tot deze bestanden echter zijn:</span><span class="sxs-lookup"><span data-stu-id="49fa5-107">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="49fa5-108">Beperkt tot de groep mensen die toegang hebben tot hen.</span><span class="sxs-lookup"><span data-stu-id="49fa5-108">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="49fa5-109">Beveiligd met een DLP-beleid (Data Loss Prevention) om te voorkomen dat gebruikers ze buiten de site distribueren.</span><span class="sxs-lookup"><span data-stu-id="49fa5-109">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="49fa5-110">Versleuteld en beveiligd met machtigingen om te voorkomen dat onbevoegde gebruikers toegang krijgen tot hun inhoud, zelfs als ze buiten de site worden gedistribueerd.</span><span class="sxs-lookup"><span data-stu-id="49fa5-110">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="49fa5-111">Beveiligings- en SharePoint-beheerders in de IT-afdeling van Contoso besloten een [SharePoint-site](teams-sharepoint-online-sites-highly-regulated-data.md)te gebruiken voor sterk gereguleerde gegevens.</span><span class="sxs-lookup"><span data-stu-id="49fa5-111">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="49fa5-112">Contoso gebruikte deze stappen om een SharePoint-teamsites voor hun onderzoeksteams te maken en te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="49fa5-112">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="49fa5-113">Stap 1: Een privé SharePoint-teamsite maken</span><span class="sxs-lookup"><span data-stu-id="49fa5-113">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="49fa5-114">Om de toegang tot de SharePoint-site te beschermen, heeft Contoso IT het [aanbevolen SharePoint-toegangsbeleid](sharepoint-file-access-policies.md)geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="49fa5-114">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="49fa5-115">Vervolgens stelden Contoso IT-beheerders een lijst samen van de gebruikersaccounts voor de onderzoekers in hun kantoren in Parijs, Moskou, New York, Beijing en Bangalore.</span><span class="sxs-lookup"><span data-stu-id="49fa5-115">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="49fa5-116">Vervolgens heeft een Contoso IT-beheerder een nieuwe privéteamsite gemaakt met de naam **Research** en alle gebruikersaccounts voor zijn onderzoekers toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="49fa5-116">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="49fa5-117">Vervolgens hebben ze extra machtigingsinstellingen voor de site geconfigureerd om te voorkomen dat onderzoekers toegang tot de site delen en om te voorkomen dat niet-onderzoekers toegang tot de site zouden aanvragen.</span><span class="sxs-lookup"><span data-stu-id="49fa5-117">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="49fa5-118">Stap 2: De site geconfigureerd voor een restrictief DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="49fa5-118">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="49fa5-119">Ten eerste hebben Contoso-beheerders het bestaande **zeer vertrouwelijke** Office 365-bewaarlabel toegepast op de map Documenten van de **onderzoekssite.**</span><span class="sxs-lookup"><span data-stu-id="49fa5-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="49fa5-120">Vervolgens hebben ze een nieuw Office 365 DLP-beleid met de naam **Research** gemaakt, dat:</span><span class="sxs-lookup"><span data-stu-id="49fa5-120">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="49fa5-121">Gebruikt het **bewaarlabel Zeer vertrouwelijk** Office 365.</span><span class="sxs-lookup"><span data-stu-id="49fa5-121">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="49fa5-122">Blokkeert gebruikers wanneer ze proberen om een digitaal actief te delen op de **onderzoekssite** buiten Contoso.</span><span class="sxs-lookup"><span data-stu-id="49fa5-122">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="49fa5-123">Zie [SharePoint-bestanden beveiligen met bewaarlabels en DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)voor de configuratiegegevens.</span><span class="sxs-lookup"><span data-stu-id="49fa5-123">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="49fa5-124">Stap 3: Een sublabel voor gevoeligheid van Office 365 voor de site maken</span><span class="sxs-lookup"><span data-stu-id="49fa5-124">Step 3: Created an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="49fa5-125">Contoso-beheerders hebben een nieuw sublabel voor gevoeligheid van Office 365 gemaakt met de naam **Research Teams** van het label **Zeer vertrouwelijk** dat:</span><span class="sxs-lookup"><span data-stu-id="49fa5-125">Contoso admins created a new Office 365 sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="49fa5-126">Vereist encryptie.</span><span class="sxs-lookup"><span data-stu-id="49fa5-126">Requires encryption.</span></span>
- <span data-ttu-id="49fa5-127">Co-auteurmachtigingen toestaan voor de **groep Research** Office 365</span><span class="sxs-lookup"><span data-stu-id="49fa5-127">Allows Co-Author permissions for the **Research** Office 365 group</span></span>
- <span data-ttu-id="49fa5-128">Van toepassing op de **groep Research** Office 365</span><span class="sxs-lookup"><span data-stu-id="49fa5-128">Applies to the **Research** Office 365 group</span></span>

<span data-ttu-id="49fa5-129">Hier is de resulterende configuratie van de **research** team site voor zeer vertrouwelijke activa.</span><span class="sxs-lookup"><span data-stu-id="49fa5-129">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![De resulterende configuratie van de onderzoeksteamsite voor zeer vertrouwelijke activa](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="49fa5-131">Bestanden in mappen van de **onderzoekssite** worden beschermd door:</span><span class="sxs-lookup"><span data-stu-id="49fa5-131">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="49fa5-132">De sitemachtigingen, die alleen toegang bieden tot leden van de **groep Research** Office 365.</span><span class="sxs-lookup"><span data-stu-id="49fa5-132">The site permissions, which only allow access to members of the **Research** Office 365 group.</span></span>
- <span data-ttu-id="49fa5-133">Het **Beleid Voor Onderzoek** DLP, dat het zeer **vertrouwelijke** bewaarlabel en -instellingen gebruikt om te voorkomen dat het bestand wordt gedeeld met externe gebruikers.</span><span class="sxs-lookup"><span data-stu-id="49fa5-133">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="49fa5-134">Het gevoeligheidssublabel **van de onderzoeksteams,** met versleuteling en machtigingen die met het bestand reizen als het wordt verplaatst of gekopieerd van de **onderzoekssite.**</span><span class="sxs-lookup"><span data-stu-id="49fa5-134">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="49fa5-135">Hier is een voorbeeld van een bestand opgeslagen in de **onderzoekssite** met het gevoeligheidssublabel **van onderzoeksteams** toegewezen.</span><span class="sxs-lookup"><span data-stu-id="49fa5-135">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![De resulterende configuratie van de onderzoeksteamsite voor zeer vertrouwelijke activa](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="49fa5-137">Stap 4: De on-premises SharePoint-onderzoeksgegevens gemigreerd</span><span class="sxs-lookup"><span data-stu-id="49fa5-137">Step 4: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="49fa5-138">Contoso-beheerders verplaatsten alle on-premises onderzoeksbestanden op de on-premises SharePoint Server 2016-site naar mappen in de nieuwe SharePoint-onderzoekssite. **Research**</span><span class="sxs-lookup"><span data-stu-id="49fa5-138">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-5-trained-their-researchers"></a><span data-ttu-id="49fa5-139">Stap 5: Trainde hun onderzoekers</span><span class="sxs-lookup"><span data-stu-id="49fa5-139">Step 5: Trained their researchers</span></span>

<span data-ttu-id="49fa5-140">Contoso-beveiligingspersoneel heeft de leden van de **Research** Office 365-groep opgeleid in een verplichte cursus die hen doorzette:</span><span class="sxs-lookup"><span data-stu-id="49fa5-140">Contoso security staff trained the members of the **Research** Office 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="49fa5-141">Hoe toegang te krijgen tot de nieuwe **onderzoekssite** en de bestaande bestanden.</span><span class="sxs-lookup"><span data-stu-id="49fa5-141">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="49fa5-142">Nieuwe bestanden op de site maken en nieuwe bestanden uploaden die lokaal zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="49fa5-142">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="49fa5-143">Een demonstratie van hoe het DLP-beleid van Het **Onderzoek** bestanden blokkeert om extern te worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="49fa5-143">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="49fa5-144">Bestanden labelen met het gevoeligheidssublabel **van onderzoeksteams.**</span><span class="sxs-lookup"><span data-stu-id="49fa5-144">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="49fa5-145">Een demonstratie van hoe het sublabel van de **Onderzoeksteams** een bestand beschermt, zelfs wanneer het van de site is gelekt.</span><span class="sxs-lookup"><span data-stu-id="49fa5-145">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="49fa5-146">Het eindresultaat is een veilige omgeving waarin de onderzoekers via Contoso kunnen samenwerken in een beveiligde omgeving aan bestanden met onderzoeksinformatie.</span><span class="sxs-lookup"><span data-stu-id="49fa5-146">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="49fa5-147">Als een onderzoeksdocument met het sublabel **Research Teams** de **onderzoekssite** verlaat, is het versleuteld en alleen toegankelijk voor leden van de **Research** Office 365-groep met geldige gebruikersaccountreferenties.</span><span class="sxs-lookup"><span data-stu-id="49fa5-147">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Office 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="49fa5-148">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="49fa5-148">Next step</span></span>

<span data-ttu-id="49fa5-149">[Implementeren](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="49fa5-149">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="49fa5-150">Zie ook</span><span class="sxs-lookup"><span data-stu-id="49fa5-150">See also</span></span>

<span data-ttu-id="49fa5-151">[Microsoft 365-productiviteitsbibliotheek](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="49fa5-151">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
