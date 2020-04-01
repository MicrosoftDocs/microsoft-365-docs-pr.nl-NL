---
title: Teams voor sterk gereglementeerde gegevens
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Maak een beveiligd team om de meest waardevolle en gevoeligste bestanden op te slaan.
ms.openlocfilehash: aeb3662d6c8a21cbd56d983515913750fd5259f1
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951968"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="3b687-103">Teams voor sterk gereglementeerde gegevens</span><span class="sxs-lookup"><span data-stu-id="3b687-103">Teams for highly regulated data</span></span>

<span data-ttu-id="3b687-104">Dit artikel bevat aanbevelingen en stappen voor het configureren van een privéteam in Microsoft Teams waarmee alleen toegang wordt verleend tot Teams-functies, zoals chats, vergaderingen en bestanden, aan leden en eigenaren van de Office 365-groep voor het team.</span><span class="sxs-lookup"><span data-stu-id="3b687-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="3b687-105">Naast de privétoegang op basis van de Office 365-groep, wordt in dit artikel beschreven hoe u de onderliggende SharePoint-privéteamsite configureert die u kunt openen vanuit de sectie **Bestanden** van een teamkanaal, voor de extra beveiliging die nodig is voor het opslaan van sterk gereglementeerde gegevens.</span><span class="sxs-lookup"><span data-stu-id="3b687-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="3b687-106">Op deze SharePoint-teamsite kunt u bestanden, pagina's, een gedeelde agenda, taken, een notitieblok en lijsten opslaan en hieraan samenwerken.</span><span class="sxs-lookup"><span data-stu-id="3b687-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

