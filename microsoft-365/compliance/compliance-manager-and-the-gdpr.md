---
title: Microsoft Compliance Manager en de AVG
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager is een gratis hulpprogramma voor risicoanalyse op basis van werkstroom in de Microsoft Service Trust Portal. Met Compliance Manager kunt u nalevingsactiviteiten met betrekking tot Microsoft-cloudservices bijhouden, toewijzen en controleren.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "52161432"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="f84c7-104">Microsoft Compliance Manager en de AVG</span><span class="sxs-lookup"><span data-stu-id="f84c7-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="f84c7-105">De Algemene verordening gegevensbescherming (AVG) van de Europese Unie kan van invloed zijn op uw compliancestrategie en specifieke acties voor het beheren van gebruikers- en klantgegevens die worden gebruikt in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="f84c7-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="f84c7-106">Privacy-instellingen voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="f84c7-106">User Privacy settings</span></span>

<span data-ttu-id="f84c7-107">Bepaalde voorschriften vereisen dat een organisatie gebruikersgeschiedenisgegevens moet kunnen verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f84c7-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="f84c7-108">Compliance Manager biedt **gebruikers privacy Instellingen** functies waarmee beheerders:</span><span class="sxs-lookup"><span data-stu-id="f84c7-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="f84c7-109">Een gebruiker zoeken</span><span class="sxs-lookup"><span data-stu-id="f84c7-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="f84c7-110">Een rapport met accountgegevensgeschiedenis exporteren</span><span class="sxs-lookup"><span data-stu-id="f84c7-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="f84c7-111">Gebruikersgegevensgeschiedenis verwijderen</span><span class="sxs-lookup"><span data-stu-id="f84c7-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="f84c7-112">Een gebruiker zoeken</span><span class="sxs-lookup"><span data-stu-id="f84c7-112">Search for a user</span></span>

<span data-ttu-id="f84c7-113">Een gebruikersaccount zoeken:</span><span class="sxs-lookup"><span data-stu-id="f84c7-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="f84c7-114">Voer de e-mailalias van de gebruiker in (de informatie links van het @-symbool) en kies de domeinnaam in de lijst met domeinachtervoegsels aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="f84c7-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="f84c7-115">Controleer voor organisaties met meerdere geregistreerde domeinen het achtervoegsel van de domeinnaam om te controleren of het juist is.</span><span class="sxs-lookup"><span data-stu-id="f84c7-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="f84c7-116">Wanneer u de gebruikersnaam correct hebt ingevoerd, selecteert u **Zoeken.**</span><span class="sxs-lookup"><span data-stu-id="f84c7-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="f84c7-117">Voor gebruikersaccounts die niet worden geretourneerd, wordt op de pagina **Gebruiker niet gevonden weergegeven.**</span><span class="sxs-lookup"><span data-stu-id="f84c7-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="f84c7-118">Controleer de e-mailadresgegevens van de gebruiker en correcties indien nodig.</span><span class="sxs-lookup"><span data-stu-id="f84c7-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="f84c7-119">Als u opnieuw wilt proberen, **selecteert** u Zoeken .</span><span class="sxs-lookup"><span data-stu-id="f84c7-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="f84c7-120">Voor geretourneerde gebruikersaccounts verandert de tekst van de knop van **Zoeken in** **Leegmaken.**</span><span class="sxs-lookup"><span data-stu-id="f84c7-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="f84c7-121">Dit geeft aan dat het geretourneerde gebruikersaccount de bedrijfscontext is voor de extra functies en dat deze functies van toepassing zijn op dit gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="f84c7-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="f84c7-122">Als u zoekresultaten wilt leeg maken en wilt zoeken naar een andere gebruiker, selecteert u **Clear**.</span><span class="sxs-lookup"><span data-stu-id="f84c7-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="f84c7-123">Een rapport met accountgegevensgeschiedenis exporteren</span><span class="sxs-lookup"><span data-stu-id="f84c7-123">Export a report of account data history</span></span>

