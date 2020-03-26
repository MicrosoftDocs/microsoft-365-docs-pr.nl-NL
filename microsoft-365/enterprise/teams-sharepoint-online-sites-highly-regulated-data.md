---
title: SharePoint-sites voor sterk gereglementeerde gegevens
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Maak een beveiligde SharePoint-teamsite om de meest waardevolle en gevoeligste bestanden op te slaan.
ms.openlocfilehash: bc1a84fa7437d9b2979e10b352f8a422c457e8a0
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951980"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="4652a-103">SharePoint-sites voor sterk gereglementeerde gegevens</span><span class="sxs-lookup"><span data-stu-id="4652a-103">SharePoint sites for highly regulated data</span></span>

<span data-ttu-id="4652a-104">*Dit scenario geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="4652a-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4652a-105">Microsoft 365 Enterprise heeft onder meer een volledige suite van cloudservices zodat u uw sterk gereglementeerde gegevens kunt maken, opslaan, beveiligen en beheren.</span><span class="sxs-lookup"><span data-stu-id="4652a-105">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, secure, and manage your highly regulated data stored in files.</span></span> <span data-ttu-id="4652a-106">Dit zijn onder meer gegevens die:</span><span class="sxs-lookup"><span data-stu-id="4652a-106">This includes data that is:</span></span>

- <span data-ttu-id="4652a-107">onderhevig zijn aan regionale regelgeving.</span><span class="sxs-lookup"><span data-stu-id="4652a-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="4652a-108">de meest waardevolle gegevens voor uw organisatie bevatten, zoals handelsgeheimen, informatie over financiën of personeel en de organisatorische strategie.</span><span class="sxs-lookup"><span data-stu-id="4652a-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

>[!Note]
> <span data-ttu-id="4652a-109">[Hier](secure-teams-highly-regulated-data-scenario.md) vindt u een vergelijkbaar scenario met Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4652a-109">A similar scenario using Microsoft Teams is [here](secure-teams-highly-regulated-data-scenario.md).</span></span>
>

<span data-ttu-id="4652a-110">Een Microsoft 365 Enterprise-cloudscenario dat aan deze bedrijfsbehoefte voldoet, vereist dat u:</span><span class="sxs-lookup"><span data-stu-id="4652a-110">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="4652a-111">bestanden (documenten, diapresentaties, spreadsheets, enz.) opslaat op een SharePoint-teamsite.</span><span class="sxs-lookup"><span data-stu-id="4652a-111">Store files (documents, slide decks, spreadsheets, etc.) in a SharePoint team site.</span></span>
- <span data-ttu-id="4652a-112">Vergrendel de site om te voorkomen dat:</span><span class="sxs-lookup"><span data-stu-id="4652a-112">Lock down the site to prevent:</span></span>
  - <span data-ttu-id="4652a-113">gebruikers toegang hebben die geen lid zijn van de Office 365-groep voor de site.</span><span class="sxs-lookup"><span data-stu-id="4652a-113">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="4652a-114">leden van de site toegang verlenen aan anderen.</span><span class="sxs-lookup"><span data-stu-id="4652a-114">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="4652a-115">niet-leden van de site toegang verzoeken tot de site.</span><span class="sxs-lookup"><span data-stu-id="4652a-115">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="4652a-116">Configureer een Office 365-retentielabel voor uw SharePoint-sites als standaardmanier om te voorkomen dat gebruikers bestanden verzenden buiten het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="4652a-116">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="4652a-117">Versleutel de meest gevoelige bestanden van de site met versleuteling die met het bestand wordt meeverplaatst.</span><span class="sxs-lookup"><span data-stu-id="4652a-117">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="4652a-118">Voeg machtigingen toe aan de meest gevoelige bestanden, zodat het openen van het bestand, zelfs als dat wordt gedeeld buiten de site, nog steeds geldige machtigingen vereist van een gebruikersaccount met toegang.</span><span class="sxs-lookup"><span data-stu-id="4652a-118">Add permissions to the most sensitive files so that if even if they get shared outside of the site, opening the file still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="4652a-119">De volgende tabel zet de vereisten voor dit scenario uit in een functie van Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4652a-119">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="4652a-120">**Vereiste**</span><span class="sxs-lookup"><span data-stu-id="4652a-120">**Requirement**</span></span> | <span data-ttu-id="4652a-121">**Microsoft 365 Enterprise feature**</span><span class="sxs-lookup"><span data-stu-id="4652a-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="4652a-122">Bestanden opslaan</span><span class="sxs-lookup"><span data-stu-id="4652a-122">Store files</span></span> | <span data-ttu-id="4652a-123">SharePoint-teamsites</span><span class="sxs-lookup"><span data-stu-id="4652a-123">SharePoint team sites</span></span> |