>[!Note]
> <span data-ttu-id="3b687-107">Een vergelijkbaar scenario waarin SharePoint wordt gebruikt, vindt u [hier](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="3b687-107">A similar scenario using SharePoint is [here](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
>

<span data-ttu-id="3b687-108">De elementen van de configuratie van een team voor sterk gereglementeerde gegevens zijn:</span><span class="sxs-lookup"><span data-stu-id="3b687-108">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="3b687-109">Een privéteam met een bijbehorende Office 365-groep met gebruikersaccounts voor eigenaren en leden.</span><span class="sxs-lookup"><span data-stu-id="3b687-109">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="3b687-110">Extra beveiliging voor de onderliggende SharePoint-site voor het team waarmee:</span><span class="sxs-lookup"><span data-stu-id="3b687-110">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="3b687-111">Wordt voorkomen dat leden van de site toegang verlenen aan anderen.</span><span class="sxs-lookup"><span data-stu-id="3b687-111">Prevents members of the site from granting access to others.</span></span>
  - <span data-ttu-id="3b687-112">Wordt voorkomen dat niet-leden van de site toegang tot de site vragen.</span><span class="sxs-lookup"><span data-stu-id="3b687-112">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="3b687-113">Een Office 365-retentielabel voor de onderliggende SharePoint-site dat automatisch wordt toegepast op nieuwe bestanden op de site als standaardmethode voor het definiëren van bewaarbeleid.</span><span class="sxs-lookup"><span data-stu-id="3b687-113">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="3b687-114">Een beleid voor preventie van gegevensverlies (DLP) waarbij het retentielabel wordt gebruikt en gebruikers de bestanden niet kunnen delen of buiten de organisatie kunnen verzenden.</span><span class="sxs-lookup"><span data-stu-id="3b687-114">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="3b687-115">Een Office 365-gevoeligheidslabel of een sublabel van een sterk gereglementeerd label waarvoor versleuteling is ingeschakeld en machtigingen voor Medeauteurs zijn ingesteld voor de Office 365-groep van het team.</span><span class="sxs-lookup"><span data-stu-id="3b687-115">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="3b687-116">Gebruikers passen het label of sublabel toe op bestanden die zijn opgeslagen in de sectie **Bestanden** van het team met de optie **Gevoeligheid** op de menubalk in Word, Excel en PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="3b687-116">Users apply the label or sublabel to files stored in **Files** section of the team from the **Sensitivity** menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="3b687-117">Hier ziet u de resulterende configuratie met een gevoeligheidslabel.</span><span class="sxs-lookup"><span data-stu-id="3b687-117">Here is the resulting configuration with a sensitivity label.</span></span>

![De configuratie van het scenario voor het beveiligde team](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="3b687-119">Bekijk deze korte video voor een kort overzicht.</span><span class="sxs-lookup"><span data-stu-id="3b687-119">For a quick overview, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a><span data-ttu-id="3b687-120">Zie de [Poster voor Teams voor sterk gereglementeerde gegevens](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) voor een overzicht van één pagina van dit scenario.</span><span class="sxs-lookup"><span data-stu-id="3b687-120">For a 1-page summary of this scenario, see the [Teams for highly regulated data poster](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="3b687-121">[![Teams voor poster voor sterk gereglementeerde gegevens](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="3b687-121">[![Teams for highly regulated data poster](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="3b687-122">U kunt deze poster ook downloaden in [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) of [PowerPoint-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx) indeling en deze afdrukken op papier met formaat Letter, Legal of Tabloid (27,9 x 43,2 cm).</span><span class="sxs-lookup"><span data-stu-id="3b687-122">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>

## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a><span data-ttu-id="3b687-123">Fase 1: Een team configureren voor sterk gereglementeerde gegevens</span><span class="sxs-lookup"><span data-stu-id="3b687-123">Phase 1: Configure a team for highly regulated data</span></span>

<span data-ttu-id="3b687-124">De configuratie van de end-to-end-servers bestaat uit de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="3b687-124">The end-to-end configuration consists of these steps:</span></span>

1. <span data-ttu-id="3b687-125">Identiteit en apparaattoegang configureren.</span><span class="sxs-lookup"><span data-stu-id="3b687-125">Configure identity and device access.</span></span>
2. <span data-ttu-id="3b687-126">Een privéteam maken.</span><span class="sxs-lookup"><span data-stu-id="3b687-126">Create a private team.</span></span>
3. <span data-ttu-id="3b687-127">De onderliggende SharePoint-site configureren voor extra beveiliging.</span><span class="sxs-lookup"><span data-stu-id="3b687-127">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="3b687-128">Een retentielabel en DLP-beleid maken.</span><span class="sxs-lookup"><span data-stu-id="3b687-128">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="3b687-129">Het label of sublabel van het sterk gereglementeerde label maken.</span><span class="sxs-lookup"><span data-stu-id="3b687-129">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="3b687-130">Stap 1: identiteit en apparaattoegang configureren</span><span class="sxs-lookup"><span data-stu-id="3b687-130">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="3b687-131">Als u de toegang tot het team en de SharePoint-site wilt beveiligen, zorgt u ervoor dat u [identiteits- en apparaattoegangsbeleid](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) en het aanbevolen [SharePoint Online-toegangsbeleid](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies) hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="3b687-131">To protect access to the team and its underlying SharePoint site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the recommended [SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="3b687-132">Stap 2: een privéteam maken</span><span class="sxs-lookup"><span data-stu-id="3b687-132">Step 2: Create a private team</span></span>

<span data-ttu-id="3b687-133">Volg [deze instructies](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) om een privéteam te maken.</span><span class="sxs-lookup"><span data-stu-id="3b687-133">Use [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private team.</span></span>

<span data-ttu-id="3b687-134">Wanneer u een privéteam maakt, zijn dit de standaardmachtigingen:</span><span class="sxs-lookup"><span data-stu-id="3b687-134">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="3b687-135">De Office 365-groep voor het team (de teamgroep) heeft groepseigenaren en groepsleden</span><span class="sxs-lookup"><span data-stu-id="3b687-135">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="3b687-136">Voor de onderliggende SharePoint-site voor het team (de teamsite):</span><span class="sxs-lookup"><span data-stu-id="3b687-136">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="3b687-137">De beheerders van de siteverzameling zijn geconfigureerd als de eigenaren van de teamgroep</span><span class="sxs-lookup"><span data-stu-id="3b687-137">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="3b687-138">Voor de teamsite:</span><span class="sxs-lookup"><span data-stu-id="3b687-138">For the Team Site:</span></span> 
    - <span data-ttu-id="3b687-139">De SharePoint-groep met teamsite-eigenaren, met het machtigingsniveau Volledig beheer, is ingesteld op de eigenaren van de teamgroep</span><span class="sxs-lookup"><span data-stu-id="3b687-139">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="3b687-140">De SharePoint-groep met teamsiteleden, met het machtigingsniveau Bewerken, is ingesteld op de leden van de teamgroep</span><span class="sxs-lookup"><span data-stu-id="3b687-140">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="3b687-141">De SharePoint-groep met bezoekers van de teamsite, met het machtigingsniveau Lezen, heeft geen groepen of gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="3b687-141">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="3b687-142">Dit zijn de standaardmachtigingen voor de teamsite.</span><span class="sxs-lookup"><span data-stu-id="3b687-142">Here are the default permissions for the Team Site.</span></span>

![De standaardmachtigingen van een teamsite](../media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="3b687-144">Als u de \<teamnaam > SharePoint-groep Eigenaren bekijkt voor het machtigingsniveau Bewerken, wordt \<teamnaam > Eigenaren niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3b687-144">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="3b687-145">Met de resulterende machtigingen kunnen:</span><span class="sxs-lookup"><span data-stu-id="3b687-145">The resulting permissions allow:</span></span>

- <span data-ttu-id="3b687-146">Eigenaren van de teamgroep de site beheren en beschikken over volledige controle over de inhoud van de site.</span><span class="sxs-lookup"><span data-stu-id="3b687-146">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="3b687-147">Leden van de teamgroep bestanden op de site maken en bewerken.</span><span class="sxs-lookup"><span data-stu-id="3b687-147">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="3b687-148">Het onderhoud van machtigingen is hetzelfde als het onderhoud van teamleden en eigenaren.</span><span class="sxs-lookup"><span data-stu-id="3b687-148">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="3b687-149">Dit is de resulterende configuratie tot nu toe.</span><span class="sxs-lookup"><span data-stu-id="3b687-149">Here’s the resulting configuration so far.</span></span>

![Stap 2 van de configuratie van het scenario voor het beveiligde team](../media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="3b687-151">Stap 3: de onderliggende SharePoint-site configureren voor extra beveiliging</span><span class="sxs-lookup"><span data-stu-id="3b687-151">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="3b687-152">Configureer deze machtigingsinstellingen vanaf de teamsite.</span><span class="sxs-lookup"><span data-stu-id="3b687-152">From the Team Site, configure these permission settings.</span></span>

1. <span data-ttu-id="3b687-153">Klik in de werkbalk op het pictogram Instellingen en vervolgens op **Site-machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="3b687-153">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="3b687-154">Klik in het deelvenster **Site-machtigingen**, onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="3b687-154">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="3b687-155">Kies onder **Machtigingen voor delen**, **Alleen site-eigenaren kunnen bestanden, mappen en de site delen**.</span><span class="sxs-lookup"><span data-stu-id="3b687-155">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="3b687-156">Schakel **Toegangsaanvragen toestaan** uit en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3b687-156">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="3b687-157">Met deze instellingen kunnen leden van de teamsite de teamsite niet delen met andere leden en kunnen niet-leden geen toegang tot de site aanvragen.</span><span class="sxs-lookup"><span data-stu-id="3b687-157">With these settings, the ability for Team Group members to share the Team Site with other members or for non-members to request access to the Team Site is disabled.</span></span>

<span data-ttu-id="3b687-158">Dit is de resulterende configuratie tot nu toe.</span><span class="sxs-lookup"><span data-stu-id="3b687-158">Here’s the resulting configuration so far.</span></span>

![Stap 3 van de configuratie van het scenario voor het beveiligde team](../media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="3b687-160">Stap 4: een retentielabel en DLP-beleid maken</span><span class="sxs-lookup"><span data-stu-id="3b687-160">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="3b687-161">Volg [deze instructies](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp) om:</span><span class="sxs-lookup"><span data-stu-id="3b687-161">Use [these instructions](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp) to:</span></span>

1. <span data-ttu-id="3b687-162">Een retentielabel voor sterk gereglementeerde gegevens (indien nodig) te maken en te publiceren.</span><span class="sxs-lookup"><span data-stu-id="3b687-162">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="3b687-163">De teamsite te configureren voor het in stap 1 gemaakte retentielabel.</span><span class="sxs-lookup"><span data-stu-id="3b687-163">Configure the Team Site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="3b687-164">DLP-beleid te maken voor sterk gereglementeerde gegevens die het in stap 2 gemaakte retentielabel gebruiken en waarmee gebruikers bestanden niet buiten de organisatie kunnen verzenden.</span><span class="sxs-lookup"><span data-stu-id="3b687-164">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization.</span></span> <span data-ttu-id="3b687-165">U kunt het beleid ook configureren voor aanvullende vereisten, zoals die voor de regelgeving voor gezondheidsinstanties en de financiële sector, op basis van [DLP-beleidssjablonen](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="3b687-165">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="3b687-166">Dit is de resulterende configuratie tot nu toe.</span><span class="sxs-lookup"><span data-stu-id="3b687-166">Here’s the resulting configuration so far.</span></span>

![Stap 4 van de configuratie van het scenario voor het beveiligde team](../media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-a-sensitivity-label-or-a-sublabel-of-the-highly-regulated-sensitivity-label"></a><span data-ttu-id="3b687-168">Stap 5: een gevoeligheidslabel of een sublabel maken van het sterk gereglementeerde gevoeligheidslabel</span><span class="sxs-lookup"><span data-stu-id="3b687-168">Step 5: Create a sensitivity label or a sublabel of the highly regulated sensitivity label</span></span>

<span data-ttu-id="3b687-169">Een beveiligd team heeft, in tegenstelling tot een gevoeligheidslabel voor sterk gereglementeerde gegevens die iedereen op een bestand kan toepassen, een eigen label of sublabel nodig, zodat toegewezen bestanden:</span><span class="sxs-lookup"><span data-stu-id="3b687-169">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="3b687-170">Zijn versleuteld en de versleuteling wordt meeverplaatst met het bestand.</span><span class="sxs-lookup"><span data-stu-id="3b687-170">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="3b687-171">Aangepaste machtigingen bevatten, zodat alleen leden van de teamgroep ze kunnen openen.</span><span class="sxs-lookup"><span data-stu-id="3b687-171">Contain custom permissions so that only members of the Team Group can open it.</span></span>

<span data-ttu-id="3b687-172">Om dit extra beveiligingsniveau te halen voor bestanden die zijn opgeslagen op de teamsite, moet u een nieuw gevoeligheidslabel configureren dat een afzonderlijk label is of een sublabel van het algemene label voor sterk gereglementeerde bestanden.</span><span class="sxs-lookup"><span data-stu-id="3b687-172">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="3b687-173">Alleen leden van de teamgroep zien dit in hun lijst met labels.</span><span class="sxs-lookup"><span data-stu-id="3b687-173">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="3b687-174">Gebruik een gevoeligheidslabel wanneer u een klein aantal labels nodig hebt voor zowel algemeen gebruik als afzonderlijke privéteams.</span><span class="sxs-lookup"><span data-stu-id="3b687-174">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="3b687-175">Gebruik een gevoeligheidssublabel wanneer u een groot aantal labels nodig hebt of als u labels wilt organiseren voor privéteams onder het sterk gereglementeerde label.</span><span class="sxs-lookup"><span data-stu-id="3b687-175">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams under the highly regulated label.</span></span>

<span data-ttu-id="3b687-176">[Gebruik deze instructies](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) om een afzonderlijk label of sublabel met de volgende instellingen te configureren:</span><span class="sxs-lookup"><span data-stu-id="3b687-176">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="3b687-177">De naam van het label bevat de naam van het team</span><span class="sxs-lookup"><span data-stu-id="3b687-177">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="3b687-178">Versleuteling is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="3b687-178">Encryption is enabled</span></span>
- <span data-ttu-id="3b687-179">De sitegroep heeft machtigingen voor Medeauteurs</span><span class="sxs-lookup"><span data-stu-id="3b687-179">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="3b687-180">Hier ziet u de resulterende configuratie met het nieuwe label.</span><span class="sxs-lookup"><span data-stu-id="3b687-180">Here’s the resulting configuration with the new label.</span></span>

![Stap 5 van de configuratie van het scenario voor het beveiligde team](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="3b687-182">Hier ziet u de relatie tussen het gevoeligheidslabel en de teamgroep.</span><span class="sxs-lookup"><span data-stu-id="3b687-182">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![Relatie tussen de teamgroep en de labelmachtigingen](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="3b687-184">Als u het gevoeligheidslabel of -sublabel configureert voor door de gebruiker gedefinieerde machtigingen of met een vervaldatum, kunt u het bestand niet openen vanuit Teams of SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3b687-184">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint.</span></span> <span data-ttu-id="3b687-185">U moet een Office-app gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3b687-185">You must use an Office app.</span></span>
>

### <a name="custom-permissions"></a><span data-ttu-id="3b687-186">Aangepaste machtigingen</span><span class="sxs-lookup"><span data-stu-id="3b687-186">Custom permissions</span></span>

<span data-ttu-id="3b687-187">U kunt ook aangepaste SharePoint-sitemachtigingen configureren voor de teamsite en zo nodig ook het bijbehorende gevoeligheidslabel.</span><span class="sxs-lookup"><span data-stu-id="3b687-187">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="3b687-188">Hier volgen twee voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="3b687-188">Here are two examples.</span></span>

#### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="3b687-189">Voorbeeld 1: het beheer van SharePoint-sites delegeren</span><span class="sxs-lookup"><span data-stu-id="3b687-189">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="3b687-190">Als de teameigenaar geen ervaring heeft met het beheer van SharePoint of het beheer van de teamsite wil delegeren, kan hij of zij het gebruikersaccount van een SharePoint-beheerder toevoegen aan de lijst met teameigenaren.</span><span class="sxs-lookup"><span data-stu-id="3b687-190">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="3b687-191">De SharePoint-beheerder heeft dan echter volledige toegang tot het team en alle bijbehorende resources en kan bestanden openen waarop het gevoeligheidslabel is toegepast.</span><span class="sxs-lookup"><span data-stu-id="3b687-191">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="3b687-192">Om te voorkomen dat er te veel bevoegdheden worden verleend, voegt u het gebruikersaccount van de SharePoint-beheerder toe aan de SharePoint-groep met teamsite-eigenaren in de geavanceerde machtigingsinstellingen van de site.</span><span class="sxs-lookup"><span data-stu-id="3b687-192">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="3b687-193">De SharePoint-beheerder kan de site beheren, maar heeft geen toegang tot het team of de bijbehorende resources en kan de bestanden waaraan het gevoeligheidslabel is toegewezen, niet openen.</span><span class="sxs-lookup"><span data-stu-id="3b687-193">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="3b687-194">Voorbeeld 2: alleen-lezen toegang tot bestanden met een label toestaan</span><span class="sxs-lookup"><span data-stu-id="3b687-194">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="3b687-195">Als sommige medewerkers alleen de inhoud van gelabelde bestanden op de teamsite hoeven te bekijken, voegt u hun individuele gebruikersaccounts toe aan de:</span><span class="sxs-lookup"><span data-stu-id="3b687-195">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="3b687-196">\<teamnaam > groep SharePoint-bezoekers, die standaard het machtigingsniveau Lezen heeft.</span><span class="sxs-lookup"><span data-stu-id="3b687-196">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="3b687-197">Het gevoeligheidslabel met de machtigingen voor bezoekers.</span><span class="sxs-lookup"><span data-stu-id="3b687-197">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="3b687-198">Dit zijn de resulterende machtigingen voor het label.</span><span class="sxs-lookup"><span data-stu-id="3b687-198">Here are the resulting permissions on the label.</span></span>

![Voorbeeld van aangepaste machtigingen voor het weergeven van gelabelde bestanden](../media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="3b687-200">De sitebezoekers hebben rechtstreeks toegang tot de teamsite en kunnen de inhoud bekijken van bestanden waarop het sublabel is toegepast.</span><span class="sxs-lookup"><span data-stu-id="3b687-200">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="3b687-201">Maar omdat ze geen lid zijn van de teamgroep, hebben ze geen toegang tot het team of de bijbehorende resources.</span><span class="sxs-lookup"><span data-stu-id="3b687-201">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>


## <a name="phase-2-drive-user-adoption-for-team-members"></a><span data-ttu-id="3b687-202">Fase 2: Ingebruikname door teamleden bevorderen</span><span class="sxs-lookup"><span data-stu-id="3b687-202">Phase 2: Drive user adoption for team members</span></span>

<span data-ttu-id="3b687-203">Nu het team is ingesteld, is het tijd om de ingebruikname van dit team en de extra beveiliging voor teamleden te stimuleren.</span><span class="sxs-lookup"><span data-stu-id="3b687-203">With the team in place, it’s time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="3b687-204">Stap 1: uw gebruikers trainen</span><span class="sxs-lookup"><span data-stu-id="3b687-204">Step 1: Train your users</span></span>

<span data-ttu-id="3b687-205">Leden van de teamgroep hebben toegang tot het team en alle bijbehorende resources, inclusief chats, vergaderingen en andere apps.</span><span class="sxs-lookup"><span data-stu-id="3b687-205">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="3b687-206">Wanneer u werkt met bestanden in de sectie **Bestanden** van een kanaal, moeten leden van de teamgroep het gevoeligheidslabel of -sublabel toewijzen aan bestanden die zijn gemaakt voor het beveiligde team.</span><span class="sxs-lookup"><span data-stu-id="3b687-206">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="3b687-207">Hier ziet u een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="3b687-207">Here’s an example.</span></span>

![Voorbeeld van een label dat is toegepast op een bestand in een beveiligd team](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="3b687-209">Wanneer het label wordt toegepast op het bestand, is het beveiligd.</span><span class="sxs-lookup"><span data-stu-id="3b687-209">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="3b687-210">Leden van de teamgroep kunnen het bestand openen in Teams en in realtime samenwerken.</span><span class="sxs-lookup"><span data-stu-id="3b687-210">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="3b687-211">Het bestand is versleuteld en de machtigingen voor medeauteurs zijn ingesteld op de leden van de teamgroep.</span><span class="sxs-lookup"><span data-stu-id="3b687-211">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="3b687-212">Als het bestand de site verlaat en wordt doorgestuurd naar een kwaadwillende gebruiker, moet hij of zij referenties opgeven voor een gebruikersaccount dat lid is van de teamgroep om het bestand te openen en de inhoud te bekijken.</span><span class="sxs-lookup"><span data-stu-id="3b687-212">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="3b687-213">Leer uw teamleden:</span><span class="sxs-lookup"><span data-stu-id="3b687-213">Train your team members:</span></span>

- <span data-ttu-id="3b687-214">het belang van het gebruik van het nieuwe team voor chats, vergaderingen, bestanden en de andere resources van de teamsite en de consequenties van een gegevenslek van sterk gereglementeerde gegevens, zoals juridische gevolgen, boetes, ransomware of verlies van concurrentievoordeel.</span><span class="sxs-lookup"><span data-stu-id="3b687-214">On the importance of using the new team for chats, meetings, files, and the other resources of the Team Site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="3b687-215">hoe ze toegang hebben tot het team.</span><span class="sxs-lookup"><span data-stu-id="3b687-215">How to access the team.</span></span>
- <span data-ttu-id="3b687-216">hoe ze nieuwe bestanden op de site kunnen maken en nieuwe bestanden kunnen uploaden die lokaal zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="3b687-216">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="3b687-217">hoe het DLP-beleid voorkomt dat ze bestanden extern delen.</span><span class="sxs-lookup"><span data-stu-id="3b687-217">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="3b687-218">hoe ze het aangepaste label of sublabel voor het team kunnen toepassen op bestanden.</span><span class="sxs-lookup"><span data-stu-id="3b687-218">How to label files with the custom label or sublabel for the team.</span></span>
- <span data-ttu-id="3b687-219">hoe het label of sublabel bestanden beschermt, zelfs wanneer deze buiten de site worden gelekt.</span><span class="sxs-lookup"><span data-stu-id="3b687-219">How the label or sublabel protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="3b687-220">Bij deze training horen praktijkoefeningen, zodat de teamleden deze functies en de resultaten ervan kunnen ervaren.</span><span class="sxs-lookup"><span data-stu-id="3b687-220">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="3b687-221">Stap 2: periodiek het gebruik bekijken en feedback van teamleden verwerken</span><span class="sxs-lookup"><span data-stu-id="3b687-221">Step 2: Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="3b687-222">In de weken na de training:</span><span class="sxs-lookup"><span data-stu-id="3b687-222">In the weeks after training:</span></span>

- <span data-ttu-id="3b687-223">Verwerk de feedback van teamleden snel en verfijn beleidsregels en configuraties.</span><span class="sxs-lookup"><span data-stu-id="3b687-223">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="3b687-224">Analyseer het gebruik van het team en vergelijk dit met gebruiksverwachtingen.</span><span class="sxs-lookup"><span data-stu-id="3b687-224">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="3b687-225">Verifieer dat gereglementeerde bestanden juist zijn gelabeld met het aangepaste gevoeligheidslabel of sublabel.</span><span class="sxs-lookup"><span data-stu-id="3b687-225">Verify that highly regulated files have been properly labeled with the custom sensitivity label or sublabel.</span></span>

  <span data-ttu-id="3b687-226">U kunt zien welke bestanden een label hebben door een map te bekijken in SharePoint en de kolom **Gevoeligheid** toe te voegen met de optie **Kolommen weergeven/verbergen** of **Kolom toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="3b687-226">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="3b687-227">School de gebruikers indien nodig bij.</span><span class="sxs-lookup"><span data-stu-id="3b687-227">Retrain your users as needed.</span></span>

## <a name="demonstrate-this-in-a-test-environment"></a><span data-ttu-id="3b687-228">Laat dit zien in een testomgeving</span><span class="sxs-lookup"><span data-stu-id="3b687-228">Demonstrate this in a test environment</span></span>

<span data-ttu-id="3b687-229">Zie [deze instructies](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment) als u uw eigen testomgeving wilt maken om teams te testen op gevoelige en zeer vertrouwelijke bestanden.</span><span class="sxs-lookup"><span data-stu-id="3b687-229">To build out your own test environment to test teams for sensitive and highly confidential files, see [these instructions](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment).</span></span> 

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)

## <a name="how-the-contoso-corporation-used-a-secure-team-for-a-top-secret-project"></a><span data-ttu-id="3b687-231">Hoe Contoso Corporation een beveiligd team gebruikte voor een zeer geheim project</span><span class="sxs-lookup"><span data-stu-id="3b687-231">How the Contoso Corporation used a secure team for a top-secret project</span></span>

<span data-ttu-id="3b687-232">De Contoso Corporation is een fictief maar representatief wereldwijd productieconglomeraat.</span><span class="sxs-lookup"><span data-stu-id="3b687-232">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="3b687-233">Bekijk hoe Contoso de ingebruikname van een [beveiligd team](contoso-team-for-top-secret-project.md) heeft gestimuleerd voor een zeer geheim project waarin nieuwe producten en services werden ontwikkeld en op de markt gebracht.</span><span class="sxs-lookup"><span data-stu-id="3b687-233">See how Contoso configured and drove the adoption of a [secure team](contoso-team-for-top-secret-project.md) for a top secret project to develop and bring to market a new set of products and services.</span></span> 

## <a name="see-also"></a><span data-ttu-id="3b687-234">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3b687-234">See also</span></span>

[<span data-ttu-id="3b687-235">SharePoint-sites voor sterk gereglementeerde gegevens</span><span class="sxs-lookup"><span data-stu-id="3b687-235">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="3b687-236">Microsoft 365 Enterprise-bedrijfsworkloads en -scenario's</span><span class="sxs-lookup"><span data-stu-id="3b687-236">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="3b687-237">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="3b687-237">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="3b687-238">Implementatiehandleiding</span><span class="sxs-lookup"><span data-stu-id="3b687-238">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
