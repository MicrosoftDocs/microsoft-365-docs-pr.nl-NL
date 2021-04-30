---
title: 'Binnenkort beschikbaar: Configureer SharePoint als een leerinhoudsbron voor Microsoft Viva Learning (Preview)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Meer informatie over het configureren SharePoint als een leerinhoudsbron voor Microsoft Viva Learning (Preview).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: da75ec0573519ed73507994afeac995c0461de0c
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100894"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a><span data-ttu-id="bb35c-103">Binnenkort beschikbaar: Configureer SharePoint als een leerinhoudsbron voor Microsoft Viva Learning (Preview)</span><span class="sxs-lookup"><span data-stu-id="bb35c-103">Coming soon: Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="bb35c-104">De informatie in dit artikel heeft betrekking op een voorbeeldproduct dat aanzienlijk kan worden gewijzigd voordat het commercieel wordt uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="bb35c-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="bb35c-105">U kunt de SharePoint als een leerinhoudsbron configureren om de eigen inhoud van uw organisatie beschikbaar te maken in Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="bb35c-105">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="bb35c-106">Overzicht</span><span class="sxs-lookup"><span data-stu-id="bb35c-106">Overview</span></span>

<span data-ttu-id="bb35c-107">De kennisbeheerder (of globale beheerder) biedt een site-URL aan waar de Learning Service een lege gecentraliseerde locatie kan maken, de Learning App Content Repository, in de vorm van een gestructureerde SharePoint lijst.</span><span class="sxs-lookup"><span data-stu-id="bb35c-107">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="bb35c-108">Deze lijst kan door uw organisatie worden gebruikt om koppelingen naar meerdere bedrijfsmappen SharePoint bevatten die leerinhoud bevatten.</span><span class="sxs-lookup"><span data-stu-id="bb35c-108">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="bb35c-109">Beheerders zijn verantwoordelijk voor het verzamelen en cureren van een lijst met URL's voor mappen.</span><span class="sxs-lookup"><span data-stu-id="bb35c-109">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="bb35c-110">Deze mappen mogen alleen inhoud bevatten die beschikbaar kan worden gesteld in Viva Learning (preview).</span><span class="sxs-lookup"><span data-stu-id="bb35c-110">These folders should only include content that can be made available in Viva Learning (Preview).</span></span>

<span data-ttu-id="bb35c-111">Viva Learning (Preview) ondersteunt de volgende documenttypen:</span><span class="sxs-lookup"><span data-stu-id="bb35c-111">Viva Learning (Preview) supports the following document types:</span></span>