| <span data-ttu-id="4652a-124">De site vergrendelen</span><span class="sxs-lookup"><span data-stu-id="4652a-124">Lock down the site</span></span> | <span data-ttu-id="4652a-125">Office 365-groeps- en SharePoint-sitemachtigingen</span><span class="sxs-lookup"><span data-stu-id="4652a-125">Office 365 groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="4652a-126">De bestanden van een site een label geven</span><span class="sxs-lookup"><span data-stu-id="4652a-126">Label the files of the site</span></span> | <span data-ttu-id="4652a-127">Office 365-retentielabels</span><span class="sxs-lookup"><span data-stu-id="4652a-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="4652a-128">Gebruikers blokkeren wanneer zij bestanden buiten het bedrijf verzenden</span><span class="sxs-lookup"><span data-stu-id="4652a-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="4652a-129">Office 365-beleid voor preventie van gegevensverlies (DLP)</span><span class="sxs-lookup"><span data-stu-id="4652a-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="4652a-130">Alle bestanden van de site versleutelen</span><span class="sxs-lookup"><span data-stu-id="4652a-130">Encrypt all of the files of the site</span></span> | <span data-ttu-id="4652a-131">Office 365-gevoeligheidslabels of -sublabels</span><span class="sxs-lookup"><span data-stu-id="4652a-131">Office 365 sensitivity labels or sublabels</span></span> |
| <span data-ttu-id="4652a-132">Machtigingen toevoegen aan de bestanden van de site</span><span class="sxs-lookup"><span data-stu-id="4652a-132">Add permissions to the files of the site</span></span> | <span data-ttu-id="4652a-133">Office 365-gevoeligheidslabels of -sublabels</span><span class="sxs-lookup"><span data-stu-id="4652a-133">Office 365 sensitivity labels or sublabels</span></span> |
|||

<span data-ttu-id="4652a-134">Hier vindt u een voorbeeldconfiguratie voor een beveiligde SharePoint-site.</span><span class="sxs-lookup"><span data-stu-id="4652a-134">Here is an example configuration for a secure SharePoint site.</span></span>

