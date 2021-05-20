---
title: Basisaudit instellen in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In dit artikel wordt beschreven hoe u Basisaudit kunt instellen, zodat u kunt zoeken naar auditactiviteiten die worden uitgevoerd door gebruikers en beheerders in uw organisatie.
ms.openlocfilehash: 59b5c85003ef0e19f7d3dd7417f764f446244652
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52564823"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a><span data-ttu-id="d339b-103">Basisaudit instellen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d339b-103">Set up Basic Audit in Microsoft 365</span></span>

<span data-ttu-id="d339b-104">Met Basisaudit in Microsoft 365 kunt u zoeken naar auditrecords voor activiteiten die in de verschillende Microsoft 365 door gebruikers en beheerders worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d339b-104">Basic Audit in Microsoft 365 lets you search for audit records for activities performed in the different Microsoft 365 services by users and admins.</span></span> <span data-ttu-id="d339b-105">Omdat Basisaudit standaard is ingeschakeld voor de meeste Microsoft 365- en Office 365-organisaties, hoeft u slechts een paar dingen te doen voordat u en anderen in uw organisatie het auditlogboek kunnen doorzoeken.</span><span class="sxs-lookup"><span data-stu-id="d339b-105">Because Basic Audit is enabled by default for most Microsoft 365 and Office 365 organizations, there's only a few things you need to do before you and others in your organization can search the audit log.</span></span>

<span data-ttu-id="d339b-106">In dit artikel worden de volgende stappen beschreven die nodig zijn om Basisaudit in te stellen.</span><span class="sxs-lookup"><span data-stu-id="d339b-106">This article discusses the following steps necessary to set up Basic Audit.</span></span>

![Stappen voor het instellen van basisaudit](../media/BasicAuditingWorkflow.png)

<span data-ttu-id="d339b-108">Deze stappen omvatten het waarborgen van de juiste organisatieabonnementen en gebruikerslicenties die nodig zijn voor het genereren en behouden van auditrecords en het toewijzen van machtigingen aan teamleden van uw beveiligingsbewerkingen, IT-, compliance- en juridische teams, zodat ze het auditlogboek kunnen doorzoeken.</span><span class="sxs-lookup"><span data-stu-id="d339b-108">These steps include ensuring the proper organizational subscriptions and user licensing required to generate and preserve audit records and assigning permissions to team members of your security operations, IT, compliance, and legal teams so that can search the audit log.</span></span>