<span data-ttu-id="f84c7-124">Voor elk geïdentificeerd gebruikersaccount kunt u een rapport genereren met afhankelijkheden die aan het account zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="f84c7-124">For each user account identified, you can generate a report of dependencies linked to the account.</span></span> <span data-ttu-id="f84c7-125">Met deze informatie kunt u de geopende actie-items opnieuw toewijzen of ervoor zorgen dat u toegang hebt tot eerder geüpload bewijs.</span><span class="sxs-lookup"><span data-stu-id="f84c7-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="f84c7-126">Een rapport genereren en exporteren:</span><span class="sxs-lookup"><span data-stu-id="f84c7-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="f84c7-127">Selecteer **Exporteren** om een rapport te genereren en te downloaden van de actie-items voor compliancebeheer die momenteel zijn toegewezen aan het geretourneerde gebruikersaccount en de lijst met documenten die door die gebruiker zijn geüpload.</span><span class="sxs-lookup"><span data-stu-id="f84c7-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="f84c7-128">Als er geen toegewezen acties of geüploade documenten zijn, wordt in een foutbericht 'Geen gegevens voor deze gebruiker' weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f84c7-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="f84c7-129">Het rapport wordt gedownload op de achtergrond van het actieve browservenster, als u geen downloadpopup ziet die u de downloadgeschiedenis van uw browser wilt controleren.</span><span class="sxs-lookup"><span data-stu-id="f84c7-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="f84c7-130">Open het document om de rapportgegevens te bekijken.</span><span class="sxs-lookup"><span data-stu-id="f84c7-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f84c7-131">De rapportgegevens zijn geen historische lijst met statuswijzigingen in de toewijzingsgeschiedenis van actieitem.</span><span class="sxs-lookup"><span data-stu-id="f84c7-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="f84c7-132">Het gegenereerde rapport is een momentopname van het besturingselement Actie-items die zijn toegewezen op het moment dat het rapport wordt uitgevoerd (datum- en tijdstempel in het rapport).</span><span class="sxs-lookup"><span data-stu-id="f84c7-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="f84c7-133">Een volgende herplaatsing van actie-items resulteert bijvoorbeeld in verschillende momentopnamerapportgegevens als het rapport opnieuw voor dezelfde gebruiker wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="f84c7-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="f84c7-134">Gebruikersgegevensgeschiedenis verwijderen</span><span class="sxs-lookup"><span data-stu-id="f84c7-134">Delete user data history</span></span>

<span data-ttu-id="f84c7-135">Hiermee stelt u alle besturingselementactie-items in die zijn toegewezen aan de geretourneerde gebruiker op 'niet-toegewezen'.</span><span class="sxs-lookup"><span data-stu-id="f84c7-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="f84c7-136">Hiermee stelt **u de geüploade waarde** in voor documenten die door de geretourneerde gebruiker zijn geüpload naar 'gebruiker verwijderd'.</span><span class="sxs-lookup"><span data-stu-id="f84c7-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="f84c7-137">De geschiedenis van het gebruikersaccount actie-item en de uploadgeschiedenis van documenten verwijderen:</span><span class="sxs-lookup"><span data-stu-id="f84c7-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="f84c7-138">Selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="f84c7-138">Select **Delete**.</span></span>

    <span data-ttu-id="f84c7-139">Er wordt een bevestigingsdialoogvenster weergegeven: " Hiermee worden alle opdrachten voor actie-items en de uploadgeschiedenis van het document voor *de geselecteerde gebruiker verwijderd. Deze actie is permanent. Weet u zeker dat u wilt doorgaan?*"</span><span class="sxs-lookup"><span data-stu-id="f84c7-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="f84c7-140">Als u ok **wilt blijven selecteren,** selecteert u anders **Annuleren.**</span><span class="sxs-lookup"><span data-stu-id="f84c7-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