![Het scenario met SharePoint-sites voor sterk gereglementeerde gegevens](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="4652a-136">Voor dit scenario moet het volgende al zijn geïmplementeerd:</span><span class="sxs-lookup"><span data-stu-id="4652a-136">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="4652a-137">De [Identiteits](identity-infrastructure.md)-fase en stap 1 en 2 van de [Informatiebeveiligings](infoprotect-infrastructure.md)-fase van de basisinfrastructuur.</span><span class="sxs-lookup"><span data-stu-id="4652a-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="4652a-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="4652a-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span></span>

<span data-ttu-id="4652a-139">In de volgende fasen wordt u stapsgewijs begeleid bij het ontwerpen, configureren en stimuleren van acceptatie van SharePoint-sites voor sterk gereglementeerde gegevens.</span><span class="sxs-lookup"><span data-stu-id="4652a-139">The following phases step you through designing, configuring, and driving adoption for SharePoint sites for highly regulated data.</span></span>

<a name="poster"></a><span data-ttu-id="4652a-140">Zie de [Poster voor SharePoint-sites voor sterk gereglementeerde gegevens](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) voor een overzicht van één pagina van dit scenario.</span><span class="sxs-lookup"><span data-stu-id="4652a-140">For a 1-page summary of this scenario, see the [SharePoint sites for highly regulated data poster](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="4652a-141">[![Poster voor SharePoint-sites voor sterk gereglementeerde gegevens](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="4652a-141">[![SharePoint sites for highly regulated data poster](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="4652a-142">U kunt deze poster ook downloaden in [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) of [PowerPoint-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) indeling en deze afdrukken op papier met formaat Letter, Legal of Tabloid (27,9 x 43,2 cm).</span><span class="sxs-lookup"><span data-stu-id="4652a-142">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="4652a-143">Vereisten voor identiteits- en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="4652a-143">Identity and device access prerequisites</span></span>

<span data-ttu-id="4652a-144">Als u de toegang tot de SharePoint-site wilt beveiligen, zorg er dan voor dat u [identiteits- en apparaattoegangsbeleid](identity-access-policies.md) en het [Aanbevolen SharePoint-toegangsbeleid](sharepoint-file-access-policies.md) hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="4652a-144">To protect access to the SharePoint site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="4652a-145">Fase 1: Ontwerp</span><span class="sxs-lookup"><span data-stu-id="4652a-145">Phase 1: Design</span></span>

<span data-ttu-id="4652a-146">Om een SharePoint-site voor sterk gereglementeerde gegevens te maken, moet u eerst het doelstelling ervan vaststellen.</span><span class="sxs-lookup"><span data-stu-id="4652a-146">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="4652a-147">Als bijvoorbeeld de onderzoeks- en ontwikkelafdeling van een productiebedrijf een SharePoint-site nodig heeft om de huidige ontwerpspecificaties voor bestaande producten op te slaan en een plaats om samen te werken aan nieuw producten.</span><span class="sxs-lookup"><span data-stu-id="4652a-147">For example, the research and development department of a manufacturing organization needs a SharePoint site to store current design specifications for existing products and a place to collaborate on new products.</span></span> <span data-ttu-id="4652a-148">Alleen leden van de afdeling Onderzoek en Ontwikkeing en geselecteerde leidinggevenden krijgen toegang tot deze site.</span><span class="sxs-lookup"><span data-stu-id="4652a-148">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="4652a-149">Die doelstelling is bepalend voor de vaststelling van essentiële configuratie-items, zoals:</span><span class="sxs-lookup"><span data-stu-id="4652a-149">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="4652a-150">het Office 365-retentielabel dat moet worden toegepast op het documentgedeelte van de site en DLP-beleid voor het label</span><span class="sxs-lookup"><span data-stu-id="4652a-150">The Office 365 retention label to assign to the Documents portion of the site and DLP policies for the label</span></span>
- <span data-ttu-id="4652a-151">de instellingen van een Office 365-gevoeligheidssublabel dat gebruikers kunnen toepassen op bijzonder gevoelige bestanden die worden opgeslagen op de site</span><span class="sxs-lookup"><span data-stu-id="4652a-151">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="4652a-152">Wanneer dat is vastgesteld, gebruikt u deze instellingen om de site te configureren in Fase 2.</span><span class="sxs-lookup"><span data-stu-id="4652a-152">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="4652a-153">Stap 1 Office 365-retentielabels en DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="4652a-153">Step 1 Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="4652a-154">Office 365-retentielabels bieden een standaardmethode om alle op de site opgeslagen bestanden te classificeren wanneer ze worden toegepast op het documentgedeelte van een SharePoint-teamsite.</span><span class="sxs-lookup"><span data-stu-id="4652a-154">When applied to the Documents portion of a SharePoint team site, Office 365 retention labels provide a default method of classifying all files stored on the site.</span></span>
 
<span data-ttu-id="4652a-155">Voor SharePoint-sites voor sterk gereglementeerde gegevens moet u vaststellen welk Office 365-retentielabel wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="4652a-155">For SharePoint sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="4652a-156">Zie [Office 365-classificatie en -labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels) voor het bepalen van het ontwerp van Office 365-labels.</span><span class="sxs-lookup"><span data-stu-id="4652a-156">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="4652a-157">Om gevoelige gegevens te beschermen en het (on)opzettlijk vrijgeven ervan te voorkomen, gebruikt u DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="4652a-157">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies.</span></span> <span data-ttu-id="4652a-158">Zie dit [overzicht](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4652a-158">For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="4652a-159">Voor SharePoint-sites moet u DLP-beleid configureren voor het Office 365-retentielabel dat wordt toegepast op de site, om gebruikers te blokkeren wanneer zij proberen bestanden te delen met externe gebruikers.</span><span class="sxs-lookup"><span data-stu-id="4652a-159">For SharePoint sites, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share files with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="4652a-160">Stap 2: uw Office 365-gevoeligheidssublabel</span><span class="sxs-lookup"><span data-stu-id="4652a-160">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="4652a-161">Om versleuteling en een verzameling machtigingen toe te passen op uw gevoeligste bestanden moeten gebruikers een Office 365-gevoeligheidslabel of -sublabel toepassen.</span><span class="sxs-lookup"><span data-stu-id="4652a-161">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity label or sublabel.</span></span> <span data-ttu-id="4652a-162">Een sublabel bestaat onder een bestaand label.</span><span class="sxs-lookup"><span data-stu-id="4652a-162">A sublabel exists under an existing label.</span></span> 

<span data-ttu-id="4652a-163">Gebruik een gevoeligheidslabel wanneer u een klein aantal labels nodig hebt voor zowel algemeen gebruik als individuele besloten teams.</span><span class="sxs-lookup"><span data-stu-id="4652a-163">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="4652a-164">Gebruik een gevoeligheidssublabel wanneer u een groot aantal labels nodig hebt of als u labels wilt instellen voor beveiligde sites onder uw sterk gereglementeerde label.</span><span class="sxs-lookup"><span data-stu-id="4652a-164">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for secure sites the under your highly regulated label.</span></span> 

<span data-ttu-id="4652a-165">De instellingen van het toegepaste label of sublabel worden verplaatst met het bestand.</span><span class="sxs-lookup"><span data-stu-id="4652a-165">The settings of the applied label or sublabel travel with the file.</span></span> <span data-ttu-id="4652a-166">Zelfs als het uitlekt buiten de site kunnen alleen geverifieerde gebruikersaccounts met machtigingen het openen.</span><span class="sxs-lookup"><span data-stu-id="4652a-166">Even if it is leaked outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="4652a-167">Ontwerpresultaten</span><span class="sxs-lookup"><span data-stu-id="4652a-167">Design results</span></span>

<span data-ttu-id="4652a-168">U hebt het volgende vastgesteld:</span><span class="sxs-lookup"><span data-stu-id="4652a-168">You have determined the following:</span></span>

- <span data-ttu-id="4652a-169">het juiste Office 365-retentielabel en het DLP-beleid dat is gekoppeld aan het label</span><span class="sxs-lookup"><span data-stu-id="4652a-169">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="4652a-170">de instellingen van het Office 365-gevoeligheidssublabel met versleuteling en machtigingen</span><span class="sxs-lookup"><span data-stu-id="4652a-170">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="4652a-171">Fase 2: Configureren</span><span class="sxs-lookup"><span data-stu-id="4652a-171">Phase 2: Configure</span></span>

<span data-ttu-id="4652a-172">In deze fase implementeert u de instellingen die zijn bepaald in Fase 1 om een SharePoint-site voor sterk gereglementeerde gegevens te maken.</span><span class="sxs-lookup"><span data-stu-id="4652a-172">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="4652a-173">Stap 1: een besloten SharePoint-teamsite maken met eigenaren en leden van de bijbehorende Office 365-groep</span><span class="sxs-lookup"><span data-stu-id="4652a-173">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="4652a-174">Volg [deze instructies]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) om een besloten SharePoint-teamsite te maken.</span><span class="sxs-lookup"><span data-stu-id="4652a-174">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="4652a-175">Stap 2: aanvullende machtigingsinstellingen configureren voor de SharePoint-teamsite</span><span class="sxs-lookup"><span data-stu-id="4652a-175">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="4652a-176">Configureer deze machtigingsinstellingen vanuit de SharePoint-site.</span><span class="sxs-lookup"><span data-stu-id="4652a-176">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="4652a-177">Klik in de werkbalk op het pictogram Instellingen en vervolgens op **Site-machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="4652a-177">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="4652a-178">Klik in het deelvenster **Site-machtigingen**, onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="4652a-178">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="4652a-179">Kies onder **Machtigingen voor delen**, **Alleen site-eigenaren kunnen bestanden, mappen en de site delen**.</span><span class="sxs-lookup"><span data-stu-id="4652a-179">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="4652a-180">Schakel **Toegangsaanvragen toestaan** uit en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4652a-180">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="4652a-181">Met deze instellingen word de mogelijkheid uitgeschakeld voor site-groepsleden om de site met andere leden te delen of voor niet-leden om toegang tot de site aan te vragen.</span><span class="sxs-lookup"><span data-stu-id="4652a-181">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="4652a-182">Stap 3: de site configureren voor een Office 365-retentielabel</span><span class="sxs-lookup"><span data-stu-id="4652a-182">Step 3: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="4652a-183">Gebruik de instructies in [SharePoint-bestanden beveiligen met Office 365-labels en DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) om:</span><span class="sxs-lookup"><span data-stu-id="4652a-183">Use the instructions in [Protect SharePoint files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="4652a-184">een retentielabel voor sterk gereglementeerde gegevens (indien nodig) te maken en te publiceren.</span><span class="sxs-lookup"><span data-stu-id="4652a-184">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="4652a-185">de site te configureren voor het in stap 1 gemaakte retentielabel.</span><span class="sxs-lookup"><span data-stu-id="4652a-185">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="4652a-186">DLP-beleid te maken voor sterk gereglementeerde gegevens die het in stap 2 gemaakte retentielabel gebruiken en het verzenden blokkeert van bestanden buiten het bedrijf door gebruikers.</span><span class="sxs-lookup"><span data-stu-id="4652a-186">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="4652a-187">Stap 4: een Office 365-gevoeligheidssublabel maken voor de site</span><span class="sxs-lookup"><span data-stu-id="4652a-187">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="4652a-188">Een beveiligde site heeft, in tegenstelling tot een gevoeligheidslabel voor sterk gereglementeerde gegevens die iedereen op een bestand kan toepassen, een eigen sublabel nodig, zodat bestanden met het toegepaste sublabel:</span><span class="sxs-lookup"><span data-stu-id="4652a-188">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="4652a-189">versleuteld zijn en dat de versleuteling wordt meeverplaatst met het bestand.</span><span class="sxs-lookup"><span data-stu-id="4652a-189">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="4652a-190">aangepaste machtigingen bevatten, zodat alleen leden van de sitegroep ze kunnen openen.</span><span class="sxs-lookup"><span data-stu-id="4652a-190">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="4652a-191">Om dit extra beveiligingsniveau te halen voor bestanden die zijn opgeslagen op de site, moet u een nieuw gevoeligheidslabel of een sublabel van het algemene label voor de sterk gereglementeerde bestanden configureren.</span><span class="sxs-lookup"><span data-stu-id="4652a-191">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label or a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="4652a-192">Alleen groepsleden van de site zullen het zien in de lijst met sublabels voor de sterk gereglementeerde bestanden.</span><span class="sxs-lookup"><span data-stu-id="4652a-192">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="4652a-193">Gebruik de instructies [hier](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) om een label of sublabel van het label dat u gebruikt voor sterk gereglementeerde bestanden te configureren met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="4652a-193">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a label or a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="4652a-194">de naam van het label of sublabel bevat de naam van de site voor eenvoudige koppeling wanneer het label of sublabel wordt toegepast op een bestand.</span><span class="sxs-lookup"><span data-stu-id="4652a-194">The name of the label or sublabel contains the name of the site for easy association when assigning the label or sublabel to a file.</span></span>
- <span data-ttu-id="4652a-195">versleuteling is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="4652a-195">Encryption is enabled.</span></span>
- <span data-ttu-id="4652a-196">de sitegroep heeft Cocreatie-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="4652a-196">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="4652a-197">Configuratieresultaten</span><span class="sxs-lookup"><span data-stu-id="4652a-197">Configuration results</span></span>

<span data-ttu-id="4652a-198">U hebt het volgende geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="4652a-198">You have configured the following:</span></span>

- <span data-ttu-id="4652a-199">meer beperkende machtigingsinstellingen op de SharePoint-site</span><span class="sxs-lookup"><span data-stu-id="4652a-199">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="4652a-200">een Office 365-retentielabel toegepast op het documentgedeelte van de SharePoint-site</span><span class="sxs-lookup"><span data-stu-id="4652a-200">An Office 365 retention label assigned to the Documents portion of the SharePoint site</span></span>
- <span data-ttu-id="4652a-201">een DLP-beleid voor het Office 365-retentielabel</span><span class="sxs-lookup"><span data-stu-id="4652a-201">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="4652a-202">een Office 365-gevoeligheidslabel of -sublabel dat gebruikers kunnen toepassen op de meest gevoelige bestanden die zijn opgeslagen op de site, waarmee het bestand wordt versleuteld en alleen Cocreatie-toegang verleent aan leden van de teamsitegroep.</span><span class="sxs-lookup"><span data-stu-id="4652a-202">An Office 365 sensitivity label or sublabel that users can apply to the most sensitive files stored in the site, which encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="4652a-203">Hier ziet u de resulterende configuratie die een sublabel van het label Sterk gereglementeerd gebruikt.</span><span class="sxs-lookup"><span data-stu-id="4652a-203">Here is the resulting configuration that uses a sublabel of the Highly regulated label.</span></span>

![Het scenario met SharePoint-sites voor sterk gereglementeerde gegevens](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="4652a-205">Hier ziet u een voorbeeld van een gebruiker die het sublabel heeft toegepast op een bestand dat is opgeslagen op de site.</span><span class="sxs-lookup"><span data-stu-id="4652a-205">Here is an example of a user that has applied the sublabel to a file stored in the site.</span></span>

![Het scenario met SharePoint-sites voor sterk gereglementeerde gegevens](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="4652a-207">Fase 3: gebruikersacceptatie stimuleren</span><span class="sxs-lookup"><span data-stu-id="4652a-207">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="4652a-208">Een SharePoint-site voor sterk gereglementeerde gegevens kan alleen de gegevens beveiligen als die consequent wordt gebruikt voor de opslag en toegang tot gevoelige bestanden.</span><span class="sxs-lookup"><span data-stu-id="4652a-208">A SharePoint site for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive files.</span></span> <span data-ttu-id="4652a-209">Dit is de moeilijkste fase, omdat het afhankelijk is van gebruikers die hun gewoonten en voorkeuren moeten veranderen.</span><span class="sxs-lookup"><span data-stu-id="4652a-209">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="4652a-210">Medewerkers die bijvoorbeeld gewend zijn gevoelige bestanden op te slaan op USB-sticks of op persoonlijke cloudopslagoplossingen moeten die nu exclusief opslaan op een SharePoint-site voor sterk gereglementeerde gegevens.</span><span class="sxs-lookup"><span data-stu-id="4652a-210">For example, employees that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="4652a-211">Stap 1: uw gebruikers onderwijzen</span><span class="sxs-lookup"><span data-stu-id="4652a-211">Step 1: Train your users</span></span>

<span data-ttu-id="4652a-212">Onderwijs na het voltooien van de configuratie de gebruikers die lid zijn van de site:</span><span class="sxs-lookup"><span data-stu-id="4652a-212">After completing your configuration, train the set of users who are members of the site:</span></span>

- <span data-ttu-id="4652a-213">over het belang van het gebruik van de nieuwe site om waardevolle bestanden te beveiligen en de consequenties van een gegevenslek van sterk gereglementeerde gegevens, zoals juridische gevolgen, boetes, ransomware of verlies van concurrentievoordeel.</span><span class="sxs-lookup"><span data-stu-id="4652a-213">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="4652a-214">hoe ze de site en de bijbehorende bestanden kunnen openen.</span><span class="sxs-lookup"><span data-stu-id="4652a-214">How to access the site and its files.</span></span>
- <span data-ttu-id="4652a-215">hoe ze nieuwe bestanden op de site kunnen maken en nieuwe bestanden kunnen uploaden die lokaal zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="4652a-215">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="4652a-216">hoe het DLP-beleid voorkomt dat ze bestanden extern delen.</span><span class="sxs-lookup"><span data-stu-id="4652a-216">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="4652a-217">hoe ze de meest gevoelige bestanden moeten labelen met het label of sublabel voor de site.</span><span class="sxs-lookup"><span data-stu-id="4652a-217">How to label the most sensitive files with the label or sublabel for the site.</span></span>
- <span data-ttu-id="4652a-218">hoe het label of sublabel een bestand beschermt, zelfs wanneer het is gelekt buiten de site. </span><span class="sxs-lookup"><span data-stu-id="4652a-218">How the label or sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="4652a-219">Bij deze scholing horen praktijkoefeningen, zodat de gebruikers deze acties en de resultaten ervan kunnen ervaren.</span><span class="sxs-lookup"><span data-stu-id="4652a-219">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="4652a-220">Stap 2: periodiek het gebruik en de bestanden bekijken</span><span class="sxs-lookup"><span data-stu-id="4652a-220">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="4652a-221">De SharePoint-beheerder van de SharePoint-site kan in de weken na de scholing het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="4652a-221">In the weeks after training, the SharePoint administrator for the SharePoint site can:</span></span>

- <span data-ttu-id="4652a-222">het gebruik van de site analyseren en vergelijken met gebruiksverwachtingen.</span><span class="sxs-lookup"><span data-stu-id="4652a-222">Analyze usage for the site and compare it with usage expectations.</span></span>
- <span data-ttu-id="4652a-223">verifiëren dat gevoelige bestanden juist zijn gelabeld met het gevoeligheidslabel of sublabel.</span><span class="sxs-lookup"><span data-stu-id="4652a-223">Verify that highly sensitive files have been properly labeled with the sensitivity label or sublabel.</span></span>

  <span data-ttu-id="4652a-224">U kunt zien welke bestanden een label hebben door een map te bekijken in SharePoint en de kolom **Gevoeligheid** toe te voegen met de optie **Kolommen weergeven/verbergen** of **Kolom toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4652a-224">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>


<span data-ttu-id="4652a-225">School de gebruikers indien nodig bij.</span><span class="sxs-lookup"><span data-stu-id="4652a-225">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="4652a-226">Resultaten van gebruikersacceptatie</span><span class="sxs-lookup"><span data-stu-id="4652a-226">User adoption results</span></span>

<span data-ttu-id="4652a-227">Sterk gereglementeerde bestanden worden exclusief opgeslagen op SharePoint-sites voor sterk gereglementeerde gegevens en de meest gevoelige bestanden hebben het gevoeligheidslabel of sublabel voor de site.</span><span class="sxs-lookup"><span data-stu-id="4652a-227">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity label or sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-used-a-sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="4652a-228">Hoe de Contoso Corporation een SharePoint-site gebruikt voor sterk gereglementeerde gegevens</span><span class="sxs-lookup"><span data-stu-id="4652a-228">How the Contoso Corporation used a SharePoint site for highly regulated data</span></span>

<span data-ttu-id="4652a-229">De Contoso Corporation is een fictief maar representatief wereldwijd productieconglomeraat.</span><span class="sxs-lookup"><span data-stu-id="4652a-229">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="4652a-230">Bekijk hoe Contoso een [beveiligde SharePoint-site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) voor hun onderzoeksteams in Parijs, Moskou, New York, Beijing en Bengaluru ontwierp, configureerde en vervolgens de acceptatie stimuleerde.</span><span class="sxs-lookup"><span data-stu-id="4652a-230">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="4652a-231">Zie ook</span><span class="sxs-lookup"><span data-stu-id="4652a-231">See also</span></span>

[<span data-ttu-id="4652a-232">Teams voor sterk gereglementeerde gegevens</span><span class="sxs-lookup"><span data-stu-id="4652a-232">Teams for highly regulated data</span></span>](secure-teams-highly-regulated-data-scenario.md)

[<span data-ttu-id="4652a-233">Microsoft 365 Enterprise-bedrijfsworkloads en -scenario's</span><span class="sxs-lookup"><span data-stu-id="4652a-233">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="4652a-234">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="4652a-234">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="4652a-235">Implementatiehandleiding</span><span class="sxs-lookup"><span data-stu-id="4652a-235">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