<span data-ttu-id="d339b-109">Zie Basisaudit [in Microsoft 365.](auditing-solutions-overview.md#basic-audit)</span><span class="sxs-lookup"><span data-stu-id="d339b-109">For more information, see [Basic Audit in Microsoft 365](auditing-solutions-overview.md#basic-audit).</span></span>

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a><span data-ttu-id="d339b-110">Stap 1: Organisatieabonnement en gebruikerslicenties controleren</span><span class="sxs-lookup"><span data-stu-id="d339b-110">Step 1: Verify organization subscription and user licensing</span></span>

<span data-ttu-id="d339b-111">Voor licenties voor basisaudit is het juiste organisatieabonnement vereist dat toegang biedt tot het zoekprogramma voor auditlogboek en licenties per gebruiker die nodig zijn voor het aanmelden en behouden van auditrecords.</span><span class="sxs-lookup"><span data-stu-id="d339b-111">Licensing for Basic Audit requires the appropriate organization subscription that provides access to audit log search tool and per-user licensing that's required to log and retain audit records.</span></span>

<span data-ttu-id="d339b-112">Wanneer een gecontroleerde activiteit wordt uitgevoerd door een gebruiker of beheerder, wordt een auditrecord gegenereerd en opgeslagen in het auditlogboek voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d339b-112">When an audited activity is performed by a user or admin, an audit record is generated and stored in the audit log for your organization.</span></span> <span data-ttu-id="d339b-113">In Basisaudit worden auditrecords 90 dagen bewaard en doorzocht in het auditlogboek.</span><span class="sxs-lookup"><span data-stu-id="d339b-113">In Basic Audit, audit records are retained and searchable in the audit log for 90 days.</span></span>

<span data-ttu-id="d339b-114">Zie Auditing solutions in Microsoft 365 voor een lijst met abonnements- en [licentievereisten voor Basisaudit.](auditing-solutions-overview.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="d339b-114">For a list of subscription and licensing requirements for Basic Audit, see [Auditing solutions in Microsoft 365](auditing-solutions-overview.md#licensing-requirements).</span></span>

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a><span data-ttu-id="d339b-115">Stap 2: Machtigingen toewijzen om het auditlogboek te doorzoeken</span><span class="sxs-lookup"><span data-stu-id="d339b-115">Step 2: Assign permissions to search the audit log</span></span>

<span data-ttu-id="d339b-116">Beheerders en leden van onderzoeksteams moeten de rol auditlogboeken of auditlogboeken View-Only auditlogboeken in Exchange Online om het auditlogboek te doorzoeken.</span><span class="sxs-lookup"><span data-stu-id="d339b-116">Admins and members of investigation teams must be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="d339b-117">Deze rollen worden standaard toegewezen aan de rollengroepen Compliancebeheer en Organisatiebeheer op de pagina **Machtigingen** in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d339b-117">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="d339b-118">Globale beheerders in Office 365 en Microsoft 365 worden automatisch toegevoegd als leden van de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d339b-118">Global administrators in Office 365 and Microsoft 365 are automatically added as members of the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d339b-119">Als u de gebruiker het auditlogboek wilt laten doorzoeken met minimale rechten, kunt u in Exchange Online een aangepaste rollengroep maken, de rol Auditlogboeken alleen-weergeven of Auditlogboeken toevoegen en vervolgens de gebruiker toevoegen als lid van de nieuwe rollengroep.</span><span class="sxs-lookup"><span data-stu-id="d339b-119">To give a user the ability to search the audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="d339b-120">Zie voor meer informatie [Rollengroepen beheren in Exchange Online](/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="d339b-120">For more information, see [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>

<span data-ttu-id="d339b-121">In de volgende schermafbeelding ziet u de twee auditgerelateerde rollen die zijn toegewezen aan de rollengroep Organisatiebeheer in het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d339b-121">The following screenshot shows the two audit-related roles assigned to the Organization Management role group in the Exchange admin center.</span></span>

![Auditrollen die zijn toegewezen aan rollengroep in Exchange Online](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a><span data-ttu-id="d339b-123">Stap 3: Het auditlogboek doorzoeken</span><span class="sxs-lookup"><span data-stu-id="d339b-123">Step 3: Search the audit log</span></span>

<span data-ttu-id="d339b-124">Nu kunt u het auditlogboek doorzoeken in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="d339b-124">Now you're ready to search the audit log in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="d339b-125">Ga naar <https://compliance.microsoft.com> en meld u aan met een account dat de juiste controlemachtigingen heeft gekregen.</span><span class="sxs-lookup"><span data-stu-id="d339b-125">Go to <https://compliance.microsoft.com> and sign in using an account that has been assigned the appropriate audit permissions.</span></span>

2. <span data-ttu-id="d339b-126">Klik in het linkernavigatiedeelvenster van het Microsoft 365 compliancecentrum op **Alles weergeven** en klik vervolgens op **Controleren.**</span><span class="sxs-lookup"><span data-stu-id="d339b-126">In the left navigation pane of the Microsoft 365 compliance center, click **Show all** and then click **Audit**.</span></span>

3. <span data-ttu-id="d339b-127">Configureer **de zoekopdracht** op de pagina Controle met behulp van de volgende voorwaarden op het **tabblad** Zoeken.</span><span class="sxs-lookup"><span data-stu-id="d339b-127">On the **Audit** page, configure the search using the following conditions on the **Search** tab.</span></span> 

   ![Configuratie-instellingen voor zoeken in auditlogboek](../media/AuditLogSearchToolMCCCallouts.png)

   1. <span data-ttu-id="d339b-129">**Datum en tijdbereik.**</span><span class="sxs-lookup"><span data-stu-id="d339b-129">**Date and time range**.</span></span> <span data-ttu-id="d339b-130">Selecteer een bereik voor de datum en tijd om de gebeurtenissen weer te geven die in die periode hebben plaatsgevonden. </span><span class="sxs-lookup"><span data-stu-id="d339b-130">Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="d339b-131">De datum en tijd worden op lokale tijd weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d339b-131">The date and time are presented in local time.</span></span> <span data-ttu-id="d339b-132">De laatste zeven dagen zijn standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="d339b-132">The last seven days are selected by default.</span></span>
  
   2. <span data-ttu-id="d339b-133">**Activiteiten**.</span><span class="sxs-lookup"><span data-stu-id="d339b-133">**Activities**.</span></span> <span data-ttu-id="d339b-134">Selecteer de activiteiten die u wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="d339b-134">Select the activities to search for.</span></span> <span data-ttu-id="d339b-135">Gebruik het zoekvak om te zoeken naar activiteiten die u aan de lijst wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="d339b-135">Use the search box to search for activities to add to the list.</span></span> <span data-ttu-id="d339b-136">Zie Gecontroleerde activiteiten voor een gedeeltelijke lijst met gecontroleerde [activiteiten.](search-the-audit-log-in-security-and-compliance.md#audited-activities)</span><span class="sxs-lookup"><span data-stu-id="d339b-136">For a partial list of audited activities, see [Audited activities](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span> <span data-ttu-id="d339b-137">Laat dit vak leeg als u items wilt retourneren voor alle gecontroleerde activiteiten.</span><span class="sxs-lookup"><span data-stu-id="d339b-137">Leave this box blank to return entries for all audited activities.</span></span>
  
   3. <span data-ttu-id="d339b-138">**Gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="d339b-138">**Users**.</span></span>  <span data-ttu-id="d339b-139">Klik in dit vak en typ de naam van gebruikers om zoekresultaten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d339b-139">Click in this box and start typing the name of users to display search results for.</span></span> <span data-ttu-id="d339b-140">De controlelogboekgegevens voor de geselecteerde activiteiten die worden uitgevoerd door de gebruikers die u in dit vak selecteert, worden weergegeven in de lijst met resultaten.</span><span class="sxs-lookup"><span data-stu-id="d339b-140">The audit log entries for the selected activities performed by the users you select in this box are displayed in the list of results.</span></span> <span data-ttu-id="d339b-141">Laat dit vak leeg als u vermeldingen wilt zien voor alle gebruikers (en serviceaccounts) in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d339b-141">Leave this box blank to return entries for all users (and service accounts) in your organization.</span></span>
  
   4. <span data-ttu-id="d339b-142">**Bestand, map of site**.</span><span class="sxs-lookup"><span data-stu-id="d339b-142">**File, folder, or site**.</span></span> <span data-ttu-id="d339b-143">Typ een of meer bestanden of mappen om te zoeken naar activiteiten die betrekking hebben op het mapbestand dat het opgegeven trefwoord bevat.</span><span class="sxs-lookup"><span data-stu-id="d339b-143">Type some or all of a file or folder name to search for activity related to the file of folder that contains the specified keyword.</span></span> <span data-ttu-id="d339b-144">U kunt ook een URL van een bestand of map opgeven.</span><span class="sxs-lookup"><span data-stu-id="d339b-144">You can also specify a URL of a file or folder.</span></span> <span data-ttu-id="d339b-145">Als u een URL van een bestand of map gebruikt, moet u het volledige URL-pad typen of als u een deel van de URL typt, geen speciale tekens of spaties bevatten.</span><span class="sxs-lookup"><span data-stu-id="d339b-145">If you use a URL of a file or folder, be sure the type the full URL path or if you type a portion of the URL, don't include any special characters or spaces.</span></span> <span data-ttu-id="d339b-146">Laat dit vak leeg als u vermeldingen wilt zien voor alle bestanden en mappen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d339b-146">Leave this box blank to return entries for all files and folders in your organization.</span></span>

4. <span data-ttu-id="d339b-147">Klik **op Zoeken** om de zoekopdracht uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d339b-147">Click **Search** to run the search.</span></span>

<span data-ttu-id="d339b-148">Er wordt een nieuwe pagina weergegeven met de zoekactie in het auditlogboek.</span><span class="sxs-lookup"><span data-stu-id="d339b-148">A new page is display that shows the audit log search is running.</span></span> <span data-ttu-id="d339b-149">Wanneer de zoekopdracht is voltooid, worden auditrecords weergegeven op de pagina.</span><span class="sxs-lookup"><span data-stu-id="d339b-149">When the search is completed, audit records are displayed on the page.</span></span> <span data-ttu-id="d339b-150">Klik op een record om een flyoutpagina met gedetailleerde eigenschappen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d339b-150">Click a record to display a flyout page with detailed properties.</span></span>

<span data-ttu-id="d339b-151">Zie Het auditlogboek in het [compliancecentrum doorzoeken](search-the-audit-log-in-security-and-compliance.md)voor meer gedetailleerde instructies.</span><span class="sxs-lookup"><span data-stu-id="d339b-151">For more detailed instructions, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md).</span></span>