- <span data-ttu-id="bb35c-112">Word, PowerPoint, Excel, PDF</span><span class="sxs-lookup"><span data-stu-id="bb35c-112">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="bb35c-113">Audio (.m4a)</span><span class="sxs-lookup"><span data-stu-id="bb35c-113">Audio (.m4a)</span></span>
- <span data-ttu-id="bb35c-114">Video (.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="bb35c-114">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="bb35c-115">Zie de onlinedocumentatie SharePoint [voor meer informatie.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)</span><span class="sxs-lookup"><span data-stu-id="bb35c-115">For more information, see the [SharePoint Online documentation](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span> 

## <a name="permissions"></a><span data-ttu-id="bb35c-116">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="bb35c-116">Permissions</span></span>

<span data-ttu-id="bb35c-117">URL's voor documentbibliotheekmappen kunnen worden verzameld vanaf SharePoint site in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="bb35c-117">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="bb35c-118">Viva Learning (Preview) volgt alle bestaande inhoudsmachtigingen.</span><span class="sxs-lookup"><span data-stu-id="bb35c-118">Viva Learning (Preview) follows all existing content permissions.</span></span> <span data-ttu-id="bb35c-119">Daarom is alleen inhoud waarvoor een gebruiker toegang heeft, doorzoekbaar en zichtbaar in Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="bb35c-119">Therefore, only content for which a user has permission to access is searchable and visable within Viva Learning (Preview).</span></span> <span data-ttu-id="bb35c-120">Inhoud in deze mappen kan worden doorzocht, maar alleen inhoud waaraan de afzonderlijke werknemer machtigingen heeft, kan worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="bb35c-120">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="bb35c-121">Het verwijderen van inhoud uit de opslagplaats van uw organisatie wordt momenteel niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="bb35c-121">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="bb35c-122">Als u onbedoeld opgedoken inhoud wilt verwijderen, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="bb35c-122">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="bb35c-123">Als u de toegang tot de documentbibliotheek wilt beperken, selecteert u de optie Acties **tonen** en selecteert u **Vervolgens Toegang beheren.**</span><span class="sxs-lookup"><span data-stu-id="bb35c-123">To restrict access to the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Pagina documentbibliotheek in SharePoint met de optie Acties weergeven met Toegang hoogbeligd beheren.](../media/learning/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="bb35c-125">Verwijder het oorspronkelijke document in de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="bb35c-125">Delete the original document within the document library.</span></span>

<span data-ttu-id="bb35c-126">Zie Delen en machtigingen in de moderne SharePoint [voor meer informatie.](/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="bb35c-126">For more information, see [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span></span> 

## <a name="learning-service"></a><span data-ttu-id="bb35c-127">Leerservice</span><span class="sxs-lookup"><span data-stu-id="bb35c-127">Learning Service</span></span>

<span data-ttu-id="bb35c-128">De Learning Service gebruikt de meegeleverde map-URL's om metagegevens op te halen uit alle inhoud die in die mappen is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="bb35c-128">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="bb35c-129">Binnen 24 uur na het leveren van de MAP-URL in de gecentraliseerde opslagplaats kunnen werknemers de inhoud van uw organisatie zoeken en gebruiken in Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="bb35c-129">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (Preview).</span></span> <span data-ttu-id="bb35c-130">Alle wijzigingen in inhoud, inclusief bijgewerkte metagegevens en machtigingen, worden ook binnen 24 uur toegepast in de Leerservice.</span><span class="sxs-lookup"><span data-stu-id="bb35c-130">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

## <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="bb35c-131">Een SharePoint als bron configureren</span><span class="sxs-lookup"><span data-stu-id="bb35c-131">Configure SharePoint as a source</span></span>

<span data-ttu-id="bb35c-132">U moet een globale Microsoft 365, beheerder SharePoint of kennisbeheerder zijn om deze taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="bb35c-132">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="bb35c-133">Als u een SharePoint wilt configureren als een leerinhoudsbron in voor Viva Learning (voorbeeld), volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="bb35c-133">To configure SharePoint as a learning content sources in for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="bb35c-134">Ga in de linkernavigatie van het Microsoft 365 beheercentrum **naar Instellingen**  >  **Organisatie-instellingen.**</span><span class="sxs-lookup"><span data-stu-id="bb35c-134">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="bb35c-135">Selecteer op **de pagina Organisatie-instellingen** op het **tabblad Services** de **optie Leer-app (Voorbeeld)**.</span><span class="sxs-lookup"><span data-stu-id="bb35c-135">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![Instellingen pagina in het Microsoft 365-beheercentrum met Viva Learning weergegeven.](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="bb35c-137">In het **deelvenster Leer-app (Preview)** onder SharePoint, wordt de SITE-URL weergegeven naar de SharePoint site waar u wilt dat Viva Learning een gecentraliseerde opslagplaats maakt.</span><span class="sxs-lookup"><span data-stu-id="bb35c-137">On the **Learning app (Preview)** panel, under SharePoint, provides the site URL to the SharePoint site where you want Viva Learning to create a centralized repository.</span></span>

     ![Leervenster in het Microsoft 365-beheercentrum met SharePoint geselecteerd.](../media/learning/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="bb35c-139">Een SharePoint wordt automatisch gemaakt binnen de opgegeven SharePoint site.</span><span class="sxs-lookup"><span data-stu-id="bb35c-139">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![Nieuw gemaakte SharePoint in de SharePoint site.](../media/learning/learning-sharepoint-configure3.png)

     <span data-ttu-id="bb35c-141">Selecteer in de linkernavigatie van de SharePoint site **Site-inhoud**  >  **Learning App Content Repository**.</span><span class="sxs-lookup"><span data-stu-id="bb35c-141">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![SharePoint lijst met de navigatie van site-inhoud en de sectie Inhoudsopslag voor leer-apps.](../media/learning/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="bb35c-143">Vul op **de pagina Inhoudsopslag** van leer-apps de SharePoint met URL's in de mappen met leerinhoud.</span><span class="sxs-lookup"><span data-stu-id="bb35c-143">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="bb35c-144">Selecteer **Nieuw om** het deelvenster Nieuw item **te** bekijken.</span><span class="sxs-lookup"><span data-stu-id="bb35c-144">Select **New** to view the **New item** panel.</span></span> 

       ![Pagina Leerinhoudsopslagplaats in SharePoint met de optie Nieuw.](../media/learning/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="bb35c-146">Voeg in **het deelvenster** Nieuw item in **het** veld Titel een adreslijstnaam van uw keuze toe.</span><span class="sxs-lookup"><span data-stu-id="bb35c-146">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="bb35c-147">Voeg in **het veld Map-URL** de URL toe aan de map leerinhoud.</span><span class="sxs-lookup"><span data-stu-id="bb35c-147">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="bb35c-148">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="bb35c-148">Select **Save**.</span></span>

       ![Nieuw itemvenster in SharePoint met de velden Titel en Map-URL.](../media/learning/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="bb35c-150">De **pagina Learning App Content Repository** wordt bijgewerkt met de nieuwe leerinhoud.</span><span class="sxs-lookup"><span data-stu-id="bb35c-150">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![Pagina Learning Content Repository in SharePoint met de bijgewerkte informatie.](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="bb35c-152">Als u een bredere toegang tot de Inhoudsopslagplaats voor leer-apps wilt toestaan, is er binnenkort een koppeling naar de lijst beschikbaar in de interface Viva Learning (Preview), waar gebruikers toegang kunnen aanvragen en uiteindelijk kunnen helpen de lijst in te vullen.</span><span class="sxs-lookup"><span data-stu-id="bb35c-152">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (Preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="bb35c-153">Site-eigenaren en globale beheerders moeten toegang verlenen tot de lijst.</span><span class="sxs-lookup"><span data-stu-id="bb35c-153">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="bb35c-154">Access is alleen specifiek voor de lijst en is niet van toepassing op de site waar de lijst is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="bb35c-154">Access is specific to the list only and does not apply to the site where the list is stored.</span></span> <span data-ttu-id="bb35c-155">Zie De inhoud van [uw](#provide-your-own-organizations-content) eigen organisatie later in dit artikel verstrekken voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bb35c-155">For more information, see [Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="bb35c-156">Map URL document library curation</span><span class="sxs-lookup"><span data-stu-id="bb35c-156">Folder URL document library curation</span></span>

<span data-ttu-id="bb35c-157">Standaardmetagegevens (zoals gewijzigde datum, gemaakt door, documentnaam, inhoudstype en organisatienaam) worden automatisch in Viva Learning (Preview) getrokken door de Microsoft Graph API.</span><span class="sxs-lookup"><span data-stu-id="bb35c-157">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (Preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="bb35c-158">Als u de algehele detectie en zoekrelevantie van de inhoud wilt verbeteren, raden we u aan een kolom **Beschrijving toe te** voegen.</span><span class="sxs-lookup"><span data-stu-id="bb35c-158">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="bb35c-159">Als u een kolom **Beschrijving wilt** toevoegen aan de pagina van de documentbibliotheek, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="bb35c-159">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="bb35c-160">Selecteer op **de pagina** Documenten de optie **Kolom toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="bb35c-160">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="bb35c-161">Selecteer de **optie Acties tonen** en selecteer vervolgens Enkele regel **tekst.**</span><span class="sxs-lookup"><span data-stu-id="bb35c-161">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![Pagina Documenten in SharePoint met de opties Acties weergeven met Één regel tekst gemarkeerd.](../media/learning/learning-sharepoint-curation1.png)

3. <span data-ttu-id="bb35c-163">Voeg in **het deelvenster** Een kolom maken in het veld **Naam** een beschrijvende naam voor de kolom toe.</span><span class="sxs-lookup"><span data-stu-id="bb35c-163">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="bb35c-164">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="bb35c-164">Select **Save**.</span></span>

     ![Maak een kolomvenster in SharePoint met de naam en andere velden.](../media/learning/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="bb35c-166">Voeg op **de** pagina Documenten in **de** kolom Beschrijving aangepaste beschrijvingen toe voor elk item.</span><span class="sxs-lookup"><span data-stu-id="bb35c-166">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="bb35c-167">Als er geen beschrijving wordt opgegeven, wordt in Viva Learning (Preview) een standaardbericht weergegeven waarin de inhoud wordt benadrukt als afkomstig uit uw eigen SharePoint bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="bb35c-167">If no description is supplied, Viva Learning (Preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![Pagina Documenten in SharePoint met de beschrijvingen in de kolom Beschrijving.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a><span data-ttu-id="bb35c-169">De inhoud van uw eigen organisatie leveren</span><span class="sxs-lookup"><span data-stu-id="bb35c-169">Provide your own organization's content</span></span>

<span data-ttu-id="bb35c-170">Kennisbeheerders hebben toegang tot de Learning App Content Repository van hun organisatie in SharePoint, waar ze verwijzingen kunnen bieden naar documentbibliotheken binnen verschillende organisaties.</span><span class="sxs-lookup"><span data-stu-id="bb35c-170">Knowledge admins can access their organization’s Learning App Content Repository in SharePoint, where they can provide references to cross-organization document libraries.</span></span> <span data-ttu-id="bb35c-171">Inhoud in deze bibliotheken wordt vervolgens weergegeven als leerinhoud in Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="bb35c-171">Content within these libraries will be then surfaced as learning content in Viva Learning (Preview).</span></span>

1. <span data-ttu-id="bb35c-172">Selecteer in Viva Learning (Preview) **Meer opties** **(...)** en selecteer vervolgens **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="bb35c-172">In Viva Learning (Preview), select **More options** (**...**), and then select **Settings**.</span></span>

     ![SharePoint bibliotheekpagina met de optie Meer opties en Instellingen.](../media/learning/learning-sharepoint-library-1.png)
     
2. <span data-ttu-id="bb35c-174">Selecteer **onder Instellingen** **machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="bb35c-174">Under **Settings**, select **Permissions**.</span></span>

     ![Instellingen optiepagina in SharePoint met de opties Machtigingen en Toegang controleren.](../media/learning/learning-sharepoint-library-2.png)

3. <span data-ttu-id="bb35c-176">Selecteer **Toegang controleren** om verbinding te maken met de gecentraliseerde bibliotheek van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bb35c-176">Select **Check access** to connect to your organization’s centralized library.</span></span>
     
